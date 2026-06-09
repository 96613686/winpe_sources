# PendingCallDelete

- ea: `0x180026670`
- end: `0x1800266ad`
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

- `0x180026670`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x18002669a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x18002669a`
- `ntoskrnl!ExFreePoolWithTag` at `0x180026684`
- `ntoskrnl!ExFreePoolWithTag` at `0x180026684`

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
0x180026670  push    rbx
0x180026672  sub     rsp, 20h
0x180026676  mov     rbx, rcx
0x180026679  mov     rcx, [rcx+10h]; P
0x18002667d  test    rcx, rcx
0x180026680  jz      short loc_180026690
0x180026682  xor     edx, edx; Tag
0x180026684  call    cs:__imp_ExFreePoolWithTag
0x18002668b  nop     dword ptr [rax+rax+00h]
0x180026690  mov     rdx, rbx; Entry
0x180026693  lea     rcx, stru_180019720; Lookaside
0x18002669a  call    cs:__imp_ExFreeToLookasideListEx
0x1800266a1  nop     dword ptr [rax+rax+00h]
0x1800266a6  add     rsp, 20h
0x1800266aa  pop     rbx
0x1800266ab  retn
```
