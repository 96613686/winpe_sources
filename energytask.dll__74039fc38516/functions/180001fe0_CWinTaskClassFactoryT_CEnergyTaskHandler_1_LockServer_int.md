# CWinTaskClassFactoryT<CEnergyTaskHandler,1>::LockServer(int)

- ea: `0x180001fe0`
- end: `0x180001ff7`
- name: `?LockServer@?$CWinTaskClassFactoryT@VCEnergyTaskHandler@@$00@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180001fe0`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CEnergyTaskHandler,1>::LockServer(__int64 a1, int a2)
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
0x180001fe0  test    edx, edx
0x180001fe2  jz      short loc_180001FED
0x180001fe4  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180001feb  jmp     short loc_180001FF4
0x180001fed  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180001ff4  xor     eax, eax
0x180001ff6  retn
```
