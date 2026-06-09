# _anonymous_namespace_::GetSignalTypes

- ea: `0x1800e5a78`
- end: `0x1800e5ec1`
- name: `_anonymous_namespace_::GetSignalTypes`
- size: `1097`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800e5180`

## callees

- `0x180008de0`
- `0x18000caf4`
- `0x18000d4d4`
- `0x18000f0c8`
- `0x180019fd8`
- `0x18002031c`
- `0x180025a78`
- `0x18002d994`
- `0x180055e74`
- `0x18005bcbc`
- `0x1800e5a78`
- `0x180107010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e5d45`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e5d45`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x1800e5bcd`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x1800e5bcd`
- `XmlLite!CreateXmlReader` at `0x1800e5b55`
- `XmlLite!CreateXmlReader` at `0x1800e5b55`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800e5ae0`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800e5ae0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall anonymous_namespace_::GetSignalTypes(const BYTE *a1, _QWORD *a2)
{
  __int64 v4; // rdx
  IUnknown *v5; // rbx
  HRESULT v6; // eax
  unsigned int v7; // edi
  HRESULT v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rax
  int pwszBaseUri; // [rsp+20h] [rbp-88h]
  int pwszBaseUria; // [rsp+20h] [rbp-88h]
  void *ppvObject; // [rsp+30h] [rbp-78h] BYREF
  int v22; // [rsp+38h] [rbp-70h] BYREF
  IXmlReaderInput *ppInput; // [rsp+40h] [rbp-68h] BYREF
  IUnknown *v24; // [rsp+48h] [rbp-60h] BYREF
  __int64 v25; // [rsp+50h] [rbp-58h] BYREF
  int v26; // [rsp+58h] [rbp-50h] BYREF
  int v27; // [rsp+5Ch] [rbp-4Ch] BYREF
  __int64 v28; // [rsp+60h] [rbp-48h] BYREF
  _BYTE v29[16]; // [rsp+68h] [rbp-40h] BYREF
  __int64 v30; // [rsp+78h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  if ( a2 )
  {
    *a2 = 0;
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)&a1[2 * v4] );
    v5 = (IUnknown *)SHCreateMemStream(a1, 2 * (int)v4);
    v24 = v5;
    Microsoft::WRL::ComPtr<IConfigNode>::InternalAddRef(&v24);
    if ( v5 )
    {
      ppvObject = 0;
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
      v6 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
      v7 = v6;
      if ( v6 >= 0 )
      {
        ppInput = 0;
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppInput);
        v8 = CreateXmlReaderInputWithEncodingName(v5, 0, L"UTF-16", 0, 0, &ppInput);
        v9 = v8;
        if ( v8 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(void *, IXmlReaderInput *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppInput);
          v11 = v10;
          if ( v10 >= 0 )
          {
            v26 = 0;
            std::wstring::wstring(v29, &Class);
            while ( !(*(unsigned int (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v26) )
            {
              v28 = 0;
              v27 = 0;
              if ( v26 == 1 )
              {
                v12 = (*(__int64 (__fastcall **)(void *, __int64 *, int *))(*(_QWORD *)ppvObject + 112LL))(
                        ppvObject,
                        &v28,
                        &v27);
                v13 = v12;
                if ( v12 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x127,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\dynamicmanagement.cpp",
                    (const char *)(unsigned int)v12,
                    pwszBaseUria);
                  std::wstring::~wstring(v29);
                  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppInput);
                  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
                  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v24);
                  return v13;
                }
                if ( !(unsigned int)_o__wcsicmp(v28, L"signal")
                  && (*(int (__fastcall **)(void *, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 80LL))(
                       ppvObject,
                       L"type",
                       0) >= 0 )
                {
                  v25 = 0;
                  v22 = 0;
                  v14 = (*(__int64 (__fastcall **)(void *, __int64 *, int *))(*(_QWORD *)ppvObject + 128LL))(
                          ppvObject,
                          &v25,
                          &v22);
                  v15 = v14;
                  if ( v14 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x12D,
                      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\dynamicmanagement.cpp",
                      (const char *)(unsigned int)v14,
                      pwszBaseUria);
                    std::wstring::~wstring(v29);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppInput);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v24);
                    return v15;
                  }
                  v16 = v25;
                  if ( v25 )
                  {
                    if ( v30 )
                    {
                      std::wstring::append(v29, L", ");
                      v16 = v25;
                    }
                    std::wstring::append(v29, v16);
                  }
                }
              }
            }
            if ( v30 )
            {
              v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
              wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                &v25,
                v17);
              v18 = v25;
              v25 = 0;
              *a2 = v18;
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v25);
            }
            std::wstring::~wstring(v29);
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppInput);
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v24);
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x11C,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\dynamicmanagement.cpp",
              (const char *)(unsigned int)v10,
              pwszBaseUria);
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppInput);
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v24);
            return v11;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x11B,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\dynamicmanagement.cpp",
            (const char *)(unsigned int)v8,
            pwszBaseUria);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppInput);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v24);
          return v9;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x118,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\dynamicmanagement.cpp",
          (const char *)(unsigned int)v6,
          pwszBaseUri);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v24);
        return v7;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x115,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\dynamicmanagement.cpp",
        (const char *)0x8007000ELL,
        pwszBaseUri);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v24);
      return 2147942414LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x111,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\dynamicmanagement.cpp",
      (const char *)0x80070057LL,
      pwszBaseUri);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800e5a78  mov     [rsp+arg_10], rbx
0x1800e5a7d  push    rsi
0x1800e5a7e  push    rdi
0x1800e5a7f  push    r14
0x1800e5a81  sub     rsp, 90h
0x1800e5a88  mov     rax, cs:__security_cookie
0x1800e5a8f  xor     rax, rsp
0x1800e5a92  mov     [rsp+0A8h+var_20], rax
0x1800e5a9a  mov     rsi, rdx
0x1800e5a9d  xor     r14d, r14d
0x1800e5aa0  test    rdx, rdx
0x1800e5aa3  jnz     short loc_1800E5ACD
0x1800e5aa5  mov     rcx, [rsp+0A8h]; this
0x1800e5aad  mov     ebx, 80070057h
0x1800e5ab2  mov     r9d, ebx; char *
0x1800e5ab5  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800e5abc  mov     edx, 111h; void *
0x1800e5ac1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5ac6  mov     eax, ebx
0x1800e5ac8  jmp     loc_1800E5E9C
0x1800e5acd  mov     [rdx], r14
0x1800e5ad0  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800e5ad4  inc     rdx
0x1800e5ad7  cmp     [rcx+rdx*2], r14w
0x1800e5adc  jnz     short loc_1800E5AD4
0x1800e5ade  add     edx, edx; cbInit
0x1800e5ae0  call    cs:__imp_SHCreateMemStream
0x1800e5ae7  nop     dword ptr [rax+rax+00h]
0x1800e5aec  mov     rbx, rax
0x1800e5aef  mov     [rsp+0A8h+var_60], rax
0x1800e5af4  lea     rcx, [rsp+0A8h+var_60]
0x1800e5af9  call    ?InternalAddRef@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalAddRef(void)
0x1800e5afe  nop
0x1800e5aff  test    rbx, rbx
0x1800e5b02  jnz     short loc_1800E5B37
0x1800e5b04  mov     rcx, [rsp+0A8h]; this
0x1800e5b0c  mov     ebx, 8007000Eh
0x1800e5b11  mov     r9d, ebx; char *
0x1800e5b14  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800e5b1b  mov     edx, 115h; void *
0x1800e5b20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5b25  nop
0x1800e5b26  lea     rcx, [rsp+0A8h+var_60]
0x1800e5b2b  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800e5b30  mov     eax, ebx
0x1800e5b32  jmp     loc_1800E5E9C
0x1800e5b37  mov     [rsp+0A8h+ppvObject], r14
0x1800e5b3c  lea     rcx, [rsp+0A8h+ppvObject]
0x1800e5b41  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800e5b46  xor     r8d, r8d; pMalloc
0x1800e5b49  lea     rdx, [rsp+0A8h+ppvObject]; ppvObject
0x1800e5b4e  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x1800e5b55  call    cs:__imp_CreateXmlReader
0x1800e5b5c  nop     dword ptr [rax+rax+00h]
0x1800e5b61  mov     edi, eax
0x1800e5b63  test    eax, eax
0x1800e5b65  jns     short loc_1800E5BA0
0x1800e5b67  mov     rcx, [rsp+0A8h]; this
0x1800e5b6f  mov     r9d, eax; char *
0x1800e5b72  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800e5b79  mov     edx, 118h; void *
0x1800e5b7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5b83  nop
0x1800e5b84  lea     rcx, [rsp+0A8h+ppvObject]
0x1800e5b89  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800e5b8e  nop
0x1800e5b8f  lea     rcx, [rsp+0A8h+var_60]
0x1800e5b94  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800e5b99  mov     eax, edi
0x1800e5b9b  jmp     loc_1800E5E9C
0x1800e5ba0  mov     [rsp+0A8h+var_68], r14
0x1800e5ba5  lea     rcx, [rsp+0A8h+var_68]
0x1800e5baa  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800e5baf  lea     rax, [rsp+0A8h+var_68]
0x1800e5bb4  mov     [rsp+0A8h+ppInput], rax; ppInput
0x1800e5bb9  mov     [rsp+0A8h+pwszBaseUri], r14; int
0x1800e5bbe  xor     r9d, r9d; fEncodingHint
0x1800e5bc1  lea     r8, pwszEncodingName; "UTF-16"
0x1800e5bc8  xor     edx, edx; pMalloc
0x1800e5bca  mov     rcx, rbx; pInputStream
0x1800e5bcd  call    cs:__imp_CreateXmlReaderInputWithEncodingName
0x1800e5bd4  nop     dword ptr [rax+rax+00h]
0x1800e5bd9  mov     ebx, eax
0x1800e5bdb  test    eax, eax
0x1800e5bdd  jns     short loc_1800E5C23
0x1800e5bdf  mov     rcx, [rsp+0A8h]; this
0x1800e5be7  mov     r9d, eax; char *
0x1800e5bea  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800e5bf1  mov     edx, 11Bh; void *
0x1800e5bf6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5bfb  nop
0x1800e5bfc  lea     rcx, [rsp+0A8h+var_68]
0x1800e5c01  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800e5c06  nop
0x1800e5c07  lea     rcx, [rsp+0A8h+ppvObject]
0x1800e5c0c  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800e5c11  nop
0x1800e5c12  lea     rcx, [rsp+0A8h+var_60]
0x1800e5c17  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800e5c1c  mov     eax, ebx
0x1800e5c1e  jmp     loc_1800E5E9C
0x1800e5c23  mov     rcx, [rsp+0A8h+ppvObject]
0x1800e5c28  mov     rax, [rcx]
0x1800e5c2b  mov     rdx, [rsp+0A8h+var_68]
0x1800e5c30  mov     rax, [rax+18h]
0x1800e5c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5c39  mov     ebx, eax
0x1800e5c3b  test    eax, eax
0x1800e5c3d  jns     short loc_1800E5C83
0x1800e5c3f  mov     rcx, [rsp+0A8h]; this
0x1800e5c47  mov     r9d, eax; char *
0x1800e5c4a  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800e5c51  mov     edx, 11Ch; void *
0x1800e5c56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5c5b  nop
0x1800e5c5c  lea     rcx, [rsp+0A8h+var_68]
0x1800e5c61  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800e5c66  nop
0x1800e5c67  lea     rcx, [rsp+0A8h+ppvObject]
0x1800e5c6c  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800e5c71  nop
0x1800e5c72  lea     rcx, [rsp+0A8h+var_60]
0x1800e5c77  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800e5c7c  mov     eax, ebx
0x1800e5c7e  jmp     loc_1800E5E9C
0x1800e5c83  mov     [rsp+0A8h+var_50], r14d
0x1800e5c88  lea     rdx, Class
0x1800e5c8f  lea     rcx, [rsp+0A8h+var_40]
0x1800e5c94  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800e5c99  nop
0x1800e5c9a  mov     rcx, [rsp+0A8h+ppvObject]
0x1800e5c9f  mov     rax, [rcx]
0x1800e5ca2  lea     rdx, [rsp+0A8h+var_50]
0x1800e5ca7  mov     rax, [rax+30h]
0x1800e5cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5cb0  test    eax, eax
0x1800e5cb2  jnz     loc_1800E5E33
0x1800e5cb8  mov     [rsp+0A8h+var_48], r14
0x1800e5cbd  mov     [rsp+0A8h+var_4C], r14d
0x1800e5cc2  cmp     [rsp+0A8h+var_50], 1
0x1800e5cc7  jnz     short loc_1800E5C9A
0x1800e5cc9  mov     rcx, [rsp+0A8h+ppvObject]
0x1800e5cce  mov     rax, [rcx]
0x1800e5cd1  lea     r8, [rsp+0A8h+var_4C]
0x1800e5cd6  lea     rdx, [rsp+0A8h+var_48]
0x1800e5cdb  mov     rax, [rax+70h]
0x1800e5cdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5ce4  mov     ebx, eax
0x1800e5ce6  test    eax, eax
0x1800e5ce8  jns     short loc_1800E5D39
0x1800e5cea  mov     rcx, [rsp+0A8h]; this
0x1800e5cf2  mov     r9d, eax; char *
0x1800e5cf5  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800e5cfc  mov     edx, 127h; void *
0x1800e5d01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5d06  nop
0x1800e5d07  lea     rcx, [rsp+0A8h+var_40]
0x1800e5d0c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e5d11  nop
0x1800e5d12  lea     rcx, [rsp+0A8h+var_68]
0x1800e5d17  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800e5d1c  nop
0x1800e5d1d  lea     rcx, [rsp+0A8h+ppvObject]
0x1800e5d22  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800e5d27  nop
0x1800e5d28  lea     rcx, [rsp+0A8h+var_60]
0x1800e5d2d  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800e5d32  mov     eax, ebx
0x1800e5d34  jmp     loc_1800E5E9C
0x1800e5d39  lea     rdx, aSignal; "signal"
0x1800e5d40  mov     rcx, [rsp+0A8h+var_48]
0x1800e5d45  call    cs:__imp__o__wcsicmp
0x1800e5d4c  nop     dword ptr [rax+rax+00h]
0x1800e5d51  test    eax, eax
0x1800e5d53  jnz     loc_1800E5C9A
0x1800e5d59  mov     rcx, [rsp+0A8h+ppvObject]
0x1800e5d5e  mov     rax, [rcx]
0x1800e5d61  xor     r8d, r8d
0x1800e5d64  lea     rdx, aType; "type"
0x1800e5d6b  mov     rax, [rax+50h]
0x1800e5d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5d74  test    eax, eax
0x1800e5d76  js      loc_1800E5C9A
0x1800e5d7c  mov     [rsp+0A8h+var_58], r14
0x1800e5d81  mov     [rsp+0A8h+var_70], r14d
0x1800e5d86  mov     rcx, [rsp+0A8h+ppvObject]
0x1800e5d8b  mov     rax, [rcx]
0x1800e5d8e  lea     r8, [rsp+0A8h+var_70]
0x1800e5d93  lea     rdx, [rsp+0A8h+var_58]
0x1800e5d98  mov     rax, [rax+80h]
0x1800e5d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5da4  mov     ebx, eax
0x1800e5da6  test    eax, eax
0x1800e5da8  jns     short loc_1800E5DF9
0x1800e5daa  mov     rcx, [rsp+0A8h]; this
0x1800e5db2  mov     r9d, eax; char *
0x1800e5db5  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800e5dbc  mov     edx, 12Dh; void *
0x1800e5dc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5dc6  nop
0x1800e5dc7  lea     rcx, [rsp+0A8h+var_40]
0x1800e5dcc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e5dd1  nop
0x1800e5dd2  lea     rcx, [rsp+0A8h+var_68]
0x1800e5dd7  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800e5ddc  nop
0x1800e5ddd  lea     rcx, [rsp+0A8h+ppvObject]
0x1800e5de2  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800e5de7  nop
0x1800e5de8  lea     rcx, [rsp+0A8h+var_60]
0x1800e5ded  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800e5df2  mov     eax, ebx
0x1800e5df4  jmp     loc_1800E5E9C
0x1800e5df9  mov     rdx, [rsp+0A8h+var_58]
0x1800e5dfe  test    rdx, rdx
0x1800e5e01  jz      loc_1800E5C9A
0x1800e5e07  cmp     [rsp+0A8h+var_30], r14
0x1800e5e0c  jz      short loc_1800E5E24
0x1800e5e0e  lea     rdx, asc_18012B8F4; ", "
0x1800e5e15  lea     rcx, [rsp+0A8h+var_40]
0x1800e5e1a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800e5e1f  mov     rdx, [rsp+0A8h+var_58]
0x1800e5e24  lea     rcx, [rsp+0A8h+var_40]
0x1800e5e29  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800e5e2e  jmp     loc_1800E5C9A
0x1800e5e33  cmp     [rsp+0A8h+var_30], r14
0x1800e5e38  jz      short loc_1800E5E69
0x1800e5e3a  lea     rcx, [rsp+0A8h+var_40]
0x1800e5e3f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e5e44  mov     rdx, rax
0x1800e5e47  lea     rcx, [rsp+0A8h+var_58]
0x1800e5e4c  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800e5e51  mov     rax, [rsp+0A8h+var_58]
0x1800e5e56  mov     [rsp+0A8h+var_58], r14
0x1800e5e5b  mov     [rsi], rax
0x1800e5e5e  lea     rcx, [rsp+0A8h+var_58]
0x1800e5e63  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800e5e68  nop
0x1800e5e69  lea     rcx, [rsp+0A8h+var_40]
0x1800e5e6e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e5e73  nop
0x1800e5e74  lea     rcx, [rsp+0A8h+var_68]
0x1800e5e79  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800e5e7e  nop
0x1800e5e7f  lea     rcx, [rsp+0A8h+ppvObject]
0x1800e5e84  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800e5e89  nop
0x1800e5e8a  lea     rcx, [rsp+0A8h+var_60]
0x1800e5e8f  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800e5e94  xor     eax, eax
0x1800e5e96  jmp     short loc_1800E5E9C
0x1800e5e98  mov     eax, [rsp+0A8h+var_70]
0x1800e5e9c  mov     rcx, [rsp+0A8h+var_20]
0x1800e5ea4  xor     rcx, rsp; StackCookie
0x1800e5ea7  call    __security_check_cookie
0x1800e5eac  mov     rbx, [rsp+0A8h+arg_10]
0x1800e5eb4  add     rsp, 90h
0x1800e5ebb  pop     r14
0x1800e5ebd  pop     rdi
0x1800e5ebe  pop     rsi
0x1800e5ebf  retn
```
