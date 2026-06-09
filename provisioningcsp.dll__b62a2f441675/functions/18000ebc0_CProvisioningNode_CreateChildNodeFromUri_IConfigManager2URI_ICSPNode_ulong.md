# CProvisioningNode::CreateChildNodeFromUri(IConfigManager2URI *,ICSPNode * *,ulong *)

- ea: `0x18000ebc0`
- end: `0x18000ed39`
- name: `?CreateChildNodeFromUri@CProvisioningNode@@AEAAJPEAUIConfigManager2URI@@PEAPEAUICSPNode@@PEAK@Z`
- size: `377`
- prototype: `int(CProvisioningNode *__hidden this, struct IConfigManager2URI *, struct ICSPNode **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e6e0`

## callees

- `0x180006974`
- `0x180009890`
- `0x18000ebc0`
- `0x180010f8c`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CProvisioningNode::CreateChildNodeFromUri(
        CProvisioningNode *this,
        struct IConfigManager2URI *a2,
        struct ICSPNode **a3,
        unsigned int *a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  struct IConfigManager2URI *v9; // rcx
  const struct CspNodeMapBase *v10; // rcx
  const struct CSP_NODE_DATA *NodeMapEntryForURI; // rax
  int NodeInstance; // eax
  struct IConfigManager2URI *v13; // rcx
  struct IConfigManager2URI *v14; // rcx
  struct IConfigManager2URI *v16; // rcx
  int v17; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  struct IConfigManager2URI *v19; // [rsp+50h] [rbp+20h] BYREF

  v19 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, struct IConfigManager2URI *, _QWORD, _QWORD))(**((_QWORD **)this + 3) + 168LL))(
         *((_QWORD *)this + 3),
         a2,
         0,
         0);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\add.cpp",
      (const char *)(unsigned int)v7,
      (int)&v19);
    v9 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return v8;
  }
  v10 = *(const struct CspNodeMapBase **)(*((_QWORD *)this + 2) + 32LL);
  if ( !v10 || (NodeMapEntryForURI = CspGetNodeMapEntryForURI(v10, v19)) == 0 )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\add.cpp",
      (const char *)0x8000FFFFLL,
      (int)&v19);
    v16 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return v8;
  }
  NodeInstance = CProvisioningNode::CreateNodeInstance(
                   *((struct CConfigServiceProvider2Impl **)this + 2),
                   v19,
                   NodeMapEntryForURI,
                   0,
                   a3,
                   a4);
  v8 = NodeInstance;
  if ( NodeInstance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\add.cpp",
      (const char *)(unsigned int)NodeInstance,
      v17);
    v13 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return v8;
  }
  v14 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v14 + 16LL))(v14);
  }
  return 0;
}

```

## disassembly

```asm
0x18000ebc0  mov     [rsp-18h+arg_8], rbx
0x18000ebc5  mov     [rsp-18h+arg_10], rsi
0x18000ebca  push    rbp
0x18000ebcb  push    rdi
0x18000ebcc  push    r14
0x18000ebce  mov     rbp, rsp
0x18000ebd1  sub     rsp, 30h
0x18000ebd5  mov     rsi, r9
0x18000ebd8  mov     r14, r8
0x18000ebdb  mov     rdi, rcx
0x18000ebde  mov     [rbp+arg_0], 0
0x18000ebe6  mov     rcx, [rcx+18h]
0x18000ebea  mov     rax, [rcx]
0x18000ebed  lea     r8, [rbp+arg_0]
0x18000ebf1  mov     [rsp+30h+var_10], r8; int
0x18000ebf6  xor     r9d, r9d
0x18000ebf9  xor     r8d, r8d
0x18000ebfc  mov     rax, [rax+0A8h]
0x18000ec03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec08  mov     ebx, eax
0x18000ec0a  test    eax, eax
0x18000ec0c  jns     short loc_18000EC4A
0x18000ec0e  mov     rcx, [rbp+18h]; this
0x18000ec12  mov     r9d, eax; char *
0x18000ec15  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\provcsp\\add.c"...
0x18000ec1c  mov     edx, 42h ; 'B'; void *
0x18000ec21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ec26  nop
0x18000ec27  mov     rcx, [rbp+arg_0]
0x18000ec2b  test    rcx, rcx
0x18000ec2e  jz      short loc_18000EC45
0x18000ec30  mov     [rbp+arg_0], 0
0x18000ec38  mov     rax, [rcx]
0x18000ec3b  mov     rax, [rax+10h]
0x18000ec3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec44  nop
0x18000ec45  jmp     loc_18000ED23
0x18000ec4a  mov     rax, [rdi+10h]
0x18000ec4e  mov     rcx, [rax+20h]; struct CspNodeMapBase *
0x18000ec52  test    rcx, rcx
0x18000ec55  jz      loc_18000ECE7
0x18000ec5b  mov     rdx, [rbp+arg_0]; struct IConfigManager2URI *
0x18000ec5f  call    ?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z; CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)
0x18000ec64  test    rax, rax
0x18000ec67  jz      short loc_18000ECE7
0x18000ec69  mov     [rsp+30h+var_8], rsi; unsigned int *
0x18000ec6e  mov     [rsp+30h+var_10], r14; int
0x18000ec73  xor     r9d, r9d; int
0x18000ec76  mov     r8, rax; struct CSP_NODE_DATA *
0x18000ec79  mov     rdx, [rbp+arg_0]; struct IConfigManager2URI *
0x18000ec7d  mov     rcx, [rdi+10h]; struct CConfigServiceProvider2Impl *
0x18000ec81  call    ?CreateNodeInstance@CProvisioningNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z; CProvisioningNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)
0x18000ec86  mov     ebx, eax
0x18000ec88  test    eax, eax
0x18000ec8a  jns     short loc_18000ECC5
0x18000ec8c  mov     rcx, [rbp+18h]; this
0x18000ec90  mov     r9d, eax; char *
0x18000ec93  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\provcsp\\add.c"...
0x18000ec9a  mov     edx, 48h ; 'H'; void *
0x18000ec9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000eca4  nop
0x18000eca5  mov     rcx, [rbp+arg_0]
0x18000eca9  test    rcx, rcx
0x18000ecac  jz      short loc_18000ECC3
0x18000ecae  mov     [rbp+arg_0], 0
0x18000ecb6  mov     rax, [rcx]
0x18000ecb9  mov     rax, [rax+10h]
0x18000ecbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecc2  nop
0x18000ecc3  jmp     short loc_18000ED23
0x18000ecc5  mov     rcx, [rbp+arg_0]
0x18000ecc9  test    rcx, rcx
0x18000eccc  jz      short loc_18000ECE3
0x18000ecce  mov     [rbp+arg_0], 0
0x18000ecd6  mov     rax, [rcx]
0x18000ecd9  mov     rax, [rax+10h]
0x18000ecdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ece2  nop
0x18000ece3  xor     eax, eax
0x18000ece5  jmp     short loc_18000ED25
0x18000ece7  mov     rcx, [rbp+18h]; this
0x18000eceb  mov     ebx, 8000FFFFh
0x18000ecf0  mov     r9d, ebx; char *
0x18000ecf3  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\provcsp\\add.c"...
0x18000ecfa  mov     edx, 45h ; 'E'; void *
0x18000ecff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ed04  nop
0x18000ed05  mov     rcx, [rbp+arg_0]
0x18000ed09  test    rcx, rcx
0x18000ed0c  jz      short loc_18000ED23
0x18000ed0e  mov     [rbp+arg_0], 0
0x18000ed16  mov     rdx, [rcx]
0x18000ed19  mov     rax, [rdx+10h]
0x18000ed1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed22  nop
0x18000ed23  mov     eax, ebx
0x18000ed25  mov     rbx, [rsp+30h+arg_8]
0x18000ed2a  mov     rsi, [rsp+30h+arg_10]
0x18000ed2f  add     rsp, 30h
0x18000ed33  pop     r14
0x18000ed35  pop     rdi
0x18000ed36  pop     rbp
0x18000ed37  retn
```
