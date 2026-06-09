# CmsServicingOpenTransaction

- ea: `0x18000d6d0`
- end: `0x18000d7d6`
- name: `CmsServicingOpenTransaction`
- size: `262`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0x180002a18`
- `0x1800066e4`
- `0x18000d6d0`
- `0x18000d9e8`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000d732`
- `RPCRT4!RpcBindingFree` at `0x18000d7a3`
- `RPCRT4!RpcBindingFree` at `0x18000d7c1`
- `RPCRT4!RpcBindingFree` at `0x18000d732`
- `RPCRT4!RpcBindingFree` at `0x18000d7a3`
- `RPCRT4!RpcBindingFree` at `0x18000d7c1`

## string_xrefs

- `0x18000d70d`: `onecore\base\gendrv\silos\clem\client\dll\servicingapi.cpp`
- `0x18000d782`: `onecore\base\gendrv\silos\clem\client\dll\servicingapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsServicingOpenTransaction(__int64 a1, int a2, _QWORD *a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  RPC_BINDING_HANDLE v7; // rbx
  int v8; // eax
  unsigned int v9; // edi
  int v10; // [rsp+20h] [rbp-20h]
  int v11; // [rsp+20h] [rbp-20h]
  __int64 v12; // [rsp+30h] [rbp-10h] BYREF
  int v13[2]; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  __int64 v15; // [rsp+60h] [rbp+20h] BYREF
  int v16; // [rsp+68h] [rbp+28h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+78h] [rbp+38h] BYREF

  v16 = a2;
  v15 = a1;
  Binding = 0;
  v4 = Container::Manager::Rpc::ConnectToServer(qword_180012D10, &Binding);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v7 = Binding;
    *(_QWORD *)v13 = &v12;
    v12 = 0;
    v8 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID *,enum _CMS_CLIENT_ID,void * *),void *,_GUID * &,enum _CMS_CLIENT_ID &,void * *>(
           (unsigned int)CmsRpcClt_OpenTransaction,
           (unsigned int)&Binding,
           (unsigned int)&v15,
           (unsigned int)&v16,
           (__int64)v13);
    v9 = v8;
    if ( v8 >= 0 )
    {
      *a3 = v12;
      if ( v7 )
      {
        Binding = v7;
        RpcBindingFree(&Binding);
      }
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x102,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\servicingapi.cpp",
        (const char *)(unsigned int)v8,
        v11);
      if ( v7 )
      {
        Binding = v7;
        RpcBindingFree(&Binding);
      }
      return v9;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF7,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\servicingapi.cpp",
      (const char *)(unsigned int)v4,
      v10);
    if ( Binding )
      RpcBindingFree(&Binding);
    return v5;
  }
}

```

## disassembly

```asm
0x18000d6d0  mov     [rsp-18h+arg_10], rbx
0x18000d6d5  mov     [rsp-18h+arg_8], edx
0x18000d6d9  mov     [rsp-18h+arg_0], rcx
0x18000d6de  push    rbp
0x18000d6df  push    rsi
0x18000d6e0  push    rdi
0x18000d6e1  mov     rbp, rsp
0x18000d6e4  sub     rsp, 40h
0x18000d6e8  lea     rdx, [rbp+Binding]
0x18000d6ec  mov     [rbp+Binding], 0
0x18000d6f4  lea     rcx, qword_180012D10; IfSpec
0x18000d6fb  mov     rsi, r8
0x18000d6fe  call    ?ConnectToServer@Rpc@Manager@Container@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Container::Manager::Rpc::ConnectToServer(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x18000d703  mov     ebx, eax
0x18000d705  test    eax, eax
0x18000d707  jns     short loc_18000D73F
0x18000d709  mov     rcx, [rbp+18h]; this
0x18000d70d  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000d714  mov     r9d, eax; char *
0x18000d717  mov     edx, 0F7h; void *
0x18000d71c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d721  mov     rcx, [rbp+Binding]
0x18000d725  test    rcx, rcx
0x18000d728  jz      short loc_18000D738
0x18000d72a  mov     [rbp+Binding], rcx
0x18000d72e  lea     rcx, [rbp+Binding]; Binding
0x18000d732  call    cs:__imp_RpcBindingFree
0x18000d738  mov     eax, ebx
0x18000d73a  jmp     loc_18000D7C9
0x18000d73f  mov     rbx, [rbp+Binding]
0x18000d743  lea     rax, [rbp+var_10]
0x18000d747  mov     qword ptr [rbp+var_8], rax
0x18000d74b  lea     r9, [rbp+arg_8]
0x18000d74f  lea     rax, [rbp+var_8]
0x18000d753  mov     [rbp+var_10], 0
0x18000d75b  lea     r8, [rbp+arg_0]
0x18000d75f  mov     qword ptr [rsp+40h+var_20], rax; int
0x18000d764  lea     rdx, [rbp+Binding]
0x18000d768  mov     [rbp+Binding], rbx
0x18000d76c  lea     rcx, CmsRpcClt_OpenTransaction
0x18000d773  call    ??$InvokeStubFunction@P6AJPEAXPEAU_GUID@@W4_CMS_CLIENT_ID@@PEAPEAX@ZPEAXAEAPEAU1@AEAW42@PEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_GUID@@W4_CMS_CLIENT_ID@@PEAPEAX@Z$$QEAPEAXAEAPEAU3@AEAW44@$$QEAPEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID *,_CMS_CLIENT_ID,void * *),void *,_GUID * &,_CMS_CLIENT_ID &,void * *>(long (*)(void *,_GUID *,_CMS_CLIENT_ID,void * *),void * &&,_GUID * &,_CMS_CLIENT_ID &,void * * &&)
0x18000d778  mov     edi, eax
0x18000d77a  test    eax, eax
0x18000d77c  jns     short loc_18000D7AD
0x18000d77e  mov     rcx, [rbp+18h]; this
0x18000d782  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000d789  mov     r9d, eax; char *
0x18000d78c  mov     edx, 102h; void *
0x18000d791  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d796  test    rbx, rbx
0x18000d799  jz      short loc_18000D7A9
0x18000d79b  lea     rcx, [rbp+Binding]; Binding
0x18000d79f  mov     [rbp+Binding], rbx
0x18000d7a3  call    cs:__imp_RpcBindingFree
0x18000d7a9  mov     eax, edi
0x18000d7ab  jmp     short loc_18000D7C9
0x18000d7ad  mov     rax, [rbp+var_10]
0x18000d7b1  mov     [rsi], rax
0x18000d7b4  test    rbx, rbx
0x18000d7b7  jz      short loc_18000D7C7
0x18000d7b9  lea     rcx, [rbp+Binding]; Binding
0x18000d7bd  mov     [rbp+Binding], rbx
0x18000d7c1  call    cs:__imp_RpcBindingFree
0x18000d7c7  xor     eax, eax
0x18000d7c9  mov     rbx, [rsp+40h+arg_10]
0x18000d7ce  add     rsp, 40h
0x18000d7d2  pop     rdi
0x18000d7d3  pop     rsi
0x18000d7d4  pop     rbp
0x18000d7d5  retn
```
