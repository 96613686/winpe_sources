# DllCanUnloadNow

- ea: `0x1800033f0`
- end: `0x180003402`
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
0x1800033f0  xor     ecx, ecx
0x1800033f2  xor     eax, eax
0x1800033f4  lock cmpxchg cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x1800033fc  mov     eax, ecx
0x1800033fe  setnz   al
0x180003401  retn
```
