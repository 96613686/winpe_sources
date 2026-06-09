# Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)

- ea: `0x18004ffb4`
- end: `0x1800500bf`
- name: `??$CreateExternalVector@PEAUHSTRING__@@V?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@1234@@Z`
- size: `267`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800500e0`

## callees

- `0x180015b64`
- `0x18003bc80`
- `0x18004ffb4`
- `0x1800500c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180050021`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180050021`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005000b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005000b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180050037`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180050037`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(
        __int64 a1,
        _QWORD *a2)
{
  HRESULT v3; // eax
  int ActivationFactory; // ebx
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // [rsp+20h] [rbp-40h] BYREF
  __int64 v9; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-18h] BYREF

  *a2 = 0;
  v9 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
  string = 0;
  v3 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &hstringHeader, &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v9);
  if ( ActivationFactory < 0 )
    goto LABEL_4;
  v8 = 0;
  v6 = v9;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v8);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{208,{flat}}(v6, &v8);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v8);
LABEL_4:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
    return (unsigned int)ActivationFactory;
  }
  v7 = v8;
  v8 = 0;
  *a2 = v7;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v8);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
  return 0;
}

```

## disassembly

```asm
0x18004ffb4  mov     [rsp-8+arg_0], rbx
0x18004ffb9  mov     [rsp-8+arg_10], rdi
0x18004ffbe  push    rbp
0x18004ffbf  mov     rbp, rsp
0x18004ffc2  sub     rsp, 60h
0x18004ffc6  mov     rax, cs:__security_cookie
0x18004ffcd  xor     rax, rsp
0x18004ffd0  mov     [rbp+var_10], rax
0x18004ffd4  mov     rdi, rdx
0x18004ffd7  mov     qword ptr [rdx], 0
0x18004ffde  mov     [rbp+var_38], 0
0x18004ffe6  lea     rcx, [rbp+var_38]
0x18004ffea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004ffef  mov     [rbp+string], 0
0x18004fff7  lea     r9, [rbp+string]; string
0x18004fffb  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004ffff  mov     edx, 2Ch ; ','; length
0x180050004  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18005000b  call    cs:__imp_WindowsCreateStringReference
0x180050011  test    eax, eax
0x180050013  jns     short loc_180050028
0x180050015  xor     r9d, r9d; lpArguments
0x180050018  xor     r8d, r8d; nNumberOfArguments
0x18005001b  lea     edx, [r9+1]; dwExceptionFlags
0x18005001f  mov     ecx, eax; dwExceptionCode
0x180050021  call    cs:__imp_RaiseException
0x180050027  int     3; Trap to Debugger
0x180050028  lea     r8, [rbp+var_38]
0x18005002c  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180050033  mov     rcx, [rbp+string]
0x180050037  call    cs:__imp_RoGetActivationFactory
0x18005003d  mov     ebx, eax
0x18005003f  test    eax, eax
0x180050041  jns     short loc_180050050
0x180050043  lea     rcx, [rbp+var_38]
0x180050047  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005004c  mov     eax, ebx
0x18005004e  jmp     short loc_1800500A1
0x180050050  mov     [rbp+var_40], 0
0x180050058  mov     rbx, [rbp+var_38]
0x18005005c  lea     rcx, [rbp+var_40]
0x180050060  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180050065  lea     rdx, [rbp+var_40]
0x180050069  mov     rcx, rbx
0x18005006c  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BNA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{208,{flat}}
0x180050071  mov     ebx, eax
0x180050073  lea     rcx, [rbp+var_40]
0x180050077  test    eax, eax
0x180050079  jns     short loc_180050082
0x18005007b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180050080  jmp     short loc_180050043
0x180050082  mov     rax, [rbp+var_40]
0x180050086  mov     [rbp+var_40], 0
0x18005008e  mov     [rdi], rax
0x180050091  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180050096  lea     rcx, [rbp+var_38]
0x18005009a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005009f  xor     eax, eax
0x1800500a1  mov     rcx, [rbp+var_10]
0x1800500a5  xor     rcx, rsp; StackCookie
0x1800500a8  call    __security_check_cookie
0x1800500ad  lea     r11, [rsp+60h+var_s0]
0x1800500b2  mov     rbx, [r11+10h]
0x1800500b6  mov     rdi, [r11+20h]
0x1800500ba  mov     rsp, r11
0x1800500bd  pop     rbp
0x1800500be  retn
```
