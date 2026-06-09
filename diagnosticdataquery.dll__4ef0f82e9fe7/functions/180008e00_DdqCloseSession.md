# DdqCloseSession

- ea: `0x180008e00`
- end: `0x180008ec8`
- name: `DdqCloseSession`
- size: `200`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007b04`
- `0x180008c60`
- `0x180008e00`
- `0x18000a818`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008e70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008eb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008e70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008eb5`
- `RPCRT4!RpcBindingFree` at `0x180008e61`
- `RPCRT4!RpcBindingFree` at `0x180008ea6`
- `RPCRT4!RpcBindingFree` at `0x180008e61`
- `RPCRT4!RpcBindingFree` at `0x180008ea6`

## pseudocode

```c
__int64 __fastcall DdqCloseSession(void *a1)
{
  Microsoft::Diagnostics::UtcEventTranscriptApiWrapper *v1; // rcx
  int v2; // ebx
  __int64 v3; // rdx
  void **v5; // [rsp+20h] [rbp-10h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  LPVOID pv; // [rsp+40h] [rbp+10h] BYREF

  pv = a1;
  v5 = &Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable';
  Binding = 0;
  v2 = Microsoft::Diagnostics::UtcWrapperBase::Initialize((RPC_BINDING_HANDLE *)&v5);
  if ( v2 < 0 )
  {
    v3 = 90;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (int)"onecore\\base\\telemetry\\utc\\tools\\diagnosticdataquery\\diagnosticdataquery.cpp",
      (const char *)(unsigned int)v2);
    v5 = &Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable';
    if ( Binding )
      RpcBindingFree(&Binding);
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)v2;
  }
  v2 = Microsoft::Diagnostics::UtcEventTranscriptApiWrapper::CloseDiagnosticDataQueryApiSession(v1, &pv);
  if ( v2 < 0 )
  {
    v3 = 92;
    goto LABEL_3;
  }
  v5 = &Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable';
  if ( Binding )
    RpcBindingFree(&Binding);
  if ( pv )
    CoTaskMemFree(pv);
  return 0;
}

```

## disassembly

```asm
0x180008e00  mov     [rsp-8+arg_8], rbx
0x180008e05  push    rbp
0x180008e06  mov     rbp, rsp
0x180008e09  sub     rsp, 30h
0x180008e0d  mov     [rbp+pv], rcx
0x180008e11  lea     rax, ??_7UtcApiUnrestrictedWrapper@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable'
0x180008e18  lea     rcx, [rbp+var_10]; this
0x180008e1c  mov     [rbp+var_10], rax
0x180008e20  mov     [rbp+Binding], 0
0x180008e28  call    ?Initialize@UtcWrapperBase@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::UtcWrapperBase::Initialize(void)
0x180008e2d  mov     ebx, eax
0x180008e2f  test    eax, eax
0x180008e31  jns     short loc_180008E7A
0x180008e33  mov     edx, 5Ah ; 'Z'; void *
0x180008e38  mov     rcx, [rbp+8]; this
0x180008e3c  lea     r8, aOnecoreBaseTel; "onecore\\base\\telemetry\\utc\\tools\\d"...
0x180008e43  mov     r9d, ebx; char *
0x180008e46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e4b  cmp     [rbp+Binding], 0
0x180008e50  lea     rcx, ??_7UtcApiUnrestrictedWrapper@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable'
0x180008e57  mov     [rbp+var_10], rcx
0x180008e5b  jz      short loc_180008E67
0x180008e5d  lea     rcx, [rbp+Binding]; Binding
0x180008e61  call    cs:__imp_RpcBindingFree
0x180008e67  mov     rcx, [rbp+pv]; pv
0x180008e6b  test    rcx, rcx
0x180008e6e  jz      short loc_180008E76
0x180008e70  call    cs:__imp_CoTaskMemFree
0x180008e76  mov     eax, ebx
0x180008e78  jmp     short loc_180008EBD
0x180008e7a  lea     rdx, [rbp+pv]; void **
0x180008e7e  call    ?CloseDiagnosticDataQueryApiSession@UtcEventTranscriptApiWrapper@Diagnostics@Microsoft@@QEBAJPEAPEAX@Z; Microsoft::Diagnostics::UtcEventTranscriptApiWrapper::CloseDiagnosticDataQueryApiSession(void * *)
0x180008e83  mov     ebx, eax
0x180008e85  test    eax, eax
0x180008e87  jns     short loc_180008E90
0x180008e89  mov     edx, 5Ch ; '\'
0x180008e8e  jmp     short loc_180008E38
0x180008e90  cmp     [rbp+Binding], 0
0x180008e95  lea     rcx, ??_7UtcApiUnrestrictedWrapper@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable'
0x180008e9c  mov     [rbp+var_10], rcx
0x180008ea0  jz      short loc_180008EAC
0x180008ea2  lea     rcx, [rbp+Binding]; Binding
0x180008ea6  call    cs:__imp_RpcBindingFree
0x180008eac  mov     rcx, [rbp+pv]; pv
0x180008eb0  test    rcx, rcx
0x180008eb3  jz      short loc_180008EBB
0x180008eb5  call    cs:__imp_CoTaskMemFree
0x180008ebb  xor     eax, eax
0x180008ebd  mov     rbx, [rsp+30h+arg_8]
0x180008ec2  add     rsp, 30h
0x180008ec6  pop     rbp
0x180008ec7  retn
```
