# CWinTaskClassFactoryT<AOMDHandler,1>::LockServer(int)

- ea: `0x18001d2f0`
- end: `0x18001d307`
- name: `?LockServer@?$CWinTaskClassFactoryT@VAOMDHandler@@$00@@UEAAJH@Z`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18001d2f0`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<AOMDHandler,1>::LockServer(__int64 a1, int a2)
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
0x18001d2f0  test    edx, edx
0x18001d2f2  jz      short loc_18001D2FD
0x18001d2f4  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18001d2fb  jmp     short loc_18001D304
0x18001d2fd  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18001d304  xor     eax, eax
0x18001d306  retn
```
