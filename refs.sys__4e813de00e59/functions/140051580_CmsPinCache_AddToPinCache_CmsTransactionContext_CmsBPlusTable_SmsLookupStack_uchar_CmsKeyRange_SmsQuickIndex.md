# CmsPinCache::AddToPinCache(CmsTransactionContext *,CmsBPlusTable *,SmsLookupStack *,uchar,CmsKeyRange *,_SmsQuickIndex *)

- ea: `0x140051580`
- end: `0x140051e67`
- name: `?AddToPinCache@CmsPinCache@@QEAAXPEAVCmsTransactionContext@@PEAVCmsBPlusTable@@PEAUSmsLookupStack@@EPEAVCmsKeyRange@@PEAU_SmsQuickIndex@@@Z`
- size: `2279`
- prototype: `void __usercall(CmsPinCache *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, struct CmsBPlusTable *@<r8>, struct SmsLookupStack *@<r9>, unsigned __int8, struct CmsKeyRange *, struct _SmsQuickIndex *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x1400a1b40`

## callees

- `0x14004c7a0`
- `0x140051580`
- `0x140051e70`
- `0x140052030`
- `0x140052710`
- `0x140089420`
- `0x1400cb544`
- `0x1400ceda0`
- `0x1401f4100`
- `0x1401f4400`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140051b76`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140051b76`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140051dbc`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140051e07`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140051dbc`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140051e07`
- `ntoskrnl!ExAllocatePool2` at `0x14005193f`
- `ntoskrnl!ExAllocatePool2` at `0x1400519dd`
- `ntoskrnl!ExAllocatePool2` at `0x14005193f`
- `ntoskrnl!ExAllocatePool2` at `0x1400519dd`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400518fe`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005199e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400518fe`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005199e`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fd5cd`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fd5df`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fd5cd`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fd5df`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140051c32`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140051c32`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fd5f8`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fd5f8`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140051dd9`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140051e24`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140051dd9`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140051e24`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051e56`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051e56`

## string_xrefs

- `0x1401fd614`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
void __fastcall CmsPinCache::AddToPinCache(
        CmsPinCache *this,
        struct CmsTransactionContext *a2,
        struct CmsBPlusTable *a3,
        struct SmsLookupStack *a4,
        unsigned __int8 a5,
        struct CmsKeyRange *a6,
        struct _SmsQuickIndex *a7)
{
  struct SmsLookupStack *v7; // r11
  char v8; // r9
  CmsPinCache *v10; // r15
  __int64 v11; // rcx
  CmsPinCache *v13; // r12
  __int64 v14; // r9
  CmsPinCache *v15; // r9
  bool v16; // r10
  __int64 i; // rax
  __int64 v18; // r8
  struct SmsLookupStack *v19; // r11
  char v20; // r8
  CmsPinCache *v21; // rbp
  __int64 v22; // r13
  unsigned int v23; // ecx
  unsigned int v24; // edx
  char v25; // al
  CmsPinCache *v26; // r14
  unsigned int v27; // ebx
  unsigned int *v28; // r14
  char *v29; // rbx
  size_t v30; // rbp
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rbx
  __int64 v34; // r9
  __int64 v35; // rdx
  __int64 Pool2; // rax
  _QWORD *v37; // r14
  int v38; // r13d
  __int64 v39; // r9
  __int64 v40; // r13
  size_t v41; // rdx
  __int64 v42; // rax
  int v43; // eax
  CmsPinCache *v44; // rdx
  __int64 v45; // r8
  CmsPinCache **v46; // rax
  __int64 v47; // rax
  const void *v48; // rdx
  __int64 v49; // rcx
  unsigned int v50; // eax
  struct _SLIST_ENTRY *v51; // r8
  __int64 v52; // rcx
  int v53; // ecx
  int v54; // ecx
  __int64 v55; // r13
  __int64 v56; // rdi
  __int64 v57; // rcx
  __int64 *v58; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v59; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v60; // rcx
  _QWORD *v61; // rax
  __int64 v62; // rdx
  void *Src; // [rsp+30h] [rbp-68h]
  unsigned int Srca; // [rsp+30h] [rbp-68h]
  unsigned __int8 v65; // [rsp+38h] [rbp-60h]
  char *v66; // [rsp+38h] [rbp-60h]
  __int64 v67; // [rsp+40h] [rbp-58h]
  __int64 v68; // [rsp+40h] [rbp-58h]
  struct _LIST_ENTRY v69; // [rsp+48h] [rbp-50h] BYREF
  unsigned int v70; // [rsp+A8h] [rbp+10h]
  int v71; // [rsp+A8h] [rbp+10h]

  v7 = a4;
  v8 = byte_140269179;
  v10 = this;
  v11 = *((_QWORD *)a3 + 4);
  if ( !a5 )
    v8 = HIBYTE(word_140269177);
  v13 = (CmsPinCache *)((char *)this + 16);
  v65 = v8;
  v14 = 32;
  if ( a5 )
  {
    v10 = (CmsPinCache *)((char *)this + 16);
    v14 = 36;
  }
  v67 = v14;
  v15 = *(CmsPinCache **)a2;
  v69 = 0;
  v16 = ((unsigned __int64)v15 & 0x30000000000000LL) != 0 && v11 != *(_QWORD *)(v11 + 64);
  if ( (*(_BYTE *)(v11 + 14) & 0x40) == 0 && (*(_DWORD *)(*(_QWORD *)(v11 + 24) + 44LL) & 0x80u) == 0
    || CmsBPlusTable::HasGlobalBindingSemantics((CmsBPlusTable *)v11)
    && ((v57 = *((_QWORD *)a2 + 1), !v20) ? (v58 = (__int64 *)(v57 + 16)) : (v58 = *(__int64 **)(v57 + 3248)),
        (v11 = *v58) != 0) )
  {
    for ( i = 0; (unsigned int)i < 0xD; i = (unsigned int)(i + 1) )
    {
      v18 = *((_QWORD *)a2 + i + 53);
      if ( !v18 )
        break;
      if ( v18 == v11 )
      {
        if ( !v16 || *((_BYTE *)a2 + 2 * i + 528) || *((_BYTE *)a2 + 2 * i + 529) )
          goto LABEL_22;
        break;
      }
    }
    if ( ((unsigned __int16)v15 & 0x800) == 0 && ((unsigned __int64)v15 & 0x80000000000000LL) == 0 )
      return;
  }
LABEL_22:
  v21 = (struct CmsTransactionContext *)((char *)a2 + 824);
  v22 = *(_QWORD *)v7;
  v23 = 0;
  v69.Blink = &v69;
  v69.Flink = &v69;
  if ( this == (struct CmsTransactionContext *)((char *)a2 + 824) )
    v24 = HIBYTE(word_140269177);
  else
    v24 = (unsigned __int16)dword_14026916C;
  v25 = *(_BYTE *)(v22 + 392);
  v70 = v24;
  if ( v25 && (v25 != -8 || *(_BYTE *)(*(_QWORD *)(v22 + 96) + 212LL)) )
  {
    if ( this == v21 )
      v24 = (unsigned __int8)byte_140269179;
    else
      v24 = (unsigned __int16)dword_140269170;
    v26 = *(CmsPinCache **)v13;
    v70 = v24;
  }
  else
  {
    v26 = *(CmsPinCache **)this;
    v13 = this;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      if ( v26 == v13 || v23 >= v24 )
      {
        v27 = v65;
        v28 = (unsigned int *)((char *)this + v67);
        v66 = (char *)this + v67;
        while ( *v28 >= v27 )
        {
          v55 = *((_QWORD *)v10 + 1);
          if ( this != v21
            || !CmsPinCache::TransferOneCachedPin(
                  this,
                  a2,
                  (struct CmsCachedPin *)(v55 - 16),
                  *(struct CmsBPlusTable **)(*(_QWORD *)(v55 + 24) + 32LL),
                  &v69) )
          {
            CmsPinCache::DoomCachedPin(this, (struct CmsCachedPin *)(v55 - 16), &v69, (struct _LIST_ENTRY **)v15);
          }
        }
        if ( this == v21 && !*((_BYTE *)a2 + 135) )
        {
          v29 = (char *)a2 + 2656;
          if ( a2 != (struct CmsTransactionContext *)-2656LL )
          {
            *(_QWORD *)v29 = 0;
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
            *(_QWORD *)v29 = 0;
            *(_QWORD *)((char *)a2 + 2804) = 0;
          }
          *((_DWORD *)a2 + 690) |= 8u;
          *((_BYTE *)a2 + 135) = 1;
          *((_QWORD *)a2 + 349) = a2;
          goto LABEL_33;
        }
        v33 = qword_140269438 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
        if ( *(_DWORD *)v33 < 0xC0u )
        {
          v33 = 0;
          v35 = 208;
LABEL_41:
          Pool2 = ExAllocatePool2(66, v35, 1766871885, v34);
          if ( (Pool2 & 0xF) != 0 )
            goto LABEL_137;
          if ( !Pool2 )
            goto LABEL_15;
          goto LABEL_100;
        }
        if ( !*(_BYTE *)(v33 + 8) )
        {
          if ( (int)*(_QWORD *)(v33 + 88) > (int)HIDWORD(*(_QWORD *)(v33 + 88)) )
          {
            v54 = _InterlockedDecrement((volatile signed __int32 *)(v33 + 88));
            if ( v54 >= *(_DWORD *)(v33 + 92) && v54 >= 0 )
            {
              Pool2 = (__int64)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v33 + 64));
              goto LABEL_99;
            }
            _InterlockedIncrement((volatile signed __int32 *)(v33 + 88));
          }
LABEL_90:
          v35 = *(unsigned int *)(v33 + 4);
          goto LABEL_41;
        }
        v59 = (struct _NPAGED_LOOKASIDE_LIST *)(v33 + 64);
        if ( *(_BYTE *)(v33 + 9) )
          Pool2 = (__int64)ExAllocateFromNPagedLookasideList(v59);
        else
          Pool2 = (__int64)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v59);
LABEL_99:
        if ( Pool2 )
        {
LABEL_100:
          v56 = Pool2 + 16;
          *(_QWORD *)Pool2 = v33;
          if ( Pool2 == -16 )
            goto LABEL_15;
          memset((void *)(Pool2 + 16), 0, 0xC0u);
          v29 = (char *)(v56 + 32);
          *(_BYTE *)(v56 + 26) = 32;
          if ( v56 != -32 )
          {
            *(_DWORD *)(v56 + 104) |= 3u;
            *(_QWORD *)(v56 + 56) = v56 + 48;
            *(_QWORD *)(v56 + 48) = v56 + 48;
            *(_QWORD *)(v56 + 180) = 0;
          }
          *(_QWORD *)(v56 + 160) = v56;
LABEL_33:
          if ( !v29 )
            goto LABEL_15;
          *((_QWORD *)v29 + 5) = a3;
          if ( *((_QWORD *)v29 + 6) )
            CmsKeyRange::FreeKeysBuffer((CmsKeyRange *)(v29 + 48));
          *((_OWORD *)v29 + 3) = 0;
          *((_OWORD *)v29 + 4) = 0;
          *((_DWORD *)v29 + 18) |= 3u;
          v30 = *((unsigned int *)a6 + 2);
          if ( !(_DWORD)v30 )
            goto LABEL_37;
          Src = *(void **)a6;
          if ( !*((_BYTE *)a2 + 129) && (unsigned int)v30 <= 0x60 )
          {
            *((_BYTE *)a2 + 129) = 1;
            v37 = (_QWORD *)((char *)a2 + 2560);
            v38 = 96;
            v71 = 8;
            goto LABEL_64;
          }
          v40 = qword_140269420 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
          if ( (unsigned int)v30 > *(_DWORD *)v40 )
          {
            v40 = 0;
            v41 = v30 + 16;
            goto LABEL_49;
          }
          if ( !*(_BYTE *)(v40 + 8) )
          {
            if ( (int)*(_QWORD *)(v40 + 88) > (int)HIDWORD(*(_QWORD *)(v40 + 88)) )
            {
              v53 = _InterlockedDecrement((volatile signed __int32 *)(v40 + 88));
              if ( v53 >= *(_DWORD *)(v40 + 92) && v53 >= 0 )
              {
                v61 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v40 + 64));
                goto LABEL_61;
              }
              _InterlockedIncrement((volatile signed __int32 *)(v40 + 88));
            }
LABEL_85:
            v41 = *(unsigned int *)(v40 + 4);
LABEL_49:
            v42 = ExAllocatePool2(66, v41, 1766871885, v39);
            v37 = (_QWORD *)v42;
            if ( (v42 & 0xF) == 0 )
            {
              if ( !v42 )
              {
LABEL_63:
                v38 = v30;
                v71 = 0;
LABEL_64:
                if ( !v37 )
                {
                  CmsCachedPin::Destroy((struct CmsCachedPin *)v29);
                  goto LABEL_15;
                }
                v48 = (const void *)*((_QWORD *)v29 + 6);
                if ( !v48 )
                  goto LABEL_68;
                memmove(v37, v48, *((unsigned int *)v29 + 14));
                v49 = *((_QWORD *)v29 + 6);
                if ( (*((_DWORD *)v29 + 18) & 8) != 0 )
                {
                  *(_BYTE *)(v49 - 2431) = 0;
                  *((_DWORD *)v29 + 18) &= ~8u;
                }
                else if ( v49 )
                {
                  v51 = (struct _SLIST_ENTRY *)(v49 - 16);
                  v52 = *(_QWORD *)(v49 - 16);
                  v68 = v52;
                  if ( !v52 )
                    goto LABEL_130;
                  if ( *(_BYTE *)(v52 + 8) )
                  {
                    if ( *(_BYTE *)(v52 + 9) )
                      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v52 + 64), v51);
                    else
                      ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)(v52 + 64), v51);
                    goto LABEL_68;
                  }
                  v62 = *(_QWORD *)(v52 + 88);
                  if ( (int)v62 < *(_DWORD *)(v52 + 80) || SHIDWORD(v62) >= (int)v62 )
                  {
                    ExpInterlockedPushEntrySList((PSLIST_HEADER)(v52 + 64), v51);
                    _InterlockedIncrement((volatile signed __int32 *)(v68 + 88));
                  }
                  else
                  {
LABEL_130:
                    ExFreePoolWithTag(v51, 0);
                  }
                }
LABEL_68:
                v50 = *((_DWORD *)v29 + 18) & 0xFFFFFFF7;
                *((_QWORD *)v29 + 6) = v37;
                *((_DWORD *)v29 + 18) = v71 | v50;
                *((_DWORD *)v29 + 14) = v38;
                if ( Src )
                  memmove(v37, Src, v30);
                v28 = (unsigned int *)v66;
LABEL_37:
                v19 = a4;
                *((_DWORD *)v29 + 15) = *((_DWORD *)a6 + 3);
                *((_DWORD *)v29 + 16) = *((_DWORD *)a6 + 4);
                *((_WORD *)v29 + 34) = *((_WORD *)a6 + 10);
                *((_WORD *)v29 + 35) = *((_WORD *)a6 + 11);
                *((_DWORD *)v29 + 18) = *((_DWORD *)a6 + 6) ^ (*((_DWORD *)v29 + 18) ^ *((_DWORD *)a6 + 6)) & 8;
                _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)a4 + 380LL));
                *((_DWORD *)v29 + 22) = *(_DWORD *)(*(_QWORD *)a4 + 368LL);
                *((_DWORD *)v29 + 23) = *((_DWORD *)a3 + 46);
                *((_QWORD *)v29 + 12) = *((_QWORD *)a3 + 20);
                *((_QWORD *)v29 + 14) = *((_QWORD *)a4 + 4);
                *((_QWORD *)v29 + 15) = *((_QWORD *)a4 + 1);
                v31 = *(_QWORD *)a4;
                *((_DWORD *)v29 + 26) |= 1u;
                *((_QWORD *)v29 + 4) = v31;
                v29[144] = a5;
                *((_QWORD *)v29 + 10) = _InterlockedIncrement64((volatile signed __int64 *)&NextCachedPinId);
                v32 = *(_QWORD *)v10;
                if ( *(CmsPinCache **)(*(_QWORD *)v10 + 8LL) == v10 )
                {
                  *((_QWORD *)v29 + 2) = v32;
                  *((_QWORD *)v29 + 3) = v10;
                  *(_QWORD *)(v32 + 8) = v29 + 16;
                  *(_QWORD *)v10 = v29 + 16;
                  ++*v28;
                  goto LABEL_19;
                }
LABEL_38:
                __fastfail(3u);
              }
LABEL_62:
              *v37 = v40;
              v37 += 2;
              goto LABEL_63;
            }
LABEL_137:
            MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
          }
          v60 = (struct _NPAGED_LOOKASIDE_LIST *)(v40 + 64);
          if ( *(_BYTE *)(v40 + 9) )
            v61 = ExAllocateFromNPagedLookasideList(v60);
          else
            v61 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v60);
LABEL_61:
          v37 = v61;
          if ( v61 )
            goto LABEL_62;
          goto LABEL_85;
        }
        goto LABEL_90;
      }
      v43 = *((_DWORD *)v26 + 14);
      v29 = (char *)v26 - 16;
      v15 = *(CmsPinCache **)v26;
      Srca = v23 + 1;
      v44 = v26;
      v26 = *(CmsPinCache **)v26;
      if ( (v43 & 4) == 0 )
      {
        v45 = *((_QWORD *)v29 + 4);
        if ( *((_DWORD *)v29 + 22) == *(_DWORD *)(v45 + 368)
          && *((_DWORD *)v29 + 23) == *(_DWORD *)(*((_QWORD *)v29 + 5) + 184LL) )
        {
          break;
        }
      }
      CmsPinCache::DoomCachedPin(this, (struct CmsCachedPin *)v29, &v69, (struct _LIST_ENTRY **)v15);
      v23 = Srca;
      v24 = v70;
    }
    if ( v45 == v22 )
      break;
    ++v23;
    v24 = v70;
  }
  if ( *((CmsPinCache **)v15 + 1) != v44 )
    goto LABEL_38;
  v46 = (CmsPinCache **)*((_QWORD *)v44 + 1);
  if ( *v46 != v44 )
    goto LABEL_38;
  *v46 = v15;
  *((_QWORD *)v15 + 1) = v46;
  v47 = *(_QWORD *)v10;
  if ( *(CmsPinCache **)(*(_QWORD *)v10 + 8LL) != v10 )
    goto LABEL_38;
  *(_QWORD *)v44 = v47;
  *((_QWORD *)v44 + 1) = v10;
  *(_QWORD *)(v47 + 8) = v44;
  *(_QWORD *)v10 = v44;
  if ( !v29 )
    goto LABEL_15;
  v19 = a4;
LABEL_19:
  if ( a7 )
  {
    *((_QWORD *)a7 + 2) = *((_QWORD *)v29 + 10);
    *((_BYTE *)a7 + 8) = (*((_DWORD *)v29 + 26) & 0x10) != 0;
    *((_DWORD *)a7 + 6) = *((_DWORD *)v19 + 6);
    *((_DWORD *)a7 + 7) = *(_DWORD *)(*(_QWORD *)v19 + 372LL);
    *(_QWORD *)a7 = *((_QWORD *)v19 + 2);
  }
LABEL_15:
  CmsPinCache::DeleteDoomedCachedPins(a2, &v69);
}

```

## disassembly

```asm
0x140051580  mov     [rsp+arg_18], r9
0x140051585  mov     [rsp+arg_10], r8
0x14005158a  push    rsi
0x14005158b  push    rdi
0x14005158c  push    r12
0x14005158e  push    r15
0x140051590  sub     rsp, 78h
0x140051594  movzx   eax, byte ptr cs:word_140269177+1
0x14005159b  mov     r11, r9
0x14005159e  movzx   r9d, cs:byte_140269179
0x1400515a6  mov     rdi, rcx
0x1400515a9  movzx   ecx, [rsp+98h+arg_20]
0x1400515b1  mov     r15, rdi
0x1400515b4  test    cl, cl
0x1400515b6  xorps   xmm0, xmm0
0x1400515b9  mov     rcx, [r8+20h]; this
0x1400515bd  mov     rsi, rdx
0x1400515c0  cmovz   r9d, eax
0x1400515c4  lea     r12, [rdi+10h]
0x1400515c8  mov     dword ptr [rsp+98h+var_60], r9d
0x1400515cd  mov     eax, 24h ; '$'
0x1400515d2  mov     r9d, 20h ; ' '
0x1400515d8  cmovnz  r15, r12
0x1400515dc  cmovnz  r9d, eax
0x1400515e0  mov     rax, 30000000000000h
0x1400515ea  mov     [rsp+98h+var_58], r9
0x1400515ef  mov     r9, [rdx]
0x1400515f2  movups  xmmword ptr [rsp+98h+var_50.Flink], xmm0
0x1400515f7  test    rax, r9
0x1400515fa  jnz     loc_140051D16
0x140051600  xor     r10b, r10b
0x140051603  movzx   r8d, byte ptr [rcx+0Eh]
0x140051608  and     r8b, 40h
0x14005160c  jnz     loc_1400516EB
0x140051612  mov     rax, [rcx+18h]
0x140051616  mov     edx, [rax+2Ch]
0x140051619  test    dl, dl
0x14005161b  js      loc_1400516EB
0x140051621  xor     eax, eax
0x140051623  cmp     eax, 0Dh
0x140051626  jnb     loc_140051CFB
0x14005162c  mov     r8, [rsi+rax*8+1A8h]
0x140051634  test    r8, r8
0x140051637  jz      loc_140051CFB
0x14005163d  cmp     r8, rcx
0x140051640  jz      loc_1401FD5BF
0x140051646  inc     eax
0x140051648  jmp     short loc_140051623
0x14005164a  mov     [rdx], rax
0x14005164d  mov     [rdx+8], r15
0x140051651  mov     [rax+8], rdx
0x140051655  mov     [r15], rdx
0x140051658  test    rbx, rbx
0x14005165b  jnz     short loc_14005168D
0x14005165d  lea     rdx, [rsp+98h+var_50]; struct _LIST_ENTRY *
0x140051662  mov     rcx, rsi; struct CmsTransactionContext *
0x140051665  call    ?DeleteDoomedCachedPins@CmsPinCache@@SAXPEAVCmsTransactionContext@@PEAU_LIST_ENTRY@@@Z; CmsPinCache::DeleteDoomedCachedPins(CmsTransactionContext *,_LIST_ENTRY *)
0x14005166a  mov     rbx, [rsp+98h+arg_0]
0x140051672  mov     rbp, [rsp+98h+var_28]
0x140051677  mov     r13, [rsp+98h+var_30]
0x14005167c  mov     r14, [rsp+98h+var_38]
0x140051681  add     rsp, 78h
0x140051685  pop     r15
0x140051687  pop     r12
0x140051689  pop     rdi
0x14005168a  pop     rsi
0x14005168b  retn
0x14005168d  mov     r11, [rsp+98h+arg_18]
0x140051695  jmp     short loc_1400516AC
0x140051697  lea     rax, [rbx+10h]
0x14005169b  mov     [rax], rcx
0x14005169e  mov     [rax+8], r15
0x1400516a2  mov     [rcx+8], rax
0x1400516a6  mov     [r15], rax
0x1400516a9  inc     dword ptr [r14]
0x1400516ac  mov     rdx, [rsp+98h+arg_30]
0x1400516b4  test    rdx, rdx
0x1400516b7  jz      short loc_14005165D
0x1400516b9  mov     rax, [rbx+50h]
0x1400516bd  mov     [rdx+10h], rax
0x1400516c1  mov     eax, [rbx+68h]
0x1400516c4  shr     eax, 4
0x1400516c7  and     al, 1
0x1400516c9  mov     [rdx+8], al
0x1400516cc  mov     eax, [r11+18h]
0x1400516d0  mov     [rdx+18h], eax
0x1400516d3  mov     rax, [r11]
0x1400516d6  mov     ecx, [rax+174h]
0x1400516dc  mov     [rdx+1Ch], ecx
0x1400516df  mov     rax, [r11+10h]
0x1400516e3  mov     [rdx], rax
0x1400516e6  jmp     loc_14005165D
0x1400516eb  call    ?HasGlobalBindingSemantics@CmsBPlusTable@@QEBA_NXZ; CmsBPlusTable::HasGlobalBindingSemantics(void)
0x1400516f0  test    al, al
0x1400516f2  jnz     loc_140051D46
0x1400516f8  mov     [rsp+98h+var_28], rbp
0x1400516fd  lea     rax, [rsp+98h+var_50]
0x140051702  mov     [rsp+98h+var_30], r13
0x140051707  lea     rbp, [rsi+338h]
0x14005170e  mov     r13, [r11]
0x140051711  xor     ecx, ecx
0x140051713  mov     [rsp+98h+var_50.Blink], rax
0x140051718  lea     rax, [rsp+98h+var_50]
0x14005171d  mov     [rsp+98h+var_50.Flink], rax
0x140051722  mov     [rsp+98h+var_38], r14
0x140051727  cmp     rdi, rbp
0x14005172a  jnz     loc_140051C84
0x140051730  movzx   edx, byte ptr cs:word_140269177+1
0x140051737  movzx   eax, byte ptr [r13+188h]
0x14005173f  mov     [rsp+98h+arg_8], edx
0x140051746  test    al, al
0x140051748  jnz     loc_140051B18
0x14005174e  mov     r14, [rdi]
0x140051751  mov     r12, rdi
0x140051754  mov     [rsp+98h+arg_0], rbx
0x14005175c  cmp     r14, r12
0x14005175f  jnz     loc_140051A02
0x140051765  movzx   ebx, byte ptr [rsp+98h+var_60]
0x14005176a  mov     r14, [rsp+98h+var_58]
0x14005176f  add     r14, rdi
0x140051772  mov     [rsp+98h+var_60], r14
0x140051777  cmp     [r14], ebx
0x14005177a  jnb     loc_140051C43
0x140051780  cmp     rdi, rbp
0x140051783  jnz     loc_1400518FC
0x140051789  cmp     byte ptr [rsi+87h], 0
0x140051790  jnz     loc_1400518FC
0x140051796  lea     rbx, [rsi+0A60h]
0x14005179d  test    rbx, rbx
0x1400517a0  jz      short loc_1400517E0
0x1400517a2  xor     r8d, r8d
0x1400517a5  lea     rax, [rbx+10h]
0x1400517a9  mov     [rbx], r8
0x1400517ac  mov     [rbx+8], r8
0x1400517b0  or      dword ptr [rbx+48h], 3
0x1400517b4  mov     [rbx+30h], r8
0x1400517b8  mov     [rbx+38h], r8
0x1400517bc  mov     [rbx+40h], r8
0x1400517c0  mov     [rbx+68h], r8d
0x1400517c4  mov     [rbx+88h], r8
0x1400517cb  mov     [rax+8], rax
0x1400517cf  mov     [rax], rax
0x1400517d2  mov     [rbx+8], r8
0x1400517d6  mov     [rbx], r8
0x1400517d9  mov     [rbx+94h], r8
0x1400517e0  or      dword ptr [rbx+68h], 8
0x1400517e4  mov     byte ptr [rsi+87h], 1
0x1400517eb  mov     [rbx+88h], rsi
0x1400517f2  test    rbx, rbx
0x1400517f5  jz      loc_14005165D
0x1400517fb  mov     rax, [rsp+98h+arg_10]
0x140051803  mov     [rbx+28h], rax
0x140051807  cmp     qword ptr [rbx+30h], 0
0x14005180c  jnz     loc_140051DEA
0x140051812  mov     r12, [rsp+98h+arg_28]
0x14005181a  xorps   xmm0, xmm0
0x14005181d  movups  xmmword ptr [rbx+30h], xmm0
0x140051821  movups  xmmword ptr [rbx+40h], xmm0
0x140051825  or      dword ptr [rbx+48h], 3
0x140051829  mov     ebp, [r12+8]
0x14005182e  test    ebp, ebp
0x140051830  jnz     loc_140051961
0x140051836  mov     eax, [r12+0Ch]
0x14005183b  mov     r11, [rsp+98h+arg_18]
0x140051843  mov     [rbx+3Ch], eax
0x140051846  mov     eax, [r12+10h]
0x14005184b  mov     [rbx+40h], eax
0x14005184e  movzx   eax, word ptr [r12+14h]
0x140051854  mov     [rbx+44h], ax
0x140051858  movzx   eax, word ptr [r12+16h]
0x14005185e  mov     [rbx+46h], ax
0x140051862  mov     eax, [r12+18h]
0x140051867  mov     ecx, eax
0x140051869  xor     ecx, [rbx+48h]
0x14005186c  and     ecx, 8
0x14005186f  xor     ecx, eax
0x140051871  mov     [rbx+48h], ecx
0x140051874  mov     rax, [r11]
0x140051877  nop
0x140051878  lock inc dword ptr [rax+17Ch]
0x14005187f  nop
0x140051880  mov     rax, [r11]
0x140051883  mov     ecx, [rax+170h]
0x140051889  mov     [rbx+58h], ecx
0x14005188c  mov     rcx, [rsp+98h+arg_10]
0x140051894  mov     eax, [rcx+0B8h]
0x14005189a  mov     [rbx+5Ch], eax
0x14005189d  mov     rax, [rcx+0A0h]
0x1400518a4  mov     [rbx+60h], rax
0x1400518a8  mov     rax, [r11+20h]
0x1400518ac  mov     [rbx+70h], rax
0x1400518b0  mov     rax, [r11+8]
0x1400518b4  mov     [rbx+78h], rax
0x1400518b8  mov     rax, [r11]
0x1400518bb  or      dword ptr [rbx+68h], 1
0x1400518bf  mov     [rbx+20h], rax
0x1400518c3  movzx   eax, [rsp+98h+arg_20]
0x1400518cb  mov     [rbx+90h], al
0x1400518d1  nop
0x1400518d2  mov     eax, 1
0x1400518d7  lock xadd cs:?NextCachedPinId@@3_KA, rax; unsigned __int64 NextCachedPinId
0x1400518e0  nop
0x1400518e1  inc     rax
0x1400518e4  mov     [rbx+50h], rax
0x1400518e8  mov     rcx, [r15]
0x1400518eb  cmp     [rcx+8], r15
0x1400518ef  jz      loc_140051697
0x1400518f5  mov     ecx, 3
0x1400518fa  int     29h; Win8: RtlFailFast(ecx)
0x1400518fc  xor     ecx, ecx; ProcNumber
0x1400518fe  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140051905  nop     dword ptr [rax+rax+00h]
0x14005190a  xor     edx, edx
0x14005190c  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140051912  lea     rbx, [rdx+rdx*2]
0x140051916  shl     rbx, 6
0x14005191a  add     rbx, cs:qword_140269438
0x140051921  cmp     dword ptr [rbx], 0C0h
0x140051927  jnb     loc_140051BD9
0x14005192d  xor     ebx, ebx
0x14005192f  mov     edx, 0D0h
0x140051934  mov     ecx, 42h ; 'B'
0x140051939  mov     r8d, 6950534Dh
0x14005193f  call    cs:__imp_ExAllocatePool2
0x140051946  nop     dword ptr [rax+rax+00h]
0x14005194b  test    al, 0Fh
0x14005194d  jnz     loc_1401FD614
0x140051953  test    rax, rax
0x140051956  jz      loc_14005165D
0x14005195c  jmp     loc_140051C99
0x140051961  cmp     byte ptr [rsi+81h], 0
0x140051968  mov     rax, [r12]
0x14005196c  mov     [rsp+98h+Src], rax
0x140051971  jnz     short loc_14005199C
0x140051973  cmp     ebp, 60h ; '`'
0x140051976  ja      short loc_14005199C
0x140051978  mov     byte ptr [rsi+81h], 1
0x14005197f  lea     r14, [rsi+0A00h]
0x140051986  mov     r13d, 60h ; '`'
0x14005198c  mov     [rsp+98h+arg_8], 8
0x140051997  jmp     loc_140051AAA
0x14005199c  xor     ecx, ecx; ProcNumber
0x14005199e  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400519a5  nop     dword ptr [rax+rax+00h]
0x1400519aa  xor     edx, edx
0x1400519ac  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x1400519b2  lea     r13, [rdx+rdx*2]
0x1400519b6  shl     r13, 6
0x1400519ba  add     r13, cs:qword_140269420
0x1400519c1  cmp     ebp, [r13+0]
0x1400519c5  jbe     loc_140051B94
0x1400519cb  xor     r13d, r13d
0x1400519ce  lea     rdx, [rbp+10h]
0x1400519d2  mov     ecx, 42h ; 'B'
0x1400519d7  mov     r8d, 6950534Dh
0x1400519dd  call    cs:__imp_ExAllocatePool2
0x1400519e4  nop     dword ptr [rax+rax+00h]
0x1400519e9  mov     r14, rax
0x1400519ec  test    al, 0Fh
0x1400519ee  jnz     loc_1401FD614
0x1400519f4  test    rax, rax
0x1400519f7  jz      loc_140051A9C
0x1400519fd  jmp     loc_140051A95
0x140051a02  cmp     ecx, edx
0x140051a04  jnb     loc_140051765
0x140051a0a  mov     eax, [r14+38h]
0x140051a0e  lea     rbx, [r14-10h]
0x140051a12  mov     r9, [r14]; struct _LIST_ENTRY **
0x140051a15  inc     ecx
0x140051a17  mov     dword ptr [rsp+98h+Src], ecx
0x140051a1b  mov     rdx, r14
0x140051a1e  mov     r14, r9
0x140051a21  test    al, 4
0x140051a23  jnz     loc_140051D78
0x140051a29  mov     r8, [rbx+20h]
0x140051a2d  mov     eax, [r8+170h]
0x140051a34  cmp     [rbx+58h], eax
0x140051a37  jnz     loc_140051D78
0x140051a3d  mov     rax, [rbx+28h]
0x140051a41  mov     ecx, [rax+0B8h]
0x140051a47  cmp     [rbx+5Ch], ecx
0x140051a4a  jnz     loc_140051D78
0x140051a50  cmp     r8, r13
0x140051a53  jnz     loc_140051D68
0x140051a59  cmp     [r9+8], rdx
0x140051a5d  jnz     loc_1400518F5
0x140051a63  mov     rax, [rdx+8]
0x140051a67  cmp     [rax], rdx
0x140051a6a  jnz     loc_1400518F5
0x140051a70  mov     [rax], r9
0x140051a73  mov     [r9+8], rax
0x140051a77  mov     rax, [r15]
0x140051a7a  cmp     [rax+8], r15
0x140051a7e  jnz     loc_1400518F5
0x140051a84  jmp     loc_14005164A
0x140051a89  mov     r14, rax
0x140051a8c  test    rax, rax
0x140051a8f  jz      loc_140051BD0
0x140051a95  mov     [r14], r13
0x140051a98  add     r14, 10h
  ... truncated ...
```
