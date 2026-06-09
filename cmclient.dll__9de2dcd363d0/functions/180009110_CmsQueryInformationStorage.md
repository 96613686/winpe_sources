# CmsQueryInformationStorage

- ea: `0x180009110`
- end: `0x18000925e`
- name: `CmsQueryInformationStorage`
- size: `334`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180001550`
- `0x180002158`
- `0x180002be8`
- `0x1800043b0`
- `0x1800044b0`
- `0x1800066e4`
- `0x180009110`

## string_xrefs

- `0x18000918b`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`
- `0x1800091f4`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`
- `0x18000922c`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CmsQueryInformationStorage(__int64 *a1, __int64 a2, _DWORD *a3)
{
  __int64 v6; // rcx
  int v7; // eax
  unsigned int v8; // edi
  int v10; // eax
  unsigned int v11; // ebx
  _OWORD *v12; // [rsp+20h] [rbp-79h] BYREF
  __int64 v13; // [rsp+28h] [rbp-71h] BYREF
  _OWORD v14[4]; // [rsp+30h] [rbp-69h] BYREF
  __int64 v15; // [rsp+70h] [rbp-29h]
  _OWORD v16[4]; // [rsp+80h] [rbp-19h] BYREF
  __int64 v17; // [rsp+C0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  if ( a3 && (!*a3 || a2) )
  {
    memset_0(v16, 0, 0x48u);
    v12 = v16;
    v13 = *a1;
    v7 = ___InvokeStubFunction_P6AJPEAXPEAU__MIDL_CmRpc_0002___ZPEAXPEAV__unique_struct_U__MIDL_CmRpc_0002____A6AXPEAU1___E_1_CleanupRpcContainerStorageInfo__YAX0_Z__T_0A__wil___Rpc_Manager_Container__YAJP6AJPEAXPEAU__MIDL_CmRpc_0002___Z__QEAPEAX__QEAPEAV__unique_struct_U__MIDL_CmRpc_0002____A6AXPEAU1___E_1_CleanupRpcContainerStorageInfo__YAX0_Z__T_0A__wil___Z(
           v6,
           &v13,
           &v12);
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x67D,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
        (const char *)(unsigned int)v7,
        (int)v12);
      CleanupRpcContainerStorageInfo((struct __MIDL_CmRpc_0002 *)v16);
      return v8;
    }
    v14[0] = v16[0];
    v14[1] = v16[1];
    v14[2] = v16[2];
    v14[3] = v16[3];
    v15 = v17;
    v10 = Container::Manager::Client::ConvertToContainerStorageInfo(v14, a2, a3);
    v11 = v10;
    if ( v10 >= 0 )
    {
      CleanupRpcContainerStorageInfo((struct __MIDL_CmRpc_0002 *)v16);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x683,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)(unsigned int)v10,
      (int)v12);
    CleanupRpcContainerStorageInfo((struct __MIDL_CmRpc_0002 *)v16);
  }
  else
  {
    v11 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x673,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)0x80070057LL,
      (int)v12);
  }
  return v11;
}

```

## disassembly

```asm
0x180009110  mov     [rsp-8+arg_18], rbx
0x180009115  push    rbp
0x180009116  push    rsi
0x180009117  push    rdi
0x180009118  lea     rbp, [rsp-47h]
0x18000911d  sub     rsp, 0E0h
0x180009124  mov     rax, cs:__security_cookie
0x18000912b  xor     rax, rsp
0x18000912e  mov     [rbp+57h+var_20], rax
0x180009132  mov     rbx, r8
0x180009135  mov     rsi, rdx
0x180009138  mov     rdi, rcx
0x18000913b  test    r8, r8
0x18000913e  jz      loc_180009220
0x180009144  cmp     dword ptr [r8], 0
0x180009148  jbe     short loc_180009153
0x18000914a  test    rdx, rdx
0x18000914d  jz      loc_180009220
0x180009153  xor     edx, edx; Val
0x180009155  lea     r8d, [rdx+48h]; Size
0x180009159  lea     rcx, [rbp+57h+var_70]; void *
0x18000915d  call    memset_0
0x180009162  lea     rax, [rbp+57h+var_70]
0x180009166  mov     [rbp+57h+var_D0], rax
0x18000916a  mov     rax, [rdi]
0x18000916d  mov     [rbp+57h+var_C8], rax
0x180009171  lea     r8, [rbp+57h+var_D0]
0x180009175  lea     rdx, [rbp+57h+var_C8]
0x180009179  call    ??$InvokeStubFunction@P6AJPEAXPEAU__MIDL_CmRpc_0002@@@ZPEAXPEAV?$unique_struct@U__MIDL_CmRpc_0002@@$$A6AXPEAU1@@_E$1?CleanupRpcContainerStorageInfo@@YAX0@Z$$T$0A@@wil@@@Rpc@Manager@Container@@YAJP6AJPEAXPEAU__MIDL_CmRpc_0002@@@Z$$QEAPEAX$$QEAPEAV?$unique_struct@U__MIDL_CmRpc_0002@@$$A6AXPEAU1@@_E$1?CleanupRpcContainerStorageInfo@@YAX0@Z$$T$0A@@wil@@@Z
0x18000917e  mov     edi, eax
0x180009180  test    eax, eax
0x180009182  jns     short loc_1800091AE
0x180009184  mov     rcx, [rbp+5Fh]; this
0x180009188  mov     r9d, eax; char *
0x18000918b  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180009192  mov     edx, 67Dh; void *
0x180009197  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000919c  nop
0x18000919d  lea     rcx, [rbp+57h+var_70]; struct __MIDL_CmRpc_0002 *
0x1800091a1  call    ?CleanupRpcContainerStorageInfo@@YAXPEAU__MIDL_CmRpc_0002@@@Z; CleanupRpcContainerStorageInfo(__MIDL_CmRpc_0002 *)
0x1800091a6  nop
0x1800091a7  mov     eax, edi
0x1800091a9  jmp     loc_18000923F
0x1800091ae  movaps  xmm0, [rbp+57h+var_70]
0x1800091b2  movaps  [rbp+57h+var_C0], xmm0
0x1800091b6  movaps  xmm1, [rbp+57h+var_60]
0x1800091ba  movaps  [rbp+57h+var_B0], xmm1
0x1800091be  movaps  xmm0, [rbp+57h+var_50]
0x1800091c2  movaps  [rbp+57h+var_A0], xmm0
0x1800091c6  movaps  xmm1, [rbp+57h+var_40]
0x1800091ca  movaps  [rbp+57h+var_90], xmm1
0x1800091ce  movsd   xmm0, [rbp+57h+var_30]
0x1800091d3  movsd   [rbp+57h+var_80], xmm0
0x1800091d8  mov     r8, rbx
0x1800091db  mov     rdx, rsi
0x1800091de  lea     rcx, [rbp+57h+var_C0]
0x1800091e2  call    ?ConvertToContainerStorageInfo@Client@Manager@Container@@YAJU__MIDL_CmRpc_0002@@PEAU_CMS_STORAGE_INFO@@PEAK@Z; Container::Manager::Client::ConvertToContainerStorageInfo(__MIDL_CmRpc_0002,_CMS_STORAGE_INFO *,ulong *)
0x1800091e7  mov     ebx, eax
0x1800091e9  test    eax, eax
0x1800091eb  jns     short loc_180009212
0x1800091ed  mov     rcx, [rbp+5Fh]; this
0x1800091f1  mov     r9d, eax; char *
0x1800091f4  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x1800091fb  mov     edx, 683h; void *
0x180009200  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009205  nop
0x180009206  lea     rcx, [rbp+57h+var_70]; struct __MIDL_CmRpc_0002 *
0x18000920a  call    ?CleanupRpcContainerStorageInfo@@YAXPEAU__MIDL_CmRpc_0002@@@Z; CleanupRpcContainerStorageInfo(__MIDL_CmRpc_0002 *)
0x18000920f  nop
0x180009210  jmp     short loc_18000923D
0x180009212  lea     rcx, [rbp+57h+var_70]; struct __MIDL_CmRpc_0002 *
0x180009216  call    ?CleanupRpcContainerStorageInfo@@YAXPEAU__MIDL_CmRpc_0002@@@Z; CleanupRpcContainerStorageInfo(__MIDL_CmRpc_0002 *)
0x18000921b  nop
0x18000921c  xor     eax, eax
0x18000921e  jmp     short loc_18000923F
0x180009220  mov     rcx, [rbp+5Fh]; this
0x180009224  mov     ebx, 80070057h
0x180009229  mov     r9d, ebx; char *
0x18000922c  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180009233  mov     edx, 673h; void *
0x180009238  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000923d  mov     eax, ebx
0x18000923f  mov     rcx, [rbp+57h+var_20]
0x180009243  xor     rcx, rsp; StackCookie
0x180009246  call    __security_check_cookie
0x18000924b  mov     rbx, [rsp+0F0h+arg_18]
0x180009253  add     rsp, 0E0h
0x18000925a  pop     rdi
0x18000925b  pop     rsi
0x18000925c  pop     rbp
0x18000925d  retn
```
