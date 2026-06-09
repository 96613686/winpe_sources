# RefreshOneSettingsClientForDxDb(void)

- ea: `0x14000bebc`
- end: `0x14000c0dd`
- name: `?RefreshOneSettingsClientForDxDb@@YAJXZ`
- size: `545`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e174`

## callees

- `0x1400022a0`
- `0x14000acd8`
- `0x14000bebc`
- `0x14000c8d4`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000c070`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000c0a7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000c070`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000c0a7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000bee0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000bee0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000bf33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000bfc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000bf33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000bfc3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000bf50`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000bf50`

## string_xrefs

- `0x14000bef3`: `onecoreuap\windows\directx\dxg\dxgi\adaptercache\exe\main.cpp`
- `0x14000bf63`: `onecoreuap\windows\directx\dxg\dxgi\adaptercache\exe\main.cpp`
- `0x14000c032`: `onecoreuap\windows\directx\dxg\dxgi\adaptercache\exe\main.cpp`

## pseudocode

```c
__int64 RefreshOneSettingsClientForDxDb(void)
{
  HRESULT v0; // eax
  unsigned int v1; // ebx
  HRESULT v3; // eax
  int v4; // edx
  unsigned int v5; // r8d
  int ActivationFactory; // eax
  __int64 *v7; // rbx
  __int64 v8; // rdi
  HRESULT v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  int v12; // eax
  int v13; // [rsp+20h] [rbp-50h]
  __int64 *v14; // [rsp+38h] [rbp-38h] BYREF
  __int64 v15; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  HSTRING string; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v0 = CoInitializeEx(0, 0);
  v1 = v0;
  if ( v0 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\adaptercache\\exe\\main.cpp",
      (const char *)(unsigned int)v0,
      v13);
    return v1;
  }
  v14 = 0;
  string = 0;
  v3 = WindowsCreateStringReference(
         L"Windows.Internal.Flighting.OneSettings.OneSettingsManager",
         0x39u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
LABEL_28:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
    JUMPOUT(0x14000C0DCLL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_6ebfc469_e65b_45eb_9863_b3f57e2a5017, &v14);
  v1 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x77,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\adaptercache\\exe\\main.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v13);
    if ( v14 )
      (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
LABEL_21:
    CoUninitialize();
    return v1;
  }
  v15 = 0;
  v7 = v14;
  v8 = *v14;
  v15 = 0;
  string = 0;
  v9 = WindowsCreateStringReference(L"DXDB", 4u, &hstringHeader, &string);
  if ( v9 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
    goto LABEL_28;
  }
  v12 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, _QWORD, __int64 *))(v8 + 56))(v7, string, 0, &v15);
  v1 = v12;
  if ( v12 < 0 )
  {
    if ( v12 == -2147012889 )
    {
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      if ( v14 )
        (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
      v1 = -2147012889;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7D,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\adaptercache\\exe\\main.cpp",
        (const char *)(unsigned int)v12,
        v13);
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      if ( v14 )
        (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
    }
    goto LABEL_21;
  }
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  if ( v14 )
    (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
  CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x14000bebc  mov     [rsp-8+arg_0], rbx
0x14000bec1  mov     [rsp-8+arg_8], rdi
0x14000bec6  push    rbp
0x14000bec7  mov     rbp, rsp
0x14000beca  sub     rsp, 70h
0x14000bece  mov     rax, cs:__security_cookie
0x14000bed5  xor     rax, rsp
0x14000bed8  mov     [rbp+var_8], rax
0x14000bedc  xor     edx, edx; dwCoInit
0x14000bede  xor     ecx, ecx; pvReserved
0x14000bee0  call    cs:__imp_CoInitializeEx
0x14000bee6  mov     ebx, eax
0x14000bee8  test    eax, eax
0x14000beea  jns     short loc_14000BF0B
0x14000beec  mov     rcx, [rbp+8]; this
0x14000bef0  mov     r9d, eax; char *
0x14000bef3  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x14000befa  mov     edx, 72h ; 'r'; void *
0x14000beff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bf04  mov     eax, ebx
0x14000bf06  jmp     loc_14000C0AF
0x14000bf0b  mov     [rbp+var_40], 1
0x14000bf0f  mov     [rbp+var_38], 0
0x14000bf17  mov     [rbp+string], 0
0x14000bf1f  lea     r9, [rbp+string]; string
0x14000bf23  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14000bf27  mov     edx, 39h ; '9'; length
0x14000bf2c  lea     rcx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsManager@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x14000bf33  call    cs:__imp_WindowsCreateStringReference
0x14000bf39  test    eax, eax
0x14000bf3b  js      loc_14000C0D5
0x14000bf41  lea     r8, [rbp+var_38]
0x14000bf45  lea     rdx, _GUID_6ebfc469_e65b_45eb_9863_b3f57e2a5017
0x14000bf4c  mov     rcx, [rbp+string]
0x14000bf50  call    cs:__imp_RoGetActivationFactory
0x14000bf56  mov     ebx, eax
0x14000bf58  test    eax, eax
0x14000bf5a  jns     short loc_14000BF90
0x14000bf5c  mov     rcx, [rbp+8]; this
0x14000bf60  mov     r9d, eax; char *
0x14000bf63  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x14000bf6a  mov     edx, 77h ; 'w'; void *
0x14000bf6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bf74  nop
0x14000bf75  mov     rcx, [rbp+var_38]
0x14000bf79  test    rcx, rcx
0x14000bf7c  jz      short loc_14000BF8B
0x14000bf7e  mov     rax, [rcx]
0x14000bf81  mov     rax, [rax+10h]
0x14000bf85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bf8a  nop
0x14000bf8b  jmp     loc_14000C070
0x14000bf90  mov     [rbp+var_30], 0
0x14000bf98  mov     rbx, [rbp+var_38]
0x14000bf9c  mov     rdi, [rbx]
0x14000bf9f  mov     [rbp+var_30], 0
0x14000bfa7  mov     [rbp+string], 0
0x14000bfaf  lea     r9, [rbp+string]; string
0x14000bfb3  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14000bfb7  mov     edx, 4; length
0x14000bfbc  lea     rcx, sourceString; "DXDB"
0x14000bfc3  call    cs:__imp_WindowsCreateStringReference
0x14000bfc9  test    eax, eax
0x14000bfcb  js      loc_14000C0CD
0x14000bfd1  lea     r9, [rbp+var_30]
0x14000bfd5  xor     r8d, r8d
0x14000bfd8  mov     rdx, [rbp+string]
0x14000bfdc  mov     rcx, rbx
0x14000bfdf  mov     rax, [rdi+38h]
0x14000bfe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bfe8  mov     ebx, eax
0x14000bfea  test    eax, eax
0x14000bfec  jns     loc_14000C07B
0x14000bff2  mov     edi, 80072EE7h
0x14000bff7  cmp     eax, edi
0x14000bff9  jnz     short loc_14000C02B
0x14000bffb  mov     rcx, [rbp+var_30]
0x14000bfff  test    rcx, rcx
0x14000c002  jz      short loc_14000C011
0x14000c004  mov     rax, [rcx]
0x14000c007  mov     rax, [rax+10h]
0x14000c00b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c010  nop
0x14000c011  mov     rcx, [rbp+var_38]
0x14000c015  test    rcx, rcx
0x14000c018  jz      short loc_14000C027
0x14000c01a  mov     rax, [rcx]
0x14000c01d  mov     rax, [rax+10h]
0x14000c021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c026  nop
0x14000c027  mov     ebx, edi
0x14000c029  jmp     short loc_14000C070
0x14000c02b  mov     rcx, [rbp+8]; this
0x14000c02f  mov     r9d, eax; char *
0x14000c032  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x14000c039  mov     edx, 7Dh ; '}'; void *
0x14000c03e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c043  nop
0x14000c044  mov     rcx, [rbp+var_30]
0x14000c048  test    rcx, rcx
0x14000c04b  jz      short loc_14000C05A
0x14000c04d  mov     rax, [rcx]
0x14000c050  mov     rax, [rax+10h]
0x14000c054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c059  nop
0x14000c05a  mov     rcx, [rbp+var_38]
0x14000c05e  test    rcx, rcx
0x14000c061  jz      short loc_14000C070
0x14000c063  mov     rax, [rcx]
0x14000c066  mov     rax, [rax+10h]
0x14000c06a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c06f  nop
0x14000c070  call    cs:__imp_CoUninitialize
0x14000c076  jmp     loc_14000BF04
0x14000c07b  mov     rcx, [rbp+var_30]
0x14000c07f  test    rcx, rcx
0x14000c082  jz      short loc_14000C091
0x14000c084  mov     rax, [rcx]
0x14000c087  mov     rax, [rax+10h]
0x14000c08b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c090  nop
0x14000c091  mov     rcx, [rbp+var_38]
0x14000c095  test    rcx, rcx
0x14000c098  jz      short loc_14000C0A7
0x14000c09a  mov     rax, [rcx]
0x14000c09d  mov     rax, [rax+10h]
0x14000c0a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c0a6  nop
0x14000c0a7  call    cs:__imp_CoUninitialize
0x14000c0ad  xor     eax, eax
0x14000c0af  mov     rcx, [rbp+var_8]
0x14000c0b3  xor     rcx, rsp; StackCookie
0x14000c0b6  call    __security_check_cookie
0x14000c0bb  lea     r11, [rsp+70h+var_s0]
0x14000c0c0  mov     rbx, [r11+10h]
0x14000c0c4  mov     rdi, [r11+18h]
0x14000c0c8  mov     rsp, r11
0x14000c0cb  pop     rbp
0x14000c0cc  retn
0x14000c0cd  mov     ecx, eax; this
0x14000c0cf  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x14000c0d4  nop
0x14000c0d5  mov     ecx, eax; this
0x14000c0d7  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
