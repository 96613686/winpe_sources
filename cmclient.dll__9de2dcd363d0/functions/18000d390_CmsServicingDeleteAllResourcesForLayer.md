# CmsServicingDeleteAllResourcesForLayer

- ea: `0x18000d390`
- end: `0x18000d495`
- name: `CmsServicingDeleteAllResourcesForLayer`
- size: `261`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0x18000230c`
- `0x1800066e4`
- `0x18000d390`
- `0x18000d9e8`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000d417`
- `RPCRT4!RpcBindingFree` at `0x18000d466`
- `RPCRT4!RpcBindingFree` at `0x18000d47d`
- `RPCRT4!RpcBindingFree` at `0x18000d417`
- `RPCRT4!RpcBindingFree` at `0x18000d466`
- `RPCRT4!RpcBindingFree` at `0x18000d47d`

## string_xrefs

- `0x18000d3b0`: `onecore\base\gendrv\silos\clem\client\dll\servicingapi.cpp`
- `0x18000d3f2`: `onecore\base\gendrv\silos\clem\client\dll\servicingapi.cpp`
- `0x18000d445`: `onecore\base\gendrv\silos\clem\client\dll\servicingapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsServicingDeleteAllResourcesForLayer(void *a1)
{
  unsigned int v1; // ebx
  int v3; // eax
  RPC_BINDING_HANDLE v4; // rbx
  int v5; // eax
  unsigned int v6; // edi
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+8h]
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp+10h] BYREF
  RPC_BINDING_HANDLE v10; // [rsp+38h] [rbp+18h] BYREF

  Binding = a1;
  if ( !a1 )
  {
    v1 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AA,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\servicingapi.cpp",
      (const char *)0x80070057LL,
      savedregs);
    return v1;
  }
  v10 = 0;
  v3 = Container::Manager::Rpc::ConnectToServer(qword_180012D10, &v10);
  v1 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AE,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\servicingapi.cpp",
      (const char *)(unsigned int)v3,
      savedregs);
    if ( v10 )
    {
      Binding = v10;
      RpcBindingFree(&Binding);
    }
    return v1;
  }
  v4 = v10;
  v5 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(
         CmsRpcClt_DeleteAllResourcesForLayer,
         &v10,
         &Binding);
  v6 = v5;
  if ( v5 >= 0 )
  {
    if ( v4 )
    {
      Binding = v4;
      RpcBindingFree(&Binding);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B4,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\servicingapi.cpp",
      (const char *)(unsigned int)v5,
      savedregs);
    if ( v4 )
    {
      Binding = v4;
      RpcBindingFree(&Binding);
    }
    return v6;
  }
}

```

## disassembly

```asm
0x18000d390  mov     [rsp-8+arg_10], rbx
0x18000d395  mov     [rsp-8+arg_18], rdi
0x18000d39a  mov     [rsp-8+Binding], rcx
0x18000d39f  push    rbp; int
0x18000d3a0  mov     rbp, rsp
0x18000d3a3  sub     rsp, 20h
0x18000d3a7  test    rcx, rcx
0x18000d3aa  jnz     short loc_18000D3D0
0x18000d3ac  mov     rcx, [rbp+8]; this
0x18000d3b0  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000d3b7  mov     ebx, 80070057h
0x18000d3bc  mov     edx, 1AAh; void *
0x18000d3c1  mov     r9d, ebx; char *
0x18000d3c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d3c9  mov     eax, ebx
0x18000d3cb  jmp     loc_18000D485
0x18000d3d0  lea     rdx, [rbp+arg_8]
0x18000d3d4  mov     [rbp+arg_8], 0
0x18000d3dc  lea     rcx, qword_180012D10; IfSpec
0x18000d3e3  call    ?ConnectToServer@Rpc@Manager@Container@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Container::Manager::Rpc::ConnectToServer(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x18000d3e8  mov     ebx, eax
0x18000d3ea  test    eax, eax
0x18000d3ec  jns     short loc_18000D41F
0x18000d3ee  mov     rcx, [rbp+8]; this
0x18000d3f2  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000d3f9  mov     r9d, eax; char *
0x18000d3fc  mov     edx, 1AEh; void *
0x18000d401  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d406  mov     rcx, [rbp+arg_8]
0x18000d40a  test    rcx, rcx
0x18000d40d  jz      short loc_18000D3C9
0x18000d40f  mov     [rbp+Binding], rcx
0x18000d413  lea     rcx, [rbp+Binding]; Binding
0x18000d417  call    cs:__imp_RpcBindingFree
0x18000d41d  jmp     short loc_18000D3C9
0x18000d41f  mov     rbx, [rbp+arg_8]
0x18000d423  lea     r8, [rbp+Binding]
0x18000d427  lea     rdx, [rbp+arg_8]
0x18000d42b  mov     [rbp+arg_8], rbx
0x18000d42f  lea     rcx, CmsRpcClt_DeleteAllResourcesForLayer
0x18000d436  call    ??$InvokeStubFunction@P6AJPEAXPEAH@ZPEAXAEAPEAH@Rpc@Manager@Container@@YAJP6AJPEAXPEAH@Z$$QEAPEAXAEAPEAH@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(long (*)(void *,int *),void * &&,int * &)
0x18000d43b  mov     edi, eax
0x18000d43d  test    eax, eax
0x18000d43f  jns     short loc_18000D470
0x18000d441  mov     rcx, [rbp+8]; this
0x18000d445  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000d44c  mov     r9d, eax; char *
0x18000d44f  mov     edx, 1B4h; void *
0x18000d454  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d459  test    rbx, rbx
0x18000d45c  jz      short loc_18000D46C
0x18000d45e  lea     rcx, [rbp+Binding]; Binding
0x18000d462  mov     [rbp+Binding], rbx
0x18000d466  call    cs:__imp_RpcBindingFree
0x18000d46c  mov     eax, edi
0x18000d46e  jmp     short loc_18000D485
0x18000d470  test    rbx, rbx
0x18000d473  jz      short loc_18000D483
0x18000d475  lea     rcx, [rbp+Binding]; Binding
0x18000d479  mov     [rbp+Binding], rbx
0x18000d47d  call    cs:__imp_RpcBindingFree
0x18000d483  xor     eax, eax
0x18000d485  mov     rbx, [rsp+20h+arg_10]
0x18000d48a  mov     rdi, [rsp+20h+arg_18]
0x18000d48f  add     rsp, 20h
0x18000d493  pop     rbp
0x18000d494  retn
```
