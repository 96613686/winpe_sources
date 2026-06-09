# CmsPinCache::AddToPinCache(CmsTransactionContext *,long,CmsBPlusTable *,_SmsLookupStack *,uchar,CmsKeyRange *,uchar,_SmsQuickIndex *)

- ea: `0x1c0014a50`
- end: `0x1c0015064`
- name: `?AddToPinCache@CmsPinCache@@QEAAXPEAVCmsTransactionContext@@JPEAVCmsBPlusTable@@PEAU_SmsLookupStack@@EPEAVCmsKeyRange@@EPEAU_SmsQuickIndex@@@Z`
- size: `1556`
- prototype: `void __usercall(CmsPinCache *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, int@<r8d>, struct CmsBPlusTable *@<r9>, struct _SmsLookupStack *, char, struct CmsKeyRange *, unsigned __int8, struct _SmsQuickIndex *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x1c00151a0`

## callees

- `0x1c0002b40`
- `0x1c0014a50`
- `0x1c001bcb0`
- `0x1c0030eec`
- `0x1c0032e3c`
- `0x1c00363b4`
- `0x1c0041e98`
- `0x1c006ac80`
- `0x1c006acc0`
- `0x1c006af80`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0014bfc`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c007562b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0014bfc`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c007562b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0014ebe`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c007555f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00755ed`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0014ebe`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c007555f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00755ed`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c0014b97`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c0014e44`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c0014b97`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c0014e44`

## pseudocode

```c
void __fastcall CmsPinCache::AddToPinCache(
        struct _LIST_ENTRY *this,
        struct CmsTransactionContext *a2,
        unsigned int a3,
        struct _LIST_ENTRY *a4,
        size_t *a5,
        char a6,
        struct CmsKeyRange *a7,
        unsigned __int8 a8,
        struct _SmsQuickIndex *a9)
{
  unsigned int v9; // r10d
  struct CmsBPlusTable **v11; // rdx
  unsigned int v14; // r9d
  struct CmsBPlusTable **v15; // rcx
  unsigned int i; // ecx
  struct _LIST_ENTRY *v17; // rbx
  unsigned int v18; // esi
  struct _LIST_ENTRY *v19; // rax
  size_t v20; // r8
  unsigned int v21; // r12d
  struct _LIST_ENTRY *Flink; // rcx
  unsigned int v23; // eax
  struct _LIST_ENTRY *v24; // rdx
  ULONG CurrentProcessorNumber; // eax
  unsigned int v26; // ecx
  __int64 v27; // rbx
  SIZE_T v28; // rdx
  _QWORD *v29; // rsi
  struct _LIST_ENTRY *v30; // rsi
  int v31; // edx
  unsigned int Flink_high; // ecx
  unsigned __int64 v33; // rax
  signed __int32 v34; // eax
  struct _LIST_ENTRY *v35; // rax
  struct _LIST_ENTRY *v36; // rcx
  struct _LIST_ENTRY *PoolWithTag; // r12
  const void *v38; // r9
  unsigned __int64 v39; // r12
  ULONG v40; // eax
  unsigned int v41; // ecx
  struct _LIST_ENTRY *v42; // rcx
  bool v43; // zf
  unsigned int *v44; // rax
  struct _PAGED_LOOKASIDE_LIST *v45; // rcx
  struct _LIST_ENTRY *v46; // rdx
  struct _LIST_ENTRY *v47; // rdx
  struct _LIST_ENTRY *v48; // r8
  struct _LIST_ENTRY *v49; // rdx
  struct _LIST_ENTRY *v50; // rax
  struct _LIST_ENTRY *Blink; // rcx
  struct _LIST_ENTRY *v52; // rcx
  struct _LIST_ENTRY *v53; // rax
  struct _NPAGED_LOOKASIDE_LIST *v54; // rcx
  _QWORD *v55; // rax
  int v56; // eax
  int v57; // eax
  SIZE_T v58; // r12
  unsigned int *v59; // [rsp+30h] [rbp-68h]
  int v60; // [rsp+30h] [rbp-68h]
  struct _LIST_ENTRY *v61; // [rsp+38h] [rbp-60h]
  int v62; // [rsp+38h] [rbp-60h]
  struct _LIST_ENTRY *v63; // [rsp+40h] [rbp-58h] BYREF
  void *Src; // [rsp+48h] [rbp-50h]
  struct _LIST_ENTRY v65; // [rsp+50h] [rbp-48h] BYREF
  size_t Size; // [rsp+A8h] [rbp+10h]
  int Sizea; // [rsp+A8h] [rbp+10h]

  v9 = 0;
  v11 = (struct CmsBPlusTable **)((char *)a2 + 1616);
  v14 = a3;
  v15 = v11;
  do
  {
    if ( !*v15 )
      break;
    if ( *v15 == (struct CmsBPlusTable *)a4 )
      goto LABEL_8;
    ++v9;
    ++v15;
  }
  while ( v9 < 0xF );
  for ( i = 0; i < 0xF; ++i )
  {
    if ( !*v11 )
      break;
    if ( *v11 == (struct CmsBPlusTable *)a4[2].Flink )
      goto LABEL_8;
    ++v11;
  }
  if ( (*((_DWORD *)a2 + 4) & 0x800LL) != 0 )
  {
LABEL_8:
    v17 = 0;
    v18 = 0;
    v65.Blink = &v65;
    v19 = &v65;
    v65.Flink = &v65;
    v20 = *a5;
    Size = *a5;
    if ( this == (struct _LIST_ENTRY *)((char *)a2 + 1584) )
      v21 = HIBYTE(word_1C0136885);
    else
      v21 = (unsigned __int16)dword_1C0136880;
    Flink = this->Flink;
    v63 = Flink;
    if ( Flink != this )
    {
      do
      {
        v23 = v18++;
        if ( v23 >= v21 )
          break;
        v24 = Flink - 1;
        if ( HIDWORD(Flink[3].Blink) == LODWORD(Flink[1].Flink[19].Flink)
          && LODWORD(v24[5].Flink) == LODWORD(v24[2].Blink[7].Blink) )
        {
          if ( v24[2].Flink == (struct _LIST_ENTRY *)v20 )
          {
            v17 = Flink - 1;
            break;
          }
          Flink = v63->Flink;
          v63 = v63->Flink;
        }
        else
        {
          CmsPinCache::DoomCachedPin((CmsPinCache *)this, (struct CmsCachedPin *)v24, &v65, &v63, 0);
          Flink = v63;
          v20 = Size;
        }
      }
      while ( Flink != this );
      v14 = a3;
      v19 = v65.Flink;
    }
    if ( v17 )
    {
      v49 = v17[1].Flink;
      v50 = v17 + 1;
      if ( v49->Blink == &v17[1] )
      {
        Blink = v17[1].Blink;
        if ( Blink->Flink == v50 )
        {
          Blink->Flink = v49;
          v49->Blink = Blink;
          v52 = this->Flink;
          if ( this->Flink->Blink == this )
          {
            v50->Flink = v52;
            v17[1].Blink = this;
            v52->Blink = v50;
            this->Flink = v50;
LABEL_41:
            if ( a9 )
            {
              *((_DWORD *)a9 + 2) = v17[4].Blink;
              *((_DWORD *)a9 + 3) = *((_DWORD *)a5 + 14);
              *((_DWORD *)a9 + 4) = *(_DWORD *)(*a5 + 308);
              *(_QWORD *)a9 = a5[6];
            }
            goto LABEL_43;
          }
        }
      }
LABEL_116:
      __fastfail(3u);
    }
    if ( LODWORD(this[1].Flink) >= v14 )
    {
      do
        CmsPinCache::DoomCachedPin((CmsPinCache *)this, (struct CmsCachedPin *)&this->Blink[-1], &v65, 0, 0);
      while ( LODWORD(this[1].Flink) >= a3 );
      v19 = v65.Flink;
    }
    if ( this == (struct _LIST_ENTRY *)((char *)a2 + 1584) && !*((_BYTE *)a2 + 1787) )
    {
      v17 = (struct _LIST_ENTRY *)((char *)a2 + 1792);
      if ( a2 != (struct CmsTransactionContext *)-1792LL )
      {
        *((_OWORD *)a2 + 115) = 0;
        *((_QWORD *)a2 + 232) = 0;
        *((_DWORD *)a2 + 465) |= 3u;
        *((_DWORD *)a2 + 470) = 0;
      }
      *((_DWORD *)a2 + 470) |= 0x10u;
      *((_BYTE *)a2 + 1787) = 1;
      *((_QWORD *)a2 + 239) = a2;
      goto LABEL_31;
    }
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    if ( NumProcessors == 56 )
      v26 = CurrentProcessorNumber % 0x38;
    else
      v26 = CurrentProcessorNumber % NumProcessors;
    v27 = qword_1C0136F48 + 192LL * v26;
    if ( *(_DWORD *)v27 < 0xA8u )
    {
      v27 = 0;
      v28 = 176;
      goto LABEL_26;
    }
    if ( *(_BYTE *)(v27 + 8) )
    {
      v54 = (struct _NPAGED_LOOKASIDE_LIST *)(v27 + 64);
      if ( *(_BYTE *)(v27 + 9) )
        v55 = ExAllocateFromNPagedLookasideList(v54);
      else
        v55 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v54);
LABEL_99:
      v29 = v55;
      if ( v55 )
      {
LABEL_27:
        *v29 = v27;
        v30 = (struct _LIST_ENTRY *)(v29 + 1);
        if ( !v30 )
          goto LABEL_43;
        memset(v30, 0, 0xA8u);
        v17 = v30 + 2;
        BYTE2(v30[1].Blink) = 32;
        if ( v30 != (struct _LIST_ENTRY *)-32LL )
        {
          v30[5] = 0;
          v30[6].Flink = 0;
          HIDWORD(v30[6].Flink) |= 3u;
          LODWORD(v30[7].Blink) = 0;
          v30[9].Blink = 0;
        }
        v30[9].Flink = v30;
        v19 = v65.Flink;
LABEL_31:
        if ( !v17 )
          goto LABEL_44;
        v17[2].Blink = a4;
        if ( v17[3].Flink )
          CmsKeyRange::FreeKeysBuffer((CmsKeyRange *)&v17[3]);
        v31 = 8;
        v17[3] = 0;
        v17[4].Flink = 0;
        Flink_high = HIDWORD(v17[4].Flink) | 3;
        HIDWORD(v17[4].Flink) = Flink_high;
        v33 = *((unsigned int *)a7 + 2);
        Sizea = v33;
        if ( !(_DWORD)v33 )
        {
LABEL_35:
          HIDWORD(v17[3].Blink) = *((_DWORD *)a7 + 3);
          LODWORD(v17[4].Flink) = *((_DWORD *)a7 + 4);
          if ( (Flink_high & 8) == 0 )
            v31 = 0;
          HIDWORD(v17[4].Flink) = v31 | *((_DWORD *)a7 + 5) & 0xFFFFFFF7;
          _InterlockedIncrement((volatile signed __int32 *)(*a5 + 324));
          HIDWORD(v17[4].Blink) = *(_DWORD *)(*a5 + 304);
          LODWORD(v17[5].Flink) = a4[7].Blink;
          HIDWORD(v17[5].Flink) = HIDWORD(a4[7].Flink);
          v17[6].Flink = (struct _LIST_ENTRY *)a5[8];
          v17[6].Blink = (struct _LIST_ENTRY *)a5[5];
          v17[2].Flink = (struct _LIST_ENTRY *)*a5;
          LOBYTE(v17[8].Flink) = a6;
          LODWORD(v17[5].Blink) = LODWORD(v17[5].Blink) ^ (LODWORD(v17[5].Blink) ^ (2 * a8)) & 2 | 1;
          do
          {
            v34 = _InterlockedExchangeAdd(&NextCachedPinId, 1u);
            LODWORD(v17[4].Blink) = v34 + 1;
          }
          while ( v34 == -1 );
          HIDWORD(v17[8].Flink) = *((_DWORD *)a2 + 1234);
          v35 = v17 + 1;
          v36 = this->Flink;
          if ( this->Flink->Blink == this )
          {
            v35->Flink = v36;
            v17[1].Blink = this;
            v36->Blink = v35;
            this->Flink = v35;
            ++LODWORD(this[1].Flink);
            goto LABEL_41;
          }
          goto LABEL_116;
        }
        PoolWithTag = v17[3].Flink;
        v38 = *(const void **)a7;
        Src = *(void **)a7;
        if ( PoolWithTag && LODWORD(v17[3].Blink) >= (unsigned int)v33 )
        {
LABEL_65:
          if ( v38 )
          {
            memmove(PoolWithTag, v38, (unsigned int)v33);
            Flink_high = HIDWORD(v17[4].Flink);
          }
          v31 = 8;
          goto LABEL_35;
        }
        if ( a2 && !*((_BYTE *)a2 + 1784) && (unsigned int)v33 <= 0x30 )
        {
          *((_BYTE *)a2 + 1784) = 1;
          PoolWithTag = (struct _LIST_ENTRY *)((char *)a2 + 1736);
          v62 = 48;
          v60 = 8;
          goto LABEL_61;
        }
        v39 = v33;
        v40 = KeGetCurrentProcessorNumberEx(0);
        if ( NumProcessors == 56 )
          v41 = v40 % 0x38;
        else
          v41 = v40 % NumProcessors;
        v42 = (struct _LIST_ENTRY *)(qword_1C0136F30 + 192LL * v41);
        v61 = v42;
        if ( v39 > LODWORD(v42->Flink) )
        {
          v61 = 0;
          v58 = v39 + 8;
LABEL_114:
          PoolWithTag = (struct _LIST_ENTRY *)ExAllocatePoolWithTag((POOL_TYPE)512, v58, 0x6950534Du);
          if ( !PoolWithTag )
            goto LABEL_60;
          goto LABEL_59;
        }
        if ( LOBYTE(v42->Blink) )
        {
          v43 = BYTE1(v42->Blink) == 0;
          v44 = (unsigned int *)&v42[4];
          v59 = (unsigned int *)&v42[4];
          v45 = (struct _PAGED_LOOKASIDE_LIST *)&v42[4];
          if ( v43 )
          {
            v53 = (struct _LIST_ENTRY *)ExAllocateFromPagedLookasideList(v45);
          }
          else
          {
            ++v44[5];
            PoolWithTag = (struct _LIST_ENTRY *)ExpInterlockedPopEntrySList(&v45->L.ListHead);
            if ( PoolWithTag )
            {
LABEL_58:
              if ( PoolWithTag )
              {
LABEL_59:
                PoolWithTag->Flink = v61;
                PoolWithTag = (struct _LIST_ENTRY *)((char *)PoolWithTag + 8);
LABEL_60:
                LODWORD(v33) = Sizea;
                v38 = Src;
                v62 = Sizea;
                v60 = 0;
LABEL_61:
                if ( !PoolWithTag )
                  goto LABEL_75;
                v46 = v17[3].Flink;
                if ( v46 )
                {
                  memmove(PoolWithTag, v46, LODWORD(v17[3].Blink));
                  CmsKeyRange::FreeKeysBuffer((CmsKeyRange *)&v17[3]);
                  LODWORD(v33) = Sizea;
                  v38 = Src;
                }
                Flink_high = v60 | HIDWORD(v17[4].Flink) & 0xFFFFFFF7;
                HIDWORD(v17[4].Flink) = Flink_high;
                v17[3].Flink = PoolWithTag;
                LODWORD(v17[3].Blink) = v62;
                goto LABEL_65;
              }
              v42 = v61;
              goto LABEL_112;
            }
            ++v59[6];
            v53 = (struct _LIST_ENTRY *)(*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))v59 + 6))(
                                          v59[9],
                                          v59[11],
                                          v59[10]);
          }
LABEL_82:
          PoolWithTag = v53;
          goto LABEL_58;
        }
        if ( SLODWORD(v42[5].Flink) > SLODWORD(v42[5].Blink) )
        {
          v57 = _InterlockedDecrement((volatile signed __int32 *)&v42[5]);
          if ( v57 >= SLODWORD(v42[5].Blink) && v57 >= 0 )
          {
            v53 = (struct _LIST_ENTRY *)ExpInterlockedPopEntrySList((PSLIST_HEADER)&v42[4]);
            goto LABEL_82;
          }
          _InterlockedIncrement((volatile signed __int32 *)&v42[5]);
        }
LABEL_112:
        v58 = HIDWORD(v42->Flink);
        goto LABEL_114;
      }
      goto LABEL_102;
    }
    if ( *(_DWORD *)(v27 + 80) > *(_DWORD *)(v27 + 88) )
    {
      v56 = _InterlockedDecrement((volatile signed __int32 *)(v27 + 80));
      if ( v56 >= *(_DWORD *)(v27 + 88) && v56 >= 0 )
      {
        v55 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v27 + 64));
        goto LABEL_99;
      }
      _InterlockedIncrement((volatile signed __int32 *)(v27 + 80));
    }
LABEL_102:
    v28 = *(unsigned int *)(v27 + 4);
LABEL_26:
    v29 = ExAllocatePoolWithTag((POOL_TYPE)512, v28, 0x6950534Du);
    if ( !v29 )
    {
LABEL_43:
      while ( 1 )
      {
        v19 = v65.Flink;
LABEL_44:
        if ( v19 == &v65 )
          return;
        v47 = v19->Flink;
        v17 = v19 - 1;
        if ( v19->Flink->Blink != v19 )
          goto LABEL_116;
        v48 = v19->Blink;
        if ( v48->Flink != v19 )
          goto LABEL_116;
        v48->Flink = v47;
        v47->Blink = v48;
        CmsCachedPin::Unpin((CmsCachedPin *)&v19[-1], a2);
LABEL_75:
        CmsCachedPin::Destroy((struct CmsCachedPin *)v17);
      }
    }
    goto LABEL_27;
  }
}

```

## disassembly

```asm
0x1c0014a50  mov     [rsp+arg_10], r8d
0x1c0014a55  push    rbp
0x1c0014a56  push    rdi
0x1c0014a57  push    r13
0x1c0014a59  sub     rsp, 80h
0x1c0014a60  xor     r10d, r10d
0x1c0014a63  mov     rbp, rdx
0x1c0014a66  add     rdx, 650h
0x1c0014a6d  mov     r13, r9
0x1c0014a70  mov     rdi, rcx
0x1c0014a73  mov     r9d, r8d
0x1c0014a76  mov     rcx, rdx
0x1c0014a79  mov     rax, [rcx]
0x1c0014a7c  test    rax, rax
0x1c0014a7f  jz      short loc_1C0014A93
0x1c0014a81  cmp     rax, r13
0x1c0014a84  jz      short loc_1C0014AAB
0x1c0014a86  inc     r10d
0x1c0014a89  add     rcx, 8
0x1c0014a8d  cmp     r10d, 0Fh
0x1c0014a91  jb      short loc_1C0014A79
0x1c0014a93  xor     ecx, ecx
0x1c0014a95  mov     rax, [rdx]
0x1c0014a98  test    rax, rax
0x1c0014a9b  jz      loc_1C0014F62
0x1c0014aa1  cmp     rax, [r13+20h]
0x1c0014aa5  jnz     loc_1C00754CC
0x1c0014aab  mov     [rsp+98h+arg_0], rbx
0x1c0014ab3  lea     rax, [rsp+98h+var_48]
0x1c0014ab8  mov     [rsp+98h+var_20], rsi
0x1c0014abd  xor     ebx, ebx
0x1c0014abf  mov     [rsp+98h+var_28], r12
0x1c0014ac4  xor     esi, esi
0x1c0014ac6  mov     [rsp+98h+var_30], r14
0x1c0014acb  lea     r14, [rbp+630h]
0x1c0014ad2  mov     [rsp+98h+var_38], r15
0x1c0014ad7  mov     r15, [rsp+98h+arg_20]
0x1c0014adf  mov     [rsp+98h+var_48.Blink], rax
0x1c0014ae4  lea     rax, [rsp+98h+var_48]
0x1c0014ae9  mov     [rsp+98h+var_48.Flink], rax
0x1c0014aee  mov     r8, [r15]
0x1c0014af1  mov     [rsp+98h+Size], r8
0x1c0014af9  cmp     rdi, r14
0x1c0014afc  jnz     loc_1C00754E0
0x1c0014b02  movzx   r12d, byte ptr cs:word_1C0136885+1
0x1c0014b0a  mov     rcx, [rdi]
0x1c0014b0d  mov     [rsp+98h+var_58], rcx
0x1c0014b12  cmp     rcx, rdi
0x1c0014b15  jz      short loc_1C0014B70
0x1c0014b17  mov     eax, esi
0x1c0014b19  inc     esi
0x1c0014b1b  cmp     eax, r12d
0x1c0014b1e  jnb     short loc_1C0014B63
0x1c0014b20  mov     rax, [rcx+10h]
0x1c0014b24  lea     rdx, [rcx-10h]; struct CmsCachedPin *
0x1c0014b28  mov     ecx, [rax+130h]
0x1c0014b2e  cmp     [rdx+4Ch], ecx
0x1c0014b31  jnz     loc_1C0015024
0x1c0014b37  mov     rax, [rdx+28h]
0x1c0014b3b  mov     ecx, [rax+78h]
0x1c0014b3e  cmp     [rdx+50h], ecx
0x1c0014b41  jnz     loc_1C0015024
0x1c0014b47  cmp     [rdx+20h], r8
0x1c0014b4b  jz      loc_1C0014FB2
0x1c0014b51  mov     rax, [rsp+98h+var_58]
0x1c0014b56  mov     rcx, [rax]
0x1c0014b59  mov     [rsp+98h+var_58], rcx
0x1c0014b5e  cmp     rcx, rdi
0x1c0014b61  jnz     short loc_1C0014B17
0x1c0014b63  mov     r9d, [rsp+98h+arg_10]
0x1c0014b6b  mov     rax, [rsp+98h+var_48.Flink]
0x1c0014b70  test    rbx, rbx
0x1c0014b73  jnz     loc_1C0014FBA
0x1c0014b79  cmp     [rdi+10h], r9d
0x1c0014b7d  jnb     loc_1C00754ED
0x1c0014b83  cmp     rdi, r14
0x1c0014b86  jnz     short loc_1C0014B95
0x1c0014b88  cmp     byte ptr [rbp+6FBh], 0
0x1c0014b8f  jz      loc_1C0014DBF
0x1c0014b95  xor     ecx, ecx; ProcNumber
0x1c0014b97  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1c0014b9e  nop     dword ptr [rax+rax+00h]
0x1c0014ba3  mov     r8d, cs:?NumProcessors@@3KA; ulong NumProcessors
0x1c0014baa  mov     ecx, eax
0x1c0014bac  cmp     r8d, 38h ; '8'
0x1c0014bb0  jnz     loc_1C001504C
0x1c0014bb6  mov     eax, 24924925h
0x1c0014bbb  mul     ecx
0x1c0014bbd  mov     eax, ecx
0x1c0014bbf  sub     eax, edx
0x1c0014bc1  shr     eax, 1
0x1c0014bc3  add     eax, edx
0x1c0014bc5  shr     eax, 5
0x1c0014bc8  imul    eax, 38h ; '8'
0x1c0014bcb  sub     ecx, eax
0x1c0014bcd  mov     eax, ecx
0x1c0014bcf  lea     rbx, [rax+rax*2]
0x1c0014bd3  shl     rbx, 6
0x1c0014bd7  add     rbx, cs:qword_1C0136F48
0x1c0014bde  cmp     dword ptr [rbx], 0A8h
0x1c0014be4  jnb     loc_1C0075520
0x1c0014bea  xor     ebx, ebx
0x1c0014bec  mov     edx, 0B0h; NumberOfBytes
0x1c0014bf1  mov     ecx, 200h; PoolType
0x1c0014bf6  mov     r8d, 6950534Dh; Tag
0x1c0014bfc  call    cs:__imp_ExAllocatePoolWithTag
0x1c0014c03  nop     dword ptr [rax+rax+00h]
0x1c0014c08  mov     rsi, rax
0x1c0014c0b  test    rax, rax
0x1c0014c0e  jz      loc_1C0014D83
0x1c0014c14  mov     [rsi], rbx
0x1c0014c17  add     rsi, 8
0x1c0014c1b  jz      loc_1C0014D83
0x1c0014c21  xor     edx, edx; Val
0x1c0014c23  mov     r8d, 0A8h; Size
0x1c0014c29  mov     rcx, rsi; void *
0x1c0014c2c  call    memset
0x1c0014c31  lea     rbx, [rsi+20h]
0x1c0014c35  mov     byte ptr [rsi+1Ah], 20h ; ' '
0x1c0014c39  test    rbx, rbx
0x1c0014c3c  jz      short loc_1C0014C56
0x1c0014c3e  xor     eax, eax
0x1c0014c40  xorps   xmm0, xmm0
0x1c0014c43  movups  xmmword ptr [rbx+30h], xmm0
0x1c0014c47  mov     [rbx+40h], rax
0x1c0014c4b  or      dword ptr [rbx+44h], 3
0x1c0014c4f  mov     [rbx+58h], eax
0x1c0014c52  mov     [rbx+78h], rax
0x1c0014c56  mov     [rbx+70h], rsi
0x1c0014c5a  mov     rax, [rsp+98h+var_48.Flink]
0x1c0014c5f  test    rbx, rbx
0x1c0014c62  jz      loc_1C0014D88
0x1c0014c68  mov     [rbx+28h], r13
0x1c0014c6c  cmp     qword ptr [rbx+30h], 0
0x1c0014c71  jnz     loc_1C0075585
0x1c0014c77  mov     r14, [rsp+98h+arg_30]
0x1c0014c7f  xor     eax, eax
0x1c0014c81  xorps   xmm0, xmm0
0x1c0014c84  mov     edx, 8
0x1c0014c89  movups  xmmword ptr [rbx+30h], xmm0
0x1c0014c8d  mov     [rbx+40h], rax
0x1c0014c91  mov     ecx, [rbx+44h]
0x1c0014c94  or      ecx, 3
0x1c0014c97  mov     [rbx+44h], ecx
0x1c0014c9a  mov     eax, [r14+8]
0x1c0014c9e  mov     dword ptr [rsp+98h+Size], eax
0x1c0014ca5  test    eax, eax
0x1c0014ca7  jnz     loc_1C0014E18
0x1c0014cad  mov     eax, [r14+0Ch]
0x1c0014cb1  mov     [rbx+3Ch], eax
0x1c0014cb4  mov     eax, [r14+10h]
0x1c0014cb8  shr     ecx, 3
0x1c0014cbb  mov     [rbx+40h], eax
0x1c0014cbe  mov     eax, [r14+14h]
0x1c0014cc2  and     cl, 1
0x1c0014cc5  jnz     short loc_1C0014CC9
0x1c0014cc7  xor     edx, edx
0x1c0014cc9  and     eax, 0FFFFFFF7h
0x1c0014ccc  or      eax, edx
0x1c0014cce  mov     [rbx+44h], eax
0x1c0014cd1  mov     rax, [r15]
0x1c0014cd4  lock inc dword ptr [rax+144h]
0x1c0014cdb  mov     rax, [r15]
0x1c0014cde  mov     ecx, [rax+130h]
0x1c0014ce4  mov     [rbx+4Ch], ecx
0x1c0014ce7  mov     eax, [r13+78h]
0x1c0014ceb  mov     [rbx+50h], eax
0x1c0014cee  mov     eax, [r13+74h]
0x1c0014cf2  mov     [rbx+54h], eax
0x1c0014cf5  mov     rax, [r15+40h]
0x1c0014cf9  mov     [rbx+60h], rax
0x1c0014cfd  mov     rax, [r15+28h]
0x1c0014d01  mov     [rbx+68h], rax
0x1c0014d05  mov     rax, [r15]
0x1c0014d08  mov     [rbx+20h], rax
0x1c0014d0c  movzx   eax, [rsp+98h+arg_28]
0x1c0014d14  mov     [rbx+80h], al
0x1c0014d1a  movzx   eax, [rsp+98h+arg_38]
0x1c0014d22  add     eax, eax
0x1c0014d24  xor     eax, [rbx+58h]
0x1c0014d27  and     eax, 2
0x1c0014d2a  xor     eax, [rbx+58h]
0x1c0014d2d  or      eax, 1
0x1c0014d30  mov     [rbx+58h], eax
0x1c0014d33  mov     eax, 1
0x1c0014d38  lock xadd cs:?NextCachedPinId@@3JA, eax; long NextCachedPinId
0x1c0014d40  add     eax, 1
0x1c0014d43  mov     [rbx+48h], eax
0x1c0014d46  jz      short loc_1C0014D33
0x1c0014d48  mov     eax, [rbp+1348h]
0x1c0014d4e  mov     [rbx+84h], eax
0x1c0014d54  lea     rax, [rbx+10h]
0x1c0014d58  mov     rcx, [rdi]
0x1c0014d5b  cmp     [rcx+8], rdi
0x1c0014d5f  jnz     loc_1C007566E
0x1c0014d65  mov     [rax], rcx
0x1c0014d68  mov     [rax+8], rdi
0x1c0014d6c  mov     [rcx+8], rax
0x1c0014d70  mov     [rdi], rax
0x1c0014d73  inc     dword ptr [rdi+10h]
0x1c0014d76  mov     rdx, [rsp+98h+arg_40]
0x1c0014d7e  test    rdx, rdx
0x1c0014d81  jnz     short loc_1C0014DF3
0x1c0014d83  mov     rax, [rsp+98h+var_48.Flink]
0x1c0014d88  lea     rcx, [rsp+98h+var_48]
0x1c0014d8d  cmp     rax, rcx
0x1c0014d90  jnz     loc_1C0014F75
0x1c0014d96  mov     r14, [rsp+98h+var_30]
0x1c0014d9b  mov     r12, [rsp+98h+var_28]
0x1c0014da0  mov     rsi, [rsp+98h+var_20]
0x1c0014da5  mov     rbx, [rsp+98h+arg_0]
0x1c0014dad  mov     r15, [rsp+98h+var_38]
0x1c0014db2  add     rsp, 80h
0x1c0014db9  pop     r13
0x1c0014dbb  pop     rdi
0x1c0014dbc  pop     rbp
0x1c0014dbd  retn
0x1c0014dbf  lea     rbx, [rbp+700h]
0x1c0014dc6  test    rbx, rbx
0x1c0014dc9  jz      short loc_1C0014DDF
0x1c0014dcb  xor     ecx, ecx
0x1c0014dcd  xorps   xmm0, xmm0
0x1c0014dd0  movups  xmmword ptr [rbx+30h], xmm0
0x1c0014dd4  mov     [rbx+40h], rcx
0x1c0014dd8  or      dword ptr [rbx+44h], 3
0x1c0014ddc  mov     [rbx+58h], ecx
0x1c0014ddf  or      dword ptr [rbx+58h], 10h
0x1c0014de3  mov     byte ptr [rbp+6FBh], 1
0x1c0014dea  mov     [rbx+78h], rbp
0x1c0014dee  jmp     loc_1C0014C5F
0x1c0014df3  mov     eax, [rbx+48h]
0x1c0014df6  mov     [rdx+8], eax
0x1c0014df9  mov     eax, [r15+38h]
0x1c0014dfd  mov     [rdx+0Ch], eax
0x1c0014e00  mov     rax, [r15]
0x1c0014e03  mov     ecx, [rax+134h]
0x1c0014e09  mov     [rdx+10h], ecx
0x1c0014e0c  mov     rax, [r15+30h]
0x1c0014e10  mov     [rdx], rax
0x1c0014e13  jmp     loc_1C0014D83
0x1c0014e18  mov     r12, [rbx+30h]
0x1c0014e1c  mov     r9, [r14]
0x1c0014e1f  mov     [rsp+98h+Src], r9
0x1c0014e24  test    r12, r12
0x1c0014e27  jnz     loc_1C0075594
0x1c0014e2d  test    rbp, rbp
0x1c0014e30  jz      short loc_1C0014E3F
0x1c0014e32  cmp     byte ptr [rbp+6F8h], 0
0x1c0014e39  jz      loc_1C0014F54
0x1c0014e3f  xor     ecx, ecx; ProcNumber
0x1c0014e41  mov     r12, rax
0x1c0014e44  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1c0014e4b  nop     dword ptr [rax+rax+00h]
0x1c0014e50  mov     r8d, cs:?NumProcessors@@3KA; ulong NumProcessors
0x1c0014e57  mov     ecx, eax
0x1c0014e59  cmp     r8d, 38h ; '8'
0x1c0014e5d  jnz     loc_1C0015058
0x1c0014e63  mov     eax, 24924925h
0x1c0014e68  mul     ecx
0x1c0014e6a  mov     eax, ecx
0x1c0014e6c  sub     eax, edx
0x1c0014e6e  shr     eax, 1
0x1c0014e70  add     eax, edx
0x1c0014e72  shr     eax, 5
0x1c0014e75  imul    eax, 38h ; '8'
0x1c0014e78  sub     ecx, eax
0x1c0014e7a  mov     eax, ecx
0x1c0014e7c  lea     rcx, [rax+rax*2]
0x1c0014e80  shl     rcx, 6
0x1c0014e84  add     rcx, cs:qword_1C0136F30
0x1c0014e8b  mov     [rsp+98h+var_60], rcx
0x1c0014e90  mov     eax, [rcx]
0x1c0014e92  cmp     r12, rax
0x1c0014e95  ja      loc_1C0075610
0x1c0014e9b  cmp     byte ptr [rcx+8], 0
0x1c0014e9f  jz      loc_1C00755CC
0x1c0014ea5  cmp     byte ptr [rcx+9], 0
0x1c0014ea9  lea     rax, [rcx+40h]
0x1c0014ead  mov     [rsp+98h+var_68], rax
0x1c0014eb2  mov     rcx, rax; Lookaside
0x1c0014eb5  jz      loc_1C00755C1
0x1c0014ebb  inc     dword ptr [rax+14h]
0x1c0014ebe  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c0014ec5  nop     dword ptr [rax+rax+00h]
0x1c0014eca  mov     r12, rax
0x1c0014ecd  test    rax, rax
0x1c0014ed0  jz      loc_1C0015000
0x1c0014ed6  test    r12, r12
0x1c0014ed9  jz      loc_1C00755FF
0x1c0014edf  mov     rax, [rsp+98h+var_60]
0x1c0014ee4  mov     [r12], rax
0x1c0014ee8  add     r12, 8
0x1c0014eec  mov     eax, dword ptr [rsp+98h+Size]
0x1c0014ef3  mov     r9, [rsp+98h+Src]
0x1c0014ef8  mov     dword ptr [rsp+98h+var_60], eax
0x1c0014efc  mov     dword ptr [rsp+98h+var_68], 0
0x1c0014f04  test    r12, r12
0x1c0014f07  jz      loc_1C0014FA5
0x1c0014f0d  mov     rdx, [rbx+30h]; Src
0x1c0014f11  test    rdx, rdx
  ... truncated ...
```
