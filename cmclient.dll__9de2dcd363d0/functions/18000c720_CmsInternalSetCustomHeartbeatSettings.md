# CmsInternalSetCustomHeartbeatSettings

- ea: `0x18000c720`
- end: `0x18000c83b`
- name: `CmsInternalSetCustomHeartbeatSettings`
- size: `283`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x1800066e4`
- `0x18000b4fc`
- `0x18000c720`
- `0x18000d9e8`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000c79b`
- `RPCRT4!RpcBindingFree` at `0x18000c7f3`
- `RPCRT4!RpcBindingFree` at `0x18000c80a`
- `RPCRT4!RpcBindingFree` at `0x18000c79b`
- `RPCRT4!RpcBindingFree` at `0x18000c7f3`
- `RPCRT4!RpcBindingFree` at `0x18000c80a`

## string_xrefs

- `0x18000c772`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`
- `0x18000c7d2`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`
- `0x18000c818`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsInternalSetCustomHeartbeatSettings(int a1, int a2, int a3)
{
  int v3; // eax
  __int64 v4; // rcx
  unsigned int v5; // ebx
  RPC_BINDING_HANDLE v6; // rbx
  int v7; // eax
  unsigned int v8; // edi
  int v10; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  int v12; // [rsp+50h] [rbp+20h] BYREF
  int v13; // [rsp+58h] [rbp+28h] BYREF
  int v14; // [rsp+60h] [rbp+30h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+68h] [rbp+38h] BYREF

  v14 = a3;
  v13 = a2;
  v12 = a1;
  if ( !a1 || !a2 || !a3 )
  {
    v5 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x102,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
      (const char *)0x80070057LL,
      v10);
    return v5;
  }
  Binding = 0;
  v3 = Container::Manager::Rpc::ConnectToServer(qword_180013DC0, &Binding);
  v5 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x107,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
      (const char *)(unsigned int)v3,
      v10);
    if ( Binding )
      RpcBindingFree(&Binding);
    return v5;
  }
  v6 = Binding;
  v7 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,unsigned long,unsigned long,unsigned long),void *,unsigned long &,unsigned long &,unsigned long &>(
         v4,
         &Binding,
         &v12,
         &v13);
  v8 = v7;
  if ( v7 >= 0 )
  {
    if ( v6 )
    {
      Binding = v6;
      RpcBindingFree(&Binding);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10E,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
      (const char *)(unsigned int)v7,
      (int)&v14);
    if ( v6 )
    {
      Binding = v6;
      RpcBindingFree(&Binding);
    }
    return v8;
  }
}

```

## disassembly

```asm
0x18000c720  mov     [rsp-18h+arg_10], r8d
0x18000c725  mov     [rsp-18h+arg_8], edx
0x18000c729  mov     [rsp-18h+arg_0], ecx
0x18000c72d  push    rbp
0x18000c72e  push    rbx
0x18000c72f  push    rdi
0x18000c730  mov     rbp, rsp
0x18000c733  sub     rsp, 30h
0x18000c737  test    ecx, ecx
0x18000c739  jz      loc_18000C814
0x18000c73f  test    edx, edx
0x18000c741  jz      loc_18000C814
0x18000c747  test    r8d, r8d
0x18000c74a  jz      loc_18000C814
0x18000c750  lea     rdx, [rbp+Binding]
0x18000c754  mov     [rbp+Binding], 0
0x18000c75c  lea     rcx, qword_180013DC0; IfSpec
0x18000c763  call    ?ConnectToServer@Rpc@Manager@Container@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Container::Manager::Rpc::ConnectToServer(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x18000c768  mov     ebx, eax
0x18000c76a  test    eax, eax
0x18000c76c  jns     short loc_18000C7A6
0x18000c76e  mov     rcx, [rbp+18h]; this
0x18000c772  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000c779  mov     r9d, eax; char *
0x18000c77c  mov     edx, 107h; void *
0x18000c781  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c786  mov     rcx, [rbp+Binding]
0x18000c78a  test    rcx, rcx
0x18000c78d  jz      loc_18000C831
0x18000c793  mov     [rbp+Binding], rcx
0x18000c797  lea     rcx, [rbp+Binding]; Binding
0x18000c79b  call    cs:__imp_RpcBindingFree
0x18000c7a1  jmp     loc_18000C831
0x18000c7a6  mov     rbx, [rbp+Binding]
0x18000c7aa  lea     rax, [rbp+arg_10]
0x18000c7ae  lea     r9, [rbp+arg_8]
0x18000c7b2  mov     [rbp+Binding], rbx
0x18000c7b6  lea     r8, [rbp+arg_0]
0x18000c7ba  mov     qword ptr [rsp+30h+var_10], rax; int
0x18000c7bf  lea     rdx, [rbp+Binding]
0x18000c7c3  call    ??$InvokeStubFunction@P6AJPEAXKKK@ZPEAXAEAKAEAKAEAK@Rpc@Manager@Container@@YAJP6AJPEAXKKK@Z$$QEAPEAXAEAK33@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,ulong,ulong,ulong),void *,ulong &,ulong &,ulong &>(long (*)(void *,ulong,ulong,ulong),void * &&,ulong &,ulong &,ulong &)
0x18000c7c8  mov     edi, eax
0x18000c7ca  test    eax, eax
0x18000c7cc  jns     short loc_18000C7FD
0x18000c7ce  mov     rcx, [rbp+18h]; this
0x18000c7d2  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000c7d9  mov     r9d, eax; char *
0x18000c7dc  mov     edx, 10Eh; void *
0x18000c7e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c7e6  test    rbx, rbx
0x18000c7e9  jz      short loc_18000C7F9
0x18000c7eb  lea     rcx, [rbp+Binding]; Binding
0x18000c7ef  mov     [rbp+Binding], rbx
0x18000c7f3  call    cs:__imp_RpcBindingFree
0x18000c7f9  mov     eax, edi
0x18000c7fb  jmp     short loc_18000C833
0x18000c7fd  test    rbx, rbx
0x18000c800  jz      short loc_18000C810
0x18000c802  lea     rcx, [rbp+Binding]; Binding
0x18000c806  mov     [rbp+Binding], rbx
0x18000c80a  call    cs:__imp_RpcBindingFree
0x18000c810  xor     eax, eax
0x18000c812  jmp     short loc_18000C833
0x18000c814  mov     rcx, [rbp+18h]; this
0x18000c818  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000c81f  mov     ebx, 80070057h
0x18000c824  mov     edx, 102h; void *
0x18000c829  mov     r9d, ebx; char *
0x18000c82c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c831  mov     eax, ebx
0x18000c833  add     rsp, 30h
0x18000c837  pop     rdi
0x18000c838  pop     rbx
0x18000c839  pop     rbp
0x18000c83a  retn
```
