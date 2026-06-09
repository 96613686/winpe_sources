# CWinTaskClassFactoryT<CDsregTaskHandler,1>::LockServer(int)

- ea: `0x180002410`
- end: `0x180002427`
- name: `?LockServer@?$CWinTaskClassFactoryT@VCDsregTaskHandler@@$00@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180002410`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CDsregTaskHandler,1>::LockServer(__int64 a1, int a2)
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
0x180002410  test    edx, edx
0x180002412  jz      short loc_18000241D
0x180002414  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000241b  jmp     short loc_180002424
0x18000241d  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180002424  xor     eax, eax
0x180002426  retn
```
