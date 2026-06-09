# CWinTaskClassFactoryT<CMapsToastTaskHandler,1>::LockServer(int)

- ea: `0x1800042f0`
- end: `0x180004307`
- name: `?LockServer@?$CWinTaskClassFactoryT@VCMapsToastTaskHandler@@$00@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800042f0`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CMapsToastTaskHandler,1>::LockServer(__int64 a1, int a2)
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
0x1800042f0  test    edx, edx
0x1800042f2  jz      short loc_1800042FD
0x1800042f4  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x1800042fb  jmp     short loc_180004304
0x1800042fd  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180004304  xor     eax, eax
0x180004306  retn
```
