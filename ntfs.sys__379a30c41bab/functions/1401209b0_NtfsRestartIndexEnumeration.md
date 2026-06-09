# NtfsRestartIndexEnumeration

- ea: `0x1401209b0`
- end: `0x1401215d9`
- name: `NtfsRestartIndexEnumeration`
- size: `3113`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140122350`
- `0x1401a7b50`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x140027f50`
- `0x1400410a8`
- `0x1400592c0`
- `0x1400593e0`
- `0x140059440`
- `0x140059740`
- `0x1400c8420`
- `0x14011fe50`
- `0x1401209b0`
- `0x140121a50`
- `0x140122780`
- `0x140124490`
- `0x14013257c`
- `0x140153960`
- `0x140153b00`
- `0x1402143b0`
- `0x140223a3c`
- `0x14023b8f0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140120f86`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140120f86`
- `ntoskrnl!ExReleasePushLockEx` at `0x140120ab4`
- `ntoskrnl!ExReleasePushLockEx` at `0x140120faa`
- `ntoskrnl!ExReleasePushLockEx` at `0x140120ab4`
- `ntoskrnl!ExReleasePushLockEx` at `0x140120faa`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402a5822`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c73c6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402a5822`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c73c6`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140120b9d`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140120b9d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012151a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401215bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a57e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012151a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401215bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a57e4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140120dcf`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140120dcf`
- `ntoskrnl!CcUnpinData` at `0x140120b04`
- `ntoskrnl!CcUnpinData` at `0x140120b2c`
- `ntoskrnl!CcUnpinData` at `0x140120b45`
- `ntoskrnl!CcUnpinData` at `0x140120b5e`
- `ntoskrnl!CcUnpinData` at `0x140120b04`
- `ntoskrnl!CcUnpinData` at `0x140120b2c`
- `ntoskrnl!CcUnpinData` at `0x140120b45`
- `ntoskrnl!CcUnpinData` at `0x140120b5e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140120eea`
- `ntoskrnl!ExReleaseResourceLite` at `0x140120fcf`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012135f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401214f1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a5789`
- `ntoskrnl!ExReleaseResourceLite` at `0x140120eea`
- `ntoskrnl!ExReleaseResourceLite` at `0x140120fcf`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012135f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401214f1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a5789`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140120e50`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401212bc`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140121476`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140120e50`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401212bc`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140121476`

## pseudocode

```c
__int64 __fastcall NtfsRestartIndexEnumeration(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int8 a5,
        char a6,
        _QWORD *a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v11; // rbx
  __int64 v12; // rsi
  __int64 v13; // rcx
  __int64 v14; // rdi
  unsigned int v15; // esi
  unsigned __int64 v16; // r14
  void *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  void *v20; // rcx
  __int64 v21; // r14
  unsigned __int8 v22; // di
  char *v23; // rdi
  __int64 v24; // r13
  __int64 v25; // rsi
  __int64 v26; // rax
  char v27; // r8
  __int64 v28; // r12
  unsigned __int8 v29; // si
  int v30; // edx
  int v31; // r10d
  int v32; // eax
  int v33; // edi
  char v34; // di
  unsigned __int16 *v35; // rdx
  void *v36; // rcx
  unsigned __int16 *v37; // rcx
  int v38; // edx
  char v39; // r8
  __int64 v40; // rdx
  int NextIndexEntry2; // eax
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 v45; // rcx
  struct _ERESOURCE *v46; // rcx
  bool v47; // di
  _BYTE *v48; // r12
  __int64 v49; // rsi
  __int64 v50; // rax
  char v51; // cl
  __int64 QueryFileName; // rax
  unsigned __int8 (__fastcall *v53)(PCWCH, __int64, _BYTE *, _QWORD); // r10
  __int64 OtherFileName; // rax
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // r9
  int v58; // r9d
  __int64 v59; // rax
  char IsEqual; // al
  __int64 v61; // rax
  int v62; // eax
  char v63; // di
  __int64 v65; // rcx
  void *v66; // rcx
  __int64 v67; // rdx
  int v68; // [rsp+28h] [rbp-260h]
  int v69; // [rsp+28h] [rbp-260h]
  __int64 v70; // [rsp+28h] [rbp-260h]
  int v71; // [rsp+50h] [rbp-238h]
  char v72; // [rsp+62h] [rbp-226h]
  char v73; // [rsp+63h] [rbp-225h]
  char v74; // [rsp+64h] [rbp-224h] BYREF
  unsigned __int8 v75; // [rsp+65h] [rbp-223h]
  int v76; // [rsp+68h] [rbp-220h]
  void *Src; // [rsp+70h] [rbp-218h] BYREF
  __int64 v78; // [rsp+78h] [rbp-210h] BYREF
  int v79[2]; // [rsp+80h] [rbp-208h]
  unsigned int v80; // [rsp+88h] [rbp-200h]
  __int64 v81; // [rsp+90h] [rbp-1F8h] BYREF
  PCWCH UpcaseTable; // [rsp+98h] [rbp-1F0h]
  __int64 v83; // [rsp+A0h] [rbp-1E8h]
  __int64 v84; // [rsp+A8h] [rbp-1E0h]
  __int64 v85; // [rsp+B0h] [rbp-1D8h]
  __int64 v86; // [rsp+B8h] [rbp-1D0h]
  _QWORD *v87; // [rsp+C0h] [rbp-1C8h]
  __int64 v88; // [rsp+C8h] [rbp-1C0h]
  _QWORD v89[46]; // [rsp+D0h] [rbp-1B8h] BYREF

  v81 = a4;
  v11 = a2;
  v12 = a1;
  *(_QWORD *)v79 = a1;
  v84 = a1;
  v85 = a2;
  v88 = a3;
  v87 = a7;
  v86 = a8;
  v83 = a9;
  Src = 0;
  memset(v89, 0, sizeof(v89));
  LODWORD(v78) = 0;
  v74 = 0;
  v13 = *(_QWORD *)(v12 + 104);
  UpcaseTable = *(PCWCH *)(v13 + 784);
  v76 = -1073741275;
  v73 = 0;
  v72 = 0;
  v14 = *(_QWORD *)(v11 + 136);
  if ( v14 )
  {
    v80 = 0;
    if ( (*(_BYTE *)(v14 + 330) & 1) != 0 )
    {
      ExReleasePushLockEx(v13 + 656, 0);
      *(_WORD *)(v14 + 330) &= ~1u;
    }
    if ( *(_QWORD *)(v14 + 352) )
    {
      ExAcquirePushLockSharedEx(*(_QWORD *)(v12 + 104) + 656LL, 0);
      _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(v14 + 352) + 28LL));
      ExReleasePushLockEx(*(_QWORD *)(v12 + 104) + 656LL, 0);
      v45 = *(_QWORD *)(v14 + 352);
      if ( *(_WORD *)v45 == 1794 )
        v46 = (struct _ERESOURCE *)(*(_QWORD *)(v45 + 104) + 64LL);
      else
        v46 = *(struct _ERESOURCE **)(v45 + 8);
      ExReleaseResourceLite(v46);
      *(_QWORD *)(v14 + 352) = 0;
    }
    v15 = 0;
    v80 = 0;
    while ( v15 < *(unsigned __int16 *)(v14 + 328) )
    {
      v16 = (unsigned __int64)v15 << 6;
      v17 = *(void **)(v16 + *(_QWORD *)(v14 + 96));
      if ( v17 )
      {
        CcUnpinData(v17);
        *(_QWORD *)(v16 + *(_QWORD *)(v14 + 96)) = 0;
      }
      v80 = ++v15;
    }
    v18 = *(void **)(v14 + 16);
    if ( v18 )
    {
      CcUnpinData(v18);
      *(_QWORD *)(v14 + 16) = 0;
    }
    v19 = *(void **)(v14 + 40);
    if ( v19 )
    {
      CcUnpinData(v19);
      *(_QWORD *)(v14 + 40) = 0;
    }
    v20 = *(void **)(v14 + 72);
    if ( v20 )
    {
      CcUnpinData(v20);
      *(_QWORD *)(v14 + 72) = 0;
    }
    memset((void *)v14, 0, 0x58u);
    LOWORD(v21) = 3;
    v22 = a5;
    LODWORD(v12) = v79[0];
  }
  else
  {
    v23 = (char *)ExAllocateFromLookasideListEx(&NtfsIndexContextLookasideList);
    *(_QWORD *)(v11 + 136) = v23;
    memset(v23 + 88, 0, 0x118u);
    memset(v23, 0, 0x58u);
    *((_QWORD *)v23 + 12) = v23 + 112;
    LOWORD(v21) = 3;
    *((_WORD *)v23 + 164) = 3;
    v72 = 1;
    v22 = a5;
    if ( a5 && (*(_DWORD *)(v11 + 4) & 1) == 0 )
      _InterlockedOr((volatile signed __int32 *)(v11 + 4), 1u);
  }
  v24 = *(_QWORD *)(v11 + 136);
  FindFirstIndexEntry(v12, a3, a4, v24);
  LOBYTE(v25) = (*(_DWORD *)(a3 + 512) & 4) != 0
             || ((unsigned __int8 (__fastcall *)(__int64))NtfsContainsWildcards[*(_QWORD *)(a3 + 688)])(a4) != 0;
  v26 = *(_QWORD *)(v11 + 80);
  if ( v26 )
  {
    *(_QWORD *)(v26 + 16) = 0;
    *(_BYTE *)(*(_QWORD *)(v11 + 80) + 48LL) = 1;
    *(_BYTE *)(*(_QWORD *)(v11 + 80) + 49LL) = 1;
  }
  v27 = a6;
  if ( v72 || !a6 )
  {
    if ( (_BYTE)v25 && (*(_DWORD *)(v11 + 4) & 4) == 0 )
      _InterlockedOr((volatile signed __int32 *)(v11 + 4), 4u);
  }
  else
  {
    NextIndexEntry2 = FindNextIndexEntry2(v79[0], a3, (unsigned __int8)v25 | (v22 != 0 ? 2 : 0) | 8u, 0);
    v33 = NextIndexEntry2;
    v76 = NextIndexEntry2;
    if ( NextIndexEntry2 == -1073741536 )
    {
      v21 = *(_QWORD *)v79;
      goto LABEL_107;
    }
    v47 = NextIndexEntry2 >= 0;
    v48 = 0;
    Src = 0;
    if ( NextIndexEntry2 >= 0 )
    {
      v48 = *(_BYTE **)(*(_QWORD *)(v24 + 304) + 24LL);
      Src = v48;
    }
    if ( *(_QWORD *)(v11 + 80) )
      goto LABEL_87;
    v49 = v81;
    while ( v47 )
    {
      if ( v49 == *(_QWORD *)(v11 + 168) + 16LL )
        goto LABEL_72;
      if ( *(_QWORD *)(a3 + 688) != 1 )
        goto LABEL_72;
      v51 = v48[81];
      if ( (unsigned __int8)((v51 & 3) - 1) > 1u )
        goto LABEL_72;
      if ( (v51 & 2) == 0 )
      {
        QueryFileName = NtfsGetQueryFileName(v11, v42, v43, v44);
        if ( v53(UpcaseTable, QueryFileName, v48, a5) )
          goto LABEL_72;
        v48 = Src;
      }
      v81 = *(_QWORD *)v48;
      memset(v89, 0, sizeof(v89));
      v89[12] = &v89[14];
      LOWORD(v89[41]) = v21;
      v73 = 1;
      v21 = *(_QWORD *)v79;
      OtherFileName = NtfsRetrieveOtherFileName(v79[0], v89, v86, (__int64)&v74, 0);
      v25 = OtherFileName;
      v47 = OtherFileName != 0;
      if ( OtherFileName || !v74 )
      {
        if ( !OtherFileName
          || ((v59 = NtfsGetQueryFileName(v11, v55, v56, v57), (*(_DWORD *)(v11 + 4) & 4) == 0)
            ? (IsEqual = NtfsFileNameIsEqual(UpcaseTable))
            : (IsEqual = NtfsFileNameIsInExpression(UpcaseTable, v59, v25, a5)),
              !IsEqual) )
        {
LABEL_72:
          if ( v47 )
          {
LABEL_73:
            v27 = 1;
            goto LABEL_28;
          }
          break;
        }
        NtfsReinitializeIndexContext(v21, v24);
        FindFirstIndexEntry(v21, a3, v25, v24);
        v61 = *(_QWORD *)(v11 + 80);
        if ( v61 )
        {
          *(_QWORD *)(v61 + 16) = 0;
          *(_BYTE *)(*(_QWORD *)(v11 + 80) + 48LL) = 1;
          *(_BYTE *)(*(_QWORD *)(v11 + 80) + 49LL) = 1;
        }
        v62 = FindNextIndexEntry2(v21, a3, 8, 0);
        v33 = v62;
        v76 = v62;
        if ( v62 == -1073741536 )
          goto LABEL_107;
        v63 = v62 >= 0;
        if ( *(_QWORD *)(v11 + 80) )
        {
          Src = 0;
          if ( v62 >= 0 )
            Src = *(void **)(*(_QWORD *)(v24 + 304) + 24LL);
          ExAcquireResourceSharedLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(a3 + 528) + 64LL) + 136LL), 1u);
          LOBYTE(v70) = 0;
          v63 = TxfFilterDirectoryQuery(
                  v21,
                  *(_QWORD *)(v21 + 400),
                  *(_QWORD *)(a3 + 528),
                  v11,
                  v25,
                  v70,
                  0,
                  0,
                  (__int64)&Src,
                  (__int64)&v78,
                  v83);
          ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(a3 + 528) + 64LL) + 136LL));
        }
        if ( v63 )
          goto LABEL_73;
      }
      else
      {
        NtfsRaiseStatusInternal(v21, -1073741608, 0, 0, 1313100);
      }
      v11 = 0x114001409BBLL;
      NtfsAttachCorruption_Connect(
        v21,
        *(_DWORD *)(a3 + 184) + 8,
        1313211,
        v58,
        *(_QWORD *)(a3 + 184) + 8LL,
        v70,
        *(_DWORD *)(a3 + 256),
        *(_WORD *)(a3 + 264) >> 1,
        *(void **)(a3 + 272),
        *(_QWORD *)(a3 + 184) + 8LL,
        v71,
        (__int64)&v81);
      NtfsAttachRepairInfoPriv(v21, 0, 0, 0x114001409BBLL);
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v21, 3221225730LL, 1313211);
      NtfsRaiseStatusInternal(v21, -1073741566, *(_QWORD *)(a3 + 184) + 8, *(_QWORD *)(a3 + 184), 1313211);
LABEL_87:
      ExAcquireResourceSharedLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(a3 + 528) + 64LL) + 136LL), 1u);
      LOBYTE(v69) = v25;
      v49 = v81;
      v47 = (unsigned __int8)TxfFilterDirectoryQuery(
                               v79[0],
                               *(_QWORD *)(*(_QWORD *)v79 + 400LL),
                               *(_QWORD *)(a3 + 528),
                               v11,
                               v81,
                               v69,
                               a5,
                               0,
                               (__int64)&Src,
                               (__int64)&v78,
                               v83)
         && !(_DWORD)v78;
      ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(a3 + 528) + 64LL) + 136LL));
      v48 = Src;
    }
    v27 = 0;
  }
LABEL_28:
  LODWORD(v78) = 0;
  v21 = *(_QWORD *)v79;
  v28 = v83;
  while ( 1 )
  {
    v29 = 0;
    v75 = 0;
    if ( v27 )
    {
      v50 = *(_QWORD *)(v11 + 80);
      if ( v50 )
      {
        v27 = *(_BYTE *)(v50 + 48);
        v29 = *(_BYTE *)(v50 + 49);
        v75 = v29;
      }
    }
    v30 = *(_DWORD *)(v11 + 4);
    if ( (v30 & 1) != 0 && ((v30 & 0x4000000) != 0 || (*(_DWORD *)(*(_QWORD *)(a3 + 184) + 16LL) & 0x400) == 0) )
      v31 = 2;
    else
      v31 = 0;
    v32 = FindNextIndexEntry2(
            v21,
            a3,
            v31 | (v27 != 0 ? 4 : 0) | ((unsigned int)((*(_DWORD *)(v11 + 4) & 4) != 0) + 8),
            0);
    v33 = v32;
    v76 = v32;
    if ( v32 == -1073741536 )
      break;
    v34 = v32 >= 0;
    v35 = 0;
    Src = 0;
    if ( v32 >= 0 )
    {
      v35 = *(unsigned __int16 **)(*(_QWORD *)(v24 + 304) + 24LL);
      Src = v35;
    }
    if ( *(_QWORD *)(v11 + 80) )
    {
      ExAcquireResourceSharedLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(a3 + 528) + 64LL) + 136LL), 1u);
      v38 = *(_DWORD *)(v11 + 4);
      v39 = (v38 & 1) != 0 && ((v38 & 0x4000000) != 0 || (*(_DWORD *)(*(_QWORD *)(a3 + 184) + 16LL) & 0x400) == 0);
      if ( (v38 & 0x1000000) != 0 )
        v40 = 0;
      else
        v40 = *(_QWORD *)(v11 + 152);
      LOBYTE(v68) = (*(_DWORD *)(v11 + 4) & 4) != 0;
      v34 = TxfFilterDirectoryQuery(
              v21,
              *(_QWORD *)(v21 + 400),
              *(_QWORD *)(a3 + 528),
              v11,
              v40,
              v68,
              v39,
              v29,
              (__int64)&Src,
              (__int64)&v78,
              v28);
      ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(a3 + 528) + 64LL) + 136LL));
      v35 = (unsigned __int16 *)Src;
    }
    v27 = 1;
    if ( !(_DWORD)v78 )
    {
      if ( v34 )
      {
        if ( *(_DWORD *)(v11 + 160) < (unsigned int)v35[4] )
        {
          v36 = *(void **)(v11 + 168);
          if ( v36 )
          {
            ExFreePoolWithTag(v36, 0);
            *(_QWORD *)(v11 + 168) = 0;
            *(_DWORD *)(v11 + 160) = 0;
            v35 = (unsigned __int16 *)Src;
          }
          *(_QWORD *)(v11 + 168) = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v35[4] + 16LL, 0x4946744Eu);
          v35 = (unsigned __int16 *)Src;
          *(_DWORD *)(v11 + 160) = *((unsigned __int16 *)Src + 4) + 16;
        }
        v37 = *(unsigned __int16 **)(v11 + 168);
        if ( v35 != v37 )
        {
          memmove(v37, v35, v35[4]);
          *(_WORD *)(*(_QWORD *)(v11 + 168) + 4LL) = 0;
        }
        *v87 = *(_QWORD *)(v11 + 168);
        v33 = 0;
        v76 = 0;
      }
      else
      {
        v33 = -1073741275;
        v76 = -1073741275;
      }
      break;
    }
  }
LABEL_107:
  if ( v73 )
    NtfsCleanupIndexContext(v21, v89);
  if ( v33 == -1073741536 && v72 )
  {
    v66 = *(void **)(v11 + 168);
    if ( v66 )
    {
      ExFreePoolWithTag(v66, 0);
      *(_QWORD *)(v11 + 168) = 0;
    }
    v67 = *(_QWORD *)(v11 + 136);
    if ( v67 )
    {
      NtfsCleanupIndexContext(v21, v67);
      ExFreeToLookasideListEx(&NtfsIndexContextLookasideList, *(PVOID *)(v11 + 136));
      *(_QWORD *)(v11 + 136) = 0;
    }
  }
  if ( v33 < 0 )
  {
    v65 = *(_QWORD *)(v11 + 168);
    if ( v65 )
      *(_WORD *)(v65 + 8) = 0;
  }
  return (unsigned int)v33;
}

```

## disassembly

```asm
0x1401209b0  push    rbx
0x1401209b2  push    rsi
0x1401209b3  push    rdi
0x1401209b4  push    r12
0x1401209b6  push    r13
0x1401209b8  push    r14
0x1401209ba  push    r15
0x1401209bc  sub     rsp, 250h
0x1401209c3  mov     rax, cs:__security_cookie
0x1401209ca  xor     rax, rsp
0x1401209cd  mov     [rsp+288h+var_48], rax
0x1401209d5  mov     r12, r9
0x1401209d8  mov     [rsp+288h+var_1F8], r9
0x1401209e0  mov     r15, r8
0x1401209e3  mov     rbx, rdx
0x1401209e6  mov     rsi, rcx
0x1401209e9  mov     qword ptr [rsp+288h+var_208], rcx
0x1401209f1  mov     [rsp+288h+var_1E0], rcx
0x1401209f9  mov     [rsp+288h+var_1D8], rdx
0x140120a01  mov     [rsp+288h+var_1C0], r8
0x140120a09  mov     rax, [rsp+288h+arg_30]
0x140120a11  mov     [rsp+288h+var_1C8], rax
0x140120a19  mov     rax, [rsp+288h+arg_38]
0x140120a21  mov     [rsp+288h+var_1D0], rax
0x140120a29  mov     rax, [rsp+288h+arg_40]
0x140120a31  mov     [rsp+288h+var_1E8], rax
0x140120a39  xor     r13d, r13d
0x140120a3c  mov     [rsp+288h+Src], r13
0x140120a41  xor     edx, edx; Val
0x140120a43  mov     r8d, 170h; Size
0x140120a49  lea     rcx, [rsp+288h+var_1B8]; void *
0x140120a51  call    memset
0x140120a56  mov     dword ptr [rsp+288h+var_210], r13d
0x140120a5b  mov     [rsp+288h+var_224], r13b
0x140120a60  mov     rcx, [rsi+68h]
0x140120a64  mov     rax, [rcx+310h]
0x140120a6b  mov     [rsp+288h+UpcaseTable], rax
0x140120a73  mov     [rsp+288h+var_220], 0C0000225h
0x140120a7b  mov     [rsp+288h+var_225], r13b
0x140120a80  mov     [rsp+288h+var_226], r13b
0x140120a85  mov     [rsp+288h+var_228], r13b
0x140120a8a  mov     rdi, [rbx+88h]
0x140120a91  test    rdi, rdi
0x140120a94  jz      loc_140120B96
0x140120a9a  mov     [rsp+288h+var_200], r13d
0x140120aa2  test    byte ptr [rdi+14Ah], 1
0x140120aa9  jz      short loc_140120ACC
0x140120aab  add     rcx, 290h
0x140120ab2  xor     edx, edx
0x140120ab4  call    cs:__imp_ExReleasePushLockEx
0x140120abb  nop     dword ptr [rax+rax+00h]
0x140120ac0  mov     eax, 0FFFEh
0x140120ac5  and     [rdi+14Ah], ax
0x140120acc  cmp     qword ptr [rdi+160h], 0
0x140120ad4  jnz     loc_140120F79
0x140120ada  mov     esi, r13d
0x140120add  mov     [rsp+288h+var_200], r13d
0x140120ae5  movzx   eax, word ptr [rdi+148h]
0x140120aec  cmp     esi, eax
0x140120aee  jnb     short loc_140120B23
0x140120af0  mov     r14d, esi
0x140120af3  shl     r14, 6
0x140120af7  mov     rax, [rdi+60h]
0x140120afb  mov     rcx, [r14+rax]; Bcb
0x140120aff  test    rcx, rcx
0x140120b02  jz      short loc_140120B18
0x140120b04  call    cs:__imp_CcUnpinData
0x140120b0b  nop     dword ptr [rax+rax+00h]
0x140120b10  mov     rax, [rdi+60h]
0x140120b14  mov     [r14+rax], r13
0x140120b18  inc     esi
0x140120b1a  mov     [rsp+288h+var_200], esi
0x140120b21  jmp     short loc_140120AE5
0x140120b23  mov     rcx, [rdi+10h]; Bcb
0x140120b27  test    rcx, rcx
0x140120b2a  jz      short loc_140120B3C
0x140120b2c  call    cs:__imp_CcUnpinData
0x140120b33  nop     dword ptr [rax+rax+00h]
0x140120b38  mov     [rdi+10h], r13
0x140120b3c  mov     rcx, [rdi+28h]; Bcb
0x140120b40  test    rcx, rcx
0x140120b43  jz      short loc_140120B55
0x140120b45  call    cs:__imp_CcUnpinData
0x140120b4c  nop     dword ptr [rax+rax+00h]
0x140120b51  mov     [rdi+28h], r13
0x140120b55  mov     rcx, [rdi+48h]; Bcb
0x140120b59  test    rcx, rcx
0x140120b5c  jz      short loc_140120B6E
0x140120b5e  call    cs:__imp_CcUnpinData
0x140120b65  nop     dword ptr [rax+rax+00h]
0x140120b6a  mov     [rdi+48h], r13
0x140120b6e  xor     edx, edx; Val
0x140120b70  mov     r8d, 58h ; 'X'; Size
0x140120b76  mov     rcx, rdi; void *
0x140120b79  call    memset
0x140120b7e  mov     r14d, 3
0x140120b84  movzx   edi, [rsp+288h+arg_20]
0x140120b8c  mov     rsi, qword ptr [rsp+288h+var_208]
0x140120b94  jmp     short loc_140120C08
0x140120b96  lea     rcx, NtfsIndexContextLookasideList; Lookaside
0x140120b9d  call    cs:__imp_ExAllocateFromLookasideListEx
0x140120ba4  nop     dword ptr [rax+rax+00h]
0x140120ba9  mov     rdi, rax
0x140120bac  mov     [rbx+88h], rax
0x140120bb3  lea     rcx, [rax+58h]; void *
0x140120bb7  xor     edx, edx; Val
0x140120bb9  mov     r8d, 118h; Size
0x140120bbf  call    memset
0x140120bc4  xor     edx, edx; Val
0x140120bc6  mov     r8d, 58h ; 'X'; Size
0x140120bcc  mov     rcx, rdi; void *
0x140120bcf  call    memset
0x140120bd4  lea     rcx, [rdi+70h]
0x140120bd8  mov     [rdi+60h], rcx
0x140120bdc  mov     r14d, 3
0x140120be2  mov     [rdi+148h], r14w
0x140120bea  mov     [rsp+288h+var_226], 1
0x140120bef  movzx   edi, [rsp+288h+arg_20]
0x140120bf7  test    dil, dil
0x140120bfa  jz      short loc_140120C08
0x140120bfc  mov     eax, [rbx+4]
0x140120bff  test    al, 1
0x140120c01  jnz     short loc_140120C08
0x140120c03  lock or dword ptr [rbx+4], 1
0x140120c08  mov     r13, [rbx+88h]
0x140120c0f  mov     r9, r13; __int64
0x140120c12  mov     r8, r12; int
0x140120c15  mov     rdx, r15; int
0x140120c18  mov     rcx, rsi; int
0x140120c1b  call    FindFirstIndexEntry
0x140120c20  mov     eax, [r15+200h]
0x140120c27  test    al, 4
0x140120c29  jnz     loc_140120F05
0x140120c2f  mov     rax, [r15+2B0h]
0x140120c36  lea     rcx, NtfsContainsWildcards
0x140120c3d  mov     rax, ds:(NtfsContainsWildcards - 140062000h)[rcx+rax*8]
0x140120c41  mov     rcx, r12
0x140120c44  call    _guard_dispatch_icall
0x140120c49  test    al, al
0x140120c4b  setnz   sil
0x140120c4f  mov     rax, [rbx+50h]
0x140120c53  test    rax, rax
0x140120c56  jz      short loc_140120C70
0x140120c58  mov     qword ptr [rax+10h], 0
0x140120c60  mov     rax, [rbx+50h]
0x140120c64  mov     byte ptr [rax+30h], 1
0x140120c68  mov     rax, [rbx+50h]
0x140120c6c  mov     byte ptr [rax+31h], 1
0x140120c70  movzx   r8d, [rsp+288h+arg_28]
0x140120c79  cmp     [rsp+288h+var_226], 0
0x140120c7e  jz      loc_140120F0D
0x140120c84  test    sil, sil
0x140120c87  jz      short loc_140120C95
0x140120c89  mov     eax, [rbx+4]
0x140120c8c  test    al, 4
0x140120c8e  jnz     short loc_140120C95
0x140120c90  lock or dword ptr [rbx+4], 4
0x140120c95  mov     dword ptr [rsp+288h+var_210], 0
0x140120c9d  mov     [rsp+288h+var_228], 0
0x140120ca2  mov     r14, qword ptr [rsp+288h+var_208]
0x140120caa  mov     r12, [rsp+288h+var_1E8]
0x140120cb2  xor     sil, sil
0x140120cb5  mov     [rsp+288h+var_223], sil
0x140120cba  test    r8b, r8b
0x140120cbd  jnz     loc_1401210A1
0x140120cc3  mov     edx, [rbx+4]
0x140120cc6  mov     r9d, edx
0x140120cc9  and     r9d, 4
0x140120ccd  test    dl, 1
0x140120cd0  jz      loc_140120E34
0x140120cd6  bt      edx, 1Ah
0x140120cda  jb      short loc_140120CF0
0x140120cdc  mov     rax, [r15+0B8h]
0x140120ce3  test    dword ptr [rax+10h], 400h
0x140120cea  jnz     loc_140120E34
0x140120cf0  mov     r10d, 2
0x140120cf6  neg     r8b
0x140120cf9  sbb     ecx, ecx
0x140120cfb  and     ecx, 4
0x140120cfe  bt      edx, 18h
0x140120d02  jb      loc_14012100F
0x140120d08  mov     r8, [rbx+98h]
0x140120d0f  xor     eax, eax
0x140120d11  test    r9d, r9d
0x140120d14  setnz   al
0x140120d17  add     eax, 8
0x140120d1a  or      eax, ecx
0x140120d1c  or      eax, r10d
0x140120d1f  mov     [rsp+288h+var_260], 0; __int64
0x140120d28  mov     dword ptr [rsp+288h+var_268], eax; int
0x140120d2c  mov     r9, r13
0x140120d2f  mov     rdx, r15; __int64
0x140120d32  mov     rcx, r14; int
0x140120d35  call    FindNextIndexEntry2
0x140120d3a  mov     edi, eax
0x140120d3c  mov     [rsp+288h+var_220], eax
0x140120d40  cmp     eax, 0C0000120h
0x140120d45  jz      loc_140121545
0x140120d4b  test    eax, eax
0x140120d4d  setns   dil
0x140120d51  mov     [rsp+288h+var_227], dil
0x140120d56  xor     edx, edx
0x140120d58  mov     [rsp+288h+Src], rdx
0x140120d5d  test    dil, dil
0x140120d60  jz      short loc_140120D72
0x140120d62  mov     rax, [r13+130h]
0x140120d69  mov     rdx, [rax+18h]
0x140120d6d  mov     [rsp+288h+Src], rdx
0x140120d72  cmp     qword ptr [rbx+50h], 0
0x140120d77  jnz     loc_140120E3C
0x140120d7d  mov     r8b, 1
0x140120d80  mov     [rsp+288h+arg_28], r8b
0x140120d88  cmp     dword ptr [rsp+288h+var_210], 0
0x140120d8d  jnz     loc_140120CB2
0x140120d93  test    dil, dil
0x140120d96  jz      loc_140120F6B
0x140120d9c  movzx   eax, word ptr [rdx+8]
0x140120da0  cmp     [rbx+0A0h], eax
0x140120da6  jnb     short loc_140120DF4
0x140120da8  mov     rcx, [rbx+0A8h]; P
0x140120daf  test    rcx, rcx
0x140120db2  jnz     loc_140121518
0x140120db8  movzx   edx, word ptr [rdx+8]
0x140120dbc  add     rdx, 10h; NumberOfBytes
0x140120dc0  mov     ecx, cs:PoolType
0x140120dc6  or      ecx, 10h; PoolType
0x140120dc9  mov     r8d, 4946744Eh; Tag
0x140120dcf  call    cs:__imp_ExAllocatePoolWithTag
0x140120dd6  nop     dword ptr [rax+rax+00h]
0x140120ddb  mov     [rbx+0A8h], rax
0x140120de2  mov     rdx, [rsp+288h+Src]; Src
0x140120de7  movzx   eax, word ptr [rdx+8]
0x140120deb  add     eax, 10h
0x140120dee  mov     [rbx+0A0h], eax
0x140120df4  mov     rcx, [rbx+0A8h]; void *
0x140120dfb  cmp     rdx, rcx
0x140120dfe  jz      short loc_140120E17
0x140120e00  movzx   r8d, word ptr [rdx+8]; Size
0x140120e05  call    memmove
0x140120e0a  mov     rcx, [rbx+0A8h]
0x140120e11  xor     eax, eax
0x140120e13  mov     [rcx+4], ax
0x140120e17  mov     rax, [rbx+0A8h]
0x140120e1e  mov     rcx, [rsp+288h+var_1C8]
0x140120e26  mov     [rcx], rax
0x140120e29  xor     edi, edi
0x140120e2b  mov     [rsp+288h+var_220], edi
0x140120e2f  jmp     loc_140121545
0x140120e34  xor     r10d, r10d
0x140120e37  jmp     loc_140120CF6
0x140120e3c  mov     rax, [r15+210h]
0x140120e43  mov     rcx, [rax+40h]
0x140120e47  mov     dl, 1; Wait
0x140120e49  mov     rcx, [rcx+88h]; Resource
0x140120e50  call    cs:__imp_ExAcquireResourceSharedLite
0x140120e57  nop     dword ptr [rax+rax+00h]
0x140120e5c  mov     [rsp+288h+var_228], 1
0x140120e61  mov     edx, [rbx+4]
0x140120e64  test    dl, 1
0x140120e67  jnz     loc_140120FE7
0x140120e6d  xor     r8b, r8b
0x140120e70  mov     ecx, edx
0x140120e72  shr     ecx, 2
0x140120e75  and     cl, 1
0x140120e78  bt      edx, 18h
0x140120e7c  jb      loc_140121017
0x140120e82  mov     rdx, [rbx+98h]
0x140120e89  movzx   eax, sil
0x140120e8d  mov     [rsp+288h+var_238], r12; __int64
0x140120e92  lea     r9, [rsp+288h+var_210]
0x140120e97  mov     [rsp+288h+var_240], r9; __int64
0x140120e9c  lea     r9, [rsp+288h+Src]
0x140120ea1  mov     [rsp+288h+var_248], r9; __int64
0x140120ea6  mov     [rsp+288h+NextFlag], eax; NextFlag
0x140120eaa  mov     [rsp+288h+var_258], r8b; char
0x140120eaf  mov     byte ptr [rsp+288h+var_260], cl; int
0x140120eb3  mov     [rsp+288h+var_268], rdx; __int64
0x140120eb8  mov     r9, rbx; int
0x140120ebb  mov     r8, [r15+210h]; int
0x140120ec2  mov     rdx, [r14+190h]; int
0x140120ec9  mov     rcx, r14; int
0x140120ecc  call    TxfFilterDirectoryQuery
0x140120ed1  movzx   edi, al
0x140120ed4  mov     [rsp+288h+var_227], al
0x140120ed8  mov     rcx, [r15+210h]
0x140120edf  mov     rcx, [rcx+40h]
0x140120ee3  mov     rcx, [rcx+88h]; Resource
0x140120eea  call    cs:__imp_ExReleaseResourceLite
0x140120ef1  nop     dword ptr [rax+rax+00h]
0x140120ef6  mov     [rsp+288h+var_228], 0
0x140120efb  mov     rdx, [rsp+288h+Src]
0x140120f00  jmp     loc_140120D7D
0x140120f05  mov     sil, 1
0x140120f08  jmp     loc_140120C4F
0x140120f0d  test    r8b, r8b
0x140120f10  jz      loc_140120C84
0x140120f16  movzx   eax, dil
0x140120f1a  neg     al
0x140120f1c  sbb     ecx, ecx
0x140120f1e  and     ecx, 2
  ... truncated ...
```
