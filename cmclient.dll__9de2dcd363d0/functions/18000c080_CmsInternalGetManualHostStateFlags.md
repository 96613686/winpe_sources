# CmsInternalGetManualHostStateFlags

- ea: `0x18000c080`
- end: `0x18000c157`
- name: `CmsInternalGetManualHostStateFlags`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0x1800066e4`
- `0x18000b788`
- `0x18000c080`
- `0x18000d9e8`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000c0de`
- `RPCRT4!RpcBindingFree` at `0x18000c128`
- `RPCRT4!RpcBindingFree` at `0x18000c13f`
- `RPCRT4!RpcBindingFree` at `0x18000c0de`
- `RPCRT4!RpcBindingFree` at `0x18000c128`
- `RPCRT4!RpcBindingFree` at `0x18000c13f`

## string_xrefs

- `0x18000c0b9`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`
- `0x18000c107`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsInternalGetManualHostStateFlags(__int64 a1)
{
  int v1; // eax
  __int64 v2; // rcx
  unsigned int v3; // ebx
  RPC_BINDING_HANDLE v5; // rbx
  int v6; // eax
  unsigned int v7; // edi
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+8h]
  __int64 v10; // [rsp+30h] [rbp+10h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+38h] [rbp+18h] BYREF

  v10 = a1;
  Binding = 0;
  v1 = Container::Manager::Rpc::ConnectToServer(qword_180013DC0, &Binding);
  v3 = v1;
  if ( v1 >= 0 )
  {
    v5 = Binding;
    v6 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_MANUAL_HOST_STATE_FLAGS *),void *,enum _CMS_MANUAL_HOST_STATE_FLAGS * &>(
           v2,
           &Binding,
           &v10);
    v7 = v6;
    if ( v6 >= 0 )
    {
      if ( v5 )
      {
        Binding = v5;
        RpcBindingFree(&Binding);
      }
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEF,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
        (const char *)(unsigned int)v6,
        savedregs);
      if ( v5 )
      {
        Binding = v5;
        RpcBindingFree(&Binding);
      }
      return v7;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEA,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
      (const char *)(unsigned int)v1,
      savedregs);
    if ( Binding )
      RpcBindingFree(&Binding);
    return v3;
  }
}

```

## disassembly

```asm
0x18000c080  mov     [rsp-8+arg_10], rbx
0x18000c085  mov     [rsp-8+arg_18], rdi
0x18000c08a  mov     [rsp-8+arg_0], rcx
0x18000c08f  push    rbp; int
0x18000c090  mov     rbp, rsp
0x18000c093  sub     rsp, 20h
0x18000c097  lea     rdx, [rbp+Binding]
0x18000c09b  mov     [rbp+Binding], 0
0x18000c0a3  lea     rcx, qword_180013DC0; IfSpec
0x18000c0aa  call    ?ConnectToServer@Rpc@Manager@Container@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Container::Manager::Rpc::ConnectToServer(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x18000c0af  mov     ebx, eax
0x18000c0b1  test    eax, eax
0x18000c0b3  jns     short loc_18000C0E8
0x18000c0b5  mov     rcx, [rbp+8]; this
0x18000c0b9  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000c0c0  mov     r9d, eax; char *
0x18000c0c3  mov     edx, 0EAh; void *
0x18000c0c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c0cd  mov     rcx, [rbp+Binding]
0x18000c0d1  test    rcx, rcx
0x18000c0d4  jz      short loc_18000C0E4
0x18000c0d6  mov     [rbp+Binding], rcx
0x18000c0da  lea     rcx, [rbp+Binding]; Binding
0x18000c0de  call    cs:__imp_RpcBindingFree
0x18000c0e4  mov     eax, ebx
0x18000c0e6  jmp     short loc_18000C147
0x18000c0e8  mov     rbx, [rbp+Binding]
0x18000c0ec  lea     r8, [rbp+arg_0]
0x18000c0f0  lea     rdx, [rbp+Binding]
0x18000c0f4  mov     [rbp+Binding], rbx
0x18000c0f8  call    ??$InvokeStubFunction@P6AJPEAXPEAW4_CMS_MANUAL_HOST_STATE_FLAGS@@@ZPEAXAEAPEAW41@@Rpc@Manager@Container@@YAJP6AJPEAXPEAW4_CMS_MANUAL_HOST_STATE_FLAGS@@@Z$$QEAPEAXAEAPEAW43@@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_MANUAL_HOST_STATE_FLAGS *),void *,_CMS_MANUAL_HOST_STATE_FLAGS * &>(long (*)(void *,_CMS_MANUAL_HOST_STATE_FLAGS *),void * &&,_CMS_MANUAL_HOST_STATE_FLAGS * &)
0x18000c0fd  mov     edi, eax
0x18000c0ff  test    eax, eax
0x18000c101  jns     short loc_18000C132
0x18000c103  mov     rcx, [rbp+8]; this
0x18000c107  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000c10e  mov     r9d, eax; char *
0x18000c111  mov     edx, 0EFh; void *
0x18000c116  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c11b  test    rbx, rbx
0x18000c11e  jz      short loc_18000C12E
0x18000c120  lea     rcx, [rbp+Binding]; Binding
0x18000c124  mov     [rbp+Binding], rbx
0x18000c128  call    cs:__imp_RpcBindingFree
0x18000c12e  mov     eax, edi
0x18000c130  jmp     short loc_18000C147
0x18000c132  test    rbx, rbx
0x18000c135  jz      short loc_18000C145
0x18000c137  lea     rcx, [rbp+Binding]; Binding
0x18000c13b  mov     [rbp+Binding], rbx
0x18000c13f  call    cs:__imp_RpcBindingFree
0x18000c145  xor     eax, eax
0x18000c147  mov     rbx, [rsp+20h+arg_10]
0x18000c14c  mov     rdi, [rsp+20h+arg_18]
0x18000c151  add     rsp, 20h
0x18000c155  pop     rbp
0x18000c156  retn
```
