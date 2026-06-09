# CreateInprocExtensionInfoFromMediaExtensionMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,InprocExtensionInfo &)

- ea: `0x18007a0e4`
- end: `0x18007a668`
- name: `?CreateInprocExtensionInfoFromMediaExtensionMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@0AEAUInprocExtensionInfo@@@Z`
- size: `1412`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007a670`

## callees

- `0x180002400`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x18003dea8`
- `0x1800744d8`
- `0x18007965c`
- `0x180079a58`
- `0x18007a0e4`
- `0x18007ab98`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18007a370`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18007a43c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18007a370`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18007a43c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a1ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a236`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a30d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a321`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a336`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a422`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a4ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a511`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a525`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a5e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a627`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a63b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a1ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a236`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a30d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a321`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a336`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a422`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a4ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a511`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a525`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a5e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a627`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a63b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a158`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a26f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a396`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a45e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a55b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a158`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a26f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a396`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a45e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a55b`

## string_xrefs

- `0x18007a24a`: `@PackageInstallLocation`
- `0x18007a213`: `@Path`
- `0x18007a10a`: `CreateInprocExtensionInfoFromMediaExtensionMap`
- `0x18007a4fc`: `@ActivatableClassId`

## pseudocode

```c
__int64 __fastcall CreateInprocExtensionInfoFromMediaExtensionMap(__int64 a1, __int64 a2, __int64 a3)
{
  HRESULT ExtensionInfoFromMediaExtensionMap; // ebx
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rdx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  HSTRING v18; // rdx
  HSTRING v19; // rcx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  HSTRING v26; // rcx
  _BYTE v28[8]; // [rsp+30h] [rbp-50h] BYREF
  HSTRING newString; // [rsp+38h] [rbp-48h] BYREF
  HSTRING string1; // [rsp+40h] [rbp-40h] BYREF
  HSTRING v31; // [rsp+48h] [rbp-38h] BYREF
  HSTRING string; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  HSTRING string2; // [rsp+70h] [rbp-10h]

  string = 0;
  v31 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v28,
    "CreateInprocExtensionInfoFromMediaExtensionMap",
    983);
  ExtensionInfoFromMediaExtensionMap = CreateExtensionInfoFromMediaExtensionMap(a1, a2, a3);
  if ( ExtensionInfoFromMediaExtensionMap < 0 )
  {
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != ExtensionInfoFromMediaExtensionMap )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CreateInprocExtensionInfoFromMediaExtensionMap",
          983,
          ExtensionInfoFromMediaExtensionMap);
    }
    if ( g_wppLevels )
    {
      v10 = 130;
LABEL_12:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
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
      v11 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v11 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v13 + 499) != ExtensionInfoFromMediaExtensionMap )
          CallStackContext::TraceFailure(
            v13,
            "CreateInprocExtensionInfoFromMediaExtensionMap",
            992,
            ExtensionInfoFromMediaExtensionMap);
      }
      if ( !g_wppLevels )
        goto LABEL_26;
      v14 = 131;
LABEL_25:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
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
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
      string2 = 0;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( *((_DWORD *)v17 + 499) != ExtensionInfoFromMediaExtensionMap )
          CallStackContext::TraceFailure(
            v17,
            "CreateInprocExtensionInfoFromMediaExtensionMap",
            993,
            ExtensionInfoFromMediaExtensionMap);
      }
      if ( !g_wppLevels )
        goto LABEL_26;
      v14 = 132;
      goto LABEL_25;
    }
    WindowsDeleteString(*(HSTRING *)(a3 + 56));
    v18 = string;
    v19 = newString;
    *(_QWORD *)(a3 + 56) = 0;
    ExtensionInfoFromMediaExtensionMap = WindowsConcatString(v19, v18, (HSTRING *)(a3 + 56));
    if ( ExtensionInfoFromMediaExtensionMap < 0 )
    {
      v20 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)v22 + 499) != ExtensionInfoFromMediaExtensionMap )
          CallStackContext::TraceFailure(
            v22,
            "CreateInprocExtensionInfoFromMediaExtensionMap",
            994,
            ExtensionInfoFromMediaExtensionMap);
      }
      if ( !g_wppLevels )
        goto LABEL_26;
      v14 = 133;
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
    v26 = v31;
    ExtensionInfoFromMediaExtensionMap = 0;
    *(_DWORD *)(a3 + 40) = 0;
    WindowsDeleteString(v26);
    v31 = 0;
    if ( (int)CreateStringFromMap(a2, L"@ProcessorArchitecture", &v31) >= 0 )
      *(_DWORD *)(a3 + 40) = CreateExtensionArchitectureFromString(v31);
    goto LABEL_63;
  }
  v23 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
    CallStackTracing::s_wpInstance = v24;
    if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
    {
      v23 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v23 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  if ( *((_BYTE *)v23 + 8) )
  {
    v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
    if ( *((_DWORD *)v25 + 499) != ExtensionInfoFromMediaExtensionMap )
      CallStackContext::TraceFailure(
        v25,
        "CreateInprocExtensionInfoFromMediaExtensionMap",
        1001,
        ExtensionInfoFromMediaExtensionMap);
  }
  if ( g_wppLevels )
  {
    v10 = 134;
    goto LABEL_12;
  }
LABEL_63:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v28);
  WindowsDeleteString(v31);
  v31 = 0;
  WindowsDeleteString(string);
  return (unsigned int)ExtensionInfoFromMediaExtensionMap;
}

```

## disassembly

```asm
0x18007a0e4  push    rbp
0x18007a0e6  push    rbx
0x18007a0e7  push    rsi
0x18007a0e8  push    rdi
0x18007a0e9  push    r12
0x18007a0eb  push    r14
0x18007a0ed  push    r15
0x18007a0ef  mov     rbp, rsp
0x18007a0f2  sub     rsp, 80h
0x18007a0f9  mov     rax, cs:__security_cookie
0x18007a100  xor     rax, rsp
0x18007a103  mov     [rbp+var_8], rax
0x18007a107  mov     rdi, r8
0x18007a10a  lea     r12, aCreateinprocex; "CreateInprocExtensionInfoFromMediaExten"...
0x18007a111  mov     rsi, rdx
0x18007a114  mov     r14, rcx
0x18007a117  xor     r15d, r15d
0x18007a11a  lea     rcx, [rbp+var_50]; this
0x18007a11e  mov     rdx, r12; char *
0x18007a121  mov     [rbp+string], r15
0x18007a125  mov     r8d, 3D7h; int
0x18007a12b  mov     [rbp+var_38], r15
0x18007a12f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007a134  mov     r8, rdi
0x18007a137  mov     rdx, rsi
0x18007a13a  mov     rcx, r14
0x18007a13d  call    ?CreateExtensionInfoFromMediaExtensionMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@0AEAUExtensionInfo@@@Z; CreateExtensionInfoFromMediaExtensionMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ExtensionInfo &)
0x18007a142  mov     ebx, eax
0x18007a144  test    eax, eax
0x18007a146  jns     loc_18007A1FB
0x18007a14c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a153  test    rcx, rcx
0x18007a156  jnz     short loc_18007A19F
0x18007a158  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007a15f  nop     dword ptr [rax+rax+00h]
0x18007a164  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a16b  mov     rcx, rax
0x18007a16e  test    rax, rax
0x18007a171  jz      short loc_18007A191
0x18007a173  mov     rax, [rax]
0x18007a176  mov     edx, 7F0h
0x18007a17b  mov     rax, [rax+8]
0x18007a17f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a184  test    eax, eax
0x18007a186  jz      short loc_18007A191
0x18007a188  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a18f  jmp     short loc_18007A19F
0x18007a191  lea     rcx, qword_1800DBF70; this
0x18007a198  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a19f  cmp     [rcx+8], r15b
0x18007a1a3  jz      short loc_18007A1C6
0x18007a1a5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007a1aa  cmp     [rax+7CCh], ebx
0x18007a1b0  jz      short loc_18007A1C6
0x18007a1b2  mov     r9d, ebx; int
0x18007a1b5  mov     r8d, 3D7h; int
0x18007a1bb  mov     rdx, r12; char *
0x18007a1be  mov     rcx, rax; this
0x18007a1c1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007a1c6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007a1cd  jb      loc_18007A61A
0x18007a1d3  mov     edx, 82h
0x18007a1d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a1df  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x18007a1e6  xor     r9d, r9d
0x18007a1e9  mov     [rsp+80h+var_60], ebx
0x18007a1ed  mov     rcx, [rcx+10h]
0x18007a1f1  call    WPP_SF_qD
0x18007a1f6  jmp     loc_18007A61A
0x18007a1fb  mov     rcx, [rbp+string]; string
0x18007a1ff  call    cs:__imp_WindowsDeleteString
0x18007a206  nop     dword ptr [rax+rax+00h]
0x18007a20b  lea     r8, [rbp+string]
0x18007a20f  mov     [rbp+string], r15
0x18007a213  lea     rdx, aPath; "@Path"
0x18007a21a  mov     rcx, rsi
0x18007a21d  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x18007a222  mov     ebx, eax
0x18007a224  test    eax, eax
0x18007a226  js      loc_18007A53D
0x18007a22c  xor     ecx, ecx; string
0x18007a22e  mov     [rbp+string1], r15
0x18007a232  mov     [rbp+newString], r15
0x18007a236  call    cs:__imp_WindowsDeleteString
0x18007a23d  nop     dword ptr [rax+rax+00h]
0x18007a242  lea     r8, [rbp+string1]
0x18007a246  mov     [rbp+string1], r15
0x18007a24a  lea     rdx, aPackageinstall; "@PackageInstallLocation"
0x18007a251  mov     rcx, r14
0x18007a254  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x18007a259  mov     ebx, eax
0x18007a25b  test    eax, eax
0x18007a25d  jns     loc_18007A332
0x18007a263  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a26a  test    rcx, rcx
0x18007a26d  jnz     short loc_18007A2B6
0x18007a26f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007a276  nop     dword ptr [rax+rax+00h]
0x18007a27b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a282  mov     rcx, rax
0x18007a285  test    rax, rax
0x18007a288  jz      short loc_18007A2A8
0x18007a28a  mov     rax, [rax]
0x18007a28d  mov     edx, 7F0h
0x18007a292  mov     rax, [rax+8]
0x18007a296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a29b  test    eax, eax
0x18007a29d  jz      short loc_18007A2A8
0x18007a29f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a2a6  jmp     short loc_18007A2B6
0x18007a2a8  lea     rcx, qword_1800DBF70; this
0x18007a2af  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a2b6  cmp     [rcx+8], r15b
0x18007a2ba  jz      short loc_18007A2DD
0x18007a2bc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007a2c1  cmp     [rax+7CCh], ebx
0x18007a2c7  jz      short loc_18007A2DD
0x18007a2c9  mov     r9d, ebx; int
0x18007a2cc  mov     r8d, 3E0h; int
0x18007a2d2  mov     rdx, r12; char *
0x18007a2d5  mov     rcx, rax; this
0x18007a2d8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007a2dd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007a2e4  jb      short loc_18007A309
0x18007a2e6  mov     edx, 83h
0x18007a2eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a2f2  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x18007a2f9  xor     r9d, r9d
0x18007a2fc  mov     [rsp+80h+var_60], ebx
0x18007a300  mov     rcx, [rcx+10h]
0x18007a304  call    WPP_SF_qD
0x18007a309  mov     rcx, [rbp+newString]; string
0x18007a30d  call    cs:__imp_WindowsDeleteString
0x18007a314  nop     dword ptr [rax+rax+00h]
0x18007a319  mov     rcx, [rbp+string1]; string
0x18007a31d  mov     [rbp+newString], r15
0x18007a321  call    cs:__imp_WindowsDeleteString
0x18007a328  nop     dword ptr [rax+rax+00h]
0x18007a32d  jmp     loc_18007A61A
0x18007a332  mov     rcx, [rbp+newString]; string
0x18007a336  call    cs:__imp_WindowsDeleteString
0x18007a33d  nop     dword ptr [rax+rax+00h]
0x18007a342  mov     r9d, 1; unsigned int
0x18007a348  mov     [rbp+newString], r15
0x18007a34c  lea     rdx, asc_1800C67F0; "\\"
0x18007a353  mov     [rbp+string2], r15
0x18007a357  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18007a35b  lea     r8d, [r9+1]; unsigned int
0x18007a35f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007a364  mov     rdx, [rbp+string2]; string2
0x18007a368  lea     r8, [rbp+newString]; newString
0x18007a36c  mov     rcx, [rbp+string1]; string1
0x18007a370  call    cs:__imp_WindowsConcatString
0x18007a377  nop     dword ptr [rax+rax+00h]
0x18007a37c  mov     ebx, eax
0x18007a37e  test    eax, eax
0x18007a380  jns     loc_18007A41B
0x18007a386  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a38d  mov     [rbp+string2], r15
0x18007a391  test    rcx, rcx
0x18007a394  jnz     short loc_18007A3DD
0x18007a396  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007a39d  nop     dword ptr [rax+rax+00h]
0x18007a3a2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a3a9  mov     rcx, rax
0x18007a3ac  test    rax, rax
0x18007a3af  jz      short loc_18007A3CF
0x18007a3b1  mov     rax, [rax]
0x18007a3b4  mov     edx, 7F0h
0x18007a3b9  mov     rax, [rax+8]
0x18007a3bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a3c2  test    eax, eax
0x18007a3c4  jz      short loc_18007A3CF
0x18007a3c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a3cd  jmp     short loc_18007A3DD
0x18007a3cf  lea     rcx, qword_1800DBF70; this
0x18007a3d6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a3dd  cmp     [rcx+8], r15b
0x18007a3e1  jz      short loc_18007A404
0x18007a3e3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007a3e8  cmp     [rax+7CCh], ebx
0x18007a3ee  jz      short loc_18007A404
0x18007a3f0  mov     r9d, ebx; int
0x18007a3f3  mov     r8d, 3E1h; int
0x18007a3f9  mov     rdx, r12; char *
0x18007a3fc  mov     rcx, rax; this
0x18007a3ff  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007a404  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007a40b  jb      loc_18007A309
0x18007a411  mov     edx, 84h
0x18007a416  jmp     loc_18007A2EB
0x18007a41b  lea     rbx, [rdi+38h]
0x18007a41f  mov     rcx, [rbx]; string
0x18007a422  call    cs:__imp_WindowsDeleteString
0x18007a429  nop     dword ptr [rax+rax+00h]
0x18007a42e  mov     rdx, [rbp+string]; string2
0x18007a432  mov     r8, rbx; newString
0x18007a435  mov     rcx, [rbp+newString]; string1
0x18007a439  mov     [rbx], r15
0x18007a43c  call    cs:__imp_WindowsConcatString
0x18007a443  nop     dword ptr [rax+rax+00h]
0x18007a448  mov     ebx, eax
0x18007a44a  test    eax, eax
0x18007a44c  jns     loc_18007A4E3
0x18007a452  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a459  test    rcx, rcx
0x18007a45c  jnz     short loc_18007A4A5
0x18007a45e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007a465  nop     dword ptr [rax+rax+00h]
0x18007a46a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a471  mov     rcx, rax
0x18007a474  test    rax, rax
0x18007a477  jz      short loc_18007A497
0x18007a479  mov     rax, [rax]
0x18007a47c  mov     edx, 7F0h
0x18007a481  mov     rax, [rax+8]
0x18007a485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a48a  test    eax, eax
0x18007a48c  jz      short loc_18007A497
0x18007a48e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a495  jmp     short loc_18007A4A5
0x18007a497  lea     rcx, qword_1800DBF70; this
0x18007a49e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a4a5  cmp     [rcx+8], r15b
0x18007a4a9  jz      short loc_18007A4CC
0x18007a4ab  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007a4b0  cmp     [rax+7CCh], ebx
0x18007a4b6  jz      short loc_18007A4CC
0x18007a4b8  mov     r9d, ebx; int
0x18007a4bb  mov     r8d, 3E2h; int
0x18007a4c1  mov     rdx, r12; char *
0x18007a4c4  mov     rcx, rax; this
0x18007a4c7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007a4cc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007a4d3  jb      loc_18007A309
0x18007a4d9  mov     edx, 85h
0x18007a4de  jmp     loc_18007A2EB
0x18007a4e3  lea     rbx, [rdi+30h]
0x18007a4e7  mov     rcx, [rbx]; string
0x18007a4ea  call    cs:__imp_WindowsDeleteString
0x18007a4f1  nop     dword ptr [rax+rax+00h]
0x18007a4f6  mov     r8, rbx
0x18007a4f9  mov     [rbx], r15
0x18007a4fc  lea     rdx, aActivatablecla; "@ActivatableClassId"
0x18007a503  mov     rcx, rsi
0x18007a506  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x18007a50b  mov     rcx, [rbp+newString]; string
0x18007a50f  mov     ebx, eax
0x18007a511  call    cs:__imp_WindowsDeleteString
0x18007a518  nop     dword ptr [rax+rax+00h]
0x18007a51d  mov     rcx, [rbp+string1]; string
0x18007a521  mov     [rbp+newString], r15
0x18007a525  call    cs:__imp_WindowsDeleteString
0x18007a52c  nop     dword ptr [rax+rax+00h]
0x18007a531  mov     [rbp+string1], r15
0x18007a535  test    ebx, ebx
0x18007a537  jns     loc_18007A5DC
0x18007a53d  cmp     [rdi+21h], r15b
0x18007a541  jz      loc_18007A5DC
0x18007a547  test    ebx, ebx
0x18007a549  jns     loc_18007A5DC
0x18007a54f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a556  test    rcx, rcx
0x18007a559  jnz     short loc_18007A5A2
0x18007a55b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007a562  nop     dword ptr [rax+rax+00h]
0x18007a567  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a56e  mov     rcx, rax
0x18007a571  test    rax, rax
0x18007a574  jz      short loc_18007A594
0x18007a576  mov     rax, [rax]
0x18007a579  mov     edx, 7F0h
0x18007a57e  mov     rax, [rax+8]
0x18007a582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a587  test    eax, eax
0x18007a589  jz      short loc_18007A594
0x18007a58b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a592  jmp     short loc_18007A5A2
0x18007a594  lea     rcx, qword_1800DBF70; this
0x18007a59b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a5a2  cmp     [rcx+8], r15b
0x18007a5a6  jz      short loc_18007A5C9
0x18007a5a8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007a5ad  cmp     [rax+7CCh], ebx
0x18007a5b3  jz      short loc_18007A5C9
0x18007a5b5  mov     r9d, ebx; int
0x18007a5b8  mov     r8d, 3E9h; int
0x18007a5be  mov     rdx, r12; char *
0x18007a5c1  mov     rcx, rax; this
0x18007a5c4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007a5c9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007a5d0  jb      short loc_18007A61A
0x18007a5d2  mov     edx, 86h
0x18007a5d7  jmp     loc_18007A1D8
0x18007a5dc  mov     rcx, [rbp+var_38]; string
0x18007a5e0  mov     ebx, r15d
0x18007a5e3  mov     [rdi+28h], r15d
0x18007a5e7  call    cs:__imp_WindowsDeleteString
0x18007a5ee  nop     dword ptr [rax+rax+00h]
0x18007a5f3  lea     r8, [rbp+var_38]
  ... truncated ...
```
