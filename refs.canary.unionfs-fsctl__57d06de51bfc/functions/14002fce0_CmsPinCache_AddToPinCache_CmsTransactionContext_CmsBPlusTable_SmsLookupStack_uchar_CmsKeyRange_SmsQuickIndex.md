# CmsPinCache::AddToPinCache(CmsTransactionContext *,CmsBPlusTable *,SmsLookupStack *,uchar,CmsKeyRange *,_SmsQuickIndex *)

- ea: `0x14002fce0`
- end: `0x1400305c7`
- name: `?AddToPinCache@CmsPinCache@@QEAAXPEAVCmsTransactionContext@@PEAVCmsBPlusTable@@PEAUSmsLookupStack@@EPEAVCmsKeyRange@@PEAU_SmsQuickIndex@@@Z`
- size: `2279`
- prototype: `void __usercall(CmsPinCache *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, struct CmsBPlusTable *@<r8>, struct SmsLookupStack *@<r9>, char, struct CmsKeyRange *, struct _SmsQuickIndex *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x1400a6c94`

## callees

- `0x14002f250`
- `0x14002f3e0`
- `0x14002f4b0`
- `0x14002fce0`
- `0x140031ae0`
- `0x14008fa30`
- `0x1400c3a64`
- `0x1400c8574`
- `0x1401e9e40`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400302d6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400302d6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003051c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140030567`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003051c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140030567`
- `ntoskrnl!ExAllocatePool2` at `0x14003009f`
- `ntoskrnl!ExAllocatePool2` at `0x14003013d`
- `ntoskrnl!ExAllocatePool2` at `0x14003009f`
- `ntoskrnl!ExAllocatePool2` at `0x14003013d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14003005e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400300fe`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14003005e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400300fe`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f18ef`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f1901`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f18ef`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f1901`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140030392`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140030392`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f191a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f191a`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140030539`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140030584`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140030539`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140030584`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400305b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400305b6`

## string_xrefs

- `0x1401f1936`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
void __fastcall CmsPinCache::AddToPinCache(
        CmsPinCache *this,
        struct CmsTransactionContext *a2,
        struct CmsBPlusTable *a3,
        struct SmsLookupStack *a4,
        char a5,
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
  __int64 v34; // rdx
  __int64 Pool2; // rax
  _QWORD *v36; // r14
  int v37; // r13d
  __int64 v38; // r13
  size_t v39; // rdx
  __int64 v40; // rax
  int v41; // eax
  CmsPinCache *v42; // rdx
  __int64 v43; // r8
  CmsPinCache **v44; // rax
  __int64 v45; // rax
  const void *v46; // rdx
  __int64 v47; // rcx
  unsigned int v48; // eax
  struct _SLIST_ENTRY *v49; // r8
  __int64 v50; // rcx
  int v51; // ecx
  int v52; // ecx
  __int64 v53; // r13
  __int64 v54; // rdi
  __int64 v55; // rcx
  __int64 *v56; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v57; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v58; // rcx
  _QWORD *v59; // rax
  __int64 v60; // rdx
  void *Src; // [rsp+30h] [rbp-68h]
  unsigned int Srca; // [rsp+30h] [rbp-68h]
  unsigned __int8 v63; // [rsp+38h] [rbp-60h]
  char *v64; // [rsp+38h] [rbp-60h]
  __int64 v65; // [rsp+40h] [rbp-58h]
  __int64 v66; // [rsp+40h] [rbp-58h]
  struct _LIST_ENTRY v67; // [rsp+48h] [rbp-50h] BYREF
  unsigned int v68; // [rsp+A8h] [rbp+10h]
  int v69; // [rsp+A8h] [rbp+10h]

  v7 = a4;
  v8 = byte_140262179;
  v10 = this;
  v11 = *((_QWORD *)a3 + 4);
  if ( !a5 )
    v8 = HIBYTE(word_140262177);
  v13 = (CmsPinCache *)((char *)this + 16);
  v63 = v8;
  v14 = 32;
  if ( a5 )
  {
    v10 = (CmsPinCache *)((char *)this + 16);
    v14 = 36;
  }
  v65 = v14;
  v15 = *(CmsPinCache **)a2;
  v67 = 0;
  v16 = ((unsigned __int64)v15 & 0x30000000000000LL) != 0 && v11 != *(_QWORD *)(v11 + 64);
  if ( (*(_BYTE *)(v11 + 14) & 0x40) == 0 && (*(_DWORD *)(*(_QWORD *)(v11 + 24) + 44LL) & 0x80u) == 0
    || CmsBPlusTable::HasGlobalBindingSemantics((CmsBPlusTable *)v11)
    && ((v55 = *((_QWORD *)a2 + 1), !v20) ? (v56 = (__int64 *)(v55 + 16)) : (v56 = *(__int64 **)(v55 + 3312)),
        (v11 = *v56) != 0) )
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
  v67.Blink = &v67;
  v67.Flink = &v67;
  if ( this == (struct CmsTransactionContext *)((char *)a2 + 824) )
    v24 = HIBYTE(word_140262177);
  else
    v24 = (unsigned __int16)dword_14026216C;
  v25 = *(_BYTE *)(v22 + 392);
  v68 = v24;
  if ( v25 && (v25 != -8 || *(_BYTE *)(*(_QWORD *)(v22 + 96) + 212LL)) )
  {
    if ( this == v21 )
      v24 = (unsigned __int8)byte_140262179;
    else
      v24 = (unsigned __int16)dword_140262170;
    v26 = *(CmsPinCache **)v13;
    v68 = v24;
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
        v27 = v63;
        v28 = (unsigned int *)((char *)this + v65);
        v64 = (char *)this + v65;
        while ( *v28 >= v27 )
        {
          v53 = *((_QWORD *)v10 + 1);
          if ( this != v21
            || !CmsPinCache::TransferOneCachedPin(
                  this,
                  a2,
                  (struct CmsCachedPin *)(v53 - 16),
                  *(struct CmsBPlusTable **)(*(_QWORD *)(v53 + 24) + 32LL),
                  &v67) )
          {
            CmsPinCache::DoomCachedPin(this, (struct CmsCachedPin *)(v53 - 16), &v67, (struct _LIST_ENTRY **)v15);
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
        v33 = qword_140262438 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
        if ( *(_DWORD *)v33 < 0xC0u )
        {
          v33 = 0;
          v34 = 208;
LABEL_41:
          Pool2 = ExAllocatePool2(66, v34, 1766871885);
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
            v52 = _InterlockedDecrement((volatile signed __int32 *)(v33 + 88));
            if ( v52 >= *(_DWORD *)(v33 + 92) && v52 >= 0 )
            {
              Pool2 = (__int64)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v33 + 64));
              goto LABEL_99;
            }
            _InterlockedIncrement((volatile signed __int32 *)(v33 + 88));
          }
LABEL_90:
          v34 = *(unsigned int *)(v33 + 4);
          goto LABEL_41;
        }
        v57 = (struct _NPAGED_LOOKASIDE_LIST *)(v33 + 64);
        if ( *(_BYTE *)(v33 + 9) )
          Pool2 = (__int64)ExAllocateFromNPagedLookasideList(v57);
        else
          Pool2 = (__int64)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v57);
LABEL_99:
        if ( Pool2 )
        {
LABEL_100:
          v54 = Pool2 + 16;
          *(_QWORD *)Pool2 = v33;
          if ( Pool2 == -16 )
            goto LABEL_15;
          memset((void *)(Pool2 + 16), 0, 0xC0u);
          v29 = (char *)(v54 + 32);
          *(_BYTE *)(v54 + 26) = 32;
          if ( v54 != -32 )
          {
            *(_DWORD *)(v54 + 104) |= 3u;
            *(_QWORD *)(v54 + 56) = v54 + 48;
            *(_QWORD *)(v54 + 48) = v54 + 48;
            *(_QWORD *)(v54 + 180) = 0;
          }
          *(_QWORD *)(v54 + 160) = v54;
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
            v36 = (_QWORD *)((char *)a2 + 2560);
            v37 = 96;
            v69 = 8;
            goto LABEL_64;
          }
          v38 = qword_140262420 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
          if ( (unsigned int)v30 > *(_DWORD *)v38 )
          {
            v38 = 0;
            v39 = v30 + 16;
            goto LABEL_49;
          }
          if ( !*(_BYTE *)(v38 + 8) )
          {
            if ( (int)*(_QWORD *)(v38 + 88) > (int)HIDWORD(*(_QWORD *)(v38 + 88)) )
            {
              v51 = _InterlockedDecrement((volatile signed __int32 *)(v38 + 88));
              if ( v51 >= *(_DWORD *)(v38 + 92) && v51 >= 0 )
              {
                v59 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v38 + 64));
                goto LABEL_61;
              }
              _InterlockedIncrement((volatile signed __int32 *)(v38 + 88));
            }
LABEL_85:
            v39 = *(unsigned int *)(v38 + 4);
LABEL_49:
            v40 = ExAllocatePool2(66, v39, 1766871885);
            v36 = (_QWORD *)v40;
            if ( (v40 & 0xF) == 0 )
            {
              if ( !v40 )
              {
LABEL_63:
                v37 = v30;
                v69 = 0;
LABEL_64:
                if ( !v36 )
                {
                  CmsCachedPin::Destroy((struct CmsCachedPin *)v29);
                  goto LABEL_15;
                }
                v46 = (const void *)*((_QWORD *)v29 + 6);
                if ( !v46 )
                  goto LABEL_68;
                memmove(v36, v46, *((unsigned int *)v29 + 14));
                v47 = *((_QWORD *)v29 + 6);
                if ( (*((_DWORD *)v29 + 18) & 8) != 0 )
                {
                  *(_BYTE *)(v47 - 2431) = 0;
                  *((_DWORD *)v29 + 18) &= ~8u;
                }
                else if ( v47 )
                {
                  v49 = (struct _SLIST_ENTRY *)(v47 - 16);
                  v50 = *(_QWORD *)(v47 - 16);
                  v66 = v50;
                  if ( !v50 )
                    goto LABEL_130;
                  if ( *(_BYTE *)(v50 + 8) )
                  {
                    if ( *(_BYTE *)(v50 + 9) )
                      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v50 + 64), v49);
                    else
                      ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)(v50 + 64), v49);
                    goto LABEL_68;
                  }
                  v60 = *(_QWORD *)(v50 + 88);
                  if ( (int)v60 < *(_DWORD *)(v50 + 80) || SHIDWORD(v60) >= (int)v60 )
                  {
                    ExpInterlockedPushEntrySList((PSLIST_HEADER)(v50 + 64), v49);
                    _InterlockedIncrement((volatile signed __int32 *)(v66 + 88));
                  }
                  else
                  {
LABEL_130:
                    ExFreePoolWithTag(v49, 0);
                  }
                }
LABEL_68:
                v48 = *((_DWORD *)v29 + 18) & 0xFFFFFFF7;
                *((_QWORD *)v29 + 6) = v36;
                *((_DWORD *)v29 + 18) = v69 | v48;
                *((_DWORD *)v29 + 14) = v37;
                if ( Src )
                  memmove(v36, Src, v30);
                v28 = (unsigned int *)v64;
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
              *v36 = v38;
              v36 += 2;
              goto LABEL_63;
            }
LABEL_137:
            MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
          }
          v58 = (struct _NPAGED_LOOKASIDE_LIST *)(v38 + 64);
          if ( *(_BYTE *)(v38 + 9) )
            v59 = ExAllocateFromNPagedLookasideList(v58);
          else
            v59 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v58);
LABEL_61:
          v36 = v59;
          if ( v59 )
            goto LABEL_62;
          goto LABEL_85;
        }
        goto LABEL_90;
      }
      v41 = *((_DWORD *)v26 + 14);
      v29 = (char *)v26 - 16;
      v15 = *(CmsPinCache **)v26;
      Srca = v23 + 1;
      v42 = v26;
      v26 = *(CmsPinCache **)v26;
      if ( (v41 & 4) == 0 )
      {
        v43 = *((_QWORD *)v29 + 4);
        if ( *((_DWORD *)v29 + 22) == *(_DWORD *)(v43 + 368)
          && *((_DWORD *)v29 + 23) == *(_DWORD *)(*((_QWORD *)v29 + 5) + 184LL) )
        {
          break;
        }
      }
      CmsPinCache::DoomCachedPin(this, (struct CmsCachedPin *)v29, &v67, (struct _LIST_ENTRY **)v15);
      v23 = Srca;
      v24 = v68;
    }
    if ( v43 == v22 )
      break;
    ++v23;
    v24 = v68;
  }
  if ( *((CmsPinCache **)v15 + 1) != v42 )
    goto LABEL_38;
  v44 = (CmsPinCache **)*((_QWORD *)v42 + 1);
  if ( *v44 != v42 )
    goto LABEL_38;
  *v44 = v15;
  *((_QWORD *)v15 + 1) = v44;
  v45 = *(_QWORD *)v10;
  if ( *(CmsPinCache **)(*(_QWORD *)v10 + 8LL) != v10 )
    goto LABEL_38;
  *(_QWORD *)v42 = v45;
  *((_QWORD *)v42 + 1) = v10;
  *(_QWORD *)(v45 + 8) = v42;
  *(_QWORD *)v10 = v42;
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
  CmsPinCache::DeleteDoomedCachedPins(a2, &v67);
}

```

## disassembly

```asm
0x14002fce0  mov     [rsp+arg_18], r9
0x14002fce5  mov     [rsp+arg_10], r8
0x14002fcea  push    rsi
0x14002fceb  push    rdi
0x14002fcec  push    r12
0x14002fcee  push    r15
0x14002fcf0  sub     rsp, 78h
0x14002fcf4  movzx   eax, byte ptr cs:word_140262177+1
0x14002fcfb  mov     r11, r9
0x14002fcfe  movzx   r9d, cs:byte_140262179
0x14002fd06  mov     rdi, rcx
0x14002fd09  movzx   ecx, [rsp+98h+arg_20]
0x14002fd11  mov     r15, rdi
0x14002fd14  test    cl, cl
0x14002fd16  xorps   xmm0, xmm0
0x14002fd19  mov     rcx, [r8+20h]; this
0x14002fd1d  mov     rsi, rdx
0x14002fd20  cmovz   r9d, eax
0x14002fd24  lea     r12, [rdi+10h]
0x14002fd28  mov     dword ptr [rsp+98h+var_60], r9d
0x14002fd2d  mov     eax, 24h ; '$'
0x14002fd32  mov     r9d, 20h ; ' '
0x14002fd38  cmovnz  r15, r12
0x14002fd3c  cmovnz  r9d, eax
0x14002fd40  mov     rax, 30000000000000h
0x14002fd4a  mov     [rsp+98h+var_58], r9
0x14002fd4f  mov     r9, [rdx]
0x14002fd52  movups  xmmword ptr [rsp+98h+var_50.Flink], xmm0
0x14002fd57  test    rax, r9
0x14002fd5a  jnz     loc_140030476
0x14002fd60  xor     r10b, r10b
0x14002fd63  movzx   r8d, byte ptr [rcx+0Eh]
0x14002fd68  and     r8b, 40h
0x14002fd6c  jnz     loc_14002FE4B
0x14002fd72  mov     rax, [rcx+18h]
0x14002fd76  mov     edx, [rax+2Ch]
0x14002fd79  test    dl, dl
0x14002fd7b  js      loc_14002FE4B
0x14002fd81  xor     eax, eax
0x14002fd83  cmp     eax, 0Dh
0x14002fd86  jnb     loc_14003045B
0x14002fd8c  mov     r8, [rsi+rax*8+1A8h]
0x14002fd94  test    r8, r8
0x14002fd97  jz      loc_14003045B
0x14002fd9d  cmp     r8, rcx
0x14002fda0  jz      loc_1401F18E1
0x14002fda6  inc     eax
0x14002fda8  jmp     short loc_14002FD83
0x14002fdaa  mov     [rdx], rax
0x14002fdad  mov     [rdx+8], r15
0x14002fdb1  mov     [rax+8], rdx
0x14002fdb5  mov     [r15], rdx
0x14002fdb8  test    rbx, rbx
0x14002fdbb  jnz     short loc_14002FDED
0x14002fdbd  lea     rdx, [rsp+98h+var_50]; struct _LIST_ENTRY *
0x14002fdc2  mov     rcx, rsi; struct CmsTransactionContext *
0x14002fdc5  call    ?DeleteDoomedCachedPins@CmsPinCache@@SAXPEAVCmsTransactionContext@@PEAU_LIST_ENTRY@@@Z; CmsPinCache::DeleteDoomedCachedPins(CmsTransactionContext *,_LIST_ENTRY *)
0x14002fdca  mov     rbx, [rsp+98h+arg_0]
0x14002fdd2  mov     rbp, [rsp+98h+var_28]
0x14002fdd7  mov     r13, [rsp+98h+var_30]
0x14002fddc  mov     r14, [rsp+98h+var_38]
0x14002fde1  add     rsp, 78h
0x14002fde5  pop     r15
0x14002fde7  pop     r12
0x14002fde9  pop     rdi
0x14002fdea  pop     rsi
0x14002fdeb  retn
0x14002fded  mov     r11, [rsp+98h+arg_18]
0x14002fdf5  jmp     short loc_14002FE0C
0x14002fdf7  lea     rax, [rbx+10h]
0x14002fdfb  mov     [rax], rcx
0x14002fdfe  mov     [rax+8], r15
0x14002fe02  mov     [rcx+8], rax
0x14002fe06  mov     [r15], rax
0x14002fe09  inc     dword ptr [r14]
0x14002fe0c  mov     rdx, [rsp+98h+arg_30]
0x14002fe14  test    rdx, rdx
0x14002fe17  jz      short loc_14002FDBD
0x14002fe19  mov     rax, [rbx+50h]
0x14002fe1d  mov     [rdx+10h], rax
0x14002fe21  mov     eax, [rbx+68h]
0x14002fe24  shr     eax, 4
0x14002fe27  and     al, 1
0x14002fe29  mov     [rdx+8], al
0x14002fe2c  mov     eax, [r11+18h]
0x14002fe30  mov     [rdx+18h], eax
0x14002fe33  mov     rax, [r11]
0x14002fe36  mov     ecx, [rax+174h]
0x14002fe3c  mov     [rdx+1Ch], ecx
0x14002fe3f  mov     rax, [r11+10h]
0x14002fe43  mov     [rdx], rax
0x14002fe46  jmp     loc_14002FDBD
0x14002fe4b  call    ?HasGlobalBindingSemantics@CmsBPlusTable@@QEBA_NXZ; CmsBPlusTable::HasGlobalBindingSemantics(void)
0x14002fe50  test    al, al
0x14002fe52  jnz     loc_1400304A6
0x14002fe58  mov     [rsp+98h+var_28], rbp
0x14002fe5d  lea     rax, [rsp+98h+var_50]
0x14002fe62  mov     [rsp+98h+var_30], r13
0x14002fe67  lea     rbp, [rsi+338h]
0x14002fe6e  mov     r13, [r11]
0x14002fe71  xor     ecx, ecx
0x14002fe73  mov     [rsp+98h+var_50.Blink], rax
0x14002fe78  lea     rax, [rsp+98h+var_50]
0x14002fe7d  mov     [rsp+98h+var_50.Flink], rax
0x14002fe82  mov     [rsp+98h+var_38], r14
0x14002fe87  cmp     rdi, rbp
0x14002fe8a  jnz     loc_1400303E4
0x14002fe90  movzx   edx, byte ptr cs:word_140262177+1
0x14002fe97  movzx   eax, byte ptr [r13+188h]
0x14002fe9f  mov     [rsp+98h+arg_8], edx
0x14002fea6  test    al, al
0x14002fea8  jnz     loc_140030278
0x14002feae  mov     r14, [rdi]
0x14002feb1  mov     r12, rdi
0x14002feb4  mov     [rsp+98h+arg_0], rbx
0x14002febc  cmp     r14, r12
0x14002febf  jnz     loc_140030162
0x14002fec5  movzx   ebx, byte ptr [rsp+98h+var_60]
0x14002feca  mov     r14, [rsp+98h+var_58]
0x14002fecf  add     r14, rdi
0x14002fed2  mov     [rsp+98h+var_60], r14
0x14002fed7  cmp     [r14], ebx
0x14002feda  jnb     loc_1400303A3
0x14002fee0  cmp     rdi, rbp
0x14002fee3  jnz     loc_14003005C
0x14002fee9  cmp     byte ptr [rsi+87h], 0
0x14002fef0  jnz     loc_14003005C
0x14002fef6  lea     rbx, [rsi+0A60h]
0x14002fefd  test    rbx, rbx
0x14002ff00  jz      short loc_14002FF40
0x14002ff02  xor     r8d, r8d
0x14002ff05  lea     rax, [rbx+10h]
0x14002ff09  mov     [rbx], r8
0x14002ff0c  mov     [rbx+8], r8
0x14002ff10  or      dword ptr [rbx+48h], 3
0x14002ff14  mov     [rbx+30h], r8
0x14002ff18  mov     [rbx+38h], r8
0x14002ff1c  mov     [rbx+40h], r8
0x14002ff20  mov     [rbx+68h], r8d
0x14002ff24  mov     [rbx+88h], r8
0x14002ff2b  mov     [rax+8], rax
0x14002ff2f  mov     [rax], rax
0x14002ff32  mov     [rbx+8], r8
0x14002ff36  mov     [rbx], r8
0x14002ff39  mov     [rbx+94h], r8
0x14002ff40  or      dword ptr [rbx+68h], 8
0x14002ff44  mov     byte ptr [rsi+87h], 1
0x14002ff4b  mov     [rbx+88h], rsi
0x14002ff52  test    rbx, rbx
0x14002ff55  jz      loc_14002FDBD
0x14002ff5b  mov     rax, [rsp+98h+arg_10]
0x14002ff63  mov     [rbx+28h], rax
0x14002ff67  cmp     qword ptr [rbx+30h], 0
0x14002ff6c  jnz     loc_14003054A
0x14002ff72  mov     r12, [rsp+98h+arg_28]
0x14002ff7a  xorps   xmm0, xmm0
0x14002ff7d  movups  xmmword ptr [rbx+30h], xmm0
0x14002ff81  movups  xmmword ptr [rbx+40h], xmm0
0x14002ff85  or      dword ptr [rbx+48h], 3
0x14002ff89  mov     ebp, [r12+8]
0x14002ff8e  test    ebp, ebp
0x14002ff90  jnz     loc_1400300C1
0x14002ff96  mov     eax, [r12+0Ch]
0x14002ff9b  mov     r11, [rsp+98h+arg_18]
0x14002ffa3  mov     [rbx+3Ch], eax
0x14002ffa6  mov     eax, [r12+10h]
0x14002ffab  mov     [rbx+40h], eax
0x14002ffae  movzx   eax, word ptr [r12+14h]
0x14002ffb4  mov     [rbx+44h], ax
0x14002ffb8  movzx   eax, word ptr [r12+16h]
0x14002ffbe  mov     [rbx+46h], ax
0x14002ffc2  mov     eax, [r12+18h]
0x14002ffc7  mov     ecx, eax
0x14002ffc9  xor     ecx, [rbx+48h]
0x14002ffcc  and     ecx, 8
0x14002ffcf  xor     ecx, eax
0x14002ffd1  mov     [rbx+48h], ecx
0x14002ffd4  mov     rax, [r11]
0x14002ffd7  nop
0x14002ffd8  lock inc dword ptr [rax+17Ch]
0x14002ffdf  nop
0x14002ffe0  mov     rax, [r11]
0x14002ffe3  mov     ecx, [rax+170h]
0x14002ffe9  mov     [rbx+58h], ecx
0x14002ffec  mov     rcx, [rsp+98h+arg_10]
0x14002fff4  mov     eax, [rcx+0B8h]
0x14002fffa  mov     [rbx+5Ch], eax
0x14002fffd  mov     rax, [rcx+0A0h]
0x140030004  mov     [rbx+60h], rax
0x140030008  mov     rax, [r11+20h]
0x14003000c  mov     [rbx+70h], rax
0x140030010  mov     rax, [r11+8]
0x140030014  mov     [rbx+78h], rax
0x140030018  mov     rax, [r11]
0x14003001b  or      dword ptr [rbx+68h], 1
0x14003001f  mov     [rbx+20h], rax
0x140030023  movzx   eax, [rsp+98h+arg_20]
0x14003002b  mov     [rbx+90h], al
0x140030031  nop
0x140030032  mov     eax, 1
0x140030037  lock xadd cs:?NextCachedPinId@@3_KA, rax; unsigned __int64 NextCachedPinId
0x140030040  nop
0x140030041  inc     rax
0x140030044  mov     [rbx+50h], rax
0x140030048  mov     rcx, [r15]
0x14003004b  cmp     [rcx+8], r15
0x14003004f  jz      loc_14002FDF7
0x140030055  mov     ecx, 3
0x14003005a  int     29h; Win8: RtlFailFast(ecx)
0x14003005c  xor     ecx, ecx; ProcNumber
0x14003005e  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140030065  nop     dword ptr [rax+rax+00h]
0x14003006a  xor     edx, edx
0x14003006c  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140030072  lea     rbx, [rdx+rdx*2]
0x140030076  shl     rbx, 6
0x14003007a  add     rbx, cs:qword_140262438
0x140030081  cmp     dword ptr [rbx], 0C0h
0x140030087  jnb     loc_140030339
0x14003008d  xor     ebx, ebx
0x14003008f  mov     edx, 0D0h
0x140030094  mov     ecx, 42h ; 'B'
0x140030099  mov     r8d, 6950534Dh
0x14003009f  call    cs:__imp_ExAllocatePool2
0x1400300a6  nop     dword ptr [rax+rax+00h]
0x1400300ab  test    al, 0Fh
0x1400300ad  jnz     loc_1401F1936
0x1400300b3  test    rax, rax
0x1400300b6  jz      loc_14002FDBD
0x1400300bc  jmp     loc_1400303F9
0x1400300c1  cmp     byte ptr [rsi+81h], 0
0x1400300c8  mov     rax, [r12]
0x1400300cc  mov     [rsp+98h+Src], rax
0x1400300d1  jnz     short loc_1400300FC
0x1400300d3  cmp     ebp, 60h ; '`'
0x1400300d6  ja      short loc_1400300FC
0x1400300d8  mov     byte ptr [rsi+81h], 1
0x1400300df  lea     r14, [rsi+0A00h]
0x1400300e6  mov     r13d, 60h ; '`'
0x1400300ec  mov     [rsp+98h+arg_8], 8
0x1400300f7  jmp     loc_14003020A
0x1400300fc  xor     ecx, ecx; ProcNumber
0x1400300fe  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140030105  nop     dword ptr [rax+rax+00h]
0x14003010a  xor     edx, edx
0x14003010c  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140030112  lea     r13, [rdx+rdx*2]
0x140030116  shl     r13, 6
0x14003011a  add     r13, cs:qword_140262420
0x140030121  cmp     ebp, [r13+0]
0x140030125  jbe     loc_1400302F4
0x14003012b  xor     r13d, r13d
0x14003012e  lea     rdx, [rbp+10h]
0x140030132  mov     ecx, 42h ; 'B'
0x140030137  mov     r8d, 6950534Dh
0x14003013d  call    cs:__imp_ExAllocatePool2
0x140030144  nop     dword ptr [rax+rax+00h]
0x140030149  mov     r14, rax
0x14003014c  test    al, 0Fh
0x14003014e  jnz     loc_1401F1936
0x140030154  test    rax, rax
0x140030157  jz      loc_1400301FC
0x14003015d  jmp     loc_1400301F5
0x140030162  cmp     ecx, edx
0x140030164  jnb     loc_14002FEC5
0x14003016a  mov     eax, [r14+38h]
0x14003016e  lea     rbx, [r14-10h]
0x140030172  mov     r9, [r14]; struct _LIST_ENTRY **
0x140030175  inc     ecx
0x140030177  mov     dword ptr [rsp+98h+Src], ecx
0x14003017b  mov     rdx, r14
0x14003017e  mov     r14, r9
0x140030181  test    al, 4
0x140030183  jnz     loc_1400304D8
0x140030189  mov     r8, [rbx+20h]
0x14003018d  mov     eax, [r8+170h]
0x140030194  cmp     [rbx+58h], eax
0x140030197  jnz     loc_1400304D8
0x14003019d  mov     rax, [rbx+28h]
0x1400301a1  mov     ecx, [rax+0B8h]
0x1400301a7  cmp     [rbx+5Ch], ecx
0x1400301aa  jnz     loc_1400304D8
0x1400301b0  cmp     r8, r13
0x1400301b3  jnz     loc_1400304C8
0x1400301b9  cmp     [r9+8], rdx
0x1400301bd  jnz     loc_140030055
0x1400301c3  mov     rax, [rdx+8]
0x1400301c7  cmp     [rax], rdx
0x1400301ca  jnz     loc_140030055
0x1400301d0  mov     [rax], r9
0x1400301d3  mov     [r9+8], rax
0x1400301d7  mov     rax, [r15]
0x1400301da  cmp     [rax+8], r15
0x1400301de  jnz     loc_140030055
0x1400301e4  jmp     loc_14002FDAA
0x1400301e9  mov     r14, rax
0x1400301ec  test    rax, rax
0x1400301ef  jz      loc_140030330
0x1400301f5  mov     [r14], r13
0x1400301f8  add     r14, 10h
  ... truncated ...
```
