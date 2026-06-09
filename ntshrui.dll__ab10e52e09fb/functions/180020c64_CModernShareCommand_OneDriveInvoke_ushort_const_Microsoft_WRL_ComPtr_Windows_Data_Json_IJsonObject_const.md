# CModernShareCommand::OneDriveInvoke(ushort const *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &)

- ea: `0x180020c64`
- end: `0x180020f64`
- name: `?OneDriveInvoke@CModernShareCommand@@QEAAJPEBGAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z`
- size: `768`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001f880`
- `0x18004fa00`

## callees

- `0x180008900`
- `0x18001efc4`
- `0x180020c64`
- `0x180020f6c`
- `0x180020fb8`
- `0x1800214cc`
- `0x1800223bc`
- `0x1800232c4`
- `0x1800254e0`
- `0x180035d9c`
- `0x18003a768`
- `0x18003a7a8`
- `0x180049154`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020e7d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020e7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180020e0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180020e0b`
- `OLEAUT32!__imp_SysAllocString` at `0x180020e14`
- `OLEAUT32!__imp_SysAllocString` at `0x180020e14`

## string_xrefs

- `0x180020cb7`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x180020d1b`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x180020d50`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x180020de5`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x180020e32`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x180020e90`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x180020ef6`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CModernShareCommand::OneDriveInvoke(__int64 a1, const unsigned __int16 *a2, __int64 a3)
{
  _QWORD *v5; // rax
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rsi
  __int64 (__fastcall *v14)(__int64, __int64, __int64); // rdi
  __int64 v15; // rbx
  int v16; // eax
  const OLECHAR *StringRawBuffer; // rax
  BSTR v18; // rbx
  __int64 **v19; // rdi
  HRESULT Instance; // eax
  HRESULT v21; // esi
  __int64 *v22; // rcx
  __int64 v23; // rax
  int v24; // eax
  int ppv; // [rsp+20h] [rbp-60h]
  __int64 v27; // [rsp+30h] [rbp-50h] BYREF
  HSTRING string; // [rsp+38h] [rbp-48h] BYREF
  __int64 v29; // [rsp+40h] [rbp-40h] BYREF
  void *v30; // [rsp+48h] [rbp-38h] BYREF
  __int64 v31; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER v32; // [rsp+58h] [rbp-28h] BYREF
  __int64 v33; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v30 = (void *)a2;
  v29 = 0;
  v5 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                   (HSTRING *)&v32,
                   (const unsigned __int16 (*)[29])a2);
  v6 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(*v5, &v29);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v32, &v30);
    v10 = AddStringToJSON(L"function", *(_QWORD *)(v9 + 24), &v29);
    v7 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9D1,
        (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
        (const char *)(unsigned int)v10,
        ppv);
LABEL_25:
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v29);
      return v7;
    }
    v27 = 0;
    v11 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(a3, &v27);
    v7 = v11;
    if ( v11 >= 0 )
    {
      v13 = v29;
      v14 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v29 + 56LL);
      v15 = v27;
      v33 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v32, L"args", 5u, 4u);
      v11 = v14(v13, v33, v15);
      v7 = v11;
      if ( v11 >= 0 )
      {
        string = 0;
        v16 = JSONToString(&v29, &string);
        v7 = v16;
        if ( v16 >= 0 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v18 = SysAllocString(StringRawBuffer);
          v30 = v18;
          if ( v18 )
          {
            v19 = (__int64 **)(a1 + 240);
            if ( !*(_QWORD *)(a1 + 240) )
            {
              Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(a1 + 240);
              Instance = CoCreateInstance(
                           &GUID_94269c4e_071a_4116_90e6_52e557067e4e,
                           0,
                           4u,
                           &GUID_6a821279_ab49_48f8_9a27_f6c59b4ff024,
                           (LPVOID *)(a1 + 240));
              v21 = Instance;
              if ( Instance < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x9DE,
                  (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
                  (const char *)(unsigned int)Instance,
                  ppv);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v30);
                wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
                Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v27);
                v7 = v21;
                goto LABEL_25;
              }
            }
            v31 = 0;
            v22 = *v19;
            v23 = **v19;
            v31 = 0;
            v24 = (*(__int64 (__fastcall **)(__int64 *, BSTR, __int64 *))(v23 + 24))(v22, v18, &v31);
            v7 = v24;
            if ( v24 >= 0 )
            {
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v31);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v30);
              wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
              Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v27);
              v7 = 0;
              goto LABEL_25;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x9E3,
              (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
              (const char *)(unsigned int)v24,
              ppv);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v31);
          }
          else
          {
            v7 = -2147024882;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x9D9,
              (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
              (const char *)0x8007000ELL,
              ppv);
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v30);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x9D7,
            (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
            (const char *)(unsigned int)v16,
            ppv);
        }
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
        goto LABEL_10;
      }
      v12 = 2516;
    }
    else
    {
      v12 = 2515;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
      (const char *)(unsigned int)v11,
      ppv);
LABEL_10:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v27);
    goto LABEL_25;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x9D0,
    (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
    (const char *)(unsigned int)v6,
    ppv);
  v8 = v29;
  if ( v29 )
  {
    v29 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return v7;
}

```

## disassembly

```asm
0x180020c64  push    rbp
0x180020c66  push    rbx
0x180020c67  push    rsi
0x180020c68  push    rdi
0x180020c69  push    r14
0x180020c6b  mov     rbp, rsp
0x180020c6e  sub     rsp, 80h
0x180020c75  mov     rax, cs:__security_cookie
0x180020c7c  xor     rax, rsp
0x180020c7f  mov     [rbp+var_8], rax
0x180020c83  mov     rdi, r8
0x180020c86  mov     r14, rcx
0x180020c89  mov     [rbp+var_38], rdx
0x180020c8d  mov     [rbp+var_40], 0
0x180020c95  lea     rcx, [rbp+var_28]; string
0x180020c99  call    ??$?0$0BN@@StringReference@Internal@Windows@@QEAA@AEAY0BN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[29])
0x180020c9e  lea     rdx, [rbp+var_40]
0x180020ca2  mov     rcx, [rax]
0x180020ca5  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x180020caa  mov     ebx, eax
0x180020cac  test    eax, eax
0x180020cae  jns     short loc_180020CEC
0x180020cb0  mov     rcx, [rbp+28h]; this
0x180020cb4  mov     r9d, eax; char *
0x180020cb7  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180020cbe  mov     edx, 9D0h; void *
0x180020cc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020cc8  nop
0x180020cc9  mov     rcx, [rbp+var_40]
0x180020ccd  test    rcx, rcx
0x180020cd0  jz      short loc_180020CE7
0x180020cd2  mov     [rbp+var_40], 0
0x180020cda  mov     rax, [rcx]
0x180020cdd  mov     rax, [rax+10h]
0x180020ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ce6  nop
0x180020ce7  jmp     loc_180020F48
0x180020cec  lea     rdx, [rbp+var_38]
0x180020cf0  lea     rcx, [rbp+var_28]
0x180020cf4  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180020cf9  nop
0x180020cfa  lea     r8, [rbp+var_40]
0x180020cfe  mov     rdx, [rax+18h]
0x180020d02  lea     rcx, aFunction; "function"
0x180020d09  call    ?AddStringToJSON@@YAJPEAGPEAUHSTRING__@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; AddStringToJSON(ushort *,HSTRING__ *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x180020d0e  mov     ebx, eax
0x180020d10  test    eax, eax
0x180020d12  jns     short loc_180020D31
0x180020d14  mov     rcx, [rbp+28h]; this
0x180020d18  mov     r9d, eax; char *
0x180020d1b  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180020d22  mov     edx, 9D1h; void *
0x180020d27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020d2c  jmp     loc_180020F3F
0x180020d31  mov     [rbp+var_50], 0
0x180020d39  lea     rdx, [rbp+var_50]
0x180020d3d  mov     rcx, rdi
0x180020d40  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x180020d45  mov     ebx, eax
0x180020d47  test    eax, eax
0x180020d49  jns     short loc_180020D72
0x180020d4b  mov     edx, 9D3h; void *
0x180020d50  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180020d57  mov     r9d, eax; char *
0x180020d5a  mov     rcx, [rbp+28h]; this
0x180020d5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020d63  nop
0x180020d64  lea     rcx, [rbp+var_50]
0x180020d68  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180020d6d  jmp     loc_180020F3F
0x180020d72  mov     rsi, [rbp+var_40]
0x180020d76  mov     rax, [rsi]
0x180020d79  mov     rdi, [rax+38h]
0x180020d7d  mov     rbx, [rbp+var_50]
0x180020d81  mov     [rbp+var_10], 0
0x180020d89  mov     r9d, 4; unsigned int
0x180020d8f  lea     r8d, [r9+1]; unsigned int
0x180020d93  lea     rdx, aArgs; "args"
0x180020d9a  lea     rcx, [rbp+var_28]; hstringHeader
0x180020d9e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180020da3  nop
0x180020da4  mov     r8, rbx
0x180020da7  mov     rdx, [rbp+var_10]
0x180020dab  mov     rcx, rsi
0x180020dae  mov     rax, rdi
0x180020db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020db6  mov     ebx, eax
0x180020db8  test    eax, eax
0x180020dba  jns     short loc_180020DC3
0x180020dbc  mov     edx, 9D4h
0x180020dc1  jmp     short loc_180020D50
0x180020dc3  mov     [rbp+string], 0
0x180020dcb  lea     rdx, [rbp+string]
0x180020dcf  lea     rcx, [rbp+var_40]
0x180020dd3  call    ?JSONToString@@YAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; JSONToString(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x180020dd8  mov     ebx, eax
0x180020dda  test    eax, eax
0x180020ddc  jns     short loc_180020E05
0x180020dde  mov     rcx, [rbp+28h]; this
0x180020de2  mov     r9d, eax; char *
0x180020de5  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180020dec  mov     edx, 9D7h; void *
0x180020df1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020df6  nop
0x180020df7  lea     rcx, [rbp+string]
0x180020dfb  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180020e00  jmp     loc_180020D64
0x180020e05  xor     edx, edx; length
0x180020e07  mov     rcx, [rbp+string]; string
0x180020e0b  call    cs:__imp_WindowsGetStringRawBuffer
0x180020e11  mov     rcx, rax; psz
0x180020e14  call    cs:__imp_SysAllocString
0x180020e1a  mov     rbx, rax
0x180020e1d  mov     [rbp+var_38], rax
0x180020e21  test    rax, rax
0x180020e24  jnz     short loc_180020E4F
0x180020e26  mov     rcx, [rbp+28h]; this
0x180020e2a  mov     ebx, 8007000Eh
0x180020e2f  mov     r9d, ebx; char *
0x180020e32  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180020e39  mov     edx, 9D9h; void *
0x180020e3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020e43  nop
0x180020e44  lea     rcx, [rbp+var_38]
0x180020e48  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180020e4d  jmp     short loc_180020DF7
0x180020e4f  lea     rdi, [r14+0F0h]
0x180020e56  cmp     qword ptr [rdi], 0
0x180020e5a  jnz     short loc_180020EC3
0x180020e5c  mov     rcx, rdi
0x180020e5f  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180020e64  mov     qword ptr [rsp+80h+ppv], rdi; int
0x180020e69  lea     r9, _GUID_6a821279_ab49_48f8_9a27_f6c59b4ff024; riid
0x180020e70  xor     edx, edx; pUnkOuter
0x180020e72  lea     r8d, [rdx+4]; dwClsContext
0x180020e76  lea     rcx, _GUID_94269c4e_071a_4116_90e6_52e557067e4e; rclsid
0x180020e7d  call    cs:__imp_CoCreateInstance
0x180020e83  mov     esi, eax
0x180020e85  test    eax, eax
0x180020e87  jns     short loc_180020EC3
0x180020e89  mov     rcx, [rbp+28h]; this
0x180020e8d  mov     r9d, eax; char *
0x180020e90  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180020e97  mov     edx, 9DEh; void *
0x180020e9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020ea1  nop
0x180020ea2  lea     rcx, [rbp+var_38]
0x180020ea6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180020eab  nop
0x180020eac  lea     rcx, [rbp+string]
0x180020eb0  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180020eb5  nop
0x180020eb6  lea     rcx, [rbp+var_50]
0x180020eba  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180020ebf  mov     ebx, esi
0x180020ec1  jmp     short loc_180020F3F
0x180020ec3  mov     [rbp+var_30], 0
0x180020ecb  mov     rcx, [rdi]
0x180020ece  mov     rax, [rcx]
0x180020ed1  mov     [rbp+var_30], 0
0x180020ed9  lea     r8, [rbp+var_30]
0x180020edd  mov     rdx, rbx
0x180020ee0  mov     rax, [rax+18h]
0x180020ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ee9  mov     ebx, eax
0x180020eeb  test    eax, eax
0x180020eed  jns     short loc_180020F16
0x180020eef  mov     rcx, [rbp+28h]; this
0x180020ef3  mov     r9d, eax; char *
0x180020ef6  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180020efd  mov     edx, 9E3h; void *
0x180020f02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020f07  nop
0x180020f08  lea     rcx, [rbp+var_30]
0x180020f0c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180020f11  jmp     loc_180020E44
0x180020f16  lea     rcx, [rbp+var_30]
0x180020f1a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180020f1f  nop
0x180020f20  lea     rcx, [rbp+var_38]
0x180020f24  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180020f29  nop
0x180020f2a  lea     rcx, [rbp+string]
0x180020f2e  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180020f33  nop
0x180020f34  lea     rcx, [rbp+var_50]
0x180020f38  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180020f3d  xor     ebx, ebx
0x180020f3f  lea     rcx, [rbp+var_40]
0x180020f43  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180020f48  mov     eax, ebx
0x180020f4a  mov     rcx, [rbp+var_8]
0x180020f4e  xor     rcx, rsp; StackCookie
0x180020f51  call    __security_check_cookie
0x180020f56  add     rsp, 80h
0x180020f5d  pop     r14
0x180020f5f  pop     rdi
0x180020f60  pop     rsi
0x180020f61  pop     rbx
0x180020f62  pop     rbp
0x180020f63  retn
```
