# TodoList-9
TodoList.sol
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract TodoList {
    struct Task {
        uint256 id;
        string content;
        bool completed;
    }

    Task[] public tasks;
    uint256 public taskCount;

    function createTask(string memory _content) public {
        tasks.push(Task(taskCount, _content, false));
        taskCount++;
    }

    function toggleCompleted(uint256 _id) public {
        require(_id < tasks.length, "Task does not exist");
        tasks[_id].completed = !tasks[_id].completed;
    }
}
