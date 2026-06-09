# ORpcClient::CreateBinding(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18001136c`
- end: `0x18001149c`
- name: `?CreateBinding@ORpcClient@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@000@Z`
- size: `304`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *Binding, RPC_WSTR Endpoint, RPC_WSTR ProtSeq, RPC_WSTR NetworkAddr, RPC_WSTR)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000957c`

## callees

- `0x18001136c`
- `0x180011618`
- `0x180011690`
- `0x18003bec8`
- `0x18003e690`
- `0x1800409e0`
- `0x180043d40`
- `0x180135c94`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x18001141e`
- `RPCRT4!RpcStringFreeW` at `0x18001141e`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800113ed`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800113ed`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180011411`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180011411`

## string_xrefs

- `0x180011453`: `RpcStringBindingCompose failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall ORpcClient::CreateBinding(
        RPC_BINDING_HANDLE *Binding,
        unsigned __int16 *Endpoint,
        unsigned __int16 *ProtSeq,
        unsigned __int16 *NetworkAddr,
        RPC_WSTR a5)
{
  unsigned __int16 *Options; // r14
  unsigned int v10; // eax
  __int64 v11; // rdx
  unsigned int v12; // edi
  __int64 v13; // rdx
  RPC_WSTR String[2]; // [rsp+30h] [rbp-3D8h] BYREF
  _BYTE pExceptionObject[912]; // [rsp+40h] [rbp-3C8h] BYREF

  Options = a5;
  String[0] = 0;
  ORpcClient::ReleaseBinding(Binding);
  if ( *((_QWORD *)a5 + 3) > 7u )
    Options = *(unsigned __int16 **)a5;
  if ( *((_QWORD *)Endpoint + 3) > 7u )
    Endpoint = *(unsigned __int16 **)Endpoint;
  if ( *((_QWORD *)NetworkAddr + 3) > 7u )
    NetworkAddr = *(unsigned __int16 **)NetworkAddr;
  if ( *((_QWORD *)ProtSeq + 3) > 7u )
    ProtSeq = *(unsigned __int16 **)ProtSeq;
  v10 = RpcStringBindingComposeW(0, ProtSeq, NetworkAddr, Endpoint, Options, String);
  if ( v10 )
  {
    OException::OException(pExceptionObject, v11, v10, L"RpcStringBindingCompose failed");
    throw (OException *)pExceptionObject;
  }
  String[1] = (RPC_WSTR)(Binding + 1);
  std::_Mutex_base::lock((std::_Mutex_base *)(Binding + 1));
  v12 = RpcBindingFromStringBindingW(String[0], Binding);
  RpcStringFreeW(String);
  if ( v12 )
  {
    OException::OException(pExceptionObject, v13, v12);
    throw (OException *)pExceptionObject;
  }
  return Mtx_unlock((_Mtx_t)(Binding + 1));
}

```

## disassembly

```asm
0x18001136c  push    rbx
0x18001136e  push    rbp
0x18001136f  push    rsi
0x180011370  push    rdi
0x180011371  push    r14
0x180011373  sub     rsp, 3E0h
0x18001137a  mov     rax, cs:__security_cookie
0x180011381  xor     rax, rsp
0x180011384  mov     [rsp+408h+var_38], rax
0x18001138c  mov     rdi, r9
0x18001138f  mov     rbx, r8
0x180011392  mov     rsi, rdx
0x180011395  mov     rbp, rcx
0x180011398  mov     r14, [rsp+408h+arg_20]
0x1800113a0  mov     [rsp+408h+String], 0
0x1800113a9  call    ?ReleaseBinding@ORpcClient@@QEAAXXZ; ORpcClient::ReleaseBinding(void)
0x1800113ae  cmp     qword ptr [r14+18h], 7
0x1800113b3  jbe     short loc_1800113B8
0x1800113b5  mov     r14, [r14]
0x1800113b8  cmp     qword ptr [rsi+18h], 7
0x1800113bd  jbe     short loc_1800113C2
0x1800113bf  mov     rsi, [rsi]
0x1800113c2  cmp     qword ptr [rdi+18h], 7
0x1800113c7  jbe     short loc_1800113CC
0x1800113c9  mov     rdi, [rdi]
0x1800113cc  cmp     qword ptr [rbx+18h], 7
0x1800113d1  ja      short loc_18001144E
0x1800113d3  lea     rax, [rsp+408h+String]
0x1800113d8  mov     [rsp+408h+StringBinding], rax; StringBinding
0x1800113dd  mov     [rsp+408h+Options], r14; Options
0x1800113e2  mov     r9, rsi; Endpoint
0x1800113e5  mov     r8, rdi; NetworkAddr
0x1800113e8  mov     rdx, rbx; ProtSeq
0x1800113eb  xor     ecx, ecx; ObjUuid
0x1800113ed  call    cs:__imp_RpcStringBindingComposeW
0x1800113f3  test    eax, eax
0x1800113f5  jnz     short loc_180011453
0x1800113f7  lea     rbx, [rbp+8]
0x1800113fb  mov     [rsp+408h+var_3D0], rbx
0x180011400  mov     rcx, rbx; this
0x180011403  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180011408  nop
0x180011409  mov     rdx, rbp; Binding
0x18001140c  mov     rcx, [rsp+408h+String]; StringBinding
0x180011411  call    cs:__imp_RpcBindingFromStringBindingW
0x180011417  mov     edi, eax
0x180011419  lea     rcx, [rsp+408h+String]; String
0x18001141e  call    cs:__imp_RpcStringFreeW
0x180011424  test    edi, edi
0x180011426  jnz     short loc_18001147D
0x180011428  mov     rcx, rbx; _Mtx_t
0x18001142b  call    _Mtx_unlock
0x180011430  mov     rcx, [rsp+408h+var_38]
0x180011438  xor     rcx, rsp; StackCookie
0x18001143b  call    __security_check_cookie
0x180011440  add     rsp, 3E0h
0x180011447  pop     r14
0x180011449  pop     rdi
0x18001144a  pop     rsi
0x18001144b  pop     rbp
0x18001144c  pop     rbx
0x18001144d  retn
0x18001144e  mov     rbx, [rbx]
0x180011451  jmp     short loc_1800113D3
0x180011453  lea     r9, aRpcstringbindi_0; "RpcStringBindingCompose failed"
0x18001145a  mov     r8d, eax
0x18001145d  lea     rcx, [rsp+408h+pExceptionObject]
0x180011462  call    ??$?0$0BP@@OException@@QEAA@W4exceptionType@et@@IAEAY0BP@$$CB_W@Z; OException::OException(et::exceptionType,uint,wchar_t const (&)[31])
0x180011467  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x18001146e  lea     rcx, [rsp+408h+pExceptionObject]; pExceptionObject
0x180011473  call    _CxxThrowException
0x180011479  jmp     short loc_18001147C
0x18001147c  nop
0x18001147d  mov     r8d, edi
0x180011480  lea     rcx, [rsp+408h+pExceptionObject]
0x180011485  call    ??$?0$0CD@@OException@@QEAA@W4exceptionType@et@@IAEAY0CD@$$CB_W@Z; OException::OException(et::exceptionType,uint,wchar_t const (&)[35])
0x18001148a  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x180011491  lea     rcx, [rsp+408h+pExceptionObject]; pExceptionObject
0x180011496  call    _CxxThrowException
```
