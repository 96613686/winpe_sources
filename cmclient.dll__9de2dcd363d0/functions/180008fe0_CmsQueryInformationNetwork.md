# CmsQueryInformationNetwork

- ea: `0x180008fe0`
- end: `0x1800090ff`
- name: `CmsQueryInformationNetwork`
- size: `287`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180002884`
- `0x1800043e8`
- `0x1800066e4`
- `0x180007074`
- `0x180008fe0`
- `0x18000ee00`

## string_xrefs

- `0x180009035`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CmsQueryInformationNetwork(__int64 a1, __int64 a2, _QWORD *a3, unsigned int *a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  void *v9; // rdx
  __int64 v10; // rax
  unsigned int v11; // r9d
  unsigned int v12; // r8d
  unsigned __int64 v13; // rcx
  unsigned int v14; // eax
  _QWORD *v15; // rbx
  void **p_Src; // [rsp+20h] [rbp-10h] BYREF
  __int64 v17; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  void *Src; // [rsp+50h] [rbp+20h] BYREF
  __int64 v20; // [rsp+58h] [rbp+28h] BYREF

  v20 = a2;
  Src = 0;
  p_Src = &Src;
  v17 = *(_QWORD *)(a1 + 24);
  v6 = ___InvokeStubFunction_P6AJPEAXPEAU_GUID__PEAU__MIDL_CmRpc_0004___ZPEAXAEAPEAU1_PEAV__unique_struct_U__MIDL_CmRpc_0004____A6AXPEAU1___E_1_CleanupRpcNetworkInfo__YAX0_Z__T_0A__wil___Rpc_Manager_Container__YAJP6AJPEAXPEAU_GUID__PEAU__MIDL_CmRpc_0004___Z__QEAPEAXAEAPEAU3___QEAPEAV__unique_struct_U__MIDL_CmRpc_0004____A6AXPEAU1___E_1_CleanupRpcNetworkInfo__YAX0_Z__T_0A__wil___Z(
         a1,
         &v17,
         &v20,
         &p_Src);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x474,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)(unsigned int)v6,
      (int)p_Src);
    CleanupRpcLayerInfo((struct __MIDL_CmRpc_0005 *)&Src);
    return v7;
  }
  v9 = Src;
  if ( Src )
  {
    v10 = -1;
    do
      ++v10;
    while ( *((_WORD *)Src + v10) );
    v11 = 2 * v10 + 2;
    v12 = 2 * v10 + 10;
    v13 = 8;
  }
  else
  {
    v12 = 8;
    v13 = 0;
    v11 = 0;
  }
  v14 = *a4;
  *a4 = v12;
  if ( v14 < v12 )
  {
    CleanupRpcLayerInfo((struct __MIDL_CmRpc_0005 *)&Src);
    return 2147942522LL;
  }
  if ( !a3 && v12 )
    goto LABEL_17;
  if ( v9 )
  {
    if ( v12 >= v13 && v12 - v13 >= v11 )
    {
      v15 = &a3[v13 / 8];
      memcpy_0(&a3[v13 / 8], v9, v11);
      *a3 = v15;
      goto LABEL_16;
    }
LABEL_17:
    gsl::details::terminate((gsl::details *)v13);
  }
LABEL_16:
  CleanupRpcLayerInfo((struct __MIDL_CmRpc_0005 *)&Src);
  return 0;
}

```

## disassembly

```asm
0x180008fe0  mov     [rsp-18h+arg_10], rbx
0x180008fe5  mov     [rsp-18h+arg_18], rsi
0x180008fea  mov     [rsp-18h+arg_8], rdx
0x180008fef  push    rbp
0x180008ff0  push    rdi
0x180008ff1  push    r14
0x180008ff3  mov     rbp, rsp
0x180008ff6  sub     rsp, 30h
0x180008ffa  mov     rsi, r9
0x180008ffd  mov     rdi, r8
0x180009000  xor     r14d, r14d
0x180009003  mov     [rbp+Src], r14
0x180009007  lea     rax, [rbp+Src]
0x18000900b  mov     [rbp+var_10], rax
0x18000900f  mov     rax, [rcx+18h]
0x180009013  mov     [rbp+var_8], rax
0x180009017  lea     r9, [rbp+var_10]
0x18000901b  lea     r8, [rbp+arg_8]
0x18000901f  lea     rdx, [rbp+var_8]
0x180009023  call    ??$InvokeStubFunction@P6AJPEAXPEAU_GUID@@PEAU__MIDL_CmRpc_0004@@@ZPEAXAEAPEAU1@PEAV?$unique_struct@U__MIDL_CmRpc_0004@@$$A6AXPEAU1@@_E$1?CleanupRpcNetworkInfo@@YAX0@Z$$T$0A@@wil@@@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_GUID@@PEAU__MIDL_CmRpc_0004@@@Z$$QEAPEAXAEAPEAU3@$$QEAPEAV?$unique_struct@U__MIDL_CmRpc_0004@@$$A6AXPEAU1@@_E$1?CleanupRpcNetworkInfo@@YAX0@Z$$T$0A@@wil@@@Z
0x180009028  mov     ebx, eax
0x18000902a  test    eax, eax
0x18000902c  jns     short loc_180009058
0x18000902e  mov     rcx, [rbp+18h]; this
0x180009032  mov     r9d, eax; char *
0x180009035  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000903c  mov     edx, 474h; void *
0x180009041  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009046  nop
0x180009047  lea     rcx, [rbp+Src]; struct __MIDL_CmRpc_0005 *
0x18000904b  call    ?CleanupRpcLayerInfo@@YAXPEAU__MIDL_CmRpc_0005@@@Z; CleanupRpcLayerInfo(__MIDL_CmRpc_0005 *)
0x180009050  nop
0x180009051  mov     eax, ebx
0x180009053  jmp     loc_1800090E6
0x180009058  mov     rdx, [rbp+Src]; Src
0x18000905c  test    rdx, rdx
0x18000905f  jz      short loc_180009082
0x180009061  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009065  inc     rax
0x180009068  cmp     [rdx+rax*2], r14w
0x18000906d  jnz     short loc_180009065
0x18000906f  lea     r9d, ds:2[rax*2]
0x180009077  lea     r8d, [r9+8]
0x18000907b  mov     ecx, 8
0x180009080  jmp     short loc_18000908E
0x180009082  mov     r8d, 8
0x180009088  mov     rcx, r14; this
0x18000908b  mov     r9d, r14d
0x18000908e  mov     eax, [rsi]
0x180009090  mov     [rsi], r8d
0x180009093  cmp     eax, r8d
0x180009096  jnb     short loc_1800090A9
0x180009098  lea     rcx, [rbp+Src]; struct __MIDL_CmRpc_0005 *
0x18000909c  call    ?CleanupRpcLayerInfo@@YAXPEAU__MIDL_CmRpc_0005@@@Z; CleanupRpcLayerInfo(__MIDL_CmRpc_0005 *)
0x1800090a1  nop
0x1800090a2  mov     eax, 8007007Ah
0x1800090a7  jmp     short loc_1800090E6
0x1800090a9  mov     eax, r8d
0x1800090ac  test    rdi, rdi
0x1800090af  jnz     short loc_1800090B6
0x1800090b1  test    r8d, r8d
0x1800090b4  jnz     short loc_1800090F9
0x1800090b6  test    rdx, rdx
0x1800090b9  jz      short loc_1800090DA
0x1800090bb  cmp     rax, rcx
0x1800090be  jb      short loc_1800090F9
0x1800090c0  mov     r8d, r9d; Size
0x1800090c3  sub     rax, rcx
0x1800090c6  cmp     rax, r8
0x1800090c9  jb      short loc_1800090F9
0x1800090cb  lea     rbx, [rcx+rdi]
0x1800090cf  mov     rcx, rbx; void *
0x1800090d2  call    memcpy_0
0x1800090d7  mov     [rdi], rbx
0x1800090da  lea     rcx, [rbp+Src]; struct __MIDL_CmRpc_0005 *
0x1800090de  call    ?CleanupRpcLayerInfo@@YAXPEAU__MIDL_CmRpc_0005@@@Z; CleanupRpcLayerInfo(__MIDL_CmRpc_0005 *)
0x1800090e3  nop
0x1800090e4  xor     eax, eax
0x1800090e6  mov     rbx, [rsp+30h+arg_10]
0x1800090eb  mov     rsi, [rsp+30h+arg_18]
0x1800090f0  add     rsp, 30h
0x1800090f4  pop     r14
0x1800090f6  pop     rdi
0x1800090f7  pop     rbp
0x1800090f8  retn
0x1800090f9  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
```
