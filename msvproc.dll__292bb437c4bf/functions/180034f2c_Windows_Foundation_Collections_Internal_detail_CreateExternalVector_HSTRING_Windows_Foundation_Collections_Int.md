# Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0> * *)

- ea: `0x180034f2c`
- end: `0x180035054`
- name: `??$CreateExternalVector@PEAUHSTRING__@@V?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@1234@@Z`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180018f2c`

## callees

- `0x18000a09c`
- `0x180034f2c`
- `0x180054140`
- `0x1800ca44c`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180034f99`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180034f99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180034f83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180034f83`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180034faf`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180034faf`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(
        __int64 a1,
        _QWORD *a2)
{
  HRESULT v3; // eax
  int ActivationFactory; // ebx
  __int64 v5; // rcx
  __int64 v7; // rbx
  __int64 v8; // [rsp+20h] [rbp-40h] BYREF
  __int64 v9; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-18h] BYREF

  *a2 = 0;
  v8 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v8);
  string = 0;
  v3 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &hstringHeader, &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v8);
  if ( ActivationFactory < 0 )
  {
    v5 = v8;
    if ( v8 )
    {
      v8 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    return (unsigned int)ActivationFactory;
  }
  v7 = v8;
  v9 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{216,{flat}}(v7, &v9);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v8);
    return (unsigned int)ActivationFactory;
  }
  *a2 = v9;
  v9 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v8);
  return 0;
}

```

## disassembly

```asm
0x180034f2c  mov     [rsp-8+arg_0], rbx
0x180034f31  mov     [rsp-8+arg_10], rdi
0x180034f36  push    rbp
0x180034f37  mov     rbp, rsp
0x180034f3a  sub     rsp, 60h
0x180034f3e  mov     rax, cs:__security_cookie
0x180034f45  xor     rax, rsp
0x180034f48  mov     [rbp+var_10], rax
0x180034f4c  lea     rcx, [rbp+var_40]
0x180034f50  mov     qword ptr [rdx], 0
0x180034f57  mov     rdi, rdx
0x180034f5a  mov     [rbp+var_40], 0
0x180034f62  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180034f67  lea     r9, [rbp+string]; string
0x180034f6b  mov     [rbp+string], 0
0x180034f73  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180034f77  mov     edx, 2Ch ; ','; length
0x180034f7c  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180034f83  call    cs:__imp_WindowsCreateStringReference
0x180034f89  test    eax, eax
0x180034f8b  jns     short loc_180034FA0
0x180034f8d  xor     r9d, r9d; lpArguments
0x180034f90  xor     r8d, r8d; nNumberOfArguments
0x180034f93  mov     ecx, eax; dwExceptionCode
0x180034f95  lea     edx, [r9+1]; dwExceptionFlags
0x180034f99  call    cs:__imp_RaiseException
0x180034f9f  int     3; Trap to Debugger
0x180034fa0  mov     rcx, [rbp+string]
0x180034fa4  lea     r8, [rbp+var_40]
0x180034fa8  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180034faf  call    cs:__imp_RoGetActivationFactory
0x180034fb5  mov     ebx, eax
0x180034fb7  test    eax, eax
0x180034fb9  jns     short loc_180034FDC
0x180034fbb  mov     rcx, [rbp+var_40]
0x180034fbf  test    rcx, rcx
0x180034fc2  jz      short loc_180034FD8
0x180034fc4  mov     [rbp+var_40], 0
0x180034fcc  mov     rdx, [rcx]
0x180034fcf  mov     rax, [rdx+10h]
0x180034fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034fd8  mov     eax, ebx
0x180034fda  jmp     short loc_180035036
0x180034fdc  mov     rbx, [rbp+var_40]
0x180034fe0  lea     rcx, [rbp+var_38]
0x180034fe4  mov     [rbp+var_38], 0
0x180034fec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180034ff1  lea     rdx, [rbp+var_38]
0x180034ff5  mov     rcx, rbx
0x180034ff8  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BNI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{216,{flat}}
0x180034ffd  lea     rcx, [rbp+var_38]
0x180035001  mov     ebx, eax
0x180035003  test    eax, eax
0x180035005  jns     short loc_180035017
0x180035007  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003500c  lea     rcx, [rbp+var_40]
0x180035010  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180035015  jmp     short loc_180034FD8
0x180035017  mov     rax, [rbp+var_38]
0x18003501b  mov     [rdi], rax
0x18003501e  mov     [rbp+var_38], 0
0x180035026  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003502b  lea     rcx, [rbp+var_40]
0x18003502f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180035034  xor     eax, eax
0x180035036  mov     rcx, [rbp+var_10]
0x18003503a  xor     rcx, rsp; StackCookie
0x18003503d  call    __security_check_cookie
0x180035042  lea     r11, [rsp+60h+var_s0]
0x180035047  mov     rbx, [r11+10h]
0x18003504b  mov     rdi, [r11+20h]
0x18003504f  mov     rsp, r11
0x180035052  pop     rbp
0x180035053  retn
```
