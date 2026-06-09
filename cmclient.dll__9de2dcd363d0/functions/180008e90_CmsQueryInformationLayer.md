# CmsQueryInformationLayer

- ea: `0x180008e90`
- end: `0x180008fd8`
- name: `CmsQueryInformationLayer`
- size: `328`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180002c50`
- `0x1800043e8`
- `0x1800066e4`
- `0x180007074`
- `0x180008e90`
- `0x18000ee00`

## string_xrefs

- `0x180008eef`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`
- `0x180008fb2`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CmsQueryInformationLayer(_QWORD *a1, _QWORD *a2, unsigned int *a3)
{
  int v5; // eax
  unsigned int v6; // esi
  void *v8; // rdx
  __int64 v9; // rax
  unsigned int v10; // r9d
  unsigned int v11; // r8d
  unsigned __int64 v12; // rcx
  unsigned int v13; // eax
  _QWORD *v14; // rbx
  int v15[10]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  void *Src; // [rsp+60h] [rbp+18h] BYREF
  void **p_Src; // [rsp+68h] [rbp+20h] BYREF

  if ( a3 && (!*a3 || a2) )
  {
    Src = 0;
    p_Src = &Src;
    *(_QWORD *)v15 = *a1;
    v5 = ___InvokeStubFunction_P6AJPEAXPEAU__MIDL_CmRpc_0005___ZPEAXPEAV__unique_struct_U__MIDL_CmRpc_0005____A6AXPEAU1___E_1_CleanupRpcLayerInfo__YAX0_Z__T_0A__wil___Rpc_Manager_Container__YAJP6AJPEAXPEAU__MIDL_CmRpc_0005___Z__QEAPEAX__QEAPEAV__unique_struct_U__MIDL_CmRpc_0005____A6AXPEAU1___E_1_CleanupRpcLayerInfo__YAX0_Z__T_0A__wil___Z(
           a1,
           v15,
           &p_Src);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x69E,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
        (const char *)(unsigned int)v5,
        v15[0]);
      CleanupRpcLayerInfo((struct __MIDL_CmRpc_0005 *)&Src);
      return v6;
    }
    v8 = Src;
    if ( Src )
    {
      v9 = -1;
      do
        ++v9;
      while ( *((_WORD *)Src + v9) );
      v10 = 2 * v9 + 2;
      v11 = 2 * v9 + 10;
      v12 = 8;
    }
    else
    {
      v11 = 8;
      v12 = 0;
      v10 = 0;
    }
    v13 = *a3;
    *a3 = v11;
    if ( v13 < v11 )
    {
      CleanupRpcLayerInfo((struct __MIDL_CmRpc_0005 *)&Src);
      return 2147942522LL;
    }
    if ( a2 || !v11 )
    {
      if ( !v8 )
      {
LABEL_19:
        CleanupRpcLayerInfo((struct __MIDL_CmRpc_0005 *)&Src);
        return 0;
      }
      if ( v11 >= v12 && v11 - v12 >= v10 )
      {
        v14 = &a2[v12 / 8];
        memcpy_0(&a2[v12 / 8], v8, v10);
        *a2 = v14;
        goto LABEL_19;
      }
    }
    gsl::details::terminate((gsl::details *)v12);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x694,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)0x80070057LL,
    v15[0]);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180008e90  mov     [rsp+arg_0], rbx
0x180008e95  push    rbp
0x180008e96  push    rsi
0x180008e97  push    rdi
0x180008e98  sub     rsp, 30h
0x180008e9c  mov     rbx, r8
0x180008e9f  mov     rdi, rdx
0x180008ea2  xor     ebp, ebp
0x180008ea4  test    r8, r8
0x180008ea7  jz      loc_180008FA5
0x180008ead  cmp     [r8], ebp
0x180008eb0  jbe     short loc_180008EBB
0x180008eb2  test    rdx, rdx
0x180008eb5  jz      loc_180008FA5
0x180008ebb  mov     [rsp+48h+Src], rbp
0x180008ec0  lea     rax, [rsp+48h+Src]
0x180008ec5  mov     [rsp+48h+arg_18], rax
0x180008eca  mov     rax, [rcx]
0x180008ecd  mov     qword ptr [rsp+48h+var_28], rax; int
0x180008ed2  lea     r8, [rsp+48h+arg_18]
0x180008ed7  lea     rdx, [rsp+48h+var_28]
0x180008edc  call    ??$InvokeStubFunction@P6AJPEAXPEAU__MIDL_CmRpc_0005@@@ZPEAXPEAV?$unique_struct@U__MIDL_CmRpc_0005@@$$A6AXPEAU1@@_E$1?CleanupRpcLayerInfo@@YAX0@Z$$T$0A@@wil@@@Rpc@Manager@Container@@YAJP6AJPEAXPEAU__MIDL_CmRpc_0005@@@Z$$QEAPEAX$$QEAPEAV?$unique_struct@U__MIDL_CmRpc_0005@@$$A6AXPEAU1@@_E$1?CleanupRpcLayerInfo@@YAX0@Z$$T$0A@@wil@@@Z
0x180008ee1  mov     esi, eax
0x180008ee3  test    eax, eax
0x180008ee5  jns     short loc_180008F13
0x180008ee7  mov     rcx, [rsp+48h]; this
0x180008eec  mov     r9d, eax; char *
0x180008eef  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180008ef6  mov     edx, 69Eh; void *
0x180008efb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f00  nop
0x180008f01  lea     rcx, [rsp+48h+Src]; struct __MIDL_CmRpc_0005 *
0x180008f06  call    ?CleanupRpcLayerInfo@@YAXPEAU__MIDL_CmRpc_0005@@@Z; CleanupRpcLayerInfo(__MIDL_CmRpc_0005 *)
0x180008f0b  nop
0x180008f0c  mov     eax, esi
0x180008f0e  jmp     loc_180008FC5
0x180008f13  mov     rdx, [rsp+48h+Src]; Src
0x180008f18  test    rdx, rdx
0x180008f1b  jz      short loc_180008F3D
0x180008f1d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008f21  inc     rax
0x180008f24  cmp     [rdx+rax*2], bp
0x180008f28  jnz     short loc_180008F21
0x180008f2a  lea     r9d, ds:2[rax*2]
0x180008f32  lea     r8d, [r9+8]
0x180008f36  mov     ecx, 8
0x180008f3b  jmp     short loc_180008F49
0x180008f3d  mov     r8d, 8
0x180008f43  mov     rcx, rbp; this
0x180008f46  mov     r9d, ebp
0x180008f49  mov     eax, [rbx]
0x180008f4b  mov     [rbx], r8d
0x180008f4e  cmp     eax, r8d
0x180008f51  jnb     short loc_180008F65
0x180008f53  lea     rcx, [rsp+48h+Src]; struct __MIDL_CmRpc_0005 *
0x180008f58  call    ?CleanupRpcLayerInfo@@YAXPEAU__MIDL_CmRpc_0005@@@Z; CleanupRpcLayerInfo(__MIDL_CmRpc_0005 *)
0x180008f5d  nop
0x180008f5e  mov     eax, 8007007Ah
0x180008f63  jmp     short loc_180008FC5
0x180008f65  mov     eax, r8d
0x180008f68  test    rdi, rdi
0x180008f6b  jnz     short loc_180008F72
0x180008f6d  test    r8d, r8d
0x180008f70  jnz     short loc_180008FD2
0x180008f72  test    rdx, rdx
0x180008f75  jz      short loc_180008F96
0x180008f77  cmp     rax, rcx
0x180008f7a  jb      short loc_180008FD2
0x180008f7c  mov     r8d, r9d; Size
0x180008f7f  sub     rax, rcx
0x180008f82  cmp     rax, r8
0x180008f85  jb      short loc_180008FD2
0x180008f87  lea     rbx, [rcx+rdi]
0x180008f8b  mov     rcx, rbx; void *
0x180008f8e  call    memcpy_0
0x180008f93  mov     [rdi], rbx
0x180008f96  lea     rcx, [rsp+48h+Src]; struct __MIDL_CmRpc_0005 *
0x180008f9b  call    ?CleanupRpcLayerInfo@@YAXPEAU__MIDL_CmRpc_0005@@@Z; CleanupRpcLayerInfo(__MIDL_CmRpc_0005 *)
0x180008fa0  nop
0x180008fa1  xor     eax, eax
0x180008fa3  jmp     short loc_180008FC5
0x180008fa5  mov     rcx, [rsp+48h]; this
0x180008faa  mov     ebx, 80070057h
0x180008faf  mov     r9d, ebx; char *
0x180008fb2  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180008fb9  mov     edx, 694h; void *
0x180008fbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008fc3  mov     eax, ebx
0x180008fc5  mov     rbx, [rsp+48h+arg_0]
0x180008fca  add     rsp, 30h
0x180008fce  pop     rdi
0x180008fcf  pop     rsi
0x180008fd0  pop     rbp
0x180008fd1  retn
0x180008fd2  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
```
