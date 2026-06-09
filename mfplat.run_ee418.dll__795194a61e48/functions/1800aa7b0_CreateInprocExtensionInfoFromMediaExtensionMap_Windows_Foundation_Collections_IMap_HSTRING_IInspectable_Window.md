# CreateInprocExtensionInfoFromMediaExtensionMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,InprocExtensionInfo &)

- ea: `0x1800aa7b0`
- end: `0x1800aacc1`
- name: `?CreateInprocExtensionInfoFromMediaExtensionMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@0AEAUInprocExtensionInfo@@@Z`
- size: `1297`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001dab0`
- `0x1800aa698`

## callees

- `0x18001fda0`
- `0x180020b80`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18003eef4`
- `0x180094910`
- `0x1800aa7b0`
- `0x1801200d0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa8c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa8f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa9c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa9cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa9de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aaab8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aab6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aab8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aab9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aac53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aac8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aac9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa8c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa8f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa9c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa9cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa9de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aaab8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aab6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aab8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aab9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aac53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aac8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aac9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1800aaa12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1800aaacc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1800aaa12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1800aaacc`

## string_xrefs

- `0x1800aa7d6`: `CreateInprocExtensionInfoFromMediaExtensionMap`
- `0x1800aa904`: `@PackageInstallLocation`
- `0x1800aa8d3`: `@Path`
- `0x1800aab7a`: `@ActivatableClassId`

## pseudocode

```c
__int64 __fastcall CreateInprocExtensionInfoFromMediaExtensionMap(__int64 a1, __int64 a2, __int64 a3)
{
  HRESULT ExtensionInfoFromMediaExtensionMap; // ebx
  CallStackTracing *v7; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  CallStackTracing *v10; // rcx
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  CallStackTracing *v13; // rcx
  struct CallStackContext *v14; // rax
  HSTRING v15; // rdx
  HSTRING v16; // rcx
  CallStackTracing *v17; // rcx
  struct CallStackContext *v18; // rax
  CallStackTracing *v19; // rcx
  struct CallStackContext *v20; // rax
  HSTRING v21; // rcx
  CallStackScopeTrace v23; // [rsp+30h] [rbp-50h] BYREF
  HSTRING newString; // [rsp+38h] [rbp-48h] BYREF
  HSTRING string1; // [rsp+40h] [rbp-40h] BYREF
  HSTRING v26; // [rsp+48h] [rbp-38h] BYREF
  HSTRING string; // [rsp+50h] [rbp-30h] BYREF
  Microsoft::WRL::Wrappers::HStringReference v28; // [rsp+58h] [rbp-28h] BYREF

  string = 0;
  v26 = 0;
  CallStackScopeTrace::CallStackScopeTrace(&v23, "CreateInprocExtensionInfoFromMediaExtensionMap", 983);
  ExtensionInfoFromMediaExtensionMap = CreateExtensionInfoFromMediaExtensionMap(a1, a2, a3);
  if ( ExtensionInfoFromMediaExtensionMap < 0 )
  {
    v7 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v7 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v7->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v7);
      if ( ThreadRelativeContext->m_result != ExtensionInfoFromMediaExtensionMap )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CreateInprocExtensionInfoFromMediaExtensionMap",
          983,
          ExtensionInfoFromMediaExtensionMap);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v9 = 130;
LABEL_11:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        &WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
        0,
        ExtensionInfoFromMediaExtensionMap);
      goto LABEL_58;
    }
    goto LABEL_58;
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
        if ( v11->m_result != ExtensionInfoFromMediaExtensionMap )
          CallStackContext::TraceFailure(
            v11,
            "CreateInprocExtensionInfoFromMediaExtensionMap",
            992,
            ExtensionInfoFromMediaExtensionMap);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_24;
      v12 = 131;
LABEL_23:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        &WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
        0,
        ExtensionInfoFromMediaExtensionMap);
LABEL_24:
      WindowsDeleteString(newString);
      newString = 0;
      WindowsDeleteString(string1);
      goto LABEL_58;
    }
    WindowsDeleteString(newString);
    newString = 0;
    v28.hstr_ = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v28, L"\\", 2u, 1u);
    ExtensionInfoFromMediaExtensionMap = WindowsConcatString(string1, v28.hstr_, &newString);
    if ( ExtensionInfoFromMediaExtensionMap < 0 )
    {
      v13 = CallStackTracing::s_wpInstance;
      v28.hstr_ = 0;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v13 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v13 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v13->m_fEnabled )
      {
        v14 = CallStackTracing::GetThreadRelativeContext(v13);
        if ( v14->m_result != ExtensionInfoFromMediaExtensionMap )
          CallStackContext::TraceFailure(
            v14,
            "CreateInprocExtensionInfoFromMediaExtensionMap",
            993,
            ExtensionInfoFromMediaExtensionMap);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_24;
      v12 = 132;
      goto LABEL_23;
    }
    WindowsDeleteString(*(HSTRING *)(a3 + 56));
    v15 = string;
    v16 = newString;
    *(_QWORD *)(a3 + 56) = 0;
    ExtensionInfoFromMediaExtensionMap = WindowsConcatString(v16, v15, (HSTRING *)(a3 + 56));
    if ( ExtensionInfoFromMediaExtensionMap < 0 )
    {
      v17 = CallStackTracing::s_wpInstance;
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
        if ( v18->m_result != ExtensionInfoFromMediaExtensionMap )
          CallStackContext::TraceFailure(
            v18,
            "CreateInprocExtensionInfoFromMediaExtensionMap",
            994,
            ExtensionInfoFromMediaExtensionMap);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_24;
      v12 = 133;
      goto LABEL_23;
    }
    WindowsDeleteString(*(HSTRING *)(a3 + 48));
    *(_QWORD *)(a3 + 48) = 0;
    ExtensionInfoFromMediaExtensionMap = CreateStringFromMap(a2, L"@ActivatableClassId", a3 + 48);
    WindowsDeleteString(newString);
    newString = 0;
    WindowsDeleteString(string1);
    string1 = 0;
    if ( ExtensionInfoFromMediaExtensionMap >= 0 )
      goto LABEL_56;
  }
  if ( !*(_BYTE *)(a3 + 33) )
  {
LABEL_56:
    v21 = v26;
    ExtensionInfoFromMediaExtensionMap = 0;
    *(_DWORD *)(a3 + 40) = 0;
    WindowsDeleteString(v21);
    v26 = 0;
    if ( (int)CreateStringFromMap(a2, L"@ProcessorArchitecture", &v26) >= 0 )
      *(_DWORD *)(a3 + 40) = CreateExtensionArchitectureFromString(v26);
    goto LABEL_58;
  }
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
    if ( v20->m_result != ExtensionInfoFromMediaExtensionMap )
      CallStackContext::TraceFailure(
        v20,
        "CreateInprocExtensionInfoFromMediaExtensionMap",
        1001,
        ExtensionInfoFromMediaExtensionMap);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v9 = 134;
    goto LABEL_11;
  }
LABEL_58:
  CallStackScopeTrace::~CallStackScopeTrace(&v23);
  WindowsDeleteString(v26);
  v26 = 0;
  WindowsDeleteString(string);
  return (unsigned int)ExtensionInfoFromMediaExtensionMap;
}

```

## disassembly

```asm
0x1800aa7b0  push    rbp
0x1800aa7b2  push    rbx
0x1800aa7b3  push    rsi
0x1800aa7b4  push    rdi
0x1800aa7b5  push    r12
0x1800aa7b7  push    r14
0x1800aa7b9  push    r15
0x1800aa7bb  mov     rbp, rsp
0x1800aa7be  sub     rsp, 80h
0x1800aa7c5  mov     rax, cs:__security_cookie
0x1800aa7cc  xor     rax, rsp
0x1800aa7cf  mov     [rbp+var_8], rax
0x1800aa7d3  mov     rdi, r8
0x1800aa7d6  lea     r12, aCreateinprocex; "CreateInprocExtensionInfoFromMediaExten"...
0x1800aa7dd  mov     rsi, rdx
0x1800aa7e0  mov     r14, rcx
0x1800aa7e3  xor     r15d, r15d
0x1800aa7e6  lea     rcx, [rbp+var_50]; this
0x1800aa7ea  mov     rdx, r12; char *
0x1800aa7ed  mov     [rbp+string], r15
0x1800aa7f1  mov     r8d, 3D7h; int
0x1800aa7f7  mov     [rbp+var_38], r15
0x1800aa7fb  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800aa800  mov     r8, rdi
0x1800aa803  mov     rdx, rsi
0x1800aa806  mov     rcx, r14
0x1800aa809  call    ?CreateExtensionInfoFromMediaExtensionMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@0AEAUExtensionInfo@@@Z; CreateExtensionInfoFromMediaExtensionMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ExtensionInfo &)
0x1800aa80e  mov     ebx, eax
0x1800aa810  test    eax, eax
0x1800aa812  jns     loc_1800AA8C1
0x1800aa818  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aa81f  test    rcx, rcx
0x1800aa822  jnz     short loc_1800AA865
0x1800aa824  mov     rcx, cs:stru_1801FC290.__vftable
0x1800aa82b  lea     r8, stru_1801FC290
0x1800aa832  mov     edx, 7F0h
0x1800aa837  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aa83e  mov     rax, [rcx+8]
0x1800aa842  mov     rcx, r8
0x1800aa845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa84a  test    eax, eax
0x1800aa84c  jnz     short loc_1800AA85E
0x1800aa84e  lea     rcx, stru_1801F8A30
0x1800aa855  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aa85c  jmp     short loc_1800AA865
0x1800aa85e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800aa865  cmp     [rcx+8], r15b
0x1800aa869  jz      short loc_1800AA88C
0x1800aa86b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aa870  cmp     [rax+7CCh], ebx
0x1800aa876  jz      short loc_1800AA88C
0x1800aa878  mov     r9d, ebx; int
0x1800aa87b  mov     r8d, 3D7h; int
0x1800aa881  mov     rdx, r12; char *
0x1800aa884  mov     rcx, rax; this
0x1800aa887  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800aa88c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800aa893  jb      loc_1800AAC80
0x1800aa899  mov     edx, 82h
0x1800aa89e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa8a5  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x1800aa8ac  xor     r9d, r9d
0x1800aa8af  mov     [rsp+80h+var_60], ebx
0x1800aa8b3  mov     rcx, [rcx+10h]
0x1800aa8b7  call    WPP_SF_qD
0x1800aa8bc  jmp     loc_1800AAC80
0x1800aa8c1  mov     rcx, [rbp+string]; string
0x1800aa8c5  call    cs:__imp_WindowsDeleteString
0x1800aa8cb  lea     r8, [rbp+string]
0x1800aa8cf  mov     [rbp+string], r15
0x1800aa8d3  lea     rdx, aPath; "@Path"
0x1800aa8da  mov     rcx, rsi
0x1800aa8dd  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x1800aa8e2  mov     ebx, eax
0x1800aa8e4  test    eax, eax
0x1800aa8e6  js      loc_1800AABAF
0x1800aa8ec  xor     ecx, ecx; string
0x1800aa8ee  mov     [rbp+string1], r15
0x1800aa8f2  mov     [rbp+newString], r15
0x1800aa8f6  call    cs:__imp_WindowsDeleteString
0x1800aa8fc  lea     r8, [rbp+string1]
0x1800aa900  mov     [rbp+string1], r15
0x1800aa904  lea     rdx, aPackageinstall; "@PackageInstallLocation"
0x1800aa90b  mov     rcx, r14
0x1800aa90e  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x1800aa913  mov     ebx, eax
0x1800aa915  test    eax, eax
0x1800aa917  jns     loc_1800AA9DA
0x1800aa91d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aa924  test    rcx, rcx
0x1800aa927  jnz     short loc_1800AA96A
0x1800aa929  mov     rax, cs:stru_1801FC290.__vftable
0x1800aa930  lea     r8, stru_1801FC290
0x1800aa937  mov     edx, 7F0h
0x1800aa93c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aa943  mov     rcx, r8
0x1800aa946  mov     rax, [rax+8]
0x1800aa94a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa94f  test    eax, eax
0x1800aa951  jnz     short loc_1800AA963
0x1800aa953  lea     rcx, stru_1801F8A30
0x1800aa95a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aa961  jmp     short loc_1800AA96A
0x1800aa963  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800aa96a  cmp     [rcx+8], r15b
0x1800aa96e  jz      short loc_1800AA991
0x1800aa970  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aa975  cmp     [rax+7CCh], ebx
0x1800aa97b  jz      short loc_1800AA991
0x1800aa97d  mov     r9d, ebx; int
0x1800aa980  mov     r8d, 3E0h; int
0x1800aa986  mov     rdx, r12; char *
0x1800aa989  mov     rcx, rax; this
0x1800aa98c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800aa991  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800aa998  jb      short loc_1800AA9BD
0x1800aa99a  mov     edx, 83h
0x1800aa99f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa9a6  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x1800aa9ad  xor     r9d, r9d
0x1800aa9b0  mov     [rsp+80h+var_60], ebx
0x1800aa9b4  mov     rcx, [rcx+10h]
0x1800aa9b8  call    WPP_SF_qD
0x1800aa9bd  mov     rcx, [rbp+newString]; string
0x1800aa9c1  call    cs:__imp_WindowsDeleteString
0x1800aa9c7  mov     rcx, [rbp+string1]; string
0x1800aa9cb  mov     [rbp+newString], r15
0x1800aa9cf  call    cs:__imp_WindowsDeleteString
0x1800aa9d5  jmp     loc_1800AAC80
0x1800aa9da  mov     rcx, [rbp+newString]; string
0x1800aa9de  call    cs:__imp_WindowsDeleteString
0x1800aa9e4  mov     r9d, 1; unsigned int
0x1800aa9ea  mov     [rbp+newString], r15
0x1800aa9ee  lea     rdx, asc_1801D05D0; "\\"
0x1800aa9f5  mov     [rbp+var_28.hstr_], r15
0x1800aa9f9  lea     rcx, [rbp+var_28]; this
0x1800aa9fd  lea     r8d, [r9+1]; unsigned int
0x1800aaa01  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800aaa06  mov     rdx, [rbp+var_28.hstr_]; string2
0x1800aaa0a  lea     r8, [rbp+newString]; newString
0x1800aaa0e  mov     rcx, [rbp+string1]; string1
0x1800aaa12  call    cs:__imp_WindowsConcatString
0x1800aaa18  mov     ebx, eax
0x1800aaa1a  test    eax, eax
0x1800aaa1c  jns     loc_1800AAAB1
0x1800aaa22  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aaa29  mov     [rbp+var_28.hstr_], r15
0x1800aaa2d  test    rcx, rcx
0x1800aaa30  jnz     short loc_1800AAA73
0x1800aaa32  mov     rax, cs:stru_1801FC290.__vftable
0x1800aaa39  lea     r8, stru_1801FC290
0x1800aaa40  mov     edx, 7F0h
0x1800aaa45  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aaa4c  mov     rcx, r8
0x1800aaa4f  mov     rax, [rax+8]
0x1800aaa53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aaa58  test    eax, eax
0x1800aaa5a  jnz     short loc_1800AAA6C
0x1800aaa5c  lea     rcx, stru_1801F8A30
0x1800aaa63  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aaa6a  jmp     short loc_1800AAA73
0x1800aaa6c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800aaa73  cmp     [rcx+8], r15b
0x1800aaa77  jz      short loc_1800AAA9A
0x1800aaa79  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aaa7e  cmp     [rax+7CCh], ebx
0x1800aaa84  jz      short loc_1800AAA9A
0x1800aaa86  mov     r9d, ebx; int
0x1800aaa89  mov     r8d, 3E1h; int
0x1800aaa8f  mov     rdx, r12; char *
0x1800aaa92  mov     rcx, rax; this
0x1800aaa95  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800aaa9a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800aaaa1  jb      loc_1800AA9BD
0x1800aaaa7  mov     edx, 84h
0x1800aaaac  jmp     loc_1800AA99F
0x1800aaab1  lea     rbx, [rdi+38h]
0x1800aaab5  mov     rcx, [rbx]; string
0x1800aaab8  call    cs:__imp_WindowsDeleteString
0x1800aaabe  mov     rdx, [rbp+string]; string2
0x1800aaac2  mov     r8, rbx; newString
0x1800aaac5  mov     rcx, [rbp+newString]; string1
0x1800aaac9  mov     [rbx], r15
0x1800aaacc  call    cs:__imp_WindowsConcatString
0x1800aaad2  mov     ebx, eax
0x1800aaad4  test    eax, eax
0x1800aaad6  jns     loc_1800AAB67
0x1800aaadc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aaae3  test    rcx, rcx
0x1800aaae6  jnz     short loc_1800AAB29
0x1800aaae8  mov     rax, cs:stru_1801FC290.__vftable
0x1800aaaef  lea     r8, stru_1801FC290
0x1800aaaf6  mov     edx, 7F0h
0x1800aaafb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aab02  mov     rcx, r8
0x1800aab05  mov     rax, [rax+8]
0x1800aab09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aab0e  test    eax, eax
0x1800aab10  jnz     short loc_1800AAB22
0x1800aab12  lea     rcx, stru_1801F8A30
0x1800aab19  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aab20  jmp     short loc_1800AAB29
0x1800aab22  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800aab29  cmp     [rcx+8], r15b
0x1800aab2d  jz      short loc_1800AAB50
0x1800aab2f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aab34  cmp     [rax+7CCh], ebx
0x1800aab3a  jz      short loc_1800AAB50
0x1800aab3c  mov     r9d, ebx; int
0x1800aab3f  mov     r8d, 3E2h; int
0x1800aab45  mov     rdx, r12; char *
0x1800aab48  mov     rcx, rax; this
0x1800aab4b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800aab50  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800aab57  jb      loc_1800AA9BD
0x1800aab5d  mov     edx, 85h
0x1800aab62  jmp     loc_1800AA99F
0x1800aab67  lea     rbx, [rdi+30h]
0x1800aab6b  mov     rcx, [rbx]; string
0x1800aab6e  call    cs:__imp_WindowsDeleteString
0x1800aab74  mov     r8, rbx
0x1800aab77  mov     [rbx], r15
0x1800aab7a  lea     rdx, aActivatablecla; "@ActivatableClassId"
0x1800aab81  mov     rcx, rsi
0x1800aab84  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x1800aab89  mov     rcx, [rbp+newString]; string
0x1800aab8d  mov     ebx, eax
0x1800aab8f  call    cs:__imp_WindowsDeleteString
0x1800aab95  mov     rcx, [rbp+string1]; string
0x1800aab99  mov     [rbp+newString], r15
0x1800aab9d  call    cs:__imp_WindowsDeleteString
0x1800aaba3  mov     [rbp+string1], r15
0x1800aaba7  test    ebx, ebx
0x1800aaba9  jns     loc_1800AAC48
0x1800aabaf  cmp     [rdi+21h], r15b
0x1800aabb3  jz      loc_1800AAC48
0x1800aabb9  test    ebx, ebx
0x1800aabbb  jns     loc_1800AAC48
0x1800aabc1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aabc8  test    rcx, rcx
0x1800aabcb  jnz     short loc_1800AAC0E
0x1800aabcd  mov     rax, cs:stru_1801FC290.__vftable
0x1800aabd4  lea     r8, stru_1801FC290
0x1800aabdb  mov     edx, 7F0h
0x1800aabe0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aabe7  mov     rcx, r8
0x1800aabea  mov     rax, [rax+8]
0x1800aabee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aabf3  test    eax, eax
0x1800aabf5  jnz     short loc_1800AAC07
0x1800aabf7  lea     rcx, stru_1801F8A30
0x1800aabfe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aac05  jmp     short loc_1800AAC0E
0x1800aac07  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800aac0e  cmp     [rcx+8], r15b
0x1800aac12  jz      short loc_1800AAC35
0x1800aac14  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aac19  cmp     [rax+7CCh], ebx
0x1800aac1f  jz      short loc_1800AAC35
0x1800aac21  mov     r9d, ebx; int
0x1800aac24  mov     r8d, 3E9h; int
0x1800aac2a  mov     rdx, r12; char *
0x1800aac2d  mov     rcx, rax; this
0x1800aac30  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800aac35  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800aac3c  jb      short loc_1800AAC80
0x1800aac3e  mov     edx, 86h
0x1800aac43  jmp     loc_1800AA89E
0x1800aac48  mov     rcx, [rbp+var_38]; string
0x1800aac4c  mov     ebx, r15d
0x1800aac4f  mov     [rdi+28h], r15d
0x1800aac53  call    cs:__imp_WindowsDeleteString
0x1800aac59  lea     r8, [rbp+var_38]
0x1800aac5d  mov     [rbp+var_38], r15
0x1800aac61  lea     rdx, aProcessorarchi; "@ProcessorArchitecture"
0x1800aac68  mov     rcx, rsi
0x1800aac6b  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x1800aac70  test    eax, eax
0x1800aac72  js      short loc_1800AAC80
0x1800aac74  mov     rcx, [rbp+var_38]
0x1800aac78  call    ?CreateExtensionArchitectureFromString@@YA?AW4MediaExtensionArchitecture@@PEAUHSTRING__@@@Z; CreateExtensionArchitectureFromString(HSTRING__ *)
0x1800aac7d  mov     [rdi+28h], eax
0x1800aac80  lea     rcx, [rbp+var_50]; this
0x1800aac84  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800aac89  mov     rcx, [rbp+var_38]; string
0x1800aac8d  call    cs:__imp_WindowsDeleteString
0x1800aac93  mov     rcx, [rbp+string]; string
0x1800aac97  mov     [rbp+var_38], r15
0x1800aac9b  call    cs:__imp_WindowsDeleteString
0x1800aaca1  mov     eax, ebx
0x1800aaca3  mov     rcx, [rbp+var_8]
0x1800aaca7  xor     rcx, rsp; StackCookie
0x1800aacaa  call    __security_check_cookie
0x1800aacaf  add     rsp, 80h
0x1800aacb6  pop     r15
0x1800aacb8  pop     r14
0x1800aacba  pop     r12
0x1800aacbc  pop     rdi
0x1800aacbd  pop     rsi
0x1800aacbe  pop     rbx
  ... truncated ...
```
