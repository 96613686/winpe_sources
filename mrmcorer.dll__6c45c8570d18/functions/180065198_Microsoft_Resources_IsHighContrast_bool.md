# Microsoft::Resources::IsHighContrast(bool *)

- ea: `0x180065198`
- end: `0x1800652ca`
- name: `?IsHighContrast@Resources@Microsoft@@YAJPEA_N@Z`
- size: `306`
- prototype: `__int64 __fastcall(Microsoft::Resources *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180065120`

## callees

- `0x18001be80`
- `0x180065198`
- `0x1800862f0`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800652c3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800652c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800651d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800651d9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180065202`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180065202`

## string_xrefs

- `0x1800651bd`: `Windows.UI.ViewManagement.AccessibilitySettings`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::IsHighContrast(Microsoft::Resources *this, bool *a2)
{
  HRESULT v3; // eax
  HSTRING v4; // rbx
  int ActivationFactory; // ebx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64 *); // rbx
  __int64 v8; // rcx
  __int64 v9; // rcx
  _BYTE v11[8]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v12; // [rsp+28h] [rbp-40h] BYREF
  __int64 v13; // [rsp+30h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-30h] BYREF
  HSTRING string; // [rsp+50h] [rbp-18h] BYREF

  v13 = 0;
  string = 0;
  v3 = WindowsCreateStringReference(L"Windows.UI.ViewManagement.AccessibilitySettings", 0x2Fu, &hstringHeader, &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    JUMPOUT(0x1800652C9LL);
  }
  v4 = string;
  Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerRepairAclsInternal>::InternalRelease(&v13);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_00000035_0000_0000_c000_000000000046, &v13);
  if ( ActivationFactory >= 0 )
  {
    v6 = v13;
    v12 = 0;
    v7 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerRepairAclsInternal>::InternalRelease(&v12);
    ActivationFactory = v7(v6, &v12);
    if ( ActivationFactory >= 0 )
    {
      v11[0] = 0;
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v12 + 48LL))(v12, v11);
      if ( ActivationFactory >= 0 )
        *(_BYTE *)this = v11[0] != 0;
    }
    v8 = v12;
    if ( v12 )
    {
      v12 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
  }
  v9 = v13;
  if ( v13 )
  {
    v13 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180065198  push    rbp
0x18006519a  push    rbx
0x18006519b  push    rsi
0x18006519c  push    rdi
0x18006519d  mov     rbp, rsp
0x1800651a0  sub     rsp, 68h
0x1800651a4  mov     rax, cs:__security_cookie
0x1800651ab  xor     rax, rsp
0x1800651ae  mov     [rbp+var_10], rax
0x1800651b2  mov     rsi, rcx
0x1800651b5  mov     [rbp+var_38], 0
0x1800651bd  lea     rcx, ?RuntimeClass_Windows_UI_ViewManagement_AccessibilitySettings@@3QBGB; "Windows.UI.ViewManagement.Accessibility"...
0x1800651c4  mov     [rbp+string], 0
0x1800651cc  lea     r9, [rbp+string]; string
0x1800651d0  mov     edx, 2Fh ; '/'; length
0x1800651d5  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800651d9  call    cs:__imp_WindowsCreateStringReference
0x1800651df  test    eax, eax
0x1800651e1  js      loc_1800652B7
0x1800651e7  mov     rbx, [rbp+string]
0x1800651eb  lea     rcx, [rbp+var_38]
0x1800651ef  call    ?InternalRelease@?$ComPtr@UIPackageManagerRepairAclsInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerRepairAclsInternal>::InternalRelease(void)
0x1800651f4  lea     r8, [rbp+var_38]
0x1800651f8  mov     rcx, rbx
0x1800651fb  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x180065202  call    cs:__imp_RoGetActivationFactory
0x180065208  mov     ebx, eax
0x18006520a  test    eax, eax
0x18006520c  js      short loc_180065283
0x18006520e  mov     rdi, [rbp+var_38]
0x180065212  lea     rcx, [rbp+var_40]
0x180065216  mov     [rbp+var_40], 0
0x18006521e  mov     rax, [rdi]
0x180065221  mov     rbx, [rax+30h]
0x180065225  call    ?InternalRelease@?$ComPtr@UIPackageManagerRepairAclsInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerRepairAclsInternal>::InternalRelease(void)
0x18006522a  lea     rdx, [rbp+var_40]
0x18006522e  mov     rcx, rdi
0x180065231  mov     rax, rbx
0x180065234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065239  mov     ebx, eax
0x18006523b  test    eax, eax
0x18006523d  js      short loc_180065266
0x18006523f  mov     rcx, [rbp+var_40]
0x180065243  lea     rdx, [rbp+var_48]
0x180065247  mov     [rbp+var_48], 0
0x18006524b  mov     rax, [rcx]
0x18006524e  mov     rax, [rax+30h]
0x180065252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065257  mov     ebx, eax
0x180065259  test    eax, eax
0x18006525b  js      short loc_180065266
0x18006525d  cmp     [rbp+var_48], 0
0x180065261  setnz   al
0x180065264  mov     [rsi], al
0x180065266  mov     rcx, [rbp+var_40]
0x18006526a  test    rcx, rcx
0x18006526d  jz      short loc_180065283
0x18006526f  mov     [rbp+var_40], 0
0x180065277  mov     rax, [rcx]
0x18006527a  mov     rax, [rax+10h]
0x18006527e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065283  mov     rcx, [rbp+var_38]
0x180065287  test    rcx, rcx
0x18006528a  jz      short loc_1800652A0
0x18006528c  mov     [rbp+var_38], 0
0x180065294  mov     rax, [rcx]
0x180065297  mov     rax, [rax+10h]
0x18006529b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800652a0  mov     eax, ebx
0x1800652a2  mov     rcx, [rbp+var_10]
0x1800652a6  xor     rcx, rsp; StackCookie
0x1800652a9  call    __security_check_cookie
0x1800652ae  add     rsp, 68h
0x1800652b2  pop     rdi
0x1800652b3  pop     rsi
0x1800652b4  pop     rbx
0x1800652b5  pop     rbp
0x1800652b6  retn
0x1800652b7  xor     r9d, r9d; lpArguments
0x1800652ba  xor     r8d, r8d; nNumberOfArguments
0x1800652bd  mov     ecx, eax; dwExceptionCode
0x1800652bf  lea     edx, [r9+1]; dwExceptionFlags
0x1800652c3  call    cs:__imp_RaiseException
```
