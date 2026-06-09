# CoreWebViewHostProcess::GetRACProfileNameInternal(HSTRING__ * *)

- ea: `0x180017768`
- end: `0x180017977`
- name: `?GetRACProfileNameInternal@CoreWebViewHostProcess@@AEAAXPEAPEAUHSTRING__@@@Z`
- size: `527`
- prototype: `void(CoreWebViewHostProcess *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180016734`

## callees

- `0x180007ee0`
- `0x18000b0ec`
- `0x180013c08`
- `0x180017768`
- `0x180017f18`
- `0x180023298`
- `0x18002b530`
- `0x180035b88`
- `0x18003fe80`
- `0x180085010`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-0!GetCurrentPackageFamilyName` at `0x180017886`
- `api-ms-win-appmodel-runtime-l1-1-0!GetCurrentPackageFamilyName` at `0x180017886`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800177ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800177ed`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800178ce`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800178ce`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180017852`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180017852`
- `edgeIso!__imp_?GetRACProfileName@@YAJKQEAG@Z` at `0x1800177ad`
- `edgeIso!__imp_?GetRACProfileName@@YAJKQEAG@Z` at `0x1800177ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CoreWebViewHostProcess::GetRACProfileNameInternal(CoreWebViewHostProcess *this, HSTRING *a2)
{
  int RACProfileName; // eax
  __int64 v5; // rcx
  HRESULT String; // eax
  __int64 *v7; // rsi
  int ActivationFactory; // eax
  unsigned int CurrentPackageFamilyName; // eax
  void *v10; // rdx
  unsigned int v11; // r8d
  unsigned __int64 v12; // rcx
  signed int v13; // eax
  __int64 v14; // rsi
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64, HSTRING *); // rdi
  UINT32 v16; // eax
  __int64 v17; // rbx
  __int64 v18; // rax
  int v19; // eax
  unsigned int v20; // [rsp+20h] [rbp-E0h]
  unsigned int v21[2]; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h]
  _BYTE v24[32]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR sourceString[2]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  if ( *((_QWORD *)this + 15) )
  {
    v7 = (__int64 *)((char *)this + 160);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 160);
    v23 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.WebView.CoreWebViewRACProfileStatics",
      0x36u,
      0x35u);
    ActivationFactory = RoGetActivationFactory(v23, &GUID_4293645b_0088_4882_9b4a_bc5b24f838dd, v7);
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewhostprocess.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v20);
    wcscpy(sourceString, L"A");
    CurrentPackageFamilyName = GetCurrentPackageFamilyName((UINT32 *)sourceString, packageFamilyName);
    if ( CurrentPackageFamilyName )
      wil::details::in1diag3::_FailFast_Win32(retaddr, v10, v11, (const char *)CurrentPackageFamilyName, v20);
    v21[0] = 0;
    v12 = -1;
    do
      ++v12;
    while ( packageFamilyName[v12] );
    v13 = ULongLongToULong(v12, v21);
    if ( v13 < 0 )
    {
      RaiseException(v13, 1u, 0, 0);
      __debugbreak();
    }
    v14 = *v7;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, HSTRING *))(*(_QWORD *)v14 + 48LL);
    v16 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v21[0]);
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, packageFamilyName, v16, v21[0]);
    v17 = v23;
    *(_QWORD *)v21 = *((_QWORD *)this + 15);
    v18 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v24, v21);
    v19 = v15(v14, *(_QWORD *)(v18 + 24), v17, a2);
    if ( v19 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x7D,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewhostprocess.cpp",
        (const char *)(unsigned int)v19,
        v20);
  }
  else
  {
    RACProfileName = GetRACProfileName(9u, sourceString);
    if ( RACProfileName < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewhostprocess.cpp",
        (const char *)(unsigned int)RACProfileName,
        v20);
    v5 = -1;
    do
      ++v5;
    while ( sourceString[v5] );
    String = WindowsCreateString(sourceString, v5, a2);
    if ( String < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x6D,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewhostprocess.cpp",
        (const char *)(unsigned int)String,
        v20);
  }
}

```

## disassembly

```asm
0x180017768  mov     [rsp-8+arg_10], rbx
0x18001776d  mov     [rsp-8+arg_18], rsi
0x180017772  push    rbp
0x180017773  push    rdi
0x180017774  push    r12
0x180017776  push    r14
0x180017778  push    r15
0x18001777a  lea     rbp, [rsp-20h]
0x18001777f  sub     rsp, 120h
0x180017786  mov     rax, cs:__security_cookie
0x18001778d  xor     rax, rsp
0x180017790  mov     [rbp+40h+var_30], rax
0x180017794  mov     r15, rdx
0x180017797  mov     r14, rcx
0x18001779a  xor     r12d, r12d
0x18001779d  cmp     [rcx+78h], r12
0x1800177a1  jnz     short loc_180017814
0x1800177a3  lea     rdx, [rsp+140h+sourceString]
0x1800177a8  lea     ecx, [r12+9]
0x1800177ad  call    cs:__imp_?GetRACProfileName@@YAJKQEAG@Z; GetRACProfileName(ulong,ushort * const)
0x1800177b3  test    eax, eax
0x1800177b5  jns     short loc_1800177D0
0x1800177b7  mov     rcx, [rbp+48h]; this
0x1800177bb  mov     r9d, eax; char *
0x1800177be  lea     r8, aOnecoreuapInet_39; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800177c5  lea     edx, [r12+6Bh]; void *
0x1800177ca  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800177d0  lea     rax, [rsp+140h+sourceString]
0x1800177d5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800177d9  inc     rcx
0x1800177dc  cmp     [rax+rcx*2], r12w
0x1800177e1  jnz     short loc_1800177D9
0x1800177e3  mov     edx, ecx; length
0x1800177e5  mov     r8, r15; string
0x1800177e8  lea     rcx, [rsp+140h+sourceString]; sourceString
0x1800177ed  call    cs:__imp_WindowsCreateString
0x1800177f3  test    eax, eax
0x1800177f5  jns     loc_18001794F
0x1800177fb  mov     rcx, [rbp+48h]; this
0x1800177ff  mov     r9d, eax; char *
0x180017802  lea     r8, aOnecoreuapInet_39; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180017809  mov     edx, 6Dh ; 'm'; void *
0x18001780e  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180017814  lea     rsi, [rcx+0A0h]
0x18001781b  mov     rcx, rsi
0x18001781e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180017823  mov     [rsp+140h+var_F0], r12
0x180017828  mov     r9d, 35h ; '5'; unsigned int
0x18001782e  lea     r8d, [r9+1]; unsigned int
0x180017832  lea     rdx, ?RuntimeClass_Windows_Internal_WebView_CoreWebViewRACProfileStatics@@3QBGB; "Windows.Internal.WebView.CoreWebViewRAC"...
0x180017839  lea     rcx, [rsp+140h+hstringHeader]; hstringHeader
0x18001783e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180017843  mov     r8, rsi
0x180017846  lea     rdx, _GUID_4293645b_0088_4882_9b4a_bc5b24f838dd
0x18001784d  mov     rcx, [rsp+140h+var_F0]
0x180017852  call    cs:__imp_RoGetActivationFactory
0x180017858  mov     rcx, [rbp+48h]; this
0x18001785c  test    eax, eax
0x18001785e  jns     short loc_180017875
0x180017860  mov     r9d, eax; char *
0x180017863  lea     r8, aOnecoreuapInet_39; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18001786a  mov     edx, 73h ; 's'; void *
0x18001786f  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180017875  mov     dword ptr [rsp+140h+sourceString], 41h ; 'A'
0x18001787d  lea     rdx, [rbp+40h+packageFamilyName]; packageFamilyName
0x180017881  lea     rcx, [rsp+140h+sourceString]; packageFamilyNameLength
0x180017886  call    cs:__imp_GetCurrentPackageFamilyName
0x18001788c  mov     rcx, [rbp+48h]; this
0x180017890  test    eax, eax
0x180017892  jz      short loc_18001789D
0x180017894  mov     r9d, eax; char *
0x180017897  call    ?_FailFast_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_FailFast_Win32(void *,uint,char const *,ulong)
0x18001789d  mov     [rsp+140h+var_110], r12d
0x1800178a2  lea     rax, [rbp+40h+packageFamilyName]
0x1800178a6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800178aa  inc     rcx; unsigned __int64
0x1800178ad  cmp     [rax+rcx*2], r12w
0x1800178b2  jnz     short loc_1800178AA
0x1800178b4  lea     rdx, [rsp+140h+var_110]; unsigned int *
0x1800178b9  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800178be  test    eax, eax
0x1800178c0  jns     short loc_1800178D5
0x1800178c2  xor     r9d, r9d; lpArguments
0x1800178c5  xor     r8d, r8d; nNumberOfArguments
0x1800178c8  lea     edx, [r9+1]; dwExceptionFlags
0x1800178cc  mov     ecx, eax; dwExceptionCode
0x1800178ce  call    cs:__imp_RaiseException
0x1800178d4  int     3; Trap to Debugger
0x1800178d5  mov     rsi, [rsi]
0x1800178d8  mov     rax, [rsi]
0x1800178db  mov     rdi, [rax+30h]
0x1800178df  mov     ecx, [rsp+140h+var_110]; unsigned int
0x1800178e3  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800178e8  mov     r9d, [rsp+140h+var_110]; unsigned int
0x1800178ed  mov     r8d, eax; unsigned int
0x1800178f0  lea     rdx, [rbp+40h+packageFamilyName]; sourceString
0x1800178f4  lea     rcx, [rsp+140h+hstringHeader]; hstringHeader
0x1800178f9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800178fe  nop
0x1800178ff  mov     rbx, [rsp+140h+var_F0]
0x180017904  mov     rdx, [r14+78h]
0x180017908  mov     qword ptr [rsp+140h+var_110], rdx
0x18001790d  lea     rdx, [rsp+140h+var_110]
0x180017912  lea     rcx, [rsp+140h+var_E8]
0x180017917  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18001791c  nop
0x18001791d  mov     r9, r15
0x180017920  mov     r8, rbx
0x180017923  mov     rdx, [rax+18h]
0x180017927  mov     rcx, rsi
0x18001792a  mov     rax, rdi
0x18001792d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017932  mov     rcx, [rbp+48h]; this
0x180017936  test    eax, eax
0x180017938  jns     short loc_18001794F
0x18001793a  mov     r9d, eax; char *
0x18001793d  lea     r8, aOnecoreuapInet_39; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180017944  mov     edx, 7Dh ; '}'; void *
0x180017949  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001794f  mov     rcx, [rbp+40h+var_30]
0x180017953  xor     rcx, rsp; StackCookie
0x180017956  call    __security_check_cookie
0x18001795b  lea     r11, [rsp+140h+var_20]
0x180017963  mov     rbx, [r11+40h]
0x180017967  mov     rsi, [r11+48h]
0x18001796b  mov     rsp, r11
0x18001796e  pop     r15
0x180017970  pop     r14
0x180017972  pop     r12
0x180017974  pop     rdi
0x180017975  pop     rbp
0x180017976  retn
```
