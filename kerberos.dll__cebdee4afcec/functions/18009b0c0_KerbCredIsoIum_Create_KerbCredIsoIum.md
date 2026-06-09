# KerbCredIsoIum::Create(KerbCredIsoIum * *)

- ea: `0x18009b0c0`
- end: `0x18009b341`
- name: `?Create@KerbCredIsoIum@@SAJPEAPEAV1@@Z`
- size: `641`
- prototype: `__int64 __fastcall(struct KerbCredIsoIum **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18007b808`

## callees

- `0x180001a48`
- `0x1800093f0`
- `0x18008b70c`
- `0x18009ac80`
- `0x18009b0c0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18009b1ff`
- `RPCRT4!NdrClientCall3` at `0x18009b1ff`
- `RPCRT4!RpcStringBindingComposeW` at `0x18009b131`
- `RPCRT4!RpcStringBindingComposeW` at `0x18009b131`
- `RPCRT4!I_RpcMapWin32Status` at `0x18009b169`
- `RPCRT4!I_RpcMapWin32Status` at `0x18009b217`
- `RPCRT4!I_RpcMapWin32Status` at `0x18009b169`
- `RPCRT4!I_RpcMapWin32Status` at `0x18009b217`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18009b186`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18009b186`
- `RPCRT4!RpcStringFreeW` at `0x18009b196`
- `RPCRT4!RpcStringFreeW` at `0x18009b196`
- `RPCRT4!RpcBindingFree` at `0x18009b2dc`
- `RPCRT4!RpcBindingFree` at `0x18009b2dc`

## string_xrefs

- `0x18009b100`: `KerbCredIsoIum::Create`
- `0x18009b13d`: `KerbCredIsoIum::Create`
- `0x18009b19c`: `KerbCredIsoIum::Create`
- `0x18009b227`: `KerbCredIsoIum::Create`
- `0x18009b252`: `KerbCredIsoIum::Create`

## pseudocode

```c
__int64 __fastcall KerbCredIsoIum::Create(struct KerbCredIsoIum **a1)
{
  int v2; // ecx
  int v3; // r8d
  int v4; // r9d
  KerbCredIsoIum *v5; // r15
  int Pointer; // ebx
  RPC_STATUS v7; // ebx
  const char *v8; // r9
  __int64 v9; // r8
  RPC_STATUS v10; // eax
  RPC_WSTR *StringBinding; // [rsp+28h] [rbp-50h]
  struct KerbCredIsoIum **v13; // [rsp+80h] [rbp+8h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+88h] [rbp+10h] BYREF
  RPC_WSTR String; // [rsp+90h] [rbp+18h] BYREF
  void *v16; // [rsp+98h] [rbp+20h] BYREF

  v13 = a1;
  Binding = 0;
  String = 0;
  v16 = 0;
  *a1 = 0;
  v5 = (KerbCredIsoIum *)MIDL_user_allocate(0x10u);
  if ( !v5 )
  {
    Pointer = -1073741801;
    goto LABEL_11;
  }
  v7 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, Endpoint, 0, &String);
  if ( v7 )
  {
    v8 = "%hs: Error creating RPC binding: %d\n";
    v9 = 87;
LABEL_5:
    LODWORD(StringBinding) = v7;
    KerbTracerT::Log(1, "KerbCredIsoIum::Create", v9, v8, "KerbCredIsoIum::Create", StringBinding);
    Pointer = I_RpcMapWin32Status(v7);
    goto LABEL_11;
  }
  v7 = RpcBindingFromStringBindingW(String, &Binding);
  RpcStringFreeW(&String);
  if ( v7 )
  {
    v8 = "%hs: Error binding to RPC server: %d\n";
    v9 = 96;
    goto LABEL_5;
  }
  KerbTracerT::Log(3, "TraceRpcStart", 39, "%hs - Start call to LsaIso\n", "KerbCredIsoIum::Create");
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800F67E8, 0, 0, Binding, &v16).Pointer;
  KerbTracerT::Log(3, "TraceRpcEnd", 44, "%hs - End call to LsaIso\n", "KerbCredIsoIum::Create");
  if ( Pointer >= 0 )
  {
    byte_18014063C = 0;
    *a1 = KerbCredIsoIum::KerbCredIsoIum(v5, v16);
  }
  else
  {
    KerbTracerT::Log(
      1,
      "KerbCredIsoIum::Create",
      109,
      "%hs: Error registering RPC client: %#x\n",
      "KerbCredIsoIum::Create",
      Pointer);
  }
LABEL_11:
  if ( Binding )
  {
    v10 = RpcBindingFree(&Binding);
    if ( v10 )
      KerbTracerT::Log(
        1,
        "KerbCredIsoIum::Create",
        126,
        "%hs: Error freeing RPC binding: %d\n",
        "KerbCredIsoIum::Create",
        v10);
  }
  if ( (unsigned int)dword_180140048 > 5 )
  {
    LODWORD(v13) = Pointer;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v2,
      (unsigned int)byte_18012C229,
      v3,
      v4,
      (__int64)&v13);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x18009b0c0  mov     rax, rsp
0x18009b0c3  mov     [rax+8], rcx
0x18009b0c7  push    rbx
0x18009b0c8  push    rsi
0x18009b0c9  push    rdi
0x18009b0ca  push    r14
0x18009b0cc  push    r15
0x18009b0ce  sub     rsp, 50h
0x18009b0d2  mov     r14, rcx
0x18009b0d5  xor     edi, edi
0x18009b0d7  mov     [rax+10h], rdi
0x18009b0db  mov     [rax+18h], rdi
0x18009b0df  mov     [rax+20h], rdi
0x18009b0e3  mov     [rcx], rdi
0x18009b0e6  lea     ecx, [rdi+10h]; size
0x18009b0e9  call    MIDL_user_allocate
0x18009b0ee  mov     r15, rax
0x18009b0f1  mov     [rsp+78h+var_38], rax
0x18009b0f6  test    rax, rax
0x18009b0f9  jnz     short loc_18009B10C
0x18009b0fb  mov     ebx, 0C0000017h
0x18009b100  lea     rsi, aKerbcredisoium_18; "KerbCredIsoIum::Create"
0x18009b107  jmp     loc_18009B2CA
0x18009b10c  lea     rax, [rsp+78h+String]
0x18009b114  mov     [rsp+78h+StringBinding], rax; StringBinding
0x18009b119  mov     [rsp+78h+Options], rdi; Options
0x18009b11e  lea     r9, Endpoint; "LSA_ISO_RPC_SERVER"
0x18009b125  xor     r8d, r8d; NetworkAddr
0x18009b128  lea     rdx, ProtSeq; "ncalrpc"
0x18009b12f  xor     ecx, ecx; ObjUuid
0x18009b131  call    cs:__imp_RpcStringBindingComposeW
0x18009b137  mov     ebx, eax
0x18009b139  test    eax, eax
0x18009b13b  jz      short loc_18009B176
0x18009b13d  lea     rsi, aKerbcredisoium_18; "KerbCredIsoIum::Create"
0x18009b144  lea     r9, aHsErrorCreatin; "%hs: Error creating RPC binding: %d\n"
0x18009b14b  mov     r8d, 57h ; 'W'
0x18009b151  mov     dword ptr [rsp+78h+StringBinding], ebx
0x18009b155  mov     [rsp+78h+Options], rsi
0x18009b15a  mov     rdx, rsi
0x18009b15d  mov     ecx, 1
0x18009b162  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18009b167  mov     ecx, ebx; Status
0x18009b169  call    cs:__imp_I_RpcMapWin32Status
0x18009b16f  mov     ebx, eax
0x18009b171  jmp     loc_18009B2CA
0x18009b176  lea     rdx, [rsp+78h+Binding]; Binding
0x18009b17e  mov     rcx, [rsp+78h+String]; StringBinding
0x18009b186  call    cs:__imp_RpcBindingFromStringBindingW
0x18009b18c  mov     ebx, eax
0x18009b18e  lea     rcx, [rsp+78h+String]; String
0x18009b196  call    cs:__imp_RpcStringFreeW
0x18009b19c  lea     rsi, aKerbcredisoium_18; "KerbCredIsoIum::Create"
0x18009b1a3  test    ebx, ebx
0x18009b1a5  jz      short loc_18009B1B6
0x18009b1a7  lea     r9, aHsErrorBinding; "%hs: Error binding to RPC server: %d\n"
0x18009b1ae  mov     r8d, 60h ; '`'
0x18009b1b4  jmp     short loc_18009B151
0x18009b1b6  mov     [rsp+78h+Options], rsi
0x18009b1bb  lea     r9, aHsStartCallToL; "%hs - Start call to LsaIso\n"
0x18009b1c2  mov     r8d, 27h ; '''
0x18009b1c8  lea     rdx, aTracerpcstart; "TraceRpcStart"
0x18009b1cf  lea     ecx, [r8-24h]
0x18009b1d3  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18009b1d8  nop
0x18009b1d9  mov     [rsp+78h+var_40], rdi
0x18009b1de  lea     rax, [rsp+78h+arg_18]
0x18009b1e6  mov     [rsp+78h+Options], rax
0x18009b1eb  mov     r9, [rsp+78h+Binding]
0x18009b1f3  xor     r8d, r8d; pReturnValue
0x18009b1f6  xor     edx, edx; nProcNum
0x18009b1f8  lea     rcx, stru_1800F67E8; pProxyInfo
0x18009b1ff  call    cs:__imp_NdrClientCall3
0x18009b205  mov     rbx, rax
0x18009b208  mov     [rsp+78h+var_40], rax
0x18009b20d  mov     [rsp+78h+var_48], eax
0x18009b211  jmp     short loc_18009B266
0x18009b213  mov     edi, eax
0x18009b215  mov     ecx, eax; Status
0x18009b217  call    cs:__imp_I_RpcMapWin32Status
0x18009b21d  mov     ebx, eax
0x18009b21f  mov     [rsp+78h+var_48], eax
0x18009b223  mov     dword ptr [rsp+78h+StringBinding], edi
0x18009b227  lea     rax, aKerbcredisoium_18; "KerbCredIsoIum::Create"
0x18009b22e  mov     [rsp+78h+Options], rax
0x18009b233  lea     r9, aHsRpcErrorD; "%hs: RPC Error: %d"
0x18009b23a  mov     r8d, 22h ; '"'
0x18009b240  lea     rdx, aLogrpcerror; "LogRpcError"
0x18009b247  lea     ecx, [r8-21h]
0x18009b24b  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18009b250  xor     edi, edi
0x18009b252  lea     rsi, aKerbcredisoium_18; "KerbCredIsoIum::Create"
0x18009b259  mov     r14, [rsp+78h+arg_0]
0x18009b261  mov     r15, [rsp+78h+var_38]
0x18009b266  mov     [rsp+78h+Options], rsi
0x18009b26b  lea     r9, aHsEndCallToLsa; "%hs - End call to LsaIso\n"
0x18009b272  mov     r8d, 2Ch ; ','
0x18009b278  lea     rdx, aTracerpcend; "TraceRpcEnd"
0x18009b27f  lea     ecx, [r8-29h]
0x18009b283  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18009b288  test    ebx, ebx
0x18009b28a  jns     short loc_18009B2B0
0x18009b28c  mov     dword ptr [rsp+78h+StringBinding], ebx
0x18009b290  mov     [rsp+78h+Options], rsi
0x18009b295  lea     r9, aHsErrorRegiste; "%hs: Error registering RPC client: %#x"...
0x18009b29c  mov     r8d, 6Dh ; 'm'
0x18009b2a2  mov     rdx, rsi
0x18009b2a5  lea     ecx, [r8-6Ch]
0x18009b2a9  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18009b2ae  jmp     short loc_18009B2CA
0x18009b2b0  mov     cs:byte_18014063C, dil
0x18009b2b7  mov     rdx, [rsp+78h+arg_18]; void *
0x18009b2bf  mov     rcx, r15; this
0x18009b2c2  call    ??0KerbCredIsoIum@@AEAA@PEAX@Z; KerbCredIsoIum::KerbCredIsoIum(void *)
0x18009b2c7  mov     [r14], rax
0x18009b2ca  cmp     [rsp+78h+Binding], rdi
0x18009b2d2  jz      short loc_18009B308
0x18009b2d4  lea     rcx, [rsp+78h+Binding]; Binding
0x18009b2dc  call    cs:__imp_RpcBindingFree
0x18009b2e2  test    eax, eax
0x18009b2e4  jz      short loc_18009B308
0x18009b2e6  mov     dword ptr [rsp+78h+StringBinding], eax
0x18009b2ea  mov     [rsp+78h+Options], rsi
0x18009b2ef  lea     r9, aHsErrorFreeing; "%hs: Error freeing RPC binding: %d\n"
0x18009b2f6  mov     r8d, 7Eh ; '~'
0x18009b2fc  mov     rdx, rsi
0x18009b2ff  lea     ecx, [r8-7Dh]
0x18009b303  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18009b308  mov     eax, cs:dword_180140048
0x18009b30e  cmp     eax, 5
0x18009b311  jbe     short loc_18009B333
0x18009b313  mov     dword ptr [rsp+78h+arg_0], ebx
0x18009b31a  lea     rax, [rsp+78h+arg_0]
0x18009b322  mov     [rsp+78h+Options], rax
0x18009b327  lea     rdx, byte_18012C229
0x18009b32e  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18009b333  mov     eax, ebx
0x18009b335  add     rsp, 50h
0x18009b339  pop     r15
0x18009b33b  pop     r14
0x18009b33d  pop     rdi
0x18009b33e  pop     rsi
0x18009b33f  pop     rbx
0x18009b340  retn
0x1800f2349  push    rbp
0x1800f234b  sub     rsp, 30h
0x1800f234f  mov     rbp, rdx
0x1800f2352  mov     rcx, [rcx]
0x1800f2355  mov     ecx, [rcx]; ExceptionCode
0x1800f2357  call    cs:__imp_RpcExceptionFilter
0x1800f235d  nop
0x1800f235e  add     rsp, 30h
0x1800f2362  pop     rbp
0x1800f2363  retn
```
