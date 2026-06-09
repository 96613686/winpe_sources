# DdqGetSessionAccessLevel

- ea: `0x18000a1d0`
- end: `0x18000a2a0`
- name: `DdqGetSessionAccessLevel`
- size: `208`
- prototype: `__int64 __fastcall(void *, enum tagDdqAccessLevel *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180007b04`
- `0x180008c60`
- `0x18000a1d0`
- `0x18000aca4`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000a259`
- `RPCRT4!RpcBindingFree` at `0x18000a28f`
- `RPCRT4!RpcBindingFree` at `0x18000a259`
- `RPCRT4!RpcBindingFree` at `0x18000a28f`

## pseudocode

```c
__int64 __fastcall DdqGetSessionAccessLevel(void *a1, enum tagDdqAccessLevel *a2)
{
  int Pointer; // ebx
  Microsoft::Diagnostics::UtcEventTranscriptApiWrapper *v6; // rcx
  __int64 v7; // rdx
  void **v8; // [rsp+20h] [rbp-18h] BYREF
  RPC_BINDING_HANDLE Binding[2]; // [rsp+28h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+20h]

  if ( !a1 )
  {
    Pointer = -2147024890;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x65,
      (int)"onecore\\base\\telemetry\\utc\\tools\\diagnosticdataquery\\diagnosticdataquery.cpp",
      (const char *)0x80070006LL);
    return (unsigned int)Pointer;
  }
  Binding[0] = 0;
  v8 = &Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable';
  Pointer = Microsoft::Diagnostics::UtcWrapperBase::Initialize((RPC_BINDING_HANDLE *)&v8);
  if ( Pointer < 0 )
  {
    v7 = 105;
    goto LABEL_6;
  }
  Pointer = (unsigned int)Microsoft::Diagnostics::UtcEventTranscriptApiWrapper::GetDiagnosticSessionAccessLevel(
                            v6,
                            a1,
                            a2).Pointer;
  if ( Pointer < 0 )
  {
    v7 = 107;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (int)"onecore\\base\\telemetry\\utc\\tools\\diagnosticdataquery\\diagnosticdataquery.cpp",
      (const char *)(unsigned int)Pointer);
    v8 = &Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable';
    if ( Binding[0] )
      RpcBindingFree(Binding);
    return (unsigned int)Pointer;
  }
  v8 = &Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable';
  if ( Binding[0] )
    RpcBindingFree(Binding);
  return 0;
}

```

## disassembly

```asm
0x18000a1d0  push    rbp
0x18000a1d2  push    rbx
0x18000a1d3  push    rsi
0x18000a1d4  push    rdi
0x18000a1d5  mov     rbp, rsp
0x18000a1d8  sub     rsp, 38h
0x18000a1dc  mov     rsi, rdx
0x18000a1df  mov     rdi, rcx
0x18000a1e2  test    rcx, rcx
0x18000a1e5  jnz     short loc_18000A209
0x18000a1e7  mov     rcx, [rbp+20h]; this
0x18000a1eb  lea     r8, aOnecoreBaseTel; "onecore\\base\\telemetry\\utc\\tools\\d"...
0x18000a1f2  mov     ebx, 80070006h
0x18000a1f7  lea     edx, [rdi+65h]; void *
0x18000a1fa  mov     r9d, ebx; char *
0x18000a1fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a202  mov     eax, ebx
0x18000a204  jmp     loc_18000A297
0x18000a209  lea     rax, ??_7UtcApiUnrestrictedWrapper@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable'
0x18000a210  mov     [rbp+Binding], 0
0x18000a218  lea     rcx, [rbp+var_18]; this
0x18000a21c  mov     [rbp+var_18], rax
0x18000a220  call    ?Initialize@UtcWrapperBase@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::UtcWrapperBase::Initialize(void)
0x18000a225  mov     ebx, eax
0x18000a227  test    eax, eax
0x18000a229  jns     short loc_18000A261
0x18000a22b  mov     edx, 69h ; 'i'; void *
0x18000a230  mov     rcx, [rbp+20h]; this
0x18000a234  lea     r8, aOnecoreBaseTel; "onecore\\base\\telemetry\\utc\\tools\\d"...
0x18000a23b  mov     r9d, ebx; char *
0x18000a23e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a243  cmp     [rbp+Binding], 0
0x18000a248  lea     rcx, ??_7UtcApiUnrestrictedWrapper@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable'
0x18000a24f  mov     [rbp+var_18], rcx
0x18000a253  jz      short loc_18000A202
0x18000a255  lea     rcx, [rbp+Binding]; Binding
0x18000a259  call    cs:__imp_RpcBindingFree
0x18000a25f  jmp     short loc_18000A202
0x18000a261  mov     r8, rsi; enum tagDdqAccessLevel *
0x18000a264  mov     rdx, rdi; void *
0x18000a267  call    ?GetDiagnosticSessionAccessLevel@UtcEventTranscriptApiWrapper@Diagnostics@Microsoft@@QEAAJPEAXPEAW4tagDdqAccessLevel@@@Z; Microsoft::Diagnostics::UtcEventTranscriptApiWrapper::GetDiagnosticSessionAccessLevel(void *,tagDdqAccessLevel *)
0x18000a26c  mov     ebx, eax
0x18000a26e  test    eax, eax
0x18000a270  jns     short loc_18000A279
0x18000a272  mov     edx, 6Bh ; 'k'
0x18000a277  jmp     short loc_18000A230
0x18000a279  cmp     [rbp+Binding], 0
0x18000a27e  lea     rcx, ??_7UtcApiUnrestrictedWrapper@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable'
0x18000a285  mov     [rbp+var_18], rcx
0x18000a289  jz      short loc_18000A295
0x18000a28b  lea     rcx, [rbp+Binding]; Binding
0x18000a28f  call    cs:__imp_RpcBindingFree
0x18000a295  xor     eax, eax
0x18000a297  add     rsp, 38h
0x18000a29b  pop     rdi
0x18000a29c  pop     rsi
0x18000a29d  pop     rbx
0x18000a29e  pop     rbp
0x18000a29f  retn
```
