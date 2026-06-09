# std::vector<std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>>,std::allocator<std::unique_ptr<TimerQueue::TimerQueueParam,std::default_delete<TimerQueue::TimerQueueParam>>>>::_Xlength(void)

- ea: `0x180010d54`
- end: `0x180010d66`
- name: `?_Xlength@?$vector@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@V?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@2@@std@@CAXXZ`
- size: `18`
- prototype: `void __noreturn()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180009c38`
- `0x18000a10c`
- `0x1800114f8`
- `0x18001167c`
- `0x180013168`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180010d5f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180010d5f`

## pseudocode

```c
void __noreturn std::vector<std::unique_ptr<TimerQueue::TimerQueueParam>>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x180010d54  sub     rsp, 28h
0x180010d58  lea     rcx, aVectorTooLong; "vector too long"
0x180010d5f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
