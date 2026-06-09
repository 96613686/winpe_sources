# CmsDiagEnumerateContainers

- ea: `0x18000aba0`
- end: `0x18000ad3d`
- name: `CmsDiagEnumerateContainers`
- size: `413`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000a150`

## callees

- `0x18000237c`
- `0x1800066e4`
- `0x18000aba0`
- `0x18000d9e8`
- `0x18000db50`
- `0x18000ee00`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000ac16`
- `RPCRT4!RpcBindingFree` at `0x18000ac99`
- `RPCRT4!RpcBindingFree` at `0x18000ace1`
- `RPCRT4!RpcBindingFree` at `0x18000ad06`
- `RPCRT4!RpcBindingFree` at `0x18000ac16`
- `RPCRT4!RpcBindingFree` at `0x18000ac99`
- `RPCRT4!RpcBindingFree` at `0x18000ace1`
- `RPCRT4!RpcBindingFree` at `0x18000ad06`

## string_xrefs

- `0x18000abed`: `onecore\base\gendrv\silos\clem\client\dll\diagapi.cpp`
- `0x18000ac6a`: `onecore\base\gendrv\silos\clem\client\dll\diagapi.cpp`
- `0x18000ad17`: `onecore\base\gendrv\silos\clem\client\dll\diagapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsDiagEnumerateContainers(void *a1, unsigned int *a2)
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
      (void *)0x2B,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\diagapi.cpp",
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
      (void *)0x30,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\diagapi.cpp",
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
         CmsRpcClt_EnumerateContainers,
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
      (void *)0x38,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\diagapi.cpp",
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
0x18000aba0  push    rbp
0x18000aba2  push    rbx
0x18000aba3  push    rsi
0x18000aba4  push    rdi
0x18000aba5  push    r14
0x18000aba7  mov     rbp, rsp
0x18000abaa  sub     rsp, 30h
0x18000abae  mov     rdi, rdx
0x18000abb1  mov     r14, rcx
0x18000abb4  test    rdx, rdx
0x18000abb7  jz      loc_18000AD13
0x18000abbd  cmp     dword ptr [rdx], 0
0x18000abc0  jbe     short loc_18000ABCB
0x18000abc2  test    rcx, rcx
0x18000abc5  jz      loc_18000AD13
0x18000abcb  lea     rdx, [rbp+Binding]
0x18000abcf  mov     [rbp+Binding], 0
0x18000abd7  lea     rcx, qword_180013DC0; IfSpec
0x18000abde  call    ?ConnectToServer@Rpc@Manager@Container@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Container::Manager::Rpc::ConnectToServer(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x18000abe3  mov     ebx, eax
0x18000abe5  test    eax, eax
0x18000abe7  jns     short loc_18000AC21
0x18000abe9  mov     rcx, [rbp+28h]; this
0x18000abed  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000abf4  mov     r9d, eax; char *
0x18000abf7  mov     edx, 30h ; '0'; void *
0x18000abfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ac01  mov     rcx, [rbp+Binding]
0x18000ac05  test    rcx, rcx
0x18000ac08  jz      loc_18000AD30
0x18000ac0e  mov     [rbp+Binding], rcx
0x18000ac12  lea     rcx, [rbp+Binding]; Binding
0x18000ac16  call    cs:__imp_RpcBindingFree
0x18000ac1c  jmp     loc_18000AD30
0x18000ac21  mov     rbx, [rbp+Binding]
0x18000ac25  lea     rax, [rbp+arg_8]
0x18000ac29  mov     [rbp+var_10], rax
0x18000ac2d  lea     r9, [rbp+var_10]
0x18000ac31  lea     rax, [rbp+Src]
0x18000ac35  mov     [rbp+arg_8], 0
0x18000ac3c  lea     r8, [rbp+var_8]
0x18000ac40  mov     [rbp+var_8], rax
0x18000ac44  lea     rdx, [rbp+Binding]
0x18000ac48  mov     [rbp+Src], 0
0x18000ac50  lea     rcx, CmsRpcClt_EnumerateContainers
0x18000ac57  mov     [rbp+Binding], rbx
0x18000ac5b  call    ??$InvokeStubFunction@P6AJPEAX0PEBG@ZPEAXPEAXAEAPEBG@Rpc@Manager@Container@@YAJP6AJPEAX0PEBG@Z$$QEAPEAX3AEAPEBG@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,void *,ushort const *),void *,void *,ushort const * &>(long (*)(void *,void *,ushort const *),void * &&,void * &&,ushort const * &)
0x18000ac60  mov     esi, eax
0x18000ac62  test    eax, eax
0x18000ac64  jns     short loc_18000ACA6
0x18000ac66  mov     rcx, [rbp+28h]; this
0x18000ac6a  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000ac71  mov     r9d, eax; char *
0x18000ac74  mov     edx, 38h ; '8'; void *
0x18000ac79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ac7e  mov     rcx, [rbp+Src]; void *
0x18000ac82  test    rcx, rcx
0x18000ac85  jz      short loc_18000AC8C
0x18000ac87  call    MIDL_user_free
0x18000ac8c  test    rbx, rbx
0x18000ac8f  jz      short loc_18000AC9F
0x18000ac91  lea     rcx, [rbp+Binding]; Binding
0x18000ac95  mov     [rbp+Binding], rbx
0x18000ac99  call    cs:__imp_RpcBindingFree
0x18000ac9f  mov     eax, esi
0x18000aca1  jmp     loc_18000AD32
0x18000aca6  mov     ecx, [rbp+arg_8]
0x18000aca9  mov     eax, [rdi]
0x18000acab  mov     [rdi], ecx
0x18000acad  cmp     eax, ecx
0x18000acaf  jb      short loc_18000ACEB
0x18000acb1  mov     rdi, [rbp+Src]
0x18000acb5  mov     r8d, ecx
0x18000acb8  shl     r8, 4; Size
0x18000acbc  mov     rdx, rdi; Src
0x18000acbf  mov     rcx, r14; void *
0x18000acc2  call    memcpy_0
0x18000acc7  test    rdi, rdi
0x18000acca  jz      short loc_18000ACD4
0x18000accc  mov     rcx, rdi; void *
0x18000accf  call    MIDL_user_free
0x18000acd4  test    rbx, rbx
0x18000acd7  jz      short loc_18000ACE7
0x18000acd9  lea     rcx, [rbp+Binding]; Binding
0x18000acdd  mov     [rbp+Binding], rbx
0x18000ace1  call    cs:__imp_RpcBindingFree
0x18000ace7  xor     eax, eax
0x18000ace9  jmp     short loc_18000AD32
0x18000aceb  mov     rcx, [rbp+Src]; void *
0x18000acef  test    rcx, rcx
0x18000acf2  jz      short loc_18000ACF9
0x18000acf4  call    MIDL_user_free
0x18000acf9  test    rbx, rbx
0x18000acfc  jz      short loc_18000AD0C
0x18000acfe  lea     rcx, [rbp+Binding]; Binding
0x18000ad02  mov     [rbp+Binding], rbx
0x18000ad06  call    cs:__imp_RpcBindingFree
0x18000ad0c  mov     eax, 8007007Ah
0x18000ad11  jmp     short loc_18000AD32
0x18000ad13  mov     rcx, [rbp+28h]; this
0x18000ad17  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000ad1e  mov     ebx, 80070057h
0x18000ad23  mov     edx, 2Bh ; '+'; void *
0x18000ad28  mov     r9d, ebx; char *
0x18000ad2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ad30  mov     eax, ebx
0x18000ad32  add     rsp, 30h
0x18000ad36  pop     r14
0x18000ad38  pop     rdi
0x18000ad39  pop     rsi
0x18000ad3a  pop     rbx
0x18000ad3b  pop     rbp
0x18000ad3c  retn
```
