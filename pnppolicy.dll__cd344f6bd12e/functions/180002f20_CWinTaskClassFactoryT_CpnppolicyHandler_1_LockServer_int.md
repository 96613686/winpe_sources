# CWinTaskClassFactoryT<CpnppolicyHandler,1>::LockServer(int)

- ea: `0x180002f20`
- end: `0x180002f37`
- name: `?LockServer@?$CWinTaskClassFactoryT@VCpnppolicyHandler@@$00@@UEAAJH@Z`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180002f20`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CpnppolicyHandler,1>::LockServer(__int64 a1, int a2)
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
0x180002f20  test    edx, edx
0x180002f22  jz      short loc_180002F2D
0x180002f24  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180002f2b  jmp     short loc_180002F34
0x180002f2d  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180002f34  xor     eax, eax
0x180002f36  retn
```
