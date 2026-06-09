# NcbCCResetUninitialize

- ea: `0x180020ddc`
- end: `0x180020e77`
- name: `NcbCCResetUninitialize`
- size: `155`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002293c`
- `0x180022d28`

## callees

- `0x180009740`
- `0x18000a0a0`
- `0x180020ddc`
- `0x180026070`

## import_xrefs

- `RPCRT4!RpcServerInterfaceGroupClose` at `0x180020e17`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x180020e17`
- `RPCRT4!RpcServerInterfaceGroupDeactivate` at `0x180020dee`
- `RPCRT4!RpcServerInterfaceGroupDeactivate` at `0x180020dee`
- `BrokerLib!BrDeleteBrokerInstance` at `0x180020e40`
- `BrokerLib!BrDeleteBrokerInstance` at `0x180020e40`

## string_xrefs

- `0x180020e66`: `NcbCCResetUninitialize completed.`

## pseudocode

```c
__int64 NcbCCResetUninitialize()
{
  unsigned int v0; // eax
  __int64 v1; // rdx
  __int64 v2; // rcx
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 result; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx

  if ( g_ncbCCResetRpcInterfaceGroup )
  {
    v0 = RpcServerInterfaceGroupDeactivate(g_ncbCCResetRpcInterfaceGroup, 0);
    if ( v0 && (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        v2,
        v1,
        L"StopNcbCCResetRpcServer: RpcServerInterfaceGroupDeactivate failed",
        v0);
    v3 = RpcServerInterfaceGroupClose(g_ncbCCResetRpcInterfaceGroup);
    if ( v3 && (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v5, v4, L"StopNcbCCResetRpcServer: RpcServerInterfaceGroupClose failed", v3);
  }
  BrDeleteBrokerInstance(g_NcbCCResetBroker);
  result = CleanupAppResurrectionManager(&g_NcbCCResetAppResurrectionManager);
  g_NcbCCResetBroker = 0;
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    return McTemplateU0z_EventWriteTransfer(v8, v7, L"NcbCCResetUninitialize completed.");
  return result;
}

```

## disassembly

```asm
0x180020ddc  sub     rsp, 28h
0x180020de0  mov     rcx, cs:g_ncbCCResetRpcInterfaceGroup
0x180020de7  test    rcx, rcx
0x180020dea  jz      short loc_180020E39
0x180020dec  xor     edx, edx
0x180020dee  call    cs:__imp_RpcServerInterfaceGroupDeactivate
0x180020df4  test    eax, eax
0x180020df6  jz      short loc_180020E10
0x180020df8  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180020dff  jz      short loc_180020E10
0x180020e01  mov     r9d, eax
0x180020e04  lea     r8, aStopncbccreset; "StopNcbCCResetRpcServer: RpcServerInter"...
0x180020e0b  call    McTemplateU0zq_EventWriteTransfer
0x180020e10  mov     rcx, cs:g_ncbCCResetRpcInterfaceGroup
0x180020e17  call    cs:__imp_RpcServerInterfaceGroupClose
0x180020e1d  test    eax, eax
0x180020e1f  jz      short loc_180020E39
0x180020e21  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180020e28  jz      short loc_180020E39
0x180020e2a  mov     r9d, eax
0x180020e2d  lea     r8, aStopncbccreset_0; "StopNcbCCResetRpcServer: RpcServerInter"...
0x180020e34  call    McTemplateU0zq_EventWriteTransfer
0x180020e39  mov     rcx, cs:g_NcbCCResetBroker
0x180020e40  call    cs:__imp_BrDeleteBrokerInstance
0x180020e46  lea     rcx, g_NcbCCResetAppResurrectionManager
0x180020e4d  call    CleanupAppResurrectionManager
0x180020e52  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180020e59  mov     cs:g_NcbCCResetBroker, 0
0x180020e64  jz      short loc_180020E72
0x180020e66  lea     r8, aNcbccresetunin; "NcbCCResetUninitialize completed."
0x180020e6d  call    McTemplateU0z_EventWriteTransfer
0x180020e72  add     rsp, 28h
0x180020e76  retn
```
