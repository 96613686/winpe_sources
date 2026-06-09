# CdOpenFileFromFileContext

- ea: `0x14000e544`
- end: `0x14000e83c`
- name: `CdOpenFileFromFileContext`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000c8b4`

## callees

- `0x14000d400`
- `0x14000e544`
- `0x1400178c8`
- `0x1400181a4`
- `0x1400184f4`
- `0x140018bec`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14000e60f`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000e704`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000e60f`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000e704`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000e69f`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000e744`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001b72a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000e69f`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000e744`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001b72a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e6b9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e7ef`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b74b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e6b9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e7ef`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b74b`

## pseudocode

```c
NTSTATUS __fastcall CdOpenFileFromFileContext(
        PIRP *a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        __int64 a5,
        char a6,
        char a7,
        __int64 a8,
        __int64 a9)
{
  int v12; // ebx
  __int64 Fcb; // rax
  __int64 v15; // r8
  __int64 v16; // rdi
  int v17; // ecx
  __int64 v18; // rsi
  int v19; // ecx
  int v20; // r9d
  int v21; // r8d
  char v22; // [rsp+20h] [rbp-78h]
  __int64 v23; // [rsp+28h] [rbp-70h]
  char v24; // [rsp+41h] [rbp-57h] BYREF
  int v25; // [rsp+44h] [rbp-54h]
  __int64 v26; // [rsp+48h] [rbp-50h]
  __int64 v27; // [rsp+50h] [rbp-48h]

  v12 = 0;
  v26 = 0;
  v24 = 0;
  v27 = 0;
  if ( (*(_DWORD *)(*(_QWORD *)(a2 + 8) + 16LL) & 0x50156) != 0 )
    return -1073741790;
  if ( *(_WORD *)(a5 + 16) )
    v12 = 8;
  v25 = v12;
  if ( a9 && (*(_DWORD *)(a9 + 4) & 3) != 0 )
  {
    v12 |= 2u;
    v25 = v12;
  }
  if ( a6 )
  {
    v12 |= 4u;
    v25 = v12;
  }
  HIDWORD(v26) = *(_DWORD *)(*a4 + 156);
  LODWORD(v26) = *(_DWORD *)(*(_QWORD *)(a8 + 8) + 32LL);
  ExAcquireFastMutex((PFAST_MUTEX)(a3 + 336));
  *(_QWORD *)(a3 + 392) = KeGetCurrentThread();
  Fcb = CdCreateFcb((__int64)a1, v26, 0x305u, (PVOID *)&v24);
  v16 = Fcb;
  if ( !v24 )
    CdInitializeFcbFromFileContext(a1, Fcb, *a4, a8);
  LOBYTE(v15) = 1;
  if ( !(unsigned __int8)CdAcquireResource(a1, *(_QWORD *)(v16 + 200) + 32LL, v15, 0) )
  {
    ++*(_DWORD *)(v16 + 164);
    *(_QWORD *)(a3 + 392) = 0;
    ExReleaseFastMutex((PFAST_MUTEX)(a3 + 336));
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*a4 + 200) + 32LL));
    CdAcquireResource(a1, *(_QWORD *)(v16 + 200) + 32LL, 0, 0);
    CdAcquireResource(a1, *(_QWORD *)(*a4 + 200) + 32LL, 0, 0);
    ExAcquireFastMutex((PFAST_MUTEX)(a3 + 336));
    *(_QWORD *)(a3 + 392) = KeGetCurrentThread();
    --*(_DWORD *)(v16 + 164);
  }
  *(_QWORD *)(a3 + 392) = 0;
  ExReleaseFastMutex((PFAST_MUTEX)(a3 + 336));
  v18 = *a4;
  v27 = *a4;
  *a4 = v16;
  if ( !a7 )
  {
    if ( *(_WORD *)(a5 + 16) )
      goto LABEL_21;
    CdInsertPrefix(v17, v16, *(_DWORD *)(a8 + 8) + 88, 0, 0, v18);
    if ( !a6 )
      goto LABEL_21;
    v21 = *(_QWORD *)(a8 + 8) + 120;
    v23 = v18;
    v22 = 0;
    goto LABEL_20;
  }
  CdInsertPrefix(v17, v16, a5, 0, 1, v18);
  if ( a6 )
  {
    v23 = v18;
    v22 = 1;
    v21 = a5;
LABEL_20:
    LOBYTE(v20) = 1;
    CdInsertPrefix(v19, v16, v21, v20, v22, v23);
  }
LABEL_21:
  ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v18 + 200) + 32LL));
  v27 = 0;
  return CdCompleteFcbOpen(a1, a2, a3, a4, 4, v12, *(_DWORD *)(*(_QWORD *)(a2 + 8) + 16LL));
}

```

## disassembly

```asm
0x14000e544  mov     rax, rsp
0x14000e547  mov     [rax+18h], r8
0x14000e54b  mov     [rax+10h], rdx
0x14000e54f  mov     [rax+8], rcx
0x14000e553  push    rbx
0x14000e554  push    rsi
0x14000e555  push    rdi
0x14000e556  push    r12
0x14000e558  push    r13
0x14000e55a  push    r14
0x14000e55c  push    r15
0x14000e55e  sub     rsp, 60h
0x14000e562  mov     r14, r9
0x14000e565  mov     r13, r8
0x14000e568  mov     rsi, rcx
0x14000e56b  xor     ecx, ecx
0x14000e56d  mov     ebx, ecx
0x14000e56f  mov     [rax-50h], rcx
0x14000e573  mov     [rax-58h], cl
0x14000e576  mov     [rax-57h], cl
0x14000e579  mov     [rax-48h], rcx
0x14000e57d  mov     rax, [rdx+8]
0x14000e581  test    dword ptr [rax+10h], 50156h
0x14000e588  jz      short loc_14000E5A0
0x14000e58a  mov     eax, 0C0000022h
0x14000e58f  add     rsp, 60h
0x14000e593  pop     r15
0x14000e595  pop     r14
0x14000e597  pop     r13
0x14000e599  pop     r12
0x14000e59b  pop     rdi
0x14000e59c  pop     rsi
0x14000e59d  pop     rbx
0x14000e59e  retn
0x14000e5a0  mov     r15, [rsp+98h+arg_20]
0x14000e5a8  mov     eax, 8
0x14000e5ad  cmp     [r15+10h], cx
0x14000e5b2  cmovnz  ebx, eax
0x14000e5b5  mov     [rsp+98h+var_54], ebx
0x14000e5b9  mov     rax, [rsp+98h+arg_40]
0x14000e5c1  test    rax, rax
0x14000e5c4  jz      short loc_14000E5D4
0x14000e5c6  mov     eax, [rax+4]
0x14000e5c9  test    al, 3
0x14000e5cb  jz      short loc_14000E5D4
0x14000e5cd  or      ebx, 2
0x14000e5d0  mov     [rsp+98h+var_54], ebx
0x14000e5d4  mov     r12b, [rsp+98h+arg_28]
0x14000e5dc  test    r12b, r12b
0x14000e5df  jz      short loc_14000E5E8
0x14000e5e1  or      ebx, 4
0x14000e5e4  mov     [rsp+98h+var_54], ebx
0x14000e5e8  mov     rax, [r9]
0x14000e5eb  mov     ecx, [rax+9Ch]
0x14000e5f1  mov     dword ptr [rsp+98h+var_50+4], ecx
0x14000e5f5  mov     rax, [rsp+98h+arg_38]
0x14000e5fd  mov     rax, [rax+8]
0x14000e601  mov     ecx, [rax+20h]
0x14000e604  mov     dword ptr [rsp+98h+var_50], ecx
0x14000e608  lea     rcx, [r8+150h]; FastMutex
0x14000e60f  call    cs:__imp_ExAcquireFastMutex
0x14000e616  nop     dword ptr [rax+rax+00h]
0x14000e61b  mov     rax, gs:188h
0x14000e624  mov     [r13+188h], rax
0x14000e62b  mov     [rsp+98h+var_58], 1
0x14000e630  mov     r8d, 305h
0x14000e636  lea     r9, [rsp+98h+var_57]
0x14000e63b  mov     rdx, [rsp+98h+var_50]
0x14000e640  mov     rcx, rsi
0x14000e643  call    CdCreateFcb
0x14000e648  mov     rdi, rax
0x14000e64b  cmp     [rsp+98h+var_57], 0
0x14000e650  jnz     short loc_14000E668
0x14000e652  mov     r9, [rsp+98h+arg_38]
0x14000e65a  mov     r8, [r14]
0x14000e65d  mov     rdx, rax
0x14000e660  mov     rcx, rsi
0x14000e663  call    CdInitializeFcbFromFileContext
0x14000e668  mov     rdx, [rdi+0C8h]
0x14000e66f  add     rdx, 20h ; ' '
0x14000e673  xor     r9d, r9d
0x14000e676  mov     r8b, 1
0x14000e679  mov     rcx, rsi
0x14000e67c  call    CdAcquireResource
0x14000e681  xor     ecx, ecx
0x14000e683  test    al, al
0x14000e685  jnz     loc_14000E736
0x14000e68b  inc     dword ptr [rdi+0A4h]
0x14000e691  mov     [r13+188h], rcx
0x14000e698  lea     rcx, [r13+150h]; FastMutex
0x14000e69f  call    cs:__imp_ExReleaseFastMutex
0x14000e6a6  nop     dword ptr [rax+rax+00h]
0x14000e6ab  mov     rax, [r14]
0x14000e6ae  mov     rcx, [rax+0C8h]
0x14000e6b5  add     rcx, 20h ; ' '; Resource
0x14000e6b9  call    cs:__imp_ExReleaseResourceLite
0x14000e6c0  nop     dword ptr [rax+rax+00h]
0x14000e6c5  mov     rdx, [rdi+0C8h]
0x14000e6cc  add     rdx, 20h ; ' '
0x14000e6d0  xor     r9d, r9d
0x14000e6d3  xor     r8d, r8d
0x14000e6d6  mov     rcx, rsi
0x14000e6d9  call    CdAcquireResource
0x14000e6de  mov     rax, [r14]
0x14000e6e1  mov     rdx, [rax+0C8h]
0x14000e6e8  add     rdx, 20h ; ' '
0x14000e6ec  xor     r9d, r9d
0x14000e6ef  xor     r8d, r8d
0x14000e6f2  mov     rcx, rsi
0x14000e6f5  call    CdAcquireResource
0x14000e6fa  lea     rsi, [r13+150h]
0x14000e701  mov     rcx, rsi; FastMutex
0x14000e704  call    cs:__imp_ExAcquireFastMutex
0x14000e70b  nop     dword ptr [rax+rax+00h]
0x14000e710  mov     rax, gs:188h
0x14000e719  mov     [r13+188h], rax
0x14000e720  dec     dword ptr [rdi+0A4h]
0x14000e726  mov     qword ptr [r13+188h], 0
0x14000e731  mov     rcx, rsi
0x14000e734  jmp     short loc_14000E744
0x14000e736  mov     [r13+188h], rcx
0x14000e73d  lea     rcx, [r13+150h]; FastMutex
0x14000e744  call    cs:__imp_ExReleaseFastMutex
0x14000e74b  nop     dword ptr [rax+rax+00h]
0x14000e750  xor     eax, eax
0x14000e752  mov     [rsp+98h+var_58], al
0x14000e756  mov     rsi, [r14]
0x14000e759  mov     [rsp+98h+var_48], rsi
0x14000e75e  mov     [r14], rdi
0x14000e761  cmp     [rsp+98h+arg_30], al
0x14000e768  jz      short loc_14000E796
0x14000e76a  mov     qword ptr [rsp+98h+var_70], rsi
0x14000e76f  mov     [rsp+98h+var_78], 1
0x14000e774  xor     r9d, r9d
0x14000e777  mov     r8, r15
0x14000e77a  mov     rdx, rdi
0x14000e77d  call    CdInsertPrefix
0x14000e782  test    r12b, r12b
0x14000e785  jz      short loc_14000E7E4
0x14000e787  mov     qword ptr [rsp+98h+var_70], rsi
0x14000e78c  mov     [rsp+98h+var_78], 1
0x14000e791  mov     r8, r15
0x14000e794  jmp     short loc_14000E7D9
0x14000e796  cmp     [r15+10h], ax
0x14000e79b  jnz     short loc_14000E7E4
0x14000e79d  mov     r15, [rsp+98h+arg_38]
0x14000e7a5  mov     r8, [r15+8]
0x14000e7a9  add     r8, 58h ; 'X'
0x14000e7ad  mov     qword ptr [rsp+98h+var_70], rsi
0x14000e7b2  mov     [rsp+98h+var_78], al
0x14000e7b6  xor     r9d, r9d
0x14000e7b9  mov     rdx, rdi
0x14000e7bc  call    CdInsertPrefix
0x14000e7c1  xor     eax, eax
0x14000e7c3  test    r12b, r12b
0x14000e7c6  jz      short loc_14000E7E4
0x14000e7c8  mov     r8, [r15+8]
0x14000e7cc  add     r8, 78h ; 'x'
0x14000e7d0  mov     qword ptr [rsp+98h+var_70], rsi
0x14000e7d5  mov     [rsp+98h+var_78], al
0x14000e7d9  mov     r9b, 1
0x14000e7dc  mov     rdx, rdi
0x14000e7df  call    CdInsertPrefix
0x14000e7e4  mov     rcx, [rsi+0C8h]
0x14000e7eb  add     rcx, 20h ; ' '; Resource
0x14000e7ef  call    cs:__imp_ExReleaseResourceLite
0x14000e7f6  nop     dword ptr [rax+rax+00h]
0x14000e7fb  mov     [rsp+98h+var_48], 0
0x14000e804  mov     rdx, [rsp+98h+arg_8]
0x14000e80c  mov     rax, [rdx+8]
0x14000e810  mov     ecx, [rax+10h]
0x14000e813  mov     [rsp+98h+DesiredAccess], ecx; DesiredAccess
0x14000e817  mov     [rsp+98h+var_70], ebx; int
0x14000e81b  mov     dword ptr [rsp+98h+var_78], 4; int
0x14000e823  mov     r9, r14
0x14000e826  mov     r8, r13
0x14000e829  mov     rcx, [rsp+98h+Context]; Context
0x14000e831  call    CdCompleteFcbOpen
0x14000e836  nop
0x14000e837  jmp     loc_14000E58F
0x14001b702  push    rbp
0x14001b704  sub     rsp, 40h
0x14001b708  mov     rbp, rdx
0x14001b70b  cmp     byte ptr [rbp+40h], 0
0x14001b70f  jz      short loc_14001B737
0x14001b711  mov     rcx, [rbp+0B0h]
0x14001b718  mov     qword ptr [rcx+188h], 0
0x14001b723  add     rcx, 150h; FastMutex
0x14001b72a  call    cs:__imp_ExReleaseFastMutex
0x14001b731  nop     dword ptr [rax+rax+00h]
0x14001b736  nop
0x14001b737  mov     rcx, [rbp+50h]
0x14001b73b  test    rcx, rcx
0x14001b73e  jz      short loc_14001B758
0x14001b740  mov     rcx, [rcx+0C8h]
0x14001b747  add     rcx, 20h ; ' '; Resource
0x14001b74b  call    cs:__imp_ExReleaseResourceLite
0x14001b752  nop     dword ptr [rax+rax+00h]
0x14001b757  nop
0x14001b758  add     rsp, 40h
0x14001b75c  pop     rbp
0x14001b75d  retn
```
