# appIsolation::EnterpriseDomainProtection::UpdatePolicy(void)

- ea: `0x1800c3ea0`
- end: `0x1800c4cb4`
- name: `?UpdatePolicy@EnterpriseDomainProtection@appIsolation@@QEAAKXZ`
- size: `3604`
- prototype: `unsigned int __fastcall(appIsolation::EnterpriseDomainProtection *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800beec0`

## callees

- `0x1800089bc`
- `0x18000a66c`
- `0x18000a710`
- `0x1800192e0`
- `0x180066b2c`
- `0x1800729c0`
- `0x1800c090c`
- `0x1800c2f20`
- `0x1800c3110`
- `0x1800c3410`
- `0x1800c3710`
- `0x1800c3a50`
- `0x1800c3b14`
- `0x1800c3ea0`
- `0x1800c53e4`

## import_xrefs

- `wkscli!NetGetJoinInformation` at `0x1800c417f`
- `wkscli!NetGetJoinInformation` at `0x1800c417f`
- `netutils!NetApiBufferFree` at `0x1800c419f`
- `netutils!NetApiBufferFree` at `0x1800c419f`
- `fwbase!FwHResultToWindowsError` at `0x1800c4347`
- `fwbase!FwHResultToWindowsError` at `0x1800c43a9`
- `fwbase!FwHResultToWindowsError` at `0x1800c440b`
- `fwbase!FwHResultToWindowsError` at `0x1800c4983`
- `fwbase!FwHResultToWindowsError` at `0x1800c4347`
- `fwbase!FwHResultToWindowsError` at `0x1800c43a9`
- `fwbase!FwHResultToWindowsError` at `0x1800c440b`
- `fwbase!FwHResultToWindowsError` at `0x1800c4983`
- `fwbase!FwAllocCheckSize` at `0x1800c4975`
- `fwbase!FwAllocCheckSize` at `0x1800c4975`
- `fwbase!FwAlloc` at `0x1800c4201`
- `fwbase!FwAlloc` at `0x1800c4201`
- `fwbase!FwCriticalSectionEnter` at `0x1800c40f2`
- `fwbase!FwCriticalSectionEnter` at `0x1800c40f2`
- `fwbase!FwCriticalSectionLeave` at `0x1800c4c4d`
- `fwbase!FwCriticalSectionLeave` at `0x1800c4c4d`
- `fwbase!FwFree` at `0x1800c4a15`
- `fwbase!FwFree` at `0x1800c4bdb`
- `fwbase!FwFree` at `0x1800c4c27`
- `fwbase!FwFree` at `0x1800c4c37`
- `fwbase!FwFree` at `0x1800c4a15`
- `fwbase!FwFree` at `0x1800c4bdb`
- `fwbase!FwFree` at `0x1800c4c27`
- `fwbase!FwFree` at `0x1800c4c37`
- `fwbase!FwRegSetDWord` at `0x1800c4b55`
- `fwbase!FwRegSetDWord` at `0x1800c4b55`
- `FWPolicyIOMgr!FwCopyRule` at `0x1800c4339`
- `FWPolicyIOMgr!FwCopyRule` at `0x1800c439b`
- `FWPolicyIOMgr!FwCopyRule` at `0x1800c43fd`
- `FWPolicyIOMgr!FwCopyRule` at `0x1800c4339`
- `FWPolicyIOMgr!FwCopyRule` at `0x1800c439b`
- `FWPolicyIOMgr!FwCopyRule` at `0x1800c43fd`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800c49e1`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800c49f9`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800c49e1`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800c49f9`
- `FWPolicyIOMgr!FwBinariesFree` at `0x1800c4bf2`
- `FWPolicyIOMgr!FwBinariesFree` at `0x1800c4c10`
- `FWPolicyIOMgr!FwBinariesFree` at `0x1800c4bf2`
- `FWPolicyIOMgr!FwBinariesFree` at `0x1800c4c10`

## string_xrefs

- `0x1800c413d`: `FwMoneisDeleteInterfaceContainer`
- `0x1800c40c6`: `FwMoneisEdpGetConfig`
- `0x1800c4b46`: `SYSTEM\CurrentControlSet\Services\mpssvc\Parameters\ACService`

## pseudocode

```c
__int64 __fastcall appIsolation::EnterpriseDomainProtection::UpdatePolicy(
        appIsolation::EnterpriseDomainProtection *this)
{
  _OWORD *v2; // rax
  const wchar_t *v3; // rcx
  unsigned int v4; // edi
  __int64 v5; // rdx
  __int128 v6; // xmm0
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int64 v15; // r12
  __int128 v16; // xmm1
  __int64 v17; // r15
  __int64 v18; // r14
  __int128 v19; // xmm0
  __int64 v20; // rsi
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  int Config; // ebx
  __int64 v26; // rcx
  int v27; // edx
  const char *v28; // rax
  appIsolation::EnterpriseDomainProtection *v29; // rsi
  DWORD JoinInformation; // eax
  __int64 v31; // rax
  size_t v33; // rbx
  __int64 v34; // r13
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  const wchar_t *v39; // rcx
  __int64 v40; // r13
  unsigned int v41; // eax
  appIsolation::EnterpriseDomainProtection *v42; // rcx
  unsigned int v43; // eax
  appIsolation::EnterpriseDomainProtection *v44; // rcx
  unsigned int v45; // eax
  appIsolation::EnterpriseDomainProtection *v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  _QWORD *v50; // rcx
  _QWORD *v51; // rbx
  _QWORD *v52; // rax
  _QWORD *v53; // rax
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // r9
  unsigned int v57; // eax
  __int64 v58; // rcx
  STRSAFE_LPWSTR v59; // rax
  _QWORD *v60; // r8
  unsigned int v61; // r9d
  __int64 v62; // rcx
  __int64 v63; // r10
  _QWORD *v64; // rax
  __int64 v65; // rdx
  __int128 v66; // xmm0
  int v67; // ecx
  unsigned int v70; // [rsp+58h] [rbp-A8h] BYREF
  int v71; // [rsp+5Ch] [rbp-A4h] BYREF
  int v72; // [rsp+60h] [rbp-A0h] BYREF
  STRSAFE_LPWSTR v73; // [rsp+68h] [rbp-98h]
  int v74; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v75; // [rsp+78h] [rbp-88h] BYREF
  __int64 v76; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v77; // [rsp+88h] [rbp-78h] BYREF
  __int64 v78; // [rsp+90h] [rbp-70h] BYREF
  __int64 v79; // [rsp+98h] [rbp-68h] BYREF
  __int64 v80; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v81; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v82; // [rsp+B0h] [rbp-50h]
  __int64 v83; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v84; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD *v85; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD *v86; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v87; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v88; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v89; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v90; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v91; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v92; // [rsp+100h] [rbp+0h] BYREF
  __int64 v93; // [rsp+108h] [rbp+8h] BYREF
  __int64 v94; // [rsp+110h] [rbp+10h] BYREF
  __int64 v95; // [rsp+118h] [rbp+18h] BYREF
  __int128 v96; // [rsp+120h] [rbp+20h] BYREF
  __int128 v97; // [rsp+130h] [rbp+30h] BYREF
  __int128 v98; // [rsp+140h] [rbp+40h] BYREF
  LPWSTR NameBuffer; // [rsp+150h] [rbp+50h] BYREF
  int v100; // [rsp+158h] [rbp+58h] BYREF
  enum _NETSETUP_JOIN_STATUS BufferType; // [rsp+15Ch] [rbp+5Ch] BYREF
  __int64 v102; // [rsp+160h] [rbp+60h] BYREF
  wchar_t v103; // [rsp+168h] [rbp+68h]
  _BYTE v104[880]; // [rsp+170h] [rbp+70h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, WPP_8a4c25f4ce093197c3f0fcd6b5570cca_Traceguids);
  ++g_invokedAddAllowEnterpriseIdRule;
  v2 = v104;
  v3 = L"O:SYG:SYD:(A;;0x1;;;AC)(A;;0x1;;;S-1-15-3-1)(A;;0x1;;;S-1-15-3-2)(A;;0x1;;;S-1-15-3-3)(A;;0x1;;;S-1-15-3-42147683"
        "33-1334025770-122408079-3919188833)(XA;;0x1;;;WD;(!(Exists EDP://EvaluationFlags) ||  (Exists EDP://PolicyFlags "
        "&& EDP://PolicyFlags == 0x1) || (Exists EDP://PolicyFlags && EDP://PolicyFlags == 0x11) || ((!(Exists EDP://Poli"
        "cyFlags) || EDP://PolicyFlags == 0xa) && Exists EDP://EnterpriseIds && EDP://EnterpriseIds contains \"";
  NameBuffer = 0;
  v4 = 6;
  BufferType = NetSetupUnknownStatus;
  v97 = 0;
  v5 = 6;
  do
  {
    v2 += 8;
    v6 = *(_OWORD *)v3;
    v7 = *((_OWORD *)v3 + 1);
    v3 += 64;
    *(v2 - 8) = v6;
    v8 = *((_OWORD *)v3 - 6);
    *(v2 - 7) = v7;
    v9 = *((_OWORD *)v3 - 5);
    *(v2 - 6) = v8;
    v10 = *((_OWORD *)v3 - 4);
    *(v2 - 5) = v9;
    v11 = *((_OWORD *)v3 - 3);
    *(v2 - 4) = v10;
    v12 = *((_OWORD *)v3 - 2);
    *(v2 - 3) = v11;
    v13 = *((_OWORD *)v3 - 1);
    *(v2 - 2) = v12;
    *(v2 - 1) = v13;
    --v5;
  }
  while ( v5 );
  v14 = *(_OWORD *)v3;
  v73 = 0;
  v15 = 0;
  v16 = *((_OWORD *)v3 + 1);
  v100 = 29032891;
  v17 = 0;
  *v2 = v14;
  v75 = 0;
  v18 = 0;
  v19 = *((_OWORD *)v3 + 2);
  v77 = 0;
  v20 = 0;
  v2[1] = v16;
  v78 = 0;
  v21 = *((_OWORD *)v3 + 3);
  v79 = 0;
  v2[2] = v19;
  v85 = 0;
  v22 = *((_OWORD *)v3 + 4);
  v86 = 0;
  v2[3] = v21;
  v80 = 0;
  v23 = *((_OWORD *)v3 + 5);
  v81 = 0;
  v2[4] = v22;
  v76 = 0;
  v24 = *(_OWORD *)(v3 + 47);
  v83 = 0;
  v2[5] = v23;
  v84 = 0;
  *(_OWORD *)((char *)v2 + 94) = v24;
  v102 = *(_QWORD *)L"\")))";
  v103 = asc_180108BE0[4];
  v96 = 0;
  v91 = 0;
  v92 = 0;
  v93 = 0;
  v87 = 0;
  v88 = 0;
  v94 = 0;
  v98 = 0;
  v74 = 0;
  v70 = 0;
  v72 = 0;
  v71 = 0;
  v90 = 0;
  v95 = 0;
  _InterlockedIncrement((volatile signed __int32 *)this + 12);
  Config = FwMoneisEdpGetConfig(
             (unsigned int)&v96,
             (unsigned int)&v98,
             (unsigned int)&v74,
             (unsigned int)&v70,
             (__int64)&v72,
             (__int64)&v71,
             (__int64)&v90,
             (__int64)&v95);
  if ( Config )
  {
    v72 = 0;
    v26 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_11;
    v27 = 20;
    v28 = "FwMoneisEdpGetConfig";
LABEL_10:
    WPP_SF_Ds(
      *(_QWORD *)(v26 + 16),
      v27,
      (unsigned int)WPP_8a4c25f4ce093197c3f0fcd6b5570cca_Traceguids,
      Config,
      (__int64)v28);
LABEL_11:
    v29 = this;
    goto LABEL_116;
  }
  FwCriticalSectionEnter(this);
  v72 = 1;
  Config = FwMoneisDeleteInterfaceContainer(0, 0, L"EDPAllInterfacesContainerGroupIdzzz");
  if ( Config )
  {
    v26 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_11;
    v27 = 21;
    v28 = "FwMoneisDeleteInterfaceContainer";
    goto LABEL_10;
  }
  if ( !v71 && !v70 )
  {
LABEL_20:
    v29 = this;
    goto LABEL_135;
  }
  if ( !v90 )
  {
LABEL_19:
    Config = 87;
    goto LABEL_20;
  }
  v97 = 0;
  JoinInformation = NetGetJoinInformation(0, &NameBuffer, &BufferType);
  Config = JoinInformation;
  if ( JoinInformation && JoinInformation != 50 )
    goto LABEL_20;
  if ( NameBuffer )
    NetApiBufferFree(NameBuffer);
  if ( BufferType == NetSetupDomainName )
  {
    LODWORD(v97) = 0;
    DWORD2(v97) = 1;
  }
  else
  {
    if ( !v95 )
      goto LABEL_19;
    *((_QWORD *)&v97 + 1) = v95;
    LODWORD(v97) = 2;
  }
  v31 = -1;
  while ( *(_WORD *)(v90 + 2 * v31++ + 2) != 0 )
    ;
  v33 = v31 + 445;
  v34 = 2 * (v31 + 445);
  v89 = v31 + 445;
  v82 = v34;
  v73 = (STRSAFE_LPWSTR)FwAlloc(v34);
  if ( !v73 )
  {
    v29 = this;
    Config = 14;
    goto LABEL_135;
  }
  Config = StringCchPrintfExW(v73, v33, 0, &v89, 0, L"%ws%ws%ws", v104, v90, &v102);
  if ( Config < 0 )
  {
    v59 = v73;
    v29 = this;
LABEL_134:
    FwFree(v59);
    goto LABEL_135;
  }
  Config = appIsolation::EnterpriseDomainProtection::FwMoneisCreateEnterpriseIdRule(v35, &v75, v90, v73, v34, 1);
  if ( Config )
    goto LABEL_111;
  Config = appIsolation::EnterpriseDomainProtection::FwMoneisCreateEnterpriseIdRule(v36, &v77, v90, v73, v34, 2);
  if ( Config )
    goto LABEL_111;
  Config = appIsolation::EnterpriseDomainProtection::FwMoneisCreatePersonalRule(v37, &v78);
  if ( Config )
    goto LABEL_111;
  Config = appIsolation::EnterpriseDomainProtection::FwMoneisCreatePersonalRule(v38, &v79);
  if ( Config )
    goto LABEL_111;
  v40 = v79;
  if ( v71 == 1 )
  {
    *(_DWORD *)(v78 + 288) = 2;
    *(_DWORD *)(v40 + 288) = 2;
  }
  else if ( v71 == 2 )
  {
    v41 = FwCopyRule(v79, &v91);
    Config = FwHResultToWindowsError(v41);
    if ( Config )
      goto LABEL_111;
    Config = appIsolation::EnterpriseDomainProtection::FwMoneisFillRuleId(v42, *(unsigned __int16 **)(v91 + 16));
    if ( Config )
      goto LABEL_111;
    *(_DWORD *)(v91 + 288) = 2;
    *(_QWORD *)(v91 + 376) = L"S-1-15-2-3624051433-2125758914-1423191267-1740899205-1073925389-3782572162-737981194";
    v43 = FwCopyRule(v40, &v92);
    Config = FwHResultToWindowsError(v43);
    if ( Config )
      goto LABEL_111;
    Config = appIsolation::EnterpriseDomainProtection::FwMoneisFillRuleId(v44, *(unsigned __int16 **)(v92 + 16));
    if ( Config )
      goto LABEL_111;
    *(_DWORD *)(v92 + 288) = 2;
    *(_QWORD *)(v92 + 272) = L"%ProgramFiles%\\Internet Explorer\\iexplore.exe";
    v45 = FwCopyRule(v40, &v93);
    Config = FwHResultToWindowsError(v45);
    if ( Config )
      goto LABEL_111;
    Config = appIsolation::EnterpriseDomainProtection::FwMoneisFillRuleId(v46, *(unsigned __int16 **)(v93 + 16));
    if ( Config )
      goto LABEL_111;
    v39 = L"%ProgramFiles% (x86)\\Internet Explorer\\iexplore.exe";
    *(_DWORD *)(v93 + 288) = 2;
    *(_QWORD *)(v93 + 272) = L"%ProgramFiles% (x86)\\Internet Explorer\\iexplore.exe";
  }
  Config = appIsolation::EnterpriseDomainProtection::FwMoneisCreateSmbAllowRule(v39, &v85, 1);
  if ( !Config )
  {
    Config = appIsolation::EnterpriseDomainProtection::FwMoneisCreateSmbAllowRule(v47, &v86, 2);
    if ( !Config )
    {
      if ( (_DWORD)v96 )
      {
        if ( v70 )
        {
          Config = appIsolation::EnterpriseDomainProtection::FwMoneisCreateEnterpriseIdRule(v48, &v80, v90, v73, v82, 2);
          if ( Config )
            goto LABEL_111;
          v15 = v80;
          *(_WORD *)(v80 + 424) = 64;
          *(_QWORD *)(v15 + 176) = 0;
          *(_DWORD *)(v15 + 432) = v96;
          *(_QWORD *)(v15 + 440) = *((_QWORD *)&v96 + 1);
        }
        Config = appIsolation::EnterpriseDomainProtection::FwMoneisCreatePersonalRule(v48, &v81);
        if ( Config )
          goto LABEL_111;
        v17 = v81;
        v48 = v70;
        *(_WORD *)(v81 + 424) = 64;
        *(_QWORD *)(v17 + 176) = 0;
        if ( (_DWORD)v48 )
          *(_DWORD *)(v17 + 288) = 2;
        *(_DWORD *)(v17 + 432) = v96;
        *(_QWORD *)(v17 + 440) = *((_QWORD *)&v96 + 1);
        if ( (_DWORD)v48 )
        {
          Config = appIsolation::EnterpriseDomainProtection::FwMoneisCreateEnterpriseIdRule(v48, &v83, v90, v73, v82, 2);
          if ( Config )
            goto LABEL_111;
          v18 = v83;
          *(_WORD *)(v83 + 424) = 80;
          *(_QWORD *)(v18 + 176) = 0;
          *(_DWORD *)(v18 + 432) = 0;
          *(_QWORD *)(v18 + 440) = 0;
          *(_WORD *)(v18 + 48) = 6;
          *(_DWORD *)(v18 + 88) = 1;
          *(_QWORD *)(v18 + 96) = &v100;
          if ( !v74 )
          {
            Config = appIsolation::EnterpriseDomainProtection::FwMoneisCreatePersonalRule(v48, &v84);
            if ( Config )
              goto LABEL_111;
            v20 = v84;
            *(_WORD *)(v84 + 424) = 80;
            *(_QWORD *)(v20 + 176) = 0;
            *(_DWORD *)(v20 + 288) = 2;
            *(_DWORD *)(v20 + 432) = 0;
            *(_QWORD *)(v20 + 440) = 0;
            *(_WORD *)(v20 + 48) = 6;
            *(_DWORD *)(v20 + 88) = 1;
            *(_QWORD *)(v20 + 96) = &v100;
          }
        }
      }
      if ( (_DWORD)v98 )
      {
        Config = appIsolation::EnterpriseDomainProtection::FwMoneisCreatePersonalRule(v48, &v76);
        if ( Config )
          goto LABEL_111;
        v48 = v76;
        *(_WORD *)(v76 + 424) = 64;
        *(_QWORD *)(v48 + 176) = 0;
        *(_DWORD *)(v48 + 432) = v98;
        *(_QWORD *)(v48 + 440) = *((_QWORD *)&v98 + 1);
      }
      Config = appIsolation::EnterpriseDomainProtection::FwMoneisCreateEdpLoopbackRule(v48, 1, &v87);
      if ( !Config )
      {
        Config = appIsolation::EnterpriseDomainProtection::FwMoneisCreateEdpLoopbackRule(v49, 2, &v88);
        if ( !Config )
        {
          v50 = v77;
          v51 = v86;
          *v75 = v77;
          v52 = (_QWORD *)v78;
          *v50 = v78;
          *v52 = v40;
          v53 = v85;
          *(_QWORD *)v40 = v85;
          *v53 = v51;
          *v51 = 0;
          if ( v15 )
          {
            *v51 = v15;
            v4 = 7;
            *(_QWORD *)v15 = 0;
            v51 = (_QWORD *)v15;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                22,
                WPP_8a4c25f4ce093197c3f0fcd6b5570cca_Traceguids,
                *(unsigned int *)(v15 + 288));
            }
          }
          if ( v17 )
          {
            *v51 = v17;
            ++v4;
            *(_QWORD *)v17 = 0;
            v51 = (_QWORD *)v17;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                23,
                WPP_8a4c25f4ce093197c3f0fcd6b5570cca_Traceguids,
                *(unsigned int *)(v17 + 288));
            }
          }
          if ( v18 )
          {
            *v51 = v18;
            ++v4;
            *(_QWORD *)v18 = 0;
            v51 = (_QWORD *)v18;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                24,
                WPP_8a4c25f4ce093197c3f0fcd6b5570cca_Traceguids,
                *(unsigned int *)(v18 + 288));
            }
          }
          if ( v20 )
          {
            *v51 = v20;
            ++v4;
            *(_QWORD *)v20 = 0;
            v51 = (_QWORD *)v20;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                25,
                WPP_8a4c25f4ce093197c3f0fcd6b5570cca_Traceguids,
                *(unsigned int *)(v20 + 288));
            }
          }
          v54 = v76;
          if ( v76 )
          {
            *v51 = v76;
            ++v4;
            *(_QWORD *)v54 = 0;
            v51 = (_QWORD *)v54;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                26,
                WPP_8a4c25f4ce093197c3f0fcd6b5570cca_Traceguids,
                *(unsigned int *)(v54 + 288));
            }
          }
          if ( v91 )
          {
            *v51 = v91;
            ++v4;
            *(_QWORD *)v91 = 0;
            v51 = (_QWORD *)v91;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                27,
                WPP_8a4c25f4ce093197c3f0fcd6b5570cca_Traceguids,
                *(unsigned int *)(v91 + 288));
            }
          }
          if ( v92 )
          {
            *v51 = v92;
            ++v4;
            *(_QWORD *)v92 = 0;
            v51 = (_QWORD *)v92;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                28,
                WPP_8a4c25f4ce093197c3f0fcd6b5570cca_Traceguids,
                *(unsigned int *)(v92 + 288));
            }
          }
          if ( v93 )
          {
            *v51 = v93;
            ++v4;
            *(_QWORD *)v93 = 0;
            v51 = (_QWORD *)v93;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                29,
                WPP_8a4c25f4ce093197c3f0fcd6b5570cca_Traceguids,
                *(unsigned int *)(v93 + 288));
            }
          }
          v55 = v87;
          if ( v87 )
          {
            *v51 = v87;
            ++v4;
            *(_QWORD *)v55 = 0;
            v51 = (_QWORD *)v55;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                30,
                WPP_8a4c25f4ce093197c3f0fcd6b5570cca_Traceguids,
                *(unsigned int *)(v55 + 288));
            }
          }
          v56 = v88;
          if ( v88 )
          {
            *v51 = v88;
            ++v4;
            *(_QWORD *)v56 = 0;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                31,
                WPP_8a4c25f4ce093197c3f0fcd6b5570cca_Traceguids,
                *(unsigned int *)(v56 + 288));
            }
          }
          v57 = FwAllocCheckSize(504, v4, &v94);
          Config = FwHResultToWindowsError(v57);
          if ( !Config )
          {
            v60 = v75;
            v61 = 0;
            if ( v4 )
            {
              while ( v60 )
              {
                *((_WORD *)v60 + 212) |= 0x400u;
                v62 = 3;
                v63 = 504LL * v61;
                v64 = v60;
                v65 = v63 + v94;
                do
                {
                  v65 += 128;
                  v66 = *(_OWORD *)v64;
                  v64 += 16;
                  *(_OWORD *)(v65 - 128) = v66;
                  *(_OWORD *)(v65 - 112) = *((_OWORD *)v64 - 7);
                  *(_OWORD *)(v65 - 96) = *((_OWORD *)v64 - 6);
                  *(_OWORD *)(v65 - 80) = *((_OWORD *)v64 - 5);
                  *(_OWORD *)(v65 - 64) = *((_OWORD *)v64 - 4);
                  *(_OWORD *)(v65 - 48) = *((_OWORD *)v64 - 3);
                  *(_OWORD *)(v65 - 32) = *((_OWORD *)v64 - 2);
                  *(_OWORD *)(v65 - 16) = *((_OWORD *)v64 - 1);
                  --v62;
                }
                while ( v62 );
                ++v61;
                *(_OWORD *)v65 = *(_OWORD *)v64;
                *(_OWORD *)(v65 + 16) = *((_OWORD *)v64 + 1);
                *(_OWORD *)(v65 + 32) = *((_OWORD *)v64 + 2);
                *(_OWORD *)(v65 + 48) = *((_OWORD *)v64 + 3);
                *(_OWORD *)(v65 + 64) = *((_OWORD *)v64 + 4);
                *(_OWORD *)(v65 + 80) = *((_OWORD *)v64 + 5);
                *(_OWORD *)(v65 + 96) = *((_OWORD *)v64 + 6);
                v58 = v64[14];
                *(_QWORD *)(v65 + 112) = v58;
                *(_QWORD *)(v63 + v94) = 0;
                v60 = (_QWORD *)*v60;
                if ( v61 >= v4 )
                  goto LABEL_125;
              }
            }
            else
            {
LABEL_125:
              if ( v60 )
                MicrosoftTelemetryAssertTriggeredNoArgs(v58);
            }
            v29 = this;
            _InterlockedIncrement((volatile signed __int32 *)this + 13);
            FwRegSetDWord(
              -2147483646,
              L"SYSTEM\\CurrentControlSet\\Services\\mpssvc\\Parameters\\ACService",
              L"TmpEdpAppHsviRefCnt",
              *((unsigned int *)this + 13));
            v67 = 1;
            if ( v70 )
              v67 = 9;
            if ( !v71 && v70 == 1 )
              v67 |= 0x10u;
            Config = FwMoneisCreateInterfaceContainer(
                       0,
                       0,
                       L"EDP Rule:",
                       L"EDP Rule:",
                       &v97,
                       v67,
                       v4,
                       v94,
                       L"EDPAllInterfacesContainerGroupIdzzz");
            goto LABEL_112;
          }
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            WPP_SF_Ds(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              32,
              (unsigned int)WPP_8a4c25f4ce093197c3f0fcd6b5570cca_Traceguids,
              Config,
              (__int64)"FwAllocCheckSize");
        }
      }
    }
  }
LABEL_111:
  v29 = this;
LABEL_112:
  if ( v75 )
    FwFreeWFRule(v75);
  if ( v77 )
    FwFreeWFRule(v77);
LABEL_116:
  if ( v94 )
    FwFree(v94);
  v59 = v73;
  if ( v73 )
    goto LABEL_134;
LABEL_135:
  if ( (_DWORD)v96 )
  {
    FwBinariesFree((unsigned int)v96, *((_QWORD *)&v96 + 1));
    v96 = 0;
  }
  if ( (_DWORD)v98 )
  {
    FwBinariesFree((unsigned int)v98, *((_QWORD *)&v98 + 1));
    v98 = 0;
  }
  FwFree(v90);
  FwFree(v95);
  if ( v72 )
    FwCriticalSectionLeave(v29);
  if ( Config < 0 )
    ++g_failedAddAllowEnterpriseIdRule;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      33,
      WPP_8a4c25f4ce093197c3f0fcd6b5570cca_Traceguids,
      (unsigned int)Config);
  return (unsigned int)Config;
}

```

## disassembly

```asm
0x1800c3ea0  push    rbp
0x1800c3ea2  push    rbx
0x1800c3ea3  push    rsi
0x1800c3ea4  push    rdi
0x1800c3ea5  push    r12
0x1800c3ea7  push    r13
0x1800c3ea9  push    r14
0x1800c3eab  push    r15
0x1800c3ead  lea     rbp, [rsp-3F8h]
0x1800c3eb5  sub     rsp, 4F8h
0x1800c3ebc  mov     rax, cs:__security_cookie
0x1800c3ec3  xor     rax, rsp
0x1800c3ec6  mov     [rbp+430h+var_50], rax
0x1800c3ecd  mov     r13, rcx
0x1800c3ed0  mov     [rsp+530h+var_4E0], rcx
0x1800c3ed5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3edc  lea     rax, WPP_GLOBAL_Control
0x1800c3ee3  cmp     rcx, rax
0x1800c3ee6  jz      short loc_1800C3F03
0x1800c3ee8  test    byte ptr [rcx+1Ch], 8
0x1800c3eec  jz      short loc_1800C3F03
0x1800c3eee  mov     rcx, [rcx+10h]
0x1800c3ef2  lea     r8, WPP_8a4c25f4ce093197c3f0fcd6b5570cca_Traceguids
0x1800c3ef9  mov     edx, 13h
0x1800c3efe  call    WPP_SF_
0x1800c3f03  inc     cs:g_invokedAddAllowEnterpriseIdRule
0x1800c3f0a  lea     rax, [rbp+430h+var_3C0]
0x1800c3f0e  xor     r8d, r8d
0x1800c3f11  lea     rcx, aOSygSydA0x1AcA; "O:SYG:SYD:(A;;0x1;;;AC)(A;;0x1;;;S-1-15"...
0x1800c3f18  xorps   xmm0, xmm0
0x1800c3f1b  mov     [rbp+430h+NameBuffer], r8
0x1800c3f1f  mov     edi, 6
0x1800c3f24  mov     [rbp+430h+BufferType], r8d
0x1800c3f28  movups  [rbp+430h+var_400], xmm0
0x1800c3f2c  mov     edx, edi
0x1800c3f2e  xchg    ax, ax
0x1800c3f30  lea     rax, [rax+80h]
0x1800c3f37  movups  xmm0, xmmword ptr [rcx]
0x1800c3f3a  movups  xmm1, xmmword ptr [rcx+10h]
0x1800c3f3e  lea     rcx, [rcx+80h]
0x1800c3f45  movups  xmmword ptr [rax-80h], xmm0
0x1800c3f49  movups  xmm0, xmmword ptr [rcx-60h]
0x1800c3f4d  movups  xmmword ptr [rax-70h], xmm1
0x1800c3f51  movups  xmm1, xmmword ptr [rcx-50h]
0x1800c3f55  movups  xmmword ptr [rax-60h], xmm0
0x1800c3f59  movups  xmm0, xmmword ptr [rcx-40h]
0x1800c3f5d  movups  xmmword ptr [rax-50h], xmm1
0x1800c3f61  movups  xmm1, xmmword ptr [rcx-30h]
0x1800c3f65  movups  xmmword ptr [rax-40h], xmm0
0x1800c3f69  movups  xmm0, xmmword ptr [rcx-20h]
0x1800c3f6d  movups  xmmword ptr [rax-30h], xmm1
0x1800c3f71  movups  xmm1, xmmword ptr [rcx-10h]
0x1800c3f75  movups  xmmword ptr [rax-20h], xmm0
0x1800c3f79  movups  xmmword ptr [rax-10h], xmm1
0x1800c3f7d  sub     rdx, 1
0x1800c3f81  jnz     short loc_1800C3F30
0x1800c3f83  movups  xmm0, xmmword ptr [rcx]
0x1800c3f86  mov     [rsp+530h+var_4C8], r8
0x1800c3f8b  mov     r12, r8
0x1800c3f8e  movups  xmm1, xmmword ptr [rcx+10h]
0x1800c3f92  mov     [rbp+430h+var_3D8], 1BB01BBh
0x1800c3f99  mov     r15, r8
0x1800c3f9c  movups  xmmword ptr [rax], xmm0
0x1800c3f9f  mov     [rsp+530h+var_4B8], r8
0x1800c3fa4  mov     r14, r8
0x1800c3fa7  movups  xmm0, xmmword ptr [rcx+20h]
0x1800c3fab  mov     [rbp+430h+var_4A8], r8
0x1800c3faf  mov     rsi, r8
0x1800c3fb2  movups  xmmword ptr [rax+10h], xmm1
0x1800c3fb6  mov     [rbp+430h+var_4A0], r8
0x1800c3fba  movups  xmm1, xmmword ptr [rcx+30h]
0x1800c3fbe  mov     [rbp+430h+var_498], r8
0x1800c3fc2  movups  xmmword ptr [rax+20h], xmm0
0x1800c3fc6  mov     [rbp+430h+var_468], r8
0x1800c3fca  movups  xmm0, xmmword ptr [rcx+40h]
0x1800c3fce  mov     [rbp+430h+var_460], r8
0x1800c3fd2  movups  xmmword ptr [rax+30h], xmm1
0x1800c3fd6  mov     [rbp+430h+var_490], r8
0x1800c3fda  movups  xmm1, xmmword ptr [rcx+50h]
0x1800c3fde  mov     [rbp+430h+var_488], r8
0x1800c3fe2  movups  xmmword ptr [rax+40h], xmm0
0x1800c3fe6  mov     [rbp+430h+var_4B0], r8
0x1800c3fea  movups  xmm0, xmmword ptr [rcx+5Eh]
0x1800c3fee  mov     [rbp+430h+var_478], r8
0x1800c3ff2  movups  xmmword ptr [rax+50h], xmm1
0x1800c3ff6  mov     [rbp+430h+var_470], r8
0x1800c3ffa  movsd   xmm1, qword ptr cs:asc_180108BE0; "\")))"
0x1800c4002  movups  xmmword ptr [rax+5Eh], xmm0
0x1800c4006  movzx   eax, word ptr cs:asc_180108BE0+8; ""
0x1800c400d  movsd   [rbp+430h+var_3D0], xmm1
0x1800c4012  xorps   xmm0, xmm0
0x1800c4015  xorps   xmm1, xmm1
0x1800c4018  mov     [rbp+430h+var_3C8], ax
0x1800c401c  movups  [rbp+430h+var_410], xmm0
0x1800c4020  mov     [rbp+430h+var_438], r8
0x1800c4024  mov     [rbp+430h+var_430], r8
0x1800c4028  mov     [rbp+430h+var_428], r8
0x1800c402c  mov     [rbp+430h+var_458], r8
0x1800c4030  mov     [rbp+430h+var_450], r8
0x1800c4034  mov     [rbp+430h+var_420], r8
0x1800c4038  movups  [rbp+430h+var_3F0], xmm1
0x1800c403c  mov     [rsp+530h+var_4C0], r8d
0x1800c4041  mov     [rsp+530h+var_4D8], r8d
0x1800c4046  mov     [rsp+530h+var_4D0], r8d
0x1800c404b  mov     [rsp+530h+var_4D4], r8d
0x1800c4050  mov     [rbp+430h+var_440], r8
0x1800c4054  mov     [rbp+430h+var_418], r8
0x1800c4058  lock inc dword ptr [r13+30h]
0x1800c405d  lea     rax, [rbp+430h+var_418]
0x1800c4061  mov     [rsp+530h+var_4F8], rax
0x1800c4066  lea     r9, [rsp+530h+var_4D8]
0x1800c406b  lea     rax, [rbp+430h+var_440]
0x1800c406f  mov     [rsp+530h+var_500], rax
0x1800c4074  lea     r8, [rsp+530h+var_4C0]
0x1800c4079  lea     rax, [rsp+530h+var_4D4]
0x1800c407e  mov     [rsp+530h+var_508], rax
0x1800c4083  lea     rdx, [rbp+430h+var_3F0]
0x1800c4087  lea     rax, [rsp+530h+var_4D0]
0x1800c408c  lea     rcx, [rbp+430h+var_410]
0x1800c4090  mov     qword ptr [rsp+530h+dwFlags], rax
0x1800c4095  call    FwMoneisEdpGetConfig
0x1800c409a  mov     ebx, eax
0x1800c409c  test    eax, eax
0x1800c409e  jz      short loc_1800C40EF
0x1800c40a0  xor     r13d, r13d
0x1800c40a3  mov     [rsp+530h+var_4D0], r13d
0x1800c40a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c40af  lea     rdi, WPP_GLOBAL_Control
0x1800c40b6  cmp     rcx, rdi
0x1800c40b9  jz      short loc_1800C40E5
0x1800c40bb  test    byte ptr [rcx+1Ch], 1
0x1800c40bf  jz      short loc_1800C40E5
0x1800c40c1  mov     edx, 14h
0x1800c40c6  lea     rax, aFwmoneisedpget; "FwMoneisEdpGetConfig"
0x1800c40cd  mov     rcx, [rcx+10h]
0x1800c40d1  lea     r8, WPP_8a4c25f4ce093197c3f0fcd6b5570cca_Traceguids
0x1800c40d8  mov     r9d, ebx
0x1800c40db  mov     qword ptr [rsp+530h+dwFlags], rax
0x1800c40e0  call    WPP_SF_Ds
0x1800c40e5  mov     rsi, [rsp+530h+var_4E0]
0x1800c40ea  jmp     loc_1800C4A0C
0x1800c40ef  mov     rcx, r13
0x1800c40f2  call    cs:__imp_FwCriticalSectionEnter
0x1800c40f9  nop     dword ptr [rax+rax+00h]
0x1800c40fe  mov     r13d, 1
0x1800c4104  lea     r8, aEdpallinterfac; "EDPAllInterfacesContainerGroupIdzzz"
0x1800c410b  xor     edx, edx
0x1800c410d  mov     [rsp+530h+var_4D0], r13d
0x1800c4112  xor     ecx, ecx
0x1800c4114  call    FwMoneisDeleteInterfaceContainer
0x1800c4119  mov     ebx, eax
0x1800c411b  test    eax, eax
0x1800c411d  jz      short loc_1800C4146
0x1800c411f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4126  lea     rdi, WPP_GLOBAL_Control
0x1800c412d  cmp     rcx, rdi
0x1800c4130  jz      short loc_1800C40E5
0x1800c4132  test    [rcx+1Ch], r13b
0x1800c4136  jz      short loc_1800C40E5
0x1800c4138  mov     edx, 15h
0x1800c413d  lea     rax, aFwmoneisdelete; "FwMoneisDeleteInterfaceContainer"
0x1800c4144  jmp     short loc_1800C40CD
0x1800c4146  cmp     [rsp+530h+var_4D4], esi
0x1800c414a  jnz     short loc_1800C4152
0x1800c414c  cmp     [rsp+530h+var_4D8], esi
0x1800c4150  jz      short loc_1800C415D
0x1800c4152  cmp     [rbp+430h+var_440], rsi
0x1800c4156  jnz     short loc_1800C416E
0x1800c4158  mov     ebx, 57h ; 'W'
0x1800c415d  mov     rsi, [rsp+530h+var_4E0]
0x1800c4162  lea     rdi, WPP_GLOBAL_Control
0x1800c4169  jmp     loc_1800C4BE7
0x1800c416e  xorps   xmm0, xmm0
0x1800c4171  lea     r8, [rbp+430h+BufferType]; BufferType
0x1800c4175  lea     rdx, [rbp+430h+NameBuffer]; lpNameBuffer
0x1800c4179  xor     ecx, ecx; lpServer
0x1800c417b  movups  [rbp+430h+var_400], xmm0
0x1800c417f  call    cs:__imp_NetGetJoinInformation
0x1800c4186  nop     dword ptr [rax+rax+00h]
0x1800c418b  mov     ebx, eax
0x1800c418d  test    eax, eax
0x1800c418f  jz      short loc_1800C4196
0x1800c4191  cmp     eax, 32h ; '2'
0x1800c4194  jnz     short loc_1800C415D
0x1800c4196  mov     rcx, [rbp+430h+NameBuffer]; Buffer
0x1800c419a  test    rcx, rcx
0x1800c419d  jz      short loc_1800C41AB
0x1800c419f  call    cs:__imp_NetApiBufferFree
0x1800c41a6  nop     dword ptr [rax+rax+00h]
0x1800c41ab  cmp     [rbp+430h+BufferType], 3
0x1800c41af  jnz     short loc_1800C41BA
0x1800c41b1  mov     dword ptr [rbp+430h+var_400], esi
0x1800c41b4  mov     dword ptr [rbp+430h+var_400+8], r13d
0x1800c41b8  jmp     short loc_1800C41D3
0x1800c41ba  mov     rax, [rbp+430h+var_418]
0x1800c41be  test    rax, rax
0x1800c41c1  jz      short loc_1800C4158
0x1800c41c3  mov     dword ptr [rbp+430h+var_400+8], eax
0x1800c41c6  mov     eax, dword ptr [rbp+430h+var_418+4]
0x1800c41c9  mov     dword ptr [rbp+430h+var_400+0Ch], eax
0x1800c41cc  mov     dword ptr [rbp+430h+var_400], 2
0x1800c41d3  mov     rcx, [rbp+430h+var_440]
0x1800c41d7  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800c41de  xchg    ax, ax
0x1800c41e0  cmp     [rcx+rax*2+2], si
0x1800c41e5  lea     rax, [rax+1]
0x1800c41e9  jnz     short loc_1800C41E0
0x1800c41eb  lea     rbx, [rax+1BDh]
0x1800c41f2  lea     r13, [rbx+rbx]
0x1800c41f6  mov     [rbp+430h+var_448], rbx
0x1800c41fa  mov     rcx, r13
0x1800c41fd  mov     [rbp+430h+var_480], r13
0x1800c4201  call    cs:__imp_FwAlloc
0x1800c4208  nop     dword ptr [rax+rax+00h]
0x1800c420d  mov     [rsp+530h+var_4C8], rax
0x1800c4212  mov     rcx, rax; pszDest
0x1800c4215  test    rax, rax
0x1800c4218  jnz     short loc_1800C4230
0x1800c421a  mov     rsi, [rsp+530h+var_4E0]
0x1800c421f  lea     rdi, WPP_GLOBAL_Control
0x1800c4226  mov     ebx, 0Eh
0x1800c422b  jmp     loc_1800C4BE7
0x1800c4230  lea     rax, [rbp+430h+var_3D0]
0x1800c4234  xor     r8d, r8d; unsigned __int16 **
0x1800c4237  mov     [rsp+530h+var_4F0], rax
0x1800c423c  lea     r9, [rbp+430h+var_448]; unsigned __int64 *
0x1800c4240  mov     rax, [rbp+430h+var_440]
0x1800c4244  mov     rdx, rbx; cchDest
0x1800c4247  mov     [rsp+530h+var_4F8], rax
0x1800c424c  lea     rax, [rbp+430h+var_3C0]
0x1800c4250  mov     [rsp+530h+var_500], rax
0x1800c4255  lea     rax, aWsWsWs; "%ws%ws%ws"
0x1800c425c  mov     [rsp+530h+var_508], rax; unsigned __int16 *
0x1800c4261  mov     qword ptr [rsp+530h+dwFlags], rsi; dwFlags
0x1800c4266  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800c426b  mov     ebx, eax
0x1800c426d  test    eax, eax
0x1800c426f  js      loc_1800C4BC7
0x1800c4275  mov     r9, [rsp+530h+var_4C8]
0x1800c427a  lea     rdx, [rsp+530h+var_4B8]
0x1800c427f  mov     r8, [rbp+430h+var_440]
0x1800c4283  mov     dword ptr [rsp+530h+var_508], 1
0x1800c428b  mov     qword ptr [rsp+530h+dwFlags], r13
0x1800c4290  call    ?FwMoneisCreateEnterpriseIdRule@EnterpriseDomainProtection@appIsolation@@AEAAKPEAPEAU_tag_FW_RULE@@PEBG1_KW4_tag_FW_DIRECTION@@@Z; appIsolation::EnterpriseDomainProtection::FwMoneisCreateEnterpriseIdRule(_tag_FW_RULE * *,ushort const *,ushort const *,unsigned __int64,_tag_FW_DIRECTION)
0x1800c4295  mov     ebx, eax
0x1800c4297  test    eax, eax
0x1800c4299  jnz     loc_1800C49CF
0x1800c429f  mov     r9, [rsp+530h+var_4C8]
0x1800c42a4  lea     rdx, [rbp+430h+var_4A8]
0x1800c42a8  mov     r8, [rbp+430h+var_440]
0x1800c42ac  mov     dword ptr [rsp+530h+var_508], 2
0x1800c42b4  mov     qword ptr [rsp+530h+dwFlags], r13
0x1800c42b9  call    ?FwMoneisCreateEnterpriseIdRule@EnterpriseDomainProtection@appIsolation@@AEAAKPEAPEAU_tag_FW_RULE@@PEBG1_KW4_tag_FW_DIRECTION@@@Z; appIsolation::EnterpriseDomainProtection::FwMoneisCreateEnterpriseIdRule(_tag_FW_RULE * *,ushort const *,ushort const *,unsigned __int64,_tag_FW_DIRECTION)
0x1800c42be  mov     ebx, eax
0x1800c42c0  test    eax, eax
0x1800c42c2  jnz     loc_1800C49CF
0x1800c42c8  lea     rdx, [rbp+430h+var_4A0]
0x1800c42cc  mov     [rsp+530h+dwFlags], 1
0x1800c42d4  call    ?FwMoneisCreatePersonalRule@EnterpriseDomainProtection@appIsolation@@AEAAKPEAPEAU_tag_FW_RULE@@PEBG1W4_tag_FW_DIRECTION@@@Z; appIsolation::EnterpriseDomainProtection::FwMoneisCreatePersonalRule(_tag_FW_RULE * *,ushort const *,ushort const *,_tag_FW_DIRECTION)
0x1800c42d9  mov     ebx, eax
0x1800c42db  test    eax, eax
0x1800c42dd  jnz     loc_1800C49CF
0x1800c42e3  lea     rdx, [rbp+430h+var_498]
0x1800c42e7  mov     [rsp+530h+dwFlags], 2
0x1800c42ef  call    ?FwMoneisCreatePersonalRule@EnterpriseDomainProtection@appIsolation@@AEAAKPEAPEAU_tag_FW_RULE@@PEBG1W4_tag_FW_DIRECTION@@@Z; appIsolation::EnterpriseDomainProtection::FwMoneisCreatePersonalRule(_tag_FW_RULE * *,ushort const *,ushort const *,_tag_FW_DIRECTION)
0x1800c42f4  mov     ebx, eax
0x1800c42f6  test    eax, eax
0x1800c42f8  jnz     loc_1800C49CF
0x1800c42fe  mov     eax, [rsp+530h+var_4D4]
0x1800c4302  mov     r13, [rbp+430h+var_498]
0x1800c4306  cmp     eax, 1
0x1800c4309  jnz     short loc_1800C4329
0x1800c430b  mov     rax, [rbp+430h+var_4A0]
0x1800c430f  mov     dword ptr [rax+120h], 2
0x1800c4319  mov     dword ptr [r13+120h], 2
0x1800c4324  jmp     loc_1800C4458
0x1800c4329  cmp     eax, 2
0x1800c432c  jnz     loc_1800C4458
0x1800c4332  lea     rdx, [rbp+430h+var_438]
0x1800c4336  mov     rcx, r13
0x1800c4339  call    cs:__imp_FwCopyRule
0x1800c4340  nop     dword ptr [rax+rax+00h]
0x1800c4345  mov     ecx, eax
0x1800c4347  call    cs:__imp_FwHResultToWindowsError
0x1800c434e  nop     dword ptr [rax+rax+00h]
0x1800c4353  mov     ebx, eax
0x1800c4355  test    eax, eax
0x1800c4357  jnz     loc_1800C49CF
0x1800c435d  mov     rdx, [rbp+430h+var_438]
0x1800c4361  mov     rdx, [rdx+10h]; unsigned __int16 *
0x1800c4365  call    ?FwMoneisFillRuleId@EnterpriseDomainProtection@appIsolation@@AEAAKPEAG@Z; appIsolation::EnterpriseDomainProtection::FwMoneisFillRuleId(ushort *)
0x1800c436a  mov     ebx, eax
0x1800c436c  test    eax, eax
0x1800c436e  jnz     loc_1800C49CF
0x1800c4374  mov     rax, [rbp+430h+var_438]
0x1800c4378  lea     rcx, aS1152362405143; "S-1-15-2-3624051433-2125758914-14231912"...
0x1800c437f  lea     rdx, [rbp+430h+var_430]
0x1800c4383  mov     dword ptr [rax+120h], 2
0x1800c438d  mov     rax, [rbp+430h+var_438]
0x1800c4391  mov     [rax+178h], rcx
  ... truncated ...
```
