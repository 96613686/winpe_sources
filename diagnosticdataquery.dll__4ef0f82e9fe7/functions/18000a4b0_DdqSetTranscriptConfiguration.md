# DdqSetTranscriptConfiguration

- ea: `0x18000a4b0`
- end: `0x18000a57c`
- name: `DdqSetTranscriptConfiguration`
- size: `204`
- prototype: `__int64 __fastcall(void *, struct tagDIAGNOSTIC_DATA_EVENT_TRANSCRIPT_CONFIGURATION *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007b04`
- `0x180008c60`
- `0x18000a4b0`
- `0x18000adcc`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000a512`
- `RPCRT4!RpcBindingFree` at `0x18000a56b`
- `RPCRT4!RpcBindingFree` at `0x18000a512`
- `RPCRT4!RpcBindingFree` at `0x18000a56b`

## pseudocode

```c
__int64 __fastcall DdqSetTranscriptConfiguration(
        void *a1,
        struct tagDIAGNOSTIC_DATA_EVENT_TRANSCRIPT_CONFIGURATION *a2)
{
  Microsoft::Diagnostics::UtcEventTranscriptApiWrapper *v4; // rcx
  int Pointer; // ebx
  __int64 v6; // rdx
  void **v8; // [rsp+20h] [rbp-18h] BYREF
  RPC_BINDING_HANDLE Binding[2]; // [rsp+28h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+20h]

  Binding[0] = 0;
  v8 = &Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable';
  Pointer = Microsoft::Diagnostics::UtcWrapperBase::Initialize((RPC_BINDING_HANDLE *)&v8);
  if ( Pointer < 0 )
  {
    v6 = 636;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (int)"onecore\\base\\telemetry\\utc\\tools\\diagnosticdataquery\\diagnosticdataquery.cpp",
      (const char *)(unsigned int)Pointer);
    v8 = &Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable';
    if ( Binding[0] )
      RpcBindingFree(Binding);
    return (unsigned int)Pointer;
  }
  Pointer = (unsigned int)Microsoft::Diagnostics::UtcEventTranscriptApiWrapper::SetTranscriptConfiguration(v4, a1, a2).Pointer;
  if ( (Pointer & 0xFFFF00FF) == 0x87AF0009 )
  {
    Pointer = -2147023673;
LABEL_11:
    v6 = 640;
    goto LABEL_3;
  }
  if ( (Pointer & 0xFFFF00FF) == 0x87AF000E )
  {
    Pointer = -2147023728;
    goto LABEL_11;
  }
  if ( Pointer < 0 )
    goto LABEL_11;
  v8 = &Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable';
  if ( Binding[0] )
    RpcBindingFree(Binding);
  return 0;
}

```

## disassembly

```asm
0x18000a4b0  push    rbp
0x18000a4b2  push    rbx
0x18000a4b3  push    rsi
0x18000a4b4  push    rdi
0x18000a4b5  mov     rbp, rsp
0x18000a4b8  sub     rsp, 38h
0x18000a4bc  mov     rsi, rcx
0x18000a4bf  mov     [rbp+Binding], 0
0x18000a4c7  lea     rax, ??_7UtcApiUnrestrictedWrapper@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable'
0x18000a4ce  mov     rdi, rdx
0x18000a4d1  lea     rcx, [rbp+var_18]; this
0x18000a4d5  mov     [rbp+var_18], rax
0x18000a4d9  call    ?Initialize@UtcWrapperBase@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::UtcWrapperBase::Initialize(void)
0x18000a4de  mov     ebx, eax
0x18000a4e0  test    eax, eax
0x18000a4e2  jns     short loc_18000A51C
0x18000a4e4  mov     edx, 27Ch; void *
0x18000a4e9  mov     rcx, [rbp+20h]; this
0x18000a4ed  lea     r8, aOnecoreBaseTel; "onecore\\base\\telemetry\\utc\\tools\\d"...
0x18000a4f4  mov     r9d, ebx; char *
0x18000a4f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a4fc  cmp     [rbp+Binding], 0
0x18000a501  lea     rcx, ??_7UtcApiUnrestrictedWrapper@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable'
0x18000a508  mov     [rbp+var_18], rcx
0x18000a50c  jz      short loc_18000A518
0x18000a50e  lea     rcx, [rbp+Binding]; Binding
0x18000a512  call    cs:__imp_RpcBindingFree
0x18000a518  mov     eax, ebx
0x18000a51a  jmp     short loc_18000A573
0x18000a51c  mov     r8, rdi; struct tagDIAGNOSTIC_DATA_EVENT_TRANSCRIPT_CONFIGURATION *
0x18000a51f  mov     rdx, rsi; void *
0x18000a522  call    ?SetTranscriptConfiguration@UtcEventTranscriptApiWrapper@Diagnostics@Microsoft@@QEBAJPEAXPEBUtagDIAGNOSTIC_DATA_EVENT_TRANSCRIPT_CONFIGURATION@@@Z; Microsoft::Diagnostics::UtcEventTranscriptApiWrapper::SetTranscriptConfiguration(void *,tagDIAGNOSTIC_DATA_EVENT_TRANSCRIPT_CONFIGURATION const *)
0x18000a527  mov     ebx, eax
0x18000a529  and     eax, 0FFFF00FFh
0x18000a52e  cmp     eax, 87AF0009h
0x18000a533  jnz     short loc_18000A53C
0x18000a535  mov     ebx, 800704C7h
0x18000a53a  jmp     short loc_18000A54E
0x18000a53c  cmp     eax, 87AF000Eh
0x18000a541  jnz     short loc_18000A54A
0x18000a543  mov     ebx, 80070490h
0x18000a548  jmp     short loc_18000A54E
0x18000a54a  test    ebx, ebx
0x18000a54c  jns     short loc_18000A555
0x18000a54e  mov     edx, 280h
0x18000a553  jmp     short loc_18000A4E9
0x18000a555  cmp     [rbp+Binding], 0
0x18000a55a  lea     rcx, ??_7UtcApiUnrestrictedWrapper@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable'
0x18000a561  mov     [rbp+var_18], rcx
0x18000a565  jz      short loc_18000A571
0x18000a567  lea     rcx, [rbp+Binding]; Binding
0x18000a56b  call    cs:__imp_RpcBindingFree
0x18000a571  xor     eax, eax
0x18000a573  add     rsp, 38h
0x18000a577  pop     rdi
0x18000a578  pop     rsi
0x18000a579  pop     rbx
0x18000a57a  pop     rbp
0x18000a57b  retn
```
