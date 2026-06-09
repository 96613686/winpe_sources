# FltpAllocateFileListCtrl

- ea: `0x18006c500`
- end: `0x18006c662`
- name: `FltpAllocateFileListCtrl`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800085f0`

## callees

- `0x180014c10`
- `0x180024c00`
- `0x18006c500`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18006c51a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18006c51a`
- `ntoskrnl!ExInitializeAutoExpandPushLock` at `0x18006c5b6`
- `ntoskrnl!ExInitializeAutoExpandPushLock` at `0x18006c5b6`

## pseudocode

```c
__int64 __fastcall FltpAllocateFileListCtrl(__int64 a1, __int64 a2, volatile signed __int32 **a3)
{
  volatile signed __int32 *v6; // rax
  volatile signed __int32 *v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rax
  int v11; // ecx

  v6 = (volatile signed __int32 *)ExAllocateFromNPagedLookasideList(&stru_18003EBC0);
  v7 = v6;
  if ( !v6 )
    return 3221225626LL;
  *((_DWORD *)v6 + 16) = 0;
  *((_QWORD *)v6 + 6) = 0;
  *v6 = 14742018;
  *((_DWORD *)v6 + 17) = 1;
  v8 = *(_QWORD *)(a2 + 24);
  if ( v8 && (*(_BYTE *)(v8 + 7) & 0xF0u) >= 0x10 && *(_QWORD *)(v8 + 80) )
  {
    *((_QWORD *)v6 + 3) = a1;
    v9 = *(_QWORD *)(a2 + 24);
    if ( !v9 || (*(_BYTE *)(v9 + 7) & 0xF0u) < 0x10 || (v10 = *(_QWORD *)(v9 + 80)) == 0 )
      v10 = 0;
    *((_QWORD *)v7 + 4) = v10;
    *((_QWORD *)v7 + 5) = DeleteFileListCtrlCallback;
  }
  else
  {
    *((_QWORD *)v6 + 3) = a1 | 1;
    *((_QWORD *)v6 + 4) = *(_QWORD *)(a2 + 24);
    *((_QWORD *)v6 + 5) = DeleteFileListCtrlCallback;
    if ( (v6[16] & 4) == 0 )
      _InterlockedOr(v6 + 16, 4u);
  }
  ExInitializeAutoExpandPushLock(v7 + 18, 1);
  memset((void *)(v7 + 22), 0, 0x80u);
  *((_QWORD *)v7 + 27) = 0;
  if ( (byte_1800404C2 & 1) != 0 )
    McTemplateU0spdd_EtwWriteTransfer(
      v11,
      (unsigned int)FileListCtrlSup_c732,
      (unsigned int)"FltpAllocateFileListCtrl",
      (_DWORD)v7,
      *((_DWORD *)v7 + 16),
      *((_DWORD *)v7 + 17));
  *a3 = v7;
  return 0;
}

```

## disassembly

```asm
0x18006c500  push    rbx
0x18006c502  push    rsi
0x18006c503  push    rdi
0x18006c504  push    r14
0x18006c506  sub     rsp, 38h
0x18006c50a  mov     rsi, rcx
0x18006c50d  mov     r14, r8
0x18006c510  lea     rcx, stru_18003EBC0; Lookaside
0x18006c517  mov     rdi, rdx
0x18006c51a  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x18006c521  nop     dword ptr [rax+rax+00h]
0x18006c526  mov     rbx, rax
0x18006c529  test    rax, rax
0x18006c52c  jz      loc_18006C5F8
0x18006c532  mov     [rsp+58h+arg_0], rbp
0x18006c537  xor     ebp, ebp
0x18006c539  mov     [rax+40h], ebp
0x18006c53c  mov     [rax+30h], rbp
0x18006c540  mov     dword ptr [rax], 0E0F202h
0x18006c546  mov     dword ptr [rax+44h], 1
0x18006c54d  mov     rcx, [rdi+18h]
0x18006c551  test    rcx, rcx
0x18006c554  jz      loc_18006C608
0x18006c55a  movzx   eax, byte ptr [rcx+7]
0x18006c55e  and     al, 0F0h
0x18006c560  cmp     al, 10h
0x18006c562  jb      loc_18006C608
0x18006c568  cmp     [rcx+50h], rbp
0x18006c56c  jz      loc_18006C608
0x18006c572  mov     [rbx+18h], rsi
0x18006c576  mov     rcx, [rdi+18h]
0x18006c57a  test    rcx, rcx
0x18006c57d  jz      loc_18006C634
0x18006c583  movzx   eax, byte ptr [rcx+7]
0x18006c587  and     al, 0F0h
0x18006c589  cmp     al, 10h
0x18006c58b  jb      loc_18006C634
0x18006c591  mov     rax, [rcx+50h]
0x18006c595  test    rax, rax
0x18006c598  jz      loc_18006C634
0x18006c59e  mov     [rbx+20h], rax
0x18006c5a2  lea     rax, DeleteFileListCtrlCallback
0x18006c5a9  mov     [rbx+28h], rax
0x18006c5ad  lea     rcx, [rbx+48h]
0x18006c5b1  mov     edx, 1
0x18006c5b6  call    cs:__imp_ExInitializeAutoExpandPushLock
0x18006c5bd  nop     dword ptr [rax+rax+00h]
0x18006c5c2  xor     edx, edx; Val
0x18006c5c4  lea     rcx, [rbx+58h]; void *
0x18006c5c8  mov     r8d, 80h; Size
0x18006c5ce  call    memset
0x18006c5d3  mov     [rbx+0D8h], rbp
0x18006c5da  test    cs:byte_1800404C2, 1
0x18006c5e1  mov     rbp, [rsp+58h+arg_0]
0x18006c5e6  jnz     short loc_18006C63C
0x18006c5e8  mov     [r14], rbx
0x18006c5eb  xor     eax, eax
0x18006c5ed  add     rsp, 38h
0x18006c5f1  pop     r14
0x18006c5f3  pop     rdi
0x18006c5f4  pop     rsi
0x18006c5f5  pop     rbx
0x18006c5f6  retn
0x18006c5f8  mov     eax, 0C000009Ah
0x18006c5fd  add     rsp, 38h
0x18006c601  pop     r14
0x18006c603  pop     rdi
0x18006c604  pop     rsi
0x18006c605  pop     rbx
0x18006c606  retn
0x18006c608  or      rsi, 1
0x18006c60c  mov     [rbx+18h], rsi
0x18006c610  mov     rax, [rdi+18h]
0x18006c614  mov     [rbx+20h], rax
0x18006c618  lea     rax, DeleteFileListCtrlCallback
0x18006c61f  mov     [rbx+28h], rax
0x18006c623  mov     eax, [rbx+40h]
0x18006c626  test    al, 4
0x18006c628  jnz     short loc_18006C5AD
0x18006c62a  lock or dword ptr [rbx+40h], 4
0x18006c62f  jmp     loc_18006C5AD
0x18006c634  mov     rax, rbp
0x18006c637  jmp     loc_18006C59E
0x18006c63c  mov     eax, [rbx+44h]
0x18006c63f  lea     r8, aFltpallocatefi; "FltpAllocateFileListCtrl"
0x18006c646  mov     [rsp+58h+var_30], eax
0x18006c64a  lea     rdx, FileListCtrlSup_c732
0x18006c651  mov     eax, [rbx+40h]
0x18006c654  mov     r9, rbx
0x18006c657  mov     [rsp+58h+var_38], eax
0x18006c65b  call    McTemplateU0spdd_EtwWriteTransfer
0x18006c660  jmp     short loc_18006C5E8
```
