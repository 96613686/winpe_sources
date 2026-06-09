# Microsoft.Xrm.Sdk.Client.ChannelExtensions::Close

- ea: `0x1b320`
- end: `0x1b369`
- name: `Microsoft.Xrm.Sdk.Client.ChannelExtensions::Close`
- size: `73`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x172b0`
- `0x1b050`
- `0x1b070`
- `0x1b610`
- `0x1be80`
- `0x1c1e0`

## callees

- `0x1b320`

## pseudocode

```c

```

## disassembly

```asm
0x1b320  ldarg.0
0x1b321  brtrue.s loc_1B324
0x1b323  ret
0x1b324  nop
0x1b325  ldarg.0
0x1b326  callvirt instance valuetype [System.ServiceModel]System.ServiceModel.CommunicationState [System.ServiceModel]System.ServiceModel.ICommunicationObject::get_State()
0x1b32b  stloc.0
0x1b32c  ldc.i4.5
0x1b32d  ldloc.0
0x1b32e  bne.un.s loc_1B338
0x1b330  ldarg.0
0x1b331  callvirt instance void [System.ServiceModel]System.ServiceModel.ICommunicationObject::Abort()
0x1b336  br.s     loc_1B346
0x1b338  ldloc.0
0x1b339  ldc.i4.3
0x1b33a  beq.s    loc_1B346
0x1b33c  ldloc.0
0x1b33d  ldc.i4.4
0x1b33e  beq.s    loc_1B346
0x1b340  ldarg.0
0x1b341  callvirt instance void [System.ServiceModel]System.ServiceModel.ICommunicationObject::Close()
0x1b346  leave.s  loc_1B368
0x1b348  pop
0x1b349  ldarg.0
0x1b34a  callvirt instance void [System.ServiceModel]System.ServiceModel.ICommunicationObject::Abort()
0x1b34f  leave.s  loc_1B368
0x1b351  pop
0x1b352  ldarg.0
0x1b353  callvirt instance void [System.ServiceModel]System.ServiceModel.ICommunicationObject::Abort()
0x1b358  leave.s  loc_1B368
0x1b35a  pop
0x1b35b  ldarg.0
0x1b35c  callvirt instance void [System.ServiceModel]System.ServiceModel.ICommunicationObject::Abort()
0x1b361  ldarg.1
0x1b362  brfalse.s loc_1B366
0x1b364  rethrow
0x1b366  leave.s  loc_1B368
0x1b368  ret
```
