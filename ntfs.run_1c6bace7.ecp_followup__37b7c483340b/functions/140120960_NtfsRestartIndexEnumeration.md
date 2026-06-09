# NtfsRestartIndexEnumeration

- ea: `0x140120960`
- end: `0x140121589`
- name: `NtfsRestartIndexEnumeration`
- size: `3113`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140122300`
- `0x1401a7b00`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x140027f50`
- `0x1400410a8`
- `0x140059250`
- `0x140059370`
- `0x1400593c0`
- `0x1400596c0`
- `0x1400c8420`
- `0x14011fe00`
- `0x140120960`
- `0x140121a00`
- `0x140122730`
- `0x140124440`
- `0x14013252c`
- `0x140153910`
- `0x140153ab0`
- `0x140214360`
- `0x1402239ec`
- `0x14023b8a0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140120f36`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140120f36`
- `ntoskrnl!ExReleasePushLockEx` at `0x140120a64`
- `ntoskrnl!ExReleasePushLockEx` at `0x140120f5a`
- `ntoskrnl!ExReleasePushLockEx` at `0x140120a64`
- `ntoskrnl!ExReleasePushLockEx` at `0x140120f5a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402a57d2`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c7376`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402a57d2`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c7376`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140120b4d`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140120b4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401214ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012156d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a5794`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401214ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012156d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a5794`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140120d7f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140120d7f`
- `ntoskrnl!CcUnpinData` at `0x140120ab4`
- `ntoskrnl!CcUnpinData` at `0x140120adc`
- `ntoskrnl!CcUnpinData` at `0x140120af5`
- `ntoskrnl!CcUnpinData` at `0x140120b0e`
- `ntoskrnl!CcUnpinData` at `0x140120ab4`
- `ntoskrnl!CcUnpinData` at `0x140120adc`
- `ntoskrnl!CcUnpinData` at `0x140120af5`
- `ntoskrnl!CcUnpinData` at `0x140120b0e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140120e9a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140120f7f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012130f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401214a1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a5739`
- `ntoskrnl!ExReleaseResourceLite` at `0x140120e9a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140120f7f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012130f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401214a1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a5739`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140120e00`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14012126c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140121426`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140120e00`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14012126c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140121426`

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
0x140120960  push    rbx
0x140120962  push    rsi
0x140120963  push    rdi
0x140120964  push    r12
0x140120966  push    r13
0x140120968  push    r14
0x14012096a  push    r15
0x14012096c  sub     rsp, 250h
0x140120973  mov     rax, cs:__security_cookie
0x14012097a  xor     rax, rsp
0x14012097d  mov     [rsp+288h+var_48], rax
0x140120985  mov     r12, r9
0x140120988  mov     [rsp+288h+var_1F8], r9
0x140120990  mov     r15, r8
0x140120993  mov     rbx, rdx
0x140120996  mov     rsi, rcx
0x140120999  mov     qword ptr [rsp+288h+var_208], rcx
0x1401209a1  mov     [rsp+288h+var_1E0], rcx
0x1401209a9  mov     [rsp+288h+var_1D8], rdx
0x1401209b1  mov     [rsp+288h+var_1C0], r8
0x1401209b9  mov     rax, [rsp+288h+arg_30]
0x1401209c1  mov     [rsp+288h+var_1C8], rax
0x1401209c9  mov     rax, [rsp+288h+arg_38]
0x1401209d1  mov     [rsp+288h+var_1D0], rax
0x1401209d9  mov     rax, [rsp+288h+arg_40]
0x1401209e1  mov     [rsp+288h+var_1E8], rax
0x1401209e9  xor     r13d, r13d
0x1401209ec  mov     [rsp+288h+Src], r13
0x1401209f1  xor     edx, edx; Val
0x1401209f3  mov     r8d, 170h; Size
0x1401209f9  lea     rcx, [rsp+288h+var_1B8]; void *
0x140120a01  call    memset
0x140120a06  mov     dword ptr [rsp+288h+var_210], r13d
0x140120a0b  mov     [rsp+288h+var_224], r13b
0x140120a10  mov     rcx, [rsi+68h]
0x140120a14  mov     rax, [rcx+310h]
0x140120a1b  mov     [rsp+288h+UpcaseTable], rax
0x140120a23  mov     [rsp+288h+var_220], 0C0000225h
0x140120a2b  mov     [rsp+288h+var_225], r13b
0x140120a30  mov     [rsp+288h+var_226], r13b
0x140120a35  mov     [rsp+288h+var_228], r13b
0x140120a3a  mov     rdi, [rbx+88h]
0x140120a41  test    rdi, rdi
0x140120a44  jz      loc_140120B46
0x140120a4a  mov     [rsp+288h+var_200], r13d
0x140120a52  test    byte ptr [rdi+14Ah], 1
0x140120a59  jz      short loc_140120A7C
0x140120a5b  add     rcx, 290h
0x140120a62  xor     edx, edx
0x140120a64  call    cs:__imp_ExReleasePushLockEx
0x140120a6b  nop     dword ptr [rax+rax+00h]
0x140120a70  mov     eax, 0FFFEh
0x140120a75  and     [rdi+14Ah], ax
0x140120a7c  cmp     qword ptr [rdi+160h], 0
0x140120a84  jnz     loc_140120F29
0x140120a8a  mov     esi, r13d
0x140120a8d  mov     [rsp+288h+var_200], r13d
0x140120a95  movzx   eax, word ptr [rdi+148h]
0x140120a9c  cmp     esi, eax
0x140120a9e  jnb     short loc_140120AD3
0x140120aa0  mov     r14d, esi
0x140120aa3  shl     r14, 6
0x140120aa7  mov     rax, [rdi+60h]
0x140120aab  mov     rcx, [r14+rax]; Bcb
0x140120aaf  test    rcx, rcx
0x140120ab2  jz      short loc_140120AC8
0x140120ab4  call    cs:__imp_CcUnpinData
0x140120abb  nop     dword ptr [rax+rax+00h]
0x140120ac0  mov     rax, [rdi+60h]
0x140120ac4  mov     [r14+rax], r13
0x140120ac8  inc     esi
0x140120aca  mov     [rsp+288h+var_200], esi
0x140120ad1  jmp     short loc_140120A95
0x140120ad3  mov     rcx, [rdi+10h]; Bcb
0x140120ad7  test    rcx, rcx
0x140120ada  jz      short loc_140120AEC
0x140120adc  call    cs:__imp_CcUnpinData
0x140120ae3  nop     dword ptr [rax+rax+00h]
0x140120ae8  mov     [rdi+10h], r13
0x140120aec  mov     rcx, [rdi+28h]; Bcb
0x140120af0  test    rcx, rcx
0x140120af3  jz      short loc_140120B05
0x140120af5  call    cs:__imp_CcUnpinData
0x140120afc  nop     dword ptr [rax+rax+00h]
0x140120b01  mov     [rdi+28h], r13
0x140120b05  mov     rcx, [rdi+48h]; Bcb
0x140120b09  test    rcx, rcx
0x140120b0c  jz      short loc_140120B1E
0x140120b0e  call    cs:__imp_CcUnpinData
0x140120b15  nop     dword ptr [rax+rax+00h]
0x140120b1a  mov     [rdi+48h], r13
0x140120b1e  xor     edx, edx; Val
0x140120b20  mov     r8d, 58h ; 'X'; Size
0x140120b26  mov     rcx, rdi; void *
0x140120b29  call    memset
0x140120b2e  mov     r14d, 3
0x140120b34  movzx   edi, [rsp+288h+arg_20]
0x140120b3c  mov     rsi, qword ptr [rsp+288h+var_208]
0x140120b44  jmp     short loc_140120BB8
0x140120b46  lea     rcx, NtfsIndexContextLookasideList; Lookaside
0x140120b4d  call    cs:__imp_ExAllocateFromLookasideListEx
0x140120b54  nop     dword ptr [rax+rax+00h]
0x140120b59  mov     rdi, rax
0x140120b5c  mov     [rbx+88h], rax
0x140120b63  lea     rcx, [rax+58h]; void *
0x140120b67  xor     edx, edx; Val
0x140120b69  mov     r8d, 118h; Size
0x140120b6f  call    memset
0x140120b74  xor     edx, edx; Val
0x140120b76  mov     r8d, 58h ; 'X'; Size
0x140120b7c  mov     rcx, rdi; void *
0x140120b7f  call    memset
0x140120b84  lea     rcx, [rdi+70h]
0x140120b88  mov     [rdi+60h], rcx
0x140120b8c  mov     r14d, 3
0x140120b92  mov     [rdi+148h], r14w
0x140120b9a  mov     [rsp+288h+var_226], 1
0x140120b9f  movzx   edi, [rsp+288h+arg_20]
0x140120ba7  test    dil, dil
0x140120baa  jz      short loc_140120BB8
0x140120bac  mov     eax, [rbx+4]
0x140120baf  test    al, 1
0x140120bb1  jnz     short loc_140120BB8
0x140120bb3  lock or dword ptr [rbx+4], 1
0x140120bb8  mov     r13, [rbx+88h]
0x140120bbf  mov     r9, r13; __int64
0x140120bc2  mov     r8, r12; int
0x140120bc5  mov     rdx, r15; int
0x140120bc8  mov     rcx, rsi; int
0x140120bcb  call    FindFirstIndexEntry
0x140120bd0  mov     eax, [r15+200h]
0x140120bd7  test    al, 4
0x140120bd9  jnz     loc_140120EB5
0x140120bdf  mov     rax, [r15+2B0h]
0x140120be6  lea     rcx, NtfsContainsWildcards
0x140120bed  mov     rax, ds:(NtfsContainsWildcards - 140062000h)[rcx+rax*8]
0x140120bf1  mov     rcx, r12
0x140120bf4  call    _guard_dispatch_icall
0x140120bf9  test    al, al
0x140120bfb  setnz   sil
0x140120bff  mov     rax, [rbx+50h]
0x140120c03  test    rax, rax
0x140120c06  jz      short loc_140120C20
0x140120c08  mov     qword ptr [rax+10h], 0
0x140120c10  mov     rax, [rbx+50h]
0x140120c14  mov     byte ptr [rax+30h], 1
0x140120c18  mov     rax, [rbx+50h]
0x140120c1c  mov     byte ptr [rax+31h], 1
0x140120c20  movzx   r8d, [rsp+288h+arg_28]
0x140120c29  cmp     [rsp+288h+var_226], 0
0x140120c2e  jz      loc_140120EBD
0x140120c34  test    sil, sil
0x140120c37  jz      short loc_140120C45
0x140120c39  mov     eax, [rbx+4]
0x140120c3c  test    al, 4
0x140120c3e  jnz     short loc_140120C45
0x140120c40  lock or dword ptr [rbx+4], 4
0x140120c45  mov     dword ptr [rsp+288h+var_210], 0
0x140120c4d  mov     [rsp+288h+var_228], 0
0x140120c52  mov     r14, qword ptr [rsp+288h+var_208]
0x140120c5a  mov     r12, [rsp+288h+var_1E8]
0x140120c62  xor     sil, sil
0x140120c65  mov     [rsp+288h+var_223], sil
0x140120c6a  test    r8b, r8b
0x140120c6d  jnz     loc_140121051
0x140120c73  mov     edx, [rbx+4]
0x140120c76  mov     r9d, edx
0x140120c79  and     r9d, 4
0x140120c7d  test    dl, 1
0x140120c80  jz      loc_140120DE4
0x140120c86  bt      edx, 1Ah
0x140120c8a  jb      short loc_140120CA0
0x140120c8c  mov     rax, [r15+0B8h]
0x140120c93  test    dword ptr [rax+10h], 400h
0x140120c9a  jnz     loc_140120DE4
0x140120ca0  mov     r10d, 2
0x140120ca6  neg     r8b
0x140120ca9  sbb     ecx, ecx
0x140120cab  and     ecx, 4
0x140120cae  bt      edx, 18h
0x140120cb2  jb      loc_140120FBF
0x140120cb8  mov     r8, [rbx+98h]
0x140120cbf  xor     eax, eax
0x140120cc1  test    r9d, r9d
0x140120cc4  setnz   al
0x140120cc7  add     eax, 8
0x140120cca  or      eax, ecx
0x140120ccc  or      eax, r10d
0x140120ccf  mov     [rsp+288h+var_260], 0; __int64
0x140120cd8  mov     dword ptr [rsp+288h+var_268], eax; int
0x140120cdc  mov     r9, r13
0x140120cdf  mov     rdx, r15; __int64
0x140120ce2  mov     rcx, r14; int
0x140120ce5  call    FindNextIndexEntry2
0x140120cea  mov     edi, eax
0x140120cec  mov     [rsp+288h+var_220], eax
0x140120cf0  cmp     eax, 0C0000120h
0x140120cf5  jz      loc_1401214F5
0x140120cfb  test    eax, eax
0x140120cfd  setns   dil
0x140120d01  mov     [rsp+288h+var_227], dil
0x140120d06  xor     edx, edx
0x140120d08  mov     [rsp+288h+Src], rdx
0x140120d0d  test    dil, dil
0x140120d10  jz      short loc_140120D22
0x140120d12  mov     rax, [r13+130h]
0x140120d19  mov     rdx, [rax+18h]
0x140120d1d  mov     [rsp+288h+Src], rdx
0x140120d22  cmp     qword ptr [rbx+50h], 0
0x140120d27  jnz     loc_140120DEC
0x140120d2d  mov     r8b, 1
0x140120d30  mov     [rsp+288h+arg_28], r8b
0x140120d38  cmp     dword ptr [rsp+288h+var_210], 0
0x140120d3d  jnz     loc_140120C62
0x140120d43  test    dil, dil
0x140120d46  jz      loc_140120F1B
0x140120d4c  movzx   eax, word ptr [rdx+8]
0x140120d50  cmp     [rbx+0A0h], eax
0x140120d56  jnb     short loc_140120DA4
0x140120d58  mov     rcx, [rbx+0A8h]; P
0x140120d5f  test    rcx, rcx
0x140120d62  jnz     loc_1401214C8
0x140120d68  movzx   edx, word ptr [rdx+8]
0x140120d6c  add     rdx, 10h; NumberOfBytes
0x140120d70  mov     ecx, cs:PoolType
0x140120d76  or      ecx, 10h; PoolType
0x140120d79  mov     r8d, 4946744Eh; Tag
0x140120d7f  call    cs:__imp_ExAllocatePoolWithTag
0x140120d86  nop     dword ptr [rax+rax+00h]
0x140120d8b  mov     [rbx+0A8h], rax
0x140120d92  mov     rdx, [rsp+288h+Src]; Src
0x140120d97  movzx   eax, word ptr [rdx+8]
0x140120d9b  add     eax, 10h
0x140120d9e  mov     [rbx+0A0h], eax
0x140120da4  mov     rcx, [rbx+0A8h]; void *
0x140120dab  cmp     rdx, rcx
0x140120dae  jz      short loc_140120DC7
0x140120db0  movzx   r8d, word ptr [rdx+8]; Size
0x140120db5  call    memmove
0x140120dba  mov     rcx, [rbx+0A8h]
0x140120dc1  xor     eax, eax
0x140120dc3  mov     [rcx+4], ax
0x140120dc7  mov     rax, [rbx+0A8h]
0x140120dce  mov     rcx, [rsp+288h+var_1C8]
0x140120dd6  mov     [rcx], rax
0x140120dd9  xor     edi, edi
0x140120ddb  mov     [rsp+288h+var_220], edi
0x140120ddf  jmp     loc_1401214F5
0x140120de4  xor     r10d, r10d
0x140120de7  jmp     loc_140120CA6
0x140120dec  mov     rax, [r15+210h]
0x140120df3  mov     rcx, [rax+40h]
0x140120df7  mov     dl, 1; Wait
0x140120df9  mov     rcx, [rcx+88h]; Resource
0x140120e00  call    cs:__imp_ExAcquireResourceSharedLite
0x140120e07  nop     dword ptr [rax+rax+00h]
0x140120e0c  mov     [rsp+288h+var_228], 1
0x140120e11  mov     edx, [rbx+4]
0x140120e14  test    dl, 1
0x140120e17  jnz     loc_140120F97
0x140120e1d  xor     r8b, r8b
0x140120e20  mov     ecx, edx
0x140120e22  shr     ecx, 2
0x140120e25  and     cl, 1
0x140120e28  bt      edx, 18h
0x140120e2c  jb      loc_140120FC7
0x140120e32  mov     rdx, [rbx+98h]
0x140120e39  movzx   eax, sil
0x140120e3d  mov     [rsp+288h+var_238], r12; __int64
0x140120e42  lea     r9, [rsp+288h+var_210]
0x140120e47  mov     [rsp+288h+var_240], r9; __int64
0x140120e4c  lea     r9, [rsp+288h+Src]
0x140120e51  mov     [rsp+288h+var_248], r9; __int64
0x140120e56  mov     [rsp+288h+NextFlag], eax; NextFlag
0x140120e5a  mov     [rsp+288h+var_258], r8b; char
0x140120e5f  mov     byte ptr [rsp+288h+var_260], cl; int
0x140120e63  mov     [rsp+288h+var_268], rdx; __int64
0x140120e68  mov     r9, rbx; int
0x140120e6b  mov     r8, [r15+210h]; int
0x140120e72  mov     rdx, [r14+190h]; int
0x140120e79  mov     rcx, r14; int
0x140120e7c  call    TxfFilterDirectoryQuery
0x140120e81  movzx   edi, al
0x140120e84  mov     [rsp+288h+var_227], al
0x140120e88  mov     rcx, [r15+210h]
0x140120e8f  mov     rcx, [rcx+40h]
0x140120e93  mov     rcx, [rcx+88h]; Resource
0x140120e9a  call    cs:__imp_ExReleaseResourceLite
0x140120ea1  nop     dword ptr [rax+rax+00h]
0x140120ea6  mov     [rsp+288h+var_228], 0
0x140120eab  mov     rdx, [rsp+288h+Src]
0x140120eb0  jmp     loc_140120D2D
0x140120eb5  mov     sil, 1
0x140120eb8  jmp     loc_140120BFF
0x140120ebd  test    r8b, r8b
0x140120ec0  jz      loc_140120C34
0x140120ec6  movzx   eax, dil
0x140120eca  neg     al
0x140120ecc  sbb     ecx, ecx
0x140120ece  and     ecx, 2
  ... truncated ...
```
