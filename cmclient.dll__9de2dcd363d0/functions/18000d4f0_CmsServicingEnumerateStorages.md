# CmsServicingEnumerateStorages

- ea: `0x18000d4f0`
- end: `0x18000d68d`
- name: `CmsServicingEnumerateStorages`
- size: `413`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callees

- `0x18000237c`
- `0x1800066e4`
- `0x18000d4f0`
- `0x18000d9e8`
- `0x18000db50`
- `0x18000ee00`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000d566`
- `RPCRT4!RpcBindingFree` at `0x18000d5e9`
- `RPCRT4!RpcBindingFree` at `0x18000d631`
- `RPCRT4!RpcBindingFree` at `0x18000d656`
- `RPCRT4!RpcBindingFree` at `0x18000d566`
- `RPCRT4!RpcBindingFree` at `0x18000d5e9`
- `RPCRT4!RpcBindingFree` at `0x18000d631`
- `RPCRT4!RpcBindingFree` at `0x18000d656`

## string_xrefs

- `0x18000d53d`: `onecore\base\gendrv\silos\clem\client\dll\servicingapi.cpp`
- `0x18000d5ba`: `onecore\base\gendrv\silos\clem\client\dll\servicingapi.cpp`
- `0x18000d667`: `onecore\base\gendrv\silos\clem\client\dll\servicingapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsServicingEnumerateStorages(void *a1, unsigned int *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  RPC_BINDING_HANDLE v6; // rbx
  int v7; // eax
  unsigned int v8; // esi
  unsigned int v10; // ecx
  unsigned int v11; // eax
  void *v12; // rdi
  unsigned int *v13; // [rsp+20h] [rbp-10h] BYREF
  void **p_Src; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  unsigned int v16; // [rsp+68h] [rbp+38h] BYREF
  void *Src; // [rsp+70h] [rbp+40h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+78h] [rbp+48h] BYREF

  if ( !a2 || *a2 && !a1 )
  {
    v5 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\servicingapi.cpp",
      (const char *)0x80070057LL,
      (int)v13);
    return v5;
  }
  Binding = 0;
  v4 = Container::Manager::Rpc::ConnectToServer(qword_180013DC0, &Binding);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\servicingapi.cpp",
      (const char *)(unsigned int)v4,
      (int)v13);
    if ( Binding )
      RpcBindingFree(&Binding);
    return v5;
  }
  v6 = Binding;
  v13 = &v16;
  v16 = 0;
  p_Src = &Src;
  Src = 0;
  v7 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,void *,unsigned short const *),void *,void *,unsigned short const * &>(
         CmsRpcClt_EnumerateContainerStoragesForServicing,
         &Binding,
         &p_Src,
         &v13);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v10 = v16;
    v11 = *a2;
    *a2 = v16;
    if ( v11 < v10 )
    {
      if ( Src )
        MIDL_user_free(Src);
      if ( v6 )
      {
        Binding = v6;
        RpcBindingFree(&Binding);
      }
      return 2147942522LL;
    }
    else
    {
      v12 = Src;
      memcpy_0(a1, Src, 16LL * v10);
      if ( v12 )
        MIDL_user_free(v12);
      if ( v6 )
      {
        Binding = v6;
        RpcBindingFree(&Binding);
      }
      return 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\servicingapi.cpp",
      (const char *)(unsigned int)v7,
      (int)v13);
    if ( Src )
      MIDL_user_free(Src);
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
0x18000d4f0  push    rbp
0x18000d4f2  push    rbx
0x18000d4f3  push    rsi
0x18000d4f4  push    rdi
0x18000d4f5  push    r14
0x18000d4f7  mov     rbp, rsp
0x18000d4fa  sub     rsp, 30h
0x18000d4fe  mov     rdi, rdx
0x18000d501  mov     r14, rcx
0x18000d504  test    rdx, rdx
0x18000d507  jz      loc_18000D663
0x18000d50d  cmp     dword ptr [rdx], 0
0x18000d510  jbe     short loc_18000D51B
0x18000d512  test    rcx, rcx
0x18000d515  jz      loc_18000D663
0x18000d51b  lea     rdx, [rbp+Binding]
0x18000d51f  mov     [rbp+Binding], 0
0x18000d527  lea     rcx, qword_180013DC0; IfSpec
0x18000d52e  call    ?ConnectToServer@Rpc@Manager@Container@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Container::Manager::Rpc::ConnectToServer(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x18000d533  mov     ebx, eax
0x18000d535  test    eax, eax
0x18000d537  jns     short loc_18000D571
0x18000d539  mov     rcx, [rbp+28h]; this
0x18000d53d  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000d544  mov     r9d, eax; char *
0x18000d547  mov     edx, 34h ; '4'; void *
0x18000d54c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d551  mov     rcx, [rbp+Binding]
0x18000d555  test    rcx, rcx
0x18000d558  jz      loc_18000D680
0x18000d55e  mov     [rbp+Binding], rcx
0x18000d562  lea     rcx, [rbp+Binding]; Binding
0x18000d566  call    cs:__imp_RpcBindingFree
0x18000d56c  jmp     loc_18000D680
0x18000d571  mov     rbx, [rbp+Binding]
0x18000d575  lea     rax, [rbp+arg_8]
0x18000d579  mov     [rbp+var_10], rax
0x18000d57d  lea     r9, [rbp+var_10]
0x18000d581  lea     rax, [rbp+Src]
0x18000d585  mov     [rbp+arg_8], 0
0x18000d58c  lea     r8, [rbp+var_8]
0x18000d590  mov     [rbp+var_8], rax
0x18000d594  lea     rdx, [rbp+Binding]
0x18000d598  mov     [rbp+Src], 0
0x18000d5a0  lea     rcx, CmsRpcClt_EnumerateContainerStoragesForServicing
0x18000d5a7  mov     [rbp+Binding], rbx
0x18000d5ab  call    ??$InvokeStubFunction@P6AJPEAX0PEBG@ZPEAXPEAXAEAPEBG@Rpc@Manager@Container@@YAJP6AJPEAX0PEBG@Z$$QEAPEAX3AEAPEBG@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,void *,ushort const *),void *,void *,ushort const * &>(long (*)(void *,void *,ushort const *),void * &&,void * &&,ushort const * &)
0x18000d5b0  mov     esi, eax
0x18000d5b2  test    eax, eax
0x18000d5b4  jns     short loc_18000D5F6
0x18000d5b6  mov     rcx, [rbp+28h]; this
0x18000d5ba  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000d5c1  mov     r9d, eax; char *
0x18000d5c4  mov     edx, 3Dh ; '='; void *
0x18000d5c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d5ce  mov     rcx, [rbp+Src]; void *
0x18000d5d2  test    rcx, rcx
0x18000d5d5  jz      short loc_18000D5DC
0x18000d5d7  call    MIDL_user_free
0x18000d5dc  test    rbx, rbx
0x18000d5df  jz      short loc_18000D5EF
0x18000d5e1  lea     rcx, [rbp+Binding]; Binding
0x18000d5e5  mov     [rbp+Binding], rbx
0x18000d5e9  call    cs:__imp_RpcBindingFree
0x18000d5ef  mov     eax, esi
0x18000d5f1  jmp     loc_18000D682
0x18000d5f6  mov     ecx, [rbp+arg_8]
0x18000d5f9  mov     eax, [rdi]
0x18000d5fb  mov     [rdi], ecx
0x18000d5fd  cmp     eax, ecx
0x18000d5ff  jb      short loc_18000D63B
0x18000d601  mov     rdi, [rbp+Src]
0x18000d605  mov     r8d, ecx
0x18000d608  shl     r8, 4; Size
0x18000d60c  mov     rdx, rdi; Src
0x18000d60f  mov     rcx, r14; void *
0x18000d612  call    memcpy_0
0x18000d617  test    rdi, rdi
0x18000d61a  jz      short loc_18000D624
0x18000d61c  mov     rcx, rdi; void *
0x18000d61f  call    MIDL_user_free
0x18000d624  test    rbx, rbx
0x18000d627  jz      short loc_18000D637
0x18000d629  lea     rcx, [rbp+Binding]; Binding
0x18000d62d  mov     [rbp+Binding], rbx
0x18000d631  call    cs:__imp_RpcBindingFree
0x18000d637  xor     eax, eax
0x18000d639  jmp     short loc_18000D682
0x18000d63b  mov     rcx, [rbp+Src]; void *
0x18000d63f  test    rcx, rcx
0x18000d642  jz      short loc_18000D649
0x18000d644  call    MIDL_user_free
0x18000d649  test    rbx, rbx
0x18000d64c  jz      short loc_18000D65C
0x18000d64e  lea     rcx, [rbp+Binding]; Binding
0x18000d652  mov     [rbp+Binding], rbx
0x18000d656  call    cs:__imp_RpcBindingFree
0x18000d65c  mov     eax, 8007007Ah
0x18000d661  jmp     short loc_18000D682
0x18000d663  mov     rcx, [rbp+28h]; this
0x18000d667  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000d66e  mov     ebx, 80070057h
0x18000d673  mov     edx, 2Dh ; '-'; void *
0x18000d678  mov     r9d, ebx; char *
0x18000d67b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d680  mov     eax, ebx
0x18000d682  add     rsp, 30h
0x18000d686  pop     r14
0x18000d688  pop     rdi
0x18000d689  pop     rsi
0x18000d68a  pop     rbx
0x18000d68b  pop     rbp
0x18000d68c  retn
```
