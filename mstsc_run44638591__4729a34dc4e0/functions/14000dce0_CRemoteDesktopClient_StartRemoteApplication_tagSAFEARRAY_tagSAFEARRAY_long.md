# CRemoteDesktopClient::StartRemoteApplication(tagSAFEARRAY *,tagSAFEARRAY *,long)

- ea: `0x14000dce0`
- end: `0x14000ebd0`
- name: `?StartRemoteApplication@CRemoteDesktopClient@@UEAAJPEAUtagSAFEARRAY@@0J@Z`
- size: `3824`
- prototype: `__int64 __fastcall(CRemoteDesktopClient *this, struct tagSAFEARRAY *, struct tagSAFEARRAY *, int)`
- caller_count: `0`
- callee_count: `33`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x140003b2c`
- `0x140008a34`
- `0x14000a670`
- `0x14000b7d8`
- `0x14000c7d0`
- `0x14000c7f8`
- `0x14000cfb0`
- `0x14000cffc`
- `0x14000d078`
- `0x14000d3a0`
- `0x14000d4cc`
- `0x14000d87c`
- `0x14000d8bc`
- `0x14000d92c`
- `0x14000d990`
- `0x14000dcac`
- `0x14000dce0`
- `0x140010ac8`
- `0x14002d8a4`
- `0x140036f80`
- `0x140037094`
- `0x1400379dc`
- `0x14004040c`
- `0x140040954`
- `0x1400427d8`
- `0x140056208`
- `0x140056eec`
- `0x1400595f0`
- `0x140059760`
- `0x1400642b4`
- `0x1400b5268`
- `0x1400b5420`
- `0x140114010`

## import_xrefs

- `USER32!PostMessageW` at `0x14000e8cb`
- `USER32!PostMessageW` at `0x14000e8cb`
- `KERNEL32!DeleteFileW` at `0x14000e833`
- `KERNEL32!DeleteFileW` at `0x14000e833`
- `KERNEL32!GetLastError` at `0x14000e8e5`
- `KERNEL32!GetLastError` at `0x14000e8e5`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x14000ea0e`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x14000ea20`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x14000ea0e`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x14000ea20`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x14000dda7`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x14000df3b`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x14000dda7`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x14000df3b`
- `OLEAUT32!__imp_SysStringByteLen` at `0x14000e130`
- `OLEAUT32!__imp_SysStringByteLen` at `0x14000e9b4`
- `OLEAUT32!__imp_SysStringByteLen` at `0x14000e130`
- `OLEAUT32!__imp_SysStringByteLen` at `0x14000e9b4`
- `ADVAPI32!CredFree` at `0x14000e62d`
- `ADVAPI32!CredFree` at `0x14000e62d`
- `ADVAPI32!CredUnmarshalCredentialW` at `0x14000e60e`
- `ADVAPI32!CredUnmarshalCredentialW` at `0x14000e60e`

## string_xrefs

- `0x14000eafe`: `CommandLineData`

## pseudocode

```c
__int64 __fastcall CRemoteDesktopClient::StartRemoteApplication(
        CRemoteDesktopClient *this,
        struct tagSAFEARRAY *a2,
        struct tagSAFEARRAY *a3,
        int a4)
{
  SAFEARRAY *v5; // rbx
  SAFEARRAY *v6; // rdi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int Vartype; // esi
  unsigned int v9; // eax
  int v10; // edx
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  __int64 v15; // rdx
  unsigned int v16; // eax
  unsigned int v17; // eax
  int v18; // r14d
  int v19; // r14d
  CommandLineData *v20; // rax
  CommandLineData *v21; // rax
  bool v22; // r8
  WCHAR *v23; // r14
  unsigned int v24; // eax
  CTscSettings *v25; // rax
  CTscSettings *v26; // r13
  unsigned int v27; // eax
  int v28; // edx
  const char *v29; // rcx
  CClxShell *v30; // rax
  CClxShell *v31; // rax
  int v32; // esi
  int v33; // esi
  unsigned int v34; // eax
  int v35; // edx
  const char *v36; // rcx
  int v37; // esi
  int v38; // esi
  _QWORD *pvData; // rax
  const WCHAR *v40; // rcx
  BOOL v41; // esi
  int v42; // esi
  int v43; // eax
  int v44; // esi
  int v45; // esi
  CTscRemoteSessionsManager *v46; // rsi
  __int64 v47; // rcx
  unsigned int v48; // eax
  signed int LastError; // eax
  unsigned int v50; // eax
  int LowerBound; // r14d
  __int64 v52; // r14
  int v53; // r15d
  _BYTE *i; // rax
  unsigned int v56; // eax
  SAFEARRAY *v57; // [rsp+30h] [rbp-50h] BYREF
  VARTYPE pvt; // [rsp+38h] [rbp-48h] BYREF
  SAFEARRAY *v59; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v60; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int16 *v61; // [rsp+50h] [rbp-30h]
  CTscSettings *v62; // [rsp+58h] [rbp-28h] BYREF
  PVOID Credential; // [rsp+60h] [rbp-20h] BYREF
  CTscRemoteSessionsManager *v64; // [rsp+68h] [rbp-18h] BYREF
  __int64 v65; // [rsp+70h] [rbp-10h] BYREF
  struct tagSAFEARRAY *CredType; // [rsp+D0h] [rbp+50h] BYREF
  int v67; // [rsp+D8h] [rbp+58h]

  v67 = a4;
  CredType = a3;
  v57 = 0;
  v5 = 0;
  v59 = 0;
  v6 = 0;
  v64 = 0;
  v62 = 0;
  v65 = 0;
  pvt = 0;
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_42ec143e2e4a3ec358f03f269ab89f1d_Traceguids,
        CurrentThreadActivityIdPrefix,
        -2147024809);
    }
    Vartype = -2147024809;
    goto LABEL_181;
  }
  if ( !a2 )
    goto LABEL_33;
  Vartype = SafeArrayGetVartype(a2, &pvt);
  if ( Vartype < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_169;
    }
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 11;
    goto LABEL_38;
  }
  if ( pvt == 8 )
  {
    Vartype = ATL::CComSafeArray<unsigned short *,8>::Attach(&v57, a2);
    if ( Vartype < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)WPP_42ec143e2e4a3ec358f03f269ab89f1d_Traceguids,
          v12,
          (__int64)"Creds.Attach failed!",
          Vartype);
      }
LABEL_31:
      v5 = v57;
LABEL_169:
      if ( v5 )
      {
        if ( (v67 & 1) == 0 && (unsigned int)ATL::CComSafeArray<unsigned short *,8>::GetCount(&v57) == 2 )
        {
          LowerBound = ATL::CComSafeArray<unsigned short *,8>::GetLowerBound(&v57);
          if ( LowerBound > 1 || (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v57) < 1 )
            ATL::AtlThrowImpl(-2147024809);
          v52 = SysStringByteLen(*((BSTR *)v5->pvData + 1 - LowerBound));
          v53 = ATL::CComSafeArray<unsigned short *,8>::GetLowerBound(&v57);
          if ( v53 > 1 || (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v57) < 1 )
            ATL::AtlThrowImpl(-2147024809);
          for ( i = (_BYTE *)*((_QWORD *)v5->pvData + 1 - v53); v52; --v52 )
            *i++ = 0;
        }
        SafeArrayUnlock(v5);
        v57 = 0;
      }
      if ( v6 )
      {
        SafeArrayUnlock(v6);
        v59 = 0;
      }
      goto LABEL_181;
    }
    if ( (unsigned int)ATL::CComSafeArray<unsigned short *,8>::GetCount(&v57) != 1
      && (unsigned int)ATL::CComSafeArray<unsigned short *,8>::GetCount(&v57) != 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_42ec143e2e4a3ec358f03f269ab89f1d_Traceguids,
          v13,
          -2147024809);
      }
      Vartype = -2147024809;
      goto LABEL_31;
    }
    v5 = v57;
    a3 = CredType;
LABEL_33:
    Vartype = SafeArrayGetVartype(a3, &pvt);
    if ( Vartype < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_169;
      }
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 15;
LABEL_38:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        (unsigned int)WPP_42ec143e2e4a3ec358f03f269ab89f1d_Traceguids,
        v9,
        (__int64)"SafeArrayGetVartype failed!",
        Vartype);
      goto LABEL_169;
    }
    if ( pvt != 8 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_45;
      }
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      v15 = 16;
LABEL_44:
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        WPP_42ec143e2e4a3ec358f03f269ab89f1d_Traceguids,
        v14,
        -2147024809);
LABEL_45:
      Vartype = -2147024809;
      goto LABEL_169;
    }
    Vartype = ATL::CComSafeArray<unsigned short *,8>::Attach(&v59, CredType);
    if ( Vartype < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)WPP_42ec143e2e4a3ec358f03f269ab89f1d_Traceguids,
          v16,
          (__int64)"Params.Attach failed!",
          Vartype);
      }
LABEL_57:
      v6 = v59;
      goto LABEL_169;
    }
    if ( !(unsigned int)ATL::CComSafeArray<unsigned short *,8>::GetCount(&v59) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          WPP_42ec143e2e4a3ec358f03f269ab89f1d_Traceguids,
          v17,
          -2147024809);
      }
      Vartype = -2147024809;
      goto LABEL_57;
    }
    v6 = v59;
    Vartype = -2147467259;
    if ( !v59 )
      ATL::AtlThrowImpl(-2147467259);
    v18 = ATL::CComSafeArray<unsigned short *,8>::GetLowerBound(&v59);
    if ( v18 > 0 || (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v59) < 0 )
      ATL::AtlThrowImpl(-2147024809);
    Credential = (PVOID)*((_QWORD *)v6->pvData - v18);
    if ( SysStringByteLen((BSTR)Credential) > 0x10000 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_45;
      }
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      v15 = 19;
      goto LABEL_44;
    }
    CredType = 0;
    v61 = 0;
    if ( (unsigned int)ATL::CComSafeArray<unsigned short *,8>::GetCount(&v59) > 2 )
    {
      if ( !v6 )
        ATL::AtlThrowImpl(-2147467259);
      v19 = ATL::CComSafeArray<unsigned short *,8>::GetLowerBound(&v59);
      if ( v19 > 2 || (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v59) < 2 )
        ATL::AtlThrowImpl(-2147024809);
      v61 = (unsigned __int16 *)*((_QWORD *)v6->pvData + 2 - v19);
    }
    if ( (unsigned int)ATL::CComSafeArray<unsigned short *,8>::GetCount(&v59) > 3 )
    {
      if ( !v6 )
        ATL::AtlThrowImpl(-2147467259);
      LODWORD(CredType) = ATL::CComSafeArray<unsigned short *,8>::GetLowerBound(&v59);
      if ( (int)CredType > 3 || (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v59) < 3 )
        ATL::AtlThrowImpl(-2147024809);
      CredType = (struct tagSAFEARRAY *)*((_QWORD *)v6->pvData + 3 - (int)CredType);
    }
    v20 = (CommandLineData *)operator new(0x19F0u);
    if ( !v20 || (v21 = CommandLineData::CommandLineData(v20), (v23 = (WCHAR *)v21) == 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v56 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          (unsigned int)WPP_42ec143e2e4a3ec358f03f269ab89f1d_Traceguids,
          v56,
          (__int64)"CommandLineData");
      }
      Vartype = -2147024882;
      goto LABEL_169;
    }
    if ( CommandLineData::ProcessCommand(v21, (const unsigned __int16 *)Credential, v22, v61) != 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v24 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          WPP_42ec143e2e4a3ec358f03f269ab89f1d_Traceguids,
          v24,
          -2147467259);
      }
      goto LABEL_188;
    }
    v25 = (CTscSettings *)operator new(0x35090u);
    if ( v25 && (v26 = CTscSettings::CTscSettings(v25)) != 0 )
    {
      TCntPtr<CTSCoreEventSink>::SafeRelease(&v62);
      v62 = v26;
      TCntPtr<CTscSettings>::SafeAddRef(&v62);
      if ( CredType )
      {
        Vartype = CTscSettings::InitSettingsFromSerializedSettingsStore(v26, &CredType->cDims);
        if ( Vartype < 0 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_188;
          }
          v27 = RdpWppGetCurrentThreadActivityIdPrefix();
          v28 = 23;
          v29 = "spTscSet->InitSettingsFromSerializedSettingsStore failed!";
          goto LABEL_152;
        }
      }
      else
      {
        Vartype = CTscSettings::Initialize(v26, (const struct CommandLineData *)v23);
        if ( Vartype < 0 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_188;
          }
          v27 = RdpWppGetCurrentThreadActivityIdPrefix();
          v28 = 24;
          v29 = "spTscSet->Initialize failed";
          goto LABEL_152;
        }
        Vartype = CTscSettings::LoadAllSettings(v26, (const struct CommandLineData *)v23);
        if ( Vartype < 0 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_188;
          }
          v27 = RdpWppGetCurrentThreadActivityIdPrefix();
          v28 = 25;
          v29 = "spTscSet->LoadAllSettings failed";
          goto LABEL_152;
        }
      }
      if ( g_pClx )
        goto LABEL_105;
      v30 = (CClxShell *)operator new(0x298u);
      if ( v30 )
      {
        v31 = CClxShell::CClxShell(v30);
        g_pClx = v31;
        if ( v31 )
        {
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v31 + 4) + 8LL))(*((_QWORD *)v31 + 4));
          CClxShell::Initialize(g_pClx, (CTscSettings *)((char *)v26 + 217208));
LABEL_105:
          if ( !v5 )
            goto LABEL_146;
          if ( (unsigned int)ATL::CComSafeArray<unsigned short *,8>::GetCount(&v57) <= 1 )
          {
            if ( (unsigned int)ATL::CComSafeArray<unsigned short *,8>::GetCount(&v57) == 1 )
            {
              v45 = ATL::CComSafeArray<unsigned short *,8>::GetLowerBound(&v57);
              if ( v45 > 0 || (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v57) < 0 )
                ATL::AtlThrowImpl(-2147024809);
              CTscSettings::SetSingleSignOnUserName(v26, *((const unsigned __int16 **)v5->pvData - v45));
            }
            goto LABEL_146;
          }
          v32 = ATL::CComSafeArray<unsigned short *,8>::GetLowerBound(&v57);
          if ( v32 > 0 || (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v57) < 0 )
            ATL::AtlThrowImpl(-2147024809);
          CTscSettings::SetSingleSignOnUserName(v26, *((const unsigned __int16 **)v5->pvData - v32));
          CTscSettings::SetDomain(v26, &pszPassword);
          LODWORD(v61) = v67 & 1;
          if ( (v67 & 1) != 0 )
          {
            v33 = ATL::CComSafeArray<unsigned short *,8>::GetLowerBound(&v57);
            if ( v33 > 1 || (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v57) < 1 )
              ATL::AtlThrowImpl(-2147024809);
            CTscPassword::SetEncryptedPassword(
              (CTscSettings *)((char *)v26 + 37424),
              *((const unsigned __int16 **)v5->pvData + 1 - v33));
          }
          else
          {
            v37 = ATL::CComSafeArray<unsigned short *,8>::GetLowerBound(&v57);
            if ( v37 > 1 || (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v57) < 1 )
              ATL::AtlThrowImpl(-2147024809);
            CTscPassword::SetPassword(
              (CTscSettings *)((char *)v26 + 37424),
              *((unsigned __int16 **)v5->pvData + 1 - v37));
          }
          if ( *((_DWORD *)v26 + 16625) != 1 )
          {
LABEL_146:
            v46 = qword_140153AD0;
            if ( !qword_140153AD0 )
            {
              v60 = 0;
              LODWORD(CredType) = 0;
              if ( v23[2098] )
                DeleteFileW(v23 + 2098);
              Vartype = CTscSettings::ValidateSettings(v26, &v60, (unsigned int *)&CredType);
              if ( Vartype >= 0 )
              {
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v26 + 4) + 8LL))(*((_QWORD *)v26 + 4));
                if ( PostMessageW(0, 0x428u, 0, (LPARAM)v26) )
                  goto LABEL_169;
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v26 + 4) + 16LL))(*((_QWORD *)v26 + 4));
                LastError = GetLastError();
                Vartype = LastError;
                if ( LastError > 0 )
                  Vartype = (unsigned __int16)LastError | 0x80070000;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v50 = RdpWppGetCurrentThreadActivityIdPrefix();
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    29,
                    WPP_42ec143e2e4a3ec358f03f269ab89f1d_Traceguids,
                    v50,
                    Vartype);
                }
                if ( Vartype >= 0 )
                  goto LABEL_169;
              }
              else
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v48 = RdpWppGetCurrentThreadActivityIdPrefix();
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    28,
                    WPP_42ec143e2e4a3ec358f03f269ab89f1d_Traceguids,
                    v48,
                    Vartype);
                }
                ShowErrorMessage(hModule, v60, (unsigned int)CredType);
              }
              goto LABEL_188;
            }
            TCntPtr<CTSCoreEventSink>::SafeRelease(&v64);
            v47 = *((_QWORD *)v46 + 4);
            v64 = v46;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 8LL))(v47);
            Vartype = CTscRemoteSessionsManager::OnStartRemoteApplicationRequest(
                        v46,
                        (struct CommandLineData *)v23,
                        v26);
            if ( Vartype >= 0 )
              goto LABEL_169;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
LABEL_188:
              CommandLineData::`scalar deleting destructor'((CommandLineData *)v23, 1u);
              goto LABEL_169;
            }
            v27 = RdpWppGetCurrentThreadActivityIdPrefix();
            v28 = 27;
            v29 = "spRemoteSessionsMgr->OnStartRemoteApplicationRequest failed";
LABEL_152:
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v28,
              (unsigned int)WPP_42ec143e2e4a3ec358f03f269ab89f1d_Traceguids,
              v27,
              (__int64)v29,
              Vartype);
            goto LABEL_188;
          }
          v38 = ATL::CComSafeArray<unsigned short *,8>::GetLowerBound(&v57);
          if ( v38 > 0 || (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v57) < 0 )
            ATL::AtlThrowImpl(-2147024809);
          pvData = v5->pvData;
          LODWORD(CredType) = 0;
          Credential = 0;
          v40 = (const WCHAR *)pvData[-v38];
          v60 = *((_DWORD *)v26 + 16623);
          v41 = CredUnmarshalCredentialW(v40, (PCRED_MARSHAL_TYPE)&CredType, &Credential);
          if ( v41 )
            v41 = (_DWORD)CredType == 1;
          if ( Credential )
            CredFree(Credential);
          if ( v60 )
          {
            if ( v60 != 1 || !v41 )
              goto LABEL_131;
          }
          else if ( v41 )
          {
LABEL_131:
            *((_DWORD *)v26 + 16625) = 0;
            goto LABEL_146;
          }
          v42 = ATL::CComSafeArray<unsigned short *,8>::GetLowerBound(&v57);
          if ( v42 > 0 || (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v57) < 0 )
            ATL::AtlThrowImpl(-2147024809);
          StringCchCopyW((unsigned __int16 *)v26 + 34296, 0x200u, *((const unsigned __int16 **)v5->pvData - v42));
          v43 = ATL::CComSafeArray<unsigned short *,8>::GetLowerBound(&v57);
          v44 = v43;
          if ( (_DWORD)v61 )
          {
            if ( v43 > 1 || (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v57) < 1 )
              ATL::AtlThrowImpl(-2147024809);
            CTscPassword::SetEncryptedPassword(
              (CTscSettings *)((char *)v26 + 69616),
              *((const unsigned __int16 **)v5->pvData + 1 - v44));
          }
          else
          {
            if ( v43 > 1 || (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v57) < 1 )
              ATL::AtlThrowImpl(-2147024809);
            CTscPassword::SetPassword(
              (CTscSettings *)((char *)v26 + 69616),
              *((unsigned __int16 **)v5->pvData + 1 - v44));
          }
          goto LABEL_146;
        }
      }
      else
      {
        g_pClx = 0;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_187:
        Vartype = -2147024882;
        goto LABEL_188;
      }
      v34 = RdpWppGetCurrentThreadActivityIdPrefix();
      v35 = 26;
      v36 = "CClxShell";
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_187;
      }
      v34 = RdpWppGetCurrentThreadActivityIdPrefix();
      v35 = 22;
      v36 = "CTscSettings";
    }
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v35,
      (unsigned int)WPP_42ec143e2e4a3ec358f03f269ab89f1d_Traceguids,
      v34,
      (__int64)v36);
    goto LABEL_187;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_42ec143e2e4a3ec358f03f269ab89f1d_Traceguids,
      v11,
      -2147024809);
  }
  Vartype = -2147024809;
LABEL_181:
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v65);
  TCntPtr<CTSCoreEventSink>::SafeRelease(&v62);
  TCntPtr<CTSCoreEventSink>::SafeRelease(&v64);
  ATL::CComSafeArray<unsigned short *,8>::Destroy(&v59);
  ATL::CComSafeArray<unsigned short *,8>::Destroy(&v57);
  return (unsigned int)Vartype;
}

```

## disassembly

```asm
0x14000dce0  mov     [rsp-38h+arg_0], rbx
0x14000dce5  mov     [rsp-38h+arg_18], r9d
0x14000dcea  mov     [rsp-38h+CredType], r8
0x14000dcef  push    rbp
0x14000dcf0  push    rsi
0x14000dcf1  push    rdi
0x14000dcf2  push    r12
0x14000dcf4  push    r13
0x14000dcf6  push    r14
0x14000dcf8  push    r15
0x14000dcfa  mov     rbp, rsp
0x14000dcfd  sub     rsp, 80h
0x14000dd04  xor     ecx, ecx
0x14000dd06  mov     r14, rdx
0x14000dd09  mov     [rbp+var_50], rcx
0x14000dd0d  mov     ebx, ecx
0x14000dd0f  mov     [rbp+var_40], rcx
0x14000dd13  mov     edi, ecx
0x14000dd15  mov     [rbp+var_18], rcx
0x14000dd19  mov     [rbp+var_28], rcx
0x14000dd1d  mov     [rbp+var_10], rcx
0x14000dd21  mov     [rbp+pvt], cx
0x14000dd25  test    r8, r8
0x14000dd28  jnz     short loc_14000DD86
0x14000dd2a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dd31  lea     rax, WPP_GLOBAL_Control
0x14000dd38  cmp     rcx, rax
0x14000dd3b  jz      short loc_14000DD7C
0x14000dd3d  mov     r12w, 8
0x14000dd42  test    [rcx+1Ch], r12b
0x14000dd46  jz      short loc_14000DD7C
0x14000dd48  lea     r15d, [rdi+2]
0x14000dd4c  cmp     [rcx+19h], r15b
0x14000dd50  jb      short loc_14000DD7C
0x14000dd52  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000dd57  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dd5e  lea     edx, [rdi+0Ah]
0x14000dd61  mov     r9d, eax
0x14000dd64  mov     dword ptr [rsp+80h+var_60], 80070057h
0x14000dd6c  lea     r8, WPP_42ec143e2e4a3ec358f03f269ab89f1d_Traceguids
0x14000dd73  mov     rcx, [rcx+10h]
0x14000dd77  call    WPP_SF_Dd
0x14000dd7c  mov     esi, 80070057h
0x14000dd81  jmp     loc_14000EA2A
0x14000dd86  mov     r13d, 80070057h
0x14000dd8c  mov     r15d, 2
0x14000dd92  mov     r12w, 8
0x14000dd97  test    r14, r14
0x14000dd9a  jz      loc_14000DF34
0x14000dda0  lea     rdx, [rbp+pvt]; pvt
0x14000dda4  mov     rcx, r14; psa
0x14000dda7  call    cs:__imp_SafeArrayGetVartype
0x14000ddad  mov     esi, eax
0x14000ddaf  test    eax, eax
0x14000ddb1  jns     short loc_14000DDEC
0x14000ddb3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ddba  lea     rax, WPP_GLOBAL_Control
0x14000ddc1  cmp     rcx, rax
0x14000ddc4  jz      loc_14000E94F
0x14000ddca  test    [rcx+1Ch], r12b
0x14000ddce  jz      loc_14000E94F
0x14000ddd4  cmp     [rcx+19h], r15b
0x14000ddd8  jb      loc_14000E94F
0x14000ddde  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000dde3  lea     edx, [r15+9]
0x14000dde7  jmp     loc_14000DF7C
0x14000ddec  cmp     [rbp+pvt], r12w
0x14000ddf1  jz      short loc_14000DE46
0x14000ddf3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ddfa  lea     rax, WPP_GLOBAL_Control
0x14000de01  cmp     rcx, rax
0x14000de04  jz      short loc_14000DE3E
0x14000de06  test    [rcx+1Ch], r12b
0x14000de0a  jz      short loc_14000DE3E
0x14000de0c  cmp     [rcx+19h], r15b
0x14000de10  jb      short loc_14000DE3E
0x14000de12  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000de17  mov     rcx, cs:WPP_GLOBAL_Control
0x14000de1e  lea     r8, WPP_42ec143e2e4a3ec358f03f269ab89f1d_Traceguids
0x14000de25  mov     edx, 0Ch
0x14000de2a  mov     dword ptr [rsp+80h+var_60], 80070057h
0x14000de32  mov     r9d, eax
0x14000de35  mov     rcx, [rcx+10h]
0x14000de39  call    WPP_SF_Dd
0x14000de3e  mov     esi, r13d
0x14000de41  jmp     loc_14000EA2A
0x14000de46  mov     rdx, r14
0x14000de49  lea     rcx, [rbp+var_50]
0x14000de4d  call    ?Attach@?$CComSafeArray@PEAG$07@ATL@@QEAAJPEBUtagSAFEARRAY@@@Z; ATL::CComSafeArray<ushort *,8>::Attach(tagSAFEARRAY const *)
0x14000de52  mov     esi, eax
0x14000de54  test    eax, eax
0x14000de56  jns     short loc_14000DEB9
0x14000de58  mov     rcx, cs:WPP_GLOBAL_Control
0x14000de5f  lea     rax, WPP_GLOBAL_Control
0x14000de66  cmp     rcx, rax
0x14000de69  jz      loc_14000DF23
0x14000de6f  test    [rcx+1Ch], r12b
0x14000de73  jz      loc_14000DF23
0x14000de79  cmp     [rcx+19h], r15b
0x14000de7d  jb      loc_14000DF23
0x14000de83  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000de88  lea     rcx, aCredsAttachFai; "Creds.Attach failed!"
0x14000de8f  mov     [rsp+80h+var_58], esi
0x14000de93  mov     [rsp+80h+var_60], rcx
0x14000de98  lea     r8, WPP_42ec143e2e4a3ec358f03f269ab89f1d_Traceguids
0x14000de9f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dea6  mov     edx, 0Dh
0x14000deab  mov     r9d, eax
0x14000deae  mov     rcx, [rcx+10h]
0x14000deb2  call    WPP_SF_DsD
0x14000deb7  jmp     short loc_14000DF23
0x14000deb9  lea     rcx, [rbp+var_50]
0x14000debd  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x14000dec2  cmp     eax, 1
0x14000dec5  jz      short loc_14000DF2C
0x14000dec7  lea     rcx, [rbp+var_50]
0x14000decb  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x14000ded0  cmp     eax, r15d
0x14000ded3  jz      short loc_14000DF2C
0x14000ded5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dedc  lea     rax, WPP_GLOBAL_Control
0x14000dee3  cmp     rcx, rax
0x14000dee6  jz      short loc_14000DF20
0x14000dee8  test    [rcx+1Ch], r12b
0x14000deec  jz      short loc_14000DF20
0x14000deee  cmp     [rcx+19h], r15b
0x14000def2  jb      short loc_14000DF20
0x14000def4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000def9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000df00  lea     r8, WPP_42ec143e2e4a3ec358f03f269ab89f1d_Traceguids
0x14000df07  mov     edx, 0Eh
0x14000df0c  mov     dword ptr [rsp+80h+var_60], 80070057h
0x14000df14  mov     r9d, eax
0x14000df17  mov     rcx, [rcx+10h]
0x14000df1b  call    WPP_SF_Dd
0x14000df20  mov     esi, r13d
0x14000df23  mov     rbx, [rbp+var_50]
0x14000df27  jmp     loc_14000E94F
0x14000df2c  mov     rbx, [rbp+var_50]
0x14000df30  mov     r8, [rbp+CredType]
0x14000df34  lea     rdx, [rbp+pvt]; pvt
0x14000df38  mov     rcx, r8; psa
0x14000df3b  call    cs:__imp_SafeArrayGetVartype
0x14000df41  mov     esi, eax
0x14000df43  test    eax, eax
0x14000df45  jns     short loc_14000DFAB
0x14000df47  mov     rcx, cs:WPP_GLOBAL_Control
0x14000df4e  lea     rax, WPP_GLOBAL_Control
0x14000df55  cmp     rcx, rax
0x14000df58  jz      loc_14000E94F
0x14000df5e  test    [rcx+1Ch], r12b
0x14000df62  jz      loc_14000E94F
0x14000df68  cmp     [rcx+19h], r15b
0x14000df6c  jb      loc_14000E94F
0x14000df72  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000df77  mov     edx, 0Fh
0x14000df7c  lea     rcx, aSafearraygetva; "SafeArrayGetVartype failed!"
0x14000df83  mov     [rsp+80h+var_58], esi
0x14000df87  mov     [rsp+80h+var_60], rcx
0x14000df8c  lea     r8, WPP_42ec143e2e4a3ec358f03f269ab89f1d_Traceguids
0x14000df93  mov     rcx, cs:WPP_GLOBAL_Control
0x14000df9a  mov     r9d, eax
0x14000df9d  mov     rcx, [rcx+10h]
0x14000dfa1  call    WPP_SF_DsD
0x14000dfa6  jmp     loc_14000E94F
0x14000dfab  cmp     [rbp+pvt], r12w
0x14000dfb0  jz      short loc_14000E005
0x14000dfb2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dfb9  lea     rax, WPP_GLOBAL_Control
0x14000dfc0  cmp     rcx, rax
0x14000dfc3  jz      short loc_14000DFFD
0x14000dfc5  test    [rcx+1Ch], r12b
0x14000dfc9  jz      short loc_14000DFFD
0x14000dfcb  cmp     [rcx+19h], r15b
0x14000dfcf  jb      short loc_14000DFFD
0x14000dfd1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000dfd6  mov     edx, 10h
0x14000dfdb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dfe2  lea     r8, WPP_42ec143e2e4a3ec358f03f269ab89f1d_Traceguids
0x14000dfe9  mov     r9d, eax
0x14000dfec  mov     dword ptr [rsp+80h+var_60], 80070057h
0x14000dff4  mov     rcx, [rcx+10h]
0x14000dff8  call    WPP_SF_Dd
0x14000dffd  mov     esi, r13d
0x14000e000  jmp     loc_14000E94F
0x14000e005  mov     rdx, [rbp+CredType]
0x14000e009  lea     rcx, [rbp+var_40]
0x14000e00d  call    ?Attach@?$CComSafeArray@PEAG$07@ATL@@QEAAJPEBUtagSAFEARRAY@@@Z; ATL::CComSafeArray<ushort *,8>::Attach(tagSAFEARRAY const *)
0x14000e012  mov     esi, eax
0x14000e014  test    eax, eax
0x14000e016  jns     short loc_14000E079
0x14000e018  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e01f  lea     rax, WPP_GLOBAL_Control
0x14000e026  cmp     rcx, rax
0x14000e029  jz      loc_14000E0D5
0x14000e02f  test    [rcx+1Ch], r12b
0x14000e033  jz      loc_14000E0D5
0x14000e039  cmp     [rcx+19h], r15b
0x14000e03d  jb      loc_14000E0D5
0x14000e043  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000e048  lea     rcx, aParamsAttachFa; "Params.Attach failed!"
0x14000e04f  mov     [rsp+80h+var_58], esi
0x14000e053  mov     [rsp+80h+var_60], rcx
0x14000e058  lea     r8, WPP_42ec143e2e4a3ec358f03f269ab89f1d_Traceguids
0x14000e05f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e066  mov     edx, 11h
0x14000e06b  mov     r9d, eax
0x14000e06e  mov     rcx, [rcx+10h]
0x14000e072  call    WPP_SF_DsD
0x14000e077  jmp     short loc_14000E0D5
0x14000e079  lea     rcx, [rbp+var_40]
0x14000e07d  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x14000e082  cmp     eax, 1
0x14000e085  jnb     short loc_14000E0DE
0x14000e087  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e08e  lea     rax, WPP_GLOBAL_Control
0x14000e095  cmp     rcx, rax
0x14000e098  jz      short loc_14000E0D2
0x14000e09a  test    [rcx+1Ch], r12b
0x14000e09e  jz      short loc_14000E0D2
0x14000e0a0  cmp     [rcx+19h], r15b
0x14000e0a4  jb      short loc_14000E0D2
0x14000e0a6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000e0ab  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e0b2  lea     r8, WPP_42ec143e2e4a3ec358f03f269ab89f1d_Traceguids
0x14000e0b9  mov     edx, 12h
0x14000e0be  mov     dword ptr [rsp+80h+var_60], 80070057h
0x14000e0c6  mov     r9d, eax
0x14000e0c9  mov     rcx, [rcx+10h]
0x14000e0cd  call    WPP_SF_Dd
0x14000e0d2  mov     esi, r13d
0x14000e0d5  mov     rdi, [rbp+var_40]
0x14000e0d9  jmp     loc_14000E94F
0x14000e0de  mov     rdi, [rbp+var_40]
0x14000e0e2  mov     esi, 80004005h
0x14000e0e7  test    rdi, rdi
0x14000e0ea  jz      loc_14000EB45
0x14000e0f0  lea     rcx, [rbp+var_40]
0x14000e0f4  call    ?GetLowerBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetLowerBound(uint)
0x14000e0f9  mov     r14d, eax
0x14000e0fc  test    eax, eax
0x14000e0fe  jg      loc_14000EB4D
0x14000e104  lea     rcx, [rbp+var_40]
0x14000e108  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x14000e10d  test    eax, eax
0x14000e10f  js      loc_14000EB4D
0x14000e115  mov     rax, [rdi+10h]
0x14000e119  neg     r14d
0x14000e11c  movsxd  rcx, r14d
0x14000e11f  xor     r14d, r14d
0x14000e122  lea     rax, [rax+rcx*8]
0x14000e126  mov     rax, [rax]
0x14000e129  mov     rcx, rax; bstr
0x14000e12c  mov     [rbp+Credential], rax
0x14000e130  call    cs:__imp_SysStringByteLen
0x14000e136  cmp     eax, 10000h
0x14000e13b  jbe     short loc_14000E176
0x14000e13d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e144  lea     rax, WPP_GLOBAL_Control
0x14000e14b  cmp     rcx, rax
0x14000e14e  jz      loc_14000DFFD
0x14000e154  test    [rcx+1Ch], r12b
0x14000e158  jz      loc_14000DFFD
0x14000e15e  cmp     [rcx+19h], r15b
0x14000e162  jb      loc_14000DFFD
0x14000e168  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000e16d  lea     edx, [r14+13h]
0x14000e171  jmp     loc_14000DFDB
0x14000e176  lea     rcx, [rbp+var_40]
0x14000e17a  mov     [rbp+CredType], r14
0x14000e17e  mov     [rbp+var_30], r14
0x14000e182  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x14000e187  cmp     eax, r15d
0x14000e18a  jbe     short loc_14000E1D4
0x14000e18c  test    rdi, rdi
0x14000e18f  jz      loc_14000EB56
0x14000e195  lea     rcx, [rbp+var_40]
0x14000e199  call    ?GetLowerBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetLowerBound(uint)
0x14000e19e  mov     r14d, eax
0x14000e1a1  cmp     eax, r15d
0x14000e1a4  jg      loc_14000EB66
0x14000e1aa  lea     rcx, [rbp+var_40]
0x14000e1ae  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x14000e1b3  cmp     eax, r15d
0x14000e1b6  jl      loc_14000EB66
0x14000e1bc  mov     rax, [rdi+10h]
0x14000e1c0  mov     ecx, r15d
0x14000e1c3  sub     ecx, r14d
0x14000e1c6  movsxd  rdx, ecx
0x14000e1c9  lea     rax, [rax+rdx*8]
0x14000e1cd  mov     rax, [rax]
0x14000e1d0  mov     [rbp+var_30], rax
0x14000e1d4  lea     rcx, [rbp+var_40]
0x14000e1d8  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x14000e1dd  mov     r14d, 3
0x14000e1e3  cmp     eax, r14d
0x14000e1e6  jbe     short loc_14000E22E
0x14000e1e8  test    rdi, rdi
0x14000e1eb  jz      loc_14000EB5E
0x14000e1f1  lea     rcx, [rbp+var_40]
  ... truncated ...
```
