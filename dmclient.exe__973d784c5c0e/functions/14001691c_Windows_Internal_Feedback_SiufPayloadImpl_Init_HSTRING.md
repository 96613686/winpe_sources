# Windows::Internal::Feedback::SiufPayloadImpl::Init(HSTRING__ *)

- ea: `0x14001691c`
- end: `0x140016b31`
- name: `?Init@SiufPayloadImpl@Feedback@Internal@Windows@@AEAAJPEAUHSTRING__@@@Z`
- size: `533`
- prototype: `__int64 __fastcall(Windows::Internal::Feedback::SiufPayloadImpl *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140016c84`

## callees

- `0x14000ac50`
- `0x14001691c`
- `0x140018850`
- `0x140019610`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140016963`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140016963`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140016986`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140016986`

## string_xrefs

- `0x14001695c`: `Windows.Data.Json.JsonValue`
- `0x140016998`: `Failed to activate a JsonValueStatics object.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Internal::Feedback::SiufPayloadImpl::Init(
        Windows::Internal::Feedback::SiufPayloadImpl *this,
        HSTRING a2)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  int ActivationFactory; // eax
  unsigned int v8; // ebx
  __int64 v9; // rcx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // [rsp+20h] [rbp-40h] BYREF
  __int64 v20; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-18h] BYREF

  v19 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    JUMPOUT(0x140016B30LL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v19);
  v8 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    SuifTraceLogging::WriteErrorTraceFormat(
      ActivationFactory,
      568,
      "Windows::Internal::Feedback::SiufPayloadImpl::Init",
      (wchar_t *)L"Failed to activate a JsonValueStatics object.");
    v9 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return v8;
  }
  v20 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v19 + 48LL))(v19, a2, &v20);
  v8 = v11;
  if ( v11 < 0 )
  {
    SuifTraceLogging::WriteErrorTraceFormat(
      v11,
      575,
      "Windows::Internal::Feedback::SiufPayloadImpl::Init",
      (wchar_t *)L"Failed to parse SifuPayload");
    v12 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    v13 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return v8;
  }
  v14 = (*(__int64 (__fastcall **)(__int64, Windows::Internal::Feedback::SiufPayloadImpl *))(*(_QWORD *)v20 + 96LL))(
          v20,
          this);
  v8 = v14;
  if ( v14 < 0 )
  {
    SuifTraceLogging::WriteErrorTraceFormat(
      v14,
      580,
      "Windows::Internal::Feedback::SiufPayloadImpl::Init",
      (wchar_t *)L"GetObjectW failed.");
    v15 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    v16 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return v8;
  }
  v17 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  v18 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return 0;
}

```

## disassembly

```asm
0x14001691c  mov     [rsp-18h+arg_10], rbx
0x140016921  push    rbp
0x140016922  push    rsi
0x140016923  push    rdi
0x140016924  mov     rbp, rsp
0x140016927  sub     rsp, 60h
0x14001692b  mov     rax, cs:__security_cookie
0x140016932  xor     rax, rsp
0x140016935  mov     [rbp+var_10], rax
0x140016939  mov     rsi, rdx
0x14001693c  mov     rdi, rcx
0x14001693f  mov     [rbp+var_40], 0
0x140016947  mov     [rbp+string], 0
0x14001694f  lea     r9, [rbp+string]; string
0x140016953  lea     r8, [rbp+hstringHeader]; hstringHeader
0x140016957  mov     edx, 1Bh; length
0x14001695c  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x140016963  call    cs:__imp_WindowsCreateStringReference
0x14001696a  nop     dword ptr [rax+rax+00h]
0x14001696f  test    eax, eax
0x140016971  js      loc_140016B29
0x140016977  lea     r8, [rbp+var_40]
0x14001697b  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x140016982  mov     rcx, [rbp+string]
0x140016986  call    cs:__imp_RoGetActivationFactory
0x14001698d  nop     dword ptr [rax+rax+00h]
0x140016992  mov     ebx, eax
0x140016994  test    eax, eax
0x140016996  jns     short loc_1400169D8
0x140016998  lea     r9, aFailedToActiva; "Failed to activate a JsonValueStatics o"...
0x14001699f  lea     r8, aWindowsInterna_1; "Windows::Internal::Feedback::SiufPayloa"...
0x1400169a6  mov     edx, 238h; int
0x1400169ab  mov     ecx, eax; int
0x1400169ad  call    ?WriteErrorTraceFormat@SuifTraceLogging@@SAXJHPEBDPEBGZZ; SuifTraceLogging::WriteErrorTraceFormat(long,int,char const *,ushort const *,...)
0x1400169b2  nop
0x1400169b3  mov     rcx, [rbp+var_40]
0x1400169b7  test    rcx, rcx
0x1400169ba  jz      short loc_1400169D1
0x1400169bc  mov     [rbp+var_40], 0
0x1400169c4  mov     rax, [rcx]
0x1400169c7  mov     rax, [rax+10h]
0x1400169cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400169d0  nop
0x1400169d1  mov     eax, ebx
0x1400169d3  jmp     loc_140016B0C
0x1400169d8  mov     [rbp+var_38], 0
0x1400169e0  mov     rcx, [rbp+var_40]
0x1400169e4  mov     rax, [rcx]
0x1400169e7  lea     r8, [rbp+var_38]
0x1400169eb  mov     rdx, rsi
0x1400169ee  mov     rax, [rax+30h]
0x1400169f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400169f7  mov     ebx, eax
0x1400169f9  test    eax, eax
0x1400169fb  jns     short loc_140016A59
0x1400169fd  lea     r9, aFailedToParseS_0; "Failed to parse SifuPayload"
0x140016a04  lea     r8, aWindowsInterna_1; "Windows::Internal::Feedback::SiufPayloa"...
0x140016a0b  mov     edx, 23Fh; int
0x140016a10  mov     ecx, eax; int
0x140016a12  call    ?WriteErrorTraceFormat@SuifTraceLogging@@SAXJHPEBDPEBGZZ; SuifTraceLogging::WriteErrorTraceFormat(long,int,char const *,ushort const *,...)
0x140016a17  nop
0x140016a18  mov     rcx, [rbp+var_38]
0x140016a1c  test    rcx, rcx
0x140016a1f  jz      short loc_140016A36
0x140016a21  mov     [rbp+var_38], 0
0x140016a29  mov     rax, [rcx]
0x140016a2c  mov     rax, [rax+10h]
0x140016a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016a35  nop
0x140016a36  mov     rcx, [rbp+var_40]
0x140016a3a  test    rcx, rcx
0x140016a3d  jz      short loc_140016A54
0x140016a3f  mov     [rbp+var_40], 0
0x140016a47  mov     rax, [rcx]
0x140016a4a  mov     rax, [rax+10h]
0x140016a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016a53  nop
0x140016a54  jmp     loc_1400169D1
0x140016a59  mov     rcx, [rbp+var_38]
0x140016a5d  mov     rax, [rcx]
0x140016a60  mov     rdx, rdi
0x140016a63  mov     rax, [rax+60h]
0x140016a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016a6c  mov     ebx, eax
0x140016a6e  test    eax, eax
0x140016a70  jns     short loc_140016ACE
0x140016a72  lea     r9, aGetobjectwFail; "GetObjectW failed."
0x140016a79  lea     r8, aWindowsInterna_1; "Windows::Internal::Feedback::SiufPayloa"...
0x140016a80  mov     edx, 244h; int
0x140016a85  mov     ecx, eax; int
0x140016a87  call    ?WriteErrorTraceFormat@SuifTraceLogging@@SAXJHPEBDPEBGZZ; SuifTraceLogging::WriteErrorTraceFormat(long,int,char const *,ushort const *,...)
0x140016a8c  nop
0x140016a8d  mov     rcx, [rbp+var_38]
0x140016a91  test    rcx, rcx
0x140016a94  jz      short loc_140016AAB
0x140016a96  mov     [rbp+var_38], 0
0x140016a9e  mov     rax, [rcx]
0x140016aa1  mov     rax, [rax+10h]
0x140016aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016aaa  nop
0x140016aab  mov     rcx, [rbp+var_40]
0x140016aaf  test    rcx, rcx
0x140016ab2  jz      short loc_140016AC9
0x140016ab4  mov     [rbp+var_40], 0
0x140016abc  mov     rax, [rcx]
0x140016abf  mov     rax, [rax+10h]
0x140016ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016ac8  nop
0x140016ac9  jmp     loc_1400169D1
0x140016ace  mov     rcx, [rbp+var_38]
0x140016ad2  test    rcx, rcx
0x140016ad5  jz      short loc_140016AEC
0x140016ad7  mov     [rbp+var_38], 0
0x140016adf  mov     rax, [rcx]
0x140016ae2  mov     rax, [rax+10h]
0x140016ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016aeb  nop
0x140016aec  mov     rcx, [rbp+var_40]
0x140016af0  test    rcx, rcx
0x140016af3  jz      short loc_140016B0A
0x140016af5  mov     [rbp+var_40], 0
0x140016afd  mov     rax, [rcx]
0x140016b00  mov     rax, [rax+10h]
0x140016b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016b09  nop
0x140016b0a  xor     eax, eax
0x140016b0c  mov     rcx, [rbp+var_10]
0x140016b10  xor     rcx, rsp; StackCookie
0x140016b13  call    __security_check_cookie
0x140016b18  mov     rbx, [rsp+60h+arg_10]
0x140016b20  add     rsp, 60h
0x140016b24  pop     rdi
0x140016b25  pop     rsi
0x140016b26  pop     rbp
0x140016b27  retn
0x140016b29  mov     ecx, eax; this
0x140016b2b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
