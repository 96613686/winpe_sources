# FwIcfAuthBypassServicesDestroy

- ea: `0x180006aa0`
- end: `0x180006ab4`
- name: `FwIcfAuthBypassServicesDestroy`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180006ac0`

## pseudocode

```c
__int64 __fastcall FwIcfAuthBypassServicesDestroy(__int64 a1)
{
  return FwArrayDestroy(64, FwIcfAuthBypassServiceDestroy, a1);
}

```

## disassembly

```asm
0x180006aa0  mov     r8, rcx
0x180006aa3  lea     rdx, FwIcfAuthBypassServiceDestroy
0x180006aaa  mov     ecx, 40h ; '@'
0x180006aaf  jmp     FwArrayDestroy
```
