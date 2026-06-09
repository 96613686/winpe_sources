# SdpFreePool

- ea: `0x14001fb74`
- end: `0x14001fb8a`
- name: `SdpFreePool`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x14003468c`
- `0x140034a80`
- `0x140034e38`
- `0x1400350f4`
- `0x140035ab8`
- `0x1400367e4`

## import_xrefs

- `ntoskrnl!ExFreePool` at `0x14001fb78`
- `ntoskrnl!ExFreePool` at `0x14001fb78`

## pseudocode

```c
void __fastcall SdpFreePool(void *a1)
{
  ExFreePool(a1);
}

```

## disassembly

```asm
0x14001fb74  sub     rsp, 28h
0x14001fb78  call    cs:__imp_ExFreePool
0x14001fb7f  nop     dword ptr [rax+rax+00h]
0x14001fb84  add     rsp, 28h
0x14001fb88  retn
```
