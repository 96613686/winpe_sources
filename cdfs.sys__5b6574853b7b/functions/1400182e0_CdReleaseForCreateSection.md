# CdReleaseForCreateSection

- ea: `0x1400182e0`
- end: `0x14001831f`
- name: `CdReleaseForCreateSection`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1400182f8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001830c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400182f8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001830c`

## pseudocode

```c
void __fastcall CdReleaseForCreateSection(__int64 a1)
{
  ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 200LL) + 32LL));
  ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(a1 + 24) + 8LL));
}

```

## disassembly

```asm
0x1400182e0  push    rbx
0x1400182e2  sub     rsp, 20h
0x1400182e6  mov     rax, [rcx+18h]
0x1400182ea  mov     rbx, rcx
0x1400182ed  mov     rcx, [rax+0C8h]
0x1400182f4  add     rcx, 20h ; ' '; Resource
0x1400182f8  call    cs:__imp_ExReleaseResourceLite
0x1400182ff  nop     dword ptr [rax+rax+00h]
0x140018304  mov     rcx, [rbx+18h]
0x140018308  mov     rcx, [rcx+8]; Resource
0x14001830c  call    cs:__imp_ExReleaseResourceLite
0x140018313  nop     dword ptr [rax+rax+00h]
0x140018318  add     rsp, 20h
0x14001831c  pop     rbx
0x14001831d  retn
```
