# NetworkCompliance::_GetWinHttpPreferredConnection

- ea: `0x1800c5d38`
- end: `0x1800c5fd1`
- name: `NetworkCompliance::_GetWinHttpPreferredConnection`
- size: `665`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c6380`

## callees

- `0x180009ab4`
- `0x18000cea4`
- `0x18009c368`
- `0x1800ae518`
- `0x1800c5d38`
- `0x1800f82f0`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c5f18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c5f18`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800c5f06`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800c5f06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800c5da4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800c5da4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800c5dde`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800c5dde`

## string_xrefs

- `0x1800c5f4e`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\token_helpers.h`
- `0x1800c5f6b`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\NetworkCompliance.cpp`
- `0x1800c5f80`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\NetworkCompliance.cpp`
- `0x1800c5f95`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\NetworkCompliance.cpp`
- `0x1800c5faa`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\NetworkCompliance.cpp`
- `0x1800c5fbf`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\NetworkCompliance.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 NetworkCompliance::_GetWinHttpPreferredConnection()
{
  unsigned int v0; // edi
  int v1; // eax
  HRESULT v2; // eax
  int v3; // edx
  unsigned int v4; // r8d
  HSTRING v5; // rbx
  __int64 v6; // rcx
  int ActivationFactory; // eax
  wil::details::in1diag3 *v8; // rcx
  int v9; // eax
  __int64 (__fastcall ***v10)(_QWORD, GUID *, _QWORD *); // rcx
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  HANDLE v16; // rbx
  wil::details::in1diag3 *v17; // rcx
  HANDLE Token; // [rsp+28h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-50h] BYREF
  HSTRING string; // [rsp+48h] [rbp-38h] BYREF
  char v22; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v23[7]; // [rsp+51h] [rbp-2Fh] BYREF
  __int64 v24; // [rsp+58h] [rbp-28h] BYREF
  __int64 v25; // [rsp+60h] [rbp-20h] BYREF
  __int64 (__fastcall ***v26)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  Token = (HANDLE)-1LL;
  v0 = 2;
  v1 = wil::impersonate_token_nothrow(0, &Token);
  if ( v1 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x208,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\token_helpers.h",
      (const char *)(unsigned int)v1,
      2);
  v24 = 0;
  string = 0;
  v2 = WindowsCreateStringReference(
         L"Windows.Networking.Connectivity.NetworkInformation",
         0x32u,
         &hstringHeader,
         &string);
  if ( v2 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v2, v3, v4);
    goto LABEL_30;
  }
  v5 = string;
  v6 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  ActivationFactory = RoGetActivationFactory(v5, &GUID_5074f851_950d_4165_9c15_365619481eea, &v24);
  v8 = retaddr;
  if ( ActivationFactory < 0 )
LABEL_30:
    wil::details::in1diag3::Throw_Hr(
      v8,
      (void *)0x21,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\NetworkCompliance.cpp",
      (const char *)(unsigned int)ActivationFactory,
      2);
  v26 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v24 + 56LL))(
         v24,
         &v26);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\NetworkCompliance.cpp",
      (const char *)(unsigned int)v9,
      2);
  v10 = v26;
  if ( v26 )
  {
    v25 = 0;
    v11 = (**v26)(v26, &GUID_e2045145_4c9f_400c_9150_7ec7d6e2888a, &v25);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2E,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\NetworkCompliance.cpp",
        (const char *)(unsigned int)v11,
        2);
    v22 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v25 + 56LL))(v25, &v22);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x31,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\NetworkCompliance.cpp",
        (const char *)(unsigned int)v12,
        2);
    if ( !v22 )
    {
      v23[0] = 0;
      v13 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v25 + 48LL))(v25, v23);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x38,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\NetworkCompliance.cpp",
          (const char *)(unsigned int)v13,
          2);
      v0 = 3;
      if ( !v23[0] )
        v0 = 1;
    }
    v14 = v25;
    if ( v25 )
    {
      v25 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    v10 = v26;
  }
  else
  {
    v0 = 0;
  }
  if ( v10 )
  {
    v26 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v10)[2])(v10);
  }
  v15 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  v16 = Token;
  if ( Token != (HANDLE)-1LL )
  {
    if ( !SetThreadToken(0, Token) )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
    if ( v16 )
      CloseHandle(v16);
  }
  return v0;
}

```

## disassembly

```asm
0x1800c5d38  mov     [rsp-8+arg_0], rbx
0x1800c5d3d  mov     [rsp-8+arg_8], rsi
0x1800c5d42  mov     [rsp-8+arg_10], rdi
0x1800c5d47  push    rbp
0x1800c5d48  mov     rbp, rsp
0x1800c5d4b  sub     rsp, 80h
0x1800c5d52  mov     rax, cs:__security_cookie
0x1800c5d59  xor     rax, rsp
0x1800c5d5c  mov     [rbp+var_10], rax
0x1800c5d60  xor     esi, esi
0x1800c5d62  mov     [rbp+var_60], esi
0x1800c5d65  mov     [rbp+Token], 0FFFFFFFFFFFFFFFFh
0x1800c5d6d  lea     edi, [rsi+2]
0x1800c5d70  mov     [rbp+var_60], edi
0x1800c5d73  lea     rdx, [rbp+Token]
0x1800c5d77  xor     ecx, ecx; Token
0x1800c5d79  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x1800c5d7e  mov     rcx, [rbp+8]; this
0x1800c5d82  test    eax, eax
0x1800c5d84  js      loc_1800C5F4B
0x1800c5d8a  mov     [rbp+var_28], rsi
0x1800c5d8e  mov     [rbp+string], rsi
0x1800c5d92  lea     r9, [rbp+string]; string
0x1800c5d96  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800c5d9a  lea     edx, [rsi+32h]; length
0x1800c5d9d  lea     rcx, ?RuntimeClass_Windows_Networking_Connectivity_NetworkInformation@@3QB_WB; "Windows.Networking.Connectivity.Network"...
0x1800c5da4  call    cs:__imp_WindowsCreateStringReference
0x1800c5daa  test    eax, eax
0x1800c5dac  js      loc_1800C5F60
0x1800c5db2  mov     rbx, [rbp+string]
0x1800c5db6  mov     rcx, [rbp+var_28]
0x1800c5dba  test    rcx, rcx
0x1800c5dbd  jz      short loc_1800C5DD0
0x1800c5dbf  mov     [rbp+var_28], rsi
0x1800c5dc3  mov     rax, [rcx]
0x1800c5dc6  mov     rax, [rax+10h]
0x1800c5dca  call    _guard_dispatch_icall
0x1800c5dcf  nop
0x1800c5dd0  lea     r8, [rbp+var_28]
0x1800c5dd4  lea     rdx, _GUID_5074f851_950d_4165_9c15_365619481eea
0x1800c5ddb  mov     rcx, rbx
0x1800c5dde  call    cs:__imp_RoGetActivationFactory
0x1800c5de4  mov     rcx, [rbp+8]
0x1800c5de8  test    eax, eax
0x1800c5dea  js      loc_1800C5F68
0x1800c5df0  mov     [rbp+var_18], rsi
0x1800c5df4  mov     rcx, [rbp+var_28]
0x1800c5df8  mov     rax, [rcx]
0x1800c5dfb  lea     rdx, [rbp+var_18]
0x1800c5dff  mov     rax, [rax+38h]
0x1800c5e03  call    _guard_dispatch_icall
0x1800c5e08  mov     rcx, [rbp+8]; this
0x1800c5e0c  test    eax, eax
0x1800c5e0e  js      loc_1800C5F7D
0x1800c5e14  mov     rcx, [rbp+var_18]
0x1800c5e18  test    rcx, rcx
0x1800c5e1b  jnz     short loc_1800C5E24
0x1800c5e1d  mov     edi, esi
0x1800c5e1f  jmp     loc_1800C5EC7
0x1800c5e24  mov     [rbp+var_20], rsi
0x1800c5e28  mov     rax, [rcx]
0x1800c5e2b  lea     r8, [rbp+var_20]
0x1800c5e2f  lea     rdx, _GUID_e2045145_4c9f_400c_9150_7ec7d6e2888a
0x1800c5e36  mov     rax, [rax]
0x1800c5e39  call    _guard_dispatch_icall
0x1800c5e3e  nop
0x1800c5e3f  mov     rcx, [rbp+8]; this
0x1800c5e43  test    eax, eax
0x1800c5e45  js      loc_1800C5F92
0x1800c5e4b  mov     [rbp+var_30], sil
0x1800c5e4f  mov     rcx, [rbp+var_20]
0x1800c5e53  mov     rax, [rcx]
0x1800c5e56  lea     rdx, [rbp+var_30]
0x1800c5e5a  mov     rax, [rax+38h]
0x1800c5e5e  call    _guard_dispatch_icall
0x1800c5e63  mov     rcx, [rbp+8]; this
0x1800c5e67  test    eax, eax
0x1800c5e69  js      loc_1800C5FA7
0x1800c5e6f  cmp     [rbp+var_30], sil
0x1800c5e73  jnz     short loc_1800C5EA9
0x1800c5e75  mov     [rbp+var_2F], sil
0x1800c5e79  mov     rcx, [rbp+var_20]
0x1800c5e7d  mov     rax, [rcx]
0x1800c5e80  lea     rdx, [rbp+var_2F]
0x1800c5e84  mov     rax, [rax+30h]
0x1800c5e88  call    _guard_dispatch_icall
0x1800c5e8d  mov     rcx, [rbp+8]; this
0x1800c5e91  test    eax, eax
0x1800c5e93  js      loc_1800C5FBC
0x1800c5e99  cmp     [rbp+var_2F], sil
0x1800c5e9d  mov     edi, 3
0x1800c5ea2  jnz     short loc_1800C5EA9
0x1800c5ea4  mov     edi, 1
0x1800c5ea9  mov     rcx, [rbp+var_20]
0x1800c5ead  test    rcx, rcx
0x1800c5eb0  jz      short loc_1800C5EC3
0x1800c5eb2  mov     [rbp+var_20], rsi
0x1800c5eb6  mov     rax, [rcx]
0x1800c5eb9  mov     rax, [rax+10h]
0x1800c5ebd  call    _guard_dispatch_icall
0x1800c5ec2  nop
0x1800c5ec3  mov     rcx, [rbp+var_18]
0x1800c5ec7  test    rcx, rcx
0x1800c5eca  jz      short loc_1800C5EDD
0x1800c5ecc  mov     [rbp+var_18], rsi
0x1800c5ed0  mov     rax, [rcx]
0x1800c5ed3  mov     rax, [rax+10h]
0x1800c5ed7  call    _guard_dispatch_icall
0x1800c5edc  nop
0x1800c5edd  mov     rcx, [rbp+var_28]
0x1800c5ee1  test    rcx, rcx
0x1800c5ee4  jz      short loc_1800C5EF7
0x1800c5ee6  mov     [rbp+var_28], rsi
0x1800c5eea  mov     rax, [rcx]
0x1800c5eed  mov     rax, [rax+10h]
0x1800c5ef1  call    _guard_dispatch_icall
0x1800c5ef6  nop
0x1800c5ef7  mov     rbx, [rbp+Token]
0x1800c5efb  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800c5eff  jz      short loc_1800C5F1E
0x1800c5f01  mov     rdx, rbx; Token
0x1800c5f04  xor     ecx, ecx; Thread
0x1800c5f06  call    cs:__imp_SetThreadToken
0x1800c5f0c  test    eax, eax
0x1800c5f0e  jz      short loc_1800C5F45
0x1800c5f10  test    rbx, rbx
0x1800c5f13  jz      short loc_1800C5F1E
0x1800c5f15  mov     rcx, rbx; hObject
0x1800c5f18  call    cs:__imp_CloseHandle
0x1800c5f1e  mov     eax, edi
0x1800c5f20  mov     rcx, [rbp+var_10]
0x1800c5f24  xor     rcx, rsp; StackCookie
0x1800c5f27  call    __security_check_cookie
0x1800c5f2c  lea     r11, [rsp+80h+var_s0]
0x1800c5f34  mov     rbx, [r11+10h]
0x1800c5f38  mov     rsi, [r11+18h]
0x1800c5f3c  mov     rdi, [r11+20h]
0x1800c5f40  mov     rsp, r11
0x1800c5f43  pop     rbp
0x1800c5f44  retn
0x1800c5f45  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800c5f4b  mov     r9d, eax; char *
0x1800c5f4e  lea     r8, aCW1SPackagesMi_6; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800c5f55  mov     edx, 208h; void *
0x1800c5f5a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c5f60  mov     ecx, eax; this
0x1800c5f62  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800c5f67  nop
0x1800c5f68  mov     r9d, eax; char *
0x1800c5f6b  lea     r8, aCW1SSrcDeliver_46; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800c5f72  mov     edx, 21h ; '!'; void *
0x1800c5f77  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c5f7d  mov     r9d, eax; char *
0x1800c5f80  lea     r8, aCW1SSrcDeliver_46; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800c5f87  mov     edx, 24h ; '$'; void *
0x1800c5f8c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c5f92  mov     r9d, eax; char *
0x1800c5f95  lea     r8, aCW1SSrcDeliver_46; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800c5f9c  mov     edx, 2Eh ; '.'; void *
0x1800c5fa1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c5fa7  mov     r9d, eax; char *
0x1800c5faa  lea     r8, aCW1SSrcDeliver_46; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800c5fb1  mov     edx, 31h ; '1'; void *
0x1800c5fb6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c5fbc  mov     r9d, eax; char *
0x1800c5fbf  lea     r8, aCW1SSrcDeliver_46; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800c5fc6  mov     edx, 38h ; '8'; void *
0x1800c5fcb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
