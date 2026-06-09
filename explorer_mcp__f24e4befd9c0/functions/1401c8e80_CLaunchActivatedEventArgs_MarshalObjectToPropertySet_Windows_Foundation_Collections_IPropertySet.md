# CLaunchActivatedEventArgs::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x1401c8e80`
- end: `0x1401c92a4`
- name: `?MarshalObjectToPropertySet@CLaunchActivatedEventArgs@@UEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `1060`
- prototype: `__int64 __fastcall(CLaunchActivatedEventArgs *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140005d28`
- `0x140012594`
- `0x140082820`
- `0x14008843c`
- `0x14009ac68`
- `0x14010e160`
- `0x1401c8144`
- `0x1401c8e80`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c8f78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c8fb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c8fd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c9018`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c9244`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c9258`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c8f78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c8fb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c8fd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c9018`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c9244`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c9258`

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
0x1401c8e80  mov     [rsp-8+arg_10], rbx
0x1401c8e85  mov     [rsp-8+arg_18], rsi
0x1401c8e8a  push    rbp
0x1401c8e8b  push    rdi
0x1401c8e8c  push    r14
0x1401c8e8e  lea     rbp, [rsp-47h]
0x1401c8e93  sub     rsp, 0A0h
0x1401c8e9a  mov     rax, cs:__security_cookie
0x1401c8ea1  xor     rax, rsp
0x1401c8ea4  mov     [rbp+57h+var_20], rax
0x1401c8ea8  mov     rsi, rcx
0x1401c8eab  mov     rdi, rdx
0x1401c8eae  add     rcx, 0FFFFFFFFFFFFFF00h; this
0x1401c8eb5  call    ?MarshalObjectToPropertySet@CActivatedEventArgsWithPrelaunchAndViewIdBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z; CActivatedEventArgsWithPrelaunchAndViewIdBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)
0x1401c8eba  xor     r14d, r14d
0x1401c8ebd  mov     ebx, eax
0x1401c8ebf  test    eax, eax
0x1401c8ec1  jns     short loc_1401C8EDF
0x1401c8ec3  mov     rcx, [rbp+5Fh]; this
0x1401c8ec7  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x1401c8ece  mov     r9d, eax; char *
0x1401c8ed1  lea     edx, [r14+64h]; void *
0x1401c8ed5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401c8eda  jmp     loc_1401C927D
0x1401c8edf  mov     rax, [rdi]
0x1401c8ee2  lea     rcx, [rbp+57h+var_50]
0x1401c8ee6  mov     [rbp+57h+var_50], r14
0x1401c8eea  mov     [rbp+57h+var_48], r14
0x1401c8eee  mov     rbx, [rax]
0x1401c8ef1  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401c8ef6  lea     r8, [rbp+57h+var_50]
0x1401c8efa  mov     rcx, rdi
0x1401c8efd  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x1401c8f04  mov     rax, rbx
0x1401c8f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401c8f0c  mov     ebx, eax
0x1401c8f0e  test    eax, eax
0x1401c8f10  jns     short loc_1401C8F19
0x1401c8f12  mov     edx, 69h ; 'i'
0x1401c8f17  jmp     short loc_1401C8F4F
0x1401c8f19  mov     r9d, 20h ; ' '; unsigned int
0x1401c8f1f  mov     [rbp+57h+var_28], r14
0x1401c8f23  lea     rdx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x1401c8f2a  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1401c8f2e  lea     r8d, [r9+1]; unsigned int
0x1401c8f32  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1401c8f37  mov     rcx, [rbp+57h+var_28]
0x1401c8f3b  lea     rdx, [rbp+57h+var_48]
0x1401c8f3f  call    ??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)
0x1401c8f44  mov     ebx, eax
0x1401c8f46  test    eax, eax
0x1401c8f48  jns     short loc_1401C8F67
0x1401c8f4a  mov     edx, 6Ah ; 'j'; void *
0x1401c8f4f  mov     rcx, [rbp+5Fh]; this
0x1401c8f53  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x1401c8f5a  mov     r9d, eax; char *
0x1401c8f5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401c8f62  jmp     loc_1401C926B
0x1401c8f67  lea     rdi, [rsi-10h]
0x1401c8f6b  mov     [rbp+57h+string], r14
0x1401c8f6f  mov     rax, [rdi]
0x1401c8f72  xor     ecx, ecx; string
0x1401c8f74  mov     rbx, [rax+30h]
0x1401c8f78  call    cs:__imp_WindowsDeleteString
0x1401c8f7f  nop     dword ptr [rax+rax+00h]
0x1401c8f84  lea     rdx, [rbp+57h+string]
0x1401c8f88  mov     [rbp+57h+string], r14
0x1401c8f8c  mov     rcx, rdi
0x1401c8f8f  mov     rax, rbx
0x1401c8f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401c8f97  mov     ebx, eax
0x1401c8f99  test    eax, eax
0x1401c8f9b  jns     short loc_1401C8FCA
0x1401c8f9d  mov     rcx, [rbp+5Fh]; this
0x1401c8fa1  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x1401c8fa8  mov     r9d, eax; char *
0x1401c8fab  mov     edx, 6Eh ; 'n'; void *
0x1401c8fb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401c8fb5  mov     rcx, [rbp+57h+string]; string
0x1401c8fb9  call    cs:__imp_WindowsDeleteString
0x1401c8fc0  nop     dword ptr [rax+rax+00h]
0x1401c8fc5  jmp     loc_1401C9267
0x1401c8fca  mov     rax, [rdi]
0x1401c8fcd  xor     ecx, ecx; string
0x1401c8fcf  mov     [rbp+57h+var_70], r14
0x1401c8fd3  mov     rbx, [rax+38h]
0x1401c8fd7  call    cs:__imp_WindowsDeleteString
0x1401c8fde  nop     dword ptr [rax+rax+00h]
0x1401c8fe3  lea     rdx, [rbp+57h+var_70]
0x1401c8fe7  mov     [rbp+57h+var_70], r14
0x1401c8feb  mov     rcx, rdi
0x1401c8fee  mov     rax, rbx
0x1401c8ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401c8ff6  mov     ebx, eax
0x1401c8ff8  test    eax, eax
0x1401c8ffa  jns     short loc_1401C902A
0x1401c8ffc  mov     rcx, [rbp+5Fh]; this
0x1401c9000  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x1401c9007  mov     r9d, eax; char *
0x1401c900a  mov     edx, 71h ; 'q'; void *
0x1401c900f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401c9014  mov     rcx, [rbp+57h+var_70]; string
0x1401c9018  call    cs:__imp_WindowsDeleteString
0x1401c901f  nop     dword ptr [rax+rax+00h]
0x1401c9024  mov     [rbp+57h+var_70], r14
0x1401c9028  jmp     short loc_1401C8FB5
0x1401c902a  mov     rax, [rsi-8]
0x1401c902e  lea     rcx, [rbp+57h+var_68]
0x1401c9032  mov     [rbp+57h+var_68], r14
0x1401c9036  mov     rbx, [rax+30h]
0x1401c903a  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401c903f  lea     rdx, [rbp+57h+var_68]
0x1401c9043  mov     rax, rbx
0x1401c9046  lea     rcx, [rsi-8]
0x1401c904a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401c904f  mov     ebx, eax
0x1401c9051  test    eax, eax
0x1401c9053  jns     short loc_1401C9078
0x1401c9055  mov     rcx, [rbp+5Fh]; this
0x1401c9059  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x1401c9060  mov     r9d, eax; char *
0x1401c9063  mov     edx, 74h ; 't'; void *
0x1401c9068  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401c906d  lea     rcx, [rbp+57h+var_68]
0x1401c9071  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401c9076  jmp     short loc_1401C9014
0x1401c9078  mov     rdi, [rbp+57h+var_48]
0x1401c907c  lea     rcx, [rbp+57h+var_60]
0x1401c9080  mov     [rbp+57h+var_60], r14
0x1401c9084  mov     rax, [rdi]
0x1401c9087  mov     rbx, [rax+90h]
0x1401c908e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1401c9093  mov     rdx, [rbp+57h+string]
0x1401c9097  lea     r8, [rbp+57h+var_60]
0x1401c909b  mov     rcx, rdi
0x1401c909e  mov     rax, rbx
0x1401c90a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401c90a6  mov     ebx, eax
0x1401c90a8  test    eax, eax
0x1401c90aa  jns     short loc_1401C90CF
0x1401c90ac  mov     edx, 78h ; 'x'; void *
0x1401c90b1  mov     rcx, [rbp+5Fh]; this
0x1401c90b5  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x1401c90bc  mov     r9d, eax; char *
0x1401c90bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401c90c4  lea     rcx, [rbp+57h+var_60]
0x1401c90c8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1401c90cd  jmp     short loc_1401C906D
0x1401c90cf  mov     rsi, [rbp+57h+var_50]
0x1401c90d3  lea     rdx, aArguments; "Arguments"
0x1401c90da  mov     rbx, [rbp+57h+var_60]
0x1401c90de  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1401c90e2  mov     [rbp+57h+var_80], r14b
0x1401c90e6  mov     r9d, 9; unsigned int
0x1401c90ec  mov     rax, [rsi]
0x1401c90ef  mov     [rbp+57h+var_28], r14
0x1401c90f3  lea     r8d, [r9+1]; unsigned int
0x1401c90f7  mov     rdi, [rax+50h]
0x1401c90fb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1401c9100  mov     rdx, [rbp+57h+var_28]
0x1401c9104  lea     r9, [rbp+57h+var_80]
0x1401c9108  mov     r8, rbx
0x1401c910b  mov     rcx, rsi
0x1401c910e  mov     rax, rdi
0x1401c9111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401c9116  mov     ebx, eax
0x1401c9118  test    eax, eax
0x1401c911a  jns     short loc_1401C9123
0x1401c911c  mov     edx, 7Ah ; 'z'
0x1401c9121  jmp     short loc_1401C90B1
0x1401c9123  mov     rdi, [rbp+57h+var_48]
0x1401c9127  lea     rcx, [rbp+57h+var_58]
0x1401c912b  mov     [rbp+57h+var_58], r14
0x1401c912f  mov     rax, [rdi]
0x1401c9132  mov     rbx, [rax+90h]
0x1401c9139  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1401c913e  mov     rdx, [rbp+57h+var_70]
0x1401c9142  lea     r8, [rbp+57h+var_58]
0x1401c9146  mov     rcx, rdi
0x1401c9149  mov     rax, rbx
0x1401c914c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401c9151  mov     ebx, eax
0x1401c9153  test    eax, eax
0x1401c9155  jns     short loc_1401C917D
0x1401c9157  mov     edx, 7Dh ; '}'; void *
0x1401c915c  mov     rcx, [rbp+5Fh]; this
0x1401c9160  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x1401c9167  mov     r9d, eax; char *
0x1401c916a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401c916f  lea     rcx, [rbp+57h+var_58]
0x1401c9173  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1401c9178  jmp     loc_1401C90C4
0x1401c917d  mov     rsi, [rbp+57h+var_50]
0x1401c9181  lea     rdx, aTileid; "TileId"
0x1401c9188  mov     rbx, [rbp+57h+var_58]
0x1401c918c  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1401c9190  mov     r9d, 6; unsigned int
0x1401c9196  mov     rax, [rsi]
0x1401c9199  mov     [rbp+57h+var_28], r14
0x1401c919d  lea     r8d, [r9+1]; unsigned int
0x1401c91a1  mov     rdi, [rax+50h]
0x1401c91a5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1401c91aa  mov     rdx, [rbp+57h+var_28]
0x1401c91ae  lea     r9, [rbp+57h+var_80]
0x1401c91b2  mov     r8, rbx
0x1401c91b5  mov     rcx, rsi
0x1401c91b8  mov     rax, rdi
0x1401c91bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401c91c0  mov     ebx, eax
0x1401c91c2  test    eax, eax
0x1401c91c4  jns     short loc_1401C91CD
0x1401c91c6  mov     edx, 7Eh ; '~'
0x1401c91cb  jmp     short loc_1401C915C
0x1401c91cd  mov     rbx, [rbp+57h+var_68]
0x1401c91d1  test    rbx, rbx
0x1401c91d4  jz      short loc_1401C9225
0x1401c91d6  mov     rsi, [rbp+57h+var_50]
0x1401c91da  lea     rdx, aTileactivatedi; "TileActivatedInfo"
0x1401c91e1  mov     r9d, 11h; unsigned int
0x1401c91e7  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1401c91eb  mov     rax, [rsi]
0x1401c91ee  lea     r8d, [r9+1]; unsigned int
0x1401c91f2  mov     [rbp+57h+var_28], r14
0x1401c91f6  mov     rdi, [rax+50h]
0x1401c91fa  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1401c91ff  mov     rdx, [rbp+57h+var_28]
0x1401c9203  lea     r9, [rbp+57h+var_80]
0x1401c9207  mov     r8, rbx
0x1401c920a  mov     rcx, rsi
0x1401c920d  mov     rax, rdi
0x1401c9210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401c9215  mov     ebx, eax
0x1401c9217  test    eax, eax
0x1401c9219  jns     short loc_1401C9225
0x1401c921b  mov     edx, 82h
0x1401c9220  jmp     loc_1401C915C
0x1401c9225  lea     rcx, [rbp+57h+var_58]
0x1401c9229  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1401c922e  lea     rcx, [rbp+57h+var_60]
0x1401c9232  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1401c9237  lea     rcx, [rbp+57h+var_68]
0x1401c923b  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401c9240  mov     rcx, [rbp+57h+var_70]; string
0x1401c9244  call    cs:__imp_WindowsDeleteString
0x1401c924b  nop     dword ptr [rax+rax+00h]
0x1401c9250  mov     rcx, [rbp+57h+string]; string
0x1401c9254  mov     [rbp+57h+var_70], r14
0x1401c9258  call    cs:__imp_WindowsDeleteString
0x1401c925f  nop     dword ptr [rax+rax+00h]
0x1401c9264  mov     ebx, r14d
0x1401c9267  mov     [rbp+57h+string], r14
0x1401c926b  lea     rcx, [rbp+57h+var_48]
0x1401c926f  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401c9274  lea     rcx, [rbp+57h+var_50]
0x1401c9278  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401c927d  mov     eax, ebx
0x1401c927f  mov     rcx, [rbp+57h+var_20]
0x1401c9283  xor     rcx, rsp; StackCookie
0x1401c9286  call    __security_check_cookie
0x1401c928b  lea     r11, [rsp+0B0h+var_10]
0x1401c9293  mov     rbx, [r11+30h]
0x1401c9297  mov     rsi, [r11+38h]
0x1401c929b  mov     rsp, r11
0x1401c929e  pop     r14
0x1401c92a0  pop     rdi
0x1401c92a1  pop     rbp
0x1401c92a2  retn
```
