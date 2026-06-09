# PendingCallDelete

- ea: `0x1800266c0`
- end: `0x1800266fd`
- name: `PendingCallDelete`
- size: `61`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180001fa0`
- `0x1800075c4`

## callees

- `0x1800266c0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x1800266ea`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1800266ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800266d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800266d4`

## pseudocode

```c
void __fastcall PendingCallDelete(_QWORD *Entry)
{
  void *v2; // rcx

  v2 = (void *)Entry[2];
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
  ExFreeToLookasideListEx(&stru_180019720, Entry);
}

```

## disassembly

```asm
0x1800266c0  push    rbx
0x1800266c2  sub     rsp, 20h
0x1800266c6  mov     rbx, rcx
0x1800266c9  mov     rcx, [rcx+10h]; P
0x1800266cd  test    rcx, rcx
0x1800266d0  jz      short loc_1800266E0
0x1800266d2  xor     edx, edx; Tag
0x1800266d4  call    cs:__imp_ExFreePoolWithTag
0x1800266db  nop     dword ptr [rax+rax+00h]
0x1800266e0  mov     rdx, rbx; Entry
0x1800266e3  lea     rcx, stru_180019720; Lookaside
0x1800266ea  call    cs:__imp_ExFreeToLookasideListEx
0x1800266f1  nop     dword ptr [rax+rax+00h]
0x1800266f6  add     rsp, 20h
0x1800266fa  pop     rbx
0x1800266fb  retn
```
