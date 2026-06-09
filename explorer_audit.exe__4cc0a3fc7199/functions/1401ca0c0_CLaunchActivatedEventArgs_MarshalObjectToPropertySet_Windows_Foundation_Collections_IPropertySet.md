# CLaunchActivatedEventArgs::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x1401ca0c0`
- end: `0x1401ca4bf`
- name: `?MarshalObjectToPropertySet@CLaunchActivatedEventArgs@@UEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `1023`
- prototype: `__int64 __fastcall(CLaunchActivatedEventArgs *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x14000c870`
- `0x14000edcc`
- `0x14007ce08`
- `0x1400826d8`
- `0x1400954e0`
- `0x1401040e0`
- `0x1401c9410`
- `0x1401ca0c0`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401ca1b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401ca1f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401ca20b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401ca246`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401ca46c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401ca47a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401ca1b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401ca1f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401ca20b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401ca246`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401ca46c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401ca47a`

## pseudocode

```c
__int64 __fastcall CLaunchActivatedEventArgs::MarshalObjectToPropertySet(
        CLaunchActivatedEventArgs *this,
        struct Windows::Foundation::Collections::IPropertySet *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 (__fastcall **v6)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **); // rax
  __int64 (__fastcall *v7)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **); // rbx
  int v8; // eax
  __int64 v9; // rdx
  __int64 (__fastcall *v10)(char *, HSTRING *); // rbx
  int v11; // eax
  __int64 v12; // rax
  __int64 (__fastcall *v13)(char *, HSTRING *); // rbx
  int v14; // eax
  __int64 v15; // rax
  __int64 (__fastcall *v16)(char *, __int64 *); // rbx
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING, __int64 *); // rbx
  int v20; // eax
  __int64 v21; // rdx
  _QWORD *v22; // rsi
  __int64 v23; // rbx
  __int64 v24; // rax
  __int64 (__fastcall *v25)(_QWORD *, __int64, __int64, _BYTE *); // rdi
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, HSTRING, __int64 *); // rbx
  int v28; // eax
  __int64 v29; // rdx
  _QWORD *v30; // rsi
  __int64 v31; // rbx
  __int64 v32; // rax
  __int64 (__fastcall *v33)(_QWORD *, __int64, __int64, _BYTE *); // rdi
  __int64 v34; // rbx
  _QWORD *v35; // rsi
  __int64 v36; // rax
  __int64 (__fastcall *v37)(_QWORD *, __int64, __int64, _BYTE *); // rdi
  int v39; // [rsp+20h] [rbp-39h]
  _BYTE v40[8]; // [rsp+30h] [rbp-29h] BYREF
  HSTRING string; // [rsp+38h] [rbp-21h] BYREF
  HSTRING v42; // [rsp+40h] [rbp-19h] BYREF
  __int64 v43; // [rsp+48h] [rbp-11h] BYREF
  __int64 v44; // [rsp+50h] [rbp-9h] BYREF
  __int64 v45; // [rsp+58h] [rbp-1h] BYREF
  _QWORD *v46; // [rsp+60h] [rbp+7h] BYREF
  __int64 v47; // [rsp+68h] [rbp+Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+17h] BYREF
  __int64 v49; // [rsp+88h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v4 = CActivatedEventArgsWithPrelaunchAndViewIdBase::MarshalObjectToPropertySet(
         (CLaunchActivatedEventArgs *)((char *)this - 256),
         a2);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = *(__int64 (__fastcall ***)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **))a2;
    v46 = 0;
    v47 = 0;
    v7 = *v6;
    Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v46);
    v8 = v7(a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v46);
    v5 = v8;
    if ( v8 < 0 )
    {
      v9 = 105;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
        (const char *)(unsigned int)v8,
        v39);
LABEL_33:
      Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v47);
      Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v46);
      return v5;
    }
    v49 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Foundation.PropertyValue",
      0x21u,
      0x20u);
    v8 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(
           v49,
           &v47);
    v5 = v8;
    if ( v8 < 0 )
    {
      v9 = 106;
      goto LABEL_7;
    }
    string = 0;
    v10 = *(__int64 (__fastcall **)(char *, HSTRING *))(*((_QWORD *)this - 2) + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v11 = v10((char *)this - 16, &string);
    v5 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
        (const char *)(unsigned int)v11,
        v39);
LABEL_10:
      WindowsDeleteString(string);
LABEL_32:
      string = 0;
      goto LABEL_33;
    }
    v12 = *((_QWORD *)this - 2);
    v42 = 0;
    v13 = *(__int64 (__fastcall **)(char *, HSTRING *))(v12 + 56);
    WindowsDeleteString(0);
    v42 = 0;
    v14 = v13((char *)this - 16, &v42);
    v5 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
        (const char *)(unsigned int)v14,
        v39);
LABEL_13:
      WindowsDeleteString(v42);
      v42 = 0;
      goto LABEL_10;
    }
    v15 = *((_QWORD *)this - 1);
    v43 = 0;
    v16 = *(__int64 (__fastcall **)(char *, __int64 *))(v15 + 48);
    Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v43);
    v17 = v16((char *)this - 8, &v43);
    v5 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
        (const char *)(unsigned int)v17,
        v39);
LABEL_16:
      Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v43);
      goto LABEL_13;
    }
    v18 = v47;
    v44 = 0;
    v19 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v47 + 144LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    v20 = v19(v18, string, &v44);
    v5 = v20;
    if ( v20 >= 0 )
    {
      v22 = v46;
      v23 = v44;
      v40[0] = 0;
      v24 = *v46;
      v49 = 0;
      v25 = *(__int64 (__fastcall **)(_QWORD *, __int64, __int64, _BYTE *))(v24 + 80);
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Arguments", 0xAu, 9u);
      v20 = v25(v22, v49, v23, v40);
      v5 = v20;
      if ( v20 >= 0 )
      {
        v26 = v47;
        v45 = 0;
        v27 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v47 + 144LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
        v28 = v27(v26, v42, &v45);
        v5 = v28;
        if ( v28 >= 0 )
        {
          v30 = v46;
          v31 = v45;
          v32 = *v46;
          v49 = 0;
          v33 = *(__int64 (__fastcall **)(_QWORD *, __int64, __int64, _BYTE *))(v32 + 80);
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"TileId", 7u, 6u);
          v28 = v33(v30, v49, v31, v40);
          v5 = v28;
          if ( v28 >= 0 )
          {
            v34 = v43;
            if ( !v43
              || (v35 = v46,
                  v36 = *v46,
                  v49 = 0,
                  v37 = *(__int64 (__fastcall **)(_QWORD *, __int64, __int64, _BYTE *))(v36 + 80),
                  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                    &hstringHeader,
                    L"TileActivatedInfo",
                    0x12u,
                    0x11u),
                  v28 = v37(v35, v49, v34, v40),
                  v5 = v28,
                  v28 >= 0) )
            {
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
              Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v43);
              WindowsDeleteString(v42);
              v42 = 0;
              WindowsDeleteString(string);
              v5 = 0;
              goto LABEL_32;
            }
            v29 = 130;
          }
          else
          {
            v29 = 126;
          }
        }
        else
        {
          v29 = 125;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v29,
          (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
          (const char *)(unsigned int)v28,
          v39);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
        goto LABEL_20;
      }
      v21 = 122;
    }
    else
    {
      v21 = 120;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v20,
      v39);
LABEL_20:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    goto LABEL_16;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x64,
    (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
    (const char *)(unsigned int)v4,
    v39);
  return v5;
}

```

## disassembly

```asm
0x1401ca0c0  mov     [rsp-8+arg_10], rbx
0x1401ca0c5  mov     [rsp-8+arg_18], rsi
0x1401ca0ca  push    rbp
0x1401ca0cb  push    rdi
0x1401ca0cc  push    r14
0x1401ca0ce  lea     rbp, [rsp-47h]
0x1401ca0d3  sub     rsp, 0A0h
0x1401ca0da  mov     rax, cs:__security_cookie
0x1401ca0e1  xor     rax, rsp
0x1401ca0e4  mov     [rbp+57h+var_20], rax
0x1401ca0e8  mov     rsi, rcx
0x1401ca0eb  mov     rdi, rdx
0x1401ca0ee  add     rcx, 0FFFFFFFFFFFFFF00h; this
0x1401ca0f5  call    ?MarshalObjectToPropertySet@CActivatedEventArgsWithPrelaunchAndViewIdBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z; CActivatedEventArgsWithPrelaunchAndViewIdBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)
0x1401ca0fa  xor     r14d, r14d
0x1401ca0fd  mov     ebx, eax
0x1401ca0ff  test    eax, eax
0x1401ca101  jns     short loc_1401CA11F
0x1401ca103  mov     rcx, [rbp+5Fh]; this
0x1401ca107  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x1401ca10e  mov     r9d, eax; char *
0x1401ca111  lea     edx, [r14+64h]; void *
0x1401ca115  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401ca11a  jmp     loc_1401CA499
0x1401ca11f  mov     rax, [rdi]
0x1401ca122  lea     rcx, [rbp+57h+var_50]
0x1401ca126  mov     [rbp+57h+var_50], r14
0x1401ca12a  mov     [rbp+57h+var_48], r14
0x1401ca12e  mov     rbx, [rax]
0x1401ca131  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401ca136  lea     r8, [rbp+57h+var_50]
0x1401ca13a  mov     rcx, rdi
0x1401ca13d  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x1401ca144  mov     rax, rbx
0x1401ca147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ca14c  mov     ebx, eax
0x1401ca14e  test    eax, eax
0x1401ca150  jns     short loc_1401CA159
0x1401ca152  mov     edx, 69h ; 'i'
0x1401ca157  jmp     short loc_1401CA18F
0x1401ca159  mov     r9d, 20h ; ' '; unsigned int
0x1401ca15f  mov     [rbp+57h+var_28], r14
0x1401ca163  lea     rdx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x1401ca16a  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1401ca16e  lea     r8d, [r9+1]; unsigned int
0x1401ca172  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1401ca177  mov     rcx, [rbp+57h+var_28]
0x1401ca17b  lea     rdx, [rbp+57h+var_48]
0x1401ca17f  call    ??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)
0x1401ca184  mov     ebx, eax
0x1401ca186  test    eax, eax
0x1401ca188  jns     short loc_1401CA1A7
0x1401ca18a  mov     edx, 6Ah ; 'j'; void *
0x1401ca18f  mov     rcx, [rbp+5Fh]; this
0x1401ca193  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x1401ca19a  mov     r9d, eax; char *
0x1401ca19d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401ca1a2  jmp     loc_1401CA487
0x1401ca1a7  lea     rdi, [rsi-10h]
0x1401ca1ab  mov     [rbp+57h+string], r14
0x1401ca1af  mov     rax, [rdi]
0x1401ca1b2  xor     ecx, ecx; string
0x1401ca1b4  mov     rbx, [rax+30h]
0x1401ca1b8  call    cs:__imp_WindowsDeleteString
0x1401ca1be  lea     rdx, [rbp+57h+string]
0x1401ca1c2  mov     [rbp+57h+string], r14
0x1401ca1c6  mov     rcx, rdi
0x1401ca1c9  mov     rax, rbx
0x1401ca1cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ca1d1  mov     ebx, eax
0x1401ca1d3  test    eax, eax
0x1401ca1d5  jns     short loc_1401CA1FE
0x1401ca1d7  mov     rcx, [rbp+5Fh]; this
0x1401ca1db  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x1401ca1e2  mov     r9d, eax; char *
0x1401ca1e5  mov     edx, 6Eh ; 'n'; void *
0x1401ca1ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401ca1ef  mov     rcx, [rbp+57h+string]; string
0x1401ca1f3  call    cs:__imp_WindowsDeleteString
0x1401ca1f9  jmp     loc_1401CA483
0x1401ca1fe  mov     rax, [rdi]
0x1401ca201  xor     ecx, ecx; string
0x1401ca203  mov     [rbp+57h+var_70], r14
0x1401ca207  mov     rbx, [rax+38h]
0x1401ca20b  call    cs:__imp_WindowsDeleteString
0x1401ca211  lea     rdx, [rbp+57h+var_70]
0x1401ca215  mov     [rbp+57h+var_70], r14
0x1401ca219  mov     rcx, rdi
0x1401ca21c  mov     rax, rbx
0x1401ca21f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ca224  mov     ebx, eax
0x1401ca226  test    eax, eax
0x1401ca228  jns     short loc_1401CA252
0x1401ca22a  mov     rcx, [rbp+5Fh]; this
0x1401ca22e  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x1401ca235  mov     r9d, eax; char *
0x1401ca238  mov     edx, 71h ; 'q'; void *
0x1401ca23d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401ca242  mov     rcx, [rbp+57h+var_70]; string
0x1401ca246  call    cs:__imp_WindowsDeleteString
0x1401ca24c  mov     [rbp+57h+var_70], r14
0x1401ca250  jmp     short loc_1401CA1EF
0x1401ca252  mov     rax, [rsi-8]
0x1401ca256  lea     rcx, [rbp+57h+var_68]
0x1401ca25a  mov     [rbp+57h+var_68], r14
0x1401ca25e  mov     rbx, [rax+30h]
0x1401ca262  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401ca267  lea     rdx, [rbp+57h+var_68]
0x1401ca26b  mov     rax, rbx
0x1401ca26e  lea     rcx, [rsi-8]
0x1401ca272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ca277  mov     ebx, eax
0x1401ca279  test    eax, eax
0x1401ca27b  jns     short loc_1401CA2A0
0x1401ca27d  mov     rcx, [rbp+5Fh]; this
0x1401ca281  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x1401ca288  mov     r9d, eax; char *
0x1401ca28b  mov     edx, 74h ; 't'; void *
0x1401ca290  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401ca295  lea     rcx, [rbp+57h+var_68]
0x1401ca299  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401ca29e  jmp     short loc_1401CA242
0x1401ca2a0  mov     rdi, [rbp+57h+var_48]
0x1401ca2a4  lea     rcx, [rbp+57h+var_60]
0x1401ca2a8  mov     [rbp+57h+var_60], r14
0x1401ca2ac  mov     rax, [rdi]
0x1401ca2af  mov     rbx, [rax+90h]
0x1401ca2b6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1401ca2bb  mov     rdx, [rbp+57h+string]
0x1401ca2bf  lea     r8, [rbp+57h+var_60]
0x1401ca2c3  mov     rcx, rdi
0x1401ca2c6  mov     rax, rbx
0x1401ca2c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ca2ce  mov     ebx, eax
0x1401ca2d0  test    eax, eax
0x1401ca2d2  jns     short loc_1401CA2F7
0x1401ca2d4  mov     edx, 78h ; 'x'; void *
0x1401ca2d9  mov     rcx, [rbp+5Fh]; this
0x1401ca2dd  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x1401ca2e4  mov     r9d, eax; char *
0x1401ca2e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401ca2ec  lea     rcx, [rbp+57h+var_60]
0x1401ca2f0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1401ca2f5  jmp     short loc_1401CA295
0x1401ca2f7  mov     rsi, [rbp+57h+var_50]
0x1401ca2fb  lea     rdx, aArguments; "Arguments"
0x1401ca302  mov     rbx, [rbp+57h+var_60]
0x1401ca306  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1401ca30a  mov     [rbp+57h+var_80], r14b
0x1401ca30e  mov     r9d, 9; unsigned int
0x1401ca314  mov     rax, [rsi]
0x1401ca317  mov     [rbp+57h+var_28], r14
0x1401ca31b  lea     r8d, [r9+1]; unsigned int
0x1401ca31f  mov     rdi, [rax+50h]
0x1401ca323  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1401ca328  mov     rdx, [rbp+57h+var_28]
0x1401ca32c  lea     r9, [rbp+57h+var_80]
0x1401ca330  mov     r8, rbx
0x1401ca333  mov     rcx, rsi
0x1401ca336  mov     rax, rdi
0x1401ca339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ca33e  mov     ebx, eax
0x1401ca340  test    eax, eax
0x1401ca342  jns     short loc_1401CA34B
0x1401ca344  mov     edx, 7Ah ; 'z'
0x1401ca349  jmp     short loc_1401CA2D9
0x1401ca34b  mov     rdi, [rbp+57h+var_48]
0x1401ca34f  lea     rcx, [rbp+57h+var_58]
0x1401ca353  mov     [rbp+57h+var_58], r14
0x1401ca357  mov     rax, [rdi]
0x1401ca35a  mov     rbx, [rax+90h]
0x1401ca361  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1401ca366  mov     rdx, [rbp+57h+var_70]
0x1401ca36a  lea     r8, [rbp+57h+var_58]
0x1401ca36e  mov     rcx, rdi
0x1401ca371  mov     rax, rbx
0x1401ca374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ca379  mov     ebx, eax
0x1401ca37b  test    eax, eax
0x1401ca37d  jns     short loc_1401CA3A5
0x1401ca37f  mov     edx, 7Dh ; '}'; void *
0x1401ca384  mov     rcx, [rbp+5Fh]; this
0x1401ca388  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x1401ca38f  mov     r9d, eax; char *
0x1401ca392  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401ca397  lea     rcx, [rbp+57h+var_58]
0x1401ca39b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1401ca3a0  jmp     loc_1401CA2EC
0x1401ca3a5  mov     rsi, [rbp+57h+var_50]
0x1401ca3a9  lea     rdx, aTileid; "TileId"
0x1401ca3b0  mov     rbx, [rbp+57h+var_58]
0x1401ca3b4  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1401ca3b8  mov     r9d, 6; unsigned int
0x1401ca3be  mov     rax, [rsi]
0x1401ca3c1  mov     [rbp+57h+var_28], r14
0x1401ca3c5  lea     r8d, [r9+1]; unsigned int
0x1401ca3c9  mov     rdi, [rax+50h]
0x1401ca3cd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1401ca3d2  mov     rdx, [rbp+57h+var_28]
0x1401ca3d6  lea     r9, [rbp+57h+var_80]
0x1401ca3da  mov     r8, rbx
0x1401ca3dd  mov     rcx, rsi
0x1401ca3e0  mov     rax, rdi
0x1401ca3e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ca3e8  mov     ebx, eax
0x1401ca3ea  test    eax, eax
0x1401ca3ec  jns     short loc_1401CA3F5
0x1401ca3ee  mov     edx, 7Eh ; '~'
0x1401ca3f3  jmp     short loc_1401CA384
0x1401ca3f5  mov     rbx, [rbp+57h+var_68]
0x1401ca3f9  test    rbx, rbx
0x1401ca3fc  jz      short loc_1401CA44D
0x1401ca3fe  mov     rsi, [rbp+57h+var_50]
0x1401ca402  lea     rdx, aTileactivatedi; "TileActivatedInfo"
0x1401ca409  mov     r9d, 11h; unsigned int
0x1401ca40f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1401ca413  mov     rax, [rsi]
0x1401ca416  lea     r8d, [r9+1]; unsigned int
0x1401ca41a  mov     [rbp+57h+var_28], r14
0x1401ca41e  mov     rdi, [rax+50h]
0x1401ca422  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1401ca427  mov     rdx, [rbp+57h+var_28]
0x1401ca42b  lea     r9, [rbp+57h+var_80]
0x1401ca42f  mov     r8, rbx
0x1401ca432  mov     rcx, rsi
0x1401ca435  mov     rax, rdi
0x1401ca438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ca43d  mov     ebx, eax
0x1401ca43f  test    eax, eax
0x1401ca441  jns     short loc_1401CA44D
0x1401ca443  mov     edx, 82h
0x1401ca448  jmp     loc_1401CA384
0x1401ca44d  lea     rcx, [rbp+57h+var_58]
0x1401ca451  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1401ca456  lea     rcx, [rbp+57h+var_60]
0x1401ca45a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1401ca45f  lea     rcx, [rbp+57h+var_68]
0x1401ca463  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401ca468  mov     rcx, [rbp+57h+var_70]; string
0x1401ca46c  call    cs:__imp_WindowsDeleteString
0x1401ca472  mov     rcx, [rbp+57h+string]; string
0x1401ca476  mov     [rbp+57h+var_70], r14
0x1401ca47a  call    cs:__imp_WindowsDeleteString
0x1401ca480  mov     ebx, r14d
0x1401ca483  mov     [rbp+57h+string], r14
0x1401ca487  lea     rcx, [rbp+57h+var_48]
0x1401ca48b  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401ca490  lea     rcx, [rbp+57h+var_50]
0x1401ca494  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401ca499  mov     eax, ebx
0x1401ca49b  mov     rcx, [rbp+57h+var_20]
0x1401ca49f  xor     rcx, rsp; StackCookie
0x1401ca4a2  call    __security_check_cookie
0x1401ca4a7  lea     r11, [rsp+0B0h+var_10]
0x1401ca4af  mov     rbx, [r11+30h]
0x1401ca4b3  mov     rsi, [r11+38h]
0x1401ca4b7  mov     rsp, r11
0x1401ca4ba  pop     r14
0x1401ca4bc  pop     rdi
0x1401ca4bd  pop     rbp
0x1401ca4be  retn
```
