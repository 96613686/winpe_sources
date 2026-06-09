# Windows::Internal::Feedback::SiufPayloadImpl::Init(HSTRING__ *)

- ea: `0x140017b80`
- end: `0x140017d88`
- name: `?Init@SiufPayloadImpl@Feedback@Internal@Windows@@AEAAJPEAUHSTRING__@@@Z`
- size: `520`
- prototype: `__int64 __fastcall(Windows::Internal::Feedback::SiufPayloadImpl *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140017d90`

## callees

- `0x14000a9f0`
- `0x140017b80`
- `0x140017fbc`
- `0x1400187e0`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140017bc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140017bc7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140017be4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140017be4`

## string_xrefs

- `0x140017bc0`: `Windows.Data.Json.JsonValue`
- `0x140017bf0`: `Failed to activate a JsonValueStatics object.`

## pseudocode

```c
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
    JUMPOUT(0x140017D87LL);
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
0x140017b80  mov     [rsp-18h+arg_10], rbx
0x140017b85  push    rbp
0x140017b86  push    rsi
0x140017b87  push    rdi
0x140017b88  mov     rbp, rsp
0x140017b8b  sub     rsp, 60h
0x140017b8f  mov     rax, cs:__security_cookie
0x140017b96  xor     rax, rsp
0x140017b99  mov     [rbp+var_10], rax
0x140017b9d  mov     rsi, rdx
0x140017ba0  mov     rdi, rcx
0x140017ba3  mov     [rbp+var_40], 0
0x140017bab  mov     [rbp+string], 0
0x140017bb3  lea     r9, [rbp+string]; string
0x140017bb7  lea     r8, [rbp+hstringHeader]; hstringHeader
0x140017bbb  mov     edx, 1Bh; length
0x140017bc0  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x140017bc7  call    cs:__imp_WindowsCreateStringReference
0x140017bcd  test    eax, eax
0x140017bcf  js      loc_140017D80
0x140017bd5  lea     r8, [rbp+var_40]
0x140017bd9  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x140017be0  mov     rcx, [rbp+string]
0x140017be4  call    cs:__imp_RoGetActivationFactory
0x140017bea  mov     ebx, eax
0x140017bec  test    eax, eax
0x140017bee  jns     short loc_140017C30
0x140017bf0  lea     r9, aFailedToActiva; "Failed to activate a JsonValueStatics o"...
0x140017bf7  lea     r8, aWindowsInterna_1; "Windows::Internal::Feedback::SiufPayloa"...
0x140017bfe  mov     edx, 238h; int
0x140017c03  mov     ecx, eax; int
0x140017c05  call    ?WriteErrorTraceFormat@SuifTraceLogging@@SAXJHPEBDPEBGZZ; SuifTraceLogging::WriteErrorTraceFormat(long,int,char const *,ushort const *,...)
0x140017c0a  nop
0x140017c0b  mov     rcx, [rbp+var_40]
0x140017c0f  test    rcx, rcx
0x140017c12  jz      short loc_140017C29
0x140017c14  mov     [rbp+var_40], 0
0x140017c1c  mov     rax, [rcx]
0x140017c1f  mov     rax, [rax+10h]
0x140017c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017c28  nop
0x140017c29  mov     eax, ebx
0x140017c2b  jmp     loc_140017D64
0x140017c30  mov     [rbp+var_38], 0
0x140017c38  mov     rcx, [rbp+var_40]
0x140017c3c  mov     rax, [rcx]
0x140017c3f  lea     r8, [rbp+var_38]
0x140017c43  mov     rdx, rsi
0x140017c46  mov     rax, [rax+30h]
0x140017c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017c4f  mov     ebx, eax
0x140017c51  test    eax, eax
0x140017c53  jns     short loc_140017CB1
0x140017c55  lea     r9, aFailedToParseS_0; "Failed to parse SifuPayload"
0x140017c5c  lea     r8, aWindowsInterna_1; "Windows::Internal::Feedback::SiufPayloa"...
0x140017c63  mov     edx, 23Fh; int
0x140017c68  mov     ecx, eax; int
0x140017c6a  call    ?WriteErrorTraceFormat@SuifTraceLogging@@SAXJHPEBDPEBGZZ; SuifTraceLogging::WriteErrorTraceFormat(long,int,char const *,ushort const *,...)
0x140017c6f  nop
0x140017c70  mov     rcx, [rbp+var_38]
0x140017c74  test    rcx, rcx
0x140017c77  jz      short loc_140017C8E
0x140017c79  mov     [rbp+var_38], 0
0x140017c81  mov     rax, [rcx]
0x140017c84  mov     rax, [rax+10h]
0x140017c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017c8d  nop
0x140017c8e  mov     rcx, [rbp+var_40]
0x140017c92  test    rcx, rcx
0x140017c95  jz      short loc_140017CAC
0x140017c97  mov     [rbp+var_40], 0
0x140017c9f  mov     rax, [rcx]
0x140017ca2  mov     rax, [rax+10h]
0x140017ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017cab  nop
0x140017cac  jmp     loc_140017C29
0x140017cb1  mov     rcx, [rbp+var_38]
0x140017cb5  mov     rax, [rcx]
0x140017cb8  mov     rdx, rdi
0x140017cbb  mov     rax, [rax+60h]
0x140017cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017cc4  mov     ebx, eax
0x140017cc6  test    eax, eax
0x140017cc8  jns     short loc_140017D26
0x140017cca  lea     r9, aGetobjectwFail; "GetObjectW failed."
0x140017cd1  lea     r8, aWindowsInterna_1; "Windows::Internal::Feedback::SiufPayloa"...
0x140017cd8  mov     edx, 244h; int
0x140017cdd  mov     ecx, eax; int
0x140017cdf  call    ?WriteErrorTraceFormat@SuifTraceLogging@@SAXJHPEBDPEBGZZ; SuifTraceLogging::WriteErrorTraceFormat(long,int,char const *,ushort const *,...)
0x140017ce4  nop
0x140017ce5  mov     rcx, [rbp+var_38]
0x140017ce9  test    rcx, rcx
0x140017cec  jz      short loc_140017D03
0x140017cee  mov     [rbp+var_38], 0
0x140017cf6  mov     rax, [rcx]
0x140017cf9  mov     rax, [rax+10h]
0x140017cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017d02  nop
0x140017d03  mov     rcx, [rbp+var_40]
0x140017d07  test    rcx, rcx
0x140017d0a  jz      short loc_140017D21
0x140017d0c  mov     [rbp+var_40], 0
0x140017d14  mov     rax, [rcx]
0x140017d17  mov     rax, [rax+10h]
0x140017d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017d20  nop
0x140017d21  jmp     loc_140017C29
0x140017d26  mov     rcx, [rbp+var_38]
0x140017d2a  test    rcx, rcx
0x140017d2d  jz      short loc_140017D44
0x140017d2f  mov     [rbp+var_38], 0
0x140017d37  mov     rax, [rcx]
0x140017d3a  mov     rax, [rax+10h]
0x140017d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017d43  nop
0x140017d44  mov     rcx, [rbp+var_40]
0x140017d48  test    rcx, rcx
0x140017d4b  jz      short loc_140017D62
0x140017d4d  mov     [rbp+var_40], 0
0x140017d55  mov     rax, [rcx]
0x140017d58  mov     rax, [rax+10h]
0x140017d5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017d61  nop
0x140017d62  xor     eax, eax
0x140017d64  mov     rcx, [rbp+var_10]
0x140017d68  xor     rcx, rsp; StackCookie
0x140017d6b  call    __security_check_cookie
0x140017d70  mov     rbx, [rsp+60h+arg_10]
0x140017d78  add     rsp, 60h
0x140017d7c  pop     rdi
0x140017d7d  pop     rsi
0x140017d7e  pop     rbp
0x140017d7f  retn
0x140017d80  mov     ecx, eax; this
0x140017d82  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
