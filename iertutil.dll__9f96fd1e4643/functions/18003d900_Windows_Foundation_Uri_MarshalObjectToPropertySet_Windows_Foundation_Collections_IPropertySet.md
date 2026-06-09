# Windows::Foundation::Uri::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x18003d900`
- end: `0x18003db0b`
- name: `?MarshalObjectToPropertySet@Uri@Foundation@Windows@@UEAAJPEAUIPropertySet@Collections@23@@Z`
- size: `523`
- prototype: `__int64 __fastcall(Windows::Foundation::Uri *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180026834`
- `0x18003d900`
- `0x180083c10`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003daf1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003db04`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003daf1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003db04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003d979`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003daa0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003d979`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003daa0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d9bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d9e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d9bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d9e3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003d9a2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003d9a2`

## string_xrefs

- `0x18003da8d`: `RawUri`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Uri::MarshalObjectToPropertySet(
        Windows::Foundation::Uri *this,
        struct Windows::Foundation::Collections::IPropertySet *a2)
{
  __int64 (__fastcall **v2)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **); // rax
  __int64 (__fastcall *v5)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **); // rbx
  int ActivationFactory; // ebx
  HRESULT v7; // eax
  HSTRING v8; // rbx
  __int64 (__fastcall *v9)(char *, HSTRING *); // rbx
  __int64 v10; // rcx
  _QWORD *v11; // rcx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING, __int64 *); // rbx
  _QWORD *v15; // rbx
  __int64 v16; // rsi
  __int64 v17; // rdi
  HRESULT v18; // eax
  __int64 v19; // rcx
  _BYTE v20[8]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v21; // [rsp+38h] [rbp-48h] BYREF
  HSTRING v22; // [rsp+40h] [rbp-40h] BYREF
  __int64 v23; // [rsp+48h] [rbp-38h] BYREF
  _QWORD *v24; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  HSTRING string; // [rsp+70h] [rbp-10h] BYREF

  v2 = *(__int64 (__fastcall ***)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **))a2;
  v24 = 0;
  v23 = 0;
  v5 = *v2;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  ActivationFactory = v5(a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v24);
  if ( ActivationFactory >= 0 )
  {
    string = 0;
    v7 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string);
    if ( v7 < 0 )
    {
      RaiseException(v7, 1u, 0, 0);
      __debugbreak();
    }
    v8 = string;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
    ActivationFactory = RoGetActivationFactory(v8, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v23);
  }
  v22 = 0;
  if ( ActivationFactory >= 0 )
  {
    v9 = *(__int64 (__fastcall **)(char *, HSTRING *))(*((_QWORD *)this - 4) + 128LL);
    WindowsDeleteString(0);
    v22 = 0;
    ActivationFactory = v9((char *)this - 32, &v22);
    if ( ActivationFactory >= 0 )
    {
      v13 = v23;
      v21 = 0;
      v14 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v23 + 144LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
      ActivationFactory = v14(v13, v22, &v21);
      if ( ActivationFactory >= 0 )
      {
        v15 = v24;
        v16 = v21;
        v20[0] = 0;
        v17 = *v24;
        string = 0;
        v18 = WindowsCreateStringReference(L"RawUri", 6u, &hstringHeader, &string);
        if ( v18 < 0 )
        {
          RaiseException(v18, 1u, 0, 0);
          JUMPOUT(0x18003DB0ALL);
        }
        ActivationFactory = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v17 + 80))(
                              v15,
                              string,
                              v16,
                              v20);
      }
      v19 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
    }
  }
  WindowsDeleteString(v22);
  v10 = v23;
  v22 = 0;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v11 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v11 + 16LL))(v11);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18003d900  mov     [rsp-18h+arg_10], rbx
0x18003d905  mov     [rsp-18h+arg_18], rsi
0x18003d90a  push    rbp
0x18003d90b  push    rdi
0x18003d90c  push    r14
0x18003d90e  mov     rbp, rsp
0x18003d911  sub     rsp, 80h
0x18003d918  mov     rax, cs:__security_cookie
0x18003d91f  xor     rax, rsp
0x18003d922  mov     [rbp+var_8], rax
0x18003d926  mov     rax, [rdx]
0x18003d929  mov     rsi, rcx
0x18003d92c  xor     r14d, r14d
0x18003d92f  lea     rcx, [rbp+var_30]
0x18003d933  mov     rdi, rdx
0x18003d936  mov     [rbp+var_30], r14
0x18003d93a  mov     [rbp+var_38], r14
0x18003d93e  mov     rbx, [rax]
0x18003d941  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d946  lea     r8, [rbp+var_30]
0x18003d94a  mov     rcx, rdi
0x18003d94d  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18003d954  mov     rax, rbx
0x18003d957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d95c  mov     ebx, eax
0x18003d95e  test    eax, eax
0x18003d960  js      short loc_18003D9AA
0x18003d962  lea     r9, [rbp+string]; string
0x18003d966  mov     [rbp+string], r14
0x18003d96a  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003d96e  lea     edx, [r14+20h]; length
0x18003d972  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18003d979  call    cs:__imp_WindowsCreateStringReference
0x18003d97f  test    eax, eax
0x18003d981  js      loc_18003DAE5
0x18003d987  mov     rbx, [rbp+string]
0x18003d98b  lea     rcx, [rbp+var_38]
0x18003d98f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d994  lea     r8, [rbp+var_38]
0x18003d998  mov     rcx, rbx
0x18003d99b  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x18003d9a2  call    cs:__imp_RoGetActivationFactory
0x18003d9a8  mov     ebx, eax
0x18003d9aa  mov     [rbp+var_40], r14
0x18003d9ae  test    ebx, ebx
0x18003d9b0  js      short loc_18003D9DF
0x18003d9b2  mov     rax, [rsi-20h]
0x18003d9b6  xor     ecx, ecx; string
0x18003d9b8  mov     rbx, [rax+80h]
0x18003d9bf  call    cs:__imp_WindowsDeleteString
0x18003d9c5  lea     rdx, [rbp+var_40]
0x18003d9c9  mov     [rbp+var_40], r14
0x18003d9cd  lea     rcx, [rsi-20h]
0x18003d9d1  mov     rax, rbx
0x18003d9d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d9d9  mov     ebx, eax
0x18003d9db  test    eax, eax
0x18003d9dd  jns     short loc_18003DA45
0x18003d9df  mov     rcx, [rbp+var_40]; string
0x18003d9e3  call    cs:__imp_WindowsDeleteString
0x18003d9e9  mov     rcx, [rbp+var_38]
0x18003d9ed  mov     [rbp+var_40], r14
0x18003d9f1  test    rcx, rcx
0x18003d9f4  jz      short loc_18003DA06
0x18003d9f6  mov     [rbp+var_38], r14
0x18003d9fa  mov     rax, [rcx]
0x18003d9fd  mov     rax, [rax+10h]
0x18003da01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da06  mov     rcx, [rbp+var_30]
0x18003da0a  test    rcx, rcx
0x18003da0d  jz      short loc_18003DA1F
0x18003da0f  mov     [rbp+var_30], r14
0x18003da13  mov     rax, [rcx]
0x18003da16  mov     rax, [rax+10h]
0x18003da1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da1f  mov     eax, ebx
0x18003da21  mov     rcx, [rbp+var_8]
0x18003da25  xor     rcx, rsp; StackCookie
0x18003da28  call    __security_check_cookie
0x18003da2d  lea     r11, [rsp+80h+var_s0]
0x18003da35  mov     rbx, [r11+30h]
0x18003da39  mov     rsi, [r11+38h]
0x18003da3d  mov     rsp, r11
0x18003da40  pop     r14
0x18003da42  pop     rdi
0x18003da43  pop     rbp
0x18003da44  retn
0x18003da45  mov     rdi, [rbp+var_38]
0x18003da49  lea     rcx, [rbp+var_48]
0x18003da4d  mov     [rbp+var_48], r14
0x18003da51  mov     rax, [rdi]
0x18003da54  mov     rbx, [rax+90h]
0x18003da5b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003da60  mov     rdx, [rbp+var_40]
0x18003da64  lea     r8, [rbp+var_48]
0x18003da68  mov     rcx, rdi
0x18003da6b  mov     rax, rbx
0x18003da6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da73  mov     ebx, eax
0x18003da75  test    eax, eax
0x18003da77  js      short loc_18003DAC3
0x18003da79  mov     rbx, [rbp+var_30]
0x18003da7d  lea     r9, [rbp+string]; string
0x18003da81  mov     rsi, [rbp+var_48]
0x18003da85  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003da89  mov     [rbp+var_50], r14b
0x18003da8d  lea     rcx, sourceString; "RawUri"
0x18003da94  mov     edx, 6; length
0x18003da99  mov     rdi, [rbx]
0x18003da9c  mov     [rbp+string], r14
0x18003daa0  call    cs:__imp_WindowsCreateStringReference
0x18003daa6  test    eax, eax
0x18003daa8  js      short loc_18003DAF8
0x18003daaa  mov     rdx, [rbp+string]
0x18003daae  lea     r9, [rbp+var_50]
0x18003dab2  mov     rax, [rdi+50h]
0x18003dab6  mov     r8, rsi
0x18003dab9  mov     rcx, rbx
0x18003dabc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dac1  mov     ebx, eax
0x18003dac3  mov     rcx, [rbp+var_48]
0x18003dac7  test    rcx, rcx
0x18003daca  jz      loc_18003D9DF
0x18003dad0  mov     [rbp+var_48], r14
0x18003dad4  mov     rax, [rcx]
0x18003dad7  mov     rax, [rax+10h]
0x18003dadb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dae0  jmp     loc_18003D9DF
0x18003dae5  xor     r9d, r9d; lpArguments
0x18003dae8  xor     r8d, r8d; nNumberOfArguments
0x18003daeb  mov     ecx, eax; dwExceptionCode
0x18003daed  lea     edx, [r9+1]; dwExceptionFlags
0x18003daf1  call    cs:__imp_RaiseException
0x18003daf7  int     3; Trap to Debugger
0x18003daf8  xor     r9d, r9d; lpArguments
0x18003dafb  xor     r8d, r8d; nNumberOfArguments
0x18003dafe  mov     ecx, eax; dwExceptionCode
0x18003db00  lea     edx, [r9+1]; dwExceptionFlags
0x18003db04  call    cs:__imp_RaiseException
```
