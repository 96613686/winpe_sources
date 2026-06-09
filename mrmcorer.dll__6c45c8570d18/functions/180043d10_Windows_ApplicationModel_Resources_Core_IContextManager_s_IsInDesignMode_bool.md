# Windows::ApplicationModel::Resources::Core::IContextManager::s_IsInDesignMode(bool *)

- ea: `0x180043d10`
- end: `0x180043e3b`
- name: `?s_IsInDesignMode@IContextManager@Core@Resources@ApplicationModel@Windows@@SAJPEA_N@Z`
- size: `299`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180043c2c`
- `0x180044418`

## callees

- `0x18000892c`
- `0x18002c8d0`
- `0x180043d10`
- `0x1800862f0`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180043e1c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180043e1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180043d5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180043d5b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180043d84`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180043d84`

## string_xrefs

- `0x1800c2979`: `onecoreuap\base\mrt\runtime\com\winrt\core\contextmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::ApplicationModel::Resources::Core::IContextManager::s_IsInDesignMode(bool *a1)
{
  int v2; // eax
  HSTRING v3; // rbx
  int ActivationFactory; // eax
  unsigned int v5; // ebx
  __int64 v6; // rcx
  __int64 v8; // rdx
  int v9; // [rsp+20h] [rbp-40h] BYREF
  __int64 v10; // [rsp+28h] [rbp-38h] BYREF
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v2 = dword_1800FC7D8;
  if ( dword_1800FC7D8 )
    goto LABEL_8;
  v10 = 0;
  if ( WindowsCreateStringReference(L"Windows.ApplicationModel.DesignMode", 0x23u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v3 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v10);
  ActivationFactory = RoGetActivationFactory(v3, &GUID_2c3893cc_f81a_4e7a_b857_76a80887e185, &v10);
  v5 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v8 = 1198;
  }
  else
  {
    LOBYTE(v9) = 0;
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 48LL))(v10, &v9);
    v5 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v2 = 2 - ((_BYTE)v9 != 0);
      dword_1800FC7D8 = v2;
      v6 = v10;
      if ( v10 )
      {
        v10 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        v2 = dword_1800FC7D8;
      }
LABEL_8:
      *a1 = v2 == 1;
      return 0;
    }
    v8 = 1201;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\contextmanager.cpp",
    (const char *)(unsigned int)ActivationFactory,
    v9);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v10);
  return v5;
}

```

## disassembly

```asm
0x180043d10  mov     [rsp-8+arg_8], rbx
0x180043d15  mov     [rsp-8+arg_10], rdi
0x180043d1a  push    rbp
0x180043d1b  mov     rbp, rsp
0x180043d1e  sub     rsp, 60h
0x180043d22  mov     rax, cs:__security_cookie
0x180043d29  xor     rax, rsp
0x180043d2c  mov     [rbp+var_10], rax
0x180043d30  mov     rdi, rcx
0x180043d33  mov     eax, cs:dword_1800FC7D8
0x180043d39  test    eax, eax
0x180043d3b  jnz     loc_180043DE5
0x180043d41  mov     [rbp+var_38], 0
0x180043d49  lea     r9, [rbp+string]; string
0x180043d4d  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180043d51  lea     edx, [rax+23h]; length
0x180043d54  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_DesignMode@@3QBGB; "Windows.ApplicationModel.DesignMode"
0x180043d5b  call    cs:__imp_WindowsCreateStringReference
0x180043d61  test    eax, eax
0x180043d63  js      loc_180043E0D
0x180043d69  mov     rbx, [rbp+string]
0x180043d6d  lea     rcx, [rbp+var_38]
0x180043d71  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180043d76  lea     r8, [rbp+var_38]
0x180043d7a  lea     rdx, _GUID_2c3893cc_f81a_4e7a_b857_76a80887e185
0x180043d81  mov     rcx, rbx
0x180043d84  call    cs:__imp_RoGetActivationFactory
0x180043d8a  mov     ebx, eax
0x180043d8c  test    eax, eax
0x180043d8e  js      loc_180043E27
0x180043d94  mov     byte ptr [rbp+var_40], 0
0x180043d98  mov     rcx, [rbp+var_38]
0x180043d9c  mov     rax, [rcx]
0x180043d9f  lea     rdx, [rbp+var_40]
0x180043da3  mov     rax, [rax+30h]
0x180043da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043dac  mov     ebx, eax
0x180043dae  test    eax, eax
0x180043db0  js      short loc_180043E31
0x180043db2  mov     al, byte ptr [rbp+var_40]
0x180043db5  neg     al
0x180043db7  sbb     eax, eax
0x180043db9  add     eax, 2
0x180043dbc  mov     cs:dword_1800FC7D8, eax
0x180043dc2  mov     rcx, [rbp+var_38]
0x180043dc6  test    rcx, rcx
0x180043dc9  jz      short loc_180043DE5
0x180043dcb  mov     [rbp+var_38], 0
0x180043dd3  mov     rax, [rcx]
0x180043dd6  mov     rax, [rax+10h]
0x180043dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043ddf  mov     eax, cs:dword_1800FC7D8
0x180043de5  cmp     eax, 1
0x180043de8  setz    al
0x180043deb  mov     [rdi], al
0x180043ded  xor     eax, eax
0x180043def  mov     rcx, [rbp+var_10]
0x180043df3  xor     rcx, rsp; StackCookie
0x180043df6  call    __security_check_cookie
0x180043dfb  lea     r11, [rsp+60h+var_s0]
0x180043e00  mov     rbx, [r11+18h]
0x180043e04  mov     rdi, [r11+20h]
0x180043e08  mov     rsp, r11
0x180043e0b  pop     rbp
0x180043e0c  retn
0x180043e0d  xor     r9d, r9d; lpArguments
0x180043e10  xor     r8d, r8d; nNumberOfArguments
0x180043e13  lea     edx, [r9+1]; dwExceptionFlags
0x180043e17  mov     ecx, 0C000000Dh; dwExceptionCode
0x180043e1c  call    cs:__imp_RaiseException
0x180043e22  jmp     loc_180043D69
0x180043e27  mov     edx, 4AEh; void *
0x180043e2c  jmp     loc_1800C2976
0x180043e31  mov     edx, 4B1h
0x180043e36  jmp     loc_1800C2976
0x1800c2976  mov     r9d, eax; char *
0x1800c2979  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800c2980  mov     rcx, [rbp+8]; this
0x1800c2984  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c2989  nop
0x1800c298a  lea     rcx, [rbp+var_38]
0x1800c298e  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800c2993  mov     eax, ebx
0x1800c2995  jmp     loc_180043DEF
```
