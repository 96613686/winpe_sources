# QMInitializeLocalRpcServer(void)

- ea: `0x180044c50`
- end: `0x180044d6c`
- name: `?QMInitializeLocalRpcServer@@YAJXZ`
- size: `284`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180044244`

## callees

- `0x18000e558`
- `0x18002c770`
- `0x180044c50`
- `0x18009a590`
- `0x18009bdf8`

## import_xrefs

- `msvcrt!free` at `0x180044d47`
- `msvcrt!free` at `0x180044d51`
- `msvcrt!free` at `0x180044d47`
- `msvcrt!free` at `0x180044d51`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180044ce6`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180044ce6`
- `mqsec!ComposeRPCEndPointName` at `0x180044ccd`
- `mqsec!ComposeRPCEndPointName` at `0x180044ccd`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 QMInitializeLocalRpcServer(void)
{
  wchar_t *v0; // rbx
  unsigned int v1; // edi
  int v3; // [rsp+30h] [rbp-30h] BYREF
  __int64 v4; // [rsp+38h] [rbp-28h]
  const wchar_t *v5; // [rsp+40h] [rbp-20h]
  int v6; // [rsp+48h] [rbp-18h]
  __int64 v7; // [rsp+50h] [rbp-10h]
  RPC_WSTR Endpoint; // [rsp+70h] [rbp+10h] BYREF
  void *Block; // [rsp+78h] [rbp+18h] BYREF

  Block = 0;
  v3 = 0;
  v4 = 0;
  v5 = L"RpcLocalEp";
  v6 = 0;
  v7 = 0;
  CmQueryValue((const struct RegEntry *)&v3, (wchar_t **)&Block);
  v0 = (wchar_t *)Block;
  if ( !Block )
  {
    v0 = newwcs(L"QMsvc");
    Block = v0;
  }
  Endpoint = 0;
  ComposeRPCEndPointName(v0, 0, &Endpoint);
  v1 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0x4D2u, Endpoint, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0 )
    WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 22), v1);
  if ( v1 )
    LogMsgRPCStatus(v1, (wchar_t *)L"qmrpcsrv", 0xB4u);
  free(Endpoint);
  free(v0);
  return v1;
}

```

## disassembly

```asm
0x180044c50  mov     [rsp-8+arg_10], rbx
0x180044c55  mov     [rsp-8+arg_18], rdi
0x180044c5a  push    rbp
0x180044c5b  mov     rbp, rsp
0x180044c5e  sub     rsp, 60h
0x180044c62  mov     [rbp+Block], 0
0x180044c6a  mov     [rbp+var_30], 0
0x180044c71  mov     [rbp+var_28], 0
0x180044c79  lea     rax, aRpclocalep; "RpcLocalEp"
0x180044c80  mov     [rbp+var_20], rax
0x180044c84  mov     [rbp+var_18], 0
0x180044c8b  mov     [rbp+var_10], 0
0x180044c93  lea     rdx, [rbp+Block]; wchar_t **
0x180044c97  lea     rcx, [rbp+var_30]; struct RegEntry *
0x180044c9b  call    ?CmQueryValue@@YAXAEBVRegEntry@@PEAPEA_W@Z; CmQueryValue(RegEntry const &,wchar_t * *)
0x180044ca0  mov     rbx, [rbp+Block]
0x180044ca4  test    rbx, rbx
0x180044ca7  jnz     short loc_180044CBC
0x180044ca9  lea     rcx, aQmsvc; "QMsvc"
0x180044cb0  call    ?newwcs@@YAPEA_WPEB_W@Z; newwcs(wchar_t const *)
0x180044cb5  mov     rbx, rax
0x180044cb8  mov     [rbp+Block], rax
0x180044cbc  mov     [rbp+Endpoint], 0
0x180044cc4  lea     r8, [rbp+Endpoint]
0x180044cc8  xor     edx, edx
0x180044cca  mov     rcx, rbx
0x180044ccd  call    cs:__imp_?ComposeRPCEndPointName@@YAXPEB_W0PEAPEA_W@Z; ComposeRPCEndPointName(wchar_t const *,wchar_t const *,wchar_t * *)
0x180044cd3  xor     r9d, r9d; SecurityDescriptor
0x180044cd6  mov     r8, [rbp+Endpoint]; Endpoint
0x180044cda  mov     edx, 4D2h; MaxCalls
0x180044cdf  lea     rcx, Protseq; "ncalrpc"
0x180044ce6  call    cs:__imp_RpcServerUseProtseqEpW
0x180044cec  mov     edi, eax
0x180044cee  lea     rax, WPP_GLOBAL_Control
0x180044cf5  mov     rcx, cs:WPP_GLOBAL_Control
0x180044cfc  cmp     rcx, rax
0x180044cff  jz      short loc_180044D2A
0x180044d01  test    byte ptr [rcx+0BCh], 4
0x180044d08  jz      short loc_180044D2A
0x180044d0a  mov     edx, 20h ; ' '
0x180044d0f  mov     dword ptr [rsp+60h+var_40], edi; char
0x180044d13  mov     r9, [rbp+Endpoint]
0x180044d17  lea     r8, WPP_4bde07fad0d03e40b51473b182e56f08_Traceguids
0x180044d1e  mov     rcx, [rcx+0B0h]; LoggerHandle
0x180044d25  call    WPP_SF_Sd
0x180044d2a  test    edi, edi
0x180044d2c  jz      short loc_180044D43
0x180044d2e  mov     r8d, 0B4h; unsigned __int16
0x180044d34  lea     rdx, aQmrpcsrv; "qmrpcsrv"
0x180044d3b  mov     ecx, edi; int
0x180044d3d  call    ?LogMsgRPCStatus@@YAXJPEA_WG@Z; LogMsgRPCStatus(long,wchar_t *,ushort)
0x180044d42  nop
0x180044d43  mov     rcx, [rbp+Endpoint]; Block
0x180044d47  call    cs:__imp_free
0x180044d4d  nop
0x180044d4e  mov     rcx, rbx; Block
0x180044d51  call    cs:__imp_free
0x180044d57  nop
0x180044d58  mov     eax, edi
0x180044d5a  lea     r11, [rsp+60h+var_s0]
0x180044d5f  mov     rbx, [r11+20h]
0x180044d63  mov     rdi, [r11+28h]
0x180044d67  mov     rsp, r11
0x180044d6a  pop     rbp
0x180044d6b  retn
```
