# CWinTaskClassFactoryT<CPnpRebootHandler,1>::LockServer(int)

- ea: `0x18000b6f0`
- end: `0x18000b707`
- name: `?LockServer@?$CWinTaskClassFactoryT@VCPnpRebootHandler@@$00@@UEAAJH@Z`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000b6f0`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CPnpRebootHandler,1>::LockServer(__int64 a1, int a2)
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
0x18000b6f0  test    edx, edx
0x18000b6f2  jz      short loc_18000B6FD
0x18000b6f4  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000b6fb  jmp     short loc_18000B704
0x18000b6fd  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000b704  xor     eax, eax
0x18000b706  retn
```
