# CmsOpenStorage

- ea: `0x180008c90`
- end: `0x180008e26`
- name: `CmsOpenStorage`
- size: `406`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callees

- `0x180001574`
- `0x180001944`
- `0x180002a18`
- `0x1800066e4`
- `0x180008c90`
- `0x18000d9e8`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180008d3a`
- `RPCRT4!RpcBindingFree` at `0x180008da6`
- `RPCRT4!RpcBindingFree` at `0x180008ddd`
- `RPCRT4!RpcBindingFree` at `0x180008d3a`
- `RPCRT4!RpcBindingFree` at `0x180008da6`
- `RPCRT4!RpcBindingFree` at `0x180008ddd`

## string_xrefs

- `0x180008d15`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`
- `0x180008d85`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`
- `0x180008e01`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsOpenStorage(_OWORD *a1, int a2, _QWORD *a3)
{
  char *v5; // rax
  _QWORD *v6; // rdi
  int v7; // eax
  unsigned int v8; // ebx
  RPC_BINDING_HANDLE v9; // rbx
  int v10; // eax
  unsigned int v11; // esi
  __int64 v13; // rdx
  int v14; // [rsp+20h] [rbp-20h]
  int v15; // [rsp+20h] [rbp-20h]
  __int64 v16; // [rsp+30h] [rbp-10h] BYREF
  int v17[2]; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  _OWORD *v19; // [rsp+70h] [rbp+30h] BYREF
  int v20; // [rsp+78h] [rbp+38h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+88h] [rbp+48h] BYREF

  v20 = a2;
  v19 = a1;
  if ( !a2 || a2 >= 33 )
  {
    v8 = -2147024809;
    v13 = 1358;
    goto LABEL_17;
  }
  v5 = (char *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( !v5 )
  {
    v8 = -2147024882;
    v13 = 1363;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)v8,
      v14);
    return v8;
  }
  *(_QWORD *)v5 = 0;
  Binding = 0;
  *(GUID *)(v5 + 8) = GUID_NULL;
  v7 = Container::Manager::Rpc::ConnectToServer(qword_180012D10, &Binding);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x557,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)(unsigned int)v7,
      v14);
    if ( Binding )
      RpcBindingFree(&Binding);
LABEL_11:
    operator delete(v6, (const struct std::nothrow_t *)0x18);
    return v8;
  }
  v9 = Binding;
  *(_QWORD *)v17 = &v16;
  v16 = 0;
  v10 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID *,enum _CMS_CLIENT_ID,void * *),void *,_GUID * &,enum _CMS_CLIENT_ID &,void * *>(
          (unsigned int)CmsRpcClt_OpenStorage,
          (unsigned int)&Binding,
          (unsigned int)&v19,
          (unsigned int)&v20,
          (__int64)v17);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x562,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)(unsigned int)v10,
      v15);
    if ( v9 )
    {
      Binding = v9;
      RpcBindingFree(&Binding);
    }
    v8 = v11;
    goto LABEL_11;
  }
  *v6 = v16;
  *(_OWORD *)(v6 + 1) = *a1;
  *a3 = v6;
  if ( v9 )
  {
    Binding = v9;
    RpcBindingFree(&Binding);
  }
  return 0;
}

```

## disassembly

```asm
0x180008c90  mov     [rsp-28h+arg_10], rbx
0x180008c95  mov     [rsp-28h+arg_8], edx
0x180008c99  mov     [rsp-28h+arg_0], rcx
0x180008c9e  push    rbp
0x180008c9f  push    rsi
0x180008ca0  push    rdi
0x180008ca1  push    r14
0x180008ca3  push    r15
0x180008ca5  mov     rbp, rsp
0x180008ca8  sub     rsp, 40h
0x180008cac  mov     r15, r8
0x180008caf  mov     r14, rcx
0x180008cb2  test    edx, edx
0x180008cb4  jz      loc_180008DF3
0x180008cba  cmp     edx, 21h ; '!'
0x180008cbd  jge     loc_180008DF3
0x180008cc3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008cca  mov     ecx, 18h; unsigned __int64
0x180008ccf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008cd4  mov     rdi, rax
0x180008cd7  test    rax, rax
0x180008cda  jz      loc_180008DE7
0x180008ce0  mov     qword ptr [rax], 0
0x180008ce7  lea     rdx, [rbp+Binding]
0x180008ceb  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180008cf2  lea     rcx, qword_180012D10; IfSpec
0x180008cf9  mov     [rbp+Binding], 0
0x180008d01  movdqu  xmmword ptr [rax+8], xmm0
0x180008d06  call    ?ConnectToServer@Rpc@Manager@Container@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Container::Manager::Rpc::ConnectToServer(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x180008d0b  mov     ebx, eax
0x180008d0d  test    eax, eax
0x180008d0f  jns     short loc_180008D42
0x180008d11  mov     rcx, [rbp+28h]; this
0x180008d15  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180008d1c  mov     r9d, eax; char *
0x180008d1f  mov     edx, 557h; void *
0x180008d24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d29  mov     rcx, [rbp+Binding]
0x180008d2d  test    rcx, rcx
0x180008d30  jz      short loc_180008DAE
0x180008d32  mov     [rbp+Binding], rcx
0x180008d36  lea     rcx, [rbp+Binding]; Binding
0x180008d3a  call    cs:__imp_RpcBindingFree
0x180008d40  jmp     short loc_180008DAE
0x180008d42  mov     rbx, [rbp+Binding]
0x180008d46  lea     rax, [rbp+var_10]
0x180008d4a  mov     qword ptr [rbp+var_8], rax
0x180008d4e  lea     r9, [rbp+arg_8]
0x180008d52  lea     rax, [rbp+var_8]
0x180008d56  mov     [rbp+var_10], 0
0x180008d5e  lea     r8, [rbp+arg_0]
0x180008d62  mov     qword ptr [rsp+40h+var_20], rax; int
0x180008d67  lea     rdx, [rbp+Binding]
0x180008d6b  mov     [rbp+Binding], rbx
0x180008d6f  lea     rcx, CmsRpcClt_OpenStorage
0x180008d76  call    ??$InvokeStubFunction@P6AJPEAXPEAU_GUID@@W4_CMS_CLIENT_ID@@PEAPEAX@ZPEAXAEAPEAU1@AEAW42@PEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_GUID@@W4_CMS_CLIENT_ID@@PEAPEAX@Z$$QEAPEAXAEAPEAU3@AEAW44@$$QEAPEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID *,_CMS_CLIENT_ID,void * *),void *,_GUID * &,_CMS_CLIENT_ID &,void * *>(long (*)(void *,_GUID *,_CMS_CLIENT_ID,void * *),void * &&,_GUID * &,_CMS_CLIENT_ID &,void * * &&)
0x180008d7b  mov     esi, eax
0x180008d7d  test    eax, eax
0x180008d7f  jns     short loc_180008DBD
0x180008d81  mov     rcx, [rbp+28h]; this
0x180008d85  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180008d8c  mov     r9d, eax; char *
0x180008d8f  mov     edx, 562h; void *
0x180008d94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d99  test    rbx, rbx
0x180008d9c  jz      short loc_180008DAC
0x180008d9e  lea     rcx, [rbp+Binding]; Binding
0x180008da2  mov     [rbp+Binding], rbx
0x180008da6  call    cs:__imp_RpcBindingFree
0x180008dac  mov     ebx, esi
0x180008dae  mov     edx, 18h; struct std::nothrow_t *
0x180008db3  mov     rcx, rdi; void *
0x180008db6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008dbb  jmp     short loc_180008E10
0x180008dbd  mov     rax, [rbp+var_10]
0x180008dc1  mov     [rdi], rax
0x180008dc4  movups  xmm0, xmmword ptr [r14]
0x180008dc8  movdqu  xmmword ptr [rdi+8], xmm0
0x180008dcd  mov     [r15], rdi
0x180008dd0  test    rbx, rbx
0x180008dd3  jz      short loc_180008DE3
0x180008dd5  lea     rcx, [rbp+Binding]; Binding
0x180008dd9  mov     [rbp+Binding], rbx
0x180008ddd  call    cs:__imp_RpcBindingFree
0x180008de3  xor     eax, eax
0x180008de5  jmp     short loc_180008E12
0x180008de7  mov     ebx, 8007000Eh
0x180008dec  mov     edx, 553h
0x180008df1  jmp     short loc_180008DFD
0x180008df3  mov     ebx, 80070057h
0x180008df8  mov     edx, 54Eh; void *
0x180008dfd  mov     rcx, [rbp+28h]; this
0x180008e01  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180008e08  mov     r9d, ebx; char *
0x180008e0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e10  mov     eax, ebx
0x180008e12  mov     rbx, [rsp+40h+arg_10]
0x180008e1a  add     rsp, 40h
0x180008e1e  pop     r15
0x180008e20  pop     r14
0x180008e22  pop     rdi
0x180008e23  pop     rsi
0x180008e24  pop     rbp
0x180008e25  retn
```
