# CWinTaskClassFactoryT<CmCleanupWim,1>::LockServer(int)

- ea: `0x180004d70`
- end: `0x180004d87`
- name: `?LockServer@?$CWinTaskClassFactoryT@VCmCleanupWim@@$00@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180004d70`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CmCleanupWim,1>::LockServer(__int64 a1, int a2)
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
0x180004d70  test    edx, edx
0x180004d72  jz      short loc_180004D7D
0x180004d74  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180004d7b  jmp     short loc_180004D84
0x180004d7d  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180004d84  xor     eax, eax
0x180004d86  retn
```
