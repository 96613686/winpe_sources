# CWinTaskClassFactoryT<CMapsUpdateTaskHandler,1>::AddRef(void)

- ea: `0x180003b80`
- end: `0x180003b8d`
- name: `?AddRef@?$CWinTaskClassFactoryT@VCMapsUpdateTaskHandler@@$00@@UEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, installer_update`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CMapsUpdateTaskHandler,1>::AddRef(__int64 a1)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
}

```

## disassembly

```asm
0x180003b80  mov     eax, 1
0x180003b85  lock xadd [rcx+8], eax
0x180003b8a  inc     eax
0x180003b8c  retn
```
