# CWinTaskClassFactoryT<CReAgentTaskHandler,1>::LockServer(int)

- ea: `0x180001b20`
- end: `0x180001b37`
- name: `?LockServer@?$CWinTaskClassFactoryT@VCReAgentTaskHandler@@$00@@UEAAJH@Z`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180001b20`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CReAgentTaskHandler,1>::LockServer(__int64 a1, int a2)
{
  if ( a2 )
    _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  else
    _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  return 0;
}

```

## disassembly

```asm
0x180001b20  test    edx, edx
0x180001b22  jz      short loc_180001B2D
0x180001b24  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180001b2b  jmp     short loc_180001B34
0x180001b2d  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180001b34  xor     eax, eax
0x180001b36  retn
```
