# ??$InvokeStubFunction@P6AJPEAXPEAU__MIDL_CmRpc_0005@@@ZPEAXPEAV?$unique_struct@U__MIDL_CmRpc_0005@@$$A6AXPEAU1@@_E$1?CleanupRpcLayerInfo@@YAX0@Z$$T$0A@@wil@@@Rpc@Manager@Container@@YAJP6AJPEAXPEAU__MIDL_CmRpc_0005@@@Z$$QEAPEAX$$QEAPEAV?$unique_struct@U__MIDL_CmRpc_0005@@$$A6AXPEAU1@@_E$1?CleanupRpcLayerInfo@@YAX0@Z$$T$0A@@wil@@@Z

- ea: `0x180002c50`
- end: `0x180002cb2`
- name: `??$InvokeStubFunction@P6AJPEAXPEAU__MIDL_CmRpc_0005@@@ZPEAXPEAV?$unique_struct@U__MIDL_CmRpc_0005@@$$A6AXPEAU1@@_E$1?CleanupRpcLayerInfo@@YAX0@Z$$T$0A@@wil@@@Rpc@Manager@Container@@YAJP6AJPEAXPEAU__MIDL_CmRpc_0005@@@Z$$QEAPEAX$$QEAPEAV?$unique_struct@U__MIDL_CmRpc_0005@@$$A6AXPEAU1@@_E$1?CleanupRpcLayerInfo@@YAX0@Z$$T$0A@@wil@@@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008e90`

## callees

- `0x180002c50`
- `0x1800066e4`
- `0x18000672c`
- `0x18000e6e8`

## string_xrefs

- `0x180002c72`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180002c97`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
__int64 __fastcall ___InvokeStubFunction_P6AJPEAXPEAU__MIDL_CmRpc_0005___ZPEAXPEAV__unique_struct_U__MIDL_CmRpc_0005____A6AXPEAU1___E_1_CleanupRpcLayerInfo__YAX0_Z__T_0A__wil___Rpc_Manager_Container__YAJP6AJPEAXPEAU__MIDL_CmRpc_0005___Z__QEAPEAX__QEAPEAV__unique_struct_U__MIDL_CmRpc_0005____A6AXPEAU1___E_1_CleanupRpcLayerInfo__YAX0_Z__T_0A__wil___Z(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  int InformationLayer; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  InformationLayer = CmsRpcClt_QueryInformationLayer(*a2, *a3);
  v4 = InformationLayer;
  if ( InformationLayer >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)InformationLayer,
    v6);
  return v4;
}

```

## disassembly

```asm
0x180002c50  push    rbx; int
0x180002c52  sub     rsp, 20h
0x180002c56  mov     rax, rdx
0x180002c59  mov     rdx, [r8]
0x180002c5c  mov     rcx, [rax]
0x180002c5f  call    CmsRpcClt_QueryInformationLayer
0x180002c64  mov     ebx, eax
0x180002c66  test    eax, eax
0x180002c68  jns     short loc_180002C87
0x180002c6a  mov     rcx, [rsp+28h]; this
0x180002c6f  mov     r9d, eax; char *
0x180002c72  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002c79  mov     edx, 56h ; 'V'; void *
0x180002c7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002c83  mov     eax, ebx
0x180002c85  jmp     short loc_180002CAC
0x180002c87  xor     eax, eax
0x180002c89  jmp     short loc_180002CAC
0x180002c8b  test    eax, eax
0x180002c8d  jz      short loc_180002CAA
0x180002c8f  mov     rcx, [rsp+28h]; this
0x180002c94  mov     r9d, eax; char *
0x180002c97  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180002c9e  mov     edx, 5Ch ; '\'; void *
0x180002ca3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180002ca8  jmp     short loc_180002CAC
0x180002caa  xor     eax, eax
0x180002cac  add     rsp, 20h
0x180002cb0  pop     rbx
0x180002cb1  retn
```
