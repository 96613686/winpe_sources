# ??$InvokeStubFunction@P6AJPEAXPEAU_GUID@@PEAU__MIDL_CmRpc_0004@@@ZPEAXAEAPEAU1@PEAV?$unique_struct@U__MIDL_CmRpc_0004@@$$A6AXPEAU1@@_E$1?CleanupRpcNetworkInfo@@YAX0@Z$$T$0A@@wil@@@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_GUID@@PEAU__MIDL_CmRpc_0004@@@Z$$QEAPEAXAEAPEAU3@$$QEAPEAV?$unique_struct@U__MIDL_CmRpc_0004@@$$A6AXPEAU1@@_E$1?CleanupRpcNetworkInfo@@YAX0@Z$$T$0A@@wil@@@Z

- ea: `0x180002884`
- end: `0x1800028ec`
- name: `??$InvokeStubFunction@P6AJPEAXPEAU_GUID@@PEAU__MIDL_CmRpc_0004@@@ZPEAXAEAPEAU1@PEAV?$unique_struct@U__MIDL_CmRpc_0004@@$$A6AXPEAU1@@_E$1?CleanupRpcNetworkInfo@@YAX0@Z$$T$0A@@wil@@@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_GUID@@PEAU__MIDL_CmRpc_0004@@@Z$$QEAPEAXAEAPEAU3@$$QEAPEAV?$unique_struct@U__MIDL_CmRpc_0004@@$$A6AXPEAU1@@_E$1?CleanupRpcNetworkInfo@@YAX0@Z$$T$0A@@wil@@@Z`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008fe0`

## callees

- `0x180002884`
- `0x1800066e4`
- `0x18000672c`
- `0x18000e714`

## string_xrefs

- `0x1800028ac`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x1800028d1`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall ___InvokeStubFunction_P6AJPEAXPEAU_GUID__PEAU__MIDL_CmRpc_0004___ZPEAXAEAPEAU1_PEAV__unique_struct_U__MIDL_CmRpc_0004____A6AXPEAU1___E_1_CleanupRpcNetworkInfo__YAX0_Z__T_0A__wil___Rpc_Manager_Container__YAJP6AJPEAXPEAU_GUID__PEAU__MIDL_CmRpc_0004___Z__QEAPEAXAEAPEAU3___QEAPEAV__unique_struct_U__MIDL_CmRpc_0004____A6AXPEAU1___E_1_CleanupRpcNetworkInfo__YAX0_Z__T_0A__wil___Z(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4)
{
  int InformationNetwork; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  InformationNetwork = CmsRpcClt_QueryInformationNetwork(*a2, *a3, *a4);
  v5 = InformationNetwork;
  if ( InformationNetwork >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)InformationNetwork,
    v7);
  return v5;
}

```

## disassembly

```asm
0x180002884  push    rbx; int
0x180002886  sub     rsp, 20h
0x18000288a  mov     rax, r8
0x18000288d  mov     r10, rdx
0x180002890  mov     r8, [r9]
0x180002893  mov     rdx, [rax]
0x180002896  mov     rcx, [r10]
0x180002899  call    CmsRpcClt_QueryInformationNetwork
0x18000289e  mov     ebx, eax
0x1800028a0  test    eax, eax
0x1800028a2  jns     short loc_1800028C1
0x1800028a4  mov     rcx, [rsp+28h]; this
0x1800028a9  mov     r9d, eax; char *
0x1800028ac  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1800028b3  mov     edx, 56h ; 'V'; void *
0x1800028b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800028bd  mov     eax, ebx
0x1800028bf  jmp     short loc_1800028E6
0x1800028c1  xor     eax, eax
0x1800028c3  jmp     short loc_1800028E6
0x1800028c5  test    eax, eax
0x1800028c7  jz      short loc_1800028E4
0x1800028c9  mov     rcx, [rsp+28h]; this
0x1800028ce  mov     r9d, eax; char *
0x1800028d1  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1800028d8  mov     edx, 5Ch ; '\'; void *
0x1800028dd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800028e2  jmp     short loc_1800028E6
0x1800028e4  xor     eax, eax
0x1800028e6  add     rsp, 20h
0x1800028ea  pop     rbx
0x1800028eb  retn
```
