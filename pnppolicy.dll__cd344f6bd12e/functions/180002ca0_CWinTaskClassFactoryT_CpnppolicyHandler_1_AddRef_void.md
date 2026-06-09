# CWinTaskClassFactoryT<CpnppolicyHandler,1>::AddRef(void)

- ea: `0x180002ca0`
- end: `0x180002cad`
- name: `?AddRef@?$CWinTaskClassFactoryT@VCpnppolicyHandler@@$00@@UEAAKXZ`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CpnppolicyHandler,1>::AddRef(__int64 a1)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
}

```

## disassembly

```asm
0x180002ca0  mov     eax, 1
0x180002ca5  lock xadd [rcx+8], eax
0x180002caa  inc     eax
0x180002cac  retn
```
