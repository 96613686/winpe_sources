# CWinTaskClassFactoryT<CMapsUpdateTaskHandler,1>::LockServer(int)

- ea: `0x180004fc0`
- end: `0x180004fd7`
- name: `?LockServer@?$CWinTaskClassFactoryT@VCMapsUpdateTaskHandler@@$00@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180004fc0`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CMapsUpdateTaskHandler,1>::LockServer(__int64 a1, int a2)
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
0x180004fc0  test    edx, edx
0x180004fc2  jz      short loc_180004FCD
0x180004fc4  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180004fcb  jmp     short loc_180004FD4
0x180004fcd  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180004fd4  xor     eax, eax
0x180004fd6  retn
```
