# CmsPinCache::TryCopyCachedPin(CmsTransactionContext *,CmsPinCache *,CmsCachedPin *)

- ea: `0x140023720`
- end: `0x140023da6`
- name: `?TryCopyCachedPin@CmsPinCache@@QEAAPEAVCmsCachedPin@@PEAVCmsTransactionContext@@PEAV1@PEAV2@@Z`
- size: `1670`
- prototype: `struct CmsCachedPin *__fastcall(CmsPinCache *__hidden this, struct CmsTransactionContext *, struct CmsPinCache *, struct CmsCachedPin *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140052030`
- `0x1400646a0`

## callees

- `0x140023720`
- `0x140024c60`
- `0x140089420`
- `0x1400ceda0`
- `0x1401f4100`
- `0x1401f4400`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140023adf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140023c31`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140023adf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140023c31`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140023cba`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140023d01`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140023cba`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140023d01`
- `ntoskrnl!ExAllocatePool2` at `0x14002394f`
- `ntoskrnl!ExAllocatePool2` at `0x1400239fc`
- `ntoskrnl!ExAllocatePool2` at `0x14002394f`
- `ntoskrnl!ExAllocatePool2` at `0x1400239fc`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002390c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400239b6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002390c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400239b6`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fa504`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fa516`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fa504`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fa516`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140023b8d`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140023c20`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140023b8d`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140023c20`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fa52f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fa54d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fa52f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fa54d`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140023cd4`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140023d1e`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140023cd4`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140023d1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023d5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023d8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023d5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023d8c`

## string_xrefs

- `0x1401fa564`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
struct CmsCachedPin *__fastcall CmsPinCache::TryCopyCachedPin(
        CmsPinCache *this,
        struct CmsTransactionContext *a2,
        struct CmsPinCache *a3,
        struct CmsCachedPin *a4)
{
  char *v7; // rbx
  unsigned int v8; // r13d
  size_t v9; // r12
  __int64 v10; // rcx
  struct CmsPinCache *v11; // rdx
  __int64 v12; // rcx
  __int64 v14; // rbx
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 Pool2; // rax
  _QWORD *v18; // rsi
  __int64 v19; // rdx
  __int64 v20; // r9
  size_t v21; // rdx
  __int64 v22; // rax
  const void *v23; // rdx
  __int64 v24; // rcx
  unsigned int v25; // eax
  __int64 v26; // rdi
  struct _SLIST_ENTRY *v27; // r8
  struct _NPAGED_LOOKASIDE_LIST *v28; // rcx
  int v29; // esi
  char *v30; // rcx
  __int64 v31; // r8
  __int64 v32; // rbx
  struct _SLIST_ENTRY *v33; // r8
  struct _PAGED_LOOKASIDE_LIST *v34; // rcx
  int v35; // ecx
  int v36; // ecx
  __int64 v37; // r14
  struct _NPAGED_LOOKASIDE_LIST *v38; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v39; // rcx
  _QWORD *v40; // rax
  __int64 v41; // rcx
  __int64 v42; // rcx
  void *Src; // [rsp+20h] [rbp-48h]
  unsigned __int8 v44; // [rsp+70h] [rbp+8h]
  int v45; // [rsp+78h] [rbp+10h]
  __int64 v46; // [rsp+78h] [rbp+10h]
  int v47; // [rsp+80h] [rbp+18h]

  if ( a3 == (struct CmsTransactionContext *)((char *)a2 + 824) )
  {
    v44 = 1;
    if ( !*((_BYTE *)a2 + 135) )
    {
      v7 = (char *)a2 + 2656;
      if ( a2 == (struct CmsTransactionContext *)-2656LL )
      {
        v7 = 0;
      }
      else
      {
        *(_QWORD *)v7 = 0;
        *((_QWORD *)a2 + 333) = 0;
        *((_DWORD *)a2 + 682) |= 3u;
        *((_QWORD *)a2 + 338) = 0;
        *((_QWORD *)a2 + 339) = 0;
        *((_QWORD *)a2 + 340) = 0;
        *((_DWORD *)a2 + 690) = 0;
        *((_QWORD *)a2 + 349) = 0;
        *((_QWORD *)a2 + 335) = (char *)a2 + 2672;
        *((_QWORD *)a2 + 334) = (char *)a2 + 2672;
        *((_QWORD *)a2 + 333) = 0;
        *(_QWORD *)v7 = 0;
        *(_QWORD *)((char *)a2 + 2804) = 0;
      }
      *((_DWORD *)v7 + 26) |= 8u;
      *((_BYTE *)a2 + 135) = 1;
      *((_QWORD *)v7 + 17) = a2;
      goto LABEL_6;
    }
  }
  else
  {
    v44 = 0;
  }
  v14 = qword_140269438 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  if ( *(_DWORD *)v14 < 0xC0u )
  {
    v14 = 0;
    v16 = 208;
LABEL_21:
    Pool2 = ExAllocatePool2(66, v16, 1766871885, v15);
    if ( (Pool2 & 0xF) != 0 )
      goto LABEL_102;
    if ( !Pool2 )
      return 0;
    goto LABEL_77;
  }
  if ( !*(_BYTE *)(v14 + 8) )
  {
    if ( (int)*(_QWORD *)(v14 + 88) > (int)HIDWORD(*(_QWORD *)(v14 + 88)) )
    {
      v36 = _InterlockedDecrement((volatile signed __int32 *)(v14 + 88));
      if ( v36 >= *(_DWORD *)(v14 + 92) && v36 >= 0 )
      {
        Pool2 = (__int64)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v14 + 64));
        goto LABEL_76;
      }
      _InterlockedIncrement((volatile signed __int32 *)(v14 + 88));
    }
LABEL_70:
    v16 = *(unsigned int *)(v14 + 4);
    goto LABEL_21;
  }
  v38 = (struct _NPAGED_LOOKASIDE_LIST *)(v14 + 64);
  if ( *(_BYTE *)(v14 + 9) )
    Pool2 = (__int64)ExAllocateFromNPagedLookasideList(v38);
  else
    Pool2 = (__int64)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v38);
LABEL_76:
  if ( !Pool2 )
    goto LABEL_70;
LABEL_77:
  v37 = Pool2 + 16;
  *(_QWORD *)Pool2 = v14;
  if ( Pool2 == -16 )
    return 0;
  memset((void *)(Pool2 + 16), 0, 0xC0u);
  v7 = (char *)(v37 + 32);
  *(_BYTE *)(v37 + 26) = 32;
  if ( v37 == -32 )
  {
    v7 = 0;
  }
  else
  {
    *(_DWORD *)(v37 + 104) |= 3u;
    *(_QWORD *)(v37 + 56) = v37 + 48;
    *(_QWORD *)(v37 + 48) = v37 + 48;
    *(_QWORD *)(v37 + 180) = 0;
  }
  *((_QWORD *)v7 + 16) = v37;
LABEL_6:
  if ( !v7 )
    return 0;
  v8 = *((_DWORD *)v7 + 26);
  if ( *((_QWORD *)v7 + 6) )
    CmsKeyRange::FreeKeysBuffer((CmsKeyRange *)(v7 + 48));
  *((_OWORD *)v7 + 3) = 0;
  *((_OWORD *)v7 + 4) = 0;
  *((_DWORD *)v7 + 18) |= 3u;
  v9 = *((unsigned int *)a4 + 14);
  if ( !(_DWORD)v9 )
    goto LABEL_10;
  Src = (void *)*((_QWORD *)a4 + 6);
  if ( a2 && !*((_BYTE *)a2 + 129) && (unsigned int)v9 <= 0x60 )
  {
    *((_BYTE *)a2 + 129) = 1;
    v18 = (_QWORD *)((char *)a2 + 2560);
    v47 = 96;
    v45 = 8;
    goto LABEL_36;
  }
  v19 = qword_140269420 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  v46 = v19;
  if ( (unsigned int)v9 > *(_DWORD *)v19 )
  {
    v46 = 0;
    v21 = v9 + 16;
    goto LABEL_30;
  }
  if ( *(_BYTE *)(v19 + 8) )
  {
    v39 = (struct _NPAGED_LOOKASIDE_LIST *)(v19 + 64);
    if ( *(_BYTE *)(v19 + 9) )
      v40 = ExAllocateFromNPagedLookasideList(v39);
    else
      v40 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v39);
    goto LABEL_33;
  }
  if ( (int)*(_QWORD *)(v19 + 88) > (int)HIDWORD(*(_QWORD *)(v19 + 88)) )
  {
    v35 = _InterlockedDecrement((volatile signed __int32 *)(v19 + 88));
    if ( v35 >= *(_DWORD *)(v19 + 92) && v35 >= 0 )
    {
      v40 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v19 + 64));
LABEL_33:
      v18 = v40;
      if ( v40 )
      {
LABEL_34:
        *v18 = v46;
        v18 += 2;
        goto LABEL_35;
      }
      v19 = v46;
      goto LABEL_65;
    }
    _InterlockedIncrement((volatile signed __int32 *)(v19 + 88));
  }
LABEL_65:
  v21 = *(unsigned int *)(v19 + 4);
LABEL_30:
  v22 = ExAllocatePool2(66, v21, 1766871885, v20);
  v18 = (_QWORD *)v22;
  if ( (v22 & 0xF) != 0 )
LABEL_102:
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( v22 )
    goto LABEL_34;
LABEL_35:
  v47 = v9;
  v45 = 0;
LABEL_36:
  if ( !v18 )
  {
    if ( (*((_DWORD *)v7 + 26) & 8) != 0 )
      *(_BYTE *)(*((_QWORD *)v7 + 17) + 135LL) = 0;
    v29 = *((_DWORD *)v7 + 26) & 8;
    if ( (*((_DWORD *)v7 + 26) & 0x10) != 0 )
      _InterlockedAdd64(&CmsCachedPin::GlobalCachedPinPageCount, -*((_DWORD *)v7 + 38));
    v30 = (char *)*((_QWORD *)v7 + 6);
    if ( v30 )
    {
      if ( (*((_DWORD *)v7 + 18) & 8) != 0 )
      {
        *(v30 - 2431) = 0;
        *((_DWORD *)v7 + 18) &= ~8u;
      }
      else
      {
        CmsLookasides::Free(v30);
      }
      *((_QWORD *)v7 + 6) = 0;
      *((_DWORD *)v7 + 14) = 0;
    }
    if ( !v29 )
    {
      v31 = *((_QWORD *)v7 + 16);
      if ( v31 )
      {
        v32 = *(_QWORD *)(v31 - 16);
        v33 = (struct _SLIST_ENTRY *)(v31 - 16);
        if ( !v32 )
          goto LABEL_96;
        if ( *(_BYTE *)(v32 + 8) )
        {
          v34 = (struct _PAGED_LOOKASIDE_LIST *)(v32 + 64);
          if ( !*(_BYTE *)(v32 + 9) )
          {
            ExFreeToPagedLookasideList(v34, v33);
            return 0;
          }
          ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v34, v33);
          return 0;
        }
        v42 = *(_QWORD *)(v32 + 88);
        if ( (int)v42 < *(_DWORD *)(v32 + 80) || SHIDWORD(v42) >= (int)v42 )
        {
          ExpInterlockedPushEntrySList((PSLIST_HEADER)(v32 + 64), v33);
          _InterlockedIncrement((volatile signed __int32 *)(v32 + 88));
        }
        else
        {
LABEL_96:
          ExFreePoolWithTag(v33, 0);
        }
      }
    }
    return 0;
  }
  v23 = (const void *)*((_QWORD *)v7 + 6);
  if ( !v23 )
    goto LABEL_40;
  memmove(v18, v23, *((unsigned int *)v7 + 14));
  v24 = *((_QWORD *)v7 + 6);
  if ( (*((_DWORD *)v7 + 18) & 8) != 0 )
  {
    *(_BYTE *)(v24 - 2431) = 0;
    *((_DWORD *)v7 + 18) &= ~8u;
    goto LABEL_40;
  }
  if ( v24 )
  {
    v26 = *(_QWORD *)(v24 - 16);
    v27 = (struct _SLIST_ENTRY *)(v24 - 16);
    if ( v26 )
    {
      if ( *(_BYTE *)(v26 + 8) )
      {
        v28 = (struct _NPAGED_LOOKASIDE_LIST *)(v26 + 64);
        if ( *(_BYTE *)(v26 + 9) )
          ExFreeToNPagedLookasideList(v28, v27);
        else
          ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v28, v27);
        goto LABEL_40;
      }
      v41 = *(_QWORD *)(v26 + 88);
      if ( (int)v41 < *(_DWORD *)(v26 + 80) || SHIDWORD(v41) >= (int)v41 )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(v26 + 64), v27);
        _InterlockedIncrement((volatile signed __int32 *)(v26 + 88));
        goto LABEL_40;
      }
    }
    ExFreePoolWithTag(v27, 0);
  }
LABEL_40:
  v25 = *((_DWORD *)v7 + 18) & 0xFFFFFFF7;
  *((_QWORD *)v7 + 6) = v18;
  *((_DWORD *)v7 + 18) = v45 | v25;
  *((_DWORD *)v7 + 14) = v47;
  if ( Src )
    memmove(v18, Src, v9);
LABEL_10:
  *((_DWORD *)v7 + 15) = *((_DWORD *)a4 + 15);
  *((_DWORD *)v7 + 16) = *((_DWORD *)a4 + 16);
  *((_WORD *)v7 + 34) = *((_WORD *)a4 + 34);
  *((_WORD *)v7 + 35) = *((_WORD *)a4 + 35);
  *((_DWORD *)v7 + 18) = *((_DWORD *)a4 + 18) ^ (*((_DWORD *)v7 + 18) ^ *((_DWORD *)a4 + 18)) & 8;
  v10 = *((_QWORD *)a4 + 4);
  *((_QWORD *)v7 + 4) = v10;
  *((_QWORD *)v7 + 5) = *((_QWORD *)a4 + 5);
  *((_QWORD *)v7 + 10) = *((_QWORD *)a4 + 10);
  *((_DWORD *)v7 + 22) = *((_DWORD *)a4 + 22);
  *((_DWORD *)v7 + 23) = *((_DWORD *)a4 + 23);
  *((_QWORD *)v7 + 12) = *((_QWORD *)a4 + 12);
  *((_QWORD *)v7 + 14) = *((_QWORD *)a4 + 14);
  *((_QWORD *)v7 + 15) = *((_QWORD *)a4 + 15);
  v7[144] = *((_BYTE *)a4 + 144);
  _InterlockedIncrement((volatile signed __int32 *)(v10 + 380));
  if ( v44 )
  {
    v11 = a3;
    if ( *((_BYTE *)a4 + 144) )
      v11 = (struct CmsPinCache *)((char *)a3 + 16);
    v12 = *(_QWORD *)v11;
    if ( *(struct CmsPinCache **)(*(_QWORD *)v11 + 8LL) != v11 )
      __fastfail(3u);
    *((_QWORD *)v7 + 2) = v12;
    *((_QWORD *)v7 + 3) = v11;
    *(_QWORD *)(v12 + 8) = v7 + 16;
    *(_QWORD *)v11 = v7 + 16;
    if ( *((_BYTE *)a4 + 144) )
      ++*((_DWORD *)a3 + 9);
    else
      ++*((_DWORD *)a3 + 8);
  }
  *((_DWORD *)v7 + 26) = ((2 * v44) & 0xFFEB | *((_DWORD *)a4 + 26) & 0xFFFFFFE9)
                       ^ (((2 * v44) & 0xEB | *((_BYTE *)a4 + 104) & 0xE9)
                        ^ (unsigned __int8)(8 * (v8 >> 3)))
                       & 8;
  return (struct CmsCachedPin *)v7;
}

```

## disassembly

```asm
0x140023720  mov     [rsp+arg_18], rbx
0x140023725  mov     [rsp+arg_0], rcx
0x14002372a  push    rbp
0x14002372b  push    rsi
0x14002372c  push    rdi
0x14002372d  push    r12
0x14002372f  push    r13
0x140023731  push    r14
0x140023733  push    r15
0x140023735  sub     rsp, 30h
0x140023739  lea     rax, [rdx+338h]
0x140023740  mov     rbp, r9
0x140023743  mov     r15, r8
0x140023746  mov     rsi, rdx
0x140023749  cmp     r8, rax
0x14002374c  jnz     loc_140023905
0x140023752  cmp     byte ptr [rdx+87h], 0
0x140023759  mov     byte ptr [rsp+68h+arg_0], 1
0x14002375e  jnz     loc_14002390A
0x140023764  lea     rbx, [rdx+0A60h]
0x14002376b  xor     edi, edi
0x14002376d  test    rbx, rbx
0x140023770  jz      loc_140023C4E
0x140023776  mov     [rbx], rdi
0x140023779  lea     rax, [rbx+10h]
0x14002377d  mov     [rbx+8], rdi
0x140023781  or      dword ptr [rbx+48h], 3
0x140023785  mov     [rbx+30h], rdi
0x140023789  mov     [rbx+38h], rdi
0x14002378d  mov     [rbx+40h], rdi
0x140023791  mov     [rbx+68h], edi
0x140023794  mov     [rbx+88h], rdi
0x14002379b  mov     [rax+8], rax
0x14002379f  mov     [rax], rax
0x1400237a2  mov     [rbx+8], rdi
0x1400237a6  mov     [rbx], rdi
0x1400237a9  mov     [rbx+94h], rdi
0x1400237b0  or      dword ptr [rbx+68h], 8
0x1400237b4  mov     byte ptr [rdx+87h], 1
0x1400237bb  mov     [rbx+88h], rsi
0x1400237c2  test    rbx, rbx
0x1400237c5  jz      loc_140023C3D
0x1400237cb  cmp     qword ptr [rbx+30h], 0
0x1400237d0  mov     r13d, [rbx+68h]
0x1400237d4  jnz     loc_140023CE5
0x1400237da  xorps   xmm0, xmm0
0x1400237dd  movups  xmmword ptr [rbx+30h], xmm0
0x1400237e1  movups  xmmword ptr [rbx+40h], xmm0
0x1400237e5  or      dword ptr [rbx+48h], 3
0x1400237e9  mov     r12d, [rbp+38h]
0x1400237ed  test    r12d, r12d
0x1400237f0  jnz     loc_140023971
0x1400237f6  mov     eax, [rbp+3Ch]
0x1400237f9  mov     [rbx+3Ch], eax
0x1400237fc  mov     eax, [rbp+40h]
0x1400237ff  mov     [rbx+40h], eax
0x140023802  movzx   eax, word ptr [rbp+44h]
0x140023806  mov     [rbx+44h], ax
0x14002380a  movzx   eax, word ptr [rbp+46h]
0x14002380e  mov     [rbx+46h], ax
0x140023812  mov     eax, [rbp+48h]
0x140023815  mov     ecx, eax
0x140023817  xor     ecx, [rbx+48h]
0x14002381a  and     ecx, 8
0x14002381d  xor     ecx, eax
0x14002381f  mov     [rbx+48h], ecx
0x140023822  mov     rcx, [rbp+20h]
0x140023826  mov     [rbx+20h], rcx
0x14002382a  mov     rax, [rbp+28h]
0x14002382e  mov     [rbx+28h], rax
0x140023832  mov     rax, [rbp+50h]
0x140023836  mov     [rbx+50h], rax
0x14002383a  mov     eax, [rbp+58h]
0x14002383d  mov     [rbx+58h], eax
0x140023840  mov     eax, [rbp+5Ch]
0x140023843  mov     [rbx+5Ch], eax
0x140023846  mov     rax, [rbp+60h]
0x14002384a  mov     [rbx+60h], rax
0x14002384e  mov     rax, [rbp+70h]
0x140023852  mov     [rbx+70h], rax
0x140023856  mov     rax, [rbp+78h]
0x14002385a  mov     [rbx+78h], rax
0x14002385e  movzx   eax, byte ptr [rbp+90h]
0x140023865  mov     [rbx+90h], al
0x14002386b  nop
0x14002386c  lock inc dword ptr [rcx+17Ch]
0x140023873  movzx   r8d, byte ptr [rsp+68h+arg_0]
0x140023879  nop
0x14002387a  test    r8b, r8b
0x14002387d  jz      short loc_1400238C4
0x14002387f  cmp     byte ptr [rbp+90h], 0
0x140023886  lea     rcx, [r15+10h]
0x14002388a  mov     rdx, r15
0x14002388d  cmovnz  rdx, rcx
0x140023891  mov     rcx, [rdx]
0x140023894  cmp     [rcx+8], rdx
0x140023898  jz      short loc_1400238A1
0x14002389a  mov     ecx, 3
0x14002389f  int     29h; Win8: RtlFailFast(ecx)
0x1400238a1  lea     rax, [rbx+10h]
0x1400238a5  mov     [rax], rcx
0x1400238a8  mov     [rax+8], rdx
0x1400238ac  mov     [rcx+8], rax
0x1400238b0  mov     [rdx], rax
0x1400238b3  cmp     byte ptr [rbp+90h], 0
0x1400238ba  jnz     loc_140023D9D
0x1400238c0  inc     dword ptr [r15+20h]
0x1400238c4  mov     ecx, [rbp+68h]
0x1400238c7  mov     eax, r8d
0x1400238ca  add     eax, eax
0x1400238cc  shr     r13d, 3
0x1400238d0  and     ecx, 0FFFFFFFDh
0x1400238d3  or      ecx, eax
0x1400238d5  movzx   eax, r13b
0x1400238d9  shl     eax, 3
0x1400238dc  and     ecx, 0FFFFFFEBh
0x1400238df  xor     eax, ecx
0x1400238e1  and     eax, 8
0x1400238e4  xor     eax, ecx
0x1400238e6  mov     [rbx+68h], eax
0x1400238e9  mov     rax, rbx
0x1400238ec  mov     rbx, [rsp+68h+arg_18]
0x1400238f4  add     rsp, 30h
0x1400238f8  pop     r15
0x1400238fa  pop     r14
0x1400238fc  pop     r13
0x1400238fe  pop     r12
0x140023900  pop     rdi
0x140023901  pop     rsi
0x140023902  pop     rbp
0x140023903  retn
0x140023905  mov     byte ptr [rsp+68h+arg_0], 0
0x14002390a  xor     ecx, ecx; ProcNumber
0x14002390c  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140023913  nop     dword ptr [rax+rax+00h]
0x140023918  xor     edx, edx
0x14002391a  xor     edi, edi
0x14002391c  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140023922  lea     rbx, [rdx+rdx*2]
0x140023926  shl     rbx, 6
0x14002392a  add     rbx, cs:qword_140269438
0x140023931  cmp     dword ptr [rbx], 0C0h
0x140023937  jnb     loc_140023BE0
0x14002393d  mov     ebx, edi
0x14002393f  mov     edx, 0D0h
0x140023944  mov     ecx, 42h ; 'B'
0x140023949  mov     r8d, 6950534Dh
0x14002394f  call    cs:__imp_ExAllocatePool2
0x140023956  nop     dword ptr [rax+rax+00h]
0x14002395b  test    al, 0Fh
0x14002395d  jnz     loc_1401FA564
0x140023963  test    rax, rax
0x140023966  jz      loc_140023C3D
0x14002396c  jmp     loc_140023C5B
0x140023971  mov     rax, [rbp+30h]
0x140023975  mov     [rsp+68h+Src], rax
0x14002397a  test    rsi, rsi
0x14002397d  jz      short loc_1400239B4
0x14002397f  cmp     byte ptr [rsi+81h], 0
0x140023986  jnz     short loc_1400239B4
0x140023988  cmp     r12d, 60h ; '`'
0x14002398c  ja      short loc_1400239B4
0x14002398e  mov     byte ptr [rsi+81h], 1
0x140023995  add     rsi, 0A00h
0x14002399c  mov     [rsp+68h+arg_10], 60h ; '`'
0x1400239a7  mov     dword ptr [rsp+68h+arg_8], 8
0x1400239af  jmp     loc_140023A3E
0x1400239b4  xor     ecx, ecx; ProcNumber
0x1400239b6  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400239bd  nop     dword ptr [rax+rax+00h]
0x1400239c2  xor     edx, edx
0x1400239c4  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x1400239ca  lea     rdx, [rdx+rdx*2]
0x1400239ce  shl     rdx, 6
0x1400239d2  add     rdx, cs:qword_140269420
0x1400239d9  mov     [rsp+68h+arg_8], rdx
0x1400239de  cmp     r12d, [rdx]
0x1400239e1  jbe     loc_140023BA0
0x1400239e7  mov     [rsp+68h+arg_8], rdi
0x1400239ec  lea     rdx, [r12+10h]
0x1400239f1  mov     ecx, 42h ; 'B'
0x1400239f6  mov     r8d, 6950534Dh
0x1400239fc  call    cs:__imp_ExAllocatePool2
0x140023a03  nop     dword ptr [rax+rax+00h]
0x140023a08  mov     rsi, rax
0x140023a0b  test    al, 0Fh
0x140023a0d  jnz     loc_1401FA564
0x140023a13  test    rax, rax
0x140023a16  jz      short loc_140023A32
0x140023a18  jmp     short loc_140023A26
0x140023a1a  mov     rsi, rax
0x140023a1d  test    rax, rax
0x140023a20  jz      loc_140023D2F
0x140023a26  mov     rax, [rsp+68h+arg_8]
0x140023a2b  mov     [rsi], rax
0x140023a2e  add     rsi, 10h
0x140023a32  mov     [rsp+68h+arg_10], r12d
0x140023a3a  mov     dword ptr [rsp+68h+arg_8], edi
0x140023a3e  test    rsi, rsi
0x140023a41  jz      loc_140023AED
0x140023a47  mov     rdx, [rbx+30h]; Src
0x140023a4b  test    rdx, rdx
0x140023a4e  jz      short loc_140023A72
0x140023a50  mov     r8d, [rbx+38h]; Size
0x140023a54  mov     rcx, rsi; void *
0x140023a57  call    memmove
0x140023a5c  mov     eax, [rbx+48h]
0x140023a5f  mov     rcx, [rbx+30h]
0x140023a63  test    al, 8
0x140023a65  jz      short loc_140023AAE
0x140023a67  mov     byte ptr [rcx-97Fh], 0
0x140023a6e  and     dword ptr [rbx+48h], 0FFFFFFF7h
0x140023a72  mov     eax, [rbx+48h]
0x140023a75  and     eax, 0FFFFFFF7h
0x140023a78  mov     [rbx+30h], rsi
0x140023a7c  or      eax, dword ptr [rsp+68h+arg_8]
0x140023a80  mov     [rbx+48h], eax
0x140023a83  mov     eax, [rsp+68h+arg_10]
0x140023a8a  mov     [rbx+38h], eax
0x140023a8d  mov     rax, [rsp+68h+Src]
0x140023a92  test    rax, rax
0x140023a95  jz      loc_1400237F6
0x140023a9b  mov     r8, r12; Size
0x140023a9e  mov     rdx, rax; Src
0x140023aa1  mov     rcx, rsi; void *
0x140023aa4  call    memmove
0x140023aa9  jmp     loc_1400237F6
0x140023aae  test    rcx, rcx
0x140023ab1  jz      short loc_140023A72
0x140023ab3  mov     rdi, [rcx-10h]
0x140023ab7  lea     r8, [rcx-10h]
0x140023abb  test    rdi, rdi
0x140023abe  jz      loc_140023D55
0x140023ac4  cmp     byte ptr [rdi+8], 0
0x140023ac8  jz      loc_140023D39
0x140023ace  cmp     byte ptr [rdi+9], 0
0x140023ad2  lea     rcx, [rdi+40h]; Lookaside
0x140023ad6  mov     rdx, r8; Entry
0x140023ad9  jz      loc_140023C20
0x140023adf  call    cs:__imp_ExFreeToNPagedLookasideList
0x140023ae6  nop     dword ptr [rax+rax+00h]
0x140023aeb  jmp     short loc_140023A72
0x140023aed  mov     eax, [rbx+68h]
0x140023af0  test    al, 8
0x140023af2  jz      short loc_140023B02
0x140023af4  mov     rax, [rbx+88h]
0x140023afb  mov     byte ptr [rax+87h], 0
0x140023b02  mov     eax, [rbx+68h]
0x140023b05  mov     esi, eax
0x140023b07  and     esi, 8
0x140023b0a  test    al, 10h
0x140023b0c  jz      short loc_140023B23
0x140023b0e  mov     eax, [rbx+98h]
0x140023b14  nop
0x140023b15  neg     eax
0x140023b17  movsxd  rcx, eax
0x140023b1a  lock add cs:?GlobalCachedPinPageCount@CmsCachedPin@@2_JA, rcx; __int64 CmsCachedPin::GlobalCachedPinPageCount
0x140023b22  nop
0x140023b23  mov     rcx, [rbx+30h]; void *
0x140023b27  test    rcx, rcx
0x140023b2a  jz      short loc_140023B49
0x140023b2c  mov     eax, [rbx+48h]
0x140023b2f  test    al, 8
0x140023b31  jz      loc_140023C44
0x140023b37  mov     byte ptr [rcx-97Fh], 0
0x140023b3e  and     dword ptr [rbx+48h], 0FFFFFFF7h
0x140023b42  mov     [rbx+30h], rdi
0x140023b46  mov     [rbx+38h], edi
0x140023b49  test    esi, esi
0x140023b4b  jnz     loc_140023C3D
0x140023b51  mov     r8, [rbx+80h]
0x140023b58  test    r8, r8
0x140023b5b  jz      loc_140023C3D
0x140023b61  mov     rbx, [r8-10h]
0x140023b65  add     r8, 0FFFFFFFFFFFFFFF0h
0x140023b69  test    rbx, rbx
0x140023b6c  jz      loc_140023D87
0x140023b72  cmp     [rbx+8], sil
0x140023b76  jz      loc_140023D6B
0x140023b7c  lea     rcx, [rbx+40h]; Lookaside
0x140023b80  mov     rdx, r8; Entry
0x140023b83  cmp     [rbx+9], sil
0x140023b87  jnz     loc_140023C31
0x140023b8d  call    cs:__imp_ExFreeToPagedLookasideList
0x140023b94  nop     dword ptr [rax+rax+00h]
0x140023b99  xor     eax, eax
0x140023b9b  jmp     loc_1400238EC
0x140023ba0  cmp     byte ptr [rdx+8], 0
0x140023ba4  jnz     loc_140023CF3
0x140023baa  mov     rcx, [rdx+58h]
0x140023bae  mov     rax, rcx
0x140023bb1  shr     rax, 20h
0x140023bb5  cmp     ecx, eax
0x140023bb7  jle     short loc_140023BD8
0x140023bb9  nop
0x140023bba  mov     ecx, 0FFFFFFFFh
0x140023bbf  lock xadd [rdx+58h], ecx
0x140023bc4  nop
0x140023bc5  dec     ecx
0x140023bc7  mov     eax, [rdx+5Ch]
  ... truncated ...
```
