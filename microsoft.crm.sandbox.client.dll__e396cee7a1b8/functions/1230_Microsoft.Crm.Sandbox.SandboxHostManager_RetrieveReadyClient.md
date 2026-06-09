# Microsoft.Crm.Sandbox.SandboxHostManager::RetrieveReadyClient

- ea: `0x1230`
- end: `0x12b2`
- name: `Microsoft.Crm.Sandbox.SandboxHostManager::RetrieveReadyClient`
- size: `130`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1220`
- `0x2f70`

## callees

- `0xaf0`
- `0x1230`
- `0x12c0`

## string_xrefs

- `0x123c`: `Calling RetrieveReadyClient() but SandboxHostManager has not been initialized yet, initializing now`
- `0x1259`: `Failed to initialize SandboxHostManager after RetrieveReadyClient() has been called : {0}`
- `0x1274`: `_nativeReadyClients`
- `0x1283`: `_drawbridgeReadyClients`

## pseudocode

```c

```

## disassembly

```asm
0x1230  ldsfld   bool Microsoft.Crm.Sandbox.SandboxHostManager::_initialized
0x1235  brtrue.s loc_126F
0x1237  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxHostManager::Logger
0x123c  ldstr    aCallingRetriev// "Calling RetrieveReadyClient() but Sandb"...
0x1241  ldc.i4.0
0x1242  newarr   [mscorlib]System.Object
0x1247  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x124c  call     void Microsoft.Crm.Sandbox.SandboxHostManager::Initialize()
0x1251  leave.s  loc_126F
0x1253  stloc.0
0x1254  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxHostManager::Logger
0x1259  ldstr    aFailedToInitia// "Failed to initialize SandboxHostManager"...
0x125e  ldc.i4.1
0x125f  newarr   [mscorlib]System.Object
0x1264  dup
0x1265  ldc.i4.0
0x1266  ldloc.0
0x1267  stelem.ref
0x1268  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogError(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x126d  rethrow
0x126f  ldsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_nativeReadyClients
0x1274  ldstr    aNativereadycli// "_nativeReadyClients"
0x1279  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x127e  ldsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_drawbridgeReadyClients
0x1283  ldstr    aDrawbridgeread// "_drawbridgeReadyClients"
0x1288  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x128d  ldarg.0
0x128e  brfalse.s loc_12A1
0x1290  ldarg.0
0x1291  ldsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_drawbridgeReadyClients
0x1296  ldsflda  int32 Microsoft.Crm.Sandbox.SandboxHostManager::_nextDrawbridgeClientIndex
0x129b  call     class Microsoft.Crm.Sandbox.SandboxClient Microsoft.Crm.Sandbox.SandboxHostManager::RetrieveReadyClientInternal(bool useDrawBridgeIsolation, class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> readyClients, int32& nextClientIndex)
0x12a0  ret
0x12a1  ldarg.0
0x12a2  ldsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_nativeReadyClients
0x12a7  ldsflda  int32 Microsoft.Crm.Sandbox.SandboxHostManager::_nextNativeClientIndex
0x12ac  call     class Microsoft.Crm.Sandbox.SandboxClient Microsoft.Crm.Sandbox.SandboxHostManager::RetrieveReadyClientInternal(bool useDrawBridgeIsolation, class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> readyClients, int32& nextClientIndex)
0x12b1  ret
```
