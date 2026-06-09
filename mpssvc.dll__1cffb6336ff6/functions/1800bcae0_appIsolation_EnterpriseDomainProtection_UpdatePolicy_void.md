# appIsolation::EnterpriseDomainProtection::UpdatePolicy(void)

- ea: `0x1800bcae0`
- end: `0x1800bd869`
- name: `?UpdatePolicy@EnterpriseDomainProtection@appIsolation@@QEAAKXZ`
- size: `3465`
- prototype: `unsigned int __fastcall(appIsolation::EnterpriseDomainProtection *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800b80a4`

## callees

- `0x1800093b0`
- `0x18000ae9c`
- `0x18000af3c`
- `0x180017110`
- `0x18006267c`
- `0x18006f520`
- `0x1800b9a54`
- `0x1800bbc60`
- `0x1800bbe30`
- `0x1800bc100`
- `0x1800bc3c0`
- `0x1800bc6c0`
- `0x1800bc770`
- `0x1800bcae0`
- `0x1800be78c`

## import_xrefs

- `wkscli!NetGetJoinInformation` at `0x1800bcdb9`
- `wkscli!NetGetJoinInformation` at `0x1800bcdb9`
- `netutils!NetApiBufferFree` at `0x1800bcdd3`
- `netutils!NetApiBufferFree` at `0x1800bcdd3`
- `fwbase!FwRegSetDWord` at `0x1800bd735`
- `fwbase!FwRegSetDWord` at `0x1800bd735`
- `fwbase!FwAllocCheckSize` at `0x1800bd57b`
- `fwbase!FwAllocCheckSize` at `0x1800bd57b`
- `fwbase!FwHResultToWindowsError` at `0x1800bcf6b`
- `fwbase!FwHResultToWindowsError` at `0x1800bcfc1`
- `fwbase!FwHResultToWindowsError` at `0x1800bd017`
- `fwbase!FwHResultToWindowsError` at `0x1800bd583`
- `fwbase!FwHResultToWindowsError` at `0x1800bcf6b`
- `fwbase!FwHResultToWindowsError` at `0x1800bcfc1`
- `fwbase!FwHResultToWindowsError` at `0x1800bd017`
- `fwbase!FwHResultToWindowsError` at `0x1800bd583`
- `fwbase!FwAlloc` at `0x1800bce31`
- `fwbase!FwAlloc` at `0x1800bce31`
- `fwbase!FwCriticalSectionEnter` at `0x1800bcd32`
- `fwbase!FwCriticalSectionEnter` at `0x1800bcd32`
- `fwbase!FwCriticalSectionLeave` at `0x1800bd809`
- `fwbase!FwCriticalSectionLeave` at `0x1800bd809`
- `fwbase!FwFree` at `0x1800bd603`
- `fwbase!FwFree` at `0x1800bd7b5`
- `fwbase!FwFree` at `0x1800bd7ef`
- `fwbase!FwFree` at `0x1800bd7f9`
- `fwbase!FwFree` at `0x1800bd603`
- `fwbase!FwFree` at `0x1800bd7b5`
- `fwbase!FwFree` at `0x1800bd7ef`
- `fwbase!FwFree` at `0x1800bd7f9`
- `FWPolicyIOMgr!FwBinariesFree` at `0x1800bd7c6`
- `FWPolicyIOMgr!FwBinariesFree` at `0x1800bd7de`
- `FWPolicyIOMgr!FwBinariesFree` at `0x1800bd7c6`
- `FWPolicyIOMgr!FwBinariesFree` at `0x1800bd7de`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800bd5db`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800bd5ed`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800bd5db`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800bd5ed`
- `FWPolicyIOMgr!FwCopyRule` at `0x1800bcf63`
- `FWPolicyIOMgr!FwCopyRule` at `0x1800bcfb9`
- `FWPolicyIOMgr!FwCopyRule` at `0x1800bd00f`
- `FWPolicyIOMgr!FwCopyRule` at `0x1800bcf63`
- `FWPolicyIOMgr!FwCopyRule` at `0x1800bcfb9`
- `FWPolicyIOMgr!FwCopyRule` at `0x1800bd00f`

## string_xrefs

- `0x1800bcd77`: `FwMoneisDeleteInterfaceContainer`
- `0x1800bcd06`: `FwMoneisEdpGetConfig`
- `0x1800bd726`: `SYSTEM\CurrentControlSet\Services\mpssvc\Parameters\ACService`

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
  __int64 v58; // rdx
  __int64 v59; // rcx
  STRSAFE_LPWSTR v60; // rax
  _QWORD *v61; // r8
  __int64 v62; // r9
  __int64 v63; // rcx
  __int64 v64; // r10
  _QWORD *v65; // rax
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
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, WPP_0766a64133523165692ca09dfc63f730_Traceguids);
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
  v103 = asc_180102E30[4];
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
      (unsigned int)WPP_0766a64133523165692ca09dfc63f730_Traceguids,
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
    v60 = v73;
    v29 = this;
LABEL_134:
    FwFree(v60);
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
                WPP_0766a64133523165692ca09dfc63f730_Traceguids,
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
                WPP_0766a64133523165692ca09dfc63f730_Traceguids,
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
                WPP_0766a64133523165692ca09dfc63f730_Traceguids,
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
                WPP_0766a64133523165692ca09dfc63f730_Traceguids,
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
                WPP_0766a64133523165692ca09dfc63f730_Traceguids,
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
                WPP_0766a64133523165692ca09dfc63f730_Traceguids,
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
                WPP_0766a64133523165692ca09dfc63f730_Traceguids,
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
                WPP_0766a64133523165692ca09dfc63f730_Traceguids,
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
                WPP_0766a64133523165692ca09dfc63f730_Traceguids,
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
                WPP_0766a64133523165692ca09dfc63f730_Traceguids,
                *(unsigned int *)(v56 + 288));
            }
          }
          v57 = FwAllocCheckSize(504, v4, &v94);
          Config = FwHResultToWindowsError(v57);
          if ( !Config )
          {
            v61 = v75;
            v62 = 0;
            if ( v4 )
            {
              while ( v61 )
              {
                *((_WORD *)v61 + 212) |= 0x400u;
                v63 = 3;
                v64 = 504LL * (unsigned int)v62;
                v65 = v61;
                v58 = v64 + v94;
                do
                {
                  v58 += 128;
                  v66 = *(_OWORD *)v65;
                  v65 += 16;
                  *(_OWORD *)(v58 - 128) = v66;
                  *(_OWORD *)(v58 - 112) = *((_OWORD *)v65 - 7);
                  *(_OWORD *)(v58 - 96) = *((_OWORD *)v65 - 6);
                  *(_OWORD *)(v58 - 80) = *((_OWORD *)v65 - 5);
                  *(_OWORD *)(v58 - 64) = *((_OWORD *)v65 - 4);
                  *(_OWORD *)(v58 - 48) = *((_OWORD *)v65 - 3);
                  *(_OWORD *)(v58 - 32) = *((_OWORD *)v65 - 2);
                  *(_OWORD *)(v58 - 16) = *((_OWORD *)v65 - 1);
                  --v63;
                }
                while ( v63 );
                v62 = (unsigned int)(v62 + 1);
                *(_OWORD *)v58 = *(_OWORD *)v65;
                *(_OWORD *)(v58 + 16) = *((_OWORD *)v65 + 1);
                *(_OWORD *)(v58 + 32) = *((_OWORD *)v65 + 2);
                *(_OWORD *)(v58 + 48) = *((_OWORD *)v65 + 3);
                *(_OWORD *)(v58 + 64) = *((_OWORD *)v65 + 4);
                *(_OWORD *)(v58 + 80) = *((_OWORD *)v65 + 5);
                *(_OWORD *)(v58 + 96) = *((_OWORD *)v65 + 6);
                v59 = v65[14];
                *(_QWORD *)(v58 + 112) = v59;
                *(_QWORD *)(v64 + v94) = 0;
                v61 = (_QWORD *)*v61;
                if ( (unsigned int)v62 >= v4 )
                  goto LABEL_125;
              }
            }
            else
            {
LABEL_125:
              if ( v61 )
                MicrosoftTelemetryAssertTriggeredNoArgs(v59, v58, v61, v62);
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
              (unsigned int)WPP_0766a64133523165692ca09dfc63f730_Traceguids,
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
  v60 = v73;
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
      WPP_0766a64133523165692ca09dfc63f730_Traceguids,
      (unsigned int)Config);
  return (unsigned int)Config;
}

```

## disassembly

```asm
0x1800bcae0  push    rbp
0x1800bcae2  push    rbx
0x1800bcae3  push    rsi
0x1800bcae4  push    rdi
0x1800bcae5  push    r12
0x1800bcae7  push    r13
0x1800bcae9  push    r14
0x1800bcaeb  push    r15
0x1800bcaed  lea     rbp, [rsp-3F8h]
0x1800bcaf5  sub     rsp, 4F8h
0x1800bcafc  mov     rax, cs:__security_cookie
0x1800bcb03  xor     rax, rsp
0x1800bcb06  mov     [rbp+430h+var_50], rax
0x1800bcb0d  mov     r13, rcx
0x1800bcb10  mov     [rsp+530h+var_4E0], rcx
0x1800bcb15  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bcb1c  lea     rax, WPP_GLOBAL_Control
0x1800bcb23  cmp     rcx, rax
0x1800bcb26  jz      short loc_1800BCB43
0x1800bcb28  test    byte ptr [rcx+1Ch], 8
0x1800bcb2c  jz      short loc_1800BCB43
0x1800bcb2e  mov     rcx, [rcx+10h]
0x1800bcb32  lea     r8, WPP_0766a64133523165692ca09dfc63f730_Traceguids
0x1800bcb39  mov     edx, 13h
0x1800bcb3e  call    WPP_SF_
0x1800bcb43  inc     cs:g_invokedAddAllowEnterpriseIdRule
0x1800bcb4a  lea     rax, [rbp+430h+var_3C0]
0x1800bcb4e  xor     r8d, r8d
0x1800bcb51  lea     rcx, aOSygSydA0x1AcA; "O:SYG:SYD:(A;;0x1;;;AC)(A;;0x1;;;S-1-15"...
0x1800bcb58  xorps   xmm0, xmm0
0x1800bcb5b  mov     [rbp+430h+NameBuffer], r8
0x1800bcb5f  mov     edi, 6
0x1800bcb64  mov     [rbp+430h+BufferType], r8d
0x1800bcb68  movups  [rbp+430h+var_400], xmm0
0x1800bcb6c  mov     edx, edi
0x1800bcb6e  xchg    ax, ax
0x1800bcb70  lea     rax, [rax+80h]
0x1800bcb77  movups  xmm0, xmmword ptr [rcx]
0x1800bcb7a  movups  xmm1, xmmword ptr [rcx+10h]
0x1800bcb7e  lea     rcx, [rcx+80h]
0x1800bcb85  movups  xmmword ptr [rax-80h], xmm0
0x1800bcb89  movups  xmm0, xmmword ptr [rcx-60h]
0x1800bcb8d  movups  xmmword ptr [rax-70h], xmm1
0x1800bcb91  movups  xmm1, xmmword ptr [rcx-50h]
0x1800bcb95  movups  xmmword ptr [rax-60h], xmm0
0x1800bcb99  movups  xmm0, xmmword ptr [rcx-40h]
0x1800bcb9d  movups  xmmword ptr [rax-50h], xmm1
0x1800bcba1  movups  xmm1, xmmword ptr [rcx-30h]
0x1800bcba5  movups  xmmword ptr [rax-40h], xmm0
0x1800bcba9  movups  xmm0, xmmword ptr [rcx-20h]
0x1800bcbad  movups  xmmword ptr [rax-30h], xmm1
0x1800bcbb1  movups  xmm1, xmmword ptr [rcx-10h]
0x1800bcbb5  movups  xmmword ptr [rax-20h], xmm0
0x1800bcbb9  movups  xmmword ptr [rax-10h], xmm1
0x1800bcbbd  sub     rdx, 1
0x1800bcbc1  jnz     short loc_1800BCB70
0x1800bcbc3  movups  xmm0, xmmword ptr [rcx]
0x1800bcbc6  mov     [rsp+530h+var_4C8], r8
0x1800bcbcb  mov     r12, r8
0x1800bcbce  movups  xmm1, xmmword ptr [rcx+10h]
0x1800bcbd2  mov     [rbp+430h+var_3D8], 1BB01BBh
0x1800bcbd9  mov     r15, r8
0x1800bcbdc  movups  xmmword ptr [rax], xmm0
0x1800bcbdf  mov     [rsp+530h+var_4B8], r8
0x1800bcbe4  mov     r14, r8
0x1800bcbe7  movups  xmm0, xmmword ptr [rcx+20h]
0x1800bcbeb  mov     [rbp+430h+var_4A8], r8
0x1800bcbef  mov     rsi, r8
0x1800bcbf2  movups  xmmword ptr [rax+10h], xmm1
0x1800bcbf6  mov     [rbp+430h+var_4A0], r8
0x1800bcbfa  movups  xmm1, xmmword ptr [rcx+30h]
0x1800bcbfe  mov     [rbp+430h+var_498], r8
0x1800bcc02  movups  xmmword ptr [rax+20h], xmm0
0x1800bcc06  mov     [rbp+430h+var_468], r8
0x1800bcc0a  movups  xmm0, xmmword ptr [rcx+40h]
0x1800bcc0e  mov     [rbp+430h+var_460], r8
0x1800bcc12  movups  xmmword ptr [rax+30h], xmm1
0x1800bcc16  mov     [rbp+430h+var_490], r8
0x1800bcc1a  movups  xmm1, xmmword ptr [rcx+50h]
0x1800bcc1e  mov     [rbp+430h+var_488], r8
0x1800bcc22  movups  xmmword ptr [rax+40h], xmm0
0x1800bcc26  mov     [rbp+430h+var_4B0], r8
0x1800bcc2a  movups  xmm0, xmmword ptr [rcx+5Eh]
0x1800bcc2e  mov     [rbp+430h+var_478], r8
0x1800bcc32  movups  xmmword ptr [rax+50h], xmm1
0x1800bcc36  mov     [rbp+430h+var_470], r8
0x1800bcc3a  movsd   xmm1, qword ptr cs:asc_180102E30; "\")))"
0x1800bcc42  movups  xmmword ptr [rax+5Eh], xmm0
0x1800bcc46  movzx   eax, word ptr cs:asc_180102E30+8; ""
0x1800bcc4d  movsd   [rbp+430h+var_3D0], xmm1
0x1800bcc52  xorps   xmm0, xmm0
0x1800bcc55  xorps   xmm1, xmm1
0x1800bcc58  mov     [rbp+430h+var_3C8], ax
0x1800bcc5c  movups  [rbp+430h+var_410], xmm0
0x1800bcc60  mov     [rbp+430h+var_438], r8
0x1800bcc64  mov     [rbp+430h+var_430], r8
0x1800bcc68  mov     [rbp+430h+var_428], r8
0x1800bcc6c  mov     [rbp+430h+var_458], r8
0x1800bcc70  mov     [rbp+430h+var_450], r8
0x1800bcc74  mov     [rbp+430h+var_420], r8
0x1800bcc78  movups  [rbp+430h+var_3F0], xmm1
0x1800bcc7c  mov     [rsp+530h+var_4C0], r8d
0x1800bcc81  mov     [rsp+530h+var_4D8], r8d
0x1800bcc86  mov     [rsp+530h+var_4D0], r8d
0x1800bcc8b  mov     [rsp+530h+var_4D4], r8d
0x1800bcc90  mov     [rbp+430h+var_440], r8
0x1800bcc94  mov     [rbp+430h+var_418], r8
0x1800bcc98  lock inc dword ptr [r13+30h]
0x1800bcc9d  lea     rax, [rbp+430h+var_418]
0x1800bcca1  mov     [rsp+530h+var_4F8], rax
0x1800bcca6  lea     r9, [rsp+530h+var_4D8]
0x1800bccab  lea     rax, [rbp+430h+var_440]
0x1800bccaf  mov     [rsp+530h+var_500], rax
0x1800bccb4  lea     r8, [rsp+530h+var_4C0]
0x1800bccb9  lea     rax, [rsp+530h+var_4D4]
0x1800bccbe  mov     [rsp+530h+var_508], rax
0x1800bccc3  lea     rdx, [rbp+430h+var_3F0]
0x1800bccc7  lea     rax, [rsp+530h+var_4D0]
0x1800bcccc  lea     rcx, [rbp+430h+var_410]
0x1800bccd0  mov     qword ptr [rsp+530h+dwFlags], rax
0x1800bccd5  call    FwMoneisEdpGetConfig
0x1800bccda  mov     ebx, eax
0x1800bccdc  test    eax, eax
0x1800bccde  jz      short loc_1800BCD2F
0x1800bcce0  xor     r13d, r13d
0x1800bcce3  mov     [rsp+530h+var_4D0], r13d
0x1800bcce8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bccef  lea     rdi, WPP_GLOBAL_Control
0x1800bccf6  cmp     rcx, rdi
0x1800bccf9  jz      short loc_1800BCD25
0x1800bccfb  test    byte ptr [rcx+1Ch], 1
0x1800bccff  jz      short loc_1800BCD25
0x1800bcd01  mov     edx, 14h
0x1800bcd06  lea     rax, aFwmoneisedpget; "FwMoneisEdpGetConfig"
0x1800bcd0d  mov     rcx, [rcx+10h]
0x1800bcd11  lea     r8, WPP_0766a64133523165692ca09dfc63f730_Traceguids
0x1800bcd18  mov     r9d, ebx
0x1800bcd1b  mov     qword ptr [rsp+530h+dwFlags], rax
0x1800bcd20  call    WPP_SF_Ds
0x1800bcd25  mov     rsi, [rsp+530h+var_4E0]
0x1800bcd2a  jmp     loc_1800BD5FA
0x1800bcd2f  mov     rcx, r13
0x1800bcd32  call    cs:__imp_FwCriticalSectionEnter
0x1800bcd38  mov     r13d, 1
0x1800bcd3e  lea     r8, aEdpallinterfac; "EDPAllInterfacesContainerGroupIdzzz"
0x1800bcd45  xor     edx, edx
0x1800bcd47  mov     [rsp+530h+var_4D0], r13d
0x1800bcd4c  xor     ecx, ecx
0x1800bcd4e  call    FwMoneisDeleteInterfaceContainer
0x1800bcd53  mov     ebx, eax
0x1800bcd55  test    eax, eax
0x1800bcd57  jz      short loc_1800BCD80
0x1800bcd59  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bcd60  lea     rdi, WPP_GLOBAL_Control
0x1800bcd67  cmp     rcx, rdi
0x1800bcd6a  jz      short loc_1800BCD25
0x1800bcd6c  test    [rcx+1Ch], r13b
0x1800bcd70  jz      short loc_1800BCD25
0x1800bcd72  mov     edx, 15h
0x1800bcd77  lea     rax, aFwmoneisdelete; "FwMoneisDeleteInterfaceContainer"
0x1800bcd7e  jmp     short loc_1800BCD0D
0x1800bcd80  cmp     [rsp+530h+var_4D4], esi
0x1800bcd84  jnz     short loc_1800BCD8C
0x1800bcd86  cmp     [rsp+530h+var_4D8], esi
0x1800bcd8a  jz      short loc_1800BCD97
0x1800bcd8c  cmp     [rbp+430h+var_440], rsi
0x1800bcd90  jnz     short loc_1800BCDA8
0x1800bcd92  mov     ebx, 57h ; 'W'
0x1800bcd97  mov     rsi, [rsp+530h+var_4E0]
0x1800bcd9c  lea     rdi, WPP_GLOBAL_Control
0x1800bcda3  jmp     loc_1800BD7BB
0x1800bcda8  xorps   xmm0, xmm0
0x1800bcdab  lea     r8, [rbp+430h+BufferType]; BufferType
0x1800bcdaf  lea     rdx, [rbp+430h+NameBuffer]; lpNameBuffer
0x1800bcdb3  xor     ecx, ecx; lpServer
0x1800bcdb5  movups  [rbp+430h+var_400], xmm0
0x1800bcdb9  call    cs:__imp_NetGetJoinInformation
0x1800bcdbf  mov     ebx, eax
0x1800bcdc1  test    eax, eax
0x1800bcdc3  jz      short loc_1800BCDCA
0x1800bcdc5  cmp     eax, 32h ; '2'
0x1800bcdc8  jnz     short loc_1800BCD97
0x1800bcdca  mov     rcx, [rbp+430h+NameBuffer]; Buffer
0x1800bcdce  test    rcx, rcx
0x1800bcdd1  jz      short loc_1800BCDD9
0x1800bcdd3  call    cs:__imp_NetApiBufferFree
0x1800bcdd9  cmp     [rbp+430h+BufferType], 3
0x1800bcddd  jnz     short loc_1800BCDE8
0x1800bcddf  mov     dword ptr [rbp+430h+var_400], esi
0x1800bcde2  mov     dword ptr [rbp+430h+var_400+8], r13d
0x1800bcde6  jmp     short loc_1800BCE01
0x1800bcde8  mov     rax, [rbp+430h+var_418]
0x1800bcdec  test    rax, rax
0x1800bcdef  jz      short loc_1800BCD92
0x1800bcdf1  mov     dword ptr [rbp+430h+var_400+8], eax
0x1800bcdf4  mov     eax, dword ptr [rbp+430h+var_418+4]
0x1800bcdf7  mov     dword ptr [rbp+430h+var_400+0Ch], eax
0x1800bcdfa  mov     dword ptr [rbp+430h+var_400], 2
0x1800bce01  mov     rcx, [rbp+430h+var_440]
0x1800bce05  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800bce0c  nop     dword ptr [rax+00h]
0x1800bce10  cmp     [rcx+rax*2+2], si
0x1800bce15  lea     rax, [rax+1]
0x1800bce19  jnz     short loc_1800BCE10
0x1800bce1b  lea     rbx, [rax+1BDh]
0x1800bce22  lea     r13, [rbx+rbx]
0x1800bce26  mov     [rbp+430h+var_448], rbx
0x1800bce2a  mov     rcx, r13
0x1800bce2d  mov     [rbp+430h+var_480], r13
0x1800bce31  call    cs:__imp_FwAlloc
0x1800bce37  mov     [rsp+530h+var_4C8], rax
0x1800bce3c  mov     rcx, rax; pszDest
0x1800bce3f  test    rax, rax
0x1800bce42  jnz     short loc_1800BCE5A
0x1800bce44  mov     rsi, [rsp+530h+var_4E0]
0x1800bce49  lea     rdi, WPP_GLOBAL_Control
0x1800bce50  mov     ebx, 0Eh
0x1800bce55  jmp     loc_1800BD7BB
0x1800bce5a  lea     rax, [rbp+430h+var_3D0]
0x1800bce5e  xor     r8d, r8d; unsigned __int16 **
0x1800bce61  mov     [rsp+530h+var_4F0], rax
0x1800bce66  lea     r9, [rbp+430h+var_448]; unsigned __int64 *
0x1800bce6a  mov     rax, [rbp+430h+var_440]
0x1800bce6e  mov     rdx, rbx; cchDest
0x1800bce71  mov     [rsp+530h+var_4F8], rax
0x1800bce76  lea     rax, [rbp+430h+var_3C0]
0x1800bce7a  mov     [rsp+530h+var_500], rax
0x1800bce7f  lea     rax, aWsWsWs; "%ws%ws%ws"
0x1800bce86  mov     [rsp+530h+var_508], rax; unsigned __int16 *
0x1800bce8b  mov     qword ptr [rsp+530h+dwFlags], rsi; dwFlags
0x1800bce90  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800bce95  mov     ebx, eax
0x1800bce97  test    eax, eax
0x1800bce99  js      loc_1800BD7A1
0x1800bce9f  mov     r9, [rsp+530h+var_4C8]
0x1800bcea4  lea     rdx, [rsp+530h+var_4B8]
0x1800bcea9  mov     r8, [rbp+430h+var_440]
0x1800bcead  mov     dword ptr [rsp+530h+var_508], 1
0x1800bceb5  mov     qword ptr [rsp+530h+dwFlags], r13
0x1800bceba  call    ?FwMoneisCreateEnterpriseIdRule@EnterpriseDomainProtection@appIsolation@@AEAAKPEAPEAU_tag_FW_RULE@@PEBG1_KW4_tag_FW_DIRECTION@@@Z; appIsolation::EnterpriseDomainProtection::FwMoneisCreateEnterpriseIdRule(_tag_FW_RULE * *,ushort const *,ushort const *,unsigned __int64,_tag_FW_DIRECTION)
0x1800bcebf  mov     ebx, eax
0x1800bcec1  test    eax, eax
0x1800bcec3  jnz     loc_1800BD5C9
0x1800bcec9  mov     r9, [rsp+530h+var_4C8]
0x1800bcece  lea     rdx, [rbp+430h+var_4A8]
0x1800bced2  mov     r8, [rbp+430h+var_440]
0x1800bced6  mov     dword ptr [rsp+530h+var_508], 2
0x1800bcede  mov     qword ptr [rsp+530h+dwFlags], r13
0x1800bcee3  call    ?FwMoneisCreateEnterpriseIdRule@EnterpriseDomainProtection@appIsolation@@AEAAKPEAPEAU_tag_FW_RULE@@PEBG1_KW4_tag_FW_DIRECTION@@@Z; appIsolation::EnterpriseDomainProtection::FwMoneisCreateEnterpriseIdRule(_tag_FW_RULE * *,ushort const *,ushort const *,unsigned __int64,_tag_FW_DIRECTION)
0x1800bcee8  mov     ebx, eax
0x1800bceea  test    eax, eax
0x1800bceec  jnz     loc_1800BD5C9
0x1800bcef2  lea     rdx, [rbp+430h+var_4A0]
0x1800bcef6  mov     [rsp+530h+dwFlags], 1
0x1800bcefe  call    ?FwMoneisCreatePersonalRule@EnterpriseDomainProtection@appIsolation@@AEAAKPEAPEAU_tag_FW_RULE@@PEBG1W4_tag_FW_DIRECTION@@@Z; appIsolation::EnterpriseDomainProtection::FwMoneisCreatePersonalRule(_tag_FW_RULE * *,ushort const *,ushort const *,_tag_FW_DIRECTION)
0x1800bcf03  mov     ebx, eax
0x1800bcf05  test    eax, eax
0x1800bcf07  jnz     loc_1800BD5C9
0x1800bcf0d  lea     rdx, [rbp+430h+var_498]
0x1800bcf11  mov     [rsp+530h+dwFlags], 2
0x1800bcf19  call    ?FwMoneisCreatePersonalRule@EnterpriseDomainProtection@appIsolation@@AEAAKPEAPEAU_tag_FW_RULE@@PEBG1W4_tag_FW_DIRECTION@@@Z; appIsolation::EnterpriseDomainProtection::FwMoneisCreatePersonalRule(_tag_FW_RULE * *,ushort const *,ushort const *,_tag_FW_DIRECTION)
0x1800bcf1e  mov     ebx, eax
0x1800bcf20  test    eax, eax
0x1800bcf22  jnz     loc_1800BD5C9
0x1800bcf28  mov     eax, [rsp+530h+var_4D4]
0x1800bcf2c  mov     r13, [rbp+430h+var_498]
0x1800bcf30  cmp     eax, 1
0x1800bcf33  jnz     short loc_1800BCF53
0x1800bcf35  mov     rax, [rbp+430h+var_4A0]
0x1800bcf39  mov     dword ptr [rax+120h], 2
0x1800bcf43  mov     dword ptr [r13+120h], 2
0x1800bcf4e  jmp     loc_1800BD05E
0x1800bcf53  cmp     eax, 2
0x1800bcf56  jnz     loc_1800BD05E
0x1800bcf5c  lea     rdx, [rbp+430h+var_438]
0x1800bcf60  mov     rcx, r13
0x1800bcf63  call    cs:__imp_FwCopyRule
0x1800bcf69  mov     ecx, eax
0x1800bcf6b  call    cs:__imp_FwHResultToWindowsError
0x1800bcf71  mov     ebx, eax
0x1800bcf73  test    eax, eax
0x1800bcf75  jnz     loc_1800BD5C9
0x1800bcf7b  mov     rdx, [rbp+430h+var_438]
0x1800bcf7f  mov     rdx, [rdx+10h]; unsigned __int16 *
0x1800bcf83  call    ?FwMoneisFillRuleId@EnterpriseDomainProtection@appIsolation@@AEAAKPEAG@Z; appIsolation::EnterpriseDomainProtection::FwMoneisFillRuleId(ushort *)
0x1800bcf88  mov     ebx, eax
0x1800bcf8a  test    eax, eax
0x1800bcf8c  jnz     loc_1800BD5C9
0x1800bcf92  mov     rax, [rbp+430h+var_438]
0x1800bcf96  lea     rcx, aS1152362405143; "S-1-15-2-3624051433-2125758914-14231912"...
0x1800bcf9d  lea     rdx, [rbp+430h+var_430]
0x1800bcfa1  mov     dword ptr [rax+120h], 2
0x1800bcfab  mov     rax, [rbp+430h+var_438]
0x1800bcfaf  mov     [rax+178h], rcx
0x1800bcfb6  mov     rcx, r13
0x1800bcfb9  call    cs:__imp_FwCopyRule
0x1800bcfbf  mov     ecx, eax
0x1800bcfc1  call    cs:__imp_FwHResultToWindowsError
0x1800bcfc7  mov     ebx, eax
0x1800bcfc9  test    eax, eax
  ... truncated ...
```
