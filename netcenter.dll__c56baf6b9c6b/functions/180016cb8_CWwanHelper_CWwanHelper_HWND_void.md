# CWwanHelper::CWwanHelper(HWND__ *,void *)

- ea: `0x180016cb8`
- end: `0x180016e68`
- name: `??0CWwanHelper@@IEAA@PEAUHWND__@@PEAX@Z`
- size: `432`
- prototype: `CWwanHelper *__fastcall(CWwanHelper *__hidden this, HWND, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000bf2c`

## callees

- `0x180002270`
- `0x180015bb8`
- `0x180016cb8`
- `0x180018708`
- `0x1800188d8`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016d7c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016d7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016d68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016d68`
- `wwapi!WwanOpenHandle` at `0x180016d40`
- `wwapi!WwanOpenHandle` at `0x180016d40`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
CWwanHelper *__fastcall CWwanHelper::CWwanHelper(CWwanHelper *this, HWND a2, void *a3)
{
  char *v4; // r14
  HRESULT v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rdi
  int (__fastcall *v8)(__int64, __int64 *); // rbx
  __int64 v9; // rdi
  void (__fastcall *v10)(__int64, __int64, _QWORD, char *); // rbx
  __int64 v12; // [rsp+30h] [rbp-50h] BYREF
  __int64 v13; // [rsp+38h] [rbp-48h] BYREF
  int v14; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v15[2]; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  HSTRING string; // [rsp+70h] [rbp-10h] BYREF

  v15[1] = this;
  *(_QWORD *)this = &TUnknownSTBaseFRE<char>::`vftable';
  *((_DWORD *)this + 2) = 1;
  _InterlockedAdd(&g_cLocks, 1u);
  *(_QWORD *)this = &CWwanHelper::`vftable'{for `TUnknownSTBaseFRE<char>'};
  *((_QWORD *)this + 2) = &CWwanHelper::`vftable'{for `IUnknown'};
  v4 = (char *)this + 32;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = a2;
  *((_QWORD *)this + 6) = a3;
  v14 = 0;
  *((_QWORD *)this + 3) = -1;
  WwanOpenHandle(1, 0, &v14);
  v15[0] = 0;
  string = 0;
  v5 = WindowsCreateStringReference(L"Windows.Networking.UX.UXManager", 0x1Fu, &hstringHeader, &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  if ( (int)Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Networking::UX::IUXManager>>(
              string,
              v15) >= 0 )
  {
    v12 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Networking::UX::IUXCategory *>>::InternalRelease(&v12);
    Windows::Foundation::Collections::Internal::Vector<enum Windows::Networking::UX::NetworkMediaType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<enum Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<enum Windows::Networking::UX::NetworkMediaType>>::Make(
      v6,
      &v12);
    if ( (*(int (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 104LL))(v12, 2) >= 0 )
    {
      v13 = 0;
      v7 = v12;
      v8 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 64LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Networking::UX::IUXCategory *>>::InternalRelease(&v13);
      if ( v8(v7, &v13) >= 0 )
      {
        v9 = v15[0];
        v10 = *(void (__fastcall **)(__int64, __int64, _QWORD, char *))(*(_QWORD *)v15[0] + 56LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Networking::UX::IUXCategory *>>::InternalRelease(v4);
        v10(v9, v13, 0, v4);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Networking::UX::IUXCategory *>>::InternalRelease(&v13);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Networking::UX::IUXCategory *>>::InternalRelease(&v12);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Networking::UX::IUXCategory *>>::InternalRelease(v15);
  return this;
}

```

## disassembly

```asm
0x180016cb8  mov     [rsp-18h+arg_8], rbx
0x180016cbd  mov     [rsp-18h+arg_10], rsi
0x180016cc2  push    rbp
0x180016cc3  push    rdi
0x180016cc4  push    r14
0x180016cc6  mov     rbp, rsp
0x180016cc9  sub     rsp, 80h
0x180016cd0  mov     rax, cs:__security_cookie
0x180016cd7  xor     rax, rsp
0x180016cda  mov     [rbp+var_8], rax
0x180016cde  mov     rsi, rcx
0x180016ce1  mov     [rbp+var_30], rcx
0x180016ce5  lea     rax, ??_7?$TUnknownSTBaseFRE@D@@6B@; const TUnknownSTBaseFRE<char>::`vftable'
0x180016cec  mov     [rcx], rax
0x180016cef  mov     ebx, 1
0x180016cf4  mov     [rcx+8], ebx
0x180016cf7  lock add cs:?g_cLocks@@3JA, ebx; long g_cLocks
0x180016cfe  lea     rax, ??_7CWwanHelper@@6B?$TUnknownSTBaseFRE@D@@@; const CWwanHelper::`vftable'{for `TUnknownSTBaseFRE<char>'}
0x180016d05  mov     [rcx], rax
0x180016d08  lea     rax, ??_7CWwanHelper@@6BIUnknown@@@; const CWwanHelper::`vftable'{for `IUnknown'}
0x180016d0f  mov     [rcx+10h], rax
0x180016d13  lea     r9, [rcx+18h]
0x180016d17  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016d1b  lea     r14, [rcx+20h]
0x180016d1f  mov     qword ptr [r14], 0
0x180016d26  mov     [rcx+28h], rdx
0x180016d2a  mov     [rcx+30h], r8
0x180016d2e  mov     [rbp+var_40], 0
0x180016d35  mov     [r9], rax
0x180016d38  lea     r8, [rbp+var_40]
0x180016d3c  xor     edx, edx
0x180016d3e  mov     ecx, ebx
0x180016d40  call    cs:__imp_WwanOpenHandle
0x180016d46  mov     [rbp+var_38], 0
0x180016d4e  mov     [rbp+string], 0
0x180016d56  lea     r9, [rbp+string]; string
0x180016d5a  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180016d5e  lea     edx, [rbx+1Eh]; length
0x180016d61  lea     rcx, ?RuntimeClass_Windows_Networking_UX_UXManager@@3QBGB; "Windows.Networking.UX.UXManager"
0x180016d68  call    cs:__imp_WindowsCreateStringReference
0x180016d6e  test    eax, eax
0x180016d70  jns     short loc_180016D83
0x180016d72  xor     r9d, r9d; lpArguments
0x180016d75  xor     r8d, r8d; nNumberOfArguments
0x180016d78  mov     edx, ebx; dwExceptionFlags
0x180016d7a  mov     ecx, eax; dwExceptionCode
0x180016d7c  call    cs:__imp_RaiseException
0x180016d82  int     3; Trap to Debugger
0x180016d83  lea     rdx, [rbp+var_38]
0x180016d87  mov     rcx, [rbp+string]
0x180016d8b  call    ??$ActivateInstance@V?$ComPtr@UIUXManager@UX@Networking@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUXManager@UX@Networking@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Networking::UX::IUXManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::UX::IUXManager>>)
0x180016d90  test    eax, eax
0x180016d92  js      loc_180016E37
0x180016d98  mov     [rbp+var_50], 0
0x180016da0  lea     rcx, [rbp+var_50]
0x180016da4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIUXCategory@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Networking::UX::IUXCategory *>>::InternalRelease(void)
0x180016da9  lea     rdx, [rbp+var_50]
0x180016dad  call    ?Make@?$Vector@W4NetworkMediaType@UX@Networking@Windows@@U?$DefaultEqualityPredicate@W4NetworkMediaType@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@W4NetworkMediaType@UX@Networking@Windows@@@6784@U?$DefaultVectorOptions@W4NetworkMediaType@UX@Networking@Windows@@@6784@@Internal@Collections@Foundation@Windows@@SAJAEBU?$DefaultEqualityPredicate@W4NetworkMediaType@UX@Networking@Windows@@@2345@PEAPEAV12345@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::NetworkMediaType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Networking::UX::NetworkMediaType>>::Make(Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::NetworkMediaType> const &,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::NetworkMediaType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Networking::UX::NetworkMediaType>> * *)
0x180016db2  mov     rcx, [rbp+var_50]
0x180016db6  mov     rax, [rcx]
0x180016db9  mov     edx, 2
0x180016dbe  mov     rax, [rax+68h]
0x180016dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dc7  test    eax, eax
0x180016dc9  js      short loc_180016E2D
0x180016dcb  mov     [rbp+var_48], 0
0x180016dd3  mov     rdi, [rbp+var_50]
0x180016dd7  mov     rax, [rdi]
0x180016dda  mov     rbx, [rax+40h]
0x180016dde  lea     rcx, [rbp+var_48]
0x180016de2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIUXCategory@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Networking::UX::IUXCategory *>>::InternalRelease(void)
0x180016de7  lea     rdx, [rbp+var_48]
0x180016deb  mov     rcx, rdi
0x180016dee  mov     rax, rbx
0x180016df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016df6  test    eax, eax
0x180016df8  js      short loc_180016E23
0x180016dfa  mov     rdi, [rbp+var_38]
0x180016dfe  mov     rax, [rdi]
0x180016e01  mov     rbx, [rax+38h]
0x180016e05  mov     rcx, r14
0x180016e08  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIUXCategory@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Networking::UX::IUXCategory *>>::InternalRelease(void)
0x180016e0d  mov     r9, r14
0x180016e10  xor     r8d, r8d
0x180016e13  mov     rdx, [rbp+var_48]
0x180016e17  mov     rcx, rdi
0x180016e1a  mov     rax, rbx
0x180016e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e22  nop
0x180016e23  lea     rcx, [rbp+var_48]
0x180016e27  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIUXCategory@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Networking::UX::IUXCategory *>>::InternalRelease(void)
0x180016e2c  nop
0x180016e2d  lea     rcx, [rbp+var_50]
0x180016e31  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIUXCategory@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Networking::UX::IUXCategory *>>::InternalRelease(void)
0x180016e36  nop
0x180016e37  lea     rcx, [rbp+var_38]
0x180016e3b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIUXCategory@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Networking::UX::IUXCategory *>>::InternalRelease(void)
0x180016e40  nop
0x180016e41  mov     rax, rsi
0x180016e44  mov     rcx, [rbp+var_8]
0x180016e48  xor     rcx, rsp; StackCookie
0x180016e4b  call    __security_check_cookie
0x180016e50  lea     r11, [rsp+80h+var_s0]
0x180016e58  mov     rbx, [r11+28h]
0x180016e5c  mov     rsi, [r11+30h]
0x180016e60  mov     rsp, r11
0x180016e63  pop     r14
0x180016e65  pop     rdi
0x180016e66  pop     rbp
0x180016e67  retn
```
