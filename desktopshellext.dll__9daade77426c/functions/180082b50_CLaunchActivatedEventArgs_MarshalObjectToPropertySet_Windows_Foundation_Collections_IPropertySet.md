# CLaunchActivatedEventArgs::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x180082b50`
- end: `0x180082f4f`
- name: `?MarshalObjectToPropertySet@CLaunchActivatedEventArgs@@UEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `1023`
- prototype: `__int64 __fastcall(CLaunchActivatedEventArgs *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180017930`
- `0x18001795c`
- `0x180017988`
- `0x18002a3d0`
- `0x180081110`
- `0x1800817e0`
- `0x180081b7c`
- `0x180082b50`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082c48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082c83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082c9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082cd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082efc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082f0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082c48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082c83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082c9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082cd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082efc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082f0a`

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
    Microsoft::WRL::ComPtr<IAgileObject>::InternalRelease(&v46);
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
      Microsoft::WRL::ComPtr<IAgileObject>::InternalRelease(&v47);
      Microsoft::WRL::ComPtr<IAgileObject>::InternalRelease(&v46);
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
    Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v44);
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
        Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v45);
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
              Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v45);
              Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v44);
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
        Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v45);
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
    Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v44);
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
0x180082b50  mov     [rsp-8+arg_10], rbx
0x180082b55  mov     [rsp-8+arg_18], rsi
0x180082b5a  push    rbp
0x180082b5b  push    rdi
0x180082b5c  push    r14
0x180082b5e  lea     rbp, [rsp-47h]
0x180082b63  sub     rsp, 0A0h
0x180082b6a  mov     rax, cs:__security_cookie
0x180082b71  xor     rax, rsp
0x180082b74  mov     [rbp+57h+var_20], rax
0x180082b78  mov     rsi, rcx
0x180082b7b  mov     rdi, rdx
0x180082b7e  add     rcx, 0FFFFFFFFFFFFFF00h; this
0x180082b85  call    ?MarshalObjectToPropertySet@CActivatedEventArgsWithPrelaunchAndViewIdBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z; CActivatedEventArgsWithPrelaunchAndViewIdBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)
0x180082b8a  xor     r14d, r14d
0x180082b8d  mov     ebx, eax
0x180082b8f  test    eax, eax
0x180082b91  jns     short loc_180082BAF
0x180082b93  mov     rcx, [rbp+5Fh]; this
0x180082b97  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x180082b9e  mov     r9d, eax; char *
0x180082ba1  lea     edx, [r14+64h]; void *
0x180082ba5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082baa  jmp     loc_180082F29
0x180082baf  mov     rax, [rdi]
0x180082bb2  lea     rcx, [rbp+57h+var_50]
0x180082bb6  mov     [rbp+57h+var_50], r14
0x180082bba  mov     [rbp+57h+var_48], r14
0x180082bbe  mov     rbx, [rax]
0x180082bc1  call    ?InternalRelease@?$ComPtr@UIAgileObject@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAgileObject>::InternalRelease(void)
0x180082bc6  lea     r8, [rbp+57h+var_50]
0x180082bca  mov     rcx, rdi
0x180082bcd  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180082bd4  mov     rax, rbx
0x180082bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082bdc  mov     ebx, eax
0x180082bde  test    eax, eax
0x180082be0  jns     short loc_180082BE9
0x180082be2  mov     edx, 69h ; 'i'
0x180082be7  jmp     short loc_180082C1F
0x180082be9  mov     r9d, 20h ; ' '; unsigned int
0x180082bef  mov     [rbp+57h+var_28], r14
0x180082bf3  lea     rdx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x180082bfa  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180082bfe  lea     r8d, [r9+1]; unsigned int
0x180082c02  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180082c07  mov     rcx, [rbp+57h+var_28]
0x180082c0b  lea     rdx, [rbp+57h+var_48]
0x180082c0f  call    ??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)
0x180082c14  mov     ebx, eax
0x180082c16  test    eax, eax
0x180082c18  jns     short loc_180082C37
0x180082c1a  mov     edx, 6Ah ; 'j'; void *
0x180082c1f  mov     rcx, [rbp+5Fh]; this
0x180082c23  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x180082c2a  mov     r9d, eax; char *
0x180082c2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082c32  jmp     loc_180082F17
0x180082c37  lea     rdi, [rsi-10h]
0x180082c3b  mov     [rbp+57h+string], r14
0x180082c3f  mov     rax, [rdi]
0x180082c42  xor     ecx, ecx; string
0x180082c44  mov     rbx, [rax+30h]
0x180082c48  call    cs:__imp_WindowsDeleteString
0x180082c4e  lea     rdx, [rbp+57h+string]
0x180082c52  mov     [rbp+57h+string], r14
0x180082c56  mov     rcx, rdi
0x180082c59  mov     rax, rbx
0x180082c5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082c61  mov     ebx, eax
0x180082c63  test    eax, eax
0x180082c65  jns     short loc_180082C8E
0x180082c67  mov     rcx, [rbp+5Fh]; this
0x180082c6b  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x180082c72  mov     r9d, eax; char *
0x180082c75  mov     edx, 6Eh ; 'n'; void *
0x180082c7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082c7f  mov     rcx, [rbp+57h+string]; string
0x180082c83  call    cs:__imp_WindowsDeleteString
0x180082c89  jmp     loc_180082F13
0x180082c8e  mov     rax, [rdi]
0x180082c91  xor     ecx, ecx; string
0x180082c93  mov     [rbp+57h+var_70], r14
0x180082c97  mov     rbx, [rax+38h]
0x180082c9b  call    cs:__imp_WindowsDeleteString
0x180082ca1  lea     rdx, [rbp+57h+var_70]
0x180082ca5  mov     [rbp+57h+var_70], r14
0x180082ca9  mov     rcx, rdi
0x180082cac  mov     rax, rbx
0x180082caf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082cb4  mov     ebx, eax
0x180082cb6  test    eax, eax
0x180082cb8  jns     short loc_180082CE2
0x180082cba  mov     rcx, [rbp+5Fh]; this
0x180082cbe  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x180082cc5  mov     r9d, eax; char *
0x180082cc8  mov     edx, 71h ; 'q'; void *
0x180082ccd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082cd2  mov     rcx, [rbp+57h+var_70]; string
0x180082cd6  call    cs:__imp_WindowsDeleteString
0x180082cdc  mov     [rbp+57h+var_70], r14
0x180082ce0  jmp     short loc_180082C7F
0x180082ce2  mov     rax, [rsi-8]
0x180082ce6  lea     rcx, [rbp+57h+var_68]
0x180082cea  mov     [rbp+57h+var_68], r14
0x180082cee  mov     rbx, [rax+30h]
0x180082cf2  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x180082cf7  lea     rdx, [rbp+57h+var_68]
0x180082cfb  mov     rax, rbx
0x180082cfe  lea     rcx, [rsi-8]
0x180082d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082d07  mov     ebx, eax
0x180082d09  test    eax, eax
0x180082d0b  jns     short loc_180082D30
0x180082d0d  mov     rcx, [rbp+5Fh]; this
0x180082d11  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x180082d18  mov     r9d, eax; char *
0x180082d1b  mov     edx, 74h ; 't'; void *
0x180082d20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082d25  lea     rcx, [rbp+57h+var_68]
0x180082d29  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x180082d2e  jmp     short loc_180082CD2
0x180082d30  mov     rdi, [rbp+57h+var_48]
0x180082d34  lea     rcx, [rbp+57h+var_60]
0x180082d38  mov     [rbp+57h+var_60], r14
0x180082d3c  mov     rax, [rdi]
0x180082d3f  mov     rbx, [rax+90h]
0x180082d46  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x180082d4b  mov     rdx, [rbp+57h+string]
0x180082d4f  lea     r8, [rbp+57h+var_60]
0x180082d53  mov     rcx, rdi
0x180082d56  mov     rax, rbx
0x180082d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082d5e  mov     ebx, eax
0x180082d60  test    eax, eax
0x180082d62  jns     short loc_180082D87
0x180082d64  mov     edx, 78h ; 'x'; void *
0x180082d69  mov     rcx, [rbp+5Fh]; this
0x180082d6d  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x180082d74  mov     r9d, eax; char *
0x180082d77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082d7c  lea     rcx, [rbp+57h+var_60]
0x180082d80  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x180082d85  jmp     short loc_180082D25
0x180082d87  mov     rsi, [rbp+57h+var_50]
0x180082d8b  lea     rdx, aArguments; "Arguments"
0x180082d92  mov     rbx, [rbp+57h+var_60]
0x180082d96  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180082d9a  mov     [rbp+57h+var_80], r14b
0x180082d9e  mov     r9d, 9; unsigned int
0x180082da4  mov     rax, [rsi]
0x180082da7  mov     [rbp+57h+var_28], r14
0x180082dab  lea     r8d, [r9+1]; unsigned int
0x180082daf  mov     rdi, [rax+50h]
0x180082db3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180082db8  mov     rdx, [rbp+57h+var_28]
0x180082dbc  lea     r9, [rbp+57h+var_80]
0x180082dc0  mov     r8, rbx
0x180082dc3  mov     rcx, rsi
0x180082dc6  mov     rax, rdi
0x180082dc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082dce  mov     ebx, eax
0x180082dd0  test    eax, eax
0x180082dd2  jns     short loc_180082DDB
0x180082dd4  mov     edx, 7Ah ; 'z'
0x180082dd9  jmp     short loc_180082D69
0x180082ddb  mov     rdi, [rbp+57h+var_48]
0x180082ddf  lea     rcx, [rbp+57h+var_58]
0x180082de3  mov     [rbp+57h+var_58], r14
0x180082de7  mov     rax, [rdi]
0x180082dea  mov     rbx, [rax+90h]
0x180082df1  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x180082df6  mov     rdx, [rbp+57h+var_70]
0x180082dfa  lea     r8, [rbp+57h+var_58]
0x180082dfe  mov     rcx, rdi
0x180082e01  mov     rax, rbx
0x180082e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082e09  mov     ebx, eax
0x180082e0b  test    eax, eax
0x180082e0d  jns     short loc_180082E35
0x180082e0f  mov     edx, 7Dh ; '}'; void *
0x180082e14  mov     rcx, [rbp+5Fh]; this
0x180082e18  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x180082e1f  mov     r9d, eax; char *
0x180082e22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082e27  lea     rcx, [rbp+57h+var_58]
0x180082e2b  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x180082e30  jmp     loc_180082D7C
0x180082e35  mov     rsi, [rbp+57h+var_50]
0x180082e39  lea     rdx, aTileid; "TileId"
0x180082e40  mov     rbx, [rbp+57h+var_58]
0x180082e44  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180082e48  mov     r9d, 6; unsigned int
0x180082e4e  mov     rax, [rsi]
0x180082e51  mov     [rbp+57h+var_28], r14
0x180082e55  lea     r8d, [r9+1]; unsigned int
0x180082e59  mov     rdi, [rax+50h]
0x180082e5d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180082e62  mov     rdx, [rbp+57h+var_28]
0x180082e66  lea     r9, [rbp+57h+var_80]
0x180082e6a  mov     r8, rbx
0x180082e6d  mov     rcx, rsi
0x180082e70  mov     rax, rdi
0x180082e73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082e78  mov     ebx, eax
0x180082e7a  test    eax, eax
0x180082e7c  jns     short loc_180082E85
0x180082e7e  mov     edx, 7Eh ; '~'
0x180082e83  jmp     short loc_180082E14
0x180082e85  mov     rbx, [rbp+57h+var_68]
0x180082e89  test    rbx, rbx
0x180082e8c  jz      short loc_180082EDD
0x180082e8e  mov     rsi, [rbp+57h+var_50]
0x180082e92  lea     rdx, aTileactivatedi; "TileActivatedInfo"
0x180082e99  mov     r9d, 11h; unsigned int
0x180082e9f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180082ea3  mov     rax, [rsi]
0x180082ea6  lea     r8d, [r9+1]; unsigned int
0x180082eaa  mov     [rbp+57h+var_28], r14
0x180082eae  mov     rdi, [rax+50h]
0x180082eb2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180082eb7  mov     rdx, [rbp+57h+var_28]
0x180082ebb  lea     r9, [rbp+57h+var_80]
0x180082ebf  mov     r8, rbx
0x180082ec2  mov     rcx, rsi
0x180082ec5  mov     rax, rdi
0x180082ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082ecd  mov     ebx, eax
0x180082ecf  test    eax, eax
0x180082ed1  jns     short loc_180082EDD
0x180082ed3  mov     edx, 82h
0x180082ed8  jmp     loc_180082E14
0x180082edd  lea     rcx, [rbp+57h+var_58]
0x180082ee1  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x180082ee6  lea     rcx, [rbp+57h+var_60]
0x180082eea  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x180082eef  lea     rcx, [rbp+57h+var_68]
0x180082ef3  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x180082ef8  mov     rcx, [rbp+57h+var_70]; string
0x180082efc  call    cs:__imp_WindowsDeleteString
0x180082f02  mov     rcx, [rbp+57h+string]; string
0x180082f06  mov     [rbp+57h+var_70], r14
0x180082f0a  call    cs:__imp_WindowsDeleteString
0x180082f10  mov     ebx, r14d
0x180082f13  mov     [rbp+57h+string], r14
0x180082f17  lea     rcx, [rbp+57h+var_48]
0x180082f1b  call    ?InternalRelease@?$ComPtr@UIAgileObject@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAgileObject>::InternalRelease(void)
0x180082f20  lea     rcx, [rbp+57h+var_50]
0x180082f24  call    ?InternalRelease@?$ComPtr@UIAgileObject@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAgileObject>::InternalRelease(void)
0x180082f29  mov     eax, ebx
0x180082f2b  mov     rcx, [rbp+57h+var_20]
0x180082f2f  xor     rcx, rsp; StackCookie
0x180082f32  call    __security_check_cookie
0x180082f37  lea     r11, [rsp+0B0h+var_10]
0x180082f3f  mov     rbx, [r11+30h]
0x180082f43  mov     rsi, [r11+38h]
0x180082f47  mov     rsp, r11
0x180082f4a  pop     r14
0x180082f4c  pop     rdi
0x180082f4d  pop     rbp
0x180082f4e  retn
```
