# NcaRpcAPIsSecurityCallback

- ea: `0x18001b2a0`
- end: `0x18001b2a8`
- name: `NcaRpcAPIsSecurityCallback`
- size: `8`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001c4e0`

## pseudocode

```c
__int64 __fastcall NcaRpcAPIsSecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  return NcaRpcAPIsInterfaceSecurityCallback(InterfaceUuid, Context, Context);
}

```

## disassembly

```asm
0x18001b2a0  mov     r8, rdx
0x18001b2a3  jmp     NcaRpcAPIsInterfaceSecurityCallback
```
