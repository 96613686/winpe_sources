# CdFspClose

- ea: `0x14000c374`
- end: `0x14000c6cf`
- name: `CdFspClose`
- size: `859`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140001fd0`
- `0x1400024e0`
- `0x140002630`
- `0x14000bcf8`
- `0x14000c0b0`
- `0x14000d400`

## callees

- `0x140001160`
- `0x1400024e0`
- `0x140003300`
- `0x14000c010`
- `0x14000c248`
- `0x14000c374`
- `0x1400181a4`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14000c3d7`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000c3d7`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000c4d4`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000c4d4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000c599`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000c5fb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000c648`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000c66d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000c6a2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000c599`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000c5fb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000c648`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000c66d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000c6a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c53c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c53c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c3b3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c3b3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c6ae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c6ae`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000c5b3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000c5b3`

## pseudocode

```c
void __fastcall CdFspClose(__int64 a1)
{
  char v2; // si
  unsigned int v3; // r12d
  __int64 v4; // rdi
  __int64 *v5; // rbx
  __int64 *v6; // rax
  __int64 v7; // r8
  __int64 *v8; // rcx
  __int64 *v9; // rcx
  __int64 v10; // rdx
  __int64 *v11; // rax
  __int64 v12; // r15
  int v13; // r13d
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int128 v16; // [rsp+30h] [rbp-79h] BYREF
  __int64 v17; // [rsp+40h] [rbp-69h]
  _QWORD v18[22]; // [rsp+50h] [rbp-59h] BYREF

  memset(v18, 0, 0x70u);
  v2 = 0;
  v3 = 0;
  v16 = 0;
  v17 = 0;
  v4 = 0;
  KeEnterCriticalRegion();
  while ( 1 )
  {
    v5 = 0;
    ExAcquireFastMutex(&FastMutex);
    qword_140007350 = (__int64)KeGetCurrentThread();
    v6 = (__int64 *)qword_140007318;
    if ( (__int64 *)qword_140007318 == &qword_140007318 )
      goto LABEL_12;
    while ( a1 && *(v6 - 8) != a1 )
    {
      v6 = (__int64 *)*v6;
      if ( v6 == &qword_140007318 )
        goto LABEL_13;
    }
    v7 = *v6;
    if ( *(__int64 **)(*v6 + 8) != v6 || (v8 = (__int64 *)v6[1], (__int64 *)*v8 != v6) )
LABEL_50:
      __fastfail(3u);
    *v8 = v7;
    v5 = v6 - 10;
    *(_QWORD *)(v7 + 8) = v8;
    --dword_140007328;
    if ( v6 == (__int64 *)80 )
    {
LABEL_12:
      if ( !a1 && (!HIBYTE(word_14000732C) || dword_140007340 <= (unsigned int)dword_140007348) )
      {
LABEL_23:
        word_14000732C = 0;
        goto LABEL_24;
      }
LABEL_13:
      v9 = (__int64 *)qword_140007330;
      if ( (__int64 *)qword_140007330 != &qword_140007330 )
      {
        while ( a1 && *(_QWORD *)(*(v9 - 1) + 120) != a1 )
        {
          v9 = (__int64 *)*v9;
          if ( v9 == &qword_140007330 )
            goto LABEL_24;
        }
        v10 = *v9;
        if ( *(__int64 **)(*v9 + 8) != v9 )
          goto LABEL_50;
        v11 = (__int64 *)v9[1];
        if ( (__int64 *)*v11 != v9 )
          goto LABEL_50;
        *v11 = v10;
        v5 = v9 - 2;
        *(_QWORD *)(v10 + 8) = v11;
        --dword_140007340;
      }
    }
    if ( !a1 && !v5 )
      goto LABEL_23;
LABEL_24:
    qword_140007350 = 0;
    ExReleaseFastMutex(&FastMutex);
    if ( !v5 )
      break;
    v12 = v5[1];
    if ( *(_WORD *)v5 == 776 )
    {
      v13 = *((_DWORD *)v5 + 6);
      *((_DWORD *)v5 + 6) = 0;
      v5[1] = 0;
    }
    else
    {
      v13 = *((_DWORD *)v5 + 8);
      memset(v18, 0, 0x70u);
      LODWORD(v18[4]) = 1;
      LODWORD(v18[0]) = 7340808;
      v18[5] = v5[5];
      v18[2] = *(_QWORD *)(v5[1] + 120);
      LOBYTE(v18[8]) = 2;
      LODWORD(v18[4]) = 5;
      ExFreePoolWithTag(v5, 0);
      v5 = v18;
    }
    *((_DWORD *)v5 + 8) |= 0x74u;
    if ( a1 )
      *((_DWORD *)v5 + 8) &= 0xFFFFFFCF;
    CdSetThreadContext((__int64)v5, (__int64)&v16);
    if ( a1 || (v14 = *(_QWORD *)(v12 + 120), (unsigned int)(*(_DWORD *)(v14 + 52) - 1) <= 1) || *(_DWORD *)(v14 + 56) )
    {
      if ( v3 <= dword_140007348 && *(_QWORD *)(v12 + 120) == v4 )
      {
        ++v3;
        goto LABEL_46;
      }
    }
    else
    {
      v2 = 1;
    }
    if ( v4 )
      ExReleaseResourceLite((PERESOURCE)(v4 + 128));
    if ( v2 )
    {
      ExAcquireResourceExclusiveLite(&Resource, 1u);
      if ( a1 || (v15 = *(_QWORD *)(v12 + 120), (unsigned int)(*(_DWORD *)(v15 + 52) - 1) <= 1) || *(_DWORD *)(v15 + 56) )
      {
        v2 = 0;
        ExReleaseResourceLite(&Resource);
      }
      else
      {
        v2 = 1;
      }
    }
    v4 = *(_QWORD *)(v12 + 120);
    CdAcquireResource((__int64)v5, (struct _ERESOURCE *)(v4 + 128), 0, 1);
    v3 = 0;
LABEL_46:
    CdCommonClosePrivate((__int64)v5, v4, v12, v13, 0);
    if ( v2 )
    {
      ExReleaseResourceLite((PERESOURCE)(v4 + 128));
      CdCheckForDismount((__int64)v5, v4, 0);
      v2 = 0;
      v4 = 0;
      ExReleaseResourceLite(&Resource);
    }
    else
    {
      v2 = 0;
    }
    CdCompleteRequest(v5, 0, 0);
  }
  if ( v4 )
    ExReleaseResourceLite((PERESOURCE)(v4 + 128));
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x14000c374  push    rbp
0x14000c376  push    rbx
0x14000c377  push    rsi
0x14000c378  push    rdi
0x14000c379  push    r12
0x14000c37b  push    r13
0x14000c37d  push    r14
0x14000c37f  push    r15
0x14000c381  lea     rbp, [rsp-1Fh]
0x14000c386  sub     rsp, 0C8h
0x14000c38d  xor     edx, edx; Val
0x14000c38f  mov     r14, rcx
0x14000c392  lea     rcx, [rbp+57h+var_B0]; void *
0x14000c396  lea     r8d, [rdx+70h]; Size
0x14000c39a  call    memset
0x14000c39f  xor     esi, esi
0x14000c3a1  xorps   xmm0, xmm0
0x14000c3a4  xor     eax, eax
0x14000c3a6  mov     r12d, esi
0x14000c3a9  movups  [rbp+57h+var_D0], xmm0
0x14000c3ad  mov     [rbp+57h+var_C0], rax
0x14000c3b1  mov     edi, esi
0x14000c3b3  call    cs:__imp_KeEnterCriticalRegion
0x14000c3ba  nop     dword ptr [rax+rax+00h]
0x14000c3bf  lea     rcx, FastMutex; FastMutex
0x14000c3c6  mov     rbx, rsi
0x14000c3c9  lea     r15, qword_140007330
0x14000c3d0  lea     r13, qword_140007318
0x14000c3d7  call    cs:__imp_ExAcquireFastMutex
0x14000c3de  nop     dword ptr [rax+rax+00h]
0x14000c3e3  mov     rax, gs:188h
0x14000c3ec  mov     cs:qword_140007350, rax
0x14000c3f3  mov     rax, cs:qword_140007318
0x14000c3fa  cmp     rax, r13
0x14000c3fd  jz      short loc_14000C447
0x14000c3ff  lea     rdx, [rax-50h]
0x14000c403  test    r14, r14
0x14000c406  jz      short loc_14000C418
0x14000c408  cmp     [rdx+10h], r14
0x14000c40c  jz      short loc_14000C418
0x14000c40e  mov     rax, [rax]
0x14000c411  cmp     rax, r13
0x14000c414  jnz     short loc_14000C3FF
0x14000c416  jmp     short loc_14000C463
0x14000c418  mov     r8, [rax]
0x14000c41b  cmp     [r8+8], rax
0x14000c41f  jnz     loc_14000C68F
0x14000c425  mov     rcx, [rax+8]
0x14000c429  cmp     [rcx], rax
0x14000c42c  jnz     loc_14000C68F
0x14000c432  mov     [rcx], r8
0x14000c435  mov     rbx, rdx
0x14000c438  mov     [r8+8], rcx
0x14000c43c  dec     cs:dword_140007328
0x14000c442  test    rdx, rdx
0x14000c445  jnz     short loc_14000C4B3
0x14000c447  test    r14, r14
0x14000c44a  jnz     short loc_14000C463
0x14000c44c  cmp     byte ptr cs:word_14000732C+1, sil
0x14000c453  jz      short loc_14000C4BD
0x14000c455  mov     eax, cs:dword_140007348
0x14000c45b  cmp     cs:dword_140007340, eax
0x14000c461  jbe     short loc_14000C4BD
0x14000c463  mov     rcx, cs:qword_140007330
0x14000c46a  cmp     rcx, r15
0x14000c46d  jz      short loc_14000C4B3
0x14000c46f  test    r14, r14
0x14000c472  jz      short loc_14000C488
0x14000c474  mov     rax, [rcx-8]
0x14000c478  cmp     [rax+78h], r14
0x14000c47c  jz      short loc_14000C488
0x14000c47e  mov     rcx, [rcx]
0x14000c481  cmp     rcx, r15
0x14000c484  jnz     short loc_14000C46F
0x14000c486  jmp     short loc_14000C4C6
0x14000c488  mov     rdx, [rcx]
0x14000c48b  cmp     [rdx+8], rcx
0x14000c48f  jnz     loc_14000C68F
0x14000c495  mov     rax, [rcx+8]
0x14000c499  cmp     [rax], rcx
0x14000c49c  jnz     loc_14000C68F
0x14000c4a2  mov     [rax], rdx
0x14000c4a5  lea     rbx, [rcx-10h]
0x14000c4a9  mov     [rdx+8], rax
0x14000c4ad  dec     cs:dword_140007340
0x14000c4b3  test    r14, r14
0x14000c4b6  jnz     short loc_14000C4C6
0x14000c4b8  test    rbx, rbx
0x14000c4bb  jnz     short loc_14000C4C6
0x14000c4bd  mov     cs:word_14000732C, 0
0x14000c4c6  lea     rcx, FastMutex; FastMutex
0x14000c4cd  mov     cs:qword_140007350, rsi
0x14000c4d4  call    cs:__imp_ExReleaseFastMutex
0x14000c4db  nop     dword ptr [rax+rax+00h]
0x14000c4e0  test    rbx, rbx
0x14000c4e3  jz      loc_14000C696
0x14000c4e9  mov     r15, [rbx+8]
0x14000c4ed  mov     eax, 308h
0x14000c4f2  cmp     [rbx], ax
0x14000c4f5  jz      short loc_14000C54E
0x14000c4f7  mov     r13d, [rbx+20h]
0x14000c4fb  lea     rcx, [rbp+57h+var_B0]; void *
0x14000c4ff  xor     edx, edx; Val
0x14000c501  lea     r8d, [rdx+70h]; Size
0x14000c505  call    memset
0x14000c50a  mov     [rbp+57h+var_90], 1
0x14000c511  xor     edx, edx; Tag
0x14000c513  mov     [rbp+57h+var_B0], 700308h
0x14000c51a  mov     rax, [rbx+28h]
0x14000c51e  mov     [rbp+57h+var_88], rax
0x14000c522  mov     rax, [rbx+8]
0x14000c526  mov     rcx, [rax+78h]
0x14000c52a  mov     [rbp+57h+var_A0], rcx
0x14000c52e  mov     rcx, rbx; P
0x14000c531  mov     [rbp+57h+var_70], 2
0x14000c535  mov     [rbp+57h+var_90], 5
0x14000c53c  call    cs:__imp_ExFreePoolWithTag
0x14000c543  nop     dword ptr [rax+rax+00h]
0x14000c548  lea     rbx, [rbp+57h+var_B0]
0x14000c54c  jmp     short loc_14000C559
0x14000c54e  mov     r13d, [rbx+18h]
0x14000c552  mov     [rbx+18h], esi
0x14000c555  mov     [rbx+8], rsi
0x14000c559  or      dword ptr [rbx+20h], 74h
0x14000c55d  test    r14, r14
0x14000c560  jz      short loc_14000C566
0x14000c562  and     dword ptr [rbx+20h], 0FFFFFFCFh
0x14000c566  lea     rdx, [rbp+57h+var_D0]
0x14000c56a  mov     rcx, rbx
0x14000c56d  call    CdSetThreadContext
0x14000c572  test    r14, r14
0x14000c575  jnz     short loc_14000C5DD
0x14000c577  mov     rcx, [r15+78h]
0x14000c57b  mov     eax, [rcx+34h]
0x14000c57e  dec     eax
0x14000c580  cmp     eax, 1
0x14000c583  jbe     short loc_14000C5DD
0x14000c585  cmp     [rcx+38h], esi
0x14000c588  jnz     short loc_14000C5DD
0x14000c58a  mov     sil, 1
0x14000c58d  test    rdi, rdi
0x14000c590  jz      short loc_14000C5A5
0x14000c592  lea     rcx, [rdi+80h]; Resource
0x14000c599  call    cs:__imp_ExReleaseResourceLite
0x14000c5a0  nop     dword ptr [rax+rax+00h]
0x14000c5a5  test    sil, sil
0x14000c5a8  jz      short loc_14000C607
0x14000c5aa  mov     dl, 1; Wait
0x14000c5ac  lea     rcx, Resource; Resource
0x14000c5b3  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000c5ba  nop     dword ptr [rax+rax+00h]
0x14000c5bf  test    r14, r14
0x14000c5c2  jnz     short loc_14000C5F1
0x14000c5c4  mov     rcx, [r15+78h]
0x14000c5c8  mov     eax, [rcx+34h]
0x14000c5cb  dec     eax
0x14000c5cd  cmp     eax, 1
0x14000c5d0  jbe     short loc_14000C5F1
0x14000c5d2  cmp     [rcx+38h], r14d
0x14000c5d6  jnz     short loc_14000C5F1
0x14000c5d8  mov     sil, 1
0x14000c5db  jmp     short loc_14000C607
0x14000c5dd  cmp     r12d, cs:dword_140007348
0x14000c5e4  ja      short loc_14000C58D
0x14000c5e6  cmp     [r15+78h], rdi
0x14000c5ea  jnz     short loc_14000C58D
0x14000c5ec  inc     r12d
0x14000c5ef  jmp     short loc_14000C626
0x14000c5f1  xor     sil, sil
0x14000c5f4  lea     rcx, Resource; Resource
0x14000c5fb  call    cs:__imp_ExReleaseResourceLite
0x14000c602  nop     dword ptr [rax+rax+00h]
0x14000c607  mov     rdi, [r15+78h]
0x14000c60b  mov     r9d, 1
0x14000c611  xor     r8d, r8d
0x14000c614  mov     rcx, rbx
0x14000c617  lea     rdx, [rdi+80h]
0x14000c61e  call    CdAcquireResource
0x14000c623  xor     r12d, r12d
0x14000c626  mov     r9d, r13d
0x14000c629  mov     [rsp+100h+var_E0], 0
0x14000c62e  mov     r8, r15
0x14000c631  mov     rdx, rdi
0x14000c634  mov     rcx, rbx
0x14000c637  call    CdCommonClosePrivate
0x14000c63c  test    sil, sil
0x14000c63f  jz      short loc_14000C67B
0x14000c641  lea     rcx, [rdi+80h]; Resource
0x14000c648  call    cs:__imp_ExReleaseResourceLite
0x14000c64f  nop     dword ptr [rax+rax+00h]
0x14000c654  xor     r8d, r8d
0x14000c657  mov     rdx, rdi
0x14000c65a  mov     rcx, rbx
0x14000c65d  call    CdCheckForDismount
0x14000c662  xor     esi, esi
0x14000c664  lea     rcx, Resource; Resource
0x14000c66b  mov     edi, esi
0x14000c66d  call    cs:__imp_ExReleaseResourceLite
0x14000c674  nop     dword ptr [rax+rax+00h]
0x14000c679  jmp     short loc_14000C67D
0x14000c67b  xor     esi, esi
0x14000c67d  xor     r8d, r8d
0x14000c680  xor     edx, edx
0x14000c682  mov     rcx, rbx
0x14000c685  call    CdCompleteRequest
0x14000c68a  jmp     loc_14000C3BF
0x14000c68f  mov     ecx, 3
0x14000c694  int     29h; Win8: RtlFailFast(ecx)
0x14000c696  test    rdi, rdi
0x14000c699  jz      short loc_14000C6AE
0x14000c69b  lea     rcx, [rdi+80h]; Resource
0x14000c6a2  call    cs:__imp_ExReleaseResourceLite
0x14000c6a9  nop     dword ptr [rax+rax+00h]
0x14000c6ae  call    cs:__imp_KeLeaveCriticalRegion
0x14000c6b5  nop     dword ptr [rax+rax+00h]
0x14000c6ba  add     rsp, 0C8h
0x14000c6c1  pop     r15
0x14000c6c3  pop     r14
0x14000c6c5  pop     r13
0x14000c6c7  pop     r12
0x14000c6c9  pop     rdi
0x14000c6ca  pop     rsi
0x14000c6cb  pop     rbx
0x14000c6cc  pop     rbp
0x14000c6cd  retn
```
