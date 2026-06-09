# CWinTaskClassFactoryT<CPnpRebootHandler,1>::AddRef(void)

- ea: `0x18000b380`
- end: `0x18000b38d`
- name: `?AddRef@?$CWinTaskClassFactoryT@VCPnpRebootHandler@@$00@@UEAAKXZ`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CPnpRebootHandler,1>::AddRef(__int64 a1)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
}

```

## disassembly

```asm
0x18000b380  mov     eax, 1
0x18000b385  lock xadd [rcx+8], eax
0x18000b38a  inc     eax
0x18000b38c  retn
```
