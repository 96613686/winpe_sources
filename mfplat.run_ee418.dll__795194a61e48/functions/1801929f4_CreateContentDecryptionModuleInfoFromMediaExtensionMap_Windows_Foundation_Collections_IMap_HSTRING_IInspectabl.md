# CreateContentDecryptionModuleInfoFromMediaExtensionMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,MediaContentDecryptionModuleInfo &)

- ea: `0x1801929f4`
- end: `0x180193433`
- name: `?CreateContentDecryptionModuleInfoFromMediaExtensionMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@AEAUMediaContentDecryptionModuleInfo@@@Z`
- size: `2623`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18011c7b8`

## callees

- `0x180004870`
- `0x180020458`
- `0x180020b80`
- `0x180020e54`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18003eef4`
- `0x180094910`
- `0x1801200d0`
- `0x1801929f4`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180192a53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180192b0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180192e89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180192f3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180192ff5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801930ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180193185`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180193238`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801932fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801933d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801933df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801933ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801933fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180192a53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180192b0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180192e89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180192f3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180192ff5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801930ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180193185`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180193238`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801932fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801933d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801933df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801933ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801933fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1801930df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180193199`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1801930df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180193199`

## string_xrefs

- `0x180192c65`: `inProcessMediaExtension`
- `0x180193003`: `@PackageInstallLocation`
- `0x180192f4c`: `@Path`
- `0x180192e93`: `@ActivatableClassId`
- `0x180192a1d`: `CreateContentDecryptionModuleInfoFromMediaExtensionMap`

## pseudocode

```c
__int64 __fastcall CreateContentDecryptionModuleInfoFromMediaExtensionMap(__int64 *a1, __int64 a2)
{
  HRESULT StringFromMap; // ebx
  CallStackTracing *v5; // rcx
  struct CallStackContext *v6; // rax
  __int64 v7; // rdx
  CallStackTracing *v8; // rcx
  struct CallStackContext *v9; // rax
  CallStackTracing *v10; // rcx
  struct CallStackContext *v11; // rax
  __int64 v12; // rax
  __int64 (__fastcall *v13)(__int64 *, HSTRING__ *, char *); // rbx
  int v14; // eax
  CallStackTracing *v15; // rcx
  struct CallStackContext *v16; // rax
  CallStackTracing *v17; // rcx
  struct CallStackContext *v18; // rax
  CallStackTracing *v19; // rcx
  struct CallStackContext *v20; // rax
  __int64 v21; // rcx
  CallStackTracing *v22; // rcx
  struct CallStackContext *v23; // rax
  CallStackTracing *v24; // rcx
  struct CallStackContext *v25; // rax
  CallStackTracing *v26; // rcx
  struct CallStackContext *v27; // rax
  CallStackTracing *v28; // rcx
  struct CallStackContext *v29; // rax
  HSTRING v30; // rdx
  HSTRING v31; // rcx
  CallStackTracing *v32; // rcx
  struct CallStackContext *v33; // rax
  CallStackTracing *v34; // rcx
  struct CallStackContext *v35; // rax
  __int64 v36; // rcx
  CallStackTracing *v37; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  char v40; // [rsp+30h] [rbp-29h] BYREF
  CallStackScopeTrace v41; // [rsp+31h] [rbp-28h] BYREF
  __int64 v42; // [rsp+38h] [rbp-21h] BYREF
  HSTRING newString; // [rsp+40h] [rbp-19h] BYREF
  HSTRING string1; // [rsp+48h] [rbp-11h] BYREF
  HSTRING v45; // [rsp+50h] [rbp-9h] BYREF
  HSTRING string; // [rsp+58h] [rbp-1h] BYREF
  Microsoft::WRL::Wrappers::HStringReference v47; // [rsp+60h] [rbp+7h] BYREF

  v42 = 0;
  string = 0;
  v45 = 0;
  string1 = 0;
  newString = 0;
  CallStackScopeTrace::CallStackScopeTrace(&v41, "CreateContentDecryptionModuleInfoFromMediaExtensionMap", 1539);
  WindowsDeleteString(*(HSTRING *)a2);
  *(_QWORD *)a2 = 0;
  StringFromMap = CreateStringFromMap(a1, L"@PackageFamilyName", a2);
  if ( StringFromMap >= 0 )
  {
    WindowsDeleteString(*(HSTRING *)(a2 + 8));
    *(_QWORD *)(a2 + 8) = 0;
    StringFromMap = CreateStringFromMap(a1, L"@PackageFullName", a2 + 8);
    if ( StringFromMap >= 0 )
    {
      StringFromMap = CreateBOOLFromMap(a1, L"@PackageRequiresRegistration", a2 + 32);
      if ( StringFromMap >= 0 )
      {
        v12 = *a1;
        v40 = 0;
        v47.hstr_ = 0;
        v13 = *(__int64 (__fastcall **)(__int64 *, HSTRING__ *, char *))(v12 + 64);
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v47, L"inProcessMediaExtension", 0x18u, 0x17u);
        v14 = v13(a1, v47.hstr_, &v40);
        v47.hstr_ = 0;
        StringFromMap = v14;
        if ( v14 >= 0 )
        {
          if ( v40 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
            StringFromMap = GetSubMapFromMap(a1, L"MediaContentDecryptionModule", &v42);
            if ( StringFromMap >= 0 )
            {
              WindowsDeleteString(*(HSTRING *)(a2 + 48));
              v21 = v42;
              *(_QWORD *)(a2 + 48) = 0;
              StringFromMap = CreateStringFromMap(v21, L"@ActivatableClassId", a2 + 48);
              if ( StringFromMap >= 0 )
              {
                WindowsDeleteString(string);
                string = 0;
                StringFromMap = CreateStringFromMap(v42, L"@Path", &string);
                if ( StringFromMap >= 0 )
                {
                  WindowsDeleteString(string1);
                  string1 = 0;
                  StringFromMap = CreateStringFromMap(a1, L"@PackageInstallLocation", &string1);
                  if ( StringFromMap >= 0 )
                  {
                    WindowsDeleteString(newString);
                    newString = 0;
                    v47.hstr_ = 0;
                    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v47, L"\\", 2u, 1u);
                    StringFromMap = WindowsConcatString(string1, v47.hstr_, &newString);
                    if ( StringFromMap >= 0 )
                    {
                      WindowsDeleteString(*(HSTRING *)(a2 + 56));
                      v30 = string;
                      v31 = newString;
                      *(_QWORD *)(a2 + 56) = 0;
                      StringFromMap = WindowsConcatString(v31, v30, (HSTRING *)(a2 + 56));
                      if ( StringFromMap >= 0 )
                      {
                        WindowsDeleteString(v45);
                        v45 = 0;
                        StringFromMap = CreateStringFromMap(v42, L"@ProcessorArchitecture", &v45);
                        if ( StringFromMap >= 0 )
                        {
                          *(_DWORD *)(a2 + 40) = CreateExtensionArchitectureFromString(v45);
                          WindowsDeleteString(*(HSTRING *)(a2 + 64));
                          v36 = v42;
                          *(_QWORD *)(a2 + 64) = 0;
                          StringFromMap = CreateStringFromMap(v36, L"@SupportedKeySystem", a2 + 64);
                          if ( StringFromMap < 0 )
                          {
                            v37 = CallStackTracing::s_wpInstance;
                            if ( !CallStackTracing::s_wpInstance )
                            {
                              CallStackTracing::s_wpInstance = &stru_1801FC290;
                              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                              {
                                v37 = CallStackTracing::s_wpInstance;
                              }
                              else
                              {
                                v37 = &stru_1801F8A30;
                                CallStackTracing::s_wpInstance = &stru_1801F8A30;
                              }
                            }
                            if ( v37->m_fEnabled )
                            {
                              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v37);
                              if ( ThreadRelativeContext->m_result != StringFromMap )
                                CallStackContext::TraceFailure(
                                  ThreadRelativeContext,
                                  "CreateContentDecryptionModuleInfoFromMediaExtensionMap",
                                  1564,
                                  StringFromMap);
                            }
                            if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                            {
                              v7 = 208;
                              goto LABEL_131;
                            }
                          }
                        }
                        else
                        {
                          v34 = CallStackTracing::s_wpInstance;
                          if ( !CallStackTracing::s_wpInstance )
                          {
                            CallStackTracing::s_wpInstance = &stru_1801FC290;
                            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                            {
                              v34 = CallStackTracing::s_wpInstance;
                            }
                            else
                            {
                              v34 = &stru_1801F8A30;
                              CallStackTracing::s_wpInstance = &stru_1801F8A30;
                            }
                          }
                          if ( v34->m_fEnabled )
                          {
                            v35 = CallStackTracing::GetThreadRelativeContext(v34);
                            if ( v35->m_result != StringFromMap )
                              CallStackContext::TraceFailure(
                                v35,
                                "CreateContentDecryptionModuleInfoFromMediaExtensionMap",
                                1561,
                                StringFromMap);
                          }
                          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                          {
                            v7 = 207;
                            goto LABEL_131;
                          }
                        }
                      }
                      else
                      {
                        v32 = CallStackTracing::s_wpInstance;
                        if ( !CallStackTracing::s_wpInstance )
                        {
                          CallStackTracing::s_wpInstance = &stru_1801FC290;
                          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                          {
                            v32 = CallStackTracing::s_wpInstance;
                          }
                          else
                          {
                            v32 = &stru_1801F8A30;
                            CallStackTracing::s_wpInstance = &stru_1801F8A30;
                          }
                        }
                        if ( v32->m_fEnabled )
                        {
                          v33 = CallStackTracing::GetThreadRelativeContext(v32);
                          if ( v33->m_result != StringFromMap )
                            CallStackContext::TraceFailure(
                              v33,
                              "CreateContentDecryptionModuleInfoFromMediaExtensionMap",
                              1559,
                              StringFromMap);
                        }
                        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                        {
                          v7 = 206;
                          goto LABEL_131;
                        }
                      }
                    }
                    else
                    {
                      v28 = CallStackTracing::s_wpInstance;
                      v47.hstr_ = 0;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        CallStackTracing::s_wpInstance = &stru_1801FC290;
                        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                        {
                          v28 = CallStackTracing::s_wpInstance;
                        }
                        else
                        {
                          v28 = &stru_1801F8A30;
                          CallStackTracing::s_wpInstance = &stru_1801F8A30;
                        }
                      }
                      if ( v28->m_fEnabled )
                      {
                        v29 = CallStackTracing::GetThreadRelativeContext(v28);
                        if ( v29->m_result != StringFromMap )
                          CallStackContext::TraceFailure(
                            v29,
                            "CreateContentDecryptionModuleInfoFromMediaExtensionMap",
                            1558,
                            StringFromMap);
                      }
                      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                      {
                        v7 = 205;
                        goto LABEL_131;
                      }
                    }
                  }
                  else
                  {
                    v26 = CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      CallStackTracing::s_wpInstance = &stru_1801FC290;
                      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                      {
                        v26 = CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v26 = &stru_1801F8A30;
                        CallStackTracing::s_wpInstance = &stru_1801F8A30;
                      }
                    }
                    if ( v26->m_fEnabled )
                    {
                      v27 = CallStackTracing::GetThreadRelativeContext(v26);
                      if ( v27->m_result != StringFromMap )
                        CallStackContext::TraceFailure(
                          v27,
                          "CreateContentDecryptionModuleInfoFromMediaExtensionMap",
                          1557,
                          StringFromMap);
                    }
                    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                    {
                      v7 = 204;
                      goto LABEL_131;
                    }
                  }
                }
                else
                {
                  v24 = CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    CallStackTracing::s_wpInstance = &stru_1801FC290;
                    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                    {
                      v24 = CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v24 = &stru_1801F8A30;
                      CallStackTracing::s_wpInstance = &stru_1801F8A30;
                    }
                  }
                  if ( v24->m_fEnabled )
                  {
                    v25 = CallStackTracing::GetThreadRelativeContext(v24);
                    if ( v25->m_result != StringFromMap )
                      CallStackContext::TraceFailure(
                        v25,
                        "CreateContentDecryptionModuleInfoFromMediaExtensionMap",
                        1556,
                        StringFromMap);
                  }
                  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                  {
                    v7 = 203;
                    goto LABEL_131;
                  }
                }
              }
              else
              {
                v22 = CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  CallStackTracing::s_wpInstance = &stru_1801FC290;
                  if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                  {
                    v22 = CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v22 = &stru_1801F8A30;
                    CallStackTracing::s_wpInstance = &stru_1801F8A30;
                  }
                }
                if ( v22->m_fEnabled )
                {
                  v23 = CallStackTracing::GetThreadRelativeContext(v22);
                  if ( v23->m_result != StringFromMap )
                    CallStackContext::TraceFailure(
                      v23,
                      "CreateContentDecryptionModuleInfoFromMediaExtensionMap",
                      1554,
                      StringFromMap);
                }
                if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                {
                  v7 = 202;
                  goto LABEL_131;
                }
              }
            }
            else
            {
              v19 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::s_wpInstance = &stru_1801FC290;
                if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                {
                  v19 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v19 = &stru_1801F8A30;
                  CallStackTracing::s_wpInstance = &stru_1801F8A30;
                }
              }
              if ( v19->m_fEnabled )
              {
                v20 = CallStackTracing::GetThreadRelativeContext(v19);
                if ( v20->m_result != StringFromMap )
                  CallStackContext::TraceFailure(
                    v20,
                    "CreateContentDecryptionModuleInfoFromMediaExtensionMap",
                    1552,
                    StringFromMap);
              }
              if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
              {
                v7 = 201;
                goto LABEL_131;
              }
            }
          }
          else
          {
            v17 = CallStackTracing::s_wpInstance;
            StringFromMap = -2147024891;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v17 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v17 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v17->m_fEnabled )
            {
              v18 = CallStackTracing::GetThreadRelativeContext(v17);
              if ( v18->m_result != -2147024891 )
                CallStackContext::TraceFailure(
                  v18,
                  "CreateContentDecryptionModuleInfoFromMediaExtensionMap",
                  1548,
                  -2147024891);
            }
            if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
            {
              v7 = 200;
              goto LABEL_131;
            }
          }
        }
        else
        {
          v15 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v15 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v15 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v15->m_fEnabled )
          {
            v16 = CallStackTracing::GetThreadRelativeContext(v15);
            if ( v16->m_result != StringFromMap )
              CallStackContext::TraceFailure(
                v16,
                "CreateContentDecryptionModuleInfoFromMediaExtensionMap",
                1544,
                StringFromMap);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v7 = 199;
            goto LABEL_131;
          }
        }
      }
      else
      {
        v10 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v10 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v10 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v10->m_fEnabled )
        {
          v11 = CallStackTracing::GetThreadRelativeContext(v10);
          if ( v11->m_result != StringFromMap )
            CallStackContext::TraceFailure(
              v11,
              "CreateContentDecryptionModuleInfoFromMediaExtensionMap",
              1541,
              StringFromMap);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v7 = 198;
          goto LABEL_131;
        }
      }
    }
    else
    {
      v8 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v8 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v8 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v8->m_fEnabled )
      {
        v9 = CallStackTracing::GetThreadRelativeContext(v8);
        if ( v9->m_result != StringFromMap )
          CallStackContext::TraceFailure(
            v9,
            "CreateContentDecryptionModuleInfoFromMediaExtensionMap",
            1540,
            StringFromMap);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v7 = 197;
        goto LABEL_131;
      }
    }
  }
  else
  {
    v5 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v5 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v5->m_fEnabled )
    {
      v6 = CallStackTracing::GetThreadRelativeContext(v5);
      if ( v6->m_result != StringFromMap )
        CallStackContext::TraceFailure(
          v6,
          "CreateContentDecryptionModuleInfoFromMediaExtensionMap",
          1539,
          StringFromMap);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v7 = 196;
LABEL_131:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        &WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
        0,
        StringFromMap);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace(&v41);
  WindowsDeleteString(newString);
  newString = 0;
  WindowsDeleteString(string1);
  string1 = 0;
  WindowsDeleteString(v45);
  v45 = 0;
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  return (unsigned int)StringFromMap;
}

```

## disassembly

```asm
0x1801929f4  mov     [rsp-8+arg_10], rbx
0x1801929f9  push    rbp
0x1801929fa  push    rsi
0x1801929fb  push    rdi
0x1801929fc  push    r14
0x1801929fe  push    r15
0x180192a00  lea     rbp, [rsp-37h]
0x180192a05  sub     rsp, 90h
0x180192a0c  mov     rax, cs:__security_cookie
0x180192a13  xor     rax, rsp
0x180192a16  mov     [rbp+57h+var_30], rax
0x180192a1a  xor     r14d, r14d
0x180192a1d  lea     r15, aCreatecontentd; "CreateContentDecryptionModuleInfoFromMe"...
0x180192a24  mov     rdi, rdx
0x180192a27  mov     [rbp+57h+var_78], r14
0x180192a2b  mov     rsi, rcx
0x180192a2e  mov     [rbp+57h+string], r14
0x180192a32  mov     rdx, r15; char *
0x180192a35  mov     [rbp+57h+var_60], r14
0x180192a39  mov     r8d, 603h; int
0x180192a3f  mov     [rbp+57h+string1], r14
0x180192a43  lea     rcx, [rbp+57h+var_7F]; this
0x180192a47  mov     [rbp+57h+newString], r14
0x180192a4b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180192a50  mov     rcx, [rdi]; string
0x180192a53  call    cs:__imp_WindowsDeleteString
0x180192a59  mov     r8, rdi
0x180192a5c  mov     [rdi], r14
0x180192a5f  lea     rdx, aPackagefamilyn; "@PackageFamilyName"
0x180192a66  mov     rcx, rsi
0x180192a69  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x180192a6e  mov     ebx, eax
0x180192a70  test    eax, eax
0x180192a72  jns     loc_180192B03
0x180192a78  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180192a7f  test    rcx, rcx
0x180192a82  jnz     short loc_180192AC5
0x180192a84  mov     rcx, cs:stru_1801FC290.__vftable
0x180192a8b  lea     r8, stru_1801FC290
0x180192a92  mov     edx, 7F0h
0x180192a97  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180192a9e  mov     rax, [rcx+8]
0x180192aa2  mov     rcx, r8
0x180192aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192aaa  test    eax, eax
0x180192aac  jnz     short loc_180192ABE
0x180192aae  lea     rcx, stru_1801F8A30
0x180192ab5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180192abc  jmp     short loc_180192AC5
0x180192abe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180192ac5  cmp     [rcx+8], r14b
0x180192ac9  jz      short loc_180192AEC
0x180192acb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180192ad0  cmp     [rax+7CCh], ebx
0x180192ad6  jz      short loc_180192AEC
0x180192ad8  mov     r9d, ebx; int
0x180192adb  mov     r8d, 603h; int
0x180192ae1  mov     rdx, r15; char *
0x180192ae4  mov     rcx, rax; this
0x180192ae7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180192aec  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180192af3  jb      loc_1801933C4
0x180192af9  mov     edx, 0C4h
0x180192afe  jmp     loc_1801933A6
0x180192b03  lea     rbx, [rdi+8]
0x180192b07  mov     rcx, [rbx]; string
0x180192b0a  call    cs:__imp_WindowsDeleteString
0x180192b10  mov     r8, rbx
0x180192b13  mov     [rbx], r14
0x180192b16  lea     rdx, aPackagefullnam; "@PackageFullName"
0x180192b1d  mov     rcx, rsi
0x180192b20  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x180192b25  mov     ebx, eax
0x180192b27  test    eax, eax
0x180192b29  jns     loc_180192BBA
0x180192b2f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180192b36  test    rcx, rcx
0x180192b39  jnz     short loc_180192B7C
0x180192b3b  mov     rax, cs:stru_1801FC290.__vftable
0x180192b42  lea     r8, stru_1801FC290
0x180192b49  mov     edx, 7F0h
0x180192b4e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180192b55  mov     rcx, r8
0x180192b58  mov     rax, [rax+8]
0x180192b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192b61  test    eax, eax
0x180192b63  jnz     short loc_180192B75
0x180192b65  lea     rcx, stru_1801F8A30
0x180192b6c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180192b73  jmp     short loc_180192B7C
0x180192b75  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180192b7c  cmp     [rcx+8], r14b
0x180192b80  jz      short loc_180192BA3
0x180192b82  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180192b87  cmp     [rax+7CCh], ebx
0x180192b8d  jz      short loc_180192BA3
0x180192b8f  mov     r9d, ebx; int
0x180192b92  mov     r8d, 604h; int
0x180192b98  mov     rdx, r15; char *
0x180192b9b  mov     rcx, rax; this
0x180192b9e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180192ba3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180192baa  jb      loc_1801933C4
0x180192bb0  mov     edx, 0C5h
0x180192bb5  jmp     loc_1801933A6
0x180192bba  lea     r8, [rdi+20h]
0x180192bbe  mov     rcx, rsi
0x180192bc1  lea     rdx, aPackagerequire; "@PackageRequiresRegistration"
0x180192bc8  call    ?CreateBOOLFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEA_N@Z; CreateBOOLFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,bool *)
0x180192bcd  mov     ebx, eax
0x180192bcf  test    eax, eax
0x180192bd1  jns     loc_180192C62
0x180192bd7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180192bde  test    rcx, rcx
0x180192be1  jnz     short loc_180192C24
0x180192be3  mov     rax, cs:stru_1801FC290.__vftable
0x180192bea  lea     r8, stru_1801FC290
0x180192bf1  mov     edx, 7F0h
0x180192bf6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180192bfd  mov     rcx, r8
0x180192c00  mov     rax, [rax+8]
0x180192c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192c09  test    eax, eax
0x180192c0b  jnz     short loc_180192C1D
0x180192c0d  lea     rcx, stru_1801F8A30
0x180192c14  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180192c1b  jmp     short loc_180192C24
0x180192c1d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180192c24  cmp     [rcx+8], r14b
0x180192c28  jz      short loc_180192C4B
0x180192c2a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180192c2f  cmp     [rax+7CCh], ebx
0x180192c35  jz      short loc_180192C4B
0x180192c37  mov     r9d, ebx; int
0x180192c3a  mov     r8d, 605h; int
0x180192c40  mov     rdx, r15; char *
0x180192c43  mov     rcx, rax; this
0x180192c46  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180192c4b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180192c52  jb      loc_1801933C4
0x180192c58  mov     edx, 0C6h
0x180192c5d  jmp     loc_1801933A6
0x180192c62  mov     rax, [rsi]
0x180192c65  lea     rdx, aInprocessmedia; "inProcessMediaExtension"
0x180192c6c  mov     r9d, 17h; unsigned int
0x180192c72  mov     [rbp+57h+var_80], r14b
0x180192c76  lea     rcx, [rbp+57h+var_50]; this
0x180192c7a  mov     [rbp+57h+var_50.hstr_], r14
0x180192c7e  mov     rbx, [rax+40h]
0x180192c82  lea     r8d, [r9+1]; unsigned int
0x180192c86  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180192c8b  mov     rdx, [rbp+57h+var_50.hstr_]
0x180192c8f  lea     r8, [rbp+57h+var_80]
0x180192c93  mov     rcx, rsi
0x180192c96  mov     rax, rbx
0x180192c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192c9e  mov     [rbp+57h+var_50.hstr_], r14
0x180192ca2  mov     ebx, eax
0x180192ca4  test    eax, eax
0x180192ca6  jns     loc_180192D37
0x180192cac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180192cb3  test    rcx, rcx
0x180192cb6  jnz     short loc_180192CF9
0x180192cb8  mov     rax, cs:stru_1801FC290.__vftable
0x180192cbf  lea     r8, stru_1801FC290
0x180192cc6  mov     edx, 7F0h
0x180192ccb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180192cd2  mov     rcx, r8
0x180192cd5  mov     rax, [rax+8]
0x180192cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192cde  test    eax, eax
0x180192ce0  jnz     short loc_180192CF2
0x180192ce2  lea     rcx, stru_1801F8A30
0x180192ce9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180192cf0  jmp     short loc_180192CF9
0x180192cf2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180192cf9  cmp     [rcx+8], r14b
0x180192cfd  jz      short loc_180192D20
0x180192cff  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180192d04  cmp     [rax+7CCh], ebx
0x180192d0a  jz      short loc_180192D20
0x180192d0c  mov     r9d, ebx; int
0x180192d0f  mov     r8d, 608h; int
0x180192d15  mov     rdx, r15; char *
0x180192d18  mov     rcx, rax; this
0x180192d1b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180192d20  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180192d27  jb      loc_1801933C4
0x180192d2d  mov     edx, 0C7h
0x180192d32  jmp     loc_1801933A6
0x180192d37  cmp     [rbp+57h+var_80], r14b
0x180192d3b  jnz     loc_180192DD1
0x180192d41  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180192d48  mov     ebx, 80070005h
0x180192d4d  test    rcx, rcx
0x180192d50  jnz     short loc_180192D93
0x180192d52  mov     rax, cs:stru_1801FC290.__vftable
0x180192d59  lea     r8, stru_1801FC290
0x180192d60  mov     edx, 7F0h
0x180192d65  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180192d6c  mov     rcx, r8
0x180192d6f  mov     rax, [rax+8]
0x180192d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192d78  test    eax, eax
0x180192d7a  jnz     short loc_180192D8C
0x180192d7c  lea     rcx, stru_1801F8A30
0x180192d83  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180192d8a  jmp     short loc_180192D93
0x180192d8c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180192d93  cmp     [rcx+8], r14b
0x180192d97  jz      short loc_180192DBA
0x180192d99  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180192d9e  cmp     [rax+7CCh], ebx
0x180192da4  jz      short loc_180192DBA
0x180192da6  mov     r9d, ebx; int
0x180192da9  mov     r8d, 60Ch; int
0x180192daf  mov     rdx, r15; char *
0x180192db2  mov     rcx, rax; this
0x180192db5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180192dba  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180192dc1  jb      loc_1801933C4
0x180192dc7  mov     edx, 0C8h
0x180192dcc  jmp     loc_1801933A6
0x180192dd1  lea     rcx, [rbp+57h+var_78]
0x180192dd5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180192dda  lea     r8, [rbp+57h+var_78]
0x180192dde  mov     rcx, rsi
0x180192de1  lea     rdx, aMediacontentde; "MediaContentDecryptionModule"
0x180192de8  call    GetSubMapFromMap
0x180192ded  mov     ebx, eax
0x180192def  test    eax, eax
0x180192df1  jns     loc_180192E82
0x180192df7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180192dfe  test    rcx, rcx
0x180192e01  jnz     short loc_180192E44
0x180192e03  mov     rax, cs:stru_1801FC290.__vftable
0x180192e0a  lea     r8, stru_1801FC290
0x180192e11  mov     edx, 7F0h
0x180192e16  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180192e1d  mov     rcx, r8
0x180192e20  mov     rax, [rax+8]
0x180192e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192e29  test    eax, eax
0x180192e2b  jnz     short loc_180192E3D
0x180192e2d  lea     rcx, stru_1801F8A30
0x180192e34  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180192e3b  jmp     short loc_180192E44
0x180192e3d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180192e44  cmp     [rcx+8], r14b
0x180192e48  jz      short loc_180192E6B
0x180192e4a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180192e4f  cmp     [rax+7CCh], ebx
0x180192e55  jz      short loc_180192E6B
0x180192e57  mov     r9d, ebx; int
0x180192e5a  mov     r8d, 610h; int
0x180192e60  mov     rdx, r15; char *
0x180192e63  mov     rcx, rax; this
0x180192e66  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180192e6b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180192e72  jb      loc_1801933C4
0x180192e78  mov     edx, 0C9h
0x180192e7d  jmp     loc_1801933A6
0x180192e82  lea     rbx, [rdi+30h]
0x180192e86  mov     rcx, [rbx]; string
0x180192e89  call    cs:__imp_WindowsDeleteString
0x180192e8f  mov     rcx, [rbp+57h+var_78]
0x180192e93  lea     rdx, aActivatablecla; "@ActivatableClassId"
0x180192e9a  mov     r8, rbx
0x180192e9d  mov     [rbx], r14
0x180192ea0  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x180192ea5  mov     ebx, eax
0x180192ea7  test    eax, eax
0x180192ea9  jns     loc_180192F3A
0x180192eaf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180192eb6  test    rcx, rcx
0x180192eb9  jnz     short loc_180192EFC
0x180192ebb  mov     rax, cs:stru_1801FC290.__vftable
0x180192ec2  lea     r8, stru_1801FC290
0x180192ec9  mov     edx, 7F0h
0x180192ece  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180192ed5  mov     rcx, r8
0x180192ed8  mov     rax, [rax+8]
0x180192edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192ee1  test    eax, eax
0x180192ee3  jnz     short loc_180192EF5
0x180192ee5  lea     rcx, stru_1801F8A30
0x180192eec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180192ef3  jmp     short loc_180192EFC
0x180192ef5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180192efc  cmp     [rcx+8], r14b
0x180192f00  jz      short loc_180192F23
0x180192f02  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180192f07  cmp     [rax+7CCh], ebx
0x180192f0d  jz      short loc_180192F23
0x180192f0f  mov     r9d, ebx; int
0x180192f12  mov     r8d, 612h; int
0x180192f18  mov     rdx, r15; char *
0x180192f1b  mov     rcx, rax; this
0x180192f1e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180192f23  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
  ... truncated ...
```
