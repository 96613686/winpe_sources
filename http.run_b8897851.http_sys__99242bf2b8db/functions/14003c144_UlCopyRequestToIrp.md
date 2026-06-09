# UlCopyRequestToIrp

- ea: `0x14003c144`
- end: `0x14003cd12`
- name: `UlCopyRequestToIrp`
- size: `3022`
- prototype: ``
- caller_count: `3`
- callee_count: `25`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14003a870`
- `0x14003cde0`
- `0x14003f1b0`

## callees

- `0x140039360`
- `0x14003be50`
- `0x14003c144`
- `0x1400416e0`
- `0x140041c8c`
- `0x140041e40`
- `0x14008ac80`
- `0x1400a6730`
- `0x1400a6e84`
- `0x1400ad5d0`
- `0x1400ad64c`
- `0x1400ad6b8`
- `0x1400ad78c`
- `0x1400b1bac`
- `0x140122ba4`
- `0x14012508c`
- `0x1401677e0`
- `0x140167b40`
- `0x1401c3008`
- `0x1401c37f8`
- `0x1401c3f78`
- `0x1401d2654`
- `0x1401d96fc`
- `0x1401d9c5c`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!IoGetRequestorProcess` at `0x14003c18e`
- `ntoskrnl!IoGetRequestorProcess` at `0x14003c18e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003c95a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003ca81`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003c95a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003ca81`
- `ntoskrnl!IofCompleteRequest` at `0x14003ccea`
- `ntoskrnl!IofCompleteRequest` at `0x14003ccea`
- `ntoskrnl!IoIs32bitProcess` at `0x14003c24f`
- `ntoskrnl!IoIs32bitProcess` at `0x14003ca16`
- `ntoskrnl!IoIs32bitProcess` at `0x14003cab3`
- `ntoskrnl!IoIs32bitProcess` at `0x14003c24f`
- `ntoskrnl!IoIs32bitProcess` at `0x14003ca16`
- `ntoskrnl!IoIs32bitProcess` at `0x14003cab3`
- `ntoskrnl!PsGetProcessId` at `0x14003c19d`
- `ntoskrnl!PsGetProcessId` at `0x14003c19d`

## pseudocode

```c
void __fastcall UlCopyRequestToIrp(__int64 a1, PIRP Irp, __int64 a3, struct _LIST_ENTRY *a4, char a5)
{
  struct _LIST_ENTRY *v5; // r13
  __int64 v6; // rdi
  int v9; // ebx
  struct _KPROCESS *RequestorProcess; // rax
  HANDLE ProcessId; // rax
  bool v12; // zf
  ULONG v13; // r12d
  int v14; // eax
  __int64 v15; // r8
  __int64 BugCheckOnFailure; // r11
  int Status; // r14d
  __int64 v18; // rax
  __int64 v19; // rdx
  BOOLEAN v20; // r13
  int v21; // eax
  int v22; // ecx
  __int64 v23; // r14
  int v24; // edi
  unsigned int v25; // eax
  unsigned int v26; // edi
  int v27; // eax
  __int64 v28; // r8
  char v29; // al
  unsigned int v30; // r8d
  __int64 v31; // r9
  unsigned int v32; // edx
  char v33; // al
  __int64 v34; // rax
  unsigned int v35; // r8d
  unsigned int v36; // ecx
  int TransportIdleConnectionTimeout; // eax
  __int64 v38; // rdx
  __int64 v39; // rax
  _QWORD *v40; // r14
  unsigned int v41; // eax
  __int64 v42; // r14
  unsigned int v43; // eax
  unsigned int v44; // r11d
  unsigned int v45; // edi
  __int64 v46; // rcx
  int UserAuthInfoSize; // eax
  int UserChannelBindInfoSize; // eax
  unsigned int v49; // edi
  unsigned int v50; // edi
  __int64 v51; // rcx
  int UserTokenBindingInfoSize; // eax
  int v53; // eax
  unsigned int v54; // edi
  unsigned int v55; // edi
  unsigned int v56; // edi
  unsigned int v57; // edi
  int QuicCreationStatsV2Size; // eax
  unsigned int v59; // r12d
  unsigned __int8 v60; // di
  struct _IO_STACK_LOCATION *v61; // rbx
  PMDL v62; // rcx
  PVOID v63; // r9
  int Length; // r8d
  char *v65; // rdx
  int v66; // ecx
  BOOLEAN v67; // al
  int v68; // edx
  unsigned int v69; // eax
  PMDL MdlAddress; // rcx
  _QWORD *MappedSystemVa; // rbx
  _QWORD *v72; // r14
  size_t v73; // r8
  size_t v74; // r8
  int v75; // eax
  ULONG v76; // r8d
  __int64 v77; // rdx
  __int64 v78; // rcx
  __int64 v79; // rax
  const wchar_t *v80; // rdx
  struct _LIST_ENTRY *Blink; // rcx
  char v82; // [rsp+40h] [rbp-99h]
  char v83; // [rsp+88h] [rbp-51h] BYREF
  unsigned __int8 v84; // [rsp+89h] [rbp-50h]
  char v85; // [rsp+8Ah] [rbp-4Fh]
  __int16 v86; // [rsp+8Ch] [rbp-4Dh] BYREF
  char v87; // [rsp+90h] [rbp-49h] BYREF
  bool v88; // [rsp+91h] [rbp-48h]
  bool v89; // [rsp+92h] [rbp-47h]
  bool v90; // [rsp+93h] [rbp-46h]
  unsigned __int8 v91; // [rsp+94h] [rbp-45h]
  char v92; // [rsp+95h] [rbp-44h]
  char v93; // [rsp+96h] [rbp-43h]
  char v94; // [rsp+97h] [rbp-42h]
  char v95; // [rsp+98h] [rbp-41h]
  unsigned __int8 v96; // [rsp+99h] [rbp-40h]
  unsigned int v97; // [rsp+9Ch] [rbp-3Dh]
  int v98; // [rsp+A0h] [rbp-39h] BYREF
  unsigned int v99; // [rsp+A4h] [rbp-35h]
  int v100; // [rsp+A8h] [rbp-31h] BYREF
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+B0h] [rbp-29h]
  int v102; // [rsp+B8h] [rbp-21h]
  _OWORD v103[3]; // [rsp+C0h] [rbp-19h] BYREF
  int *v104; // [rsp+F0h] [rbp+17h]
  unsigned __int8 v105; // [rsp+140h] [rbp+67h] BYREF
  __int64 v106; // [rsp+148h] [rbp+6Fh]
  struct _LIST_ENTRY *v107; // [rsp+150h] [rbp+77h]

  v107 = a4;
  v106 = a3;
  v5 = a4;
  v6 = a3;
  v9 = *(_DWORD *)(*(_QWORD *)(a3 + 8) + 276LL);
  v102 = v9;
  if ( (BYTE2(xmmword_1401A2CA0) & 0x40) != 0 )
  {
    RequestorProcess = IoGetRequestorProcess(Irp);
    ProcessId = PsGetProcessId(RequestorProcess);
    WPP_SF_q(1046, 88, WPP_f5e766570e8f37c45cbdb4a59743600d_Traceguids, ProcessId);
  }
  v12 = *(_DWORD *)(v6 + 40) == 1;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  if ( v12 )
  {
    LOBYTE(v13) = 0;
    v14 = UlChargeRequestQueueQuota(a1);
    BugCheckOnFailure = 0;
    Status = v14;
    if ( v14 < 0 )
      goto LABEL_157;
  }
  v98 = 0;
  v100 = 0;
  memset(v103, 0, sizeof(v103));
  v104 = 0;
  if ( SBYTE1(xmmword_1401A2CA0) < 0 )
  {
    if ( a1 )
      v18 = *(_QWORD *)(a1 + 64);
    else
      v18 = 0;
    WPP_SF_qqP(1039, 14, WPP_f5e766570e8f37c45cbdb4a59743600d_Traceguids, a1, v18, Irp);
  }
  v13 = 0;
  v20 = IoIs32bitProcess(Irp);
  v21 = *(unsigned __int16 *)(a1 + 1980);
  if ( v20 )
    v22 = 12 * v21 + 536;
  else
    v22 = 24 * v21 + 928;
  v23 = *(_QWORD *)(a1 + 24);
  LOBYTE(v19) = v20 != 0;
  v24 = v22 + *(_DWORD *)(a1 + 1976);
  if ( *(_BYTE *)(v23 + 465) )
  {
    BYTE8(v103[0]) = v20 != 0;
    v104 = &v98;
    if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_qLqqqq(1049, 10, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v23 + 496, 37, v103, 0, 0, 0);
    v25 = (*(__int64 (__fastcall **)(_QWORD, __int64, _OWORD *))(*(_QWORD *)(v23 + 504) + 136LL))(
            *(_QWORD *)(v23 + 496),
            37,
            v103);
    Status = v25;
    if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_d(1049, 11, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v25);
    BugCheckOnFailure = 0;
    if ( Status < 0 )
      goto LABEL_118;
    if ( v20 )
      v26 = (v24 + 3) & 0xFFFFFFFC;
    else
      v26 = (v24 + 7) & 0xFFFFFFF8;
    v24 = v98 + v26;
  }
  v99 = 0;
  v91 = 0;
  v92 = 0;
  v93 = 0;
  v94 = 0;
  v95 = 0;
  v85 = 0;
  v96 = 0;
  v86 = 0;
  v83 = 0;
  v87 = 0;
  v84 = 0;
  v105 = 0;
  if ( SBYTE1(xmmword_1401A2CA0) < 0 )
    WPP_SF_qq(1039, 10, WPP_f5e766570e8f37c45cbdb4a59743600d_Traceguids, a1, *(_QWORD *)(a1 + 64));
  v27 = *(_DWORD *)(a1 + 2264);
  v28 = (unsigned int)(*(_BYTE *)(*(_QWORD *)(a1 + 24) + 480LL) != 0) + 4;
  if ( (v27 & 1) != 0 && (v27 & 2) == 0 )
  {
    v84 = 1;
    v28 = (unsigned int)(v28 + 1);
  }
  v29 = UlChannelBindRequestInfoPresent(a1, v19, v28);
  v32 = v30 + 1;
  v88 = v29 != 0;
  v12 = v29 == 0;
  v33 = *(_BYTE *)(v31 + 465);
  if ( v12 )
    v32 = v30;
  v89 = v33 != 0;
  v12 = v33 == 0;
  v34 = *(_QWORD *)(v31 + 880);
  v35 = v32 + 1;
  if ( v12 )
    v35 = v32;
  v90 = v34 != 0;
  v36 = v35 + 1;
  if ( !v34 )
    v36 = v35;
  v97 = v36;
  TransportIdleConnectionTimeout = UlGetTransportIdleConnectionTimeout(v31, &v86);
  BugCheckOnFailure = 0;
  Status = TransportIdleConnectionTimeout;
  if ( TransportIdleConnectionTimeout >= 0 )
  {
    if ( v86 )
    {
      ++v97;
      LOBYTE(v86) = 1;
    }
    else
    {
      LOBYTE(v86) = 0;
    }
    if ( !UxKirBrHttpQuerySocketTtl
      || !*(_BYTE *)(a1 + 1596)
      || !*(_BYTE *)(a1 + 1597)
      || (v39 = *(_QWORD *)(a1 + 24), !*(_BYTE *)(v39 + 480)) )
    {
LABEL_51:
      v42 = *(_QWORD *)(a1 + 24);
      if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_qLqqqq(1049, 10, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v42 + 496, 75, &v83, 0, 0, 0);
      v43 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)(v42 + 504) + 136LL))(
              *(_QWORD *)(v42 + 496),
              75,
              &v83,
              0,
              0,
              0);
      Status = v43;
      if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_d(1049, 11, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v43);
      BugCheckOnFailure = 0;
      if ( Status >= 0 )
      {
        v44 = v97;
        v85 = 0;
        if ( v83 )
        {
          v44 = v97 + 1;
          v85 = 1;
          ++v97;
        }
        if ( SBYTE1(xmmword_1401A2CA0) < 0 )
        {
          v82 = v90;
          WPP_SF_dllllll((unsigned __int8)v86, v90, v89, v44, v84, v88, v89);
        }
        BugCheckOnFailure = 0;
        v99 = v97;
        v91 = v84;
        v92 = v88;
        v93 = v89;
        v94 = v90;
        v95 = v86;
        v96 = v105;
      }
      goto LABEL_61;
    }
    v40 = (_QWORD *)(v39 + 496);
    if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_qLqqqq(1049, 10, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v40, 76, &v87, &v105, 0, 0);
    v41 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *, unsigned __int8 *, _QWORD, _QWORD))(v40[1] + 136LL))(
            *v40,
            76,
            &v87,
            &v105,
            0,
            0);
    Status = v41;
    if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_d(1049, 11, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v41);
    BugCheckOnFailure = 0;
    if ( Status >= 0 )
    {
      if ( v105 )
        ++v97;
      if ( SBYTE1(xmmword_1401A2CA0) < 0 )
        WPP_SF_d(1039, 11, WPP_f5e766570e8f37c45cbdb4a59743600d_Traceguids, v105);
      goto LABEL_51;
    }
  }
LABEL_61:
  if ( SBYTE1(xmmword_1401A2CA0) < 0 )
  {
    WPP_SF_d(1039, 13, WPP_f5e766570e8f37c45cbdb4a59743600d_Traceguids, (unsigned int)Status);
    BugCheckOnFailure = 0;
  }
  if ( Status < 0 )
    goto LABEL_118;
  if ( v20 )
    v45 = ((v24 + 3) & 0xFFFFFFFC) + 12 * v99;
  else
    v45 = 16 * v99 + ((v24 + 7) & 0xFFFFFFF8);
  if ( v91 )
  {
    v46 = a1 + 2264;
    if ( v20 )
    {
      LOBYTE(v38) = 1;
      UserAuthInfoSize = UlGetUserAuthInfoSize(v46, v38);
    }
    else
    {
      UserAuthInfoSize = UlGetUserAuthInfoSize(v46, 0);
      v45 = (v45 + 7) & 0xFFFFFFF8;
    }
    v45 += UserAuthInfoSize;
  }
  if ( v92 != (_BYTE)BugCheckOnFailure )
  {
    if ( v20 )
    {
      LOBYTE(v38) = 1;
      UserChannelBindInfoSize = UlGetUserChannelBindInfoSize(a1, v38);
      v49 = (v45 + 3) & 0xFFFFFFFC;
    }
    else
    {
      UserChannelBindInfoSize = UlGetUserChannelBindInfoSize(a1, 0);
      v49 = (v45 + 7) & 0xFFFFFFF8;
    }
    v45 = UserChannelBindInfoSize + v49;
    BugCheckOnFailure = 0;
  }
  if ( v93 != (_BYTE)BugCheckOnFailure )
  {
    if ( v20 )
      v50 = (v45 + 3) & 0xFFFFFFFC;
    else
      v50 = (v45 + 7) & 0xFFFFFFF8;
    v45 = v50 + 28;
  }
  if ( v94 == (_BYTE)BugCheckOnFailure )
  {
    v15 = 4294967292LL;
  }
  else
  {
    v51 = *(_QWORD *)(a1 + 24) + 880LL;
    if ( v20 )
    {
      LOBYTE(v38) = 1;
      UserTokenBindingInfoSize = UlGetUserTokenBindingInfoSize(v51, v38);
      v15 = 4294967292LL;
      v45 = UserTokenBindingInfoSize + ((v45 + 3) & 0xFFFFFFFC);
    }
    else
    {
      v53 = UlGetUserTokenBindingInfoSize(v51, 0);
      v15 = 4294967292LL;
      v45 = v53 + ((v45 + 7) & 0xFFFFFFF8);
    }
    BugCheckOnFailure = 0;
  }
  if ( v95 != (_BYTE)BugCheckOnFailure )
  {
    if ( v20 )
      v54 = (v45 + 3) & 0xFFFFFFFC;
    else
      v54 = (v45 + 7) & 0xFFFFFFF8;
    v45 = v54 + 2;
  }
  if ( v85 != (_BYTE)BugCheckOnFailure )
  {
    if ( v20 )
      v55 = (v45 + 3) & 0xFFFFFFFC;
    else
      v55 = (v45 + 7) & 0xFFFFFFF8;
    v45 = v55 + 1;
  }
  if ( UxKirBrHttpQuerySocketTtl == (_BYTE)BugCheckOnFailure || v96 == (_BYTE)BugCheckOnFailure )
  {
    if ( v20 )
      goto LABEL_108;
LABEL_103:
    v56 = (v45 + 255) & 0xFFFFFFF8;
    goto LABEL_104;
  }
  if ( !v20 )
  {
    v45 = ((v45 + 7) & 0xFFFFFFF8) + 1;
    goto LABEL_103;
  }
  v45 = ((v45 + 3) & 0xFFFFFFFC) + 1;
LABEL_108:
  v56 = (v45 + 251) & 0xFFFFFFFC;
LABEL_104:
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 24) + 480LL) == (_BYTE)BugCheckOnFailure )
  {
    QuicCreationStatsV2Size = UlGetQuicCreationStatsV2Size(a1, &v100, 4294967292LL);
    BugCheckOnFailure = 0;
    Status = QuicCreationStatsV2Size;
    if ( QuicCreationStatsV2Size < 0 )
      goto LABEL_118;
    if ( v20 )
      v59 = (v56 + 259) & 0xFFFFFFFC;
    else
      v59 = (v56 + 263) & 0xFFFFFFF8;
    v13 = v100 + v59;
  }
  else
  {
    if ( v20 )
      v57 = (v56 + 59) & 0xFFFFFFFC;
    else
      v57 = (v56 + 63) & 0xFFFFFFF8;
    v13 = v57 + 152;
  }
  if ( SBYTE1(xmmword_1401A2CA0) >= (char)BugCheckOnFailure )
    goto LABEL_120;
  WPP_SF_d(1039, 15, WPP_f5e766570e8f37c45cbdb4a59743600d_Traceguids, v13);
  BugCheckOnFailure = 0;
LABEL_118:
  if ( SBYTE1(xmmword_1401A2CA0) < 0 )
  {
    WPP_SF_d(1039, 16, WPP_f5e766570e8f37c45cbdb4a59743600d_Traceguids, (unsigned int)Status);
    BugCheckOnFailure = 0;
  }
LABEL_120:
  if ( Status < 0 )
    goto LABEL_156;
  v60 = BugCheckOnFailure;
  if ( (_WORD)v9 == 1 && HIWORD(v102) == (_WORD)BugCheckOnFailure )
    v60 = 1;
  v61 = CurrentStackLocation;
  if ( v13 > CurrentStackLocation->Parameters.Read.Length )
  {
    v67 = IoIs32bitProcess(Irp);
    BugCheckOnFailure = 0;
    if ( v67 )
      v69 = 8 * (v60 ^ 1) + 464;
    else
      v69 = v60 != 0 ? 848 : 864;
    if ( v61->Parameters.Read.Length < v69 )
    {
      Status = -1073741789;
      goto LABEL_130;
    }
    MdlAddress = Irp->MdlAddress;
    if ( (MdlAddress->MdlFlags & 5) != 0 )
    {
      MappedSystemVa = MdlAddress->MappedSystemVa;
    }
    else
    {
      MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000000u);
      BugCheckOnFailure = 0;
    }
    if ( MappedSystemVa )
    {
      if ( UxKirNewUma )
      {
        LOBYTE(v68) = v60;
        v75 = UlpCopyRequestId((_DWORD)Irp, v68, a1, (_DWORD)MappedSystemVa, 0);
        BugCheckOnFailure = 0;
        Status = v75;
        if ( v75 < 0 )
          goto LABEL_156;
      }
      else
      {
        v72 = (_QWORD *)(a1 + 56);
        if ( IoIs32bitProcess(Irp) )
        {
          v73 = 464;
          if ( !v60 )
            v73 = 472;
          memset(MappedSystemVa, 0, v73);
          MappedSystemVa[2] = *v72;
          MappedSystemVa[1] = *(_QWORD *)(a1 + 32);
          MappedSystemVa[56] = *(_QWORD *)(a1 + 40);
        }
        else
        {
          v74 = 848;
          if ( !v60 )
            v74 = 864;
          memset(MappedSystemVa, 0, v74);
          MappedSystemVa[2] = *v72;
          MappedSystemVa[1] = *(_QWORD *)(a1 + 32);
          MappedSystemVa[104] = *(_QWORD *)(a1 + 40);
        }
        BugCheckOnFailure = 0;
      }
      Status = -2147483643;
      Irp->IoStatus.Information = v13;
      goto LABEL_156;
    }
    Status = -1073741670;
LABEL_156:
    v5 = v107;
    v6 = v106;
LABEL_157:
    v61 = CurrentStackLocation;
    goto LABEL_158;
  }
  v62 = Irp->MdlAddress;
  if ( (v62->MdlFlags & 5) != 0 )
  {
    v63 = v62->MappedSystemVa;
  }
  else
  {
    v63 = MmMapLockedPagesSpecifyCache(v62, 0, MmCached, 0, BugCheckOnFailure, 0x40000000u);
    BugCheckOnFailure = 0;
  }
  if ( !v63 )
  {
    Status = -1073741670;
LABEL_130:
    v6 = v106;
    v5 = v107;
    goto LABEL_158;
  }
  Length = v61->Parameters.Read.Length;
  v6 = v106;
  v65 = (char *)Irp->MdlAddress->StartVa + Irp->MdlAddress->ByteOffset;
  v66 = (int)Irp->AssociatedIrp.MasterIrp->MdlAddress;
  if ( UxKirNewUma == (_BYTE)BugCheckOnFailure )
    UlpCopyRequestToBufferOld(a1, Irp, (int)v65, Length, v13, v66, a5, (__int64)&Irp->IoStatus);
  else
    UlpCopyRequestToBuffer(a1, Irp, (__int64)v65, Length, BugCheckOnFailure, v82, v66, a5, (__int64)&Irp->IoStatus);
  Status = Irp->IoStatus.Status;
  BugCheckOnFailure = 0;
  v5 = v107;
LABEL_158:
  if ( SBYTE1(xmmword_1401A2CA0) < (char)BugCheckOnFailure )
  {
    if ( v61 )
      v76 = v61->Parameters.Read.Length;
    else
      v76 = BugCheckOnFailure;
    WPP_SF_dqiqZLSiqddP(
      *(_QWORD *)(v6 + 8) + 160,
      *(_QWORD *)(v6 + 8),
      v76,
      Status,
      a1,
      *(_QWORD *)(a1 + 56),
      *(_QWORD *)(v6 + 8),
      *(_QWORD *)(v6 + 8) + 160LL,
      *(_DWORD *)(a1 + 1408),
      *(_QWORD *)(a1 + 2032),
      *(_QWORD *)(a1 + 32),
      (char)Irp,
      v76,
      v13,
      Irp->IoStatus.Information);
    BugCheckOnFailure = 0;
  }
  Irp->IoStatus.Status = Status;
  if ( (int)(Status + 0x80000000) < 0 || Status == -2147483643 )
  {
    v77 = *(_QWORD *)(a1 + 24);
    if ( v77 )
    {
      v78 = *(_QWORD *)(v77 + 1096);
      if ( (*(_BYTE *)(v78 + 1760) & 1) != 0
        && (*(_QWORD *)(v78 + 1776) == BugCheckOnFailure
         || (unsigned __int8)UlEtwEvaluateFilterForRequestConnection(a1, v77, 0)) )
      {
        v79 = *(_QWORD *)(v6 + 8);
        v80 = L"<<unnamed>>";
        if ( *(_QWORD *)(v79 + 168) )
          v80 = *(const wchar_t **)(v79 + 168);
        McTemplateK0pxqzzq_EtwWriteTransfer(
          *(_QWORD *)(*(_QWORD *)(a1 + 24) + 1096LL) + 1688,
          (_DWORD)v80,
          a1 + 72,
          a1,
          *(_QWORD *)(a1 + 56),
          *(_DWORD *)(a1 + 1408),
          (__int64)v80,
          *(_QWORD *)(a1 + 2032),
          Status);
      }
    }
    if ( Status == -2147483643 )
      UlStartRequestQueueTimer(a1, v77, v15);
  }
  else
  {
    UlCloseConnection(*(_QWORD *)(a1 + 24));
  }
  UlUpdateReceiveHttpRequestApiTimings(v6, (unsigned int)Status);
  if ( v5 )
  {
    Blink = v5->Blink;
    if ( Blink->Flink != v5 )
      __fastfail(3u);
    Irp->Tail.Overlay.ListEntry.Flink = v5;
    Irp->Tail.Overlay.ListEntry.Blink = Blink;
    Blink->Flink = &Irp->Tail.Overlay.ListEntry;
    v5->Blink = &Irp->Tail.Overlay.ListEntry;
  }
  else
  {
    IofCompleteRequest(Irp, 0);
  }
}

```

## disassembly

```asm
0x14003c144  mov     rax, rsp
0x14003c147  mov     [rax+8], rbx
0x14003c14b  mov     [rax+20h], r9
0x14003c14f  mov     [rax+18h], r8
0x14003c153  push    rbp
0x14003c154  push    rsi
0x14003c155  push    rdi
0x14003c156  push    r12
0x14003c158  push    r13
0x14003c15a  push    r14
0x14003c15c  push    r15
0x14003c15e  lea     rbp, [rax-57h]
0x14003c162  sub     rsp, 0F0h
0x14003c169  mov     rbx, [r8+8]
0x14003c16d  mov     r13, r9
0x14003c170  mov     rdi, r8
0x14003c173  mov     r15, rdx
0x14003c176  mov     rsi, rcx
0x14003c179  mov     ebx, [rbx+114h]
0x14003c17f  mov     [rbp+4Fh+var_70], ebx
0x14003c182  test    byte ptr cs:xmmword_1401A2CA0+2, 40h
0x14003c189  jz      short loc_14003C1C2
0x14003c18b  mov     rcx, rdx; Irp
0x14003c18e  call    cs:__imp_IoGetRequestorProcess
0x14003c195  nop     dword ptr [rax+rax+00h]
0x14003c19a  mov     rcx, rax; Process
0x14003c19d  call    cs:__imp_PsGetProcessId
0x14003c1a4  nop     dword ptr [rax+rax+00h]
0x14003c1a9  mov     edx, 58h ; 'X'
0x14003c1ae  lea     r8, WPP_f5e766570e8f37c45cbdb4a59743600d_Traceguids
0x14003c1b5  mov     r9, rax
0x14003c1b8  mov     ecx, 416h
0x14003c1bd  call    WPP_SF_q
0x14003c1c2  mov     rax, [r15+0B8h]
0x14003c1c9  xor     r11d, r11d
0x14003c1cc  cmp     dword ptr [rdi+28h], 1
0x14003c1d0  mov     [rbp+4Fh+var_78], rax
0x14003c1d4  jnz     short loc_14003C1EF
0x14003c1d6  mov     rcx, rsi
0x14003c1d9  mov     r12d, r11d
0x14003c1dc  call    UlChargeRequestQueueQuota
0x14003c1e1  xor     r11d, r11d
0x14003c1e4  mov     r14d, eax
0x14003c1e7  test    eax, eax
0x14003c1e9  js      loc_14003CB5E
0x14003c1ef  xorps   xmm0, xmm0
0x14003c1f2  mov     [rbp+4Fh+var_88], r11d
0x14003c1f6  xor     eax, eax
0x14003c1f8  mov     [rbp+4Fh+var_80], r11d
0x14003c1fc  movups  [rbp+4Fh+var_68], xmm0
0x14003c200  mov     [rbp+4Fh+var_38], rax
0x14003c204  movups  [rbp+4Fh+var_58], xmm0
0x14003c208  movups  [rbp+4Fh+var_48], xmm0
0x14003c20c  cmp     byte ptr cs:xmmword_1401A2CA0+1, r11b
0x14003c213  jge     short loc_14003C249
0x14003c215  test    rsi, rsi
0x14003c218  jz      short loc_14003C220
0x14003c21a  mov     rax, [rsi+40h]
0x14003c21e  jmp     short loc_14003C223
0x14003c220  mov     rax, r11
0x14003c223  mov     edx, 0Eh
0x14003c228  mov     qword ptr [rsp+120h+Priority], r15
0x14003c22d  mov     ecx, 40Fh
0x14003c232  mov     qword ptr [rsp+120h+BugCheckOnFailure], rax
0x14003c237  mov     r9, rsi
0x14003c23a  lea     r8, WPP_f5e766570e8f37c45cbdb4a59743600d_Traceguids
0x14003c241  call    WPP_SF_qqP
0x14003c246  xor     r11d, r11d
0x14003c249  mov     rcx, r15; Irp
0x14003c24c  mov     r12d, r11d
0x14003c24f  call    cs:__imp_IoIs32bitProcess
0x14003c256  nop     dword ptr [rax+rax+00h]
0x14003c25b  mov     r13b, al
0x14003c25e  xor     r11d, r11d
0x14003c261  movzx   eax, word ptr [rsi+7BCh]
0x14003c268  test    r13b, r13b
0x14003c26b  jz      short loc_14003C279
0x14003c26d  lea     ecx, [rax+rax*2]
0x14003c270  lea     ecx, ds:218h[rcx*4]
0x14003c277  jmp     short loc_14003C283
0x14003c279  lea     eax, [rax+rax*2]
0x14003c27c  lea     ecx, ds:3A0h[rax*8]
0x14003c283  mov     r14, [rsi+18h]
0x14003c287  test    r13b, r13b
0x14003c28a  mov     edi, [rsi+7B8h]
0x14003c290  setnz   dl
0x14003c293  add     edi, ecx
0x14003c295  cmp     [r14+1D1h], r11b
0x14003c29c  jz      loc_14003C36C
0x14003c2a2  lea     rax, [rbp+4Fh+var_88]
0x14003c2a6  mov     byte ptr [rbp+4Fh+var_68+8], dl
0x14003c2a9  mov     [rbp+4Fh+var_38], rax
0x14003c2ad  test    byte ptr cs:xmmword_1401A2CA0+3, 2
0x14003c2b4  jz      short loc_14003C2F6
0x14003c2b6  mov     qword ptr [rsp+120h+var_E0], r11
0x14003c2bb  lea     rax, [rbp+4Fh+var_68]
0x14003c2bf  mov     qword ptr [rsp+120h+var_E8], r11
0x14003c2c4  lea     r9, [r14+1F0h]
0x14003c2cb  mov     qword ptr [rsp+120h+var_F0], r11
0x14003c2d0  lea     r8, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids
0x14003c2d7  mov     qword ptr [rsp+120h+Priority], rax
0x14003c2dc  mov     edx, 0Ah
0x14003c2e1  mov     ecx, 419h
0x14003c2e6  mov     [rsp+120h+BugCheckOnFailure], 25h ; '%'
0x14003c2ee  call    WPP_SF_qLqqqq
0x14003c2f3  xor     r11d, r11d
0x14003c2f6  mov     rax, [r14+1F8h]
0x14003c2fd  lea     r8, [rbp+4Fh+var_68]
0x14003c301  mov     rcx, [r14+1F0h]
0x14003c308  xor     r9d, r9d
0x14003c30b  mov     qword ptr [rsp+120h+Priority], r11
0x14003c310  mov     qword ptr [rsp+120h+BugCheckOnFailure], r11
0x14003c315  mov     rax, [rax+88h]
0x14003c31c  lea     edx, [r9+25h]
0x14003c320  call    _guard_dispatch_icall
0x14003c325  mov     r14d, eax
0x14003c328  test    byte ptr cs:xmmword_1401A2CA0+3, 2
0x14003c32f  jz      short loc_14003C34A
0x14003c331  mov     edx, 0Bh
0x14003c336  lea     r8, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids
0x14003c33d  mov     ecx, 419h
0x14003c342  mov     r9d, eax
0x14003c345  call    WPP_SF_d
0x14003c34a  xor     r11d, r11d
0x14003c34d  test    r14d, r14d
0x14003c350  js      loc_14003C8E0
0x14003c356  test    r13b, r13b
0x14003c359  jz      short loc_14003C363
0x14003c35b  add     edi, 3
0x14003c35e  and     edi, 0FFFFFFFCh
0x14003c361  jmp     short loc_14003C369
0x14003c363  add     edi, 7
0x14003c366  and     edi, 0FFFFFFF8h
0x14003c369  add     edi, [rbp+4Fh+var_88]
0x14003c36c  mov     [rbp+4Fh+var_84], r11d
0x14003c370  mov     [rbp+4Fh+var_94], r11b
0x14003c374  mov     [rbp+4Fh+var_93], r11b
0x14003c378  mov     [rbp+4Fh+var_92], r11b
0x14003c37c  mov     [rbp+4Fh+var_91], r11b
0x14003c380  mov     [rbp+4Fh+var_90], r11b
0x14003c384  mov     [rbp+4Fh+var_9E], r11b
0x14003c388  mov     [rbp+4Fh+var_8F], r11b
0x14003c38c  mov     [rbp+4Fh+var_9C], r11w
0x14003c391  mov     [rbp+4Fh+var_A0], r11b
0x14003c395  mov     [rbp+4Fh+var_98], r11b
0x14003c399  mov     [rbp+4Fh+var_9F], r11b
0x14003c39d  mov     [rbp+4Fh+arg_8], r11b
0x14003c3a1  cmp     byte ptr cs:xmmword_1401A2CA0+1, r11b
0x14003c3a8  jge     short loc_14003C3CC
0x14003c3aa  mov     rax, [rsi+40h]
0x14003c3ae  lea     r8, WPP_f5e766570e8f37c45cbdb4a59743600d_Traceguids
0x14003c3b5  mov     edx, 0Ah
0x14003c3ba  mov     qword ptr [rsp+120h+BugCheckOnFailure], rax
0x14003c3bf  mov     ecx, 40Fh
0x14003c3c4  mov     r9, rsi
0x14003c3c7  call    WPP_SF_qq
0x14003c3cc  mov     r9, [rsi+18h]
0x14003c3d0  mov     ecx, 1
0x14003c3d5  mov     al, [r9+1E0h]
0x14003c3dc  neg     al
0x14003c3de  mov     eax, [rsi+8D8h]
0x14003c3e4  sbb     r8d, r8d
0x14003c3e7  neg     r8d
0x14003c3ea  add     r8d, 4
0x14003c3ee  test    cl, al
0x14003c3f0  jz      short loc_14003C3FC
0x14003c3f2  test    al, 2
0x14003c3f4  jnz     short loc_14003C3FC
0x14003c3f6  mov     [rbp+4Fh+var_9F], cl
0x14003c3f9  inc     r8d
0x14003c3fc  mov     rcx, rsi
0x14003c3ff  call    UlChannelBindRequestInfoPresent
0x14003c404  test    al, al
0x14003c406  lea     edx, [r8+1]
0x14003c40a  setnz   [rbp+4Fh+var_97]
0x14003c40e  test    al, al
0x14003c410  mov     al, [r9+1D1h]
0x14003c417  cmovz   edx, r8d
0x14003c41b  test    al, al
0x14003c41d  setnz   [rbp+4Fh+var_96]
0x14003c421  test    al, al
0x14003c423  mov     rax, [r9+370h]
0x14003c42a  lea     r8d, [rdx+1]
0x14003c42e  cmovz   r8d, edx
0x14003c432  test    rax, rax
0x14003c435  lea     rdx, [rbp+4Fh+var_9C]
0x14003c439  setnz   [rbp+4Fh+var_95]
0x14003c43d  test    rax, rax
0x14003c440  lea     ecx, [r8+1]
0x14003c444  cmovz   ecx, r8d
0x14003c448  mov     [rbp+4Fh+var_8C], ecx
0x14003c44b  mov     rcx, r9
0x14003c44e  call    UlGetTransportIdleConnectionTimeout
0x14003c453  xor     r11d, r11d
0x14003c456  mov     r14d, eax
0x14003c459  test    eax, eax
0x14003c45b  js      loc_14003C6C8
0x14003c461  cmp     [rbp+4Fh+var_9C], r11w
0x14003c466  jz      short loc_14003C471
0x14003c468  inc     [rbp+4Fh+var_8C]
0x14003c46b  mov     byte ptr [rbp+4Fh+var_9C], 1
0x14003c46f  jmp     short loc_14003C475
0x14003c471  mov     byte ptr [rbp+4Fh+var_9C], r11b
0x14003c475  cmp     cs:UxKirBrHttpQuerySocketTtl, r11b
0x14003c47c  jz      loc_14003C588
0x14003c482  cmp     [rsi+63Ch], r11b
0x14003c489  jz      loc_14003C588
0x14003c48f  cmp     [rsi+63Dh], r11b
0x14003c496  jz      loc_14003C588
0x14003c49c  mov     rax, [rsi+18h]
0x14003c4a0  cmp     [rax+1E0h], r11b
0x14003c4a7  jz      loc_14003C588
0x14003c4ad  lea     r14, [rax+1F0h]
0x14003c4b4  test    byte ptr cs:xmmword_1401A2CA0+3, 2
0x14003c4bb  jz      short loc_14003C4FD
0x14003c4bd  mov     qword ptr [rsp+120h+var_E0], r11
0x14003c4c2  lea     rax, [rbp+4Fh+arg_8]
0x14003c4c6  mov     qword ptr [rsp+120h+var_E8], r11
0x14003c4cb  lea     r8, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids
0x14003c4d2  mov     qword ptr [rsp+120h+var_F0], rax
0x14003c4d7  mov     edx, 0Ah
0x14003c4dc  lea     rax, [rbp+4Fh+var_98]
0x14003c4e0  mov     ecx, 419h
0x14003c4e5  mov     qword ptr [rsp+120h+Priority], rax
0x14003c4ea  mov     r9, r14
0x14003c4ed  mov     [rsp+120h+BugCheckOnFailure], 4Ch ; 'L'
0x14003c4f5  call    WPP_SF_qLqqqq
0x14003c4fa  xor     r11d, r11d
0x14003c4fd  mov     rax, [r14+8]
0x14003c501  lea     r9, [rbp+4Fh+arg_8]
0x14003c505  mov     rcx, [r14]
0x14003c508  lea     r8, [rbp+4Fh+var_98]
0x14003c50c  mov     qword ptr [rsp+120h+Priority], r11
0x14003c511  mov     edx, 4Ch ; 'L'
0x14003c516  mov     qword ptr [rsp+120h+BugCheckOnFailure], r11
0x14003c51b  mov     rax, [rax+88h]
0x14003c522  call    _guard_dispatch_icall
0x14003c527  mov     r14d, eax
0x14003c52a  test    byte ptr cs:xmmword_1401A2CA0+3, 2
0x14003c531  jz      short loc_14003C54C
0x14003c533  mov     edx, 0Bh
0x14003c538  lea     r8, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids
0x14003c53f  mov     ecx, 419h
0x14003c544  mov     r9d, eax
0x14003c547  call    WPP_SF_d
0x14003c54c  xor     r11d, r11d
0x14003c54f  test    r14d, r14d
0x14003c552  js      loc_14003C6C8
0x14003c558  movzx   eax, [rbp+4Fh+arg_8]
0x14003c55c  test    al, al
0x14003c55e  jz      short loc_14003C563
0x14003c560  inc     [rbp+4Fh+var_8C]
0x14003c563  cmp     byte ptr cs:xmmword_1401A2CA0+1, r11b
0x14003c56a  jge     short loc_14003C588
0x14003c56c  mov     r9d, eax
0x14003c56f  lea     r8, WPP_f5e766570e8f37c45cbdb4a59743600d_Traceguids
0x14003c576  mov     edx, 0Bh
0x14003c57b  mov     ecx, 40Fh
0x14003c580  call    WPP_SF_d
0x14003c585  xor     r11d, r11d
0x14003c588  mov     r14, [rsi+18h]
0x14003c58c  test    byte ptr cs:xmmword_1401A2CA0+3, 2
0x14003c593  jz      short loc_14003C5D2
0x14003c595  mov     qword ptr [rsp+120h+var_E0], r11
0x14003c59a  lea     rax, [rbp+4Fh+var_A0]
0x14003c59e  mov     qword ptr [rsp+120h+var_E8], r11
0x14003c5a3  lea     r9, [r14+1F0h]
0x14003c5aa  mov     qword ptr [rsp+120h+var_F0], r11
0x14003c5af  lea     r8, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids
0x14003c5b6  mov     qword ptr [rsp+120h+Priority], rax
0x14003c5bb  mov     edx, 0Ah
0x14003c5c0  mov     ecx, 419h
0x14003c5c5  mov     [rsp+120h+BugCheckOnFailure], 4Bh ; 'K'
0x14003c5cd  call    WPP_SF_qLqqqq
0x14003c5d2  mov     rax, [r14+1F8h]
0x14003c5d9  lea     r8, [rbp+4Fh+var_A0]
0x14003c5dd  xor     ecx, ecx
0x14003c5df  xor     r9d, r9d
0x14003c5e2  mov     qword ptr [rsp+120h+Priority], rcx
0x14003c5e7  mov     qword ptr [rsp+120h+BugCheckOnFailure], rcx
0x14003c5ec  mov     rax, [rax+88h]
0x14003c5f3  lea     edx, [rcx+4Bh]
0x14003c5f6  mov     rcx, [r14+1F0h]
0x14003c5fd  call    _guard_dispatch_icall
0x14003c602  mov     r14d, eax
0x14003c605  test    byte ptr cs:xmmword_1401A2CA0+3, 2
0x14003c60c  jz      short loc_14003C627
0x14003c60e  mov     edx, 0Bh
0x14003c613  lea     r8, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids
0x14003c61a  mov     ecx, 419h
0x14003c61f  mov     r9d, eax
0x14003c622  call    WPP_SF_d
0x14003c627  xor     r11d, r11d
0x14003c62a  test    r14d, r14d
0x14003c62d  js      loc_14003C6C8
0x14003c633  cmp     [rbp+4Fh+var_A0], r11b
0x14003c637  mov     al, r11b
0x14003c63a  mov     r11d, [rbp+4Fh+var_8C]
0x14003c63e  mov     [rbp+4Fh+var_9E], al
0x14003c641  jz      short loc_14003C654
  ... truncated ...
```
