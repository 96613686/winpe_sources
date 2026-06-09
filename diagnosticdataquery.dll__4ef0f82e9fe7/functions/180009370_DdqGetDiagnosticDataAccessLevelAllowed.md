# DdqGetDiagnosticDataAccessLevelAllowed

- ea: `0x180009370`
- end: `0x180009426`
- name: `DdqGetDiagnosticDataAccessLevelAllowed`
- size: `182`
- prototype: `__int64 __fastcall(enum tagDdqAccessLevel *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180007b04`
- `0x180008c60`
- `0x180009370`
- `0x18000ac54`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x1800093d5`
- `RPCRT4!RpcBindingFree` at `0x18000940e`
- `RPCRT4!RpcBindingFree` at `0x1800093d5`
- `RPCRT4!RpcBindingFree` at `0x18000940e`

## pseudocode

```c
__int64 __fastcall DdqGetDiagnosticDataAccessLevelAllowed(enum tagDdqAccessLevel *a1)
{
  int Pointer; // ebx
  __int64 v3; // rdx
  void **v5; // [rsp+20h] [rbp-10h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]

  Binding = 0;
  v5 = &Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable';
  Pointer = Microsoft::Diagnostics::UtcWrapperBase::Initialize((RPC_BINDING_HANDLE *)&v5);
  if ( Pointer < 0 )
  {
    v3 = 116;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (int)"onecore\\base\\telemetry\\utc\\tools\\diagnosticdataquery\\diagnosticdataquery.cpp",
      (const char *)(unsigned int)Pointer);
    v5 = &Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable';
    if ( Binding )
      RpcBindingFree(&Binding);
    return (unsigned int)Pointer;
  }
  Pointer = (unsigned int)Microsoft::Diagnostics::UtcEventTranscriptApiWrapper::GetDiagnosticDataAccessAllowed(
                            (Microsoft::Diagnostics::UtcEventTranscriptApiWrapper *)&v5,
                            a1).Pointer;
  if ( Pointer < 0 )
  {
    v3 = 118;
    goto LABEL_3;
  }
  v5 = &Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable';
  if ( Binding )
    RpcBindingFree(&Binding);
  return 0;
}

```

## disassembly

```asm
0x180009370  mov     [rsp-8+arg_0], rbx
0x180009375  mov     [rsp-8+arg_8], rdi
0x18000937a  push    rbp
0x18000937b  mov     rbp, rsp
0x18000937e  sub     rsp, 30h
0x180009382  mov     rdi, rcx
0x180009385  mov     [rbp+Binding], 0
0x18000938d  lea     rax, ??_7UtcApiUnrestrictedWrapper@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable'
0x180009394  lea     rcx, [rbp+var_10]; this
0x180009398  mov     [rbp+var_10], rax
0x18000939c  call    ?Initialize@UtcWrapperBase@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::UtcWrapperBase::Initialize(void)
0x1800093a1  mov     ebx, eax
0x1800093a3  test    eax, eax
0x1800093a5  jns     short loc_1800093DF
0x1800093a7  mov     edx, 74h ; 't'; void *
0x1800093ac  mov     rcx, [rbp+8]; this
0x1800093b0  lea     r8, aOnecoreBaseTel; "onecore\\base\\telemetry\\utc\\tools\\d"...
0x1800093b7  mov     r9d, ebx; char *
0x1800093ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800093bf  cmp     [rbp+Binding], 0
0x1800093c4  lea     rcx, ??_7UtcApiUnrestrictedWrapper@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable'
0x1800093cb  mov     [rbp+var_10], rcx
0x1800093cf  jz      short loc_1800093DB
0x1800093d1  lea     rcx, [rbp+Binding]; Binding
0x1800093d5  call    cs:__imp_RpcBindingFree
0x1800093db  mov     eax, ebx
0x1800093dd  jmp     short loc_180009416
0x1800093df  mov     rdx, rdi; enum tagDdqAccessLevel *
0x1800093e2  lea     rcx, [rbp+var_10]; this
0x1800093e6  call    ?GetDiagnosticDataAccessAllowed@UtcEventTranscriptApiWrapper@Diagnostics@Microsoft@@QEAAJPEAW4tagDdqAccessLevel@@@Z; Microsoft::Diagnostics::UtcEventTranscriptApiWrapper::GetDiagnosticDataAccessAllowed(tagDdqAccessLevel *)
0x1800093eb  mov     ebx, eax
0x1800093ed  test    eax, eax
0x1800093ef  jns     short loc_1800093F8
0x1800093f1  mov     edx, 76h ; 'v'
0x1800093f6  jmp     short loc_1800093AC
0x1800093f8  cmp     [rbp+Binding], 0
0x1800093fd  lea     rcx, ??_7UtcApiUnrestrictedWrapper@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::UtcApiUnrestrictedWrapper::`vftable'
0x180009404  mov     [rbp+var_10], rcx
0x180009408  jz      short loc_180009414
0x18000940a  lea     rcx, [rbp+Binding]; Binding
0x18000940e  call    cs:__imp_RpcBindingFree
0x180009414  xor     eax, eax
0x180009416  mov     rbx, [rsp+30h+arg_0]
0x18000941b  mov     rdi, [rsp+30h+arg_8]
0x180009420  add     rsp, 30h
0x180009424  pop     rbp
0x180009425  retn
```
