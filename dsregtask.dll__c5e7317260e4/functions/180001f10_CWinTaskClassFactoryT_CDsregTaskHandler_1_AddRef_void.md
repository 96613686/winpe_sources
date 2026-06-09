# CWinTaskClassFactoryT<CDsregTaskHandler,1>::AddRef(void)

- ea: `0x180001f10`
- end: `0x180001f1d`
- name: `?AddRef@?$CWinTaskClassFactoryT@VCDsregTaskHandler@@$00@@UEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CDsregTaskHandler,1>::AddRef(__int64 a1)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
}

```

## disassembly

```asm
0x180001f10  mov     eax, 1
0x180001f15  lock xadd [rcx+8], eax
0x180001f1a  inc     eax
0x180001f1c  retn
```
