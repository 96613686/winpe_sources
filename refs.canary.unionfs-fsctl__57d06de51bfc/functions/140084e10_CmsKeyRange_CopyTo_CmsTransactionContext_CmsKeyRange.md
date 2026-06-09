# CmsKeyRange::CopyTo(CmsTransactionContext *,CmsKeyRange &)

- ea: `0x140084e10`
- end: `0x1400850ce`
- name: `?CopyTo@CmsKeyRange@@QEAAJPEAVCmsTransactionContext@@AEAV1@@Z`
- size: `702`
- prototype: `int(CmsKeyRange *__hidden this, struct CmsTransactionContext *, struct CmsKeyRange *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1400c64fc`

## callees

- `0x140084e10`
- `0x14008fa30`
- `0x1400c8574`
- `0x1401e9e40`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140084fec`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140084fec`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140085072`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140085072`
- `ntoskrnl!ExAllocatePool2` at `0x140084f15`
- `ntoskrnl!ExAllocatePool2` at `0x140084f15`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140084ed7`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140084ed7`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f8086`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f8086`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140085045`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140085045`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f80ad`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f80ad`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14008508b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14008508b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400850bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400850bd`

## string_xrefs

- `0x140084f2c`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsKeyRange::CopyTo(CmsKeyRange *this, struct CmsTransactionContext *a2, struct CmsKeyRange *a3)
{
  size_t v6; // rbp
  const void *v8; // r13
  int v9; // r15d
  _QWORD *v10; // r14
  int v11; // r12d
  __int64 v12; // r15
  size_t v13; // rdx
  __int64 Pool2; // rax
  __int64 v15; // rcx
  unsigned int v16; // eax
  struct _SLIST_ENTRY *v17; // r8
  __int64 v18; // rcx
  int v19; // ecx
  struct _NPAGED_LOOKASIDE_LIST *v20; // rcx
  _QWORD *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // [rsp+50h] [rbp+8h]

  if ( *(_QWORD *)a3 )
    CmsKeyRange::FreeKeysBuffer(a3);
  *(_OWORD *)a3 = 0;
  *((_OWORD *)a3 + 1) = 0;
  *((_DWORD *)a3 + 6) = 3;
  v6 = *((unsigned int *)this + 2);
  if ( !(_DWORD)v6 )
    goto LABEL_4;
  v8 = *(const void **)this;
  if ( a2 && !*((_BYTE *)a2 + 129) && (unsigned int)v6 <= 0x60 )
  {
    *((_BYTE *)a2 + 129) = 1;
    v9 = 96;
    v10 = (_QWORD *)((char *)a2 + 2560);
    v11 = 8;
    goto LABEL_16;
  }
  v12 = qword_140262420 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  if ( (unsigned int)v6 > *(_DWORD *)v12 )
  {
    v12 = 0;
    v13 = v6 + 16;
    goto LABEL_11;
  }
  if ( *(_BYTE *)(v12 + 8) )
  {
    v20 = (struct _NPAGED_LOOKASIDE_LIST *)(v12 + 64);
    if ( *(_BYTE *)(v12 + 9) )
      v21 = ExAllocateFromNPagedLookasideList(v20);
    else
      v21 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v20);
  }
  else
  {
    if ( (int)*(_QWORD *)(v12 + 88) <= (int)HIDWORD(*(_QWORD *)(v12 + 88)) )
      goto LABEL_33;
    v19 = _InterlockedDecrement((volatile signed __int32 *)(v12 + 88));
    if ( v19 < *(_DWORD *)(v12 + 92) || v19 < 0 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v12 + 88));
      goto LABEL_33;
    }
    v21 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v12 + 64));
  }
  v10 = v21;
  if ( !v21 )
  {
LABEL_33:
    v13 = *(unsigned int *)(v12 + 4);
LABEL_11:
    Pool2 = ExAllocatePool2(66, v13, 1766871885);
    v10 = (_QWORD *)Pool2;
    if ( (Pool2 & 0xF) != 0 )
      MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
    if ( !Pool2 )
      goto LABEL_15;
  }
  *v10 = v12;
  v10 += 2;
LABEL_15:
  v9 = v6;
  v11 = 0;
LABEL_16:
  if ( v10 )
  {
    if ( !*(_QWORD *)a3 )
      goto LABEL_21;
    memmove(v10, *(const void **)a3, *((unsigned int *)a3 + 2));
    v15 = *(_QWORD *)a3;
    if ( (*((_DWORD *)a3 + 6) & 8) != 0 )
    {
      *(_BYTE *)(v15 - 2431) = 0;
      *((_DWORD *)a3 + 6) &= ~8u;
    }
    else if ( v15 )
    {
      v17 = (struct _SLIST_ENTRY *)(v15 - 16);
      v18 = *(_QWORD *)(v15 - 16);
      v23 = v18;
      if ( !v18 )
        goto LABEL_41;
      if ( *(_BYTE *)(v18 + 8) )
      {
        if ( *(_BYTE *)(v18 + 9) )
          ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v18 + 64), v17);
        else
          ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)(v18 + 64), v17);
        goto LABEL_20;
      }
      v22 = *(_QWORD *)(v18 + 88);
      if ( (int)v22 < *(_DWORD *)(v18 + 80) || SHIDWORD(v22) >= (int)v22 )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(v18 + 64), v17);
        _InterlockedIncrement((volatile signed __int32 *)(v23 + 88));
      }
      else
      {
LABEL_41:
        ExFreePoolWithTag(v17, 0);
      }
    }
LABEL_20:
    *((_DWORD *)a3 + 2) = 0;
LABEL_21:
    v16 = *((_DWORD *)a3 + 6) & 0xFFFFFFF7;
    *(_QWORD *)a3 = v10;
    *((_DWORD *)a3 + 2) = v9;
    *((_DWORD *)a3 + 6) = v11 | v16;
    if ( v8 )
      memmove(v10, v8, v6);
LABEL_4:
    *((_DWORD *)a3 + 3) = *((_DWORD *)this + 3);
    *((_DWORD *)a3 + 4) = *((_DWORD *)this + 4);
    *((_WORD *)a3 + 10) = *((_WORD *)this + 10);
    *((_WORD *)a3 + 11) = *((_WORD *)this + 11);
    *((_DWORD *)a3 + 6) = *((_DWORD *)this + 6) ^ (*((_DWORD *)a3 + 6) ^ *((_DWORD *)this + 6)) & 8;
    return 0;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x140084e10  push    rbx
0x140084e12  push    rbp
0x140084e13  push    rsi
0x140084e14  push    rdi
0x140084e15  push    r14
0x140084e17  sub     rsp, 20h
0x140084e1b  cmp     qword ptr [r8], 0
0x140084e1f  mov     rbx, r8
0x140084e22  mov     r14, rdx
0x140084e25  mov     rdi, rcx
0x140084e28  jnz     loc_140085056
0x140084e2e  xorps   xmm0, xmm0
0x140084e31  mov     [rsp+48h+arg_8], r12
0x140084e36  movups  xmmword ptr [rbx], xmm0
0x140084e39  mov     [rsp+48h+arg_10], r13
0x140084e3e  movups  xmmword ptr [rbx+10h], xmm0
0x140084e42  mov     dword ptr [rbx+18h], 3
0x140084e49  mov     ebp, [rdi+8]
0x140084e4c  mov     [rsp+48h+arg_18], r15
0x140084e51  test    ebp, ebp
0x140084e53  jnz     short loc_140084EA1
0x140084e55  mov     eax, [rdi+0Ch]
0x140084e58  lea     rdx, [rbx+18h]
0x140084e5c  mov     [rbx+0Ch], eax
0x140084e5f  mov     eax, [rdi+10h]
0x140084e62  mov     [rbx+10h], eax
0x140084e65  movzx   eax, word ptr [rdi+14h]
0x140084e69  mov     [rbx+14h], ax
0x140084e6d  movzx   eax, word ptr [rdi+16h]
0x140084e71  mov     [rbx+16h], ax
0x140084e75  mov     eax, [rdi+18h]
0x140084e78  mov     ecx, eax
0x140084e7a  xor     ecx, [rdx]
0x140084e7c  and     ecx, 8
0x140084e7f  xor     ecx, eax
0x140084e81  mov     [rbx+18h], ecx
0x140084e84  xor     eax, eax
0x140084e86  mov     r15, [rsp+48h+arg_18]
0x140084e8b  mov     r13, [rsp+48h+arg_10]
0x140084e90  mov     r12, [rsp+48h+arg_8]
0x140084e95  add     rsp, 20h
0x140084e99  pop     r14
0x140084e9b  pop     rdi
0x140084e9c  pop     rsi
0x140084e9d  pop     rbp
0x140084e9e  pop     rbx
0x140084e9f  retn
0x140084ea1  mov     r13, [rdi]
0x140084ea4  test    r14, r14
0x140084ea7  jz      short loc_140084ED5
0x140084ea9  cmp     byte ptr [r14+81h], 0
0x140084eb1  jnz     short loc_140084ED5
0x140084eb3  cmp     ebp, 60h ; '`'
0x140084eb6  ja      short loc_140084ED5
0x140084eb8  mov     byte ptr [r14+81h], 1
0x140084ec0  mov     r15d, 60h ; '`'
0x140084ec6  add     r14, 0A00h
0x140084ecd  mov     r12d, 8
0x140084ed3  jmp     short loc_140084F52
0x140084ed5  xor     ecx, ecx; ProcNumber
0x140084ed7  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140084ede  nop     dword ptr [rax+rax+00h]
0x140084ee3  xor     edx, edx
0x140084ee5  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140084eeb  lea     r15, [rdx+rdx*2]
0x140084eef  shl     r15, 6
0x140084ef3  add     r15, cs:qword_140262420
0x140084efa  cmp     ebp, [r15]
0x140084efd  jbe     loc_140085004
0x140084f03  xor     r15d, r15d
0x140084f06  lea     rdx, [rbp+10h]
0x140084f0a  mov     ecx, 42h ; 'B'
0x140084f0f  mov     r8d, 6950534Dh
0x140084f15  call    cs:__imp_ExAllocatePool2
0x140084f1c  nop     dword ptr [rax+rax+00h]
0x140084f21  mov     r14, rax
0x140084f24  test    al, 0Fh
0x140084f26  jz      loc_1401F8098
0x140084f2c  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x140084f33  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x140084f39  mov     r14, rax
0x140084f3c  test    rax, rax
0x140084f3f  jz      loc_140085038
0x140084f45  mov     [r14], r15
0x140084f48  add     r14, 10h
0x140084f4c  mov     r15d, ebp
0x140084f4f  xor     r12d, r12d
0x140084f52  test    r14, r14
0x140084f55  jz      loc_140084FFA
0x140084f5b  mov     rdx, [rbx]; Src
0x140084f5e  test    rdx, rdx
0x140084f61  jz      short loc_140084F8B
0x140084f63  mov     r8d, [rbx+8]; Size
0x140084f67  mov     rcx, r14; void *
0x140084f6a  call    memmove
0x140084f6f  mov     eax, [rbx+18h]
0x140084f72  mov     rcx, [rbx]
0x140084f75  test    al, 8
0x140084f77  jz      short loc_140084FBA
0x140084f79  mov     byte ptr [rcx-97Fh], 0
0x140084f80  and     dword ptr [rbx+18h], 0FFFFFFF7h
0x140084f84  mov     dword ptr [rbx+8], 0
0x140084f8b  mov     eax, [rbx+18h]
0x140084f8e  and     eax, 0FFFFFFF7h
0x140084f91  mov     [rbx], r14
0x140084f94  or      eax, r12d
0x140084f97  mov     [rbx+8], r15d
0x140084f9b  mov     [rbx+18h], eax
0x140084f9e  test    r13, r13
0x140084fa1  jz      loc_140084E55
0x140084fa7  mov     r8, rbp; Size
0x140084faa  mov     rdx, r13; Src
0x140084fad  mov     rcx, r14; void *
0x140084fb0  call    memmove
0x140084fb5  jmp     loc_140084E55
0x140084fba  test    rcx, rcx
0x140084fbd  jz      short loc_140084F84
0x140084fbf  lea     r8, [rcx-10h]
0x140084fc3  mov     rcx, [rcx-10h]
0x140084fc7  mov     [rsp+48h+arg_0], rcx
0x140084fcc  test    rcx, rcx
0x140084fcf  jz      loc_1400850B8
0x140084fd5  cmp     byte ptr [rcx+8], 0
0x140084fd9  jz      loc_14008509C
0x140084fdf  cmp     byte ptr [rcx+9], 0
0x140084fe3  mov     rdx, r8; Entry
0x140084fe6  jz      short loc_140085041
0x140084fe8  add     rcx, 40h ; '@'; Lookaside
0x140084fec  call    cs:__imp_ExFreeToNPagedLookasideList
0x140084ff3  nop     dword ptr [rax+rax+00h]
0x140084ff8  jmp     short loc_140084F84
0x140084ffa  mov     eax, 0C000009Ah
0x140084fff  jmp     loc_140084E86
0x140085004  cmp     byte ptr [r15+8], 0
0x140085009  jnz     short loc_140085063
0x14008500b  mov     rcx, [r15+58h]
0x14008500f  mov     rax, rcx
0x140085012  shr     rax, 20h
0x140085016  cmp     ecx, eax
0x140085018  jle     short loc_140085038
0x14008501a  nop
0x14008501b  mov     ecx, 0FFFFFFFFh
0x140085020  lock xadd [r15+58h], ecx
0x140085026  nop
0x140085027  dec     ecx
0x140085029  mov     eax, [r15+5Ch]
0x14008502d  cmp     ecx, eax
0x14008502f  jge     short loc_140085083
0x140085031  nop
0x140085032  lock inc dword ptr [r15+58h]
0x140085037  nop
0x140085038  mov     edx, [r15+4]
0x14008503c  jmp     loc_140084F0A
0x140085041  add     rcx, 40h ; '@'; Lookaside
0x140085045  call    cs:__imp_ExFreeToPagedLookasideList
0x14008504c  nop     dword ptr [rax+rax+00h]
0x140085051  jmp     loc_140084F84
0x140085056  mov     rcx, rbx; this
0x140085059  call    ?FreeKeysBuffer@CmsKeyRange@@QEAAXXZ; CmsKeyRange::FreeKeysBuffer(void)
0x14008505e  jmp     loc_140084E2E
0x140085063  cmp     byte ptr [r15+9], 0
0x140085068  lea     rcx, [r15+40h]; Lookaside
0x14008506c  jz      loc_1401F8086
0x140085072  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140085079  nop     dword ptr [rax+rax+00h]
0x14008507e  jmp     loc_140084F39
0x140085083  test    ecx, ecx
0x140085085  js      short loc_140085031
0x140085087  lea     rcx, [r15+40h]; ListHead
0x14008508b  call    cs:__imp_ExpInterlockedPopEntrySList
0x140085092  nop     dword ptr [rax+rax+00h]
0x140085097  jmp     loc_140084F39
0x14008509c  mov     rdx, [rcx+58h]
0x1400850a0  cmp     edx, [rcx+50h]
0x1400850a3  jl      loc_1401F80A6
0x1400850a9  mov     rax, rdx
0x1400850ac  shr     rax, 20h
0x1400850b0  cmp     eax, edx
0x1400850b2  jge     loc_1401F80A6
0x1400850b8  xor     edx, edx; Tag
0x1400850ba  mov     rcx, r8; P
0x1400850bd  call    cs:__imp_ExFreePoolWithTag
0x1400850c4  nop     dword ptr [rax+rax+00h]
0x1400850c9  jmp     loc_140084F84
0x1401f8086  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1401f808d  nop     dword ptr [rax+rax+00h]
0x1401f8092  nop
0x1401f8093  jmp     loc_140084F39
0x1401f8098  test    rax, rax
0x1401f809b  jz      loc_140084F4C
0x1401f80a1  jmp     loc_140084F45
0x1401f80a6  add     rcx, 40h ; '@'; ListHead
0x1401f80aa  mov     rdx, r8; ListEntry
0x1401f80ad  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401f80b4  nop     dword ptr [rax+rax+00h]
0x1401f80b9  mov     rax, [rsp+48h+arg_0]
0x1401f80be  nop
0x1401f80bf  lock inc dword ptr [rax+58h]
0x1401f80c3  nop
0x1401f80c4  jmp     loc_140084F84
```
