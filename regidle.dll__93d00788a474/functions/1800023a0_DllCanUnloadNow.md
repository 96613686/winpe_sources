# DllCanUnloadNow

- ea: `0x1800023a0`
- end: `0x1800023b2`
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
0x1800023a0  xor     ecx, ecx
0x1800023a2  xor     eax, eax
0x1800023a4  lock cmpxchg cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x1800023ac  mov     eax, ecx
0x1800023ae  setnz   al
0x1800023b1  retn
```
