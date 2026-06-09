# EnsurePackageRegistered(ushort const *)

- ea: `0x18008bb78`
- end: `0x18008bcf1`
- name: `?EnsurePackageRegistered@@YAJPEBG@Z`
- size: `377`
- prototype: `__int64 __fastcall(PCWSTR sourceString)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18008c094`

## callees

- `0x180067d2c`
- `0x18006a460`
- `0x180075fa0`
- `0x1800887ec`
- `0x18008b10c`
- `0x18008bb78`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008bc26`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008bcea`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008bc26`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008bcea`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x18008bbac`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x18008bbac`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x18008bc98`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x18008bc98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008bc0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008bc0d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EnsurePackageRegistered(PCWSTR sourceString)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // eax
  __int64 v6; // rdx
  _QWORD *v7; // rbx
  __int64 v8; // rsi
  unsigned __int64 v9; // r9
  unsigned int v10; // edi
  _QWORD *v11; // [rsp+20h] [rbp-60h] BYREF
  __int64 v12; // [rsp+28h] [rbp-58h] BYREF
  HSTRING string; // [rsp+30h] [rbp-50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-48h] BYREF
  HSTRING_HEADER v15; // [rsp+50h] [rbp-30h] BYREF
  __int64 v16; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v12 = 0;
  v2 = CoIncrementMTAUsage(&v12);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecoreuap\\internal\\windows\\inc\\private\\dxgi\\dxgieffectutility.h",
      (const char *)(unsigned int)v2,
      (int)v11);
    return v3;
  }
  v11 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Management.Deployment.Internal.PackageManagerInternal",
         0x3Du,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v5 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(
         string,
         &v11);
  v3 = v5;
  if ( v5 < 0 )
  {
    v6 = 79;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\internal\\windows\\inc\\private\\dxgi\\dxgieffectutility.h",
      (const char *)(unsigned int)v5,
      (int)v11);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v11);
    return v3;
  }
  v7 = v11;
  v8 = *v11;
  v16 = 0;
  v9 = -1;
  do
    ++v9;
  while ( sourceString[v9] );
  if ( v9 > 0xFFFFFFFF || (int)v9 + 1 < (unsigned int)v9 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    JUMPOUT(0x18008BCF0LL);
  }
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v15, sourceString, v9 + 1, v9);
  v10 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(v8 + 264))(v7, v16);
  v5 = CoDecrementMTAUsage(v12);
  v3 = v5;
  if ( v5 < 0 )
  {
    v6 = 82;
    goto LABEL_14;
  }
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v11);
  return v10;
}

```

## disassembly

```asm
0x18008bb78  mov     [rsp-18h+arg_8], rbx
0x18008bb7d  mov     [rsp-18h+arg_10], rsi
0x18008bb82  push    rbp
0x18008bb83  push    rdi
0x18008bb84  push    r14
0x18008bb86  mov     rbp, rsp
0x18008bb89  sub     rsp, 80h
0x18008bb90  mov     rax, cs:__security_cookie
0x18008bb97  xor     rax, rsp
0x18008bb9a  mov     [rbp+var_10], rax
0x18008bb9e  mov     rdi, rcx
0x18008bba1  xor     r14d, r14d
0x18008bba4  mov     [rbp+var_58], r14
0x18008bba8  lea     rcx, [rbp+var_58]
0x18008bbac  call    cs:__imp_CoIncrementMTAUsage
0x18008bbb2  mov     ebx, eax
0x18008bbb4  test    eax, eax
0x18008bbb6  jns     short loc_18008BBF5
0x18008bbb8  mov     rcx, [rbp+18h]; this
0x18008bbbc  mov     r9d, eax; char *
0x18008bbbf  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\windows\\inc\\pri"...
0x18008bbc6  lea     edx, [r14+4Bh]; void *
0x18008bbca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008bbcf  mov     eax, ebx
0x18008bbd1  mov     rcx, [rbp+var_10]
0x18008bbd5  xor     rcx, rsp; StackCookie
0x18008bbd8  call    __security_check_cookie
0x18008bbdd  lea     r11, [rsp+80h+var_s0]
0x18008bbe5  mov     rbx, [r11+28h]
0x18008bbe9  mov     rsi, [r11+30h]
0x18008bbed  mov     rsp, r11
0x18008bbf0  pop     r14
0x18008bbf2  pop     rdi
0x18008bbf3  pop     rbp
0x18008bbf4  retn
0x18008bbf5  mov     [rbp+var_60], r14
0x18008bbf9  lea     r9, [rbp+string]; string
0x18008bbfd  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18008bc01  mov     edx, 3Dh ; '='; length
0x18008bc06  lea     rcx, ?RuntimeClass_Windows_Management_Deployment_Internal_PackageManagerInternal@@3QBGB; "Windows.Management.Deployment.Internal."...
0x18008bc0d  call    cs:__imp_WindowsCreateStringReference
0x18008bc13  test    eax, eax
0x18008bc15  jns     short loc_18008BC2C
0x18008bc17  xor     r9d, r9d; lpArguments
0x18008bc1a  xor     r8d, r8d; nNumberOfArguments
0x18008bc1d  lea     edx, [r9+1]; dwExceptionFlags
0x18008bc21  mov     ecx, 0C000000Dh; dwExceptionCode
0x18008bc26  call    cs:__imp_RaiseException
0x18008bc2c  lea     rdx, [rbp+var_60]
0x18008bc30  mov     rcx, [rbp+string]
0x18008bc34  call    ??$ActivateInstance@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>)
0x18008bc39  mov     ebx, eax
0x18008bc3b  test    eax, eax
0x18008bc3d  jns     short loc_18008BC46
0x18008bc3f  mov     edx, 4Fh ; 'O'
0x18008bc44  jmp     short loc_18008BCA9
0x18008bc46  mov     rbx, [rbp+var_60]
0x18008bc4a  mov     rsi, [rbx]
0x18008bc4d  mov     [rbp+var_18], r14
0x18008bc51  or      r9, 0FFFFFFFFFFFFFFFFh
0x18008bc55  inc     r9; unsigned int
0x18008bc58  cmp     [rdi+r9*2], r14w
0x18008bc5d  jnz     short loc_18008BC55
0x18008bc5f  mov     eax, 0FFFFFFFFh
0x18008bc64  cmp     r9, rax
0x18008bc67  ja      short loc_18008BCDB
0x18008bc69  lea     r8d, [r9+1]; unsigned int
0x18008bc6d  cmp     r8d, r9d
0x18008bc70  jb      short loc_18008BCDB
0x18008bc72  mov     rdx, rdi; sourceString
0x18008bc75  lea     rcx, [rbp+var_30]; hstringHeader
0x18008bc79  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18008bc7e  nop
0x18008bc7f  mov     rdx, [rbp+var_18]
0x18008bc83  mov     rcx, rbx
0x18008bc86  mov     rax, [rsi+108h]
0x18008bc8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bc92  mov     edi, eax
0x18008bc94  mov     rcx, [rbp+var_58]
0x18008bc98  call    cs:__imp_CoDecrementMTAUsage
0x18008bc9e  mov     ebx, eax
0x18008bca0  test    eax, eax
0x18008bca2  jns     short loc_18008BCCB
0x18008bca4  mov     edx, 52h ; 'R'; void *
0x18008bca9  mov     r9d, eax; char *
0x18008bcac  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\windows\\inc\\pri"...
0x18008bcb3  mov     rcx, [rbp+18h]; this
0x18008bcb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008bcbc  nop
0x18008bcbd  lea     rcx, [rbp+var_60]
0x18008bcc1  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18008bcc6  jmp     loc_18008BBCF
0x18008bccb  lea     rcx, [rbp+var_60]
0x18008bccf  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18008bcd4  mov     eax, edi
0x18008bcd6  jmp     loc_18008BBD1
0x18008bcdb  xor     r9d, r9d; lpArguments
0x18008bcde  xor     r8d, r8d; nNumberOfArguments
0x18008bce1  lea     edx, [r9+1]; dwExceptionFlags
0x18008bce5  mov     ecx, 80070216h; dwExceptionCode
0x18008bcea  call    cs:__imp_RaiseException
```
