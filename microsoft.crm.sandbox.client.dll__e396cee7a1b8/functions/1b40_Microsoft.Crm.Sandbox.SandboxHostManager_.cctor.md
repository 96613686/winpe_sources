# Microsoft.Crm.Sandbox.SandboxHostManager::.cctor

- ea: `0x1b40`
- end: `0x1bd4`
- name: `Microsoft.Crm.Sandbox.SandboxHostManager::.cctor`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## string_xrefs

- `0x1bc8`: `PluginSecureStore`

## pseudocode

```c

```

## disassembly

```asm
0x1b40  call     class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILoggerFactory [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmLoggerFactory::get_LoggerFactory()
0x1b45  ldtoken  Microsoft.Crm.Sandbox.SandboxHostManager
0x1b4a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b4f  callvirt instance string [mscorlib]System.Type::get_Namespace()
0x1b54  callvirt instance class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILoggerFactory::CreateLogger(string)
0x1b59  stsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxHostManager::Logger
0x1b5e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor()
0x1b63  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Sandbox.SandboxHostManager::_sandboxAdditionalInfo
0x1b68  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxHostInfo>::.ctor()
0x1b6d  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxHostInfo> Microsoft.Crm.Sandbox.SandboxHostManager::_hostNames
0x1b72  newobj   instance void class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::.ctor()
0x1b77  stsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_nativeReadyClients
0x1b7c  newobj   instance void class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::.ctor()
0x1b81  stsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_drawbridgeReadyClients
0x1b86  newobj   instance void class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::.ctor()
0x1b8b  stsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_nativePendingClients
0x1b90  newobj   instance void class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::.ctor()
0x1b95  stsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_drawbridgePendingClients
0x1b9a  newobj   instance void [System.Core]System.Threading.ReaderWriterLockSlim::.ctor()
0x1b9f  stsfld   class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxHostManager::_listsLock
0x1ba4  newobj   instance void [mscorlib]System.Object::.ctor()
0x1ba9  stsfld   object Microsoft.Crm.Sandbox.SandboxHostManager::_intializeLock
0x1bae  newobj   instance void [mscorlib]System.Object::.ctor()
0x1bb3  stsfld   object Microsoft.Crm.Sandbox.SandboxHostManager::_processingLock
0x1bb8  ldc.i4.2
0x1bb9  newarr   [mscorlib]System.String
0x1bbe  dup
0x1bbf  ldc.i4.0
0x1bc0  ldstr    aSandboxworkerp// "SandboxWorkerProcessAutoDump"
0x1bc5  stelem.ref
0x1bc6  dup
0x1bc7  ldc.i4.1
0x1bc8  ldstr    aPluginsecurest// "PluginSecureStore"
0x1bcd  stelem.ref
0x1bce  stsfld   string[] Microsoft.Crm.Sandbox.SandboxHostManager::_fcbKeyNames
0x1bd3  ret
```
