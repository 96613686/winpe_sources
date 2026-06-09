# CmsInternalQueryInformationStorage

- ea: `0x18000c420`
- end: `0x18000c5de`
- name: `CmsInternalQueryInformationStorage`
- size: `446`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callees

- `0x180001550`
- `0x180002158`
- `0x180002be8`
- `0x1800043b0`
- `0x1800044b0`
- `0x1800048a0`
- `0x1800066e4`
- `0x18000ba8c`
- `0x18000c420`

## string_xrefs

- `0x18000c49b`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`
- `0x18000c58e`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`
- `0x18000c5c9`: `onecore\base\gendrv\silos\clem\client\dll\internalapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CmsInternalQueryInformationStorage(__int64 *a1, _DWORD *a2, unsigned int *a3)
{
  __int64 v6; // rcx
  int v7; // eax
  unsigned int v8; // esi
  const char *v10; // r9
  unsigned int v11; // edx
  unsigned int v12; // ecx
  int v13; // eax
  void *v14; // rdx
  unsigned int v15; // r8d
  __int128 *v16; // [rsp+20h] [rbp-79h] BYREF
  __int64 v17; // [rsp+28h] [rbp-71h] BYREF
  __int128 v18; // [rsp+30h] [rbp-69h] BYREF
  __int128 v19; // [rsp+40h] [rbp-59h]
  __int128 v20; // [rsp+50h] [rbp-49h]
  __int128 v21; // [rsp+60h] [rbp-39h]
  __int64 v22; // [rsp+70h] [rbp-29h]
  __int128 v23; // [rsp+80h] [rbp-19h] BYREF
  __int128 v24; // [rsp+90h] [rbp-9h]
  __int128 v25; // [rsp+A0h] [rbp+7h]
  __int128 v26; // [rsp+B0h] [rbp+17h]
  __int64 v27; // [rsp+C0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  if ( a3 && (!*a3 || a2) )
  {
    memset_0(&v23, 0, 0x48u);
    v16 = &v23;
    v17 = *a1;
    v7 = ___InvokeStubFunction_P6AJPEAXPEAU__MIDL_CmRpc_0002___ZPEAXPEAV__unique_struct_U__MIDL_CmRpc_0002____A6AXPEAU1___E_1_CleanupRpcContainerStorageInfo__YAX0_Z__T_0A__wil___Rpc_Manager_Container__YAJP6AJPEAXPEAU__MIDL_CmRpc_0002___Z__QEAPEAX__QEAPEAV__unique_struct_U__MIDL_CmRpc_0002____A6AXPEAU1___E_1_CleanupRpcContainerStorageInfo__YAX0_Z__T_0A__wil___Z(
           v6,
           &v17,
           &v16);
    v8 = v7;
    if ( v7 >= 0 )
    {
      LODWORD(v16) = 0;
      v18 = v23;
      v19 = v24;
      v20 = v25;
      v21 = v26;
      v22 = v27;
      if ( (unsigned int)Container::Manager::Client::ConvertToContainerStorageInfo(&v18, 0, &v16) != -2147024774 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x1DF,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
          v10);
      v11 = (_DWORD)v16 + 8;
      v12 = *a3;
      *a3 = (_DWORD)v16 + 8;
      if ( v12 >= v11 )
      {
        v18 = v23;
        v19 = v24;
        v20 = v25;
        v21 = v26;
        v22 = v27;
        v13 = Container::Manager::Client::ConvertToContainerStorageInfo(&v18, a2 + 2, &v16);
        if ( v13 < 0 )
          wil::details::in1diag3::_FailFast_Hr(retaddr, v14, v15, (const char *)(unsigned int)v13, (int)v16);
        *a2 = v23;
        CleanupRpcContainerStorageInfo((struct __MIDL_CmRpc_0002 *)&v23);
        return 0;
      }
      else
      {
        CleanupRpcContainerStorageInfo((struct __MIDL_CmRpc_0002 *)&v23);
        return 2147942522LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D6,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
        (const char *)(unsigned int)v7,
        (int)v16);
      CleanupRpcContainerStorageInfo((struct __MIDL_CmRpc_0002 *)&v23);
      return v8;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CC,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\internalapi.cpp",
      (const char *)0x80070057LL,
      (int)v16);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000c420  mov     [rsp-8+arg_18], rbx
0x18000c425  push    rbp
0x18000c426  push    rsi
0x18000c427  push    rdi
0x18000c428  lea     rbp, [rsp-47h]
0x18000c42d  sub     rsp, 0E0h
0x18000c434  mov     rax, cs:__security_cookie
0x18000c43b  xor     rax, rsp
0x18000c43e  mov     [rbp+57h+var_20], rax
0x18000c442  mov     rbx, r8
0x18000c445  mov     rdi, rdx
0x18000c448  mov     rsi, rcx
0x18000c44b  test    r8, r8
0x18000c44e  jz      loc_18000C582
0x18000c454  cmp     dword ptr [r8], 0
0x18000c458  jbe     short loc_18000C463
0x18000c45a  test    rdx, rdx
0x18000c45d  jz      loc_18000C582
0x18000c463  xor     edx, edx; Val
0x18000c465  lea     r8d, [rdx+48h]; Size
0x18000c469  lea     rcx, [rbp+57h+var_70]; void *
0x18000c46d  call    memset_0
0x18000c472  lea     rax, [rbp+57h+var_70]
0x18000c476  mov     [rbp+57h+var_D0], rax
0x18000c47a  mov     rax, [rsi]
0x18000c47d  mov     [rbp+57h+var_C8], rax
0x18000c481  lea     r8, [rbp+57h+var_D0]
0x18000c485  lea     rdx, [rbp+57h+var_C8]
0x18000c489  call    ??$InvokeStubFunction@P6AJPEAXPEAU__MIDL_CmRpc_0002@@@ZPEAXPEAV?$unique_struct@U__MIDL_CmRpc_0002@@$$A6AXPEAU1@@_E$1?CleanupRpcContainerStorageInfo@@YAX0@Z$$T$0A@@wil@@@Rpc@Manager@Container@@YAJP6AJPEAXPEAU__MIDL_CmRpc_0002@@@Z$$QEAPEAX$$QEAPEAV?$unique_struct@U__MIDL_CmRpc_0002@@$$A6AXPEAU1@@_E$1?CleanupRpcContainerStorageInfo@@YAX0@Z$$T$0A@@wil@@@Z
0x18000c48e  mov     esi, eax
0x18000c490  test    eax, eax
0x18000c492  jns     short loc_18000C4BE
0x18000c494  mov     rcx, [rbp+5Fh]; this
0x18000c498  mov     r9d, eax; char *
0x18000c49b  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000c4a2  mov     edx, 1D6h; void *
0x18000c4a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c4ac  nop
0x18000c4ad  lea     rcx, [rbp+57h+var_70]; struct __MIDL_CmRpc_0002 *
0x18000c4b1  call    ?CleanupRpcContainerStorageInfo@@YAXPEAU__MIDL_CmRpc_0002@@@Z; CleanupRpcContainerStorageInfo(__MIDL_CmRpc_0002 *)
0x18000c4b6  nop
0x18000c4b7  mov     eax, esi
0x18000c4b9  jmp     loc_18000C5A1
0x18000c4be  mov     dword ptr [rbp+57h+var_D0], 0
0x18000c4c5  movaps  xmm0, [rbp+57h+var_70]
0x18000c4c9  movaps  [rbp+57h+var_C0], xmm0
0x18000c4cd  movaps  xmm1, [rbp+57h+var_60]
0x18000c4d1  movaps  [rbp+57h+var_B0], xmm1
0x18000c4d5  movaps  xmm0, [rbp+57h+var_50]
0x18000c4d9  movaps  [rbp+57h+var_A0], xmm0
0x18000c4dd  movaps  xmm1, [rbp+57h+var_40]
0x18000c4e1  movaps  [rbp+57h+var_90], xmm1
0x18000c4e5  movsd   xmm0, [rbp+57h+var_30]
0x18000c4ea  movsd   [rbp+57h+var_80], xmm0
0x18000c4ef  mov     rsi, [rbp+5Fh]
0x18000c4f3  lea     r8, [rbp+57h+var_D0]
0x18000c4f7  xor     edx, edx
0x18000c4f9  lea     rcx, [rbp+57h+var_C0]
0x18000c4fd  call    ?ConvertToContainerStorageInfo@Client@Manager@Container@@YAJU__MIDL_CmRpc_0002@@PEAU_CMS_STORAGE_INFO@@PEAK@Z; Container::Manager::Client::ConvertToContainerStorageInfo(__MIDL_CmRpc_0002,_CMS_STORAGE_INFO *,ulong *)
0x18000c502  cmp     eax, 8007007Ah
0x18000c507  jnz     loc_18000C5C9
0x18000c50d  mov     edx, dword ptr [rbp+57h+var_D0]
0x18000c510  add     edx, 8
0x18000c513  mov     ecx, [rbx]
0x18000c515  mov     [rbx], edx
0x18000c517  cmp     ecx, edx
0x18000c519  jnb     short loc_18000C52C
0x18000c51b  lea     rcx, [rbp+57h+var_70]; struct __MIDL_CmRpc_0002 *
0x18000c51f  call    ?CleanupRpcContainerStorageInfo@@YAXPEAU__MIDL_CmRpc_0002@@@Z; CleanupRpcContainerStorageInfo(__MIDL_CmRpc_0002 *)
0x18000c524  nop
0x18000c525  mov     eax, 8007007Ah
0x18000c52a  jmp     short loc_18000C5A1
0x18000c52c  movaps  xmm0, [rbp+57h+var_70]
0x18000c530  movaps  [rbp+57h+var_C0], xmm0
0x18000c534  movaps  xmm1, [rbp+57h+var_60]
0x18000c538  movaps  [rbp+57h+var_B0], xmm1
0x18000c53c  movaps  xmm0, [rbp+57h+var_50]
0x18000c540  movaps  [rbp+57h+var_A0], xmm0
0x18000c544  movaps  xmm1, [rbp+57h+var_40]
0x18000c548  movaps  [rbp+57h+var_90], xmm1
0x18000c54c  movsd   xmm0, [rbp+57h+var_30]
0x18000c551  movsd   [rbp+57h+var_80], xmm0
0x18000c556  lea     rdx, [rdi+8]
0x18000c55a  lea     r8, [rbp+57h+var_D0]
0x18000c55e  lea     rcx, [rbp+57h+var_C0]
0x18000c562  call    ?ConvertToContainerStorageInfo@Client@Manager@Container@@YAJU__MIDL_CmRpc_0002@@PEAU_CMS_STORAGE_INFO@@PEAK@Z; Container::Manager::Client::ConvertToContainerStorageInfo(__MIDL_CmRpc_0002,_CMS_STORAGE_INFO *,ulong *)
0x18000c567  mov     rcx, [rbp+5Fh]; this
0x18000c56b  test    eax, eax
0x18000c56d  js      short loc_18000C5C0
0x18000c56f  mov     eax, dword ptr [rbp+57h+var_70]
0x18000c572  mov     [rdi], eax
0x18000c574  lea     rcx, [rbp+57h+var_70]; struct __MIDL_CmRpc_0002 *
0x18000c578  call    ?CleanupRpcContainerStorageInfo@@YAXPEAU__MIDL_CmRpc_0002@@@Z; CleanupRpcContainerStorageInfo(__MIDL_CmRpc_0002 *)
0x18000c57d  nop
0x18000c57e  xor     eax, eax
0x18000c580  jmp     short loc_18000C5A1
0x18000c582  mov     rcx, [rbp+5Fh]; this
0x18000c586  mov     ebx, 80070057h
0x18000c58b  mov     r9d, ebx; char *
0x18000c58e  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000c595  mov     edx, 1CCh; void *
0x18000c59a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c59f  mov     eax, ebx
0x18000c5a1  mov     rcx, [rbp+57h+var_20]
0x18000c5a5  xor     rcx, rsp; StackCookie
0x18000c5a8  call    __security_check_cookie
0x18000c5ad  mov     rbx, [rsp+0F0h+arg_18]
0x18000c5b5  add     rsp, 0E0h
0x18000c5bc  pop     rdi
0x18000c5bd  pop     rsi
0x18000c5be  pop     rbp
0x18000c5bf  retn
0x18000c5c0  mov     r9d, eax; char *
0x18000c5c3  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000c5c9  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000c5d0  mov     edx, 1DFh; void *
0x18000c5d5  mov     rcx, rsi; this
0x18000c5d8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
