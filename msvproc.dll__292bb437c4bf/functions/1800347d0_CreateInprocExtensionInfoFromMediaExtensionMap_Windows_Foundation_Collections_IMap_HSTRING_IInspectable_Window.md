# CreateInprocExtensionInfoFromMediaExtensionMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,InprocExtensionInfo &)

- ea: `0x1800347d0`
- end: `0x180034ca8`
- name: `?CreateInprocExtensionInfoFromMediaExtensionMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@0AEAUInprocExtensionInfo@@@Z`
- size: `1240`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800346b4`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000caec`
- `0x18000ec20`
- `0x18000ecf0`
- `0x1800180fc`
- `0x180018a4c`
- `0x180025b08`
- `0x1800347d0`
- `0x18003639c`
- `0x180054140`
- `0x1800ca498`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800348ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800348dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800349a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800349b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800349c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034a9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034b55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034b76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034b84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034c3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034c74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034c82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800348ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800348dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800349a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800349b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800349c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034a9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034b55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034b76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034b84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034c3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034c74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034c82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1800349f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180034ab3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1800349f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180034ab3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180034910`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180034a19`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180034acf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180034bb4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180034910`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180034a19`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180034acf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180034bb4`

## string_xrefs

- `0x1800347f6`: `CreateInprocExtensionInfoFromMediaExtensionMap`
- `0x1800348ba`: `@Path`
- `0x1800348eb`: `@PackageInstallLocation`
- `0x180034b61`: `@ActivatableClassId`

## pseudocode

```c
__int64 __fastcall CreateInprocExtensionInfoFromMediaExtensionMap(__int64 a1, __int64 a2, __int64 a3)
{
  HRESULT ExtensionInfoFromMediaExtensionMap; // ebx
  CallStackTracing *v7; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  HSTRING v17; // rdx
  HSTRING v18; // rcx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  HSTRING v25; // rcx
  _BYTE v27[8]; // [rsp+30h] [rbp-50h] BYREF
  HSTRING newString; // [rsp+38h] [rbp-48h] BYREF
  HSTRING string1; // [rsp+40h] [rbp-40h] BYREF
  HSTRING v30; // [rsp+48h] [rbp-38h] BYREF
  HSTRING string; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  HSTRING string2; // [rsp+70h] [rbp-10h]

  string = 0;
  v30 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v27,
    "CreateInprocExtensionInfoFromMediaExtensionMap",
    983);
  ExtensionInfoFromMediaExtensionMap = CreateExtensionInfoFromMediaExtensionMap(a1, a2, a3);
  if ( ExtensionInfoFromMediaExtensionMap < 0 )
  {
    v7 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v7 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != ExtensionInfoFromMediaExtensionMap )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CreateInprocExtensionInfoFromMediaExtensionMap",
          983,
          ExtensionInfoFromMediaExtensionMap);
    }
    if ( g_wppLevels )
    {
      v9 = 130;
LABEL_9:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
        0,
        ExtensionInfoFromMediaExtensionMap);
      goto LABEL_60;
    }
    goto LABEL_60;
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
      v10 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v11;
        if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
        {
          v10 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v10 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v10 + 8) )
      {
        v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
        if ( *((_DWORD *)v12 + 499) != ExtensionInfoFromMediaExtensionMap )
          CallStackContext::TraceFailure(
            v12,
            "CreateInprocExtensionInfoFromMediaExtensionMap",
            992,
            ExtensionInfoFromMediaExtensionMap);
      }
      if ( !g_wppLevels )
        goto LABEL_23;
      v13 = 131;
LABEL_22:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
        0,
        ExtensionInfoFromMediaExtensionMap);
LABEL_23:
      WindowsDeleteString(newString);
      newString = 0;
      WindowsDeleteString(string1);
      goto LABEL_60;
    }
    WindowsDeleteString(newString);
    newString = 0;
    string2 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"\\", 2u, 1u);
    ExtensionInfoFromMediaExtensionMap = WindowsConcatString(string1, string2, &newString);
    if ( ExtensionInfoFromMediaExtensionMap < 0 )
    {
      v14 = (__int64 *)CallStackTracing::s_wpInstance;
      string2 = 0;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)v16 + 499) != ExtensionInfoFromMediaExtensionMap )
          CallStackContext::TraceFailure(
            v16,
            "CreateInprocExtensionInfoFromMediaExtensionMap",
            993,
            ExtensionInfoFromMediaExtensionMap);
      }
      if ( !g_wppLevels )
        goto LABEL_23;
      v13 = 132;
      goto LABEL_22;
    }
    WindowsDeleteString(*(HSTRING *)(a3 + 56));
    v17 = string;
    v18 = newString;
    *(_QWORD *)(a3 + 56) = 0;
    ExtensionInfoFromMediaExtensionMap = WindowsConcatString(v18, v17, (HSTRING *)(a3 + 56));
    if ( ExtensionInfoFromMediaExtensionMap < 0 )
    {
      v19 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
        {
          v19 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
        if ( *((_DWORD *)v21 + 499) != ExtensionInfoFromMediaExtensionMap )
          CallStackContext::TraceFailure(
            v21,
            "CreateInprocExtensionInfoFromMediaExtensionMap",
            994,
            ExtensionInfoFromMediaExtensionMap);
      }
      if ( !g_wppLevels )
        goto LABEL_23;
      v13 = 133;
      goto LABEL_22;
    }
    WindowsDeleteString(*(HSTRING *)(a3 + 48));
    *(_QWORD *)(a3 + 48) = 0;
    ExtensionInfoFromMediaExtensionMap = CreateStringFromMap(a2, L"@ActivatableClassId", a3 + 48);
    WindowsDeleteString(newString);
    newString = 0;
    WindowsDeleteString(string1);
    string1 = 0;
    if ( ExtensionInfoFromMediaExtensionMap >= 0 )
      goto LABEL_58;
  }
  if ( !*(_BYTE *)(a3 + 33) )
  {
LABEL_58:
    v25 = v30;
    ExtensionInfoFromMediaExtensionMap = 0;
    *(_DWORD *)(a3 + 40) = 0;
    WindowsDeleteString(v25);
    v30 = 0;
    if ( (int)CreateStringFromMap(a2, L"@ProcessorArchitecture", &v30) >= 0 )
      *(_DWORD *)(a3 + 40) = CreateExtensionArchitectureFromString(v30);
    goto LABEL_60;
  }
  v22 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
    CallStackTracing::s_wpInstance = v23;
    if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
    {
      v22 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v22 = &qword_180153440;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
    }
  }
  if ( *((_BYTE *)v22 + 8) )
  {
    v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
    if ( *((_DWORD *)v24 + 499) != ExtensionInfoFromMediaExtensionMap )
      CallStackContext::TraceFailure(
        v24,
        "CreateInprocExtensionInfoFromMediaExtensionMap",
        1001,
        ExtensionInfoFromMediaExtensionMap);
  }
  if ( g_wppLevels )
  {
    v9 = 134;
    goto LABEL_9;
  }
LABEL_60:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v27);
  WindowsDeleteString(v30);
  v30 = 0;
  WindowsDeleteString(string);
  return (unsigned int)ExtensionInfoFromMediaExtensionMap;
}

```

## disassembly

```asm
0x1800347d0  push    rbp
0x1800347d2  push    rbx
0x1800347d3  push    rsi
0x1800347d4  push    rdi
0x1800347d5  push    r12
0x1800347d7  push    r14
0x1800347d9  push    r15
0x1800347db  mov     rbp, rsp
0x1800347de  sub     rsp, 80h
0x1800347e5  mov     rax, cs:__security_cookie
0x1800347ec  xor     rax, rsp
0x1800347ef  mov     [rbp+var_8], rax
0x1800347f3  mov     rdi, r8
0x1800347f6  lea     r12, aCreateinprocex; "CreateInprocExtensionInfoFromMediaExten"...
0x1800347fd  mov     rsi, rdx
0x180034800  mov     r14, rcx
0x180034803  xor     r15d, r15d
0x180034806  lea     rcx, [rbp+var_50]; this
0x18003480a  mov     rdx, r12; char *
0x18003480d  mov     [rbp+string], r15
0x180034811  mov     r8d, 3D7h; int
0x180034817  mov     [rbp+var_38], r15
0x18003481b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180034820  mov     r8, rdi
0x180034823  mov     rdx, rsi
0x180034826  mov     rcx, r14
0x180034829  call    ?CreateExtensionInfoFromMediaExtensionMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@0AEAUExtensionInfo@@@Z; CreateExtensionInfoFromMediaExtensionMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ExtensionInfo &)
0x18003482e  mov     ebx, eax
0x180034830  test    eax, eax
0x180034832  jns     short loc_1800348A8
0x180034834  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003483b  test    rcx, rcx
0x18003483e  jnz     short loc_18003484C
0x180034840  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180034845  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003484c  cmp     [rcx+8], r15b
0x180034850  jz      short loc_180034873
0x180034852  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180034857  cmp     [rax+7CCh], ebx
0x18003485d  jz      short loc_180034873
0x18003485f  mov     r9d, ebx; int
0x180034862  mov     r8d, 3D7h; int
0x180034868  mov     rdx, r12; char *
0x18003486b  mov     rcx, rax; this
0x18003486e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180034873  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003487a  jb      loc_180034C67
0x180034880  mov     edx, 82h
0x180034885  mov     rcx, cs:WPP_GLOBAL_Control
0x18003488c  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x180034893  xor     r9d, r9d
0x180034896  mov     [rsp+80h+var_60], ebx
0x18003489a  mov     rcx, [rcx+10h]
0x18003489e  call    WPP_SF_qD
0x1800348a3  jmp     loc_180034C67
0x1800348a8  mov     rcx, [rbp+string]; string
0x1800348ac  call    cs:__imp_WindowsDeleteString
0x1800348b2  lea     r8, [rbp+string]
0x1800348b6  mov     [rbp+string], r15
0x1800348ba  lea     rdx, aPath; "@Path"
0x1800348c1  mov     rcx, rsi
0x1800348c4  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x1800348c9  mov     ebx, eax
0x1800348cb  test    eax, eax
0x1800348cd  js      loc_180034B96
0x1800348d3  xor     ecx, ecx; string
0x1800348d5  mov     [rbp+string1], r15
0x1800348d9  mov     [rbp+newString], r15
0x1800348dd  call    cs:__imp_WindowsDeleteString
0x1800348e3  lea     r8, [rbp+string1]
0x1800348e7  mov     [rbp+string1], r15
0x1800348eb  lea     rdx, aPackageinstall; "@PackageInstallLocation"
0x1800348f2  mov     rcx, r14
0x1800348f5  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x1800348fa  mov     ebx, eax
0x1800348fc  test    eax, eax
0x1800348fe  jns     loc_1800349C1
0x180034904  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003490b  test    rcx, rcx
0x18003490e  jnz     short loc_180034951
0x180034910  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180034916  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003491d  mov     rcx, rax
0x180034920  test    rax, rax
0x180034923  jz      short loc_180034943
0x180034925  mov     rax, [rax]
0x180034928  mov     edx, 7F0h
0x18003492d  mov     rax, [rax+8]
0x180034931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034936  test    eax, eax
0x180034938  jz      short loc_180034943
0x18003493a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180034941  jmp     short loc_180034951
0x180034943  lea     rcx, qword_180153440; this
0x18003494a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180034951  cmp     [rcx+8], r15b
0x180034955  jz      short loc_180034978
0x180034957  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003495c  cmp     [rax+7CCh], ebx
0x180034962  jz      short loc_180034978
0x180034964  mov     r9d, ebx; int
0x180034967  mov     r8d, 3E0h; int
0x18003496d  mov     rdx, r12; char *
0x180034970  mov     rcx, rax; this
0x180034973  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180034978  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003497f  jb      short loc_1800349A4
0x180034981  mov     edx, 83h
0x180034986  mov     rcx, cs:WPP_GLOBAL_Control
0x18003498d  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x180034994  xor     r9d, r9d
0x180034997  mov     [rsp+80h+var_60], ebx
0x18003499b  mov     rcx, [rcx+10h]
0x18003499f  call    WPP_SF_qD
0x1800349a4  mov     rcx, [rbp+newString]; string
0x1800349a8  call    cs:__imp_WindowsDeleteString
0x1800349ae  mov     rcx, [rbp+string1]; string
0x1800349b2  mov     [rbp+newString], r15
0x1800349b6  call    cs:__imp_WindowsDeleteString
0x1800349bc  jmp     loc_180034C67
0x1800349c1  mov     rcx, [rbp+newString]; string
0x1800349c5  call    cs:__imp_WindowsDeleteString
0x1800349cb  mov     r9d, 1; unsigned int
0x1800349d1  mov     [rbp+newString], r15
0x1800349d5  lea     rdx, asc_180145A78; "\\"
0x1800349dc  mov     [rbp+string2], r15
0x1800349e0  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800349e4  lea     r8d, [r9+1]; unsigned int
0x1800349e8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800349ed  mov     rdx, [rbp+string2]; string2
0x1800349f1  lea     r8, [rbp+newString]; newString
0x1800349f5  mov     rcx, [rbp+string1]; string1
0x1800349f9  call    cs:__imp_WindowsConcatString
0x1800349ff  mov     ebx, eax
0x180034a01  test    eax, eax
0x180034a03  jns     loc_180034A98
0x180034a09  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180034a10  mov     [rbp+string2], r15
0x180034a14  test    rcx, rcx
0x180034a17  jnz     short loc_180034A5A
0x180034a19  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180034a1f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180034a26  mov     rcx, rax
0x180034a29  test    rax, rax
0x180034a2c  jz      short loc_180034A4C
0x180034a2e  mov     rax, [rax]
0x180034a31  mov     edx, 7F0h
0x180034a36  mov     rax, [rax+8]
0x180034a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034a3f  test    eax, eax
0x180034a41  jz      short loc_180034A4C
0x180034a43  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180034a4a  jmp     short loc_180034A5A
0x180034a4c  lea     rcx, qword_180153440; this
0x180034a53  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180034a5a  cmp     [rcx+8], r15b
0x180034a5e  jz      short loc_180034A81
0x180034a60  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180034a65  cmp     [rax+7CCh], ebx
0x180034a6b  jz      short loc_180034A81
0x180034a6d  mov     r9d, ebx; int
0x180034a70  mov     r8d, 3E1h; int
0x180034a76  mov     rdx, r12; char *
0x180034a79  mov     rcx, rax; this
0x180034a7c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180034a81  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180034a88  jb      loc_1800349A4
0x180034a8e  mov     edx, 84h
0x180034a93  jmp     loc_180034986
0x180034a98  lea     rbx, [rdi+38h]
0x180034a9c  mov     rcx, [rbx]; string
0x180034a9f  call    cs:__imp_WindowsDeleteString
0x180034aa5  mov     rdx, [rbp+string]; string2
0x180034aa9  mov     r8, rbx; newString
0x180034aac  mov     rcx, [rbp+newString]; string1
0x180034ab0  mov     [rbx], r15
0x180034ab3  call    cs:__imp_WindowsConcatString
0x180034ab9  mov     ebx, eax
0x180034abb  test    eax, eax
0x180034abd  jns     loc_180034B4E
0x180034ac3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180034aca  test    rcx, rcx
0x180034acd  jnz     short loc_180034B10
0x180034acf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180034ad5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180034adc  mov     rcx, rax
0x180034adf  test    rax, rax
0x180034ae2  jz      short loc_180034B02
0x180034ae4  mov     rax, [rax]
0x180034ae7  mov     edx, 7F0h
0x180034aec  mov     rax, [rax+8]
0x180034af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034af5  test    eax, eax
0x180034af7  jz      short loc_180034B02
0x180034af9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180034b00  jmp     short loc_180034B10
0x180034b02  lea     rcx, qword_180153440; this
0x180034b09  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180034b10  cmp     [rcx+8], r15b
0x180034b14  jz      short loc_180034B37
0x180034b16  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180034b1b  cmp     [rax+7CCh], ebx
0x180034b21  jz      short loc_180034B37
0x180034b23  mov     r9d, ebx; int
0x180034b26  mov     r8d, 3E2h; int
0x180034b2c  mov     rdx, r12; char *
0x180034b2f  mov     rcx, rax; this
0x180034b32  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180034b37  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180034b3e  jb      loc_1800349A4
0x180034b44  mov     edx, 85h
0x180034b49  jmp     loc_180034986
0x180034b4e  lea     rbx, [rdi+30h]
0x180034b52  mov     rcx, [rbx]; string
0x180034b55  call    cs:__imp_WindowsDeleteString
0x180034b5b  mov     r8, rbx
0x180034b5e  mov     [rbx], r15
0x180034b61  lea     rdx, aActivatablecla; "@ActivatableClassId"
0x180034b68  mov     rcx, rsi
0x180034b6b  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x180034b70  mov     rcx, [rbp+newString]; string
0x180034b74  mov     ebx, eax
0x180034b76  call    cs:__imp_WindowsDeleteString
0x180034b7c  mov     rcx, [rbp+string1]; string
0x180034b80  mov     [rbp+newString], r15
0x180034b84  call    cs:__imp_WindowsDeleteString
0x180034b8a  mov     [rbp+string1], r15
0x180034b8e  test    ebx, ebx
0x180034b90  jns     loc_180034C2F
0x180034b96  cmp     [rdi+21h], r15b
0x180034b9a  jz      loc_180034C2F
0x180034ba0  test    ebx, ebx
0x180034ba2  jns     loc_180034C2F
0x180034ba8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180034baf  test    rcx, rcx
0x180034bb2  jnz     short loc_180034BF5
0x180034bb4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180034bba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180034bc1  mov     rcx, rax
0x180034bc4  test    rax, rax
0x180034bc7  jz      short loc_180034BE7
0x180034bc9  mov     rax, [rax]
0x180034bcc  mov     edx, 7F0h
0x180034bd1  mov     rax, [rax+8]
0x180034bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034bda  test    eax, eax
0x180034bdc  jz      short loc_180034BE7
0x180034bde  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180034be5  jmp     short loc_180034BF5
0x180034be7  lea     rcx, qword_180153440; this
0x180034bee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180034bf5  cmp     [rcx+8], r15b
0x180034bf9  jz      short loc_180034C1C
0x180034bfb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180034c00  cmp     [rax+7CCh], ebx
0x180034c06  jz      short loc_180034C1C
0x180034c08  mov     r9d, ebx; int
0x180034c0b  mov     r8d, 3E9h; int
0x180034c11  mov     rdx, r12; char *
0x180034c14  mov     rcx, rax; this
0x180034c17  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180034c1c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180034c23  jb      short loc_180034C67
0x180034c25  mov     edx, 86h
0x180034c2a  jmp     loc_180034885
0x180034c2f  mov     rcx, [rbp+var_38]; string
0x180034c33  mov     ebx, r15d
0x180034c36  mov     [rdi+28h], r15d
0x180034c3a  call    cs:__imp_WindowsDeleteString
0x180034c40  lea     r8, [rbp+var_38]
0x180034c44  mov     [rbp+var_38], r15
0x180034c48  lea     rdx, aProcessorarchi; "@ProcessorArchitecture"
0x180034c4f  mov     rcx, rsi
0x180034c52  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x180034c57  test    eax, eax
0x180034c59  js      short loc_180034C67
0x180034c5b  mov     rcx, [rbp+var_38]
0x180034c5f  call    ?CreateExtensionArchitectureFromString@@YA?AW4MediaExtensionArchitecture@@PEAUHSTRING__@@@Z; CreateExtensionArchitectureFromString(HSTRING__ *)
0x180034c64  mov     [rdi+28h], eax
0x180034c67  lea     rcx, [rbp+var_50]; this
0x180034c6b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180034c70  mov     rcx, [rbp+var_38]; string
0x180034c74  call    cs:__imp_WindowsDeleteString
0x180034c7a  mov     rcx, [rbp+string]; string
0x180034c7e  mov     [rbp+var_38], r15
0x180034c82  call    cs:__imp_WindowsDeleteString
0x180034c88  mov     eax, ebx
0x180034c8a  mov     rcx, [rbp+var_8]
0x180034c8e  xor     rcx, rsp; StackCookie
0x180034c91  call    __security_check_cookie
0x180034c96  add     rsp, 80h
0x180034c9d  pop     r15
0x180034c9f  pop     r14
0x180034ca1  pop     r12
0x180034ca3  pop     rdi
0x180034ca4  pop     rsi
0x180034ca5  pop     rbx
0x180034ca6  pop     rbp
0x180034ca7  retn
```
