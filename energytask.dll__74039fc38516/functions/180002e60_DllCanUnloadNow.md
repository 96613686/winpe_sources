# DllCanUnloadNow

- ea: `0x180002e60`
- end: `0x180002e72`
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
0x180002e60  xor     ecx, ecx
0x180002e62  xor     eax, eax
0x180002e64  lock cmpxchg cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x180002e6c  mov     eax, ecx
0x180002e6e  setnz   al
0x180002e71  retn
```
