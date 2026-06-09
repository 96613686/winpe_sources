# CreateInprocExtensionInfoFromMediaExtensionMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,InprocExtensionInfo &)

- ea: `0x180076bb0`
- end: `0x1800770c1`
- name: `?CreateInprocExtensionInfoFromMediaExtensionMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@0AEAUInprocExtensionInfo@@@Z`
- size: `1297`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800770c8`

## callees

- `0x1800023e0`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x18003c478`
- `0x180071330`
- `0x1800761b0`
- `0x18007656c`
- `0x180076bb0`
- `0x1800775b0`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180076e12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180076ecc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180076e12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180076ecc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076cc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076cf6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076dc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076dcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076dde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076eb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076f6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076f8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076f9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077053`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007708d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007709b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076cc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076cf6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076dc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076dcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076dde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076eb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076f6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076f8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076f9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077053`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007708d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007709b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076c24`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076d29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076e32`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076ee8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076fcd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076c24`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076d29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076e32`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076ee8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076fcd`

## string_xrefs

- `0x180076cd3`: `@Path`
- `0x180076bd6`: `CreateInprocExtensionInfoFromMediaExtensionMap`
- `0x180076f7a`: `@ActivatableClassId`
- `0x180076d04`: `@PackageInstallLocation`

## pseudocode

```c
__int64 __fastcall CreateInprocExtensionInfoFromMediaExtensionMap(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rdx
  HRESULT ExtensionInfoFromMediaExtensionMap; // ebx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  HSTRING v30; // rdx
  HSTRING v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  HSTRING v41; // rcx
  _BYTE v43[8]; // [rsp+30h] [rbp-50h] BYREF
  HSTRING newString; // [rsp+38h] [rbp-48h] BYREF
  HSTRING string1; // [rsp+40h] [rbp-40h] BYREF
  HSTRING v46; // [rsp+48h] [rbp-38h] BYREF
  HSTRING string; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  HSTRING string2; // [rsp+70h] [rbp-10h]

  string = 0;
  v46 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v43,
    "CreateInprocExtensionInfoFromMediaExtensionMap",
    983);
  ExtensionInfoFromMediaExtensionMap = CreateExtensionInfoFromMediaExtensionMap(a1, a2, a3);
  if ( ExtensionInfoFromMediaExtensionMap < 0 )
  {
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v8, v9);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != ExtensionInfoFromMediaExtensionMap )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CreateInprocExtensionInfoFromMediaExtensionMap",
          983,
          ExtensionInfoFromMediaExtensionMap);
    }
    if ( g_wppLevels )
    {
      v13 = 130;
LABEL_12:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
        0,
        ExtensionInfoFromMediaExtensionMap);
      goto LABEL_63;
    }
    goto LABEL_63;
  }
  WindowsDeleteString(string);
  string = 0;
  ExtensionInfoFromMediaExtensionMap = CreateStringFromMap(a2, L"@Path", &string);
  if ( ExtensionInfoFromMediaExtensionMap >= 0 )
  {
    string1 = 0;
    newString = 0;
    WindowsDeleteString(0);
    string1 = 0;
    ExtensionInfoFromMediaExtensionMap = CreateStringFromMap(a1, L"@PackageInstallLocation", &string1);
    if ( ExtensionInfoFromMediaExtensionMap < 0 )
    {
      v20 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v18, v19);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)v22 + 499) != ExtensionInfoFromMediaExtensionMap )
          CallStackContext::TraceFailure(
            v22,
            "CreateInprocExtensionInfoFromMediaExtensionMap",
            992,
            ExtensionInfoFromMediaExtensionMap);
      }
      if ( !g_wppLevels )
        goto LABEL_26;
      v23 = 131;
LABEL_25:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v23,
        WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
        0,
        ExtensionInfoFromMediaExtensionMap);
LABEL_26:
      WindowsDeleteString(newString);
      newString = 0;
      WindowsDeleteString(string1);
      goto LABEL_63;
    }
    WindowsDeleteString(newString);
    newString = 0;
    string2 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"\\", 2u, 1u);
    ExtensionInfoFromMediaExtensionMap = WindowsConcatString(string1, string2, &newString);
    if ( ExtensionInfoFromMediaExtensionMap < 0 )
    {
      v27 = (__int64 *)CallStackTracing::s_wpInstance;
      string2 = 0;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25, v26);
        CallStackTracing::s_wpInstance = v28;
        if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        {
          v27 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v27 + 8) )
      {
        v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
        if ( *((_DWORD *)v29 + 499) != ExtensionInfoFromMediaExtensionMap )
          CallStackContext::TraceFailure(
            v29,
            "CreateInprocExtensionInfoFromMediaExtensionMap",
            993,
            ExtensionInfoFromMediaExtensionMap);
      }
      if ( !g_wppLevels )
        goto LABEL_26;
      v23 = 132;
      goto LABEL_25;
    }
    WindowsDeleteString(*(HSTRING *)(a3 + 56));
    v30 = string;
    v31 = newString;
    *(_QWORD *)(a3 + 56) = 0;
    ExtensionInfoFromMediaExtensionMap = WindowsConcatString(v31, v30, (HSTRING *)(a3 + 56));
    if ( ExtensionInfoFromMediaExtensionMap < 0 )
    {
      v35 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33, v34);
        CallStackTracing::s_wpInstance = v36;
        if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
        {
          v35 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v35 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v35 + 8) )
      {
        v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
        if ( *((_DWORD *)v37 + 499) != ExtensionInfoFromMediaExtensionMap )
          CallStackContext::TraceFailure(
            v37,
            "CreateInprocExtensionInfoFromMediaExtensionMap",
            994,
            ExtensionInfoFromMediaExtensionMap);
      }
      if ( !g_wppLevels )
        goto LABEL_26;
      v23 = 133;
      goto LABEL_25;
    }
    WindowsDeleteString(*(HSTRING *)(a3 + 48));
    *(_QWORD *)(a3 + 48) = 0;
    ExtensionInfoFromMediaExtensionMap = CreateStringFromMap(a2, L"@ActivatableClassId", a3 + 48);
    WindowsDeleteString(newString);
    newString = 0;
    WindowsDeleteString(string1);
    string1 = 0;
    if ( ExtensionInfoFromMediaExtensionMap >= 0 )
      goto LABEL_61;
  }
  if ( !*(_BYTE *)(a3 + 33) )
  {
LABEL_61:
    v41 = v46;
    ExtensionInfoFromMediaExtensionMap = 0;
    *(_DWORD *)(a3 + 40) = 0;
    WindowsDeleteString(v41);
    v46 = 0;
    if ( (int)CreateStringFromMap(a2, L"@ProcessorArchitecture", &v46) >= 0 )
      *(_DWORD *)(a3 + 40) = CreateExtensionArchitectureFromString(v46);
    goto LABEL_63;
  }
  v38 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15, v16);
    CallStackTracing::s_wpInstance = v39;
    if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
    {
      v38 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v38 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
    }
  }
  if ( *((_BYTE *)v38 + 8) )
  {
    v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
    if ( *((_DWORD *)v40 + 499) != ExtensionInfoFromMediaExtensionMap )
      CallStackContext::TraceFailure(
        v40,
        "CreateInprocExtensionInfoFromMediaExtensionMap",
        1001,
        ExtensionInfoFromMediaExtensionMap);
  }
  if ( g_wppLevels )
  {
    v13 = 134;
    goto LABEL_12;
  }
LABEL_63:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v43);
  WindowsDeleteString(v46);
  v46 = 0;
  WindowsDeleteString(string);
  return (unsigned int)ExtensionInfoFromMediaExtensionMap;
}

```

## disassembly

```asm
0x180076bb0  push    rbp
0x180076bb2  push    rbx
0x180076bb3  push    rsi
0x180076bb4  push    rdi
0x180076bb5  push    r12
0x180076bb7  push    r14
0x180076bb9  push    r15
0x180076bbb  mov     rbp, rsp
0x180076bbe  sub     rsp, 80h
0x180076bc5  mov     rax, cs:__security_cookie
0x180076bcc  xor     rax, rsp
0x180076bcf  mov     [rbp+var_8], rax
0x180076bd3  mov     rdi, r8
0x180076bd6  lea     r12, aCreateinprocex; "CreateInprocExtensionInfoFromMediaExten"...
0x180076bdd  mov     rsi, rdx
0x180076be0  mov     r14, rcx
0x180076be3  xor     r15d, r15d
0x180076be6  lea     rcx, [rbp+var_50]; this
0x180076bea  mov     rdx, r12; char *
0x180076bed  mov     [rbp+string], r15
0x180076bf1  mov     r8d, 3D7h; int
0x180076bf7  mov     [rbp+var_38], r15
0x180076bfb  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180076c00  mov     r8, rdi
0x180076c03  mov     rdx, rsi
0x180076c06  mov     rcx, r14
0x180076c09  call    ?CreateExtensionInfoFromMediaExtensionMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@0AEAUExtensionInfo@@@Z; CreateExtensionInfoFromMediaExtensionMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ExtensionInfo &)
0x180076c0e  mov     ebx, eax
0x180076c10  test    eax, eax
0x180076c12  jns     loc_180076CC1
0x180076c18  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076c1f  test    rcx, rcx
0x180076c22  jnz     short loc_180076C65
0x180076c24  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180076c2a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180076c31  mov     rcx, rax
0x180076c34  test    rax, rax
0x180076c37  jz      short loc_180076C57
0x180076c39  mov     rax, [rax]
0x180076c3c  mov     edx, 7F0h
0x180076c41  mov     rax, [rax+8]
0x180076c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076c4a  test    eax, eax
0x180076c4c  jz      short loc_180076C57
0x180076c4e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076c55  jmp     short loc_180076C65
0x180076c57  lea     rcx, qword_1800D6F70; this
0x180076c5e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180076c65  cmp     [rcx+8], r15b
0x180076c69  jz      short loc_180076C8C
0x180076c6b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180076c70  cmp     [rax+7CCh], ebx
0x180076c76  jz      short loc_180076C8C
0x180076c78  mov     r9d, ebx; int
0x180076c7b  mov     r8d, 3D7h; int
0x180076c81  mov     rdx, r12; char *
0x180076c84  mov     rcx, rax; this
0x180076c87  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180076c8c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180076c93  jb      loc_180077080
0x180076c99  mov     edx, 82h
0x180076c9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180076ca5  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x180076cac  xor     r9d, r9d
0x180076caf  mov     [rsp+80h+var_60], ebx
0x180076cb3  mov     rcx, [rcx+10h]
0x180076cb7  call    WPP_SF_qD
0x180076cbc  jmp     loc_180077080
0x180076cc1  mov     rcx, [rbp+string]; string
0x180076cc5  call    cs:__imp_WindowsDeleteString
0x180076ccb  lea     r8, [rbp+string]
0x180076ccf  mov     [rbp+string], r15
0x180076cd3  lea     rdx, aPath; "@Path"
0x180076cda  mov     rcx, rsi
0x180076cdd  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x180076ce2  mov     ebx, eax
0x180076ce4  test    eax, eax
0x180076ce6  js      loc_180076FAF
0x180076cec  xor     ecx, ecx; string
0x180076cee  mov     [rbp+string1], r15
0x180076cf2  mov     [rbp+newString], r15
0x180076cf6  call    cs:__imp_WindowsDeleteString
0x180076cfc  lea     r8, [rbp+string1]
0x180076d00  mov     [rbp+string1], r15
0x180076d04  lea     rdx, aPackageinstall; "@PackageInstallLocation"
0x180076d0b  mov     rcx, r14
0x180076d0e  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x180076d13  mov     ebx, eax
0x180076d15  test    eax, eax
0x180076d17  jns     loc_180076DDA
0x180076d1d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076d24  test    rcx, rcx
0x180076d27  jnz     short loc_180076D6A
0x180076d29  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180076d2f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180076d36  mov     rcx, rax
0x180076d39  test    rax, rax
0x180076d3c  jz      short loc_180076D5C
0x180076d3e  mov     rax, [rax]
0x180076d41  mov     edx, 7F0h
0x180076d46  mov     rax, [rax+8]
0x180076d4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076d4f  test    eax, eax
0x180076d51  jz      short loc_180076D5C
0x180076d53  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076d5a  jmp     short loc_180076D6A
0x180076d5c  lea     rcx, qword_1800D6F70; this
0x180076d63  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180076d6a  cmp     [rcx+8], r15b
0x180076d6e  jz      short loc_180076D91
0x180076d70  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180076d75  cmp     [rax+7CCh], ebx
0x180076d7b  jz      short loc_180076D91
0x180076d7d  mov     r9d, ebx; int
0x180076d80  mov     r8d, 3E0h; int
0x180076d86  mov     rdx, r12; char *
0x180076d89  mov     rcx, rax; this
0x180076d8c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180076d91  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180076d98  jb      short loc_180076DBD
0x180076d9a  mov     edx, 83h
0x180076d9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180076da6  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x180076dad  xor     r9d, r9d
0x180076db0  mov     [rsp+80h+var_60], ebx
0x180076db4  mov     rcx, [rcx+10h]
0x180076db8  call    WPP_SF_qD
0x180076dbd  mov     rcx, [rbp+newString]; string
0x180076dc1  call    cs:__imp_WindowsDeleteString
0x180076dc7  mov     rcx, [rbp+string1]; string
0x180076dcb  mov     [rbp+newString], r15
0x180076dcf  call    cs:__imp_WindowsDeleteString
0x180076dd5  jmp     loc_180077080
0x180076dda  mov     rcx, [rbp+newString]; string
0x180076dde  call    cs:__imp_WindowsDeleteString
0x180076de4  mov     r9d, 1; unsigned int
0x180076dea  mov     [rbp+newString], r15
0x180076dee  lea     rdx, asc_1800C17C8; "\\"
0x180076df5  mov     [rbp+string2], r15
0x180076df9  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180076dfd  lea     r8d, [r9+1]; unsigned int
0x180076e01  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180076e06  mov     rdx, [rbp+string2]; string2
0x180076e0a  lea     r8, [rbp+newString]; newString
0x180076e0e  mov     rcx, [rbp+string1]; string1
0x180076e12  call    cs:__imp_WindowsConcatString
0x180076e18  mov     ebx, eax
0x180076e1a  test    eax, eax
0x180076e1c  jns     loc_180076EB1
0x180076e22  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076e29  mov     [rbp+string2], r15
0x180076e2d  test    rcx, rcx
0x180076e30  jnz     short loc_180076E73
0x180076e32  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180076e38  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180076e3f  mov     rcx, rax
0x180076e42  test    rax, rax
0x180076e45  jz      short loc_180076E65
0x180076e47  mov     rax, [rax]
0x180076e4a  mov     edx, 7F0h
0x180076e4f  mov     rax, [rax+8]
0x180076e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076e58  test    eax, eax
0x180076e5a  jz      short loc_180076E65
0x180076e5c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076e63  jmp     short loc_180076E73
0x180076e65  lea     rcx, qword_1800D6F70; this
0x180076e6c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180076e73  cmp     [rcx+8], r15b
0x180076e77  jz      short loc_180076E9A
0x180076e79  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180076e7e  cmp     [rax+7CCh], ebx
0x180076e84  jz      short loc_180076E9A
0x180076e86  mov     r9d, ebx; int
0x180076e89  mov     r8d, 3E1h; int
0x180076e8f  mov     rdx, r12; char *
0x180076e92  mov     rcx, rax; this
0x180076e95  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180076e9a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180076ea1  jb      loc_180076DBD
0x180076ea7  mov     edx, 84h
0x180076eac  jmp     loc_180076D9F
0x180076eb1  lea     rbx, [rdi+38h]
0x180076eb5  mov     rcx, [rbx]; string
0x180076eb8  call    cs:__imp_WindowsDeleteString
0x180076ebe  mov     rdx, [rbp+string]; string2
0x180076ec2  mov     r8, rbx; newString
0x180076ec5  mov     rcx, [rbp+newString]; string1
0x180076ec9  mov     [rbx], r15
0x180076ecc  call    cs:__imp_WindowsConcatString
0x180076ed2  mov     ebx, eax
0x180076ed4  test    eax, eax
0x180076ed6  jns     loc_180076F67
0x180076edc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076ee3  test    rcx, rcx
0x180076ee6  jnz     short loc_180076F29
0x180076ee8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180076eee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180076ef5  mov     rcx, rax
0x180076ef8  test    rax, rax
0x180076efb  jz      short loc_180076F1B
0x180076efd  mov     rax, [rax]
0x180076f00  mov     edx, 7F0h
0x180076f05  mov     rax, [rax+8]
0x180076f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076f0e  test    eax, eax
0x180076f10  jz      short loc_180076F1B
0x180076f12  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076f19  jmp     short loc_180076F29
0x180076f1b  lea     rcx, qword_1800D6F70; this
0x180076f22  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180076f29  cmp     [rcx+8], r15b
0x180076f2d  jz      short loc_180076F50
0x180076f2f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180076f34  cmp     [rax+7CCh], ebx
0x180076f3a  jz      short loc_180076F50
0x180076f3c  mov     r9d, ebx; int
0x180076f3f  mov     r8d, 3E2h; int
0x180076f45  mov     rdx, r12; char *
0x180076f48  mov     rcx, rax; this
0x180076f4b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180076f50  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180076f57  jb      loc_180076DBD
0x180076f5d  mov     edx, 85h
0x180076f62  jmp     loc_180076D9F
0x180076f67  lea     rbx, [rdi+30h]
0x180076f6b  mov     rcx, [rbx]; string
0x180076f6e  call    cs:__imp_WindowsDeleteString
0x180076f74  mov     r8, rbx
0x180076f77  mov     [rbx], r15
0x180076f7a  lea     rdx, aActivatablecla; "@ActivatableClassId"
0x180076f81  mov     rcx, rsi
0x180076f84  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x180076f89  mov     rcx, [rbp+newString]; string
0x180076f8d  mov     ebx, eax
0x180076f8f  call    cs:__imp_WindowsDeleteString
0x180076f95  mov     rcx, [rbp+string1]; string
0x180076f99  mov     [rbp+newString], r15
0x180076f9d  call    cs:__imp_WindowsDeleteString
0x180076fa3  mov     [rbp+string1], r15
0x180076fa7  test    ebx, ebx
0x180076fa9  jns     loc_180077048
0x180076faf  cmp     [rdi+21h], r15b
0x180076fb3  jz      loc_180077048
0x180076fb9  test    ebx, ebx
0x180076fbb  jns     loc_180077048
0x180076fc1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076fc8  test    rcx, rcx
0x180076fcb  jnz     short loc_18007700E
0x180076fcd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180076fd3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180076fda  mov     rcx, rax
0x180076fdd  test    rax, rax
0x180076fe0  jz      short loc_180077000
0x180076fe2  mov     rax, [rax]
0x180076fe5  mov     edx, 7F0h
0x180076fea  mov     rax, [rax+8]
0x180076fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076ff3  test    eax, eax
0x180076ff5  jz      short loc_180077000
0x180076ff7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076ffe  jmp     short loc_18007700E
0x180077000  lea     rcx, qword_1800D6F70; this
0x180077007  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007700e  cmp     [rcx+8], r15b
0x180077012  jz      short loc_180077035
0x180077014  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180077019  cmp     [rax+7CCh], ebx
0x18007701f  jz      short loc_180077035
0x180077021  mov     r9d, ebx; int
0x180077024  mov     r8d, 3E9h; int
0x18007702a  mov     rdx, r12; char *
0x18007702d  mov     rcx, rax; this
0x180077030  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180077035  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007703c  jb      short loc_180077080
0x18007703e  mov     edx, 86h
0x180077043  jmp     loc_180076C9E
0x180077048  mov     rcx, [rbp+var_38]; string
0x18007704c  mov     ebx, r15d
0x18007704f  mov     [rdi+28h], r15d
0x180077053  call    cs:__imp_WindowsDeleteString
0x180077059  lea     r8, [rbp+var_38]
0x18007705d  mov     [rbp+var_38], r15
0x180077061  lea     rdx, aProcessorarchi; "@ProcessorArchitecture"
0x180077068  mov     rcx, rsi
0x18007706b  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x180077070  test    eax, eax
0x180077072  js      short loc_180077080
0x180077074  mov     rcx, [rbp+var_38]
0x180077078  call    ?CreateExtensionArchitectureFromString@@YA?AW4MediaExtensionArchitecture@@PEAUHSTRING__@@@Z; CreateExtensionArchitectureFromString(HSTRING__ *)
0x18007707d  mov     [rdi+28h], eax
0x180077080  lea     rcx, [rbp+var_50]; this
0x180077084  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180077089  mov     rcx, [rbp+var_38]; string
0x18007708d  call    cs:__imp_WindowsDeleteString
0x180077093  mov     rcx, [rbp+string]; string
0x180077097  mov     [rbp+var_38], r15
0x18007709b  call    cs:__imp_WindowsDeleteString
0x1800770a1  mov     eax, ebx
  ... truncated ...
```
