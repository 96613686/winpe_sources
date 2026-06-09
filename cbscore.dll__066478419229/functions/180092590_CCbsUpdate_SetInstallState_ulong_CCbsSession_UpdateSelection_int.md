# CCbsUpdate::SetInstallState(ulong,CCbsSession *,UpdateSelection,int)

- ea: `0x180092590`
- end: `0x180093502`
- name: `?SetInstallState@CCbsUpdate@@QEAAJKPEAVCCbsSession@@W4UpdateSelection@@H@Z`
- size: `3954`
- prototype: ``
- caller_count: `6`
- callee_count: `37`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180068de0`
- `0x18015ac58`
- `0x1801680f4`
- `0x1801a9cd8`
- `0x1801b1874`
- `0x1801bc584`

## callees

- `0x18000d910`
- `0x18000e780`
- `0x180010cc0`
- `0x1800138b8`
- `0x18001e1a0`
- `0x180022c78`
- `0x18002341c`
- `0x180023444`
- `0x18003f40c`
- `0x18004a1cc`
- `0x18004d564`
- `0x180092590`
- `0x180093a70`
- `0x180093c4c`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800a0988`
- `0x1800a5fe0`
- `0x1800ad504`
- `0x1800be2e0`
- `0x1800be858`
- `0x1800e9f30`
- `0x1800eb920`
- `0x1801433b8`
- `0x18014b4e4`
- `0x18015a428`
- `0x1801a33f0`
- `0x1801b23c8`
- `0x1801b2460`
- `0x1801b260c`
- `0x1801b28bc`
- `0x1801b40fc`
- `0x1801c2c30`
- `0x1801c8ac4`
- `0x1801d304c`

## string_xrefs

- `0x180092629`: `onecore\base\cbs\core\cbsupdate.cpp`
- `0x180092a9f`: `onecore\base\cbs\core\cbsupdate.cpp`
- `0x1800931da`: `onecore\base\cbs\core\cbsupdate.cpp`
- `0x18009335d`: `onecore\base\cbs\core\cbsupdate.cpp`
- `0x18009343a`: `onecore\base\cbs\core\cbsupdate.cpp`
- `0x1800927d0`: `Update: Setting Install State, Package: {}, Update: {}, new state: {}`
- `0x180092727`: `Attempt to change a finalized session`
- `0x180093477`: `Failed to decompress OC content.`
- `0x1800928ac`: `Windows Optional Component Manager`
- `0x180092bdc`: `Update: Setting SynchronousScavenge to ensure content is immediately removed for {}, package: {}`
- `0x180092c35`: `Failed to get per-session update state`
- `0x1800929b9`: `Update: Inferring removal for disable request by client '{}' for {}, package: {}`
- `0x180092a1e`: `Update: Failed to check if the payload is removable for Package: {}, Update: {}`
- `0x180092832`: `Cannot change state of Update because Update: {} is not selectable.`
- `0x180092ff9`: `Failed to add task for package: {}, update: {}`
- `0x180093219`: `Exec: NetFx3 OC and package already added to the execution, ignore the failure and just added the feature name`
- `0x1800930db`: `Update: State is unchanged, Package: {}, Update: {}, current State: {}, new state: {}, RemovePayload: {}`
- `0x180092f61`: `Update: Setting Install State, Package: {}, Update: {}, current State: {}, new state: {}, RemovePayload: {}`
- `0x180092cb8`: `Failed to get current selection state for package: {}, update: {}`
- `0x180092ea2`: `No write operations (enable/disable feature) are allowed on a container, states: {}, {}`

## pseudocode

```c
__int64 __fastcall CCbsUpdate::SetInstallState(__int64 a1, unsigned int a2, __int64 a3, unsigned int a4, int a5)
{
  unsigned int v6; // r13d
  unsigned int v8; // edi
  __int64 v9; // rdx
  const wchar_t *v11; // r14
  struct PerSessionUpdateState *v12; // rax
  __int64 v13; // rax
  int v14; // edx
  int v15; // edx
  __int64 v16; // rax
  int v17; // edx
  bool v18; // zf
  struct PerSessionUpdateState *v19; // r14
  const wchar_t *v20; // rcx
  const wchar_t *v21; // rax
  __int64 v22; // rax
  int v23; // r9d
  __int64 v24; // r10
  int v25; // edx
  _WORD *v26; // rdx
  __int64 v27; // rax
  __int64 v28; // xmm0_8
  __int64 v29; // rax
  __int64 v30; // xmm0_8
  __int64 v31; // rbx
  __int64 v32; // rax
  __int64 v33; // xmm0_8
  const wchar_t *v34; // rdx
  __int64 v35; // rax
  __int64 v36; // xmm0_8
  int v37; // edx
  const wchar_t *v38; // rax
  const wchar_t *v39; // rax
  int v40; // eax
  unsigned int v41; // r12d
  __int64 v42; // rax
  const wchar_t *v43; // rcx
  int v44; // edx
  __int64 v45; // rdx
  int v46; // eax
  int v47; // ecx
  __int64 v48; // rbx
  __int64 v49; // rax
  __int64 v50; // xmm0_8
  const wchar_t *v51; // rdx
  __int64 v52; // rax
  __int64 v53; // xmm0_8
  int v54; // edx
  const wchar_t *v55; // rax
  const wchar_t *v56; // rax
  int SessionUpdateState; // eax
  int v58; // edx
  int CurrentSelectionState; // eax
  int v60; // r9d
  __int64 v61; // rax
  const wchar_t *v62; // rcx
  int v63; // edx
  unsigned int v64; // ebx
  const wchar_t *v65; // rax
  __int64 v66; // rax
  int v67; // edx
  struct PerSessionUpdateState *v68; // rax
  __int64 v69; // r12
  __int64 v70; // rcx
  int v71; // r10d
  int v72; // edx
  int v73; // edx
  int v74; // r8d
  const wchar_t *v75; // rax
  struct PerSessionUpdateState *v76; // rcx
  __int64 v77; // rax
  int v78; // eax
  __int64 v79; // rax
  const wchar_t *v80; // rcx
  int v81; // edx
  __int64 v82; // rax
  int v83; // edx
  __int64 v84; // r8
  const wchar_t *v85; // rax
  __int64 v86; // rax
  unsigned int v87; // ecx
  __int64 *v88; // r13
  __int64 *v89; // rax
  __int64 v90; // r12
  CCbsCapabilityManager *v91; // rbx
  struct CCbsCapability **InitPointer; // rax
  int v93; // r12d
  const wchar_t *v94; // rdx
  int v95; // eax
  unsigned int v96; // ebx
  __int64 v97; // rdx
  const wchar_t *v98; // rcx
  __int64 v99; // rax
  int v100; // edx
  int v101; // r8d
  int v102; // r9d
  const wchar_t *v103; // rcx
  struct PerSessionUpdateState *v104; // rax
  __int64 v105; // rax
  int v106; // edx
  const wchar_t *v107; // rcx
  int v108; // eax
  unsigned int v109; // esi
  int v110; // edx
  int v111; // eax
  int v112; // edx
  __int64 v113; // rax
  const wchar_t *v114; // r8
  int v115; // [rsp+20h] [rbp-E0h]
  int v116[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v117; // [rsp+58h] [rbp-A8h]
  int v118[2]; // [rsp+60h] [rbp-A0h] BYREF
  int *v119; // [rsp+68h] [rbp-98h] BYREF
  struct PerSessionUpdateState *v120; // [rsp+70h] [rbp-90h] BYREF
  int v121[2]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v122; // [rsp+80h] [rbp-80h] BYREF
  __int64 v123; // [rsp+90h] [rbp-70h]
  _BYTE v124[24]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v125; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v126; // [rsp+C0h] [rbp-40h]
  _BYTE v127[24]; // [rsp+C8h] [rbp-38h] BYREF
  int v128[2]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v129; // [rsp+E8h] [rbp-18h] BYREF
  const wchar_t *v130; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v129 = a4;
  v6 = a2;
  if ( !a3 )
  {
    v8 = -2147024809;
    v128[0] = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No session specified");
      v120 = (struct PerSessionUpdateState *)v128;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        1,
        3,
        (unsigned int)": {}",
        (__int64)&v120);
    }
    v9 = 276;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsupdate.cpp",
      (const char *)v8,
      v115);
    return v8;
  }
  if ( a4 != 255 && a4 > 1 && a4 != 999 )
  {
    v8 = -2146498560;
    v128[0] = -2146498560;
    if ( LogAdapter::g_Logger )
    {
      v11 = &qword_1802EB518;
      v12 = (struct PerSessionUpdateState *)&qword_1802EB518;
      if ( *(_QWORD *)(a1 + 32) )
        v12 = *(struct PerSessionUpdateState **)(a1 + 32);
      v120 = v12;
      v13 = *(_QWORD *)(a1 + 24);
      if ( *(_QWORD *)(v13 + 120) )
        v11 = *(const wchar_t **)(v13 + 120);
      v130 = v11;
      LogAdapter::Logger::LogNumObjects<enum UpdateSelection,wchar_t const *,wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        a2,
        a3,
        a4,
        (__int64)&v129,
        (__int64)&v130,
        (__int64)&v120);
      *(_QWORD *)v118 = v128;
      LOBYTE(v14) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v14,
        3,
        (unsigned int)": {}",
        (__int64)v118);
    }
    v9 = 279;
    goto LABEL_5;
  }
  if ( a5 && (unsigned int)CCbsSession::IsLocked((CCbsSession *)a3) )
  {
    v8 = -2146498494;
    v128[0] = -2146498494;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Attempt to change a finalized session");
      *(_QWORD *)v118 = v128;
      LOBYTE(v15) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v15,
        3,
        (unsigned int)": {}",
        (__int64)v118);
    }
    v9 = 281;
    goto LABEL_5;
  }
  LODWORD(v130) = -1;
  v120 = 0;
  v128[0] = 0;
  v16 = CbsSelectionToString(a4);
  v18 = *(_QWORD *)(a1 + 32) == 0;
  v19 = (struct PerSessionUpdateState *)&qword_1802EB518;
  v20 = &qword_1802EB518;
  *(_QWORD *)v118 = v16;
  v21 = &qword_1802EB518;
  if ( !v18 )
    v21 = *(const wchar_t **)(a1 + 32);
  v119 = (int *)v21;
  v22 = *(_QWORD *)(a1 + 24);
  if ( *(_QWORD *)(v22 + 120) )
    v20 = *(const wchar_t **)(v22 + 120);
  *(_QWORD *)v116 = v20;
  if ( LogAdapter::g_Logger )
  {
    LOBYTE(v17) = 1;
    LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
      (_DWORD)LogAdapter::g_Logger,
      v17,
      1,
      (unsigned int)"Update: Setting Install State, Package: {}, Update: {}, new state: {}",
      (__int64)v116,
      (__int64)&v119,
      (__int64)v118);
  }
  if ( !(unsigned int)CCbsUpdate::IsSelectable((CCbsUpdate *)a1) )
  {
    v8 = -2146498541;
    v128[0] = -2146498541;
    if ( v24 )
    {
      if ( *(_QWORD *)(a1 + 32) )
        v19 = *(struct PerSessionUpdateState **)(a1 + 32);
      *(_QWORD *)v116 = v19;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        v24,
        0,
        3,
        (unsigned int)"Cannot change state of Update because Update: {} is not selectable.",
        (__int64)v116);
      v119 = v128;
      LOBYTE(v25) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v25,
        3,
        (unsigned int)": {}",
        (__int64)&v119);
    }
    v9 = 296;
    goto LABEL_5;
  }
  if ( !v23 )
  {
    v26 = *(_WORD **)(a3 + 648);
    if ( v26 )
    {
      if ( *v26 )
      {
        v27 = Windows::StringUtil::AsLUnicode(v127, v26);
        v28 = *(_QWORD *)(v27 + 16);
        v125 = *(_OWORD *)v27;
        v126 = v28;
        v29 = Windows::StringUtil::AsLUnicode(v124, L"Windows Optional Component Manager");
        v30 = *(_QWORD *)(v29 + 16);
        v122 = *(_OWORD *)v29;
        v123 = v30;
        if ( (unsigned __int8)Windows::StringUtil::IsStringPrefixEqualByOrdinalCaseInvariant<_LUNICODE_STRING,_LUNICODE_STRING>(
                                &v122,
                                &v125) )
        {
          if ( (unsigned int)CCbsUpdate::GetDeploymentType(a1) != 5 )
          {
            v31 = *(_QWORD *)(a1 + 24);
            v32 = Windows::StringUtil::AsLUnicode(v124, *(_QWORD *)(v31 + 112) + 30LL);
            v33 = *(_QWORD *)(v32 + 16);
            v122 = *(_OWORD *)v32;
            v123 = v33;
            if ( (unsigned __int8)Windows::StringUtil::AreStringAndLowerCaseAsciiStringEqualCaseInvariant<_LUNICODE_STRING,wchar_t [30]>(&v122) )
            {
              v34 = &qword_1802EB518;
              if ( *(_QWORD *)(a1 + 32) )
                v34 = *(const wchar_t **)(a1 + 32);
              v35 = Windows::StringUtil::AsLUnicode(v124, v34);
              v36 = *(_QWORD *)(v35 + 16);
              v122 = *(_OWORD *)v35;
              v123 = v36;
              if ( (unsigned __int8)Windows::StringUtil::AreStringAndLowerCaseAsciiStringEqualCaseInvariant<_LUNICODE_STRING,wchar_t [7]>(&v122) )
              {
                v38 = &qword_1802EB518;
                if ( *(_QWORD *)(v31 + 120) )
                  v38 = *(const wchar_t **)(v31 + 120);
                v18 = *(_QWORD *)(a1 + 32) == 0;
                *(_QWORD *)v116 = v38;
                v39 = &qword_1802EB518;
                if ( !v18 )
                  v39 = *(const wchar_t **)(a1 + 32);
                v119 = (int *)v39;
                *(_QWORD *)v118 = *(_QWORD *)(a3 + 648);
                if ( LogAdapter::g_Logger )
                {
                  LOBYTE(v37) = 1;
                  LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
                    (_DWORD)LogAdapter::g_Logger,
                    v37,
                    1,
                    (unsigned int)"Update: Inferring removal for disable request by client '{}' for {}, package: {}",
                    (__int64)v118,
                    (__int64)&v119,
                    (__int64)v116);
                }
                v6 |= 1u;
              }
            }
          }
        }
      }
    }
  }
  if ( (v6 & 1) != 0 )
  {
    v117 = 0;
    v40 = IsSelectablePayloadRemovable((CCbsSession *)a3, (CCbsUpdate *)a1);
    v41 = v40;
    if ( v40 < 0 )
    {
      v128[0] = v40;
      if ( LogAdapter::g_Logger )
      {
        v42 = *(_QWORD *)(a1 + 24);
        v43 = &qword_1802EB518;
        if ( *(_QWORD *)(a1 + 32) )
          v43 = *(const wchar_t **)(a1 + 32);
        *(_QWORD *)v116 = v43;
        if ( *(_QWORD *)(v42 + 120) )
          v19 = *(struct PerSessionUpdateState **)(v42 + 120);
        v119 = (int *)v19;
        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Update: Failed to check if the payload is removable for Package: {}, Update: {}",
          (__int64)&v119,
          (__int64)v116);
        *(_QWORD *)v118 = v128;
        LOBYTE(v44) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v44,
          3,
          (unsigned int)": {}",
          (__int64)v118);
      }
      v45 = 320;
LABEL_58:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v45,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsupdate.cpp",
        (const char *)v41,
        v115);
      return v41;
    }
    if ( v117 )
    {
      if ( !(unsigned int)CCbsSession::IsClientPBR((CCbsSession *)a3) && !*(_BYTE *)(a3 + 1744) )
      {
        v46 = *(_DWORD *)(a3 + 692);
        if ( v46 >= 0 )
        {
          v47 = *(_DWORD *)(a3 + 2208);
          if ( (v47 & 0x100000) == 0 && (v46 & 4) == 0 && (v47 & 0x20) == 0 && (v47 & 0x10) == 0 && (v46 & 0x20) == 0 )
          {
            v48 = *(_QWORD *)(a1 + 24);
            v49 = Windows::StringUtil::AsLUnicode(v124, *(_QWORD *)(v48 + 112) + 30LL);
            v50 = *(_QWORD *)(v49 + 16);
            v122 = *(_OWORD *)v49;
            v123 = v50;
            if ( (unsigned __int8)Windows::StringUtil::AreStringAndLowerCaseAsciiStringEqualCaseInvariant<_LUNICODE_STRING,wchar_t [30]>(&v122) )
            {
              v51 = &qword_1802EB518;
              if ( *(_QWORD *)(a1 + 32) )
                v51 = *(const wchar_t **)(a1 + 32);
              v52 = Windows::StringUtil::AsLUnicode(v124, v51);
              v53 = *(_QWORD *)(v52 + 16);
              v122 = *(_OWORD *)v52;
              v123 = v53;
              if ( (unsigned __int8)Windows::StringUtil::AreStringAndLowerCaseAsciiStringEqualCaseInvariant<_LUNICODE_STRING,wchar_t [7]>(&v122)
                && CCbsSession::IsAnLCUInstalled((CCbsSession *)a3, 0) )
              {
                v55 = &qword_1802EB518;
                if ( *(_QWORD *)(v48 + 120) )
                  v55 = *(const wchar_t **)(v48 + 120);
                v18 = *(_QWORD *)(a1 + 32) == 0;
                *(_QWORD *)v116 = v55;
                v56 = &qword_1802EB518;
                if ( !v18 )
                  v56 = *(const wchar_t **)(a1 + 32);
                v119 = (int *)v56;
                if ( LogAdapter::g_Logger )
                {
                  LOBYTE(v54) = 1;
                  LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                    (_DWORD)LogAdapter::g_Logger,
                    v54,
                    1,
                    (unsigned int)"Update: Setting SynchronousScavenge to ensure content is immediately removed for {}, package: {}",
                    (__int64)&v119,
                    (__int64)v116);
                }
                *(_DWORD *)(a3 + 688) |= 0x401u;
              }
            }
          }
        }
      }
    }
    else
    {
      v6 &= ~1u;
    }
  }
  SessionUpdateState = CCbsSession::GetSessionUpdateState((CCbsSession *)a3, (struct CCbsUpdate *)a1, 0, 1, &v120);
  v41 = SessionUpdateState;
  if ( SessionUpdateState < 0 )
  {
    v128[0] = SessionUpdateState;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get per-session update state");
      *(_QWORD *)v116 = v128;
      LOBYTE(v58) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v58,
        3,
        (unsigned int)": {}",
        (__int64)v116);
    }
    v45 = 355;
    goto LABEL_58;
  }
  CurrentSelectionState = CCbsUpdate::GetCurrentSelectionState(
                            (CCbsUpdate *)a1,
                            (struct CCbsSession *)a3,
                            (enum UpdateSelection *)&v130,
                            v128);
  v41 = CurrentSelectionState;
  if ( CurrentSelectionState < 0 )
  {
    v128[0] = CurrentSelectionState;
    if ( LogAdapter::g_Logger )
    {
      v61 = *(_QWORD *)(a1 + 24);
      v62 = &qword_1802EB518;
      if ( *(_QWORD *)(a1 + 32) )
        v62 = *(const wchar_t **)(a1 + 32);
      *(_QWORD *)v116 = v62;
      if ( *(_QWORD *)(v61 + 120) )
        v19 = *(struct PerSessionUpdateState **)(v61 + 120);
      v119 = (int *)v19;
      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to get current selection state for package: {}, update: {}",
        (__int64)&v119,
        (__int64)v116);
      *(_QWORD *)v118 = v128;
      LOBYTE(v63) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v63,
        3,
        (unsigned int)": {}",
        (__int64)v118);
    }
    v45 = 358;
    goto LABEL_58;
  }
  v64 = (unsigned int)v130;
  if ( v129 < 2 || v129 == 255 )
  {
    v68 = v120;
    *((_DWORD *)v120 + 2) = v129;
  }
  else
  {
    if ( v129 != 999 )
    {
      v8 = -2146498560;
      LODWORD(v130) = -2146498560;
      if ( LogAdapter::g_Logger )
      {
        v65 = &qword_1802EB518;
        if ( *(_QWORD *)(a1 + 32) )
          v65 = *(const wchar_t **)(a1 + 32);
        *(_QWORD *)v116 = v65;
        v66 = *(_QWORD *)(a1 + 24);
        if ( *(_QWORD *)(v66 + 120) )
          v19 = *(struct PerSessionUpdateState **)(v66 + 120);
        v119 = (int *)v19;
        LogAdapter::Logger::LogNumObjects<enum UpdateSelection,wchar_t const *,wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          v129,
          0,
          v60,
          (__int64)&v129,
          (__int64)&v119,
          (__int64)v116);
        *(_QWORD *)v118 = &v130;
        LOBYTE(v67) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v67,
          3,
          (unsigned int)": {}",
          (__int64)v118);
      }
      v9 = 380;
      goto LABEL_5;
    }
    v68 = v120;
    *((_DWORD *)v120 + 2) = (_DWORD)v130;
  }
  v69 = (__int64)v68 + 24;
  *((_DWORD *)v68 + 6) = v6;
  v70 = v129;
  if ( v64 == v129 )
    goto LABEL_111;
  if ( v64 == 255 )
  {
    if ( v129 == 1 && *(_DWORD *)(a1 + 448) )
      goto LABEL_136;
    if ( v129 || *(_DWORD *)(a1 + 448) )
      goto LABEL_114;
LABEL_111:
    if ( v129 )
      goto LABEL_137;
    if ( (v6 & 1) != 0 && !v128[0] )
      goto LABEL_114;
LABEL_136:
    if ( !v129 )
      goto LABEL_121;
LABEL_137:
    *(_QWORD *)v116 = CbsSelectionToString(v129);
    v82 = CbsSelectionToString(v64);
    v18 = *(_QWORD *)(a1 + 32) == v84;
    v119 = (int *)v82;
    v85 = &qword_1802EB518;
    if ( !v18 )
      v85 = *(const wchar_t **)(a1 + 32);
    *(_QWORD *)v118 = v85;
    v86 = *(_QWORD *)(a1 + 24);
    if ( *(_QWORD *)(v86 + 120) != v84 )
      v19 = *(struct PerSessionUpdateState **)(v86 + 120);
    v120 = v19;
    if ( LogAdapter::g_Logger )
      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,unsigned long>(
        (_DWORD)LogAdapter::g_Logger,
        v83,
        v84,
        (unsigned int)"Update: State is unchanged, Package: {}, Update: {}, current State: {}, new state: {}, RemovePayload: {}",
        (__int64)&v120,
        (__int64)v118,
        (__int64)&v119,
        (__int64)v116,
        v69);
    return 0;
  }
LABEL_114:
  if ( CCbsSession::IsImageReadOnly((CCbsSession *)a3) )
  {
    if ( !vbInTestMode )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v8 = -2146498493;
    v128[0] = -2146498493;
    if ( LogAdapter::g_Logger )
    {
      *(_QWORD *)v116 = CbsSelectionToString(v129);
      v119 = (int *)CbsSelectionToString(v64);
      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
        v71,
        0,
        3,
        (unsigned int)"No write operations (enable/disable feature) are allowed on a container, states: {}, {}",
        (__int64)&v119,
        (__int64)v116);
      *(_QWORD *)v118 = v128;
      LOBYTE(v72) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v72,
        3,
        (unsigned int)": {}",
        (__int64)v118);
    }
    v9 = 416;
    goto LABEL_5;
  }
  v70 = v129;
LABEL_121:
  *(_QWORD *)v116 = CbsSelectionToString(v70);
  v119 = (int *)CbsSelectionToString(v64);
  v75 = &qword_1802EB518;
  v76 = (struct PerSessionUpdateState *)&qword_1802EB518;
  if ( *(_QWORD *)(a1 + 32) )
    v75 = *(const wchar_t **)(a1 + 32);
  *(_QWORD *)v118 = v75;
  v77 = *(_QWORD *)(a1 + 24);
  if ( *(_QWORD *)(v77 + 120) )
    v76 = *(struct PerSessionUpdateState **)(v77 + 120);
  v120 = v76;
  if ( LogAdapter::g_Logger )
    LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,unsigned long>(
      (_DWORD)LogAdapter::g_Logger,
      v73,
      v74,
      (unsigned int)"Update: Setting Install State, Package: {}, Update: {}, current State: {}, new state: {}, RemovePayload: {}",
      (__int64)&v120,
      (__int64)v118,
      (__int64)&v119,
      (__int64)v116,
      v69);
  if ( !a5 )
  {
    v113 = *(_QWORD *)(a1 + 24);
    v114 = &qword_1802EB518;
    if ( *(_QWORD *)(a1 + 32) )
      v114 = *(const wchar_t **)(a1 + 32);
    if ( *(_QWORD *)(v113 + 120) )
      v19 = *(struct PerSessionUpdateState **)(v113 + 120);
    CCbsSession::ClearPlannedParentState((CCbsSession *)a3, (const wchar_t *const)v19, v114);
    return 0;
  }
  CCbsSession::InvalidateApplicabilityCache((CCbsSession *)a3);
  v115 = 0;
  v78 = CCbsSession::AddPackageTask(a3, 0, v6, *(_QWORD *)(a1 + 24));
  v41 = v78;
  if ( v78 < 0 )
  {
    v128[0] = v78;
    if ( LogAdapter::g_Logger )
    {
      v79 = *(_QWORD *)(a1 + 24);
      v80 = &qword_1802EB518;
      if ( *(_QWORD *)(a1 + 32) )
        v80 = *(const wchar_t **)(a1 + 32);
      *(_QWORD *)v116 = v80;
      if ( *(_QWORD *)(v79 + 120) )
        v19 = *(struct PerSessionUpdateState **)(v79 + 120);
      v119 = (int *)v19;
      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to add task for package: {}, update: {}",
        (__int64)&v119,
        (__int64)v116);
      *(_QWORD *)v118 = v128;
      LOBYTE(v81) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v81,
        3,
        (unsigned int)": {}",
        (__int64)v118);
    }
    v45 = 449;
    goto LABEL_58;
  }
  if ( (unsigned int)CCbsUpdate::GetDeploymentType(a1) == 5 )
  {
    if ( !CCbsSession::IsImageReadOnly((CCbsSession *)a3) )
    {
      v87 = v129;
      if ( v129 == 1 )
      {
        *(_DWORD *)(a3 + 2208) |= 0x44u;
      }
      else if ( !v129 )
      {
        *(_DWORD *)(a3 + 2208) |= 0x88u;
      }
      v88 = *(__int64 **)(a1 + 224);
      v89 = &v88[*(_QWORD *)(a1 + 208)];
      for ( *(_QWORD *)v121 = v89; ; v89 = *(__int64 **)v121 )
      {
        if ( v88 == v89 )
          goto LABEL_178;
        v90 = *v88;
        v130 = 0;
        v91 = vpCapabilityManager;
        *(_QWORD *)v116 = v90;
        InitPointer = (struct CCbsCapability **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v130);
        v93 = CCbsCapabilityManager::ResolveCapability(
                v91,
                (struct CCbsSession *)a3,
                *(const struct CCbsIdentity **)(*(_QWORD *)(v90 + 40) + 24LL),
                InitPointer);
        if ( v93 >= 0 && (v94 = (const wchar_t *)*((_QWORD *)v130 + 6)) != 0 )
        {
          v95 = CCbsStringArray::CopyAndAdd((CCbsStringArray *)(a3 + 1824), v94);
          v96 = v95;
          if ( v95 < 0 )
          {
            v97 = 520;
LABEL_155:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v97,
              (unsigned int)"onecore\\base\\cbs\\core\\cbsupdate.cpp",
              (const char *)(unsigned int)v95,
              v115);
LABEL_176:
            Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v130);
            return v96;
          }
        }
        else
        {
          v98 = &qword_1802EB518;
          if ( *(_QWORD *)(a1 + 32) )
            v98 = *(const wchar_t **)(a1 + 32);
          if ( (unsigned __int8)StringsAreEqual(v98, L"NetFx3", 1) && (*(_DWORD *)(a3 + 2208) & 0x2000) != 0 )
          {
            LogAdapter::TraceAtLevel<>(
              1,
              "Exec: NetFx3 OC and package already added to the execution, ignore the failure and just added the feature name");
            v95 = CCbsStringArray::CopyAndAdd((CCbsStringArray *)(a3 + 1824), L"NetFx3");
            v96 = v95;
            if ( v95 < 0 )
            {
              v97 = 503;
              goto LABEL_155;
            }
          }
          else if ( v129 )
          {
            if ( v93 < 0 )
            {
              v128[0] = v93;
              if ( LogAdapter::g_Logger )
              {
                if ( *(_QWORD *)(a1 + 32) )
                  v19 = *(struct PerSessionUpdateState **)(a1 + 32);
                *(_QWORD *)v121 = v19;
                LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                  (_DWORD)LogAdapter::g_Logger,
                  0,
                  3,
                  (unsigned int)"Failed to resolve OC capability: {}",
                  (__int64)v121);
                *(_QWORD *)v116 = v128;
                LOBYTE(v106) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v106,
                  3,
                  (unsigned int)": {}",
                  (__int64)v116);
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x204,
                (unsigned int)"onecore\\base\\cbs\\core\\cbsupdate.cpp",
                (const char *)(unsigned int)v93,
                v115);
              v96 = v93;
              goto LABEL_176;
            }
          }
          else
          {
            v119 = *(int **)(*(_QWORD *)(*(_QWORD *)v116 + 40LL) + 24LL);
            v99 = CbsSelectionToString(0);
            v18 = *(_QWORD *)(a1 + 32) == 0;
            v103 = &qword_1802EB518;
            *(_QWORD *)v118 = v99;
            v104 = (struct PerSessionUpdateState *)&qword_1802EB518;
            if ( !v18 )
              v104 = *(struct PerSessionUpdateState **)(a1 + 32);
            v120 = v104;
            v105 = *(_QWORD *)(a1 + 24);
            if ( *(_QWORD *)(v105 + 120) )
              v103 = *(const wchar_t **)(v105 + 120);
            *(_QWORD *)v128 = v103;
            if ( LogAdapter::g_Logger )
              LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t const *,wchar_t const *,CCbsIdentity *>(
                (_DWORD)LogAdapter::g_Logger,
                v100,
                v101,
                v102,
                (__int64)v128,
                (__int64)&v120,
                (__int64)v118,
                (__int64)&v119);
          }
        }
        Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v130);
        v87 = v129;
        ++v88;
      }
    }
    return 0;
  }
  v87 = v129;
LABEL_178:
  if ( v87 != 1 )
    return 0;
  v107 = &qword_1802EB518;
  if ( *(_QWORD *)(a1 + 32) )
    v107 = *(const wchar_t **)(a1 + 32);
  if ( !(unsigned __int8)StringsAreEqual(v107, L"Containers-DisposableClientVM", 1) )
  {
    if ( *(_QWORD *)(a1 + 32) )
      v19 = *(struct PerSessionUpdateState **)(a1 + 32);
    if ( !(unsigned __int8)StringsAreEqual(v19, L"Windows-Defender-ApplicationGuard", 1) )
      return 0;
  }
  v108 = CCbsSession::SetEnhancedOptions((CCbsSession *)a3, 0x40u);
  v109 = v108;
  if ( v108 >= 0 )
  {
    v111 = CCbsSession::DecompressOCContent((CCbsSession *)a3);
    v8 = v111;
    if ( v111 < 0 )
    {
      v128[0] = v111;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to decompress OC content.");
        *(_QWORD *)v121 = v128;
        LOBYTE(v112) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v112,
          3,
          (unsigned int)": {}",
          (__int64)v121);
      }
      v9 = 532;
      goto LABEL_5;
    }
    return 0;
  }
  v128[0] = v108;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to set the enhanced option on the session.");
    *(_QWORD *)v121 = v128;
    LOBYTE(v110) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v110,
      3,
      (unsigned int)": {}",
      (__int64)v121);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x212,
    (unsigned int)"onecore\\base\\cbs\\core\\cbsupdate.cpp",
    (const char *)v109,
    v115);
  return v109;
}

```

## disassembly

```asm
0x180092590  push    rbp
0x180092592  push    rbx
0x180092593  push    rsi
0x180092594  push    rdi
0x180092595  push    r12
0x180092597  push    r13
0x180092599  push    r14
0x18009259b  push    r15
0x18009259d  lea     rbp, [rsp-8]
0x1800925a2  sub     rsp, 108h
0x1800925a9  mov     rax, cs:__security_cookie
0x1800925b0  xor     rax, rsp
0x1800925b3  mov     [rbp+40h+var_48], rax
0x1800925b7  xor     ebx, ebx
0x1800925b9  mov     [rbp+40h+var_58], r9d
0x1800925bd  mov     rdi, r8
0x1800925c0  mov     r13d, edx
0x1800925c3  mov     rsi, rcx
0x1800925c6  test    r8, r8
0x1800925c9  jnz     short loc_18009263F
0x1800925cb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800925d2  mov     edi, 80070057h
0x1800925d7  mov     [rbp+40h+var_60], edi
0x1800925da  test    rcx, rcx
0x1800925dd  jz      short loc_180092620
0x1800925df  lea     ebx, [r8+3]
0x1800925e3  xor     edx, edx
0x1800925e5  mov     r8d, ebx
0x1800925e8  lea     r9, aNoSessionSpeci_0; "No session specified"
0x1800925ef  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800925f4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800925fb  lea     rax, [rbp+40h+var_60]
0x1800925ff  mov     [rsp+140h+var_D0], rax
0x180092604  lea     r9, asc_1802EE7AC; ": {}"
0x18009260b  lea     rax, [rsp+140h+var_D0]
0x180092610  mov     r8d, ebx
0x180092613  lea     edx, [rbx-2]
0x180092616  mov     [rsp+140h+var_120], rax; int
0x18009261b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180092620  mov     edx, 114h; void *
0x180092625  mov     rcx, [rbp+48h]; this
0x180092629  lea     r8, aOnecoreBaseCbs_96; "onecore\\base\\cbs\\core\\cbsupdate.cpp"
0x180092630  mov     r9d, edi; char *
0x180092633  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180092638  mov     eax, edi
0x18009263a  jmp     loc_1800934E1
0x18009263f  mov     r15d, 1
0x180092645  cmp     r9d, 0FFh
0x18009264c  jz      loc_1800926FD
0x180092652  cmp     r9d, r15d
0x180092655  jbe     loc_1800926FD
0x18009265b  cmp     r9d, 3E7h
0x180092662  jz      loc_1800926FD
0x180092668  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009266f  mov     edi, 800F0800h
0x180092674  mov     [rbp+40h+var_60], edi
0x180092677  test    rcx, rcx
0x18009267a  jz      short loc_1800926F3
0x18009267c  cmp     [rsi+20h], rbx
0x180092680  lea     r14, qword_1802EB518
0x180092687  mov     rax, r14
0x18009268a  cmovnz  rax, [rsi+20h]
0x18009268f  mov     [rsp+140h+var_D0], rax
0x180092694  mov     rax, [rsi+18h]
0x180092698  cmp     [rax+78h], rbx
0x18009269c  cmovnz  r14, [rax+78h]
0x1800926a1  lea     rax, [rsp+140h+var_D0]
0x1800926a6  mov     [rsp+140h+var_110], rax
0x1800926ab  lea     rax, [rbp+40h+var_50]
0x1800926af  mov     [rsp+140h+var_118], rax
0x1800926b4  lea     rax, [rbp+40h+var_58]
0x1800926b8  mov     [rsp+140h+var_120], rax
0x1800926bd  mov     [rbp+40h+var_50], r14
0x1800926c1  call    ??$LogNumObjects@W4UpdateSelection@@PEB_WPEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBW4UpdateSelection@@AEBQEB_W4@Z; LogAdapter::Logger::LogNumObjects<UpdateSelection,wchar_t const *,wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,UpdateSelection const &,wchar_t const * const &,wchar_t const * const &)
0x1800926c6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800926cd  lea     rax, [rbp+40h+var_60]
0x1800926d1  mov     qword ptr [rsp+140h+var_E0], rax
0x1800926d6  lea     r9, asc_1802EE7AC; ": {}"
0x1800926dd  lea     rax, [rsp+140h+var_E0]
0x1800926e2  mov     dl, r15b
0x1800926e5  lea     r8d, [r15+2]
0x1800926e9  mov     [rsp+140h+var_120], rax
0x1800926ee  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800926f3  mov     edx, 117h
0x1800926f8  jmp     loc_180092625
0x1800926fd  cmp     [rbp+40h+arg_20], ebx
0x180092700  jz      short loc_18009276E
0x180092702  mov     rcx, rdi; this
0x180092705  call    ?IsLocked@CCbsSession@@QEAAHXZ; CCbsSession::IsLocked(void)
0x18009270a  test    eax, eax
0x18009270c  jz      short loc_18009276E
0x18009270e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180092715  mov     edi, 800F0842h
0x18009271a  mov     [rbp+40h+var_60], edi
0x18009271d  test    rcx, rcx
0x180092720  jz      short loc_180092764
0x180092722  mov     ebx, 3
0x180092727  lea     r9, aAttemptToChang; "Attempt to change a finalized session"
0x18009272e  mov     r8d, ebx
0x180092731  xor     edx, edx
0x180092733  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180092738  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009273f  lea     rax, [rbp+40h+var_60]
0x180092743  mov     qword ptr [rsp+140h+var_E0], rax
0x180092748  lea     r9, asc_1802EE7AC; ": {}"
0x18009274f  lea     rax, [rsp+140h+var_E0]
0x180092754  mov     r8d, ebx
0x180092757  mov     dl, r15b
0x18009275a  mov     [rsp+140h+var_120], rax
0x18009275f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180092764  mov     edx, 119h
0x180092769  jmp     loc_180092625
0x18009276e  mov     ecx, r9d
0x180092771  mov     dword ptr [rbp+40h+var_50], 0FFFFFFFFh
0x180092778  mov     [rsp+140h+var_D0], rbx
0x18009277d  mov     [rbp+40h+var_60], ebx
0x180092780  call    ?CbsSelectionToString@@YAPEB_WW4UpdateSelection@@@Z; CbsSelectionToString(UpdateSelection)
0x180092785  cmp     [rsi+20h], rbx
0x180092789  lea     r14, qword_1802EB518
0x180092790  mov     r10, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180092797  mov     rcx, r14
0x18009279a  mov     qword ptr [rsp+140h+var_E0], rax
0x18009279f  mov     rax, r14
0x1800927a2  cmovnz  rax, [rsi+20h]
0x1800927a7  mov     [rsp+140h+var_D8], rax
0x1800927ac  mov     rax, [rsi+18h]
0x1800927b0  cmp     [rax+78h], rbx
0x1800927b4  cmovnz  rcx, [rax+78h]
0x1800927b9  mov     qword ptr [rsp+140h+var_F0], rcx
0x1800927be  test    r10, r10
0x1800927c1  jz      short loc_180092801
0x1800927c3  lea     rax, [rsp+140h+var_E0]
0x1800927c8  mov     r8d, r15d
0x1800927cb  mov     [rsp+140h+var_110], rax
0x1800927d0  lea     r9, aUpdateSettingI; "Update: Setting Install State, Package:"...
0x1800927d7  lea     rax, [rsp+140h+var_D8]
0x1800927dc  mov     dl, r15b
0x1800927df  mov     [rsp+140h+var_118], rax
0x1800927e4  mov     rcx, r10
0x1800927e7  lea     rax, [rsp+140h+var_F0]
0x1800927ec  mov     [rsp+140h+var_120], rax
0x1800927f1  call    ??$LogNumObjects@PEB_WVAutoScz@@PEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBVAutoScz@@AEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,AutoScz const &,wchar_t * const &)
0x1800927f6  mov     r10, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800927fd  mov     r9d, [rbp+40h+var_58]
0x180092801  mov     rcx, rsi; this
0x180092804  call    ?IsSelectable@CCbsUpdate@@QEBAHXZ; CCbsUpdate::IsSelectable(void)
0x180092809  test    eax, eax
0x18009280b  jnz     short loc_180092881
0x18009280d  mov     edi, 800F0813h
0x180092812  mov     [rbp+40h+var_60], edi
0x180092815  test    r10, r10
0x180092818  jz      short loc_180092877
0x18009281a  cmp     [rsi+20h], rbx
0x18009281e  lea     rax, [rsp+140h+var_F0]
0x180092823  mov     ebx, 3
0x180092828  mov     [rsp+140h+var_120], rax
0x18009282d  cmovnz  r14, [rsi+20h]
0x180092832  lea     r9, aCannotChangeSt; "Cannot change state of Update because U"...
0x180092839  xor     edx, edx
0x18009283b  mov     qword ptr [rsp+140h+var_F0], r14
0x180092840  mov     r8d, ebx
0x180092843  mov     rcx, r10
0x180092846  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18009284b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180092852  lea     rax, [rbp+40h+var_60]
0x180092856  mov     [rsp+140h+var_D8], rax
0x18009285b  lea     r9, asc_1802EE7AC; ": {}"
0x180092862  lea     rax, [rsp+140h+var_D8]
0x180092867  mov     r8d, ebx
0x18009286a  mov     dl, r15b
0x18009286d  mov     [rsp+140h+var_120], rax
0x180092872  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180092877  mov     edx, 128h
0x18009287c  jmp     loc_180092625
0x180092881  test    r9d, r9d
0x180092884  jnz     loc_1800929E3
0x18009288a  mov     rdx, [rdi+288h]
0x180092891  test    rdx, rdx
0x180092894  jz      loc_1800929E3
0x18009289a  cmp     bx, [rdx]
0x18009289d  jz      loc_1800929E3
0x1800928a3  lea     rcx, [rbp+40h+var_78]
0x1800928a7  call    ?AsLUnicode@StringUtil@Windows@@YA?AU_LUNICODE_STRING@@PEB_W@Z; Windows::StringUtil::AsLUnicode(wchar_t const *)
0x1800928ac  lea     rdx, aWindowsOptiona; "Windows Optional Component Manager"
0x1800928b3  lea     rcx, [rbp+40h+var_A8]
0x1800928b7  movups  xmm1, xmmword ptr [rax]
0x1800928ba  movsd   xmm0, qword ptr [rax+10h]
0x1800928bf  movups  [rbp+40h+var_90], xmm1
0x1800928c3  movsd   [rbp+40h+var_80], xmm0
0x1800928c8  call    ?AsLUnicode@StringUtil@Windows@@YA?AU_LUNICODE_STRING@@PEB_W@Z; Windows::StringUtil::AsLUnicode(wchar_t const *)
0x1800928cd  lea     rdx, [rbp+40h+var_90]
0x1800928d1  lea     rcx, [rbp+40h+var_C0]
0x1800928d5  movups  xmm1, xmmword ptr [rax]
0x1800928d8  movsd   xmm0, qword ptr [rax+10h]
0x1800928dd  movups  [rbp+40h+var_C0], xmm1
0x1800928e1  movsd   [rbp+40h+var_B0], xmm0
0x1800928e6  call    ??$IsStringPrefixEqualByOrdinalCaseInvariant@U_LUNICODE_STRING@@U1@@StringUtil@Windows@@YA_NAEBU_LUNICODE_STRING@@0PEAU2@@Z; Windows::StringUtil::IsStringPrefixEqualByOrdinalCaseInvariant<_LUNICODE_STRING,_LUNICODE_STRING>(_LUNICODE_STRING const &,_LUNICODE_STRING const &,_LUNICODE_STRING *)
0x1800928eb  test    al, al
0x1800928ed  jz      loc_1800929E3
0x1800928f3  mov     rcx, rsi
0x1800928f6  call    ?GetDeploymentType@CCbsUpdate@@QEBA?AW4DEPLOYMENT_TYPE@UPDATE_TYPE@@XZ; CCbsUpdate::GetDeploymentType(void)
0x1800928fb  cmp     eax, 5
0x1800928fe  jz      loc_1800929E3
0x180092904  mov     rbx, [rsi+18h]
0x180092908  lea     rcx, [rbp+40h+var_A8]
0x18009290c  mov     rdx, [rbx+70h]
0x180092910  add     rdx, 1Eh
0x180092914  call    ?AsLUnicode@StringUtil@Windows@@YA?AU_LUNICODE_STRING@@PEB_W@Z; Windows::StringUtil::AsLUnicode(wchar_t const *)
0x180092919  lea     rcx, [rbp+40h+var_C0]
0x18009291d  movups  xmm1, xmmword ptr [rax]
0x180092920  movsd   xmm0, qword ptr [rax+10h]
0x180092925  movups  [rbp+40h+var_C0], xmm1
0x180092929  movsd   [rbp+40h+var_B0], xmm0
0x18009292e  call    ??$AreStringAndLowerCaseAsciiStringEqualCaseInvariant@U_LUNICODE_STRING@@$$BY0BO@_W@StringUtil@Windows@@YA_NAEBU_LUNICODE_STRING@@AEAY0BO@$$CB_W@Z; Windows::StringUtil::AreStringAndLowerCaseAsciiStringEqualCaseInvariant<_LUNICODE_STRING,wchar_t [30]>(_LUNICODE_STRING const &,wchar_t const (&)[30])
0x180092933  test    al, al
0x180092935  jz      loc_1800929E1
0x18009293b  cmp     qword ptr [rsi+20h], 0
0x180092940  lea     rcx, [rbp+40h+var_A8]
0x180092944  mov     rdx, r14
0x180092947  cmovnz  rdx, [rsi+20h]
0x18009294c  call    ?AsLUnicode@StringUtil@Windows@@YA?AU_LUNICODE_STRING@@PEB_W@Z; Windows::StringUtil::AsLUnicode(wchar_t const *)
0x180092951  lea     rcx, [rbp+40h+var_C0]
0x180092955  movups  xmm1, xmmword ptr [rax]
0x180092958  movsd   xmm0, qword ptr [rax+10h]
0x18009295d  movups  [rbp+40h+var_C0], xmm1
0x180092961  movsd   [rbp+40h+var_B0], xmm0
0x180092966  call    ??$AreStringAndLowerCaseAsciiStringEqualCaseInvariant@U_LUNICODE_STRING@@$$BY06_W@StringUtil@Windows@@YA_NAEBU_LUNICODE_STRING@@AEAY06$$CB_W@Z; Windows::StringUtil::AreStringAndLowerCaseAsciiStringEqualCaseInvariant<_LUNICODE_STRING,wchar_t [7]>(_LUNICODE_STRING const &,wchar_t const (&)[7])
0x18009296b  test    al, al
0x18009296d  jz      short loc_1800929E1
0x18009296f  cmp     qword ptr [rbx+78h], 0
0x180092974  mov     rax, r14
0x180092977  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009297e  cmovnz  rax, [rbx+78h]
0x180092983  xor     ebx, ebx
0x180092985  cmp     [rsi+20h], rbx
0x180092989  mov     qword ptr [rsp+140h+var_F0], rax
0x18009298e  mov     rax, r14
0x180092991  cmovnz  rax, [rsi+20h]
0x180092996  mov     [rsp+140h+var_D8], rax
0x18009299b  mov     rax, [rdi+288h]
0x1800929a2  mov     qword ptr [rsp+140h+var_E0], rax
0x1800929a7  test    rcx, rcx
0x1800929aa  jz      short loc_1800929DC
0x1800929ac  lea     rax, [rsp+140h+var_F0]
0x1800929b1  mov     r8d, r15d
0x1800929b4  mov     [rsp+140h+var_110], rax
0x1800929b9  lea     r9, aUpdateInferrin; "Update: Inferring removal for disable r"...
0x1800929c0  lea     rax, [rsp+140h+var_D8]
0x1800929c5  mov     dl, r15b
0x1800929c8  mov     [rsp+140h+var_118], rax
0x1800929cd  lea     rax, [rsp+140h+var_E0]
0x1800929d2  mov     [rsp+140h+var_120], rax
0x1800929d7  call    ??$LogNumObjects@PEB_WVAutoScz@@PEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBVAutoScz@@AEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,AutoScz const &,wchar_t * const &)
0x1800929dc  or      r13d, r15d
0x1800929df  jmp     short loc_1800929E3
0x1800929e1  xor     ebx, ebx
0x1800929e3  test    r15b, r13b
0x1800929e6  jz      loc_180092BFF
0x1800929ec  lea     r8, [rsp+140h+var_E8]
0x1800929f1  mov     [rsp+140h+var_E8], bl
0x1800929f5  mov     rdx, rsi; CCbsUpdate *
0x1800929f8  mov     rcx, rdi; this
0x1800929fb  call    IsSelectablePayloadRemovable
0x180092a00  mov     r12d, eax
0x180092a03  test    eax, eax
0x180092a05  jns     loc_180092AB6
0x180092a0b  mov     r10, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180092a12  mov     [rbp+40h+var_60], eax
0x180092a15  test    r10, r10
0x180092a18  jz      short loc_180092A96
0x180092a1a  cmp     [rsi+20h], rbx
0x180092a1e  lea     r9, aUpdateFailedTo; "Update: Failed to check if the payload "...
0x180092a25  mov     rax, [rsi+18h]
0x180092a29  mov     rcx, r14
0x180092a2c  cmovnz  rcx, [rsi+20h]
0x180092a31  mov     qword ptr [rsp+140h+var_F0], rcx
0x180092a36  mov     rcx, r10
0x180092a39  cmp     [rax+78h], rbx
0x180092a3d  mov     ebx, 3
0x180092a42  mov     r8d, ebx
0x180092a45  cmovnz  r14, [rax+78h]
0x180092a4a  lea     rax, [rsp+140h+var_F0]
0x180092a4f  mov     [rsp+140h+var_118], rax
0x180092a54  xor     edx, edx
0x180092a56  lea     rax, [rsp+140h+var_D8]
0x180092a5b  mov     [rsp+140h+var_D8], r14
0x180092a60  mov     [rsp+140h+var_120], rax
0x180092a65  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x180092a6a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180092a71  lea     rax, [rbp+40h+var_60]
0x180092a75  mov     qword ptr [rsp+140h+var_E0], rax
0x180092a7a  lea     r9, asc_1802EE7AC; ": {}"
0x180092a81  lea     rax, [rsp+140h+var_E0]
0x180092a86  mov     r8d, ebx
0x180092a89  mov     dl, r15b
0x180092a8c  mov     [rsp+140h+var_120], rax; int
0x180092a91  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180092a96  mov     edx, 140h; void *
0x180092a9b  mov     rcx, [rbp+48h]; this
0x180092a9f  lea     r8, aOnecoreBaseCbs_96; "onecore\\base\\cbs\\core\\cbsupdate.cpp"
  ... truncated ...
```
