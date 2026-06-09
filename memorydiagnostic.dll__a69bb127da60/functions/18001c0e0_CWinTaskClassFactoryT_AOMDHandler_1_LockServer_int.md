# CWinTaskClassFactoryT<AOMDHandler,1>::LockServer(int)

- ea: `0x18001c0e0`
- end: `0x18001c0f7`
- name: `?LockServer@?$CWinTaskClassFactoryT@VAOMDHandler@@$00@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18001c0e0`

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
0x18001c0e0  test    edx, edx
0x18001c0e2  jz      short loc_18001C0ED
0x18001c0e4  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18001c0eb  jmp     short loc_18001C0F4
0x18001c0ed  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18001c0f4  xor     eax, eax
0x18001c0f6  retn
```
