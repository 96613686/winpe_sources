# CmsBPlusTable::UpdateInIndex(CmsTransactionContext *,_CmsRow const &,SmsLookupStack &&,ulong,EmsPinRowFlags)

- ea: `0x140097970`
- end: `0x1400980b5`
- name: `?UpdateInIndex@CmsBPlusTable@@UEAAJPEAVCmsTransactionContext@@AEBU_CmsRow@@$$QEAUSmsLookupStack@@KW4EmsPinRowFlags@@@Z`
- size: `1861`
- prototype: `__int64 __usercall@<rax>(CmsBPlusTable *this@<rcx>, int)`
- caller_count: `5`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14001a36c`
- `0x14001b120`
- `0x140023c38`
- `0x140130a30`
- `0x140153264`

## callees

- `0x14001a0c0`
- `0x140036df0`
- `0x140083ec0`
- `0x140097970`
- `0x1400c3a64`
- `0x1400c4acc`
- `0x1400c8574`
- `0x1400cb7e0`
- `0x1401e9e40`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x140097f9c`
- `ntoskrnl!KdDebuggerEnabled` at `0x140097fdc`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140098062`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140098062`
- `ntoskrnl!ExAllocatePool2` at `0x140097abf`
- `ntoskrnl!ExAllocatePool2` at `0x140097abf`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140097a84`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140097a84`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f9d56`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f9d56`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14009807f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14009807f`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140097e33`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140097e33`

## string_xrefs

- `0x14009809f`: `Calling UpdateSimple with a mismatch DataLength row!`
- `0x140097ad6`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsBPlusTable::UpdateInIndex(
        CmsBPlusTable *this,
        __int64 a2,
        __int64 a3,
        struct SmsPage **a4,
        unsigned int a5)
{
  struct SmsPage *v5; // r10
  __int64 v8; // r13
  __int16 v9; // r9
  __int16 v11; // r11
  unsigned int v12; // r8d
  unsigned int v13; // edx
  unsigned int *v14; // r14
  char v15; // bl
  __int64 v16; // r8
  int v17; // esi
  __int64 *v18; // r13
  struct SmsPage *v19; // r14
  __int16 v20; // ax
  bool v21; // zf
  unsigned __int16 v22; // ax
  unsigned int v23; // edi
  unsigned __int64 v24; // rbx
  unsigned int *v25; // rsi
  unsigned __int64 v26; // rdx
  __int64 Pool2; // rax
  _DWORD *v28; // rbx
  int v29; // ecx
  __int64 v30; // rdi
  unsigned int v31; // r8d
  struct _SmsRedoMarker *v32; // rcx
  __int16 v33; // r9
  char *v34; // rax
  struct SmsPage *v36; // rdx
  struct SmsPage *v37; // r8
  int v38; // r9d
  struct SmsPage *v39; // r10
  int v40; // r11d
  struct SmsPage *v41; // rax
  unsigned int v42; // eax
  char *v43; // rcx
  int v44; // r14d
  char *v45; // r9
  _BYTE *v46; // rsi
  unsigned __int16 *v47; // r12
  int *v48; // rbx
  int v49; // edi
  int v50; // eax
  char *v51; // rsi
  _DWORD *v52; // r12
  unsigned int v53; // eax
  size_t v54; // r8
  struct SmsPage *v55; // rdx
  char *v56; // rcx
  struct SmsPage *v57; // rdi
  __int128 v58; // xmm0
  unsigned __int16 v59; // r11
  __int16 v60; // ax
  __int16 v61; // ax
  void *v62; // rcx
  char *v63; // rdx
  __int64 v64; // rax
  struct _NPAGED_LOOKASIDE_LIST *v65; // rcx
  _DWORD *v66; // rax
  __int64 v67; // [rsp+40h] [rbp-69h]
  unsigned int *v68; // [rsp+60h] [rbp-49h]
  struct _SmsRedoMarker *v69; // [rsp+68h] [rbp-41h] BYREF
  int v70; // [rsp+70h] [rbp-39h] BYREF
  __int16 v71; // [rsp+74h] [rbp-35h]
  char *v72; // [rsp+78h] [rbp-31h]
  _DWORD v73[2]; // [rsp+80h] [rbp-29h] BYREF
  unsigned int *v74; // [rsp+88h] [rbp-21h]
  __int64 v75; // [rsp+90h] [rbp-19h] BYREF
  __int64 v76; // [rsp+98h] [rbp-11h]
  int v77; // [rsp+A4h] [rbp-5h]

  v5 = a4[2];
  v75 = 0;
  v76 = 0;
  v8 = a2;
  v69 = 0;
  v9 = *((_WORD *)v5 + 4);
  v11 = v9 & 0x40;
  if ( (v9 & 0x40) != 0 )
    v12 = *((unsigned __int16 *)v5 + 5);
  else
    v12 = *((_DWORD *)v5 + 3);
  v13 = a5;
  v14 = (unsigned int *)(a3 + 16);
  v68 = (unsigned int *)(a3 + 16);
  if ( a5 )
    goto LABEL_4;
  if ( *v14 < v12 )
  {
    v68 = (unsigned int *)(a3 + 16);
LABEL_4:
    v15 = 1;
    goto LABEL_5;
  }
  v15 = 0;
LABEL_5:
  if ( a5 + *v14 > v12 )
    return 3221225859LL;
  v16 = 12;
  v17 = 1;
  if ( (*((_BYTE *)this + 15) & 0x40) == 0 )
  {
    v30 = *(_QWORD *)(v8 + 416);
    v31 = 0;
    v32 = *(struct _SmsRedoMarker **)(v30 + 8);
    v73[0] = 0;
    v74 = 0;
    if ( !v32 )
      v32 = (struct _SmsRedoMarker *)(v30 + 8);
    v69 = v32;
    if ( a5 )
    {
      v31 = 1;
      v73[1] = v77;
      v74 = &a5;
      v73[0] = 4;
    }
    v33 = v9 & 3;
    if ( v11 )
    {
      v34 = (char *)v5 + 12;
      v70 = 12;
    }
    else
    {
      v33 |= 4u;
      v70 = *((unsigned __int16 *)v5 + 3);
      v34 = (char *)v5 + *((unsigned __int16 *)v5 + 2);
    }
    v72 = v34;
    v71 = v33;
    if ( !MsDisableRedoLogging && (*(_QWORD *)v8 & 0x2000000000LL) == 0 && (*(_QWORD *)v8 & 0x20) == 0 )
    {
      v64 = *(_QWORD *)(v8 + 8);
      if ( !v64 || (*(_DWORD *)(v64 + 3460) & 0x400001) == 0 )
      {
        v44 = CmsTxMemLog::AddRedoRecord(v30, this, 3u, &v70, v14, (__int64)v73, v31, 0, v67, 0, 0);
        if ( CmsBPlusTable::HasGlobalBindingSemantics(this) )
        {
          *(_QWORD *)(v8 + 112) = this;
          *(_QWORD *)v8 |= 0x80000000000uLL;
        }
        if ( v44 < 0 )
          goto LABEL_101;
        v13 = a5;
        v14 = v68;
      }
    }
    v16 = 12;
  }
  v18 = 0;
  if ( v15 && (*(_DWORD *)(*((_QWORD *)this + 3) + 44LL) & 2) == 0 )
  {
    v18 = &v75;
    v75 = v13;
    v76 = *v14;
  }
  if ( (*(_DWORD *)(*((_QWORD *)this + 3) + 44LL) & 2) != 0 && !*((_BYTE *)a4[1] + 12) )
    v17 = 2;
  v19 = a4[2];
  v20 = *((_WORD *)v19 + 4) & 0x40;
  if ( v18 )
  {
    v21 = v20 == 0;
    v22 = 12;
    if ( v21 )
      v22 = *((_WORD *)v19 + 3);
    v23 = *((_DWORD *)v18 + 2) + ((v22 + 7) & 0xFFFFFFF8);
  }
  else if ( v20 )
  {
    v23 = v17 * ((*((unsigned __int16 *)v19 + 5) + 7) & 0xFFFFFFF8);
  }
  else
  {
    v23 = v17 * *(_DWORD *)v19;
  }
  if ( (*(_DWORD *)a2 & 0x1000LL) == 0 )
  {
    v24 = ((v23 + 47) & 0xFFFFFFF8) + 88;
    v25 = (unsigned int *)(qword_140262410 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
    if ( v24 > *v25 )
    {
      v25 = 0;
      v26 = v24 + 16;
      goto LABEL_16;
    }
    if ( !*((_BYTE *)v25 + 8) )
    {
      if ( (int)*((_QWORD *)v25 + 11) > (int)HIDWORD(*((_QWORD *)v25 + 11)) )
      {
        v29 = _InterlockedDecrement((volatile signed __int32 *)v25 + 22);
        if ( v29 >= (int)v25[23] && v29 >= 0 )
        {
          v66 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v25 + 4);
          goto LABEL_64;
        }
        _InterlockedIncrement((volatile signed __int32 *)v25 + 22);
      }
LABEL_26:
      v26 = v25[1];
LABEL_16:
      Pool2 = ExAllocatePool2(66, v26, 1766871885);
      v28 = (_DWORD *)Pool2;
      if ( (Pool2 & 0xF) != 0 )
        MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
      if ( !Pool2 )
        goto LABEL_66;
      goto LABEL_65;
    }
    v65 = (struct _NPAGED_LOOKASIDE_LIST *)(v25 + 16);
    if ( *((_BYTE *)v25 + 9) )
      v66 = ExAllocateFromNPagedLookasideList(v65);
    else
      v66 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v65);
LABEL_64:
    v28 = v66;
    if ( v66 )
    {
LABEL_65:
      *(_QWORD *)v28 = v25;
      v28 += 4;
LABEL_66:
      if ( v28 )
      {
        v28[4] = 7;
        v28[3] = v23 + 40;
        v28[2] = v23 + 40;
        *((_QWORD *)v28 + 5) = this;
        *((_WORD *)v28 + 10) = 0;
        *((_OWORD *)v28 + 3) = 0;
        *((_OWORD *)v28 + 4) = 0;
        *((_QWORD *)v28 + 10) = 0;
        v28[8] = 0;
        if ( v23 == -40 )
        {
          *((_QWORD *)v28 + 3) = 0;
          v51 = 0;
        }
        else
        {
          *((_QWORD *)v28 + 3) = v28 + 22;
          memset(v28 + 22, 0, v23 + 40);
          v51 = (char *)*((_QWORD *)v28 + 3);
        }
        v52 = v51 + 20;
        if ( v18 )
        {
          v58 = *(_OWORD *)v18;
          v51[16] = 1;
          v59 = 12;
          *(_OWORD *)v51 = v58;
          *((_WORD *)v51 + 14) = *((_WORD *)v19 + 4);
          *v52 = v23 + 16;
          v60 = 12;
          *((_WORD *)v51 + 12) = 16;
          if ( (*((_BYTE *)v19 + 8) & 0x40) == 0 )
            v60 = *((_WORD *)v19 + 3);
          *((_WORD *)v51 + 13) = v60;
          v61 = 12;
          if ( (*((_BYTE *)v19 + 8) & 0x40) == 0 )
            v61 = *((_WORD *)v19 + 3);
          v62 = v51 + 32;
          *((_WORD *)v51 + 15) = (v61 + 23) & 0xFFF8;
          *((_DWORD *)v51 + 8) = *((_DWORD *)v18 + 2);
          if ( (*((_BYTE *)v19 + 8) & 0x40) != 0 )
          {
            v63 = (char *)v19 + 12;
          }
          else
          {
            v59 = *((_WORD *)v19 + 3);
            v63 = (char *)v19 + *((unsigned __int16 *)v19 + 2);
          }
          if ( (v51[28] & 0x40) == 0 )
            v62 = v51 + 36;
          memmove(v62, v63, v59);
          if ( (*((_BYTE *)v19 + 8) & 0x40) == 0 )
            v19 = (struct SmsPage *)((char *)v19 + *((unsigned __int16 *)v19 + 5));
          if ( (v51[28] & 0x40) != 0 )
            v56 = v51 + 20;
          else
            v56 = (char *)v52 + *((unsigned __int16 *)v51 + 15);
          v54 = v18[1];
          v55 = (struct SmsPage *)((char *)v19 + *v18);
        }
        else
        {
          *(_QWORD *)v51 = 0;
          *((_QWORD *)v51 + 1) = 0;
          v51[16] = 0;
          if ( (*((_BYTE *)v19 + 8) & 0x40) != 0 )
            v53 = (*((unsigned __int16 *)v19 + 5) + 7) & 0xFFFFFFF8;
          else
            v53 = *(_DWORD *)v19;
          v54 = v53;
          v55 = v19;
          v56 = v51 + 20;
        }
        memmove(v56, v55, v54);
        v28[2] = v23 + 40;
        *((_QWORD *)v28 + 5) = this;
        v28[8] = 0;
        v57 = *a4;
        _InterlockedIncrement((volatile signed __int32 *)*a4 + 95);
        v8 = a2;
        if ( (unsigned __int8)ExIsFastResourceHeldExclusive((char *)v57 + 560) )
          ++*((_DWORD *)v57 + 96);
        else
          SmsPageLatch::AcquireShared((struct SmsPage *)((char *)v57 + 560), (struct CmsTransactionContext *)a2, 1);
        if ( *(char *)(*((_QWORD *)v57 + 12) + 14LL) >= 0 )
          ++*(_DWORD *)(a2 + 196);
        ++*((_DWORD *)v57 + 97);
        v36 = a4[1];
        v37 = a4[2];
        v38 = *((_DWORD *)a4 + 6);
        v39 = a4[4];
        v40 = *((_DWORD *)a4 + 7);
        if ( *((_QWORD *)v28 + 6) && (_BYTE)KdDebuggerEnabled )
          __debugbreak();
        *((_QWORD *)v28 + 6) = *a4;
        *((_QWORD *)v28 + 7) = v36;
        *((_QWORD *)v28 + 8) = v37;
        v28[18] = v38;
        *((_QWORD *)v28 + 10) = v39;
        v28[19] = v40;
        v41 = *a4;
        if ( *a4 && (!*((_BYTE *)v41 + 392) && *((CmsBPlusTable **)v41 + 12) == this || !*((_BYTE *)this + 212)) )
          *((_BYTE *)v28 + 20) |= 1u;
        v42 = v28[2];
        if ( v42 )
        {
          v43 = (char *)*((_QWORD *)v28 + 3);
          if ( v51 )
          {
            if ( v51 != v43 )
              memmove(v43, v51, v42);
          }
          else
          {
            memset(v43, 0, (unsigned int)v28[2]);
          }
        }
        v44 = 0;
        *(_QWORD *)v28 = *(_QWORD *)(a2 + 144);
        *(_QWORD *)(a2 + 144) = v28;
        v45 = (char *)a4[1]
            + *(unsigned __int16 *)((char *)a4[1] + 4 * *((unsigned int *)a4 + 6) + *((unsigned int *)a4[1] + 4));
        v46 = v45 + 8;
        v47 = (unsigned __int16 *)(v45 + 10);
        v48 = (int *)(v45 + 12);
        if ( (v45[8] & 0x40) != 0 )
        {
          v49 = *v47;
        }
        else
        {
          v49 = *v48;
          v45 += *v47;
        }
        memmove(&v45[a5], *(const void **)(a3 + 24), *v68);
        if ( (*v46 & 0x40) != 0 )
          v50 = *v47;
        else
          v50 = *v48;
        if ( v50 != v49 )
          MsUnsupportedOperationBugCheck("Calling UpdateSimple with a mismatch DataLength row!");
        goto LABEL_54;
      }
      v8 = a2;
      goto LABEL_100;
    }
    goto LABEL_26;
  }
  if ( (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  v8 = a2;
  LOBYTE(v16) = 1;
  CmsVolume::ChangeVolumeOptionDynamically(*(_QWORD *)(a2 + 8), 0x20000000, v16);
LABEL_100:
  v44 = -1073741670;
LABEL_101:
  CmsTxMemLog::DiscardPendingRecordsFrom(*(CmsTxMemLog **)(v8 + 416), &v69);
LABEL_54:
  if ( *a4 )
    CmsVolume::Unpin(*(CmsVolume **)(v8 + 8), (struct CmsTransactionCore *)v8, a4, 3u);
  return (unsigned int)v44;
}

```

## disassembly

```asm
0x140097970  mov     [rsp-8+arg_10], r8
0x140097975  mov     [rsp-8+arg_8], rdx
0x14009797a  mov     [rsp-8+arg_0], rcx
0x14009797f  push    rbp
0x140097980  push    rbx
0x140097981  push    r12
0x140097983  push    r13
0x140097985  push    r14
0x140097987  push    r15
0x140097989  lea     rbp, [rsp-1Fh]
0x14009798e  sub     rsp, 0C8h
0x140097995  mov     r10, [r9+10h]
0x140097999  xor     eax, eax
0x14009799b  mov     r15, r9
0x14009799e  mov     [rbp+47h+var_60], rax
0x1400979a2  mov     rbx, r8
0x1400979a5  mov     [rbp+47h+var_58], rax
0x1400979a9  mov     r13, rdx
0x1400979ac  mov     [rbp+47h+var_88], rax
0x1400979b0  movzx   r9d, word ptr [r10+8]
0x1400979b5  mov     r12, rcx
0x1400979b8  movzx   r11d, r9w
0x1400979bc  and     r11w, 40h
0x1400979c1  jnz     loc_140097D59
0x1400979c7  mov     r8d, [r10+0Ch]
0x1400979cb  mov     edx, [rbp+47h+arg_20]
0x1400979ce  lea     r14, [rbx+10h]
0x1400979d2  mov     [rbp+47h+var_90], r14
0x1400979d6  test    edx, edx
0x1400979d8  jz      loc_140097AF3
0x1400979de  mov     bl, 1
0x1400979e0  mov     ecx, [r14]
0x1400979e3  add     ecx, edx
0x1400979e5  cmp     ecx, r8d
0x1400979e8  ja      loc_140097BC7
0x1400979ee  test    byte ptr [r12+0Fh], 40h
0x1400979f4  mov     r8d, 0Ch
0x1400979fa  mov     [rsp+0F0h+var_30], rsi
0x140097a02  mov     esi, 1
0x140097a07  mov     [rsp+0F0h+var_38], rdi
0x140097a0f  jz      loc_140097B56
0x140097a15  xor     r13d, r13d
0x140097a18  test    bl, bl
0x140097a1a  jnz     loc_14009800F
0x140097a20  mov     rax, [r12+18h]
0x140097a25  mov     ecx, [rax+2Ch]
0x140097a28  test    cl, 2
0x140097a2b  jnz     loc_140098036
0x140097a31  mov     r14, [r15+10h]
0x140097a35  movzx   eax, word ptr [r14+8]
0x140097a3a  and     ax, 40h
0x140097a3e  test    r13, r13
0x140097a41  jz      loc_140097AE3
0x140097a47  test    ax, ax
0x140097a4a  movzx   eax, r8w
0x140097a4e  jnz     short loc_140097A55
0x140097a50  movzx   eax, word ptr [r14+6]
0x140097a55  movzx   edi, ax
0x140097a58  add     edi, 7
0x140097a5b  and     edi, 0FFFFFFF8h
0x140097a5e  add     edi, [r13+8]
0x140097a62  mov     rax, [rbp+47h+arg_8]
0x140097a66  mov     eax, [rax]
0x140097a68  bt      rax, 0Ch
0x140097a6d  jb      loc_140097F9C
0x140097a73  lea     eax, [rdi+28h]
0x140097a76  xor     ecx, ecx; ProcNumber
0x140097a78  lea     ebx, [rax+7]
0x140097a7b  mov     [rbp+47h+arg_18], eax
0x140097a7e  and     ebx, 0FFFFFFF8h
0x140097a81  add     ebx, 58h ; 'X'
0x140097a84  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140097a8b  nop     dword ptr [rax+rax+00h]
0x140097a90  xor     edx, edx
0x140097a92  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140097a98  lea     rsi, [rdx+rdx*2]
0x140097a9c  shl     rsi, 6
0x140097aa0  add     rsi, cs:qword_140262410
0x140097aa7  mov     eax, [rsi]
0x140097aa9  cmp     rbx, rax
0x140097aac  jbe     short loc_140097B03
0x140097aae  xor     esi, esi
0x140097ab0  lea     rdx, [rbx+10h]
0x140097ab4  mov     ecx, 42h ; 'B'
0x140097ab9  mov     r8d, 6950534Dh
0x140097abf  call    cs:__imp_ExAllocatePool2
0x140097ac6  nop     dword ptr [rax+rax+00h]
0x140097acb  mov     rbx, rax
0x140097ace  test    al, 0Fh
0x140097ad0  jz      loc_1401F9D68
0x140097ad6  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x140097add  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x140097ae3  test    ax, ax
0x140097ae6  jnz     short loc_140097B43
0x140097ae8  mov     edi, [r14]
0x140097aeb  imul    edi, esi
0x140097aee  jmp     loc_140097A62
0x140097af3  cmp     [r14], r8d
0x140097af6  jb      loc_140097D63
0x140097afc  xor     bl, bl
0x140097afe  jmp     loc_1400979E0
0x140097b03  cmp     byte ptr [rsi+8], 0
0x140097b07  jnz     loc_140098054
0x140097b0d  mov     rcx, [rsi+58h]
0x140097b11  mov     rax, rcx
0x140097b14  shr     rax, 20h
0x140097b18  cmp     ecx, eax
0x140097b1a  jle     short loc_140097B3B
0x140097b1c  nop
0x140097b1d  mov     ecx, 0FFFFFFFFh
0x140097b22  lock xadd [rsi+58h], ecx
0x140097b27  nop
0x140097b28  dec     ecx
0x140097b2a  mov     eax, [rsi+5Ch]
0x140097b2d  cmp     ecx, eax
0x140097b2f  jge     loc_140098073
0x140097b35  nop
0x140097b36  lock inc dword ptr [rsi+58h]
0x140097b3a  nop
0x140097b3b  mov     edx, [rsi+4]
0x140097b3e  jmp     loc_140097AB4
0x140097b43  movzx   edi, word ptr [r14+0Ah]
0x140097b48  add     edi, 7
0x140097b4b  and     edi, 0FFFFFFF8h
0x140097b4e  imul    edi, esi
0x140097b51  jmp     loc_140097A62
0x140097b56  mov     rdi, [r13+1A0h]
0x140097b5d  mov     r8d, eax
0x140097b60  mov     rcx, [rdi+8]
0x140097b64  test    rcx, rcx
0x140097b67  mov     [rbp+47h+var_70], eax
0x140097b6a  mov     [rbp+47h+var_68], rax
0x140097b6e  lea     rax, [rdi+8]
0x140097b72  cmovz   rcx, rax
0x140097b76  mov     [rbp+47h+var_88], rcx
0x140097b7a  test    edx, edx
0x140097b7c  jnz     loc_140097FF2
0x140097b82  and     r9w, 3
0x140097b87  test    r11w, r11w
0x140097b8b  jnz     loc_140097D6C
0x140097b91  movzx   eax, word ptr [r10+6]
0x140097b96  or      r9w, 4
0x140097b9b  mov     [rbp+47h+var_80], eax
0x140097b9e  movzx   eax, word ptr [r10+4]
0x140097ba3  add     rax, r10
0x140097ba6  cmp     cs:?MsDisableRedoLogging@@3EA, 0; uchar MsDisableRedoLogging
0x140097bad  mov     [rbp+47h+var_78], rax
0x140097bb1  mov     [rbp+47h+var_7C], r9w
0x140097bb6  jz      loc_140097F63
0x140097bbc  mov     r8d, 0Ch
0x140097bc2  jmp     loc_140097A15
0x140097bc7  mov     eax, 0C0000183h
0x140097bcc  add     rsp, 0C8h
0x140097bd3  pop     r15
0x140097bd5  pop     r14
0x140097bd7  pop     r13
0x140097bd9  pop     r12
0x140097bdb  pop     rbx
0x140097bdc  pop     rbp
0x140097bdd  retn
0x140097bdf  inc     dword ptr [rdi+180h]
0x140097be5  mov     rax, [rdi+60h]
0x140097be9  cmp     byte ptr [rax+0Eh], 0
0x140097bed  jl      short loc_140097BF6
0x140097bef  inc     dword ptr [r13+0C4h]
0x140097bf6  inc     dword ptr [rdi+184h]
0x140097bfc  cmp     qword ptr [rbx+30h], 0
0x140097c01  mov     rcx, [r15]
0x140097c04  mov     rdx, [r15+8]
0x140097c08  mov     r8, [r15+10h]
0x140097c0c  mov     r9d, [r15+18h]
0x140097c10  mov     r10, [r15+20h]
0x140097c14  mov     r11d, [r15+1Ch]
0x140097c18  jnz     loc_140097FDC
0x140097c1e  mov     [rbx+30h], rcx
0x140097c22  mov     [rbx+38h], rdx
0x140097c26  mov     [rbx+40h], r8
0x140097c2a  mov     [rbx+48h], r9d
0x140097c2e  mov     [rbx+50h], r10
0x140097c32  mov     [rbx+4Ch], r11d
0x140097c36  mov     rax, [r15]
0x140097c39  test    rax, rax
0x140097c3c  jz      short loc_140097C59
0x140097c3e  cmp     byte ptr [rax+188h], 0
0x140097c45  jnz     loc_140097D34
0x140097c4b  cmp     [rax+60h], r12
0x140097c4f  jnz     loc_140097D34
0x140097c55  or      byte ptr [rbx+14h], 1
0x140097c59  mov     eax, [rbx+8]
0x140097c5c  test    eax, eax
0x140097c5e  jz      short loc_140097C7D
0x140097c60  mov     rcx, [rbx+18h]; void *
0x140097c64  test    rsi, rsi
0x140097c67  jz      loc_140098090
0x140097c6d  cmp     rsi, rcx
0x140097c70  jz      short loc_140097C7D
0x140097c72  mov     r8d, eax; Size
0x140097c75  mov     rdx, rsi; Src
0x140097c78  call    memmove
0x140097c7d  mov     rax, [r13+90h]
0x140097c84  xor     r14d, r14d
0x140097c87  mov     [rbx], rax
0x140097c8a  mov     [r13+90h], rbx
0x140097c91  mov     rdx, [r15+8]
0x140097c95  mov     ecx, [r15+18h]
0x140097c99  mov     eax, [rdx+10h]
0x140097c9c  add     rax, rdx
0x140097c9f  movzx   r9d, word ptr [rax+rcx*4]
0x140097ca4  add     r9, rdx
0x140097ca7  test    byte ptr [r9+8], 40h
0x140097cac  lea     rsi, [r9+8]
0x140097cb0  lea     r12, [r9+0Ah]
0x140097cb4  lea     rbx, [r9+0Ch]
0x140097cb8  jnz     loc_140097D48
0x140097cbe  movzx   eax, word ptr [r12]
0x140097cc3  mov     edi, [rbx]
0x140097cc5  add     r9, rax
0x140097cc8  mov     rax, [rbp+47h+var_90]
0x140097ccc  mov     ecx, [rbp+47h+arg_20]
0x140097ccf  mov     rdx, [rbp+47h+arg_10]
0x140097cd3  add     rcx, r9; void *
0x140097cd6  mov     r8d, [rax]; Size
0x140097cd9  mov     rdx, [rdx+18h]; Src
0x140097cdd  call    memmove
0x140097ce2  test    byte ptr [rsi], 40h
0x140097ce5  jnz     short loc_140097D52
0x140097ce7  mov     eax, [rbx]
0x140097ce9  cmp     eax, edi
0x140097ceb  jnz     loc_14009809F
0x140097cf1  cmp     qword ptr [r15], 0
0x140097cf5  jnz     short loc_140097D1D
0x140097cf7  mov     rsi, [rsp+0F0h+var_30]
0x140097cff  mov     eax, r14d
0x140097d02  mov     rdi, [rsp+0F0h+var_38]
0x140097d0a  add     rsp, 0C8h
0x140097d11  pop     r15
0x140097d13  pop     r14
0x140097d15  pop     r13
0x140097d17  pop     r12
0x140097d19  pop     rbx
0x140097d1a  pop     rbp
0x140097d1b  retn
0x140097d1d  mov     rcx, [r13+8]; this
0x140097d21  mov     r9d, 3; unsigned int
0x140097d27  mov     r8, r15; struct SmsPage **
0x140097d2a  mov     rdx, r13; struct CmsTransactionCore *
0x140097d2d  call    ?Unpin@CmsVolume@@QEAAXPEAVCmsTransactionCore@@PEAPEAUSmsPage@@K@Z; CmsVolume::Unpin(CmsTransactionCore *,SmsPage * *,ulong)
0x140097d32  jmp     short loc_140097CF7
0x140097d34  cmp     byte ptr [r12+0D4h], 0
0x140097d3d  jz      loc_140097C55
0x140097d43  jmp     loc_140097C59
0x140097d48  movzx   edi, word ptr [r12]
0x140097d4d  jmp     loc_140097CC8
0x140097d52  movzx   eax, word ptr [r12]
0x140097d57  jmp     short loc_140097CE9
0x140097d59  movzx   r8d, word ptr [r10+0Ah]
0x140097d5e  jmp     loc_1400979CB
0x140097d63  mov     [rbp+47h+var_90], r14
0x140097d67  jmp     loc_1400979DE
0x140097d6c  mov     r11d, 0Ch
0x140097d72  lea     rax, [r10+0Ch]
0x140097d76  mov     [rbp+47h+var_80], r11d
0x140097d7a  jmp     loc_140097BA6
0x140097d7f  mov     rbx, rax
0x140097d82  test    rax, rax
0x140097d85  jz      loc_140097B3B
0x140097d8b  mov     [rbx], rsi
0x140097d8e  add     rbx, 10h
0x140097d92  test    rbx, rbx
0x140097d95  jz      loc_1400980AC
0x140097d9b  mov     dword ptr [rbx+10h], 7
0x140097da2  lea     eax, [rdi+28h]
0x140097da5  mov     [rbx+0Ch], eax
0x140097da8  xor     ecx, ecx
0x140097daa  mov     [rbx+8], eax
0x140097dad  xorps   xmm0, xmm0
0x140097db0  mov     [rbx+28h], r12
0x140097db4  mov     word ptr [rbx+14h], 0
0x140097dba  movups  xmmword ptr [rbx+30h], xmm0
0x140097dbe  movups  xmmword ptr [rbx+40h], xmm0
0x140097dc2  mov     [rbx+50h], rcx
0x140097dc6  mov     [rbx+20h], ecx
0x140097dc9  test    eax, eax
0x140097dcb  jnz     loc_140097E62
0x140097dd1  mov     [rbx+18h], rcx
0x140097dd5  mov     esi, ecx
0x140097dd7  lea     r12, [rsi+14h]
0x140097ddb  test    r13, r13
0x140097dde  jnz     loc_140097E7F
0x140097de4  mov     [rsi], rcx
0x140097de7  mov     [rsi+8], rcx
0x140097deb  mov     [rsi+10h], r13b
0x140097def  test    byte ptr [r14+8], 40h
0x140097df4  jnz     loc_140097F53
0x140097dfa  mov     eax, [r14]
0x140097dfd  mov     r8d, eax; Size
0x140097e00  mov     rdx, r14; Src
0x140097e03  mov     rcx, r12; void *
0x140097e06  call    memmove
0x140097e0b  mov     r12, [rbp+47h+arg_0]
  ... truncated ...
```
