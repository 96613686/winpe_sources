# CmsBlockRefcount::GetNextRange(CmsTransactionContext *,_RANGE const *,_RANGE *,ushort *,uchar *,uchar *,CmsRefcountCacheEntry * *)

- ea: `0x140023480`
- end: `0x140023ab4`
- name: `?GetNextRange@CmsBlockRefcount@@QEAAJPEAVCmsTransactionContext@@PEBU_RANGE@@PEAU3@PEAGPEAE4PEAPEAVCmsRefcountCacheEntry@@@Z`
- size: `1588`
- prototype: `__int64 __usercall@<rax>(CmsBlockRefcount *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, const struct _RANGE *@<r8>, struct _RANGE *@<r9>, unsigned __int16 *, unsigned __int8 *, unsigned __int8 *, struct CmsRefcountCacheEntry **)`
- caller_count: `5`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400c01a0`
- `0x1401418d8`
- `0x140143978`
- `0x140145484`
- `0x1401455f8`

## callees

- `0x140023480`
- `0x140023ac0`
- `0x14003234c`
- `0x1400325d0`
- `0x140034ab0`
- `0x140036df0`
- `0x140081940`
- `0x14009ac80`
- `0x1400a2ab0`
- `0x1400a3600`
- `0x1400a3840`
- `0x1400c6fd0`
- `0x1400cb474`
- `0x14013b3dc`
- `0x14013c800`
- `0x14013c864`
- `0x14013c9f0`
- `0x1401e9dc0`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x14002396a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140023a92`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140023a92`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401f06df`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401f06df`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140023567`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140023567`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x140023787`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1401f07de`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x140023787`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1401f07de`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x140023644`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400239e7`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1401f07af`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x140023644`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400239e7`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1401f07af`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400235a9`
- `ntoskrnl!ExReleasePushLockEx` at `0x14002365e`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400239f9`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401f06cc`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400235a9`
- `ntoskrnl!ExReleasePushLockEx` at `0x14002365e`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400239f9`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401f06cc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140023766`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140023a1a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140023766`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140023a1a`

## pseudocode

```c
__int64 __fastcall CmsBlockRefcount::GetNextRange(
        CmsBlockRefcount *this,
        struct CmsTransactionContext *a2,
        const struct _RANGE *a3,
        struct _RANGE *a4,
        unsigned __int16 *a5,
        unsigned __int8 *a6,
        unsigned __int8 *a7,
        struct CmsRefcountCacheEntry **a8)
{
  __int64 v8; // rsi
  __int64 v10; // r15
  unsigned __int8 *v11; // rbx
  struct CmsRefcountCacheEntry **v12; // r12
  unsigned __int16 *v14; // rcx
  __int64 result; // rax
  unsigned int v16; // edx
  __int64 v17; // rax
  _QWORD *v18; // rdi
  _WORD *v19; // rcx
  _WORD *v20; // rdi
  unsigned int v21; // r8d
  __int64 v22; // r8
  _DWORD *v23; // r10
  int v24; // r11d
  int v25; // esi
  unsigned __int8 *v26; // r9
  unsigned __int8 *v27; // r10
  __int64 v28; // rax
  __int64 v29; // r15
  unsigned __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rbx
  struct CmsRefcountCacheEntry **v33; // rcx
  int v34; // eax
  unsigned __int64 v35; // rdx
  __int16 v36; // r11
  unsigned __int64 i; // rax
  _WORD *v38; // rax
  int v39; // ecx
  int v40; // eax
  PVOID v41; // rax
  struct _SmsTriageContext *v42; // rsi
  __int64 v43; // rax
  unsigned __int64 v44; // rcx
  int v45; // eax
  int v46; // [rsp+40h] [rbp-A9h] BYREF
  unsigned int v47; // [rsp+44h] [rbp-A5h]
  unsigned __int64 *v48; // [rsp+48h] [rbp-A1h]
  struct SmsPage *v49[2]; // [rsp+50h] [rbp-99h] BYREF
  __int128 v50; // [rsp+60h] [rbp-89h]
  __int64 v51; // [rsp+70h] [rbp-79h]
  unsigned __int64 v52; // [rsp+78h] [rbp-71h] BYREF
  __int64 v53; // [rsp+80h] [rbp-69h]
  _BYTE v54[24]; // [rsp+A8h] [rbp-41h] BYREF
  __int16 v55; // [rsp+C0h] [rbp-29h]
  char v56; // [rsp+C2h] [rbp-27h]
  int v57; // [rsp+D0h] [rbp-19h]
  _QWORD *v58; // [rsp+130h] [rbp+47h] BYREF
  struct CmsTransactionContext *v59; // [rsp+138h] [rbp+4Fh]
  PVOID Entry; // [rsp+140h] [rbp+57h]
  __int64 v61; // [rsp+148h] [rbp+5Fh]

  v59 = a2;
  v8 = *((_QWORD *)a3 + 1);
  v10 = *(_QWORD *)a3;
  v11 = a6;
  v12 = a8;
  v14 = a5;
  *(_QWORD *)a4 = *(_QWORD *)a3;
  *((_QWORD *)a4 + 1) = v8;
  v61 = v8;
  *v14 = 0;
  *v11 = 0;
  LOBYTE(v58) = 0;
  if ( v12 )
    *v12 = 0;
  if ( *((_DWORD *)this + 4) != 2 )
    return 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  a8 = (struct CmsRefcountCacheEntry **)(v10 & 0xFFFFFFFFFFFFFC00uLL);
  v48 = 0;
  v46 = 0;
  v16 = (((1103515245 * ((unsigned int)v10 & 0xFFFFFC00) + 12345) >> 16)
       | (unsigned __int64)((69069 * (v10 & 0xFFFFFC00)) & 0xFFFF0000))
      % *((unsigned int *)this + 10);
  v17 = *((_QWORD *)this + 4);
  v47 = v16;
  v18 = (_QWORD *)(v17 + 24LL * v16);
  v58 = v18 + 2;
  ExAcquirePushLockSharedEx(v18 + 2, 4);
  if ( v18[1] )
  {
    v19 = (_WORD *)*v18;
    v20 = (_WORD *)*v18;
    while ( *((struct CmsRefcountCacheEntry ***)v20 + 2) != a8 )
    {
      v20 = *(_WORD **)v20;
      if ( v20 == v19 )
        goto LABEL_79;
    }
    CmsRefcountCacheEntry::PinAndTouchEntry((struct SmsHashEntryLite *)v20);
    ExReleasePushLockEx(v58, 0);
  }
  else
  {
LABEL_79:
    ExReleasePushLockEx(v58, 0);
    v38 = ExAllocateFromNPagedLookasideList(&CmsRefcountCacheEntry::EntriesLookasideList);
    v20 = v38;
    if ( !v38 )
      return 3221225626LL;
    v38[24] = 1;
    v38[25] = 0;
    *((_DWORD *)v38 + 13) = 0;
    *((_DWORD *)v38 + 16) = 0;
    *((_QWORD *)v38 + 9) = 0;
    *((_QWORD *)v38 + 7) = 0;
    *((_QWORD *)v38 + 2) = a8;
    *((_OWORD *)v38 + 2) = 0;
    v39 = CmsHashTableLite::AddToIndex<1>((char *)this + 32, v38, CmsRefcountCacheEntry::PinAndTouchEntry);
    if ( v39 == -1073741771 )
    {
      CmsRefcountCacheEntry::Release(v20);
      Entry = 0;
      v58 = 0;
      v40 = CmsHashTableLite::PinInIndex<1>((char *)this + 32, a8, &v58, CmsRefcountCacheEntry::PinAndTouchEntry);
      v20 = v58;
      v39 = v40;
      v41 = Entry;
    }
    else
    {
      v41 = v20;
    }
    if ( v39 < 0 )
    {
      CmsRefcountCacheEntry::Release(v41);
      return 3221225626LL;
    }
  }
  if ( !v20 )
    return 3221225626LL;
  if ( (v20[25] & 1) != 0 )
  {
    v21 = 0;
    LODWORD(a8) = 0;
  }
  else
  {
    if ( !v59 )
    {
      CmsRefcountCacheEntry::Release(v20);
      return 3221225494LL;
    }
    CmsVolume::BeginTopLevelActionInternal(1024, v59, v54, 0, 0, 0);
    if ( (*(_DWORD *)(*(_QWORD *)(v31 + 8) + 3460LL) & 2) != 0 && CmsBlockRefcount::TrimCache(this) )
      CmsBlockRefcount::Persist(this, 0);
    CmsBPlusTable::EnterTree(*((CmsBPlusTable **)this + 1), v59);
    ExAcquirePushLockExclusiveEx(v20 + 28, 0);
    if ( (v20[25] & 1) != 0 )
    {
      LODWORD(a8) = 0;
    }
    else
    {
      v32 = ExAcquireAutoExpandPushLockShared((char *)this + 96, 2);
      v53 = 1024;
      v52 = *((_QWORD *)v20 + 2);
      while ( 1 )
      {
        v33 = (struct CmsRefcountCacheEntry **)*((_QWORD *)this + 1);
        v46 = 16;
        LOWORD(v47) = 0;
        v48 = &v52;
        v51 = 0;
        *(_OWORD *)v49 = 0;
        a8 = v33;
        v50 = 0;
        v34 = (*((__int64 (__fastcall **)(struct CmsRefcountCacheEntry **, struct CmsTransactionContext *, int *, _QWORD, struct SmsPage **, _QWORD))*v33
               + 10))(
                v33,
                v59,
                &v46,
                0,
                v49,
                0);
        v25 = v34;
        if ( v34 >= 0 )
          break;
        if ( v34 != -1073741400 )
          goto LABEL_44;
        if ( v49[0] )
          CmsVolume::Unpin(*((CmsVolumeContainer ***)v59 + 1), v59, v49, 3u);
        v42 = (struct _SmsTriageContext *)*((_QWORD *)v59 + 23);
        *((_QWORD *)v59 + 23) = 0;
        ExReleaseAutoExpandPushLockShared(v32, 2);
        LODWORD(a8) = CmsBlockRefcount::TriageCorruptChildRef(this, v59, v42);
        MsTriageDeleteContext(v42);
        v43 = ExAcquireAutoExpandPushLockShared((char *)this + 96, 2);
        v25 = (int)a8;
        v32 = v43;
        if ( (int)a8 < 0 )
          goto LABEL_19;
      }
      v22 = v50;
      if ( (*(_WORD *)(v50 + 8) & 0x40) != 0 )
      {
        v24 = *(unsigned __int16 *)(v50 + 10);
        v23 = (_DWORD *)(v50 + 12);
      }
      else
      {
        v23 = (_DWORD *)(v50 + *(unsigned __int16 *)(v50 + 4));
        v24 = *(_DWORD *)(v50 + 12);
        v22 = *(unsigned __int16 *)(v50 + 10) + (_QWORD)v50;
      }
      if ( (*((_DWORD *)a8[3] + 11) & 1) == 0 || *v23 == v24 )
      {
        if ( *(_BYTE *)(v22 + 16) == 1 )
        {
          v35 = 0;
          if ( *(_QWORD *)v22 > v52 )
            v35 = *(_QWORD *)v22 - v52;
          v44 = v53 - v35;
          if ( *(_QWORD *)(v22 + 8) < v53 - v35 )
            v44 = *(_QWORD *)(v22 + 8);
          if ( (*(_DWORD *)(v22 + 20) & 1) != 0 )
            v45 = CmsRefcountCacheEntry::Set(
                    (CmsRefcountCacheEntry *)v20,
                    v35,
                    v44,
                    (const unsigned __int16 *)(v22 + 2 * (v35 + 14)),
                    *(_DWORD *)(v22 + 24));
          else
            v45 = CmsRefcountCacheEntry::Set((CmsRefcountCacheEntry *)v20, v35, v44, *(_WORD *)(v22 + 28));
          v25 = v45;
          LODWORD(a8) = v45;
          if ( v49[0] )
            CmsVolume::Unpin(*((CmsVolumeContainer ***)v59 + 1), v59, v49, 3u);
          if ( v25 >= 0 && (v20[25] & 1) == 0 )
            _InterlockedOr16(v20 + 25, 1u);
        }
        else
        {
          v25 = -1073741637;
          LODWORD(a8) = -1073741637;
        }
        goto LABEL_19;
      }
      v25 = -1073741637;
      LODWORD(a8) = -1073741637;
      if ( v49[0] )
      {
        CmsVolume::Unpin(*((CmsVolumeContainer ***)v59 + 1), v59, v49, 3u);
        goto LABEL_46;
      }
LABEL_44:
      if ( v25 == -1073741772 )
      {
        if ( v49[0] )
          CmsVolume::Unpin(*((CmsVolumeContainer ***)v59 + 1), v59, v49, 3u);
        if ( (v20[25] & 1) == 0 )
          _InterlockedOr16(v20 + 25, 1u);
        v25 = 0;
        LODWORD(a8) = 0;
        goto LABEL_19;
      }
      LODWORD(a8) = v25;
LABEL_46:
      if ( !v49[0] )
        goto LABEL_20;
      CmsVolume::Unpin(*((CmsVolumeContainer ***)v59 + 1), v59, v49, 3u);
LABEL_19:
      if ( v49[0] && (_BYTE)KdDebuggerEnabled )
        __debugbreak();
LABEL_20:
      if ( v25 < 0 )
      {
        CmsVolume::AbortTopLevelAction(*(CmsVolume **)this, v59, (struct _SmsTopLevelAction *)v54);
        ExReleaseAutoExpandPushLockShared(v32, 2);
        ExReleasePushLockEx(v20 + 28, 0);
        CmsRefcountCacheEntry::Release(v20);
        return (unsigned int)v25;
      }
      ExReleaseAutoExpandPushLockShared(v32, 2);
      v11 = a6;
      v8 = v61;
    }
    ExReleasePushLockEx(v20 + 28, 0);
    CmsVolume::CommitTopLevelAction(*(CmsVolume **)this, v59, (struct _SmsTopLevelAction *)v54, 0);
    v21 = (unsigned int)a8;
  }
  if ( v12 )
  {
    ExAcquirePushLockExclusiveEx(v20 + 28, 0);
    v21 = (unsigned int)a8;
  }
  v26 = a7;
  v27 = (unsigned __int8 *)&v58;
  v28 = *((_QWORD *)v20 + 9);
  if ( a7 )
    v27 = a7;
  v29 = v10 - *((_QWORD *)v20 + 2);
  v30 = v8 + v29;
  if ( v28 )
  {
    v36 = *(_WORD *)(v28 + 2 * v29);
    if ( v30 > 0x400 )
      v30 = 1024;
    *v11 = v36 < 0;
    *v27 = (v36 & 0x4000) != 0;
    *a5 = v36 & 0x1FFF;
    for ( i = v29 + 1; i < v30; ++i )
    {
      if ( *(_WORD *)(*((_QWORD *)v20 + 9) + 2 * i) != v36 )
        break;
    }
    *((_QWORD *)a4 + 1) = i - v29;
  }
  else
  {
    if ( v30 > 0x400 )
      v30 = 1024;
    *a5 = 0;
    *((_QWORD *)a4 + 1) = v30 - v29;
    *v11 = 0;
    *v27 = 0;
  }
  if ( v12 )
  {
    *v12 = (struct CmsRefcountCacheEntry *)v20;
  }
  else if ( _InterlockedExchangeAdd16(v20 + 24, 0xFFFFu) == 1 )
  {
    CmsRefcountCacheEntry::~CmsRefcountCacheEntry((CmsRefcountCacheEntry *)v20);
    ExFreeToNPagedLookasideList(&CmsRefcountCacheEntry::EntriesLookasideList, v20);
    v21 = (unsigned int)a8;
    v26 = a7;
  }
  result = v21;
  if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 1712LL) + 120LL) & 0x20) == 0 )
  {
    *v11 = 0;
    if ( v26 )
      *v26 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140023480  mov     [rsp-8+arg_8], rdx
0x140023485  push    rbp
0x140023486  push    rbx
0x140023487  push    rsi
0x140023488  push    r12
0x14002348a  push    r13
0x14002348c  push    r14
0x14002348e  push    r15
0x140023490  lea     rbp, [rsp-7]
0x140023495  sub     rsp, 0F0h
0x14002349c  mov     rsi, [r8+8]
0x1400234a0  mov     r14, r9
0x1400234a3  mov     r15, [r8]
0x1400234a6  xor     eax, eax
0x1400234a8  mov     rbx, [rbp+37h+arg_28]
0x1400234ac  xor     r9d, r9d
0x1400234af  mov     r12, [rbp+37h+arg_38]
0x1400234b3  mov     r13, rcx
0x1400234b6  mov     rcx, [rbp+37h+arg_20]
0x1400234ba  mov     [r14], r15
0x1400234bd  mov     [r14+8], rsi
0x1400234c1  mov     [rbp+37h+arg_18], rsi
0x1400234c5  mov     [rcx], ax
0x1400234c8  mov     [rbx], al
0x1400234ca  mov     byte ptr [rbp+37h+arg_0], r9b
0x1400234ce  test    r12, r12
0x1400234d1  jz      short loc_1400234D7
0x1400234d3  mov     [r12], rax
0x1400234d7  mov     eax, [r13+10h]
0x1400234db  cmp     eax, 2
0x1400234de  jz      short loc_1400234F7
0x1400234e0  mov     eax, r9d
0x1400234e3  add     rsp, 0F0h
0x1400234ea  pop     r15
0x1400234ec  pop     r14
0x1400234ee  pop     r13
0x1400234f0  pop     r12
0x1400234f2  pop     rsi
0x1400234f3  pop     rbx
0x1400234f4  pop     rbp
0x1400234f5  retn
0x1400234f7  xor     edx, edx
0x1400234f9  mov     [rbp+37h+var_60], r9w
0x1400234fe  mov     [rbp+37h+var_5E], r9b
0x140023502  mov     rax, r15
0x140023505  and     rax, 0FFFFFFFFFFFFFC00h
0x14002350b  mov     [rbp+37h+var_50], r9d
0x14002350f  imul    ecx, eax, 41C64E6Dh
0x140023515  mov     [rbp+37h+arg_38], rax
0x140023519  imul    eax, 10DCDh
0x14002351f  mov     [rsp+120h+var_38], rdi
0x140023527  mov     [rsp+120h+var_D8], r9
0x14002352c  add     ecx, 3039h
0x140023532  mov     [rsp+120h+var_E0], r9d
0x140023537  shr     ecx, 10h
0x14002353a  and     eax, 0FFFF0000h
0x14002353f  or      eax, ecx
0x140023541  div     dword ptr [r13+28h]
0x140023545  mov     rax, [r13+20h]
0x140023549  mov     ecx, edx
0x14002354b  mov     [rsp+120h+var_DC], ecx
0x14002354f  lea     rcx, [rdx+rdx*2]
0x140023553  mov     edx, 4
0x140023558  lea     rdi, [rax+rcx*8]
0x14002355c  lea     rax, [rdi+10h]
0x140023560  mov     rcx, rax
0x140023563  mov     [rbp+37h+arg_0], rax
0x140023567  call    cs:__imp_ExAcquirePushLockSharedEx
0x14002356e  nop     dword ptr [rax+rax+00h]
0x140023573  cmp     qword ptr [rdi+8], 0
0x140023578  jbe     loc_1401F06C6
0x14002357e  mov     rcx, [rdi]
0x140023581  mov     rax, [rbp+37h+arg_38]
0x140023585  mov     rdi, rcx
0x140023588  cmp     [rdi+10h], rax
0x14002358c  jz      short loc_14002359B
0x14002358e  mov     rdi, [rdi]
0x140023591  cmp     rdi, rcx
0x140023594  jnz     short loc_140023588
0x140023596  jmp     loc_1401F06C6
0x14002359b  mov     rcx, rdi; struct SmsHashEntryLite *
0x14002359e  call    ?PinAndTouchEntry@CmsRefcountCacheEntry@@SAEPEAUSmsHashEntryLite@@@Z; CmsRefcountCacheEntry::PinAndTouchEntry(SmsHashEntryLite *)
0x1400235a3  mov     rcx, [rbp+37h+arg_0]
0x1400235a7  xor     edx, edx
0x1400235a9  call    cs:__imp_ExReleasePushLockEx
0x1400235b0  nop     dword ptr [rax+rax+00h]
0x1400235b5  test    rdi, rdi
0x1400235b8  jz      loc_1400238E4
0x1400235be  movzx   eax, word ptr [rdi+32h]
0x1400235c2  mov     ecx, 400h
0x1400235c7  test    al, 1
0x1400235c9  jz      loc_14002371A
0x1400235cf  xor     r8d, r8d
0x1400235d2  mov     dword ptr [rbp+37h+arg_38], r8d
0x1400235d6  jmp     loc_140023687
0x1400235db  mov     r8, qword ptr [rsp+120h+var_C0]
0x1400235e0  movzx   eax, word ptr [r8+8]
0x1400235e5  test    al, 40h
0x1400235e7  jnz     loc_1400238D6
0x1400235ed  movzx   r10d, word ptr [r8+4]
0x1400235f2  movzx   edx, word ptr [r8+0Ah]
0x1400235f7  add     r10, r8
0x1400235fa  mov     r11d, [r8+0Ch]
0x1400235fe  add     r8, rdx
0x140023601  mov     rax, [rbp+37h+arg_38]
0x140023605  mov     rax, [rax+18h]
0x140023609  mov     edx, [rax+2Ch]
0x14002360c  test    dl, 1
0x14002360f  jnz     loc_140023859
0x140023615  cmp     byte ptr [r8+10h], 1
0x14002361a  jz      loc_1400239B1
0x140023620  mov     esi, 0C00000BBh
0x140023625  mov     dword ptr [rbp+37h+arg_38], esi
0x140023628  cmp     [rsp+120h+var_D0], 0
0x14002362e  jnz     loc_14002396A
0x140023634  test    esi, esi
0x140023636  js      loc_1400239CE
0x14002363c  mov     edx, 2
0x140023641  mov     rcx, rbx
0x140023644  call    cs:__imp_ExReleaseAutoExpandPushLockShared
0x14002364b  nop     dword ptr [rax+rax+00h]
0x140023650  mov     rbx, [rbp+37h+arg_28]
0x140023654  mov     rsi, [rbp+37h+arg_18]
0x140023658  xor     edx, edx
0x14002365a  lea     rcx, [rdi+38h]
0x14002365e  call    cs:__imp_ExReleasePushLockEx
0x140023665  nop     dword ptr [rax+rax+00h]
0x14002366a  mov     rdx, [rbp+37h+arg_8]; struct CmsTransactionContext *
0x14002366e  lea     r8, [rbp+37h+var_78]; struct _SmsTopLevelAction *
0x140023672  mov     rcx, [r13+0]; this
0x140023676  xor     r9d, r9d; unsigned __int8
0x140023679  call    ?CommitTopLevelAction@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAU_SmsTopLevelAction@@E@Z; CmsVolume::CommitTopLevelAction(CmsTransactionContext *,_SmsTopLevelAction *,uchar)
0x14002367e  mov     r8d, dword ptr [rbp+37h+arg_38]
0x140023682  mov     ecx, 400h
0x140023687  test    r12, r12
0x14002368a  jnz     loc_140023A14
0x140023690  mov     r9, [rbp+37h+arg_30]
0x140023694  lea     r10, [rbp+37h+arg_0]
0x140023698  mov     rax, [rdi+48h]
0x14002369c  test    r9, r9
0x14002369f  cmovnz  r10, r9
0x1400236a3  sub     r15, [rdi+10h]
0x1400236a7  lea     rdx, [rsi+r15]
0x1400236ab  test    rax, rax
0x1400236ae  jnz     loc_140023A34
0x1400236b4  cmp     rdx, rcx
0x1400236b7  cmova   rdx, rcx
0x1400236bb  mov     rcx, [rbp+37h+arg_20]
0x1400236bf  sub     rdx, r15
0x1400236c2  mov     [rcx], ax
0x1400236c5  mov     [r14+8], rdx
0x1400236c9  mov     [rbx], al
0x1400236cb  mov     [r10], al
0x1400236ce  test    r12, r12
0x1400236d1  jnz     loc_140023850
0x1400236d7  mov     eax, 0FFFFFFFFh
0x1400236dc  lock xadd [rdi+30h], ax
0x1400236e2  cmp     ax, 1
0x1400236e6  jz      loc_140023A80
0x1400236ec  mov     rax, [r13+0]
0x1400236f0  mov     rcx, [rax+6B0h]
0x1400236f7  mov     eax, [rcx+78h]
0x1400236fa  test    al, 20h
0x1400236fc  mov     eax, r8d
0x1400236ff  jnz     short loc_14002370D
0x140023701  mov     byte ptr [rbx], 0
0x140023704  test    r9, r9
0x140023707  jnz     loc_140023AAB
0x14002370d  mov     rdi, [rsp+120h+var_38]
0x140023715  jmp     loc_1400234E3
0x14002371a  mov     rax, [rbp+37h+arg_8]
0x14002371e  test    rax, rax
0x140023721  jz      loc_140023980
0x140023727  mov     byte ptr [rsp+120h+var_F8], 0
0x14002372c  lea     r8, [rbp+37h+var_78]
0x140023730  xor     r9d, r9d
0x140023733  mov     byte ptr [rsp+120h+var_100], 0
0x140023738  mov     rdx, rax
0x14002373b  call    ?BeginTopLevelActionInternal@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAU_SmsTopLevelAction@@EEW4FoldOnlyTla@@@Z; CmsVolume::BeginTopLevelActionInternal(CmsTransactionContext *,_SmsTopLevelAction *,uchar,uchar,FoldOnlyTla)
0x140023740  mov     rax, [rdx+8]
0x140023744  mov     ecx, [rax+0D84h]
0x14002374a  test    cl, 2
0x14002374d  jnz     loc_140023992
0x140023753  mov     rdx, [rbp+37h+arg_8]; struct CmsTransactionContext *
0x140023757  mov     rcx, [r13+8]; this
0x14002375b  call    ?EnterTree@CmsBPlusTable@@UEAAEPEAVCmsTransactionContext@@@Z; CmsBPlusTable::EnterTree(CmsTransactionContext *)
0x140023760  lea     rcx, [rdi+38h]
0x140023764  xor     edx, edx
0x140023766  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14002376d  nop     dword ptr [rax+rax+00h]
0x140023772  movzx   eax, word ptr [rdi+32h]
0x140023776  test    al, 1
0x140023778  jnz     loc_1400238CC
0x14002377e  lea     rcx, [r13+60h]
0x140023782  mov     edx, 2
0x140023787  call    cs:__imp_ExAcquireAutoExpandPushLockShared
0x14002378e  nop     dword ptr [rax+rax+00h]
0x140023793  mov     rbx, rax
0x140023796  mov     [rbp+37h+var_A0], 400h
0x14002379e  mov     rax, [rdi+10h]
0x1400237a2  mov     [rbp+37h+var_A8], rax
0x1400237a6  mov     rcx, [r13+8]
0x1400237aa  lea     rdx, [rsp+120h+var_D0]
0x1400237af  xor     eax, eax
0x1400237b1  mov     [rsp+120h+var_E0], 10h
0x1400237b9  mov     word ptr [rsp+120h+var_DC], ax
0x1400237be  lea     r8, [rsp+120h+var_E0]
0x1400237c3  xorps   xmm0, xmm0
0x1400237c6  mov     [rsp+120h+var_F8], 0
0x1400237cf  lea     rax, [rbp+37h+var_A8]
0x1400237d3  mov     qword ptr [rsp+120h+var_100], rdx
0x1400237d8  mov     rdx, [rbp+37h+arg_8]
0x1400237dc  xor     r9d, r9d
0x1400237df  mov     [rsp+120h+var_D8], rax
0x1400237e4  xor     eax, eax
0x1400237e6  mov     [rbp+37h+var_B0], rax
0x1400237ea  movups  xmmword ptr [rsp+120h+var_D0], xmm0
0x1400237ef  mov     [rbp+37h+arg_38], rcx
0x1400237f3  movups  [rsp+120h+var_C0], xmm0
0x1400237f8  mov     rax, [rcx]
0x1400237fb  mov     rax, [rax+50h]
0x1400237ff  call    _guard_dispatch_icall
0x140023804  mov     esi, eax
0x140023806  test    eax, eax
0x140023808  jns     loc_1400235DB
0x14002380e  cmp     eax, 0C00001A8h
0x140023813  jz      loc_1400238F6
0x140023819  cmp     esi, 0C0000034h
0x14002381f  jz      short loc_14002388F
0x140023821  mov     dword ptr [rbp+37h+arg_38], esi
0x140023824  cmp     [rsp+120h+var_D0], 0
0x14002382a  jz      loc_140023634
0x140023830  mov     rax, [rbp+37h+arg_8]
0x140023834  lea     r8, [rsp+120h+var_D0]; struct SmsPage **
0x140023839  mov     r9d, 3; unsigned int
0x14002383f  mov     rdx, rax; struct CmsTransactionCore *
0x140023842  mov     rcx, [rax+8]; this
0x140023846  call    ?Unpin@CmsVolume@@QEAAXPEAVCmsTransactionCore@@PEAPEAUSmsPage@@K@Z; CmsVolume::Unpin(CmsTransactionCore *,SmsPage * *,ulong)
0x14002384b  jmp     loc_140023628
0x140023850  mov     [r12], rdi
0x140023854  jmp     loc_1400236EC
0x140023859  cmp     [r10], r11d
0x14002385c  jz      loc_140023615
0x140023862  cmp     [rsp+120h+var_D0], 0
0x140023868  mov     esi, 0C00000BBh
0x14002386d  mov     dword ptr [rbp+37h+arg_38], esi
0x140023870  jz      short loc_140023819
0x140023872  mov     rax, [rbp+37h+arg_8]
0x140023876  lea     r8, [rsp+120h+var_D0]; struct SmsPage **
0x14002387b  mov     r9d, 3; unsigned int
0x140023881  mov     rdx, rax; struct CmsTransactionCore *
0x140023884  mov     rcx, [rax+8]; this
0x140023888  call    ?Unpin@CmsVolume@@QEAAXPEAVCmsTransactionCore@@PEAPEAUSmsPage@@K@Z; CmsVolume::Unpin(CmsTransactionCore *,SmsPage * *,ulong)
0x14002388d  jmp     short loc_140023824
0x14002388f  cmp     [rsp+120h+var_D0], 0
0x140023895  jnz     short loc_1400238AF
0x140023897  test    byte ptr [rdi+32h], 1
0x14002389b  jnz     short loc_1400238A5
0x14002389d  nop
0x14002389e  lock or word ptr [rdi+32h], 1
0x1400238a4  nop
0x1400238a5  xor     esi, esi
0x1400238a7  mov     dword ptr [rbp+37h+arg_38], esi
0x1400238aa  jmp     loc_140023628
0x1400238af  mov     rax, [rbp+37h+arg_8]
0x1400238b3  lea     r8, [rsp+120h+var_D0]; struct SmsPage **
0x1400238b8  mov     r9d, 3; unsigned int
0x1400238be  mov     rdx, rax; struct CmsTransactionCore *
0x1400238c1  mov     rcx, [rax+8]; this
0x1400238c5  call    ?Unpin@CmsVolume@@QEAAXPEAVCmsTransactionCore@@PEAPEAUSmsPage@@K@Z; CmsVolume::Unpin(CmsTransactionCore *,SmsPage * *,ulong)
0x1400238ca  jmp     short loc_140023897
0x1400238cc  xor     eax, eax
0x1400238ce  mov     dword ptr [rbp+37h+arg_38], eax
0x1400238d1  jmp     loc_140023658
0x1400238d6  movzx   r11d, word ptr [r8+0Ah]
0x1400238db  lea     r10, [r8+0Ch]
0x1400238df  jmp     loc_140023601
0x1400238e4  mov     rdi, [rsp+120h+var_38]
0x1400238ec  mov     eax, 0C000009Ah
0x1400238f1  jmp     loc_1400234E3
0x1400238f6  cmp     [rsp+120h+var_D0], 0
0x1400238fc  jz      loc_1401F0791
0x140023902  mov     rax, [rbp+37h+arg_8]
0x140023906  lea     r8, [rsp+120h+var_D0]; struct SmsPage **
0x14002390b  mov     r9d, 3; unsigned int
0x140023911  mov     rdx, rax; struct CmsTransactionCore *
0x140023914  mov     rcx, [rax+8]; this
0x140023918  call    ?Unpin@CmsVolume@@QEAAXPEAVCmsTransactionCore@@PEAPEAUSmsPage@@K@Z; CmsVolume::Unpin(CmsTransactionCore *,SmsPage * *,ulong)
0x14002391d  nop
0x14002391e  jmp     loc_1401F0791
0x140023923  cmp     [rsp+120h+var_D0], 0
0x140023929  mov     esi, eax
0x14002392b  mov     dword ptr [rbp+37h+arg_38], eax
0x14002392e  jz      short loc_14002394B
0x140023930  mov     rax, [rbp+37h+arg_8]
0x140023934  lea     r8, [rsp+120h+var_D0]; struct SmsPage **
0x140023939  mov     r9d, 3; unsigned int
0x14002393f  mov     rdx, rax; struct CmsTransactionCore *
0x140023942  mov     rcx, [rax+8]; this
0x140023946  call    ?Unpin@CmsVolume@@QEAAXPEAVCmsTransactionCore@@PEAPEAUSmsPage@@K@Z; CmsVolume::Unpin(CmsTransactionCore *,SmsPage * *,ulong)
  ... truncated ...
```
