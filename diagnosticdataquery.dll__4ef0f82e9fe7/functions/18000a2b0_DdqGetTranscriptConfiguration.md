# DdqGetTranscriptConfiguration

- ea: `0x18000a2b0`
- end: `0x18000a37c`
- name: `DdqGetTranscriptConfiguration`
- size: `204`
- prototype: `__int64 __fastcall(void *, struct tagDIAGNOSTIC_DATA_EVENT_TRANSCRIPT_CONFIGURATION *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007b04`
- `0x180008c60`
- `0x18000a2b0`
- `0x18000acf4`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000a312`
- `RPCRT4!RpcBindingFree` at `0x18000a36b`
- `RPCRT4!RpcBindingFree` at `0x18000a312`
- `RPCRT4!RpcBindingFree` at `0x18000a36b`

## pseudocode

```c
__int64 __fastcall DdqGetTranscriptConfiguration(
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
    v6 = 650;
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
  Pointer = (unsigned int)Microsoft::Diagnostics::UtcEventTranscriptApiWrapper::GetTranscriptConfiguration(v4, a1, a2).Pointer;
  if ( (Pointer & 0xFFFF00FF) == 0x87AF0009 )
  {
    Pointer = -2147023673;
LABEL_11:
    v6 = 654;
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
0x18000a2b0  push    rbp
0x18000a2b2  push    rbx
0x18000a2b3  push    rsi
0x18000a2b4  push    rdi
0x18000a2b5  mov     rbp, rsp
0x18000a2b8  sub     rsp, 38h
0x18000a2bc  mov     rsi, rcx
0x18000a2bf  mov     [rbp+Binding], 0
0x18000a2c7  lea     rax, ??_7UtcApiUnrestrictedWrapper@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable'
0x18000a2ce  mov     rdi, rdx
0x18000a2d1  lea     rcx, [rbp+var_18]; this
0x18000a2d5  mov     [rbp+var_18], rax
0x18000a2d9  call    ?Initialize@UtcWrapperBase@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::UtcWrapperBase::Initialize(void)
0x18000a2de  mov     ebx, eax
0x18000a2e0  test    eax, eax
0x18000a2e2  jns     short loc_18000A31C
0x18000a2e4  mov     edx, 28Ah; void *
0x18000a2e9  mov     rcx, [rbp+20h]; this
0x18000a2ed  lea     r8, aOnecoreBaseTel; "onecore\\base\\telemetry\\utc\\tools\\d"...
0x18000a2f4  mov     r9d, ebx; char *
0x18000a2f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a2fc  cmp     [rbp+Binding], 0
0x18000a301  lea     rcx, ??_7UtcApiUnrestrictedWrapper@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable'
0x18000a308  mov     [rbp+var_18], rcx
0x18000a30c  jz      short loc_18000A318
0x18000a30e  lea     rcx, [rbp+Binding]; Binding
0x18000a312  call    cs:__imp_RpcBindingFree
0x18000a318  mov     eax, ebx
0x18000a31a  jmp     short loc_18000A373
0x18000a31c  mov     r8, rdi; struct tagDIAGNOSTIC_DATA_EVENT_TRANSCRIPT_CONFIGURATION *
0x18000a31f  mov     rdx, rsi; void *
0x18000a322  call    ?GetTranscriptConfiguration@UtcEventTranscriptApiWrapper@Diagnostics@Microsoft@@QEBAJPEAXPEAUtagDIAGNOSTIC_DATA_EVENT_TRANSCRIPT_CONFIGURATION@@@Z; Microsoft::Diagnostics::UtcEventTranscriptApiWrapper::GetTranscriptConfiguration(void *,tagDIAGNOSTIC_DATA_EVENT_TRANSCRIPT_CONFIGURATION *)
0x18000a327  mov     ebx, eax
0x18000a329  and     eax, 0FFFF00FFh
0x18000a32e  cmp     eax, 87AF0009h
0x18000a333  jnz     short loc_18000A33C
0x18000a335  mov     ebx, 800704C7h
0x18000a33a  jmp     short loc_18000A34E
0x18000a33c  cmp     eax, 87AF000Eh
0x18000a341  jnz     short loc_18000A34A
0x18000a343  mov     ebx, 80070490h
0x18000a348  jmp     short loc_18000A34E
0x18000a34a  test    ebx, ebx
0x18000a34c  jns     short loc_18000A355
0x18000a34e  mov     edx, 28Eh
0x18000a353  jmp     short loc_18000A2E9
0x18000a355  cmp     [rbp+Binding], 0
0x18000a35a  lea     rcx, ??_7UtcApiUnrestrictedWrapper@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable'
0x18000a361  mov     [rbp+var_18], rcx
0x18000a365  jz      short loc_18000A371
0x18000a367  lea     rcx, [rbp+Binding]; Binding
0x18000a36b  call    cs:__imp_RpcBindingFree
0x18000a371  xor     eax, eax
0x18000a373  add     rsp, 38h
0x18000a377  pop     rdi
0x18000a378  pop     rsi
0x18000a379  pop     rbx
0x18000a37a  pop     rbp
0x18000a37b  retn
```
