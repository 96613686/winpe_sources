# ??$InvokeStubFunction@P6AJPEAXPEAU__MIDL_CmRpc_0002@@@ZPEAXPEAV?$unique_struct@U__MIDL_CmRpc_0002@@$$A6AXPEAU1@@_E$1?CleanupRpcContainerStorageInfo@@YAX0@Z$$T$0A@@wil@@@Rpc@Manager@Container@@YAJP6AJPEAXPEAU__MIDL_CmRpc_0002@@@Z$$QEAPEAX$$QEAPEAV?$unique_struct@U__MIDL_CmRpc_0002@@$$A6AXPEAU1@@_E$1?CleanupRpcContainerStorageInfo@@YAX0@Z$$T$0A@@wil@@@Z

- ea: `0x180002be8`
- end: `0x180002c4a`
- name: `??$InvokeStubFunction@P6AJPEAXPEAU__MIDL_CmRpc_0002@@@ZPEAXPEAV?$unique_struct@U__MIDL_CmRpc_0002@@$$A6AXPEAU1@@_E$1?CleanupRpcContainerStorageInfo@@YAX0@Z$$T$0A@@wil@@@Rpc@Manager@Container@@YAJP6AJPEAXPEAU__MIDL_CmRpc_0002@@@Z$$QEAPEAX$$QEAPEAV?$unique_struct@U__MIDL_CmRpc_0002@@$$A6AXPEAU1@@_E$1?CleanupRpcContainerStorageInfo@@YAX0@Z$$T$0A@@wil@@@Z`
- size: `98`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009110`
- `0x18000c420`

## callees

- `0x180002be8`
- `0x1800066e4`
- `0x18000672c`
- `0x18000e6bc`

## string_xrefs

- `0x180002c0a`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180002c2f`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall ___InvokeStubFunction_P6AJPEAXPEAU__MIDL_CmRpc_0002___ZPEAXPEAV__unique_struct_U__MIDL_CmRpc_0002____A6AXPEAU1___E_1_CleanupRpcContainerStorageInfo__YAX0_Z__T_0A__wil___Rpc_Manager_Container__YAJP6AJPEAXPEAU__MIDL_CmRpc_0002___Z__QEAPEAX__QEAPEAV__unique_struct_U__MIDL_CmRpc_0002____A6AXPEAU1___E_1_CleanupRpcContainerStorageInfo__YAX0_Z__T_0A__wil___Z(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  int InformationContainerStorage; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  InformationContainerStorage = CmsRpcClt_QueryInformationContainerStorage(*a2, *a3);
  v4 = InformationContainerStorage;
  if ( InformationContainerStorage >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)InformationContainerStorage,
    v6);
  return v4;
}

```

## disassembly

```asm
0x180002be8  push    rbx; int
0x180002bea  sub     rsp, 20h
0x180002bee  mov     rax, rdx
0x180002bf1  mov     rdx, [r8]
0x180002bf4  mov     rcx, [rax]
0x180002bf7  call    CmsRpcClt_QueryInformationContainerStorage
0x180002bfc  mov     ebx, eax
0x180002bfe  test    eax, eax
0x180002c00  jns     short loc_180002C1F
0x180002c02  mov     rcx, [rsp+28h]; this
0x180002c07  mov     r9d, eax; char *
0x180002c0a  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002c11  mov     edx, 56h ; 'V'; void *
0x180002c16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002c1b  mov     eax, ebx
0x180002c1d  jmp     short loc_180002C44
0x180002c1f  xor     eax, eax
0x180002c21  jmp     short loc_180002C44
0x180002c23  test    eax, eax
0x180002c25  jz      short loc_180002C42
0x180002c27  mov     rcx, [rsp+28h]; this
0x180002c2c  mov     r9d, eax; char *
0x180002c2f  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002c36  mov     edx, 5Ch ; '\'; void *
0x180002c3b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180002c40  jmp     short loc_180002C44
0x180002c42  xor     eax, eax
0x180002c44  add     rsp, 20h
0x180002c48  pop     rbx
0x180002c49  retn
```
