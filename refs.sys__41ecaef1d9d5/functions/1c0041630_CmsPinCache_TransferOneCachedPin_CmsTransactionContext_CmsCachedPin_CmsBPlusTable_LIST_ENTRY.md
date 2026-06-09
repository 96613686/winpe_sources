# CmsPinCache::TransferOneCachedPin(CmsTransactionContext *,CmsCachedPin *,CmsBPlusTable *,_LIST_ENTRY *)

- ea: `0x1c0041630`
- end: `0x1c0041d87`
- name: `?TransferOneCachedPin@CmsPinCache@@QEAAEPEAVCmsTransactionContext@@PEAVCmsCachedPin@@PEAVCmsBPlusTable@@PEAU_LIST_ENTRY@@@Z`
- size: `1879`
- prototype: `unsigned __int8(CmsPinCache *__hidden this, struct CmsTransactionContext *, struct CmsCachedPin *, struct CmsBPlusTable *, struct _LIST_ENTRY *)`
- caller_count: `6`
- callee_count: `16`
- tags: `authz_impersonation`

## callers

- `0x1c0010b30`
- `0x1c0011660`
- `0x1c00224d0`
- `0x1c002313c`
- `0x1c0036af0`
- `0x1c0040310`

## callees

- `0x1c0002b40`
- `0x1c001bcb0`
- `0x1c0030ebc`
- `0x1c0030eec`
- `0x1c0031400`
- `0x1c0032e3c`
- `0x1c00363b4`
- `0x1c0041630`
- `0x1c0041d90`
- `0x1c0041e98`
- `0x1c0041ed0`
- `0x1c0042440`
- `0x1c00424b4`
- `0x1c00669fc`
- `0x1c006af80`
- `0x1c00cd0ac`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0041960`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0041d49`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0041960`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0041d49`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00418b9`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0082b94`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00418b9`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0082b94`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0082ae6`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0082ae6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c004191d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c004191d`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1c00418a3`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1c00418a3`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x1c0041773`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x1c0041773`
- `ntoskrnl!ExTryAcquireAutoExpandPushLockExclusive` at `0x1c0041755`
- `ntoskrnl!ExTryAcquireAutoExpandPushLockExclusive` at `0x1c0041755`

## pseudocode

```c
bool __fastcall CmsPinCache::TransferOneCachedPin(
        CmsPinCache *this,
        struct CmsTransactionContext *a2,
        struct CmsCachedPin *a3,
        struct CmsBPlusTable *a4,
        struct _LIST_ENTRY *a5)
{
  int v5; // ebp
  __int64 v6; // rdi
  unsigned int v7; // r12d
  struct CmsCachedPin *v9; // rbx
  CmsCachedPin *v11; // r14
  __int64 v12; // rax
  char v13; // r13
  struct CmsTransactionCore *v15; // rcx
  struct CmsCachedPin *v16; // rdx
  struct _LIST_ENTRY *v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rax
  char *v20; // rcx
  char **v21; // rax
  unsigned int v22; // r10d
  __int64 v23; // rdx
  char **v24; // rax
  unsigned int v25; // r8d
  __int64 *v26; // rdx
  __int64 *v27; // rax
  unsigned __int8 v28; // r8
  __int64 *v29; // r9
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // r14
  SIZE_T v33; // rdx
  _QWORD *PoolWithTag; // r13
  _QWORD *v35; // r13
  unsigned __int8 v36; // r9
  int v37; // edx
  unsigned int v38; // r8d
  __int64 v39; // rcx
  int v40; // eax
  __int64 i; // rdx
  char **v42; // rax
  char *v43; // rdx
  __int64 v44; // rax
  __int64 **v45; // rcx
  __int64 **v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rax
  CmsAvlTableLite *v50; // rcx
  unsigned int v51; // eax
  struct CmsCachedPin *v52; // rdx
  _DWORD *v53; // rax
  struct CmsCachedPin *v54; // rdx
  struct _NPAGED_LOOKASIDE_LIST *v55; // rcx
  _QWORD *v56; // rax
  int v57; // eax
  __int64 *v58; // rcx
  _QWORD *v59; // rax
  __int128 v60; // [rsp+40h] [rbp-78h] BYREF
  __int64 v61; // [rsp+50h] [rbp-68h]
  _DWORD v62[2]; // [rsp+58h] [rbp-60h] BYREF
  __int64 v63; // [rsp+60h] [rbp-58h]
  int v64; // [rsp+68h] [rbp-50h]
  int v65; // [rsp+6Ch] [rbp-4Ch]
  __int64 v66; // [rsp+70h] [rbp-48h]
  __int64 v67; // [rsp+78h] [rbp-40h]
  char v68; // [rsp+C0h] [rbp+8h]
  char v69; // [rsp+D0h] [rbp+18h]

  v5 = 0;
  v6 = *((_QWORD *)a4 + 6) + 80LL;
  v7 = (unsigned __int16)dword_1C0136880;
  v9 = a3;
  v11 = 0;
  if ( (*((_DWORD *)a3 + 22) & 4) != 0
    || *((_DWORD *)a3 + 19) != *(_DWORD *)(*((_QWORD *)a3 + 4) + 304LL)
    || *((_DWORD *)a3 + 20) != *(_DWORD *)(*((_QWORD *)a3 + 5) + 120LL) )
  {
    return 0;
  }
  v12 = *((_QWORD *)a3 + 4);
  if ( *(_QWORD *)(v12 + 520) )
  {
    v13 = 0;
    if ( (*(_QWORD *)(v12 + 408) & 0x800000LL) == 0 )
      return 0;
    CmsBPlusTable::LockCachedPinList(a4);
    v16 = *(struct CmsCachedPin **)(*((_QWORD *)v9 + 4) + 520LL);
    if ( v16 && CmsPinCache::ShouldDoomCachedPin(v15, v16) )
    {
      CmsPinCache::DoomCachedPin((CmsPinCache *)v6, *(struct CmsCachedPin **)(*((_QWORD *)v9 + 4) + 520LL), v17, 0, 0);
    }
    else
    {
      v54 = *(struct CmsCachedPin **)(*((_QWORD *)v9 + 4) + 520LL);
      if ( v54 )
      {
        v13 = 1;
        CmsPinCache::PromoteCachedPin((CmsPinCache *)v6, v54, v7);
      }
    }
    CmsBPlusTable::UnlockCachedPinList(a4);
    if ( v13 )
      return 0;
  }
  if ( (*((_DWORD *)v9 + 22) & 0x10) == 0 )
    goto LABEL_12;
  if ( (struct CmsTransactionContext *)v6 != (struct CmsTransactionContext *)((char *)a2 + 1584) )
  {
    v68 = 0;
    goto LABEL_44;
  }
  v36 = 1;
  v68 = 1;
  if ( *((_BYTE *)a2 + 1787) )
  {
LABEL_44:
    v32 = qword_1C0136F48 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
    if ( *(_DWORD *)v32 < 0xA8u )
    {
      v32 = 0;
      v33 = 176;
      goto LABEL_46;
    }
    if ( *(_BYTE *)(v32 + 8) )
    {
      v55 = (struct _NPAGED_LOOKASIDE_LIST *)(v32 + 64);
      if ( *(_BYTE *)(v32 + 9) )
        v56 = ExAllocateFromNPagedLookasideList(v55);
      else
        v56 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v55);
LABEL_103:
      PoolWithTag = v56;
      if ( v56 )
      {
LABEL_47:
        *PoolWithTag = v32;
        v35 = PoolWithTag + 1;
        if ( v35 )
        {
          memset(v35, 0, 0xA8u);
          v11 = (CmsCachedPin *)(v35 + 4);
          *((_BYTE *)v35 + 26) = 32;
          if ( v35 == (_QWORD *)-32LL )
          {
            v11 = 0;
          }
          else
          {
            *((_OWORD *)v35 + 5) = 0;
            v35[12] = 0;
            *((_DWORD *)v35 + 25) |= 3u;
            *((_DWORD *)v35 + 30) = 0;
            v35[19] = 0;
          }
          v36 = v68;
          *((_QWORD *)v11 + 14) = v35;
          goto LABEL_51;
        }
        return 0;
      }
      goto LABEL_106;
    }
    if ( *(_DWORD *)(v32 + 80) > *(_DWORD *)(v32 + 88) )
    {
      v57 = _InterlockedDecrement((volatile signed __int32 *)(v32 + 80));
      if ( v57 >= *(_DWORD *)(v32 + 88) && v57 >= 0 )
      {
        v56 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v32 + 64));
        goto LABEL_103;
      }
      _InterlockedIncrement((volatile signed __int32 *)(v32 + 80));
    }
LABEL_106:
    v33 = *(unsigned int *)(v32 + 4);
LABEL_46:
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, v33, 0x6950534Du);
    if ( !PoolWithTag )
      return 0;
    goto LABEL_47;
  }
  if ( a2 != (struct CmsTransactionContext *)-1792LL )
  {
    v11 = CmsCachedPin::CmsCachedPin((struct CmsTransactionContext *)((char *)a2 + 1792));
    v36 = 1;
  }
  *((_DWORD *)v11 + 22) |= 0x10u;
  *((_BYTE *)a2 + 1787) = 1;
  *((_QWORD *)v11 + 15) = a2;
LABEL_51:
  if ( !v11 )
    return 0;
  v37 = *((_DWORD *)v11 + 22) >> 4;
  v69 = v37;
  if ( *((_QWORD *)v11 + 6) )
  {
    CmsKeyRange::FreeKeysBuffer((CmsCachedPin *)((char *)v11 + 48));
    LOBYTE(v37) = v69;
    v36 = v68;
  }
  *((_OWORD *)v11 + 3) = 0;
  *((_QWORD *)v11 + 8) = 0;
  *((_DWORD *)v11 + 17) |= 3u;
  v38 = *((_DWORD *)v9 + 14);
  if ( !v38 )
    goto LABEL_55;
  if ( (int)CmsKeyRange::ReallocateKeysBuffer((CmsCachedPin *)((char *)v11 + 48), a2, v38, *((void **)v9 + 6), 0) < 0 )
  {
    CmsCachedPin::Destroy(v11);
    return 0;
  }
  LOBYTE(v37) = v69;
  v36 = v68;
LABEL_55:
  *((_DWORD *)v11 + 15) = *((_DWORD *)v9 + 15);
  *((_DWORD *)v11 + 16) = *((_DWORD *)v9 + 16);
  *((_DWORD *)v11 + 17) = *((_DWORD *)v9 + 17) ^ (*((_DWORD *)v11 + 17) ^ *((_DWORD *)v9 + 17)) & 8;
  v39 = *((_QWORD *)v9 + 4);
  *((_QWORD *)v11 + 4) = v39;
  *((_QWORD *)v11 + 5) = *((_QWORD *)v9 + 5);
  *((_DWORD *)v11 + 18) = *((_DWORD *)v9 + 18);
  *((_DWORD *)v11 + 19) = *((_DWORD *)v9 + 19);
  *((_DWORD *)v11 + 20) = *((_DWORD *)v9 + 20);
  *((_DWORD *)v11 + 21) = *((_DWORD *)v9 + 21);
  *((_QWORD *)v11 + 12) = *((_QWORD *)v9 + 12);
  *((_QWORD *)v11 + 13) = *((_QWORD *)v9 + 13);
  *((_BYTE *)v11 + 128) = *((_BYTE *)v9 + 128);
  *((_DWORD *)v11 + 33) = *((_DWORD *)a2 + 1234);
  _InterlockedIncrement((volatile signed __int32 *)(v39 + 324));
  if ( v36 )
  {
    v58 = *(__int64 **)v6;
    v59 = (_QWORD *)((char *)v11 + 16);
    if ( *(_QWORD *)(*(_QWORD *)v6 + 8LL) != v6 )
      goto LABEL_113;
    *v59 = v58;
    *((_QWORD *)v11 + 3) = v6;
    v58[1] = (__int64)v59;
    *(_QWORD *)v6 = v59;
    ++*(_DWORD *)(v6 + 16);
  }
  v40 = *((_DWORD *)v9 + 22);
  v9 = v11;
  *((_DWORD *)v11 + 22) = (16 * (v37 & 1)) | v40 & 0xFFFFFFC3 | (4 * v36) & 0xFFC7;
LABEL_12:
  if ( (*((_DWORD *)v9 + 17) & 8) != 0
    && (int)CmsKeyRange::ReallocateKeysBuffer((struct CmsCachedPin *)((char *)v9 + 48), 0, *((_DWORD *)v9 + 14), 0, 1u) < 0 )
  {
    goto LABEL_39;
  }
  v18 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a4 + 4) + 48LL) + 8LL);
  if ( !v18 || !(unsigned __int8)ExTryAcquireAutoExpandPushLockExclusive(v18, 0) )
    goto LABEL_39;
  if ( !(unsigned __int8)ExTryAcquirePushLockExclusiveEx(*(_QWORD *)(*((_QWORD *)a4 + 4) + 48LL), 0) )
  {
    CmsBPlusTable::UnlockCachedPinList(a4);
    goto LABEL_39;
  }
  if ( *((_DWORD *)v9 + 19) != *(_DWORD *)(*((_QWORD *)v9 + 4) + 304LL)
    || *((_DWORD *)v9 + 20) != *(_DWORD *)(*((_QWORD *)v9 + 5) + 120LL)
    || (v19 = *((_QWORD *)v9 + 4), *(_QWORD *)(v19 + 520)) )
  {
    CmsBPlusTable::UnlockCachedPinList(a4);
    ExReleasePushLockEx(*(_QWORD *)(*((_QWORD *)a4 + 4) + 48LL), 0);
LABEL_39:
    if ( v11 )
    {
      CmsCachedPin::Unpin(v11, a2);
      CmsCachedPin::Destroy(v11);
    }
    return 0;
  }
  *(_QWORD *)(v19 + 520) = v9;
  v20 = (char *)v9 + 16;
  v21 = *(char ***)(v6 + 8);
  if ( *v21 != (char *)v6 )
    goto LABEL_113;
  *(_QWORD *)v20 = v6;
  v22 = 0;
  *((_QWORD *)v9 + 3) = v21;
  *v21 = v20;
  *(_QWORD *)(v6 + 8) = v20;
  ++*(_DWORD *)(v6 + 16);
  v23 = *(_QWORD *)v20;
  if ( *(char **)(*(_QWORD *)v20 + 8LL) != v20 )
    goto LABEL_113;
  v24 = (char **)*((_QWORD *)v9 + 3);
  if ( *v24 != v20 )
    goto LABEL_113;
  *v24 = (char *)v23;
  v25 = 0;
  *(_QWORD *)(v23 + 8) = v24;
  v26 = *(__int64 **)v6;
  v27 = *(__int64 **)v6;
  do
  {
    if ( v27 == (__int64 *)v6 )
      break;
    if ( *((_BYTE *)v27 + 112) )
      break;
    v27 = (__int64 *)*v27;
    ++v22;
    ++v25;
  }
  while ( v25 < 3 );
  v28 = *((_BYTE *)v9 + 128);
  v29 = (__int64 *)v27[1];
  if ( v28 )
  {
    for ( i = *v29; i != v6; i = *(_QWORD *)i )
    {
      v51 = v22++;
      if ( v51 >= v7 )
        break;
      if ( *(_BYTE *)(i + 112) < v28 )
        break;
    }
    v42 = *(char ***)(i + 8);
    v43 = *v42;
    if ( *((char ***)*v42 + 1) != v42 )
      goto LABEL_113;
    *(_QWORD *)v20 = v43;
    *((_QWORD *)v9 + 3) = v42;
    *((_QWORD *)v43 + 1) = v20;
    *v42 = v20;
  }
  else
  {
    if ( v26[1] != v6 )
      goto LABEL_113;
    *(_QWORD *)v20 = v26;
    *((_QWORD *)v9 + 3) = v6;
    v26[1] = (__int64)v20;
    *(_QWORD *)v6 = v20;
    if ( v29 != (__int64 *)v6 && v22 == 3 )
    {
      v44 = *v29;
      if ( *(__int64 **)(*v29 + 8) == v29 )
      {
        v45 = (__int64 **)v29[1];
        if ( *v45 == v29 )
        {
          *v45 = (__int64 *)v44;
          *(_QWORD *)(v44 + 8) = v45;
          v46 = *(__int64 ***)(v6 + 8);
          if ( *v46 == (__int64 *)v6 )
          {
            *v29 = v6;
            v29[1] = (__int64)v46;
            *v46 = v29;
            *(_QWORD *)(v6 + 8) = v29;
            goto LABEL_27;
          }
        }
      }
LABEL_113:
      __fastfail(3u);
    }
  }
LABEL_27:
  if ( !*((_BYTE *)v9 + 128) )
  {
    if ( (_BYTE)word_1C0136885 )
    {
      if ( *(_DWORD *)(v6 + 16) >= 0xFu )
      {
        v47 = *((_QWORD *)v9 + 5);
        if ( (*(_DWORD *)(*(_QWORD *)(v47 + 24) + 44LL) & 2) != 0 && (*(_DWORD *)(v47 + 16) & 0x20000) == 0 )
        {
          if ( *(_QWORD *)(v6 + 24) )
            goto LABEL_117;
          v53 = ExAllocatePoolWithTag((POOL_TYPE)512, 0x30u, 0x6950534Du);
          if ( v53 )
          {
            v53[10] = 0;
            *((_QWORD *)v53 + 1) = 0;
            *((_QWORD *)v53 + 2) = 0;
            *((_QWORD *)v53 + 3) = 0;
            *((_QWORD *)v53 + 4) = 0;
            *(_QWORD *)v53 = v53;
          }
          else
          {
            v53 = 0;
          }
          *(_QWORD *)(v6 + 24) = v53;
          if ( v53 )
          {
LABEL_117:
            if ( CmsKeyRange::GetInnerRange((struct CmsCachedPin *)((char *)v9 + 48), v9) )
            {
              v48 = *((_QWORD *)v9 + 14);
              v62[1] = 0;
              v61 = 0;
              v65 = 0;
              *(_OWORD *)v48 = 0;
              *(_OWORD *)(v48 + 16) = 0;
              *(_WORD *)(v48 + 30) = 136;
              *(_WORD *)(v48 + 26) = 4128;
              v67 = v48;
              v62[0] = *(unsigned __int8 *)(v48 + 27);
              v63 = v48 + *(unsigned __int8 *)(v48 + 26);
              v64 = *(unsigned __int16 *)(v48 + 30);
              v49 = v48 + *(unsigned __int8 *)(v48 + 26);
              v50 = *(CmsAvlTableLite **)(v6 + 24);
              v66 = v49;
              v60 = 0;
              if ( (unsigned int)CmsAvlTableLite::AddToIndexEx(
                                   v50,
                                   a2,
                                   (struct _SmsPropertyDef *)&dword_1C0137008,
                                   (struct _CmsRow *)v62,
                                   (struct _SmsQuickIndex *)&v60,
                                   (struct _SmsPreAllocatedRow *)v62,
                                   0) )
              {
                if ( (_QWORD)v60 )
                  v52 = (struct CmsCachedPin *)(v60 + *(unsigned __int8 *)(v60 + 26));
                else
                  v52 = 0;
                CmsPinCache::DoomCachedPin((CmsPinCache *)v6, v52, a5, 0, 1);
                if ( !(unsigned int)CmsAvlTableLite::AddToIndexEx(
                                      *(CmsAvlTableLite **)(v6 + 24),
                                      a2,
                                      (struct _SmsPropertyDef *)&dword_1C0137008,
                                      (struct _CmsRow *)v62,
                                      0,
                                      (struct _SmsPreAllocatedRow *)v62,
                                      0) )
                  v5 = 8;
                *((_DWORD *)v9 + 22) = v5 | *((_DWORD *)v9 + 22) & 0xFFFFFFF7;
              }
              else
              {
                *((_DWORD *)v9 + 22) |= 8u;
              }
            }
          }
        }
      }
    }
  }
  if ( (*(_QWORD *)(*((_QWORD *)v9 + 4) + 408LL) & 0x800000LL) != 0 )
    _InterlockedAnd64((volatile signed __int64 *)(*((_QWORD *)v9 + 4) + 408LL), 0xFFFFFFFFFF7FFFFFuLL);
  _InterlockedIncrement(&CmsCachedPin::GlobalCachedPinCount);
  *((_DWORD *)v9 + 22) |= 0x20u;
  v30 = *((_QWORD *)a4 + 4);
  v31 = *(_QWORD *)(v30 + 48);
  if ( *(_QWORD *)(v31 + 8) )
  {
    ExReleaseAutoExpandPushLockExclusive(*(_QWORD *)(v31 + 8), 0);
    v30 = *((_QWORD *)a4 + 4);
  }
  ExReleasePushLockEx(*(_QWORD *)(v30 + 48), 0);
  return !v11;
}

```

## disassembly

```asm
0x1c0041630  mov     [rsp+arg_8], rbx
0x1c0041635  mov     [rsp+arg_0], rcx
0x1c004163a  push    rbp
0x1c004163b  push    rsi
0x1c004163c  push    rdi
0x1c004163d  push    r12
0x1c004163f  push    r13
0x1c0041641  push    r14
0x1c0041643  push    r15
0x1c0041645  sub     rsp, 80h
0x1c004164c  mov     rdi, [r9+30h]
0x1c0041650  xor     ebp, ebp
0x1c0041652  mov     eax, [r8+58h]
0x1c0041656  add     rdi, 50h ; 'P'
0x1c004165a  movzx   r12d, word ptr cs:dword_1C0136880
0x1c0041662  mov     rsi, r9
0x1c0041665  mov     rbx, r8
0x1c0041668  mov     r15, rdx
0x1c004166b  mov     r14d, ebp
0x1c004166e  test    al, 4
0x1c0041670  jnz     short loc_1C00416B1
0x1c0041672  mov     rax, [r8+20h]
0x1c0041676  mov     ecx, [rax+130h]
0x1c004167c  cmp     [r8+4Ch], ecx
0x1c0041680  jnz     short loc_1C00416B1
0x1c0041682  mov     rax, [r8+28h]
0x1c0041686  mov     ecx, [rax+78h]
0x1c0041689  cmp     [r8+50h], ecx
0x1c004168d  jnz     short loc_1C00416B1
0x1c004168f  mov     rax, [r8+20h]
0x1c0041693  cmp     [rax+208h], rbp
0x1c004169a  jz      loc_1C0041728
0x1c00416a0  mov     rax, [rax+198h]
0x1c00416a7  xor     r13b, r13b
0x1c00416aa  bt      rax, 17h
0x1c00416af  jb      short loc_1C00416CF
0x1c00416b1  xor     al, al
0x1c00416b3  mov     rbx, [rsp+0B8h+arg_8]
0x1c00416bb  add     rsp, 80h
0x1c00416c2  pop     r15
0x1c00416c4  pop     r14
0x1c00416c6  pop     r13
0x1c00416c8  pop     r12
0x1c00416ca  pop     rdi
0x1c00416cb  pop     rsi
0x1c00416cc  pop     rbp
0x1c00416cd  retn
0x1c00416cf  mov     rcx, rsi; this
0x1c00416d2  call    ?LockCachedPinList@CmsBPlusTable@@QEAAXXZ; CmsBPlusTable::LockCachedPinList(void)
0x1c00416d7  mov     rax, [rbx+20h]
0x1c00416db  mov     r8, [rsp+0B8h+arg_20]
0x1c00416e3  mov     rdx, [rax+208h]; struct CmsCachedPin *
0x1c00416ea  test    rdx, rdx
0x1c00416ed  jz      loc_1C0082A36
0x1c00416f3  call    ?ShouldDoomCachedPin@CmsPinCache@@SAEPEAVCmsTransactionCore@@PEAVCmsCachedPin@@@Z; CmsPinCache::ShouldDoomCachedPin(CmsTransactionCore *,CmsCachedPin *)
0x1c00416f8  test    al, al
0x1c00416fa  jz      loc_1C0082A36
0x1c0041700  mov     rdx, [rbx+20h]
0x1c0041704  xor     r9d, r9d; struct _LIST_ENTRY **
0x1c0041707  mov     rcx, rdi; this
0x1c004170a  mov     byte ptr [rsp+0B8h+var_98], bpl; char
0x1c004170f  mov     rdx, [rdx+208h]; struct CmsCachedPin *
0x1c0041716  call    ?DoomCachedPin@CmsPinCache@@QEAAXPEAVCmsCachedPin@@PEAU_LIST_ENTRY@@PEAPEAU3@E@Z; CmsPinCache::DoomCachedPin(CmsCachedPin *,_LIST_ENTRY *,_LIST_ENTRY * *,uchar)
0x1c004171b  mov     rcx, rsi; this
0x1c004171e  call    ?UnlockCachedPinList@CmsBPlusTable@@QEAAXXZ; CmsBPlusTable::UnlockCachedPinList(void)
0x1c0041723  test    r13b, r13b
0x1c0041726  jnz     short loc_1C00416B1
0x1c0041728  mov     eax, [rbx+58h]
0x1c004172b  test    al, 10h
0x1c004172d  jnz     loc_1C0041903
0x1c0041733  mov     eax, [rbx+44h]
0x1c0041736  test    al, 8
0x1c0041738  jnz     loc_1C0041B6D
0x1c004173e  mov     rax, [rsi+20h]
0x1c0041742  mov     rcx, [rax+30h]
0x1c0041746  mov     rcx, [rcx+8]
0x1c004174a  test    rcx, rcx
0x1c004174d  jz      loc_1C00418F3
0x1c0041753  xor     edx, edx
0x1c0041755  call    cs:__imp_ExTryAcquireAutoExpandPushLockExclusive
0x1c004175c  nop     dword ptr [rax+rax+00h]
0x1c0041761  test    al, al
0x1c0041763  jz      loc_1C00418F3
0x1c0041769  mov     rcx, [rsi+20h]
0x1c004176d  xor     edx, edx
0x1c004176f  mov     rcx, [rcx+30h]
0x1c0041773  call    cs:__imp_ExTryAcquirePushLockExclusiveEx
0x1c004177a  nop     dword ptr [rax+rax+00h]
0x1c004177f  test    al, al
0x1c0041781  jz      loc_1C0082B65
0x1c0041787  mov     rax, [rbx+20h]
0x1c004178b  mov     ecx, [rax+130h]
0x1c0041791  cmp     [rbx+4Ch], ecx
0x1c0041794  jnz     loc_1C0082B82
0x1c004179a  mov     rax, [rbx+28h]
0x1c004179e  mov     ecx, [rax+78h]
0x1c00417a1  cmp     [rbx+50h], ecx
0x1c00417a4  jnz     loc_1C0082B82
0x1c00417aa  mov     rax, [rbx+20h]
0x1c00417ae  cmp     [rax+208h], rbp
0x1c00417b5  jnz     loc_1C0082B82
0x1c00417bb  mov     [rax+208h], rbx
0x1c00417c2  lea     rcx, [rbx+10h]
0x1c00417c6  mov     rax, [rdi+8]
0x1c00417ca  cmp     [rax], rdi
0x1c00417cd  jnz     loc_1C0082B7B
0x1c00417d3  mov     [rcx], rdi
0x1c00417d6  mov     r10d, ebp
0x1c00417d9  mov     [rcx+8], rax
0x1c00417dd  mov     [rax], rcx
0x1c00417e0  mov     [rdi+8], rcx
0x1c00417e4  inc     dword ptr [rdi+10h]
0x1c00417e7  mov     rdx, [rcx]
0x1c00417ea  cmp     [rdx+8], rcx
0x1c00417ee  jnz     loc_1C0082B7B
0x1c00417f4  mov     rax, [rcx+8]
0x1c00417f8  cmp     [rax], rcx
0x1c00417fb  jnz     loc_1C0082B7B
0x1c0041801  mov     [rax], rdx
0x1c0041804  mov     r8d, ebp
0x1c0041807  mov     [rdx+8], rax
0x1c004180b  mov     rdx, [rdi]
0x1c004180e  mov     rax, rdx
0x1c0041811  cmp     rax, rdi
0x1c0041814  jnz     loc_1C00418D1
0x1c004181a  movzx   r8d, byte ptr [rbx+80h]
0x1c0041822  mov     r9, [rax+8]
0x1c0041826  test    r8b, r8b
0x1c0041829  jnz     loc_1C0041AC1
0x1c004182f  cmp     [rdx+8], rdi
0x1c0041833  jnz     loc_1C0082B7B
0x1c0041839  mov     [rcx], rdx
0x1c004183c  mov     [rcx+8], rdi
0x1c0041840  mov     [rdx+8], rcx
0x1c0041844  mov     [rdi], rcx
0x1c0041847  cmp     r9, rdi
0x1c004184a  jnz     loc_1C0041AF1
0x1c0041850  cmp     [rbx+80h], bpl
0x1c0041857  jnz     short loc_1C004186C
0x1c0041859  cmp     byte ptr cs:word_1C0136885, bpl
0x1c0041860  jz      short loc_1C004186C
0x1c0041862  cmp     dword ptr [rdi+10h], 0Fh
0x1c0041866  jnb     loc_1C0041B91
0x1c004186c  mov     rax, [rbx+20h]
0x1c0041870  mov     rcx, [rax+198h]
0x1c0041877  bt      rcx, 17h
0x1c004187c  jb      loc_1C0041C84
0x1c0041882  lock inc cs:?GlobalCachedPinCount@CmsCachedPin@@2JA; long CmsCachedPin::GlobalCachedPinCount
0x1c0041889  or      dword ptr [rbx+58h], 20h
0x1c004188d  mov     rcx, [rsi+20h]
0x1c0041891  mov     rax, [rcx+30h]
0x1c0041895  mov     r8, [rax+8]
0x1c0041899  test    r8, r8
0x1c004189c  jz      short loc_1C00418B3
0x1c004189e  xor     edx, edx
0x1c00418a0  mov     rcx, r8
0x1c00418a3  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x1c00418aa  nop     dword ptr [rax+rax+00h]
0x1c00418af  mov     rcx, [rsi+20h]
0x1c00418b3  mov     rcx, [rcx+30h]
0x1c00418b7  xor     edx, edx
0x1c00418b9  call    cs:__imp_ExReleasePushLockEx
0x1c00418c0  nop     dword ptr [rax+rax+00h]
0x1c00418c5  test    r14, r14
0x1c00418c8  jnz     short loc_1C00418FC
0x1c00418ca  mov     al, 1
0x1c00418cc  jmp     loc_1C00416B3
0x1c00418d1  cmp     [rax+70h], bpl
0x1c00418d5  ja      loc_1C004181A
0x1c00418db  mov     rax, [rax]
0x1c00418de  inc     r10d
0x1c00418e1  inc     r8d
0x1c00418e4  cmp     r8d, 3
0x1c00418e8  jb      loc_1C0041811
0x1c00418ee  jmp     loc_1C004181A
0x1c00418f3  test    r14, r14
0x1c00418f6  jnz     loc_1C0041C6C
0x1c00418fc  xor     eax, eax
0x1c00418fe  jmp     loc_1C00416B3
0x1c0041903  lea     rax, [r15+630h]
0x1c004190a  cmp     rdi, rax
0x1c004190d  jz      loc_1C0082A5E
0x1c0041913  mov     byte ptr [rsp+0B8h+arg_0], bpl
0x1c004191b  xor     ecx, ecx; ProcNumber
0x1c004191d  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1c0041924  nop     dword ptr [rax+rax+00h]
0x1c0041929  xor     edx, edx
0x1c004192b  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x1c0041931  lea     r14, [rdx+rdx*2]
0x1c0041935  shl     r14, 6
0x1c0041939  add     r14, cs:qword_1C0136F48
0x1c0041940  cmp     dword ptr [r14], 0A8h
0x1c0041947  jnb     loc_1C0082AA3
0x1c004194d  mov     r14, rbp
0x1c0041950  mov     edx, 0B0h; NumberOfBytes
0x1c0041955  mov     ecx, 200h; PoolType
0x1c004195a  mov     r8d, 6950534Dh; Tag
0x1c0041960  call    cs:__imp_ExAllocatePoolWithTag
0x1c0041967  nop     dword ptr [rax+rax+00h]
0x1c004196c  mov     r13, rax
0x1c004196f  test    rax, rax
0x1c0041972  jz      loc_1C00416B1
0x1c0041978  mov     [r13+0], r14
0x1c004197c  add     r13, 8
0x1c0041980  jz      loc_1C00416B1
0x1c0041986  xor     edx, edx; Val
0x1c0041988  mov     r8d, 0A8h; Size
0x1c004198e  mov     rcx, r13; void *
0x1c0041991  call    memset
0x1c0041996  lea     r14, [r13+20h]
0x1c004199a  mov     byte ptr [r13+1Ah], 20h ; ' '
0x1c004199f  test    r14, r14
0x1c00419a2  jz      loc_1C0082B0E
0x1c00419a8  xor     eax, eax
0x1c00419aa  xorps   xmm0, xmm0
0x1c00419ad  movups  xmmword ptr [r14+30h], xmm0
0x1c00419b2  mov     [r14+40h], rax
0x1c00419b6  or      dword ptr [r14+44h], 3
0x1c00419bb  mov     [r14+58h], ebp
0x1c00419bf  mov     [r14+78h], rbp
0x1c00419c3  movzx   r9d, byte ptr [rsp+0B8h+arg_0]
0x1c00419cc  mov     [r14+70h], r13
0x1c00419d0  test    r14, r14
0x1c00419d3  jz      loc_1C00416B1
0x1c00419d9  mov     edx, [r14+58h]
0x1c00419dd  shr     edx, 4
0x1c00419e0  mov     [rsp+0B8h+arg_10], edx
0x1c00419e7  cmp     [r14+30h], rbp
0x1c00419eb  jnz     loc_1C0082B16
0x1c00419f1  xor     eax, eax
0x1c00419f3  xorps   xmm0, xmm0
0x1c00419f6  movups  xmmword ptr [r14+30h], xmm0
0x1c00419fb  mov     [r14+40h], rax
0x1c00419ff  or      dword ptr [r14+44h], 3
0x1c0041a04  mov     r8d, [rbx+38h]; unsigned int
0x1c0041a08  test    r8d, r8d
0x1c0041a0b  jnz     loc_1C0041B3C
0x1c0041a11  mov     eax, [rbx+3Ch]
0x1c0041a14  mov     [r14+3Ch], eax
0x1c0041a18  mov     eax, [rbx+40h]
0x1c0041a1b  mov     [r14+40h], eax
0x1c0041a1f  mov     ecx, [rbx+44h]
0x1c0041a22  xor     ecx, [r14+44h]
0x1c0041a26  and     ecx, 8
0x1c0041a29  xor     ecx, [rbx+44h]
0x1c0041a2c  mov     [r14+44h], ecx
0x1c0041a30  mov     rcx, [rbx+20h]
0x1c0041a34  mov     [r14+20h], rcx
0x1c0041a38  mov     rax, [rbx+28h]
0x1c0041a3c  mov     [r14+28h], rax
0x1c0041a40  mov     eax, [rbx+48h]
0x1c0041a43  mov     [r14+48h], eax
0x1c0041a47  mov     eax, [rbx+4Ch]
0x1c0041a4a  mov     [r14+4Ch], eax
0x1c0041a4e  mov     eax, [rbx+50h]
0x1c0041a51  mov     [r14+50h], eax
0x1c0041a55  mov     eax, [rbx+54h]
0x1c0041a58  mov     [r14+54h], eax
0x1c0041a5c  mov     rax, [rbx+60h]
0x1c0041a60  mov     [r14+60h], rax
0x1c0041a64  mov     rax, [rbx+68h]
0x1c0041a68  mov     [r14+68h], rax
0x1c0041a6c  movzx   eax, byte ptr [rbx+80h]
0x1c0041a73  mov     [r14+80h], al
0x1c0041a7a  mov     eax, [r15+1348h]
0x1c0041a81  mov     [r14+84h], eax
0x1c0041a88  lock inc dword ptr [rcx+144h]
0x1c0041a8f  test    r9b, r9b
0x1c0041a92  jnz     loc_1C0082B42
0x1c0041a98  mov     eax, [rbx+58h]
0x1c0041a9b  mov     rbx, r14
0x1c0041a9e  and     eax, 0FFFFFFFBh
0x1c0041aa1  movzx   ecx, r9b
0x1c0041aa5  shl     ecx, 2
0x1c0041aa8  or      ecx, eax
0x1c0041aaa  movzx   eax, dl
0x1c0041aad  and     eax, 1
0x1c0041ab0  and     ecx, 0FFFFFFC7h
0x1c0041ab3  shl     eax, 4
0x1c0041ab6  or      ecx, eax
0x1c0041ab8  mov     [r14+58h], ecx
0x1c0041abc  jmp     loc_1C0041733
0x1c0041ac1  mov     rdx, [r9]
0x1c0041ac4  cmp     rdx, rdi
0x1c0041ac7  jnz     loc_1C0041CA0
0x1c0041acd  mov     rax, [rdx+8]
0x1c0041ad1  mov     rdx, [rax]
0x1c0041ad4  cmp     [rdx+8], rax
0x1c0041ad8  jnz     loc_1C0082B7B
0x1c0041ade  mov     [rcx], rdx
0x1c0041ae1  mov     [rcx+8], rax
0x1c0041ae5  mov     [rdx+8], rcx
0x1c0041ae9  mov     [rax], rcx
0x1c0041aec  jmp     loc_1C0041850
0x1c0041af1  cmp     r10d, 3
0x1c0041af5  jnz     loc_1C0041850
0x1c0041afb  mov     rax, [r9]
0x1c0041afe  cmp     [rax+8], r9
0x1c0041b02  jnz     loc_1C0082B7B
0x1c0041b08  mov     rcx, [r9+8]
  ... truncated ...
```
