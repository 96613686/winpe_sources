# CWinTaskClassFactoryT<CEnergyTaskHandler,1>::AddRef(void)

- ea: `0x180001b60`
- end: `0x180001b6d`
- name: `?AddRef@?$CWinTaskClassFactoryT@VCEnergyTaskHandler@@$00@@UEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CEnergyTaskHandler,1>::AddRef(__int64 a1)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
}

```

## disassembly

```asm
0x180001b60  mov     eax, 1
0x180001b65  lock xadd [rcx+8], eax
0x180001b6a  inc     eax
0x180001b6c  retn
```
