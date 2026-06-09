# DdqCreateSession

- ea: `0x180008ed0`
- end: `0x180008f8d`
- name: `DdqCreateSession`
- size: `189`
- prototype: `__int64 __fastcall(unsigned int, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180007b04`
- `0x180008c60`
- `0x180008ed0`
- `0x18000a864`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180008f31`
- `RPCRT4!RpcBindingFree` at `0x180008f7c`
- `RPCRT4!RpcBindingFree` at `0x180008f31`
- `RPCRT4!RpcBindingFree` at `0x180008f7c`

## pseudocode

```c
__int64 __fastcall DdqCreateSession(unsigned int a1, _QWORD *a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  bool v7; // zf
  void **v8; // [rsp+20h] [rbp-18h] BYREF
  RPC_BINDING_HANDLE Binding[2]; // [rsp+28h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+20h]
  __int64 v11; // [rsp+70h] [rbp+38h] BYREF

  Binding[0] = 0;
  v8 = &Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable';
  v4 = Microsoft::Diagnostics::UtcWrapperBase::Initialize((Microsoft::Diagnostics::UtcWrapperBase *)&v8);
  if ( v4 < 0 )
  {
    v5 = 67;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\telemetry\\utc\\tools\\diagnosticdataquery\\diagnosticdataquery.cpp",
      (const char *)(unsigned int)v4,
      (int)v8);
    v8 = &Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable';
    if ( Binding[0] )
      RpcBindingFree(Binding);
    return (unsigned int)v4;
  }
  v11 = 0;
  v4 = Microsoft::Diagnostics::UtcEventTranscriptApiWrapper::CreateDiagnosticDataQueryApiSession(&v8, a1, &v11);
  if ( v4 < 0 )
  {
    v5 = 70;
    goto LABEL_3;
  }
  v7 = Binding[0] == 0;
  *a2 = v11;
  v8 = &Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable';
  if ( !v7 )
    RpcBindingFree(Binding);
  return 0;
}

```

## disassembly

```asm
0x180008ed0  push    rbp
0x180008ed2  push    rbx
0x180008ed3  push    rsi
0x180008ed4  push    rdi
0x180008ed5  mov     rbp, rsp
0x180008ed8  sub     rsp, 38h
0x180008edc  mov     esi, ecx
0x180008ede  mov     [rbp+Binding], 0
0x180008ee6  lea     rax, ??_7UtcApiUnrestrictedWrapper@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable'
0x180008eed  mov     rdi, rdx
0x180008ef0  lea     rcx, [rbp+var_18]; this
0x180008ef4  mov     [rbp+var_18], rax
0x180008ef8  call    ?Initialize@UtcWrapperBase@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::UtcWrapperBase::Initialize(void)
0x180008efd  mov     ebx, eax
0x180008eff  test    eax, eax
0x180008f01  jns     short loc_180008F3B
0x180008f03  mov     edx, 43h ; 'C'; void *
0x180008f08  mov     rcx, [rbp+20h]; this
0x180008f0c  lea     r8, aOnecoreBaseTel; "onecore\\base\\telemetry\\utc\\tools\\d"...
0x180008f13  mov     r9d, ebx; char *
0x180008f16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f1b  cmp     [rbp+Binding], 0
0x180008f20  lea     rcx, ??_7UtcApiUnrestrictedWrapper@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable'
0x180008f27  mov     [rbp+var_18], rcx
0x180008f2b  jz      short loc_180008F37
0x180008f2d  lea     rcx, [rbp+Binding]; Binding
0x180008f31  call    cs:__imp_RpcBindingFree
0x180008f37  mov     eax, ebx
0x180008f39  jmp     short loc_180008F84
0x180008f3b  lea     r8, [rbp+arg_10]
0x180008f3f  mov     [rbp+arg_10], 0
0x180008f47  mov     edx, esi
0x180008f49  lea     rcx, [rbp+var_18]
0x180008f4d  call    ?CreateDiagnosticDataQueryApiSession@UtcEventTranscriptApiWrapper@Diagnostics@Microsoft@@QEBAJW4tagDdqAccessLevel@@PEAPEAX@Z; Microsoft::Diagnostics::UtcEventTranscriptApiWrapper::CreateDiagnosticDataQueryApiSession(tagDdqAccessLevel,void * *)
0x180008f52  mov     ebx, eax
0x180008f54  test    eax, eax
0x180008f56  jns     short loc_180008F5F
0x180008f58  mov     edx, 46h ; 'F'
0x180008f5d  jmp     short loc_180008F08
0x180008f5f  cmp     [rbp+Binding], 0
0x180008f64  lea     rcx, ??_7UtcApiUnrestrictedWrapper@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable'
0x180008f6b  mov     rax, [rbp+arg_10]
0x180008f6f  mov     [rdi], rax
0x180008f72  mov     [rbp+var_18], rcx
0x180008f76  jz      short loc_180008F82
0x180008f78  lea     rcx, [rbp+Binding]; Binding
0x180008f7c  call    cs:__imp_RpcBindingFree
0x180008f82  xor     eax, eax
0x180008f84  add     rsp, 38h
0x180008f88  pop     rdi
0x180008f89  pop     rsi
0x180008f8a  pop     rbx
0x180008f8b  pop     rbp
0x180008f8c  retn
```
