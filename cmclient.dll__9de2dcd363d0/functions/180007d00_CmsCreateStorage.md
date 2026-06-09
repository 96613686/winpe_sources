# CmsCreateStorage

- ea: `0x180007d00`
- end: `0x180007ec7`
- name: `CmsCreateStorage`
- size: `455`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callees

- `0x180001550`
- `0x180001574`
- `0x180001944`
- `0x180002e04`
- `0x1800066e4`
- `0x180007d00`
- `0x18000d9e8`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180007dc4`
- `RPCRT4!RpcBindingFree` at `0x180007e41`
- `RPCRT4!RpcBindingFree` at `0x180007e78`
- `RPCRT4!RpcBindingFree` at `0x180007dc4`
- `RPCRT4!RpcBindingFree` at `0x180007e41`
- `RPCRT4!RpcBindingFree` at `0x180007e78`

## string_xrefs

- `0x180007d9b`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`
- `0x180007e20`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`
- `0x180007e9c`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsCreateStorage(int a1, void *a2, _QWORD *a3)
{
  __int64 v4; // rdx
  char *v5; // rax
  _QWORD *v6; // rdi
  int v7; // eax
  int v8; // ecx
  unsigned int v9; // ebx
  RPC_BINDING_HANDLE v10; // rbx
  int v11; // eax
  unsigned int v12; // esi
  int v14; // [rsp+20h] [rbp-60h]
  int v15; // [rsp+20h] [rbp-60h]
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp-50h] BYREF
  RPC_BINDING_HANDLE v17; // [rsp+38h] [rbp-48h] BYREF
  int v18; // [rsp+40h] [rbp-40h] BYREF
  __int64 v19; // [rsp+48h] [rbp-38h] BYREF
  __int64 *v20; // [rsp+50h] [rbp-30h] BYREF
  int v21[2]; // [rsp+58h] [rbp-28h] BYREF
  __int128 v22; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v18 = a1;
  v17 = a2;
  if ( !a2 )
  {
    v4 = 1313;
LABEL_19:
    v9 = -2147024809;
    goto LABEL_20;
  }
  if ( !a1 || a1 >= 33 )
  {
    v4 = 1314;
    goto LABEL_19;
  }
  v5 = (char *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( !v5 )
  {
    v9 = -2147024882;
    v4 = 1319;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)v9,
      v14);
    return v9;
  }
  *(_QWORD *)v5 = 0;
  Binding = 0;
  *(GUID *)(v5 + 8) = GUID_NULL;
  v7 = Container::Manager::Rpc::ConnectToServer(qword_180012D10, &Binding);
  v9 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52B,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)(unsigned int)v7,
      v14);
    if ( Binding )
      RpcBindingFree(&Binding);
LABEL_13:
    operator delete(v6, (const struct std::nothrow_t *)0x18);
    return v9;
  }
  v10 = Binding;
  v20 = &v19;
  v19 = 0;
  *(_QWORD *)v21 = &v22;
  v22 = 0;
  v11 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_CLIENT_ID,_CMS_STORAGE_PROPERTIES *,_GUID *,void * *),void *,enum _CMS_CLIENT_ID &,_CMS_STORAGE_PROPERTIES * &,_GUID *,void * *>(
          v8,
          (unsigned int)&Binding,
          (unsigned int)&v18,
          (unsigned int)&v17,
          (__int64)v21,
          (__int64)&v20);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x538,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)(unsigned int)v11,
      v15);
    if ( v10 )
    {
      v17 = v10;
      RpcBindingFree(&v17);
    }
    v9 = v12;
    goto LABEL_13;
  }
  *v6 = v19;
  *(_OWORD *)(v6 + 1) = v22;
  *a3 = v6;
  if ( v10 )
  {
    v17 = v10;
    RpcBindingFree(&v17);
  }
  return 0;
}

```

## disassembly

```asm
0x180007d00  push    rbp
0x180007d02  push    rbx
0x180007d03  push    rsi
0x180007d04  push    rdi
0x180007d05  push    r14
0x180007d07  mov     rbp, rsp
0x180007d0a  sub     rsp, 80h
0x180007d11  mov     rax, cs:__security_cookie
0x180007d18  xor     rax, rsp
0x180007d1b  mov     [rbp+var_10], rax
0x180007d1f  mov     [rbp+var_40], ecx
0x180007d22  mov     r14, r8
0x180007d25  mov     [rbp+var_48], rdx
0x180007d29  test    rdx, rdx
0x180007d2c  jnz     short loc_180007D38
0x180007d2e  mov     edx, 521h
0x180007d33  jmp     loc_180007E93
0x180007d38  test    ecx, ecx
0x180007d3a  jz      loc_180007E8E
0x180007d40  cmp     ecx, 21h ; '!'
0x180007d43  jge     loc_180007E8E
0x180007d49  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007d50  mov     ecx, 18h; unsigned __int64
0x180007d55  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007d5a  mov     rdi, rax
0x180007d5d  test    rax, rax
0x180007d60  jz      loc_180007E82
0x180007d66  mov     qword ptr [rax], 0
0x180007d6d  lea     rdx, [rbp+Binding]
0x180007d71  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180007d78  lea     rcx, qword_180012D10; IfSpec
0x180007d7f  mov     [rbp+Binding], 0
0x180007d87  movdqu  xmmword ptr [rax+8], xmm0
0x180007d8c  call    ?ConnectToServer@Rpc@Manager@Container@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Container::Manager::Rpc::ConnectToServer(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x180007d91  mov     ebx, eax
0x180007d93  test    eax, eax
0x180007d95  jns     short loc_180007DCC
0x180007d97  mov     rcx, [rbp+28h]; this
0x180007d9b  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180007da2  mov     r9d, eax; char *
0x180007da5  mov     edx, 52Bh; void *
0x180007daa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007daf  mov     rcx, [rbp+Binding]
0x180007db3  test    rcx, rcx
0x180007db6  jz      loc_180007E49
0x180007dbc  mov     [rbp+Binding], rcx
0x180007dc0  lea     rcx, [rbp+Binding]; Binding
0x180007dc4  call    cs:__imp_RpcBindingFree
0x180007dca  jmp     short loc_180007E49
0x180007dcc  mov     rbx, [rbp+Binding]
0x180007dd0  lea     rax, [rbp+var_38]
0x180007dd4  mov     [rbp+var_30], rax
0x180007dd8  lea     r9, [rbp+var_48]
0x180007ddc  lea     rax, [rbp+var_20]
0x180007de0  mov     [rbp+var_38], 0
0x180007de8  mov     qword ptr [rbp+var_28], rax
0x180007dec  lea     r8, [rbp+var_40]
0x180007df0  lea     rax, [rbp+var_30]
0x180007df4  mov     [rbp+Binding], rbx
0x180007df8  mov     [rsp+80h+var_58], rax
0x180007dfd  lea     rdx, [rbp+Binding]
0x180007e01  lea     rax, [rbp+var_28]
0x180007e05  xorps   xmm0, xmm0
0x180007e08  mov     qword ptr [rsp+80h+var_60], rax; int
0x180007e0d  movups  [rbp+var_20], xmm0
0x180007e11  call    ??$InvokeStubFunction@P6AJPEAXW4_CMS_CLIENT_ID@@PEAU_CMS_STORAGE_PROPERTIES@@PEAU_GUID@@PEAPEAX@ZPEAXAEAW41@AEAPEAU2@PEAU3@PEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAXW4_CMS_CLIENT_ID@@PEAU_CMS_STORAGE_PROPERTIES@@PEAU_GUID@@PEAPEAX@Z$$QEAPEAXAEAW43@AEAPEAU4@$$QEAPEAU5@$$QEAPEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_CLIENT_ID,_CMS_STORAGE_PROPERTIES *,_GUID *,void * *),void *,_CMS_CLIENT_ID &,_CMS_STORAGE_PROPERTIES * &,_GUID *,void * *>(long (*)(void *,_CMS_CLIENT_ID,_CMS_STORAGE_PROPERTIES *,_GUID *,void * *),void * &&,_CMS_CLIENT_ID &,_CMS_STORAGE_PROPERTIES * &,_GUID * &&,void * * &&)
0x180007e16  mov     esi, eax
0x180007e18  test    eax, eax
0x180007e1a  jns     short loc_180007E58
0x180007e1c  mov     rcx, [rbp+28h]; this
0x180007e20  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180007e27  mov     r9d, eax; char *
0x180007e2a  mov     edx, 538h; void *
0x180007e2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007e34  test    rbx, rbx
0x180007e37  jz      short loc_180007E47
0x180007e39  lea     rcx, [rbp+var_48]; Binding
0x180007e3d  mov     [rbp+var_48], rbx
0x180007e41  call    cs:__imp_RpcBindingFree
0x180007e47  mov     ebx, esi
0x180007e49  mov     edx, 18h; struct std::nothrow_t *
0x180007e4e  mov     rcx, rdi; void *
0x180007e51  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007e56  jmp     short loc_180007EAB
0x180007e58  mov     rax, [rbp+var_38]
0x180007e5c  mov     [rdi], rax
0x180007e5f  movups  xmm0, [rbp+var_20]
0x180007e63  movdqu  xmmword ptr [rdi+8], xmm0
0x180007e68  mov     [r14], rdi
0x180007e6b  test    rbx, rbx
0x180007e6e  jz      short loc_180007E7E
0x180007e70  lea     rcx, [rbp+var_48]; Binding
0x180007e74  mov     [rbp+var_48], rbx
0x180007e78  call    cs:__imp_RpcBindingFree
0x180007e7e  xor     eax, eax
0x180007e80  jmp     short loc_180007EAD
0x180007e82  mov     ebx, 8007000Eh
0x180007e87  mov     edx, 527h
0x180007e8c  jmp     short loc_180007E98
0x180007e8e  mov     edx, 522h; void *
0x180007e93  mov     ebx, 80070057h
0x180007e98  mov     rcx, [rbp+28h]; this
0x180007e9c  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180007ea3  mov     r9d, ebx; char *
0x180007ea6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007eab  mov     eax, ebx
0x180007ead  mov     rcx, [rbp+var_10]
0x180007eb1  xor     rcx, rsp; StackCookie
0x180007eb4  call    __security_check_cookie
0x180007eb9  add     rsp, 80h
0x180007ec0  pop     r14
0x180007ec2  pop     rdi
0x180007ec3  pop     rsi
0x180007ec4  pop     rbx
0x180007ec5  pop     rbp
0x180007ec6  retn
```
