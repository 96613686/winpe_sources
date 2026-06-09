# CWinTaskClassFactoryT<CRegIdleHandler,1>::LockServer(int)

- ea: `0x180001e90`
- end: `0x180001ea7`
- name: `?LockServer@?$CWinTaskClassFactoryT@VCRegIdleHandler@@$00@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180001e90`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CRegIdleHandler,1>::LockServer(__int64 a1, int a2)
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
0x180001e90  test    edx, edx
0x180001e92  jz      short loc_180001E9D
0x180001e94  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180001e9b  jmp     short loc_180001EA4
0x180001e9d  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180001ea4  xor     eax, eax
0x180001ea6  retn
```
