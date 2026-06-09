# CdOpenDirectoryFromPathEntry

- ea: `0x14000e1d0`
- end: `0x14000e49a`
- name: `CdOpenDirectoryFromPathEntry`
- size: `714`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int64 *, __int64, char, char, __int64, char, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000c8b4`

## callees

- `0x14000d400`
- `0x14000e1d0`
- `0x1400178c8`
- `0x1400181a4`
- `0x1400184f4`
- `0x140018f0c`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14000e28d`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000e37c`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000e28d`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000e37c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000e317`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000e3ac`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001b6c7`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000e317`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000e3ac`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001b6c7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e331`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e43e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b6e8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e331`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e43e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b6e8`

## pseudocode

```c
__int64 __fastcall CdOpenDirectoryFromPathEntry(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        __int64 a5,
        char a6,
        char a7,
        __int64 a8,
        char a9,
        __int64 a10)
{
  int v13; // ebx
  __int64 Fcb; // rax
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // rdi
  char v19; // al
  struct _FAST_MUTEX *v20; // rcx
  int v21; // ecx
  __int64 v22; // rsi
  int v23; // ecx
  int v24; // r9d
  int v25; // r8d
  char v26; // [rsp+20h] [rbp-78h]
  __int64 v27; // [rsp+28h] [rbp-70h]
  char v28[3]; // [rsp+41h] [rbp-57h] BYREF
  int v29; // [rsp+44h] [rbp-54h]
  unsigned int v30; // [rsp+48h] [rbp-50h]
  __int64 v31; // [rsp+50h] [rbp-48h]
  __int64 v32; // [rsp+58h] [rbp-40h]

  v13 = 0;
  v28[0] = 0;
  v32 = 0;
  v30 = 0;
  if ( a9 && (*(_DWORD *)(*(_QWORD *)(a2 + 8) + 16LL) & 0x50156) != 0 )
    return 3221225506LL;
  if ( a10 )
  {
    if ( (*(_BYTE *)(a10 + 4) & 3) != 0 )
      v13 = 2;
    v29 = v13;
  }
  if ( a6 )
  {
    v13 |= 4u;
    v29 = v13;
  }
  v31 = 0;
  HIDWORD(v31) = *(_DWORD *)(a8 + 4);
  LODWORD(v31) = 0x80000000;
  ExAcquireFastMutex((PFAST_MUTEX)(a3 + 336));
  *(_QWORD *)(a3 + 392) = KeGetCurrentThread();
  Fcb = CdCreateFcb(a1, v31, 772, v28);
  v18 = Fcb;
  if ( !v28[0] )
    CdInitializeFcbFromPathEntry(v16, Fcb, *a4, a8);
  LOBYTE(v17) = 1;
  v19 = CdAcquireResource(a1, *(_QWORD *)(v18 + 200) + 32LL, v17, 0);
  v20 = (struct _FAST_MUTEX *)(a3 + 336);
  if ( !v19 )
  {
    ++*(_DWORD *)(v18 + 164);
    *(_QWORD *)(a3 + 392) = 0;
    ExReleaseFastMutex(v20);
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*a4 + 200) + 32LL));
    CdAcquireResource(a1, *(_QWORD *)(v18 + 200) + 32LL, 0, 0);
    CdAcquireResource(a1, *(_QWORD *)(*a4 + 200) + 32LL, 0, 0);
    ExAcquireFastMutex((PFAST_MUTEX)(a3 + 336));
    *(_QWORD *)(a3 + 392) = KeGetCurrentThread();
    --*(_DWORD *)(v18 + 164);
    v20 = (struct _FAST_MUTEX *)(a3 + 336);
  }
  *(_QWORD *)(a3 + 392) = 0;
  ExReleaseFastMutex(v20);
  v32 = *a4;
  v22 = v32;
  *a4 = v18;
  if ( a7 )
  {
    CdInsertPrefix(v21, v18, a5, 0, 1, v22);
    if ( !a6 )
      goto LABEL_20;
    v27 = v22;
    v26 = 1;
    v25 = a5;
  }
  else
  {
    CdInsertPrefix(v21, v18, a8 + 40, 0, 0, v22);
    if ( !a6 )
      goto LABEL_20;
    v25 = a8 + 72;
    v27 = v22;
    v26 = 0;
  }
  LOBYTE(v24) = 1;
  CdInsertPrefix(v23, v18, v25, v24, v26, v27);
LABEL_20:
  ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v22 + 200) + 32LL));
  v32 = 0;
  if ( a9 )
    return CdCompleteFcbOpen(a1, 3, v13, *(_DWORD *)(*(_QWORD *)(a2 + 8) + 16LL));
  else
    return v30;
}

```

## disassembly

```asm
0x14000e1d0  mov     r11, rsp
0x14000e1d3  mov     [r11+18h], r8
0x14000e1d7  mov     [r11+10h], rdx
0x14000e1db  mov     [r11+8], rcx
0x14000e1df  push    rbx
0x14000e1e0  push    rsi
0x14000e1e1  push    rdi
0x14000e1e2  push    r12
0x14000e1e4  push    r13
0x14000e1e6  push    r14
0x14000e1e8  push    r15
0x14000e1ea  sub     rsp, 60h
0x14000e1ee  mov     r15, r9
0x14000e1f1  mov     r14, r8
0x14000e1f4  mov     rax, rdx
0x14000e1f7  mov     rsi, rcx
0x14000e1fa  xor     ecx, ecx
0x14000e1fc  mov     ebx, ecx
0x14000e1fe  mov     [rsp+98h+var_58], cl
0x14000e202  mov     [rsp+98h+var_57], cl
0x14000e206  mov     [r11-40h], rcx
0x14000e20a  mov     [rsp+98h+var_50], ecx
0x14000e20e  cmp     [rsp+98h+arg_40], cl
0x14000e215  jz      short loc_14000E23A
0x14000e217  mov     rax, [rdx+8]
0x14000e21b  test    dword ptr [rax+10h], 50156h
0x14000e222  jz      short loc_14000E23A
0x14000e224  mov     eax, 0C0000022h
0x14000e229  add     rsp, 60h
0x14000e22d  pop     r15
0x14000e22f  pop     r14
0x14000e231  pop     r13
0x14000e233  pop     r12
0x14000e235  pop     rdi
0x14000e236  pop     rsi
0x14000e237  pop     rbx
0x14000e238  retn
0x14000e23a  mov     rax, [rsp+98h+arg_48]
0x14000e242  test    rax, rax
0x14000e245  jz      short loc_14000E257
0x14000e247  test    byte ptr [rax+4], 3
0x14000e24b  mov     eax, 2
0x14000e250  cmovnz  ebx, eax
0x14000e253  mov     [rsp+98h+var_54], ebx
0x14000e257  mov     r12b, [rsp+98h+arg_28]
0x14000e25f  test    r12b, r12b
0x14000e262  jz      short loc_14000E26B
0x14000e264  or      ebx, 4
0x14000e267  mov     [rsp+98h+var_54], ebx
0x14000e26b  mov     [rsp+98h+var_48], rcx
0x14000e270  mov     r13, [rsp+98h+arg_38]
0x14000e278  mov     eax, [r13+4]
0x14000e27c  mov     dword ptr [rsp+98h+var_48+4], eax
0x14000e280  bts     dword ptr [rsp+98h+var_48], 1Fh
0x14000e286  lea     rcx, [r8+150h]; FastMutex
0x14000e28d  call    cs:__imp_ExAcquireFastMutex
0x14000e294  nop     dword ptr [rax+rax+00h]
0x14000e299  mov     rax, gs:188h
0x14000e2a2  mov     [r14+188h], rax
0x14000e2a9  mov     [rsp+98h+var_58], 1
0x14000e2ae  mov     r8d, 304h
0x14000e2b4  lea     r9, [rsp+98h+var_57]
0x14000e2b9  mov     rdx, [rsp+98h+var_48]
0x14000e2be  mov     rcx, rsi
0x14000e2c1  call    CdCreateFcb
0x14000e2c6  mov     rdi, rax
0x14000e2c9  cmp     [rsp+98h+var_57], 0
0x14000e2ce  jnz     short loc_14000E2DE
0x14000e2d0  mov     r9, r13
0x14000e2d3  mov     r8, [r15]
0x14000e2d6  mov     rdx, rax
0x14000e2d9  call    CdInitializeFcbFromPathEntry
0x14000e2de  mov     rdx, [rdi+0C8h]
0x14000e2e5  add     rdx, 20h ; ' '
0x14000e2e9  xor     r9d, r9d
0x14000e2ec  mov     r8b, 1
0x14000e2ef  mov     rcx, rsi
0x14000e2f2  call    CdAcquireResource
0x14000e2f7  lea     rcx, [r14+150h]; FastMutex
0x14000e2fe  test    al, al
0x14000e300  jnz     loc_14000E3A1
0x14000e306  inc     dword ptr [rdi+0A4h]
0x14000e30c  mov     qword ptr [r14+188h], 0
0x14000e317  call    cs:__imp_ExReleaseFastMutex
0x14000e31e  nop     dword ptr [rax+rax+00h]
0x14000e323  mov     rax, [r15]
0x14000e326  mov     rcx, [rax+0C8h]
0x14000e32d  add     rcx, 20h ; ' '; Resource
0x14000e331  call    cs:__imp_ExReleaseResourceLite
0x14000e338  nop     dword ptr [rax+rax+00h]
0x14000e33d  mov     rdx, [rdi+0C8h]
0x14000e344  add     rdx, 20h ; ' '
0x14000e348  xor     r9d, r9d
0x14000e34b  xor     r8d, r8d
0x14000e34e  mov     rcx, rsi
0x14000e351  call    CdAcquireResource
0x14000e356  mov     rax, [r15]
0x14000e359  mov     rdx, [rax+0C8h]
0x14000e360  add     rdx, 20h ; ' '
0x14000e364  xor     r9d, r9d
0x14000e367  xor     r8d, r8d
0x14000e36a  mov     rcx, rsi
0x14000e36d  call    CdAcquireResource
0x14000e372  lea     rsi, [r14+150h]
0x14000e379  mov     rcx, rsi; FastMutex
0x14000e37c  call    cs:__imp_ExAcquireFastMutex
0x14000e383  nop     dword ptr [rax+rax+00h]
0x14000e388  mov     rax, gs:188h
0x14000e391  mov     [r14+188h], rax
0x14000e398  dec     dword ptr [rdi+0A4h]
0x14000e39e  mov     rcx, rsi; FastMutex
0x14000e3a1  mov     qword ptr [r14+188h], 0
0x14000e3ac  call    cs:__imp_ExReleaseFastMutex
0x14000e3b3  nop     dword ptr [rax+rax+00h]
0x14000e3b8  xor     eax, eax
0x14000e3ba  mov     [rsp+98h+var_58], al
0x14000e3be  mov     rsi, [r15]
0x14000e3c1  mov     [rsp+98h+var_40], rsi
0x14000e3c6  mov     [r15], rdi
0x14000e3c9  mov     qword ptr [rsp+98h+var_70], rsi
0x14000e3ce  xor     r9d, r9d
0x14000e3d1  mov     rdx, rdi
0x14000e3d4  cmp     [rsp+98h+arg_30], al
0x14000e3db  jz      short loc_14000E408
0x14000e3dd  mov     [rsp+98h+var_78], 1
0x14000e3e2  mov     r8, [rsp+98h+arg_20]
0x14000e3ea  call    CdInsertPrefix
0x14000e3ef  test    r12b, r12b
0x14000e3f2  jz      short loc_14000E433
0x14000e3f4  mov     qword ptr [rsp+98h+var_70], rsi
0x14000e3f9  mov     [rsp+98h+var_78], 1
0x14000e3fe  mov     r8, [rsp+98h+arg_20]
0x14000e406  jmp     short loc_14000E428
0x14000e408  lea     r8, [r13+28h]
0x14000e40c  mov     [rsp+98h+var_78], al
0x14000e410  call    CdInsertPrefix
0x14000e415  test    r12b, r12b
0x14000e418  jz      short loc_14000E433
0x14000e41a  lea     r8, [r13+48h]
0x14000e41e  mov     qword ptr [rsp+98h+var_70], rsi
0x14000e423  mov     [rsp+98h+var_78], 0
0x14000e428  mov     r9b, 1
0x14000e42b  mov     rdx, rdi
0x14000e42e  call    CdInsertPrefix
0x14000e433  mov     rcx, [rsi+0C8h]
0x14000e43a  add     rcx, 20h ; ' '; Resource
0x14000e43e  call    cs:__imp_ExReleaseResourceLite
0x14000e445  nop     dword ptr [rax+rax+00h]
0x14000e44a  mov     [rsp+98h+var_40], 0
0x14000e453  cmp     [rsp+98h+arg_40], 0
0x14000e45b  jz      short loc_14000E491
0x14000e45d  mov     rdx, [rsp+98h+arg_8]
0x14000e465  mov     rax, [rdx+8]
0x14000e469  mov     ecx, [rax+10h]
0x14000e46c  mov     [rsp+98h+DesiredAccess], ecx; DesiredAccess
0x14000e470  mov     [rsp+98h+var_70], ebx; int
0x14000e474  mov     dword ptr [rsp+98h+var_78], 3; int
0x14000e47c  mov     r9, r15
0x14000e47f  mov     r8, r14
0x14000e482  mov     rcx, [rsp+98h+Context]; Context
0x14000e48a  call    CdCompleteFcbOpen
0x14000e48f  jmp     short loc_14000E495
0x14000e491  mov     eax, [rsp+98h+var_50]
0x14000e495  jmp     loc_14000E229
0x14001b69f  push    rbp
0x14001b6a1  sub     rsp, 40h
0x14001b6a5  mov     rbp, rdx
0x14001b6a8  cmp     byte ptr [rbp+40h], 0
0x14001b6ac  jz      short loc_14001B6D4
0x14001b6ae  mov     rcx, [rbp+0B0h]
0x14001b6b5  mov     qword ptr [rcx+188h], 0
0x14001b6c0  add     rcx, 150h; FastMutex
0x14001b6c7  call    cs:__imp_ExReleaseFastMutex
0x14001b6ce  nop     dword ptr [rax+rax+00h]
0x14001b6d3  nop
0x14001b6d4  mov     rcx, [rbp+58h]
0x14001b6d8  test    rcx, rcx
0x14001b6db  jz      short loc_14001B6F5
0x14001b6dd  mov     rcx, [rcx+0C8h]
0x14001b6e4  add     rcx, 20h ; ' '; Resource
0x14001b6e8  call    cs:__imp_ExReleaseResourceLite
0x14001b6ef  nop     dword ptr [rax+rax+00h]
0x14001b6f4  nop
0x14001b6f5  add     rsp, 40h
0x14001b6f9  pop     rbp
0x14001b6fa  retn
```
