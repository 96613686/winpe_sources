# ReadOneSettingsJsonFileForDxDb(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x14000adf0`
- end: `0x14000b16c`
- name: `?ReadOneSettingsJsonFileForDxDb@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `892`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000eafc`

## callees

- `0x1400022a0`
- `0x1400048b8`
- `0x14000acd8`
- `0x14000adf0`
- `0x14000c8d4`
- `0x140011428`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000b086`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000b12b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000b086`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000b12b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000ae1a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000ae1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000b097`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000b097`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000ae68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000aeec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000b003`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000ae68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000aeec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000b003`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000ae85`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000ae85`

## string_xrefs

- `0x14000ae30`: `onecoreuap\windows\directx\dxg\dxgi\adaptercache\exe\main.cpp`
- `0x14000ae98`: `onecoreuap\windows\directx\dxg\dxgi\adaptercache\exe\main.cpp`
- `0x14000af1b`: `onecoreuap\windows\directx\dxg\dxgi\adaptercache\exe\main.cpp`
- `0x14000af87`: `onecoreuap\windows\directx\dxg\dxgi\adaptercache\exe\main.cpp`
- `0x14000b032`: `onecoreuap\windows\directx\dxg\dxgi\adaptercache\exe\main.cpp`

## pseudocode

```c
__int64 __fastcall ReadOneSettingsJsonFileForDxDb(char **a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  HRESULT v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  int ActivationFactory; // eax
  __int64 *v9; // rbx
  __int64 v10; // rsi
  HRESULT v11; // eax
  int v12; // edx
  unsigned int v13; // r8d
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  __int64 *v17; // rbx
  __int64 v18; // rsi
  HRESULT v19; // eax
  int v20; // edx
  unsigned int v21; // r8d
  int v22; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v24; // r8
  unsigned __int64 v25; // rdx
  char *v26; // rsi
  __int64 v27; // rbx
  int v28; // [rsp+20h] [rbp-50h]
  __int64 *v29; // [rsp+28h] [rbp-48h] BYREF
  __int64 *v30; // [rsp+30h] [rbp-40h] BYREF
  __int64 *v31; // [rsp+38h] [rbp-38h] BYREF
  HSTRING v32; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  HSTRING string; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v2 = CoInitializeEx(0, 0);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\adaptercache\\exe\\main.cpp",
      (const char *)(unsigned int)v2,
      v28);
    return v3;
  }
  LOBYTE(v28) = 1;
  v30 = 0;
  string = 0;
  v5 = WindowsCreateStringReference(
         L"Windows.Internal.Flighting.OneSettings.OneSettingsPayload",
         0x39u,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
    goto LABEL_49;
  ActivationFactory = RoGetActivationFactory(string, &GUID_d70cd0ed_0f1b_4bec_9bec_c230dc7996b0, &v30);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\adaptercache\\exe\\main.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v28);
    if ( v30 )
      (*(void (__fastcall **)(__int64 *))(*v30 + 16))(v30);
LABEL_32:
    CoUninitialize();
    return v3;
  }
  v29 = 0;
  v9 = v30;
  v10 = *v30;
  v29 = 0;
  string = 0;
  v11 = WindowsCreateStringReference(L"DXDB", 4u, &hstringHeader, &string);
  if ( v11 < 0 )
  {
LABEL_50:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v11, v12, v13);
    JUMPOUT(0x14000B16BLL);
  }
  v14 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 **))(v10 + 48))(v9, string, &v29);
  v3 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\adaptercache\\exe\\main.cpp",
      (const char *)(unsigned int)v14,
      v28);
    if ( v29 )
      (*(void (__fastcall **)(__int64 *))(*v29 + 16))(v29);
    if ( v30 )
      (*(void (__fastcall **)(__int64 *))(*v30 + 16))(v30);
    goto LABEL_32;
  }
  v31 = 0;
  v15 = *v29;
  v31 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v15 + 96))(v29, &v31);
  v3 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x91,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\adaptercache\\exe\\main.cpp",
      (const char *)(unsigned int)v16,
      v28);
    if ( v31 )
      (*(void (__fastcall **)(__int64 *))(*v31 + 16))(v31);
    if ( v29 )
      (*(void (__fastcall **)(__int64 *))(*v29 + 16))(v29);
    if ( v30 )
      (*(void (__fastcall **)(__int64 *))(*v30 + 16))(v30);
    goto LABEL_32;
  }
  v32 = 0;
  v17 = v31;
  v18 = *v31;
  string = 0;
  v19 = WindowsCreateStringReference(L"VERSION", 7u, &hstringHeader, &string);
  if ( v19 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v19, v20, v21);
LABEL_49:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
    goto LABEL_50;
  }
  v22 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING *))(v18 + 80))(v17, string, &v32);
  v3 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x95,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\adaptercache\\exe\\main.cpp",
      (const char *)(unsigned int)v22,
      v28);
    if ( v31 )
      (*(void (__fastcall **)(__int64 *))(*v31 + 16))(v31);
    if ( v29 )
      (*(void (__fastcall **)(__int64 *))(*v29 + 16))(v29);
    if ( v30 )
      (*(void (__fastcall **)(__int64 *))(*v30 + 16))(v30);
    goto LABEL_32;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v32, 0);
  v25 = -1;
  do
    ++v25;
  while ( StringRawBuffer[v25] );
  if ( v25 > (unsigned __int64)a1[3] )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      a1,
      v25,
      v24,
      StringRawBuffer);
  }
  else
  {
    if ( (unsigned __int64)a1[3] <= 7 )
      v26 = (char *)a1;
    else
      v26 = *a1;
    a1[2] = (char *)v25;
    v27 = 2 * v25;
    memmove_0(v26, StringRawBuffer, 2 * v25);
    *(_WORD *)&v26[v27] = 0;
  }
  if ( v31 )
    (*(void (__fastcall **)(__int64 *))(*v31 + 16))(v31);
  if ( v29 )
    (*(void (__fastcall **)(__int64 *))(*v29 + 16))(v29);
  if ( v30 )
    (*(void (__fastcall **)(__int64 *))(*v30 + 16))(v30);
  CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x14000adf0  mov     [rsp-18h+arg_8], rbx
0x14000adf5  mov     [rsp-18h+arg_10], rsi
0x14000adfa  push    rbp
0x14000adfb  push    rdi
0x14000adfc  push    r14
0x14000adfe  mov     rbp, rsp
0x14000ae01  sub     rsp, 70h
0x14000ae05  mov     rax, cs:__security_cookie
0x14000ae0c  xor     rax, rsp
0x14000ae0f  mov     [rbp+var_8], rax
0x14000ae13  mov     rdi, rcx
0x14000ae16  xor     edx, edx; dwCoInit
0x14000ae18  xor     ecx, ecx; pvReserved
0x14000ae1a  call    cs:__imp_CoInitializeEx
0x14000ae20  mov     ebx, eax
0x14000ae22  xor     r14d, r14d
0x14000ae25  test    eax, eax
0x14000ae27  jns     short loc_14000AE48
0x14000ae29  mov     rcx, [rbp+18h]; this
0x14000ae2d  mov     r9d, eax; char *
0x14000ae30  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x14000ae37  mov     edx, 84h; void *
0x14000ae3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ae41  mov     eax, ebx
0x14000ae43  jmp     loc_14000B133
0x14000ae48  mov     [rbp+var_50], 1
0x14000ae4c  mov     [rbp+var_40], r14
0x14000ae50  mov     [rbp+string], r14
0x14000ae54  lea     r9, [rbp+string]; string
0x14000ae58  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14000ae5c  mov     edx, 39h ; '9'; length
0x14000ae61  lea     rcx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsPayload@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x14000ae68  call    cs:__imp_WindowsCreateStringReference
0x14000ae6e  test    eax, eax
0x14000ae70  js      loc_14000B15C
0x14000ae76  lea     r8, [rbp+var_40]
0x14000ae7a  lea     rdx, _GUID_d70cd0ed_0f1b_4bec_9bec_c230dc7996b0
0x14000ae81  mov     rcx, [rbp+string]
0x14000ae85  call    cs:__imp_RoGetActivationFactory
0x14000ae8b  mov     ebx, eax
0x14000ae8d  test    eax, eax
0x14000ae8f  jns     short loc_14000AEC5
0x14000ae91  mov     rcx, [rbp+18h]; this
0x14000ae95  mov     r9d, eax; char *
0x14000ae98  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x14000ae9f  mov     edx, 8Bh; void *
0x14000aea4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000aea9  nop
0x14000aeaa  mov     rcx, [rbp+var_40]
0x14000aeae  test    rcx, rcx
0x14000aeb1  jz      short loc_14000AEC0
0x14000aeb3  mov     rax, [rcx]
0x14000aeb6  mov     rax, [rax+10h]
0x14000aeba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aebf  nop
0x14000aec0  jmp     loc_14000B086
0x14000aec5  mov     [rbp+var_48], r14
0x14000aec9  mov     rbx, [rbp+var_40]
0x14000aecd  mov     rsi, [rbx]
0x14000aed0  mov     [rbp+var_48], r14
0x14000aed4  mov     [rbp+string], r14
0x14000aed8  lea     r9, [rbp+string]; string
0x14000aedc  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14000aee0  mov     edx, 4; length
0x14000aee5  lea     rcx, sourceString; "DXDB"
0x14000aeec  call    cs:__imp_WindowsCreateStringReference
0x14000aef2  test    eax, eax
0x14000aef4  js      loc_14000B164
0x14000aefa  lea     r8, [rbp+var_48]
0x14000aefe  mov     rdx, [rbp+string]
0x14000af02  mov     rcx, rbx
0x14000af05  mov     rax, [rsi+30h]
0x14000af09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000af0e  mov     ebx, eax
0x14000af10  test    eax, eax
0x14000af12  jns     short loc_14000AF5E
0x14000af14  mov     rcx, [rbp+18h]; this
0x14000af18  mov     r9d, eax; char *
0x14000af1b  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x14000af22  mov     edx, 8Eh; void *
0x14000af27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000af2c  nop
0x14000af2d  mov     rcx, [rbp+var_48]
0x14000af31  test    rcx, rcx
0x14000af34  jz      short loc_14000AF43
0x14000af36  mov     rax, [rcx]
0x14000af39  mov     rax, [rax+10h]
0x14000af3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000af42  nop
0x14000af43  mov     rcx, [rbp+var_40]
0x14000af47  test    rcx, rcx
0x14000af4a  jz      short loc_14000AF59
0x14000af4c  mov     rax, [rcx]
0x14000af4f  mov     rax, [rax+10h]
0x14000af53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000af58  nop
0x14000af59  jmp     loc_14000B086
0x14000af5e  mov     [rbp+var_38], r14
0x14000af62  mov     rcx, [rbp+var_48]
0x14000af66  mov     rax, [rcx]
0x14000af69  mov     [rbp+var_38], r14
0x14000af6d  lea     rdx, [rbp+var_38]
0x14000af71  mov     rax, [rax+60h]
0x14000af75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000af7a  mov     ebx, eax
0x14000af7c  test    eax, eax
0x14000af7e  jns     short loc_14000AFE0
0x14000af80  mov     rcx, [rbp+18h]; this
0x14000af84  mov     r9d, eax; char *
0x14000af87  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x14000af8e  mov     edx, 91h; void *
0x14000af93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000af98  nop
0x14000af99  mov     rcx, [rbp+var_38]
0x14000af9d  test    rcx, rcx
0x14000afa0  jz      short loc_14000AFAF
0x14000afa2  mov     rax, [rcx]
0x14000afa5  mov     rax, [rax+10h]
0x14000afa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000afae  nop
0x14000afaf  mov     rcx, [rbp+var_48]
0x14000afb3  test    rcx, rcx
0x14000afb6  jz      short loc_14000AFC5
0x14000afb8  mov     rax, [rcx]
0x14000afbb  mov     rax, [rax+10h]
0x14000afbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000afc4  nop
0x14000afc5  mov     rcx, [rbp+var_40]
0x14000afc9  test    rcx, rcx
0x14000afcc  jz      short loc_14000AFDB
0x14000afce  mov     rax, [rcx]
0x14000afd1  mov     rax, [rax+10h]
0x14000afd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000afda  nop
0x14000afdb  jmp     loc_14000B086
0x14000afe0  mov     [rbp+var_30], r14
0x14000afe4  mov     rbx, [rbp+var_38]
0x14000afe8  mov     rsi, [rbx]
0x14000afeb  mov     [rbp+string], r14
0x14000afef  lea     r9, [rbp+string]; string
0x14000aff3  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14000aff7  mov     edx, 7; length
0x14000affc  lea     rcx, aVersion_0; "VERSION"
0x14000b003  call    cs:__imp_WindowsCreateStringReference
0x14000b009  test    eax, eax
0x14000b00b  js      loc_14000B154
0x14000b011  lea     r8, [rbp+var_30]
0x14000b015  mov     rdx, [rbp+string]
0x14000b019  mov     rcx, rbx
0x14000b01c  mov     rax, [rsi+50h]
0x14000b020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b025  mov     ebx, eax
0x14000b027  test    eax, eax
0x14000b029  jns     short loc_14000B091
0x14000b02b  mov     rcx, [rbp+18h]; this
0x14000b02f  mov     r9d, eax; char *
0x14000b032  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x14000b039  mov     edx, 95h; void *
0x14000b03e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b043  nop
0x14000b044  mov     rcx, [rbp+var_38]
0x14000b048  test    rcx, rcx
0x14000b04b  jz      short loc_14000B05A
0x14000b04d  mov     rax, [rcx]
0x14000b050  mov     rax, [rax+10h]
0x14000b054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b059  nop
0x14000b05a  mov     rcx, [rbp+var_48]
0x14000b05e  test    rcx, rcx
0x14000b061  jz      short loc_14000B070
0x14000b063  mov     rax, [rcx]
0x14000b066  mov     rax, [rax+10h]
0x14000b06a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b06f  nop
0x14000b070  mov     rcx, [rbp+var_40]
0x14000b074  test    rcx, rcx
0x14000b077  jz      short loc_14000B086
0x14000b079  mov     rax, [rcx]
0x14000b07c  mov     rax, [rax+10h]
0x14000b080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b085  nop
0x14000b086  call    cs:__imp_CoUninitialize
0x14000b08c  jmp     loc_14000AE41
0x14000b091  xor     edx, edx; length
0x14000b093  mov     rcx, [rbp+var_30]; string
0x14000b097  call    cs:__imp_WindowsGetStringRawBuffer
0x14000b09d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000b0a1  inc     rdx
0x14000b0a4  cmp     [rax+rdx*2], r14w
0x14000b0a9  jnz     short loc_14000B0A1
0x14000b0ab  cmp     rdx, [rdi+18h]
0x14000b0af  ja      short loc_14000B0DD
0x14000b0b1  cmp     qword ptr [rdi+18h], 7
0x14000b0b6  jbe     short loc_14000B0BD
0x14000b0b8  mov     rsi, [rdi]
0x14000b0bb  jmp     short loc_14000B0C0
0x14000b0bd  mov     rsi, rdi
0x14000b0c0  mov     [rdi+10h], rdx
0x14000b0c4  lea     rbx, [rdx+rdx]
0x14000b0c8  mov     r8, rbx; Size
0x14000b0cb  mov     rdx, rax; Src
0x14000b0ce  mov     rcx, rsi; void *
0x14000b0d1  call    memmove_0
0x14000b0d6  mov     [rbx+rsi], r14w
0x14000b0db  jmp     short loc_14000B0E9
0x14000b0dd  mov     r9, rax
0x14000b0e0  mov     rcx, rdi
0x14000b0e3  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x14000b0e8  nop
0x14000b0e9  mov     rcx, [rbp+var_38]
0x14000b0ed  test    rcx, rcx
0x14000b0f0  jz      short loc_14000B0FF
0x14000b0f2  mov     rax, [rcx]
0x14000b0f5  mov     rax, [rax+10h]
0x14000b0f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b0fe  nop
0x14000b0ff  mov     rcx, [rbp+var_48]
0x14000b103  test    rcx, rcx
0x14000b106  jz      short loc_14000B115
0x14000b108  mov     rax, [rcx]
0x14000b10b  mov     rax, [rax+10h]
0x14000b10f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b114  nop
0x14000b115  mov     rcx, [rbp+var_40]
0x14000b119  test    rcx, rcx
0x14000b11c  jz      short loc_14000B12B
0x14000b11e  mov     rax, [rcx]
0x14000b121  mov     rax, [rax+10h]
0x14000b125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b12a  nop
0x14000b12b  call    cs:__imp_CoUninitialize
0x14000b131  xor     eax, eax
0x14000b133  mov     rcx, [rbp+var_8]
0x14000b137  xor     rcx, rsp; StackCookie
0x14000b13a  call    __security_check_cookie
0x14000b13f  lea     r11, [rsp+70h+var_s0]
0x14000b144  mov     rbx, [r11+28h]
0x14000b148  mov     rsi, [r11+30h]
0x14000b14c  mov     rsp, r11
0x14000b14f  pop     r14
0x14000b151  pop     rdi
0x14000b152  pop     rbp
0x14000b153  retn
0x14000b154  mov     ecx, eax; this
0x14000b156  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x14000b15b  nop
0x14000b15c  mov     ecx, eax; this
0x14000b15e  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x14000b163  nop
0x14000b164  mov     ecx, eax; this
0x14000b166  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
