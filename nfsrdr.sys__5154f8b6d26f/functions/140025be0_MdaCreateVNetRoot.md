# MdaCreateVNetRoot

- ea: `0x140025be0`
- end: `0x14002723d`
- name: `MdaCreateVNetRoot`
- size: `5725`
- prototype: ``
- caller_count: `0`
- callee_count: `31`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1400022c0`
- `0x1400029d0`
- `0x140005c90`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x140015f84`
- `0x1400173f8`
- `0x14001db18`
- `0x140025484`
- `0x140025be0`
- `0x1400282a8`
- `0x14002840c`
- `0x140028478`
- `0x140028608`
- `0x140028870`
- `0x140028ac8`
- `0x140028f00`
- `0x140029104`
- `0x1400293c4`
- `0x14002998c`
- `0x140029b24`
- `0x140029e34`
- `0x14002a1ac`
- `0x14002a20c`
- `0x140036354`
- `0x14003677c`
- `0x140038550`
- `0x14003aba0`
- `0x14003abe0`
- `0x14003b0c0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x140026f7f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400271be`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140026f7f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400271be`
- `ntoskrnl!ExAcquireFastMutex` at `0x140026ea0`
- `ntoskrnl!ExAcquireFastMutex` at `0x140026ea0`
- `ntoskrnl!ExReleaseFastMutex` at `0x140026f3a`
- `ntoskrnl!ExReleaseFastMutex` at `0x140027092`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400270f4`
- `ntoskrnl!ExReleaseFastMutex` at `0x140026f3a`
- `ntoskrnl!ExReleaseFastMutex` at `0x140027092`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400270f4`
- `ntoskrnl!LsaFreeReturnBuffer` at `0x140025fd7`
- `ntoskrnl!LsaFreeReturnBuffer` at `0x140025fd7`
- `ntoskrnl!KeInitializeMutex` at `0x140025dfa`
- `ntoskrnl!KeInitializeMutex` at `0x140025dfa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026dd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026f99`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026fc3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026dd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026f99`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026fc3`
- `ntoskrnl!ZwClose` at `0x140026fb2`
- `ntoskrnl!ZwClose` at `0x140026fb2`
- `ntoskrnl!ExAllocatePool2` at `0x140025cff`
- `ntoskrnl!ExAllocatePool2` at `0x140025da0`
- `ntoskrnl!ExAllocatePool2` at `0x140025cff`
- `ntoskrnl!ExAllocatePool2` at `0x140025da0`
- `rdbss!RxLogEventDirect` at `0x1400265a8`
- `rdbss!RxLogEventDirect` at `0x1400265a8`
- `ksecdd!LsaGetLogonSessionData` at `0x140025fbd`
- `ksecdd!LsaGetLogonSessionData` at `0x140025fbd`

## string_xrefs

- `0x140026369`: `MountOptions`
- `0x14002609e`: `SOFTWARE\Microsoft\ServicesForNFS`
- `0x1400260e6`: `SOFTWARE\Microsoft\ServicesForNFS`
- `0x140025c20`: `MdaCreateVNetRoot`
- `0x140027191`: `MountSymlinkTargetShare`

## pseudocode

```c
__int64 __fastcall MdaCreateVNetRoot(__int64 a1)
{
  __int64 v1; // r12
  __int64 v3; // rax
  __int64 v4; // r14
  char v5; // si
  _QWORD *v6; // r13
  __int64 v7; // rbx
  int *Pool2; // rax
  int *v9; // rbx
  int SecurityInfo; // edi
  struct _KMUTANT *v11; // rax
  __int64 v12; // r9
  int v13; // ecx
  int v14; // eax
  __int64 v15; // rcx
  int v16; // r8d
  char *v17; // rcx
  int Registry; // edi
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rcx
  int v25; // r8d
  unsigned int v26; // ecx
  unsigned int v27; // eax
  int v28; // eax
  int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  __int64 v36; // r14
  __int64 v37; // rcx
  PDEVICE_OBJECT v38; // rcx
  __int64 v39; // rdx
  _DWORD *v40; // rdi
  int v41; // r8d
  unsigned int v42; // eax
  unsigned int v43; // eax
  int v44; // eax
  __int64 v45; // rax
  int v46; // r8d
  char v47; // al
  char v48; // cl
  int v49; // r8d
  int v50; // r9d
  unsigned int v51; // ecx
  unsigned int v52; // eax
  unsigned int v53; // eax
  int v54; // eax
  __int64 v55; // rax
  int v56; // r8d
  int v57; // r9d
  unsigned int v58; // ecx
  unsigned int v59; // eax
  unsigned int v60; // eax
  int v61; // eax
  __int64 v62; // rax
  __int64 v63; // r14
  __int64 v64; // rax
  _WORD *v65; // r9
  __int64 v66; // r11
  __int64 v67; // r10
  unsigned __int16 v68; // cx
  int v69; // edx
  __int16 v70; // r8
  unsigned __int16 v71; // dx
  __int16 v72; // cx
  int v73; // eax
  __int64 *v74; // r12
  __int64 *v75; // rdi
  __int64 v76; // rax
  _DWORD *v77; // r13
  PDEVICE_OBJECT v78; // rcx
  int v79; // edx
  void *v80; // rcx
  void *v81; // rcx
  __int64 v83; // rcx
  __int64 v84; // rax
  int V3StatInfo; // eax
  void (__fastcall *v86)(__int64); // rax
  char v87; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v88[3]; // [rsp+41h] [rbp-BFh] BYREF
  int v89; // [rsp+44h] [rbp-BCh] BYREF
  char v90; // [rsp+48h] [rbp-B8h] BYREF
  int v91; // [rsp+4Ch] [rbp-B4h] BYREF
  int v92; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v93; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v94[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v95; // [rsp+A0h] [rbp-60h]
  __int64 v96; // [rsp+A8h] [rbp-58h] BYREF
  int v97; // [rsp+B0h] [rbp-50h] BYREF
  int v98[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v99; // [rsp+C0h] [rbp-40h]
  __int64 v100; // [rsp+C8h] [rbp-38h]
  int v101; // [rsp+D0h] [rbp-30h]
  __int64 v102; // [rsp+D8h] [rbp-28h]
  struct _UNICODE_STRING UnicodeString; // [rsp+E0h] [rbp-20h] BYREF
  PVOID Buffer; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD *v105; // [rsp+F8h] [rbp-8h]
  PVOID P[2]; // [rsp+100h] [rbp+0h] BYREF
  PSID v107[12]; // [rsp+110h] [rbp+10h] BYREF
  char v108[24]; // [rsp+170h] [rbp+70h] BYREF

  v1 = *(_QWORD *)(a1 + 264);
  v3 = *(_QWORD *)(a1 + 32);
  strcpy(v108, "MdaCreateVNetRoot");
  v95 = v1;
  v4 = *(_QWORD *)(v3 + 80);
  v100 = v4;
  memset(v94, 0, sizeof(v94));
  v96 = 0;
  v5 = 0;
  UnicodeString = 0;
  *(_QWORD *)v98 = 0;
  v99 = 0;
  v89 = 0;
  v92 = 0;
  Buffer = 0;
  v6 = *(_QWORD **)(v1 + 104);
  v105 = v6;
  v87 = 0;
  v90 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 93, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
  v7 = *(_QWORD *)(v1 + 32);
  v102 = v7;
  if ( *(_BYTE *)(v7 + 77) )
  {
    if ( *(_BYTE *)(v7 + 77) != 4 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 127, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
      SecurityInfo = -1073741634;
      goto LABEL_269;
    }
    if ( !*(_QWORD *)(v7 + 40) )
      *(_BYTE *)(v7 + 77) = 0;
  }
  Pool2 = (int *)ExAllocatePool2(258, 208, 1448240718);
  *(_QWORD *)(v1 + 40) = Pool2;
  v9 = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 94, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
    SecurityInfo = -1073741670;
    goto LABEL_268;
  }
  memset(Pool2, 0, 0xD0u);
  v11 = (struct _KMUTANT *)ExAllocatePool2(66, 56, 1498572366);
  *((_QWORD *)v9 + 23) = v11;
  if ( !v11 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 95, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
    SecurityInfo = -1073741670;
LABEL_267:
    ExFreePoolWithTag(v9, 0);
    *(_QWORD *)(v1 + 40) = 0;
LABEL_268:
    v7 = v102;
    v5 = v87;
LABEL_269:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 129, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
    *(_DWORD *)(a1 + 280) = SecurityInfo;
    *(_DWORD *)(a1 + 284) = SecurityInfo;
    if ( !v5 && *(_QWORD *)(v7 + 40) )
      *(_DWORD *)(a1 + 284) = 0;
    (*(void (__fastcall **)(__int64))(a1 + 272))(a1);
    return 259;
  }
  KeInitializeMutex(v11, 0);
  *((_BYTE *)v9 + 152) = 0;
  *v9 = 800;
  v9[1] = 936;
  *((_QWORD *)v9 + 21) = -1;
  v9[2] = 1120;
  v9[3] = 4;
  v9[5] = 0x100000;
  v9[6] = 0x2000;
  v9[7] = 0x100000;
  v9[29] = 493;
  v9[30] = 256;
  *((_BYTE *)v9 + 16) = 1;
  v9[8] = 924;
  *((_QWORD *)v9 + 18) = 50000000;
  memset(v94, 0, sizeof(v94));
  HIDWORD(v94[2]) = *v9 / 0x64u;
  LODWORD(v94[3]) = v9[3];
  HIDWORD(v94[3]) = *((unsigned __int8 *)v9 + 16);
  LODWORD(v94[4]) = v9[29];
  HIDWORD(v94[1]) = v9[5];
  LODWORD(v94[2]) = v9[7];
  LODWORD(v94[7]) = v9[8];
  HIDWORD(v94[7]) = v9[40];
  v13 = v9[30];
  if ( v13 == 256 )
    v13 = 0;
  LODWORD(v94[5]) = v13;
  v94[6] = *((_QWORD *)v9 + 18) / 10000000LL;
  v9[9] = *(_DWORD *)(v4 + 2332);
  v14 = *(_DWORD *)(v4 + 2336);
  v9[11] = 0;
  v9[10] = v14;
  v15 = *(_QWORD *)(a1 + 40);
  UnicodeString = 0;
  SecurityInfo = MdaGetSecurityInfo(v15, &UnicodeString, v107, v12, (HANDLE *)v9 + 21);
  if ( SecurityInfo < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 96, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
    goto LABEL_267;
  }
  v101 = 97;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 97, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids, &UnicodeString);
  v96 = *(_QWORD *)(a1 + 80);
  SecurityInfo = LsaGetLogonSessionData(&v96, &Buffer);
  if ( SecurityInfo < 0 )
  {
LABEL_263:
    RtlFreeUnicodeString(&UnicodeString);
    v80 = (void *)*((_QWORD *)v9 + 23);
    if ( v80 )
      ExFreePoolWithTag(v80, 0);
    v81 = (void *)*((_QWORD *)v9 + 21);
    if ( v81 != (void *)-1LL )
      ZwClose(v81);
    goto LABEL_267;
  }
  LsaFreeReturnBuffer(Buffer);
  *(_QWORD *)(v9 + 31) = v96;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        98,
        WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids,
        *(unsigned int *)(v1 + 76),
        *(_DWORD *)(v1 + 72));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        99,
        WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids,
        HIDWORD(v96),
        v96);
  }
  *((_BYTE *)v9 + 152) = *(_BYTE *)(*(_QWORD *)(a1 + 32) + 746LL) & 1;
  if ( (*(_DWORD *)(v4 + 2316) & 0x800) == 0
    && ((int)NfsReadRegistry(&stru_140041070, L"SOFTWARE\\Microsoft\\ServicesForNFS", (__int64)&v92, 4) >= 0 && v92
     || (int)NfsReadRegistry(&stru_140041070, L"SOFTWARE\\Microsoft\\ServicesForNFS", (__int64)&v92, 4) >= 0 && v92) )
  {
    v9[44] |= 1u;
  }
  LODWORD(v93) = 5;
  if ( v6 && v6[2] && v6[4]
    || *(_DWORD *)(a1 + 72) && (v17 = *(char **)(a1 + 64)) != 0 && (unsigned __int8)MdaIsEAPresent(v17) )
  {
    Registry = 0;
    v89 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      if ( v6 )
      {
        v19 = v6[4];
        v20 = v6[2];
      }
      else
      {
        v19 = 0;
        v20 = 0;
      }
      WPP_SF_qZZ(WPP_GLOBAL_Control->AttachedDevice, v20, v16, (_DWORD)v6, v19, v20);
    }
    v21 = *(unsigned int *)(a1 + 72);
    if ( (_DWORD)v21 )
    {
      v22 = *(_QWORD *)(a1 + 64);
      if ( v22 )
      {
        if ( (unsigned int)MdaParseEA(v22, v21, &v89, 4, "AuthType") )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 108, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
          }
          Registry = NfsReadRegistry(
                       &stru_140041070,
                       L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Auth",
                       (__int64)&v89,
                       4);
          if ( Registry < 0
            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 109, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
          }
        }
      }
    }
    if ( v89 != 5 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 112, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
      goto LABEL_75;
    }
    if ( v6 && v6[4] && v6[2] && v6[3] )
    {
      if ( (int)NfsRdrpVerifyCredentials((PDEVICE_OBJECT)v4) < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 110, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
LABEL_75:
        SecurityInfo = -1073741715;
        goto LABEL_263;
      }
    }
    else if ( Registry < 0 )
    {
      goto LABEL_78;
    }
    if ( (int)NfsRdrpNTAuthFromMRxCredentialOrToken(v4, a1, (_DWORD)v9, (_DWORD)v6, (__int64)v107) >= 0 )
    {
LABEL_82:
      v23 = *(unsigned int *)(a1 + 72);
      if ( (_DWORD)v23
        && (v24 = *(_QWORD *)(a1 + 64)) != 0
        && !(unsigned int)MdaParseEA(v24, v23, v94, 64, "MountOptions")
        || !(unsigned int)NuiCheckDefault(&v96, 2, 0) )
      {
        v25 = 100 * WORD2(v94[2]);
        *v9 = v25;
        v26 = 17 * v25 / 0x64u + v25;
        if ( v26 >= 0xEA60 )
          v26 = 60000;
        v9[1] = v26;
        v27 = 40 * v25 / 0x64u + v25;
        if ( v27 >= 0xEA60 )
          v27 = 60000;
        v9[2] = v27;
        v9[3] = LOWORD(v94[3]);
        *((_BYTE *)v9 + 16) = BYTE4(v94[3]);
        v9[29] = v94[4];
        v9[5] = HIDWORD(v94[1]);
        v9[6] = HIDWORD(v94[1]);
        v9[7] = v94[2];
        v9[8] = v94[7];
        v9[40] = HIDWORD(v94[7]);
        v28 = v94[5];
        if ( !LODWORD(v94[5]) )
          v28 = 256;
        v9[30] = v28;
        if ( (v94[7] & 0x10) != 0 )
          *((_QWORD *)v9 + 18) = 10000000LL * v94[6];
        else
          *((_QWORD *)v9 + 18) = 0;
      }
      if ( (v9[8] & 2) != 0 )
      {
        v29 = 0;
        v89 = 0;
      }
      else
      {
        v29 = v89;
      }
      if ( !v29 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 113, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
        v9[9] = *(_DWORD *)(v4 + 2332);
        v9[10] = *(_DWORD *)(v4 + 2336);
        v9[11] = 0;
        v29 = v89;
      }
      v9[39] = v29;
      goto LABEL_104;
    }
LABEL_78:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 111, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
    v89 = 0;
    goto LABEL_82;
  }
  if ( (unsigned int)NuiCheckDefault(v1 + 72, 1, v9 + 9) )
  {
    v40 = v9 + 9;
    if ( (int)MdaGetUserInfo(v9, v1, *(_QWORD *)(a1 + 32), &UnicodeString, v9 + 9, (__int64)v94) < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
    }
    v41 = 100 * WORD2(v94[2]);
    *v9 = v41;
    v42 = 17 * v41 / 0x64u + v41;
    if ( v42 >= 0xEA60 )
      v42 = 60000;
    v9[1] = v42;
    v43 = 40 * v41 / 0x64u + v41;
    if ( v43 >= 0xEA60 )
      v43 = 60000;
    v9[2] = v43;
    v9[3] = LOWORD(v94[3]);
    *((_BYTE *)v9 + 16) = BYTE4(v94[3]);
    v9[29] = v94[4];
    v9[5] = HIDWORD(v94[1]);
    v9[6] = HIDWORD(v94[1]);
    v9[7] = v94[2];
    v9[8] = v94[7];
    v9[40] = HIDWORD(v94[7]);
    v44 = v94[5];
    if ( !LODWORD(v94[5]) )
      v44 = 256;
    v9[30] = v44;
    v45 = 0;
    if ( (v94[7] & 0x10) != 0 )
      v45 = 10000000LL * v94[6];
    *((_QWORD *)v9 + 18) = v45;
    if ( (int)NfsReadRegistry(
                &stru_140041070,
                L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Auth",
                (__int64)&v89,
                4) < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 101, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
      v89 = 0;
    }
    if ( v89 != 5 )
      goto LABEL_172;
    v88[0] = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 102, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
    if ( (int)NfsRdrpGetUidGidFromPasswdGroup(v4, v6, v107, v9 + 9) < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 103, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
      if ( (unsigned int)NfsRdrGetUnixCredsFromMapSvr(a1, (_DWORD)v9, v46, (unsigned int)v107, (__int64)v88) == -1073741670 )
      {
        SecurityInfo = -1073741670;
        goto LABEL_263;
      }
      v47 = v88[0];
      v40 = v9 + 9;
    }
    else
    {
      v47 = 1;
    }
    if ( v47 )
      goto LABEL_172;
    v97 = 0;
    v91 = 0;
    v87 = 0;
    v88[0] = 0;
    v9[11] = 0;
    if ( (int)NfsRdrpGetUidGidFromLdap(
                v4,
                (_DWORD)v6,
                (unsigned int)v107,
                (unsigned int)&v97,
                (__int64)&v91,
                (__int64)&v87,
                (__int64)v88) < 0 )
      goto LABEL_168;
    v48 = v88[0];
    if ( v87 )
    {
      *v40 = v97;
    }
    else if ( !v88[0] )
    {
LABEL_168:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 104, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
      v89 = 0;
LABEL_172:
      if ( !v89 )
      {
        *v40 = *(_DWORD *)(v4 + 2332);
        *((_QWORD *)v9 + 5) = *(unsigned int *)(v4 + 2336);
      }
      goto LABEL_104;
    }
    if ( v48 )
      v9[10] = v91;
    goto LABEL_172;
  }
  if ( (unsigned int)NuiCheckDefault(v1 + 72, 2, 0) )
  {
    MdaGetDefaultMountInfo(v94);
    v56 = WORD2(v94[2]);
    v57 = 100 * WORD2(v94[2]);
    v58 = 1700 * WORD2(v94[2]);
    *v9 = v57;
    v59 = v58 / 0x64 + v57;
    if ( v59 >= 0xEA60 )
      v59 = 60000;
    v9[1] = v59;
    v60 = 4000 * v56 / 0x64u + v57;
    if ( v60 >= 0xEA60 )
      v60 = 60000;
    v9[2] = v60;
    v9[3] = LOWORD(v94[3]);
    *((_BYTE *)v9 + 16) = BYTE4(v94[3]);
    v9[29] = v94[4];
    v9[5] = HIDWORD(v94[1]);
    v9[6] = HIDWORD(v94[1]);
    v9[7] = v94[2];
    v9[8] = v94[7];
    v9[40] = HIDWORD(v94[7]);
    v61 = v94[5];
    if ( !LODWORD(v94[5]) )
      v61 = 256;
    v9[30] = v61;
    v62 = 0;
    if ( (v94[7] & 0x10) != 0 )
      v62 = 10000000LL * v94[6];
    *((_QWORD *)v9 + 18) = v62;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_dd(
          WPP_GLOBAL_Control->AttachedDevice,
          105,
          WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids,
          HIDWORD(v94[1]),
          v94[2]);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_ddd(
          WPP_GLOBAL_Control->AttachedDevice,
          106,
          WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids,
          HIDWORD(v94[2]),
          v94[3],
          HIDWORD(v94[3]));
    }
  }
  else
  {
    v49 = WORD2(v94[2]);
    v50 = 100 * WORD2(v94[2]);
    v51 = 1700 * WORD2(v94[2]);
    *v9 = v50;
    v52 = v51 / 0x64 + v50;
    if ( v52 >= 0xEA60 )
      v52 = 60000;
    v9[1] = v52;
    v53 = 4000 * v49 / 0x64u + v50;
    if ( v53 >= 0xEA60 )
      v53 = 60000;
    v9[2] = v53;
    v9[3] = LOWORD(v94[3]);
    *((_BYTE *)v9 + 16) = BYTE4(v94[3]);
    v9[29] = v94[4];
    v9[5] = HIDWORD(v94[1]);
    v9[6] = HIDWORD(v94[1]);
    v9[7] = v94[2];
    v9[8] = v94[7];
    v9[40] = HIDWORD(v94[7]);
    v54 = v94[5];
    if ( !LODWORD(v94[5]) )
      v54 = 256;
    v9[30] = v54;
    v55 = 0;
    if ( (v94[7] & 0x10) != 0 )
      v55 = 10000000LL * v94[6];
    *((_QWORD *)v9 + 18) = v55;
  }
LABEL_104:
  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 32) + 32LL) + 32LL) + 80LL) == 17 )
  {
    v30 = v9[7];
    if ( v30 > 0xFC00 )
      v30 = 64512;
    v9[7] = v30;
    v31 = v9[5];
    if ( v31 > 0xFC00 )
      v31 = 64512;
    v9[5] = v31;
    v32 = v9[6];
    if ( v32 > 0xFC00 )
      v32 = 64512;
    v9[6] = v32;
  }
  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 32) + 32LL) + 32LL) + 88LL) == 2 )
  {
    v33 = v9[5];
    if ( v33 > 0x2000 )
      v33 = 0x2000;
    v9[5] = v33;
    v34 = v9[6];
    if ( v34 > 0x2000 )
      v34 = 0x2000;
    v9[6] = v34;
    v35 = v9[7];
    if ( v35 > 0x2000 )
      v35 = 0x2000;
    v9[7] = v35;
  }
  if ( (v9[8] & 1) != 0 && !*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 32) + 32LL) + 32LL) + 160LL) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 114, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
    v9[8] &= ~1u;
    RxLogEventDirect((PRDBSS_DEVICE_OBJECT)v4, 0, 0x80004000, -1073741637, 0xE0Bu);
  }
  v36 = v102;
  if ( *(_QWORD *)(v102 + 40) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 116, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
    v63 = *(_QWORD *)(v36 + 40);
    v87 = 0;
  }
  else
  {
    v37 = *(_QWORD *)(a1 + 32);
    v87 = 1;
    SecurityInfo = MdaCreateNetRoot(v37);
    if ( SecurityInfo < 0 )
    {
      v38 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_263;
      v39 = 115;
      goto LABEL_131;
    }
    *(_DWORD *)(v36 + 56) &= ~0x10u;
    v63 = *(_QWORD *)(v36 + 40);
    NfsGetAttributes(v1, *(_QWORD *)(a1 + 32), *(_QWORD *)(v63 + 40));
    v64 = *(_QWORD *)(v63 + 40);
    if ( v64 )
      *(_DWORD *)(v64 + 284) |= 0x10u;
  }
  SecurityInfo = NfsRdrpInitializeSecurityContext(v100, v1);
  if ( SecurityInfo < 0 )
  {
    v38 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_263;
    v39 = 118;
LABEL_131:
    WPP_SF_d(v38->AttachedDevice, v39, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
    goto LABEL_263;
  }
  v66 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 48LL);
  v67 = *(_QWORD *)(v66 + 48);
  v68 = *(_WORD *)(v67 + 88);
  if ( v68 > 0x28u )
  {
    v65 = *(_WORD **)(v67 + 96);
    if ( *v65 == 92 && v65[1] == 59 && v65[3] == 58 )
    {
      v69 = 0;
      while ( 1 )
      {
        v70 = v65[v69 + 4];
        if ( (unsigned __int16)(v70 - 48) > 9u
          && (unsigned __int16)(v70 - v101) > (unsigned __int16)v93
          && (unsigned __int16)(v70 - 65) > 5u )
        {
          break;
        }
        if ( ++v69 >= 16 )
        {
          if ( v69 != 16 )
            break;
          v71 = **(_WORD **)(v102 + 88) + 40;
          v72 = v68 - v71;
          LOWORD(v98[0]) = v72;
          if ( v72 )
          {
            HIWORD(v98[0]) = v72;
            v99 = *(_QWORD *)(v67 + 96) + v71;
          }
          goto LABEL_225;
        }
      }
    }
  }
  v72 = v98[0];
LABEL_225:
  if ( (*(_DWORD *)(v66 + 16) & 0x80u) == 0 )
  {
    v72 = 0;
    LOWORD(v98[0]) = 0;
  }
  v93 = 0;
  *(_OWORD *)P = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
  {
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 119, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids, v98);
    v72 = v98[0];
  }
  if ( v72 )
  {
    LOBYTE(v65) = 1;
    v73 = MdaParsePathFast(
            v1,
            *(_QWORD *)(a1 + 32),
            (int)v98,
            (int)v65,
            (__int64)&v93,
            (PUNICODE_STRING)P,
            (__int64)&v90,
            0);
    SecurityInfo = v73;
    if ( v73 == 260 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 120, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
      ExFreePoolWithTag(P[1], 0);
      SecurityInfo = -1073741275;
      goto LABEL_263;
    }
    if ( v73 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 121, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
      goto LABEL_263;
    }
    HacDereference(v100, v93);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 122, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
  if ( v6 && v6[4] && v6[2] && v6[3] && v89 )
  {
    ExAcquireFastMutex(*(PFAST_MUTEX *)(v63 + 48));
    v74 = (__int64 *)(v63 + 56);
    v75 = *(__int64 **)(v63 + 56);
    v93 = (__int64)v75;
    v76 = (__int64)v75;
    v77 = v75;
    while ( (__int64 *)v76 != v74 )
    {
      if ( v9[31] == v77[4] && v9[32] == v77[5] )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 123, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
        SecurityInfo = NfsRdrpCompareEAs(v100, v105, (__int64)v75);
        if ( SecurityInfo < 0 )
        {
          ExReleaseFastMutex(*(PFAST_MUTEX *)(v63 + 48));
          v78 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            v79 = 125;
            goto LABEL_261;
          }
          goto LABEL_262;
        }
        ++v77[6];
        goto LABEL_285;
      }
      v76 = *v75;
      v75 = (__int64 *)v76;
      v93 = v76;
      v77 = (_DWORD *)v76;
    }
    SecurityInfo = NfsRdrpCaptureEAs(&v93, v100, v105, v9);
    if ( SecurityInfo < 0 )
    {
      ExReleaseFastMutex(*(PFAST_MUTEX *)(v63 + 48));
      v78 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v79 = 124;
LABEL_261:
        WPP_SF_sD(
          v78->AttachedDevice,
          v79,
          (unsigned int)WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids,
          (unsigned int)v108,
          SecurityInfo);
      }
LABEL_262:
      v1 = v95;
      goto LABEL_263;
    }
    v83 = *v74;
    if ( *(__int64 **)(*v74 + 8) != v74 )
      __fastfail(3u);
    v84 = v93;
    *(_QWORD *)v93 = v83;
    *(_QWORD *)(v84 + 8) = v74;
    *(_QWORD *)(v83 + 8) = v84;
    *v74 = v84;
LABEL_285:
    ExReleaseFastMutex(*(PFAST_MUTEX *)(v63 + 48));
    v1 = v95;
  }
  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 32) + 32LL) + 32LL) + 88LL) == 3 )
  {
    V3StatInfo = NfsRdrpGetV3StatInfo(a1, v1, v63, v9);
    if ( V3StatInfo < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_sD(
        WPP_GLOBAL_Control->AttachedDevice,
        126,
        (unsigned int)WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids,
        (unsigned int)v108,
        V3StatInfo);
    }
  }
  v91 = 0;
  if ( (int)NfsReadRegistry(
              &stru_140041070,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Defaults",
              (__int64)&v91,
              4) >= 0
    && v91 )
  {
    v9[8] |= 0x200000u;
  }
  else
  {
    v9[8] &= ~0x200000u;
  }
  RtlFreeUnicodeString(&UnicodeString);
  _InterlockedAdd((volatile signed __int32 *)(v63 + 248), 1u);
  _InterlockedAdd((volatile signed __int32 *)(v63 + 252), 1u);
  if ( v63 )
    *(_DWORD *)(v63 + 256) |= 2u;
  v9[44] |= 0x20u;
  v86 = *(void (__fastcall **)(__int64))(a1 + 272);
  *(_QWORD *)(a1 + 280) = 0;
  v86(a1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 128, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
  return 259;
}

```

## disassembly

```asm
0x140025be0  push    rbp
0x140025be2  push    rbx
0x140025be3  push    rsi
0x140025be4  push    rdi
0x140025be5  push    r12
0x140025be7  push    r13
0x140025be9  push    r14
0x140025beb  push    r15
0x140025bed  lea     rbp, [rsp-98h]
0x140025bf5  sub     rsp, 198h
0x140025bfc  mov     rax, cs:__security_cookie
0x140025c03  xor     rax, rsp
0x140025c06  mov     [rbp+0D0h+var_48], rax
0x140025c0d  mov     r12, [rcx+108h]
0x140025c14  xor     edx, edx; Val
0x140025c16  movzx   eax, word ptr cs:aMdacreatevnetr+10h; "t"
0x140025c1d  mov     r15, rcx
0x140025c20  movups  xmm0, xmmword ptr cs:aMdacreatevnetr; "MdaCreateVNetRoot"
0x140025c27  mov     word ptr [rbp+0D0h+var_60+10h], ax
0x140025c2e  mov     rax, [rcx+20h]
0x140025c32  lea     r8d, [rdx+40h]; Size
0x140025c36  movups  xmmword ptr [rbp+0D0h+var_60], xmm0
0x140025c3a  lea     rcx, [rsp+1D0h+var_170]; void *
0x140025c3f  mov     [rbp+0D0h+var_130], r12
0x140025c43  mov     r14, [rax+50h]
0x140025c47  mov     [rbp+0D0h+var_108], r14
0x140025c4b  call    memset
0x140025c50  xor     edi, edi
0x140025c52  xorps   xmm0, xmm0
0x140025c55  mov     [rbp+0D0h+var_128], rdi
0x140025c59  mov     sil, dil
0x140025c5c  movups  xmmword ptr [rbp+0D0h+UnicodeString.Length], xmm0
0x140025c60  mov     qword ptr [rbp+0D0h+var_118], rdi
0x140025c64  mov     [rbp+0D0h+var_110], rdi
0x140025c68  mov     dword ptr [rsp+1D0h+var_18C], edi
0x140025c6c  mov     dword ptr [rsp+1D0h+var_184+4], edi
0x140025c70  mov     [rbp+0D0h+Buffer], rdi
0x140025c74  mov     r13, [r12+68h]
0x140025c79  mov     [rbp+0D0h+var_D8], r13
0x140025c7d  mov     [rsp+1D0h+var_190], dil
0x140025c82  mov     byte ptr [rsp+1D0h+var_18C+4], dil
0x140025c87  mov     rcx, cs:WPP_GLOBAL_Control
0x140025c8e  lea     rdx, WPP_GLOBAL_Control
0x140025c95  cmp     rcx, rdx
0x140025c98  jz      short loc_140025CBB
0x140025c9a  mov     eax, [rcx+2Ch]
0x140025c9d  test    al, 8
0x140025c9f  jz      short loc_140025CBB
0x140025ca1  mov     rcx, [rcx+18h]
0x140025ca5  lea     edx, [rdi+5Dh]
0x140025ca8  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x140025caf  call    WPP_SF_
0x140025cb4  lea     rdx, WPP_GLOBAL_Control
0x140025cbb  mov     rbx, [r12+20h]
0x140025cc0  mov     [rbp+0D0h+var_F8], rbx
0x140025cc4  movzx   r9d, byte ptr [rbx+4Dh]
0x140025cc9  mov     ecx, r9d
0x140025ccc  test    r9d, r9d
0x140025ccf  jz      short loc_140025CEF
0x140025cd1  sub     ecx, 1
0x140025cd4  jz      short loc_140025D53
0x140025cd6  sub     ecx, 1
0x140025cd9  jz      short loc_140025D53
0x140025cdb  sub     ecx, 1
0x140025cde  jz      short loc_140025D53
0x140025ce0  cmp     ecx, 1
0x140025ce3  jnz     short loc_140025D53
0x140025ce5  cmp     [rbx+28h], rdi
0x140025ce9  jnz     short loc_140025CEF
0x140025ceb  mov     [rbx+4Dh], dil
0x140025cef  mov     esi, 0D0h
0x140025cf4  mov     r8d, 5652664Eh
0x140025cfa  mov     edx, esi
0x140025cfc  lea     ecx, [rsi+32h]
0x140025cff  call    cs:__imp_ExAllocatePool2
0x140025d06  nop     dword ptr [rax+rax+00h]
0x140025d0b  mov     [r12+28h], rax
0x140025d10  mov     rbx, rax
0x140025d13  test    rax, rax
0x140025d16  jnz     short loc_140025D85
0x140025d18  mov     rcx, cs:WPP_GLOBAL_Control
0x140025d1f  lea     rax, WPP_GLOBAL_Control
0x140025d26  cmp     rcx, rax
0x140025d29  jz      short loc_140025D49
0x140025d2b  mov     eax, [rcx+2Ch]
0x140025d2e  lea     esi, [rbx+1]
0x140025d31  test    sil, al
0x140025d34  jz      short loc_140025D49
0x140025d36  mov     rcx, [rcx+18h]
0x140025d3a  lea     edx, [rbx+5Eh]
0x140025d3d  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x140025d44  call    WPP_SF_
0x140025d49  mov     edi, 0C000009Ah
0x140025d4e  jmp     loc_140026FD8
0x140025d53  mov     rcx, cs:WPP_GLOBAL_Control
0x140025d5a  cmp     rcx, rdx
0x140025d5d  jz      short loc_140025D7B
0x140025d5f  mov     eax, [rcx+2Ch]
0x140025d62  test    al, 2
0x140025d64  jz      short loc_140025D7B
0x140025d66  mov     rcx, [rcx+18h]
0x140025d6a  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x140025d71  mov     edx, 7Fh
0x140025d76  call    WPP_SF_d
0x140025d7b  mov     edi, 0C00000BEh
0x140025d80  jmp     loc_140026FE1
0x140025d85  mov     r8, rsi; Size
0x140025d88  xor     edx, edx; Val
0x140025d8a  mov     rcx, rbx; void *
0x140025d8d  call    memset
0x140025d92  mov     edx, 38h ; '8'
0x140025d97  mov     r8d, 5952664Eh
0x140025d9d  lea     ecx, [rdx+0Ah]
0x140025da0  call    cs:__imp_ExAllocatePool2
0x140025da7  nop     dword ptr [rax+rax+00h]
0x140025dac  mov     [rbx+0B8h], rax
0x140025db3  test    rax, rax
0x140025db6  jnz     short loc_140025DF5
0x140025db8  mov     rcx, cs:WPP_GLOBAL_Control
0x140025dbf  lea     rax, WPP_GLOBAL_Control
0x140025dc6  cmp     rcx, rax
0x140025dc9  jz      short loc_140025DEB
0x140025dcb  mov     eax, [rcx+2Ch]
0x140025dce  mov     esi, 1
0x140025dd3  test    sil, al
0x140025dd6  jz      short loc_140025DEB
0x140025dd8  mov     rcx, [rcx+18h]
0x140025ddc  lea     edx, [rsi+5Eh]
0x140025ddf  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x140025de6  call    WPP_SF_
0x140025deb  mov     edi, 0C000009Ah
0x140025df0  jmp     loc_140026FBE
0x140025df5  xor     edx, edx; Level
0x140025df7  mov     rcx, rax; Mutex
0x140025dfa  call    cs:__imp_KeInitializeMutex
0x140025e01  nop     dword ptr [rax+rax+00h]
0x140025e06  mov     eax, 100000h
0x140025e0b  mov     byte ptr [rbx+98h], 0
0x140025e12  mov     esi, 1
0x140025e17  mov     dword ptr [rbx], 320h
0x140025e1d  lea     rdi, [rbx+0A8h]
0x140025e24  mov     dword ptr [rbx+4], 3A8h
0x140025e2b  xor     edx, edx; Val
0x140025e2d  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x140025e34  lea     rcx, [rsp+1D0h+var_170]; void *
0x140025e39  mov     dword ptr [rbx+8], 460h
0x140025e40  lea     r8d, [rsi+3Fh]; Size
0x140025e44  mov     dword ptr [rbx+0Ch], 4
0x140025e4b  mov     [rbx+14h], eax
0x140025e4e  mov     dword ptr [rbx+18h], 2000h
0x140025e55  mov     [rbx+1Ch], eax
0x140025e58  mov     dword ptr [rbx+74h], 1EDh
0x140025e5f  mov     dword ptr [rbx+78h], 100h
0x140025e66  mov     [rbx+10h], sil
0x140025e6a  mov     dword ptr [rbx+20h], 39Ch
0x140025e71  mov     qword ptr [rbx+90h], 2FAF080h
0x140025e7c  call    memset
0x140025e81  xor     r8d, r8d
0x140025e84  mov     qword ptr [rsp+1D0h+Line], rdi
0x140025e89  mov     eax, 51EB851Fh
0x140025e8e  xorps   xmm0, xmm0
0x140025e91  mul     dword ptr [rbx]
0x140025e93  shr     edx, 5
0x140025e96  mov     [rsp+1D0h+var_15C], edx
0x140025e9a  mov     eax, [rbx+0Ch]
0x140025e9d  mov     [rsp+1D0h+var_158], eax
0x140025ea1  movzx   eax, byte ptr [rbx+10h]
0x140025ea5  mov     [rsp+1D0h+var_154], eax
0x140025ea9  mov     eax, [rbx+74h]
0x140025eac  mov     [rbp+0D0h+var_150], eax
0x140025eaf  mov     eax, [rbx+14h]
0x140025eb2  mov     [rsp+1D0h+var_164], eax
0x140025eb6  mov     eax, [rbx+1Ch]
0x140025eb9  mov     [rsp+1D0h+var_160], eax
0x140025ebd  mov     eax, [rbx+20h]
0x140025ec0  mov     [rbp+0D0h+var_138], eax
0x140025ec3  mov     eax, [rbx+0A0h]
0x140025ec9  mov     [rbp+0D0h+var_134], eax
0x140025ecc  mov     rax, 0D6BF94D5E57A42BDh
0x140025ed6  mov     ecx, [rbx+78h]
0x140025ed9  cmp     ecx, 100h
0x140025edf  cmovz   ecx, r8d
0x140025ee3  mov     [rbp+0D0h+var_148], ecx
0x140025ee6  mov     rcx, [rbx+90h]
0x140025eed  imul    rcx
0x140025ef0  add     rdx, rcx
0x140025ef3  sar     rdx, 17h
0x140025ef7  mov     rax, rdx
0x140025efa  shr     rax, 3Fh
0x140025efe  add     rdx, rax
0x140025f01  mov     [rbp+0D0h+var_140], rdx
0x140025f05  lea     rdx, [rbp+0D0h+UnicodeString]
0x140025f09  mov     eax, [r14+91Ch]
0x140025f10  mov     [rbx+24h], eax
0x140025f13  mov     eax, [r14+920h]
0x140025f1a  mov     [rbx+2Ch], r8d
0x140025f1e  lea     r8, [rbp+0D0h+var_C0]
0x140025f22  mov     [rbx+28h], eax
0x140025f25  mov     rcx, [r15+28h]
0x140025f29  movups  xmmword ptr [rbp+0D0h+UnicodeString.Length], xmm0
0x140025f2d  call    MdaGetSecurityInfo
0x140025f32  mov     edi, eax
0x140025f34  test    eax, eax
0x140025f36  jns     short loc_140025F77
0x140025f38  mov     r10, cs:WPP_GLOBAL_Control
0x140025f3f  lea     rax, WPP_GLOBAL_Control
0x140025f46  cmp     r10, rax
0x140025f49  jz      loc_140026FBE
0x140025f4f  mov     ecx, [r10+2Ch]
0x140025f53  test    sil, cl
0x140025f56  jz      loc_140026FBE
0x140025f5c  mov     rcx, [r10+18h]
0x140025f60  lea     edx, [rsi+5Fh]
0x140025f63  mov     r9d, edi
0x140025f66  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x140025f6d  call    WPP_SF_d
0x140025f72  jmp     loc_140026FBE
0x140025f77  mov     rcx, cs:WPP_GLOBAL_Control
0x140025f7e  lea     rax, WPP_GLOBAL_Control
0x140025f85  mov     edx, 61h ; 'a'
0x140025f8a  mov     [rbp+0D0h+var_100], edx
0x140025f8d  cmp     rcx, rax
0x140025f90  jz      short loc_140025FAD
0x140025f92  mov     eax, [rcx+2Ch]
0x140025f95  test    al, 4
0x140025f97  jz      short loc_140025FAD
0x140025f99  mov     rcx, [rcx+18h]
0x140025f9d  lea     r9, [rbp+0D0h+UnicodeString]
0x140025fa1  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x140025fa8  call    WPP_SF_Z
0x140025fad  mov     rax, [r15+50h]
0x140025fb1  lea     rdx, [rbp+0D0h+Buffer]
0x140025fb5  lea     rcx, [rbp+0D0h+var_128]
0x140025fb9  mov     [rbp+0D0h+var_128], rax
0x140025fbd  call    cs:__imp_LsaGetLogonSessionData
0x140025fc4  nop     dword ptr [rax+rax+00h]
0x140025fc9  mov     edi, eax
0x140025fcb  test    eax, eax
0x140025fcd  js      loc_140026F7B
0x140025fd3  mov     rcx, [rbp+0D0h+Buffer]; Buffer
0x140025fd7  call    cs:__imp_LsaFreeReturnBuffer
0x140025fde  nop     dword ptr [rax+rax+00h]
0x140025fe3  mov     rax, [rbp+0D0h+var_128]
0x140025fe7  mov     [rbx+7Ch], rax
0x140025feb  mov     rcx, cs:WPP_GLOBAL_Control
0x140025ff2  lea     rdi, WPP_GLOBAL_Control
0x140025ff9  cmp     rcx, rdi
0x140025ffc  jz      short loc_14002605B
0x140025ffe  mov     eax, [rcx+2Ch]
0x140026001  test    al, 4
0x140026003  jz      short loc_140026028
0x140026005  mov     eax, [r12+48h]
0x14002600a  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x140026011  mov     r9d, [r12+4Ch]
0x140026016  mov     edx, 62h ; 'b'
0x14002601b  mov     rcx, [rcx+18h]
0x14002601f  mov     [rsp+1D0h+Line], eax
0x140026023  call    WPP_SF_dd
0x140026028  mov     rcx, cs:WPP_GLOBAL_Control
0x14002602f  cmp     rcx, rdi
0x140026032  jz      short loc_14002605B
0x140026034  mov     eax, [rcx+2Ch]
0x140026037  test    al, 4
0x140026039  jz      short loc_14002605B
0x14002603b  mov     eax, dword ptr [rbp+0D0h+var_128]
0x14002603e  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x140026045  mov     r9d, dword ptr [rbp+0D0h+var_128+4]
0x140026049  mov     edx, 63h ; 'c'
0x14002604e  mov     rcx, [rcx+18h]
0x140026052  mov     [rsp+1D0h+Line], eax
0x140026056  call    WPP_SF_dd
0x14002605b  mov     rax, [r15+20h]
0x14002605f  mov     cl, [rax+2EAh]
0x140026065  and     cl, sil
0x140026068  mov     [rbx+98h], cl
0x14002606e  test    dword ptr [r14+90Ch], 800h
0x140026079  jnz     loc_140026109
0x14002607f  lea     rax, [rsp+1D0h+var_184+4]
0x140026084  mov     dword ptr [rsp+1D0h+Destination], 4; int
0x14002608c  mov     r9d, 4
0x140026092  mov     qword ptr [rsp+1D0h+Line], rax; __int64
0x140026097  lea     r8, aRfc2307; "Rfc2307"
0x14002609e  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\ServicesForNFS"
0x1400260a5  lea     rcx, stru_140041070; SourceString
0x1400260ac  call    NfsReadRegistry
0x1400260b1  xor     r10d, r10d
0x1400260b4  test    eax, eax
0x1400260b6  js      short loc_1400260C7
0x1400260b8  cmp     dword ptr [rsp+1D0h+var_184+4], r10d
0x1400260bd  jz      short loc_1400260C7
0x1400260bf  or      [rbx+0B0h], esi
0x1400260c5  jmp     short loc_14002610C
0x1400260c7  lea     rax, [rsp+1D0h+var_184+4]
0x1400260cc  mov     dword ptr [rsp+1D0h+Destination], 4; int
0x1400260d4  mov     r9d, 4
0x1400260da  mov     qword ptr [rsp+1D0h+Line], rax; __int64
0x1400260df  lea     r8, aRfc2307ldaploo; "Rfc2307LdapLookup"
0x1400260e6  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\ServicesForNFS"
0x1400260ed  lea     rcx, stru_140041070; SourceString
0x1400260f4  call    NfsReadRegistry
  ... truncated ...
```
