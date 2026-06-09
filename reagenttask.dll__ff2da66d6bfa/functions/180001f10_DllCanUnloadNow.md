# DllCanUnloadNow

- ea: `0x180001f10`
- end: `0x180001f22`
- name: `DllCanUnloadNow`
- size: `18`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return _InterlockedCompareExchange(&CWinTaskHandler::s_cInstances, 0, 0) != 0;
}

```

## disassembly

```asm
0x180001f10  xor     ecx, ecx
0x180001f12  xor     eax, eax
0x180001f14  lock cmpxchg cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x180001f1c  setnz   cl
0x180001f1f  mov     eax, ecx
0x180001f21  retn
```
