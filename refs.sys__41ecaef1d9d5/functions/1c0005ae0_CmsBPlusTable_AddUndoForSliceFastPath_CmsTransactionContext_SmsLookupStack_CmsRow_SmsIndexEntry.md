# CmsBPlusTable::AddUndoForSliceFastPath(CmsTransactionContext *,_SmsLookupStack *,_CmsRow *,_SmsIndexEntry * *)

- ea: `0x1c0005ae0`
- end: `0x1c0006106`
- name: `?AddUndoForSliceFastPath@CmsBPlusTable@@IEAAJPEAVCmsTransactionContext@@PEAU_SmsLookupStack@@PEAU_CmsRow@@PEAPEAU_SmsIndexEntry@@@Z`
- size: `1574`
- prototype: `int(CmsBPlusTable *__hidden this, struct CmsTransactionContext *, struct _SmsLookupStack *, struct _CmsRow *, struct _SmsIndexEntry **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1c00071d0`

## callees

- `0x1c0002b40`
- `0x1c0005ae0`
- `0x1c0019730`
- `0x1c001afd4`
- `0x1c001bc80`
- `0x1c0036a10`
- `0x1c0068960`
- `0x1c006ac80`
- `0x1c006acc0`
- `0x1c006af80`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c006e877`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c006e936`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c006e877`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c006e936`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c0005ed4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c0005fec`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c0005ed4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c0005fec`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0005ca1`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0005dd3`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c006e845`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c006e907`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0005ca1`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0005dd3`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c006e845`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c006e907`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c0005c2f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c0005d66`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c0005c2f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c0005d66`

## pseudocode

```c
__int64 __fastcall CmsBPlusTable::AddUndoForSliceFastPath(
        CmsBPlusTable *this,
        struct CmsTransactionContext *a2,
        struct _SmsLookupStack *a3,
        struct _CmsRow *a4,
        struct _SmsIndexEntry **a5)
{
  _QWORD *v5; // rsi
  unsigned int v7; // r8d
  unsigned int v8; // edi
  struct _CmsRow *v9; // r10
  struct CmsTransactionContext *v10; // r14
  CmsBPlusTable *v11; // r13
  unsigned int v12; // eax
  bool v13; // al
  struct _CmsData *v14; // rdx
  unsigned int v15; // eax
  bool v16; // al
  struct _CmsData *v17; // rdx
  unsigned int v18; // eax
  unsigned int v19; // ebp
  _QWORD *v20; // r15
  __int64 v21; // rbx
  unsigned __int64 v22; // r14
  ULONG CurrentProcessorNumber; // eax
  unsigned int v24; // ecx
  unsigned int *v25; // r13
  struct _PAGED_LOOKASIDE_LIST *v26; // rcx
  _QWORD *PoolWithTag; // r14
  _QWORD *v28; // r14
  __int64 v29; // rcx
  unsigned int v30; // ebp
  unsigned int v31; // ebp
  unsigned __int64 v32; // rbx
  ULONG v33; // eax
  unsigned int v34; // ecx
  unsigned int *v35; // rsi
  struct _PAGED_LOOKASIDE_LIST *v36; // rcx
  _QWORD *v37; // rbx
  __int64 v38; // r13
  unsigned int *v39; // rsi
  unsigned int v40; // eax
  __int64 v41; // rbp
  __int64 v42; // rax
  unsigned int v43; // eax
  unsigned int *v44; // rcx
  signed __int64 v45; // rdx
  _OWORD *i; // rsi
  __int64 v47; // rbx
  const void *v48; // r15
  CmsBPlusTable *v49; // rcx
  __int64 v50; // rbp
  unsigned __int8 updated; // al
  __int64 v52; // rax
  void *v53; // rcx
  _QWORD *v55; // rax
  _QWORD *v56; // rax
  __int64 v57; // r9
  unsigned int v58; // edx
  struct _CmsData *v59; // rdx
  unsigned int v60; // r11d
  struct _CmsData *v61; // rdx
  __int64 v62; // r10
  unsigned int v63; // r10d
  int v64; // eax
  SIZE_T v65; // r14
  void **v66; // rbx
  __int64 v67; // rdi
  void *v68; // rcx
  int v69; // eax
  SIZE_T v70; // rbx
  unsigned int v71; // [rsp+20h] [rbp-88h]
  _OWORD v74[2]; // [rsp+40h] [rbp-68h] BYREF

  v5 = (_QWORD *)((char *)a4 + 8);
  v7 = 0;
  v8 = 0;
  v71 = 0;
  v9 = a4;
  v10 = a2;
  v11 = this;
  memset(v74, 0, sizeof(v74));
  if ( *((_QWORD *)a4 + 1) )
  {
    if ( *(_BYTE *)(*((_QWORD *)a3 + 5) + 12LL) || (*(_DWORD *)(*((_QWORD *)this + 3) + 44LL) & 4) == 0 )
    {
      v58 = _SmsIndexEntry::MmsKeyIsInData(a4, (struct _CmsRow *)((char *)a4 + 16))
          ? 0
          : (_SmsIndexEntry::MmsKeyLengthOutsideData(v9, (struct _CmsData *)(v57 + 16)) + 7) & 0xFFFFFFF8;
      v7 = 0;
      v12 = v58 + ((*((_DWORD *)v9 + 4) + 7) & 0xFFFFFFF8) + 16;
    }
    else
    {
      v12 = (*((_DWORD *)a4 + 4) + 7) & 0xFFFFFFF8;
    }
    if ( v12 )
      v8 = v12;
  }
  if ( *((_QWORD *)v9 + 5) )
  {
    v13 = !*(_BYTE *)(*((_QWORD *)a3 + 5) + 12LL) && (*(_DWORD *)(*((_QWORD *)v11 + 3) + 44LL) & 4) != 0;
    v14 = (struct _CmsRow *)((char *)v9 + 48);
    if ( v13 )
    {
      v15 = (*(_DWORD *)v14 + 7) & 0xFFFFFFF8;
    }
    else
    {
      v60 = _SmsIndexEntry::MmsKeyIsInData((struct _CmsRow *)((char *)v9 + 32), v14)
          ? 0
          : (_SmsIndexEntry::MmsKeyLengthOutsideData((struct _CmsRow *)((char *)v9 + 32), v59) + 7) & 0xFFFFFFF8;
      v7 = 0;
      v15 = v60 + ((*(_DWORD *)v59 + 7) & 0xFFFFFFF8) + 16;
    }
    if ( v15 > v8 )
      v8 = v15;
  }
  if ( *((_QWORD *)v9 + 9) )
  {
    v16 = !*(_BYTE *)(*((_QWORD *)a3 + 5) + 12LL) && (*(_DWORD *)(*((_QWORD *)v11 + 3) + 44LL) & 4) != 0;
    v17 = (struct _CmsRow *)((char *)v9 + 80);
    if ( v16 )
    {
      v18 = (*(_DWORD *)v17 + 7) & 0xFFFFFFF8;
    }
    else
    {
      v63 = _SmsIndexEntry::MmsKeyIsInData((struct _CmsRow *)((char *)v9 + 64), v17)
          ? 0
          : (_SmsIndexEntry::MmsKeyLengthOutsideData((struct _CmsKey *)(v62 + 64), v61) + 7) & 0xFFFFFFF8;
      v7 = 0;
      v18 = v63 + ((*(_DWORD *)v61 + 7) & 0xFFFFFFF8) + 16;
    }
    if ( v18 > v8 )
      v8 = v18;
  }
  v19 = 0;
  v20 = v74;
  v21 = 1;
  do
  {
    if ( !*v5 )
      goto LABEL_37;
    v71 = ++v7;
    if ( (*((_DWORD *)v10 + 4) & 0x1000LL) != 0 )
    {
      *v20 = 1;
      goto LABEL_37;
    }
    v22 = ((v8 + 7) & 0xFFFFFFF8) + 120;
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    if ( NumProcessors == 56 )
      v24 = CurrentProcessorNumber % 0x38;
    else
      v24 = CurrentProcessorNumber % NumProcessors;
    v25 = (unsigned int *)(qword_1C0136F20 + 192LL * v24);
    if ( v22 > *v25 )
    {
      v25 = 0;
      v65 = v22 + 8;
      goto LABEL_114;
    }
    if ( *((_BYTE *)v25 + 8) )
    {
      v26 = (struct _PAGED_LOOKASIDE_LIST *)(v25 + 16);
      if ( *((_BYTE *)v25 + 9) )
      {
        ++v25[21];
        PoolWithTag = ExpInterlockedPopEntrySList(&v26->L.ListHead);
        if ( PoolWithTag )
          goto LABEL_32;
        ++v25[22];
        v55 = (_QWORD *)(*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))v25 + 14))(v25[25], v25[27], v25[26]);
      }
      else
      {
        v55 = ExAllocateFromPagedLookasideList(v26);
      }
    }
    else
    {
      if ( (int)v25[20] <= (int)v25[22] )
        goto LABEL_112;
      v64 = _InterlockedDecrement((volatile signed __int32 *)v25 + 20);
      if ( v64 < (int)v25[22] || v64 < 0 )
      {
        _InterlockedIncrement((volatile signed __int32 *)v25 + 20);
LABEL_112:
        v65 = v25[1];
LABEL_114:
        PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, v65, 0x6950534Du);
        if ( !PoolWithTag )
        {
LABEL_115:
          *v20 = 0;
          goto LABEL_116;
        }
        goto LABEL_33;
      }
      v55 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v25 + 4);
    }
    PoolWithTag = v55;
LABEL_32:
    if ( !PoolWithTag )
      goto LABEL_112;
LABEL_33:
    *PoolWithTag = v25;
    v28 = PoolWithTag + 1;
    if ( !v28 )
      goto LABEL_115;
    v11 = this;
    v28[5] = this;
    *((_DWORD *)v28 + 4) = 31;
    *((_DWORD *)v28 + 3) = v8;
    *((_DWORD *)v28 + 2) = v8;
    *((_WORD *)v28 + 10) = 0;
    *((_DWORD *)v28 + 8) = 0;
    if ( v8 )
    {
      v28[3] = v28 + 15;
      memset(v28 + 15, 0, v8);
    }
    else
    {
      v28[3] = 0;
    }
    v7 = v71;
    *v20 = v28;
    v10 = a2;
LABEL_37:
    ++v19;
    v5 += 4;
    ++v20;
  }
  while ( v19 < 3 );
  v29 = *((_QWORD *)a3 + 6);
  if ( (*(_BYTE *)(v29 + 8) & 0x40) != 0 )
    v30 = (*(unsigned __int16 *)(v29 + 10) + 7) & 0xFFFFFFF8;
  else
    v30 = *(_DWORD *)v29;
  v31 = 2 * v30;
  if ( (*((_DWORD *)v10 + 4) & 0x1000LL) == 0 )
  {
    v32 = ((v31 + 7) & 0xFFFFFFF8) + 120;
    v33 = KeGetCurrentProcessorNumberEx(0);
    if ( NumProcessors == 56 )
      v34 = v33 % 0x38;
    else
      v34 = v33 % NumProcessors;
    v35 = (unsigned int *)(qword_1C0136F20 + 192LL * v34);
    if ( v32 > *v35 )
    {
      v35 = 0;
      v70 = v32 + 8;
    }
    else
    {
      if ( *((_BYTE *)v35 + 8) )
      {
        v36 = (struct _PAGED_LOOKASIDE_LIST *)(v35 + 16);
        if ( *((_BYTE *)v35 + 9) )
        {
          ++v35[21];
          v37 = ExpInterlockedPopEntrySList(&v36->L.ListHead);
          if ( v37 )
            goto LABEL_47;
          ++v35[22];
          v56 = (_QWORD *)(*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))v35 + 14))(v35[25], v35[27], v35[26]);
        }
        else
        {
          v56 = ExAllocateFromPagedLookasideList(v36);
        }
LABEL_88:
        v37 = v56;
LABEL_47:
        if ( v37 )
        {
LABEL_48:
          *v37 = v35;
          v21 = (__int64)(v37 + 1);
          if ( v21 )
          {
            *(_DWORD *)(v21 + 16) = 30;
            *(_QWORD *)(v21 + 40) = v11;
            *(_DWORD *)(v21 + 12) = v31;
            *(_DWORD *)(v21 + 8) = v31;
            *(_WORD *)(v21 + 20) = 0;
            *(_DWORD *)(v21 + 32) = 0;
            if ( v31 )
            {
              *(_QWORD *)(v21 + 24) = v21 + 120;
              memset((void *)(v21 + 120), 0, v31);
            }
            else
            {
              *(_QWORD *)(v21 + 24) = 0;
            }
            goto LABEL_51;
          }
LABEL_133:
          v21 = 0;
          goto LABEL_51;
        }
      }
      else if ( (int)v35[20] > (int)v35[22] )
      {
        v69 = _InterlockedDecrement((volatile signed __int32 *)v35 + 20);
        if ( v69 >= (int)v35[22] && v69 >= 0 )
        {
          v56 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v35 + 4);
          goto LABEL_88;
        }
        _InterlockedIncrement((volatile signed __int32 *)v35 + 20);
      }
      v70 = v35[1];
    }
    v37 = ExAllocatePoolWithTag((POOL_TYPE)512, v70, 0x6950534Du);
    if ( v37 )
      goto LABEL_48;
    goto LABEL_133;
  }
LABEL_51:
  v38 = v71;
  *((_QWORD *)v74 + v71) = v21;
  if ( v21 )
  {
    v39 = (unsigned int *)*((_QWORD *)a3 + 6);
    if ( (v39[2] & 0x40) != 0 )
      v40 = (*((unsigned __int16 *)v39 + 5) + 7) & 0xFFFFFFF8;
    else
      v40 = *v39;
    if ( v21 != 1 )
    {
      *(_QWORD *)(v21 + 40) = this;
      *(_DWORD *)(v21 + 8) = v40;
      *(_DWORD *)(v21 + 32) = 0;
      *(_OWORD *)(v21 + 48) = *(_OWORD *)a3;
      *(_OWORD *)(v21 + 64) = *((_OWORD *)a3 + 1);
      *(_OWORD *)(v21 + 80) = *((_OWORD *)a3 + 2);
      *(_OWORD *)(v21 + 96) = *((_OWORD *)a3 + 3);
      *(_QWORD *)(v21 + 112) = *((_QWORD *)a3 + 8);
      v41 = *(_QWORD *)a3;
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)a3 + 324LL));
      if ( (*(_QWORD *)(v41 + 408) & 0x20) == 0 )
      {
        ExAcquireResourceExclusiveLite((PERESOURCE)(v41 + 416), 0);
        if ( !CmsBPlusTable::WasUpdateDeferred(*(CmsBPlusTable **)(v41 + 120)) )
          ++*((_DWORD *)v10 + 6);
      }
      v42 = *(_QWORD *)a3;
      if ( *(_QWORD *)a3
        && (!*(_BYTE *)(v42 + 328) && *(CmsBPlusTable **)(v42 + 120) == this || !*((_BYTE *)this + 154)) )
      {
        *(_BYTE *)(v21 + 20) |= 1u;
      }
      v43 = *(_DWORD *)(v21 + 8);
      if ( v43 )
      {
        v44 = *(unsigned int **)(v21 + 24);
        if ( v39 )
        {
          if ( v39 != v44 )
            memmove(v44, v39, v43);
        }
        else
        {
          memset(v44, 0, *(unsigned int *)(v21 + 8));
        }
      }
      *(_QWORD *)v21 = *((_QWORD *)v10 + 324);
      *((_QWORD *)v10 + 324) = v21;
      if ( *(_DWORD *)(v21 + 16) == 18 )
        _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v21 + 40) + 8LL));
    }
    if ( v71 )
    {
      v45 = (char *)a5 - (char *)v74;
      for ( i = v74; ; i = (_OWORD *)((char *)i + 8) )
      {
        v47 = *(_QWORD *)i;
        v48 = *(const void **)(*(_QWORD *)i + 24LL);
        if ( *(_QWORD *)i != 1 )
          break;
LABEL_83:
        *(_QWORD *)((char *)i + v45) = *(_QWORD *)(v47 + 24);
        if ( !--v38 )
          return 0;
      }
      v49 = this;
      *(_QWORD *)(v47 + 40) = this;
      *(_DWORD *)(v47 + 8) = v8;
      *(_DWORD *)(v47 + 32) = 0;
      *(_OWORD *)(v47 + 48) = *(_OWORD *)a3;
      *(_OWORD *)(v47 + 64) = *((_OWORD *)a3 + 1);
      *(_OWORD *)(v47 + 80) = *((_OWORD *)a3 + 2);
      *(_OWORD *)(v47 + 96) = *((_OWORD *)a3 + 3);
      *(_QWORD *)(v47 + 112) = *((_QWORD *)a3 + 8);
      v50 = *(_QWORD *)a3;
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)a3 + 324LL));
      if ( (*(_QWORD *)(v50 + 408) & 0x20) == 0 )
      {
        ExAcquireResourceExclusiveLite((PERESOURCE)(v50 + 416), 0);
        updated = CmsBPlusTable::WasUpdateDeferred(*(CmsBPlusTable **)(v50 + 120));
        v49 = this;
        v45 = (char *)a5 - (char *)v74;
        if ( !updated )
          ++*((_DWORD *)v10 + 6);
      }
      v52 = *(_QWORD *)a3;
      if ( *(_QWORD *)a3 && (!*(_BYTE *)(v52 + 328) && *(CmsBPlusTable **)(v52 + 120) == v49 || !*((_BYTE *)v49 + 154)) )
        *(_BYTE *)(v47 + 20) |= 1u;
      if ( *(_DWORD *)(v47 + 8) )
      {
        v53 = *(void **)(v47 + 24);
        if ( v48 )
        {
          if ( v48 == v53 )
            goto LABEL_81;
          memmove(v53, v48, *(unsigned int *)(v47 + 8));
        }
        else
        {
          memset(v53, 0, *(unsigned int *)(v47 + 8));
        }
        v45 = (char *)a5 - (char *)v74;
      }
LABEL_81:
      *(_QWORD *)v47 = *((_QWORD *)v10 + 324);
      *((_QWORD *)v10 + 324) = v47;
      if ( *(_DWORD *)(v47 + 16) == 18 )
        _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v47 + 40) + 8LL));
      goto LABEL_83;
    }
    return 0;
  }
  else
  {
LABEL_116:
    v66 = (void **)v74;
    v67 = 4;
    do
    {
      v68 = *v66;
      if ( *v66 && v68 != (void *)1 )
        CmsLookasides::Free(v68);
      ++v66;
      --v67;
    }
    while ( v67 );
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x1c0005ae0  mov     [rsp+arg_0], rbx
0x1c0005ae5  push    rbp
0x1c0005ae6  push    rsi
0x1c0005ae7  push    rdi
0x1c0005ae8  push    r12
0x1c0005aea  push    r13
0x1c0005aec  push    r14
0x1c0005aee  push    r15
0x1c0005af0  sub     rsp, 70h
0x1c0005af4  mov     rax, cs:__security_cookie
0x1c0005afb  xor     rax, rsp
0x1c0005afe  mov     [rsp+0A8h+var_48], rax
0x1c0005b03  mov     rax, [rsp+0A8h+arg_20]
0x1c0005b0b  lea     rsi, [r9+8]
0x1c0005b0f  xorps   xmm0, xmm0
0x1c0005b12  mov     [rsp+0A8h+var_70], rdx
0x1c0005b17  mov     r12, r8
0x1c0005b1a  mov     [rsp+0A8h+var_78], rcx
0x1c0005b1f  xor     r8d, r8d
0x1c0005b22  mov     [rsp+0A8h+var_80], rax
0x1c0005b27  xor     edi, edi
0x1c0005b29  mov     [rsp+0A8h+var_88], r8d
0x1c0005b2e  mov     r10, r9
0x1c0005b31  mov     r14, rdx
0x1c0005b34  mov     r13, rcx
0x1c0005b37  movups  [rsp+0A8h+var_68], xmm0
0x1c0005b3c  movups  [rsp+0A8h+var_58], xmm0
0x1c0005b41  cmp     [rsi], rdi
0x1c0005b44  jz      short loc_1C0005B74
0x1c0005b46  mov     rax, [r12+28h]
0x1c0005b4b  cmp     [rax+0Ch], dil
0x1c0005b4f  jnz     loc_1C006E74C
0x1c0005b55  mov     rax, [rcx+18h]
0x1c0005b59  mov     ecx, [rax+2Ch]
0x1c0005b5c  test    cl, 4
0x1c0005b5f  jz      loc_1C006E74C
0x1c0005b65  mov     eax, [r9+10h]
0x1c0005b69  add     eax, 7
0x1c0005b6c  and     eax, 0FFFFFFF8h
0x1c0005b6f  test    eax, eax
0x1c0005b71  cmovnz  edi, eax
0x1c0005b74  cmp     qword ptr [r10+28h], 0
0x1c0005b79  jz      short loc_1C0005BB5
0x1c0005b7b  mov     rax, [r12+28h]
0x1c0005b80  cmp     byte ptr [rax+0Ch], 0
0x1c0005b84  jnz     loc_1C006E789
0x1c0005b8a  mov     rax, [r13+18h]
0x1c0005b8e  mov     ecx, [rax+2Ch]
0x1c0005b91  test    cl, 4
0x1c0005b94  jz      loc_1C006E789
0x1c0005b9a  mov     al, 1
0x1c0005b9c  lea     rdx, [r10+30h]; struct _CmsData *
0x1c0005ba0  test    al, al
0x1c0005ba2  jz      loc_1C006E790
0x1c0005ba8  mov     eax, [rdx]
0x1c0005baa  add     eax, 7
0x1c0005bad  and     eax, 0FFFFFFF8h
0x1c0005bb0  cmp     eax, edi
0x1c0005bb2  cmova   edi, eax
0x1c0005bb5  cmp     qword ptr [r10+48h], 0
0x1c0005bba  jz      short loc_1C0005BF6
0x1c0005bbc  mov     rax, [r12+28h]
0x1c0005bc1  cmp     byte ptr [rax+0Ch], 0
0x1c0005bc5  jnz     loc_1C006E7CB
0x1c0005bcb  mov     rax, [r13+18h]
0x1c0005bcf  mov     ecx, [rax+2Ch]
0x1c0005bd2  test    cl, 4
0x1c0005bd5  jz      loc_1C006E7CB
0x1c0005bdb  mov     al, 1
0x1c0005bdd  lea     rdx, [r10+50h]; struct _CmsData *
0x1c0005be1  test    al, al
0x1c0005be3  jz      loc_1C006E7D2
0x1c0005be9  mov     eax, [rdx]
0x1c0005beb  add     eax, 7
0x1c0005bee  and     eax, 0FFFFFFF8h
0x1c0005bf1  cmp     eax, edi
0x1c0005bf3  cmova   edi, eax
0x1c0005bf6  xor     ebp, ebp
0x1c0005bf8  lea     r15, [rsp+0A8h+var_68]
0x1c0005bfd  lea     ebx, [rbp+1]
0x1c0005c00  cmp     qword ptr [rsi], 0
0x1c0005c04  jz      loc_1C0005D1E
0x1c0005c0a  mov     eax, [r14+10h]
0x1c0005c0e  inc     r8d
0x1c0005c11  mov     [rsp+0A8h+var_88], r8d
0x1c0005c16  bt      rax, 0Ch
0x1c0005c1b  jb      loc_1C006E80D
0x1c0005c21  lea     r14d, [rdi+7]
0x1c0005c25  xor     ecx, ecx; ProcNumber
0x1c0005c27  and     r14d, 0FFFFFFF8h
0x1c0005c2b  add     r14d, 78h ; 'x'
0x1c0005c2f  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1c0005c36  nop     dword ptr [rax+rax+00h]
0x1c0005c3b  mov     r8d, cs:?NumProcessors@@3KA; ulong NumProcessors
0x1c0005c42  mov     ecx, eax
0x1c0005c44  cmp     r8d, 38h ; '8'
0x1c0005c48  jnz     loc_1C00060EE
0x1c0005c4e  mov     eax, 24924925h
0x1c0005c53  mul     ecx
0x1c0005c55  mov     eax, ecx
0x1c0005c57  sub     eax, edx
0x1c0005c59  shr     eax, 1
0x1c0005c5b  add     eax, edx
0x1c0005c5d  shr     eax, 5
0x1c0005c60  imul    eax, 38h ; '8'
0x1c0005c63  sub     ecx, eax
0x1c0005c65  mov     eax, ecx
0x1c0005c67  lea     r13, [rax+rax*2]
0x1c0005c6b  shl     r13, 6
0x1c0005c6f  add     r13, cs:qword_1C0136F20
0x1c0005c76  mov     eax, [r13+0]
0x1c0005c7a  cmp     r14, rax
0x1c0005c7d  ja      loc_1C006E862
0x1c0005c83  cmp     byte ptr [r13+8], 0
0x1c0005c88  jz      loc_1C006E820
0x1c0005c8e  cmp     byte ptr [r13+9], 0
0x1c0005c93  lea     rcx, [r13+40h]; Lookaside
0x1c0005c97  jz      loc_1C006E815
0x1c0005c9d  inc     dword ptr [r13+54h]
0x1c0005ca1  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c0005ca8  nop     dword ptr [rax+rax+00h]
0x1c0005cad  mov     r14, rax
0x1c0005cb0  test    rax, rax
0x1c0005cb3  jz      loc_1C00060AD
0x1c0005cb9  test    r14, r14
0x1c0005cbc  jz      loc_1C006E85C
0x1c0005cc2  mov     [r14], r13
0x1c0005cc5  add     r14, 8
0x1c0005cc9  jz      loc_1C006E88F
0x1c0005ccf  mov     r13, [rsp+0A8h+var_78]
0x1c0005cd4  mov     [r14+28h], r13
0x1c0005cd8  mov     dword ptr [r14+10h], 1Fh
0x1c0005ce0  mov     [r14+0Ch], edi
0x1c0005ce4  mov     [r14+8], edi
0x1c0005ce8  mov     word ptr [r14+14h], 0
0x1c0005cef  mov     dword ptr [r14+20h], 0
0x1c0005cf7  test    edi, edi
0x1c0005cf9  jz      loc_1C006E8C7
0x1c0005cff  lea     rcx, [r14+78h]; void *
0x1c0005d03  mov     r8d, edi; Size
0x1c0005d06  xor     edx, edx; Val
0x1c0005d08  mov     [r14+18h], rcx
0x1c0005d0c  call    memset
0x1c0005d11  mov     r8d, [rsp+0A8h+var_88]
0x1c0005d16  mov     [r15], r14
0x1c0005d19  mov     r14, [rsp+0A8h+var_70]
0x1c0005d1e  inc     ebp
0x1c0005d20  add     rsi, 20h ; ' '
0x1c0005d24  add     r15, 8
0x1c0005d28  cmp     ebp, 3
0x1c0005d2b  jb      loc_1C0005C00
0x1c0005d31  mov     rcx, [r12+30h]
0x1c0005d36  test    byte ptr [rcx+8], 40h
0x1c0005d3a  jz      loc_1C006E8D4
0x1c0005d40  movzx   ebp, word ptr [rcx+0Ah]
0x1c0005d44  add     ebp, 7
0x1c0005d47  and     ebp, 0FFFFFFF8h
0x1c0005d4a  mov     eax, [r14+10h]
0x1c0005d4e  add     ebp, ebp
0x1c0005d50  bt      rax, 0Ch
0x1c0005d55  jb      loc_1C0005E39
0x1c0005d5b  lea     ebx, [rbp+7]
0x1c0005d5e  xor     ecx, ecx; ProcNumber
0x1c0005d60  and     ebx, 0FFFFFFF8h
0x1c0005d63  add     ebx, 78h ; 'x'
0x1c0005d66  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1c0005d6d  nop     dword ptr [rax+rax+00h]
0x1c0005d72  mov     r8d, cs:?NumProcessors@@3KA; ulong NumProcessors
0x1c0005d79  mov     ecx, eax
0x1c0005d7b  cmp     r8d, 38h ; '8'
0x1c0005d7f  jnz     loc_1C00060FA
0x1c0005d85  mov     eax, 24924925h
0x1c0005d8a  mul     ecx
0x1c0005d8c  mov     eax, ecx
0x1c0005d8e  sub     eax, edx
0x1c0005d90  shr     eax, 1
0x1c0005d92  add     eax, edx
0x1c0005d94  shr     eax, 5
0x1c0005d97  imul    eax, 38h ; '8'
0x1c0005d9a  sub     ecx, eax
0x1c0005d9c  mov     eax, ecx
0x1c0005d9e  lea     rsi, [rax+rax*2]
0x1c0005da2  shl     rsi, 6
0x1c0005da6  add     rsi, cs:qword_1C0136F20
0x1c0005dad  mov     eax, [rsi]
0x1c0005daf  cmp     rbx, rax
0x1c0005db2  ja      loc_1C006E922
0x1c0005db8  cmp     byte ptr [rsi+8], 0
0x1c0005dbc  jz      loc_1C006E8E6
0x1c0005dc2  cmp     byte ptr [rsi+9], 0
0x1c0005dc6  lea     rcx, [rsi+40h]; Lookaside
0x1c0005dca  jz      loc_1C006E8DB
0x1c0005dd0  inc     dword ptr [rsi+54h]
0x1c0005dd3  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c0005dda  nop     dword ptr [rax+rax+00h]
0x1c0005ddf  mov     rbx, rax
0x1c0005de2  test    rax, rax
0x1c0005de5  jz      loc_1C00060CF
0x1c0005deb  test    rbx, rbx
0x1c0005dee  jz      loc_1C006E91D
0x1c0005df4  mov     [rbx], rsi
0x1c0005df7  add     rbx, 8
0x1c0005dfb  jz      loc_1C006E94E
0x1c0005e01  mov     dword ptr [rbx+10h], 1Eh
0x1c0005e08  mov     [rbx+28h], r13
0x1c0005e0c  mov     [rbx+0Ch], ebp
0x1c0005e0f  mov     [rbx+8], ebp
0x1c0005e12  mov     word ptr [rbx+14h], 0
0x1c0005e18  mov     dword ptr [rbx+20h], 0
0x1c0005e1f  test    ebp, ebp
0x1c0005e21  jz      loc_1C006E955
0x1c0005e27  lea     rcx, [rbx+78h]; void *
0x1c0005e2b  mov     r8d, ebp; Size
0x1c0005e2e  xor     edx, edx; Val
0x1c0005e30  mov     [rbx+18h], rcx
0x1c0005e34  call    memset
0x1c0005e39  mov     r13d, [rsp+0A8h+var_88]
0x1c0005e3e  mov     qword ptr [rsp+r13*8+0A8h+var_68], rbx
0x1c0005e43  test    rbx, rbx
0x1c0005e46  jz      loc_1C006E896
0x1c0005e4c  mov     rsi, [r12+30h]
0x1c0005e51  test    byte ptr [rsi+8], 40h
0x1c0005e55  jz      loc_1C006E962
0x1c0005e5b  movzx   eax, word ptr [rsi+0Ah]
0x1c0005e5f  add     eax, 7
0x1c0005e62  and     eax, 0FFFFFFF8h
0x1c0005e65  cmp     rbx, 1
0x1c0005e69  jz      loc_1C0005F54
0x1c0005e6f  mov     r15, [rsp+0A8h+var_78]
0x1c0005e74  mov     [rbx+28h], r15
0x1c0005e78  mov     [rbx+8], eax
0x1c0005e7b  mov     dword ptr [rbx+20h], 0
0x1c0005e82  movups  xmm0, xmmword ptr [r12]
0x1c0005e87  movups  xmmword ptr [rbx+30h], xmm0
0x1c0005e8b  movups  xmm1, xmmword ptr [r12+10h]
0x1c0005e91  movups  xmmword ptr [rbx+40h], xmm1
0x1c0005e95  movups  xmm0, xmmword ptr [r12+20h]
0x1c0005e9b  movups  xmmword ptr [rbx+50h], xmm0
0x1c0005e9f  movups  xmm1, xmmword ptr [r12+30h]
0x1c0005ea5  movups  xmmword ptr [rbx+60h], xmm1
0x1c0005ea9  movsd   xmm0, qword ptr [r12+40h]
0x1c0005eb0  movsd   qword ptr [rbx+70h], xmm0
0x1c0005eb5  mov     rbp, [r12]
0x1c0005eb9  lock inc dword ptr [rbp+144h]
0x1c0005ec0  mov     rax, [rbp+198h]
0x1c0005ec7  test    al, 20h
0x1c0005ec9  jnz     short loc_1C0005EF1
0x1c0005ecb  lea     rcx, [rbp+1A0h]; Resource
0x1c0005ed2  xor     edx, edx; Wait
0x1c0005ed4  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1c0005edb  nop     dword ptr [rax+rax+00h]
0x1c0005ee0  mov     rcx, [rbp+78h]; this
0x1c0005ee4  call    ?WasUpdateDeferred@CmsBPlusTable@@QEAAEXZ; CmsBPlusTable::WasUpdateDeferred(void)
0x1c0005ee9  test    al, al
0x1c0005eeb  jnz     short loc_1C0005EF1
0x1c0005eed  inc     dword ptr [r14+18h]
0x1c0005ef1  mov     rax, [r12]
0x1c0005ef5  test    rax, rax
0x1c0005ef8  jz      short loc_1C0005F15
0x1c0005efa  cmp     byte ptr [rax+148h], 0
0x1c0005f01  jnz     loc_1C006E969
0x1c0005f07  cmp     [rax+78h], r15
0x1c0005f0b  jnz     loc_1C006E969
0x1c0005f11  or      byte ptr [rbx+14h], 1
0x1c0005f15  mov     eax, [rbx+8]
0x1c0005f18  test    eax, eax
0x1c0005f1a  jz      short loc_1C0005F39
0x1c0005f1c  mov     rcx, [rbx+18h]; void *
0x1c0005f20  test    rsi, rsi
0x1c0005f23  jz      loc_1C006E97C
0x1c0005f29  cmp     rsi, rcx
0x1c0005f2c  jz      short loc_1C0005F39
0x1c0005f2e  mov     r8d, eax; Size
0x1c0005f31  mov     rdx, rsi; Src
0x1c0005f34  call    memmove
0x1c0005f39  mov     rax, [r14+0A20h]
0x1c0005f40  mov     [rbx], rax
0x1c0005f43  mov     [r14+0A20h], rbx
0x1c0005f4a  cmp     dword ptr [rbx+10h], 12h
0x1c0005f4e  jz      loc_1C006E98C
0x1c0005f54  cmp     [rsp+0A8h+var_88], 0
0x1c0005f59  jbe     loc_1C0006085
0x1c0005f5f  mov     rdx, [rsp+0A8h+var_80]
0x1c0005f64  lea     rax, [rsp+0A8h+var_68]
0x1c0005f69  sub     rdx, rax
0x1c0005f6c  lea     rsi, [rsp+0A8h+var_68]
0x1c0005f71  mov     [rsp+0A8h+var_80], rdx
0x1c0005f76  mov     rbx, [rsi]
0x1c0005f79  mov     r15, [rbx+18h]
0x1c0005f7d  cmp     rbx, 1
0x1c0005f81  jz      loc_1C000606F
0x1c0005f87  mov     rcx, [rsp+0A8h+var_78]
0x1c0005f8c  mov     [rbx+28h], rcx
0x1c0005f90  mov     [rbx+8], edi
0x1c0005f93  mov     dword ptr [rbx+20h], 0
0x1c0005f9a  movups  xmm0, xmmword ptr [r12]
0x1c0005f9f  movups  xmmword ptr [rbx+30h], xmm0
0x1c0005fa3  movups  xmm1, xmmword ptr [r12+10h]
0x1c0005fa9  movups  xmmword ptr [rbx+40h], xmm1
0x1c0005fad  movups  xmm0, xmmword ptr [r12+20h]
  ... truncated ...
```
