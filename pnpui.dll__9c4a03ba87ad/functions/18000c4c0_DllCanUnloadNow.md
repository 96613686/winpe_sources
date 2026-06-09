# DllCanUnloadNow

- ea: `0x18000c4c0`
- end: `0x18000c4d2`
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
0x18000c4c0  xor     ecx, ecx
0x18000c4c2  xor     eax, eax
0x18000c4c4  lock cmpxchg cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x18000c4cc  mov     eax, ecx
0x18000c4ce  setnz   al
0x18000c4d1  retn
```
