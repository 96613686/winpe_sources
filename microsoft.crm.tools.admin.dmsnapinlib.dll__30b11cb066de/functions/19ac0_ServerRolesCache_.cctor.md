# ServerRolesCache::.cctor

- ea: `0x19ac0`
- end: `0x19c14`
- name: `ServerRolesCache::.cctor`
- size: `340`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x22e0`

## string_xrefs

- `0x19b3b`: `ServerState.ServiceName.Async`
- `0x19b76`: `ServerState.ServiceName.Async`
- `0x19b4e`: `ServerState.ServiceName.Async.Maintenance`
- `0x19b9e`: `ServerState.ServiceName.Sandbox`
- `0x19bc2`: `ServerState.ServiceName.Unzip`
- `0x19bd5`: `ServerState.ServiceName.Website`
- `0x19bfd`: `ServerState.ServiceName.Website`

## pseudocode

```c

```

## disassembly

```asm
0x19ac0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string>::.ctor()
0x19ac5  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string> ServerRolesCache::_serverRolesToDisplayNameMap
0x19aca  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string> ServerRolesCache::_serverRolesToDisplayNameMap
0x19acf  ldc.i4   0x100
0x19ad4  ldstr    aServerrolesDis// "ServerRoles.Display.SqlServer"
0x19ad9  ldc.i4.0
0x19ada  newarr   [mscorlib]System.Object
0x19adf  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x19ae4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string>::Add(var<u1>, !!T0)
0x19ae9  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string> ServerRolesCache::_serverRolesToDisplayNameMap
0x19aee  ldc.i4.4
0x19aef  ldstr    aServerrolesDis_0// "ServerRoles.Display.SrsDataConnector"
0x19af4  ldc.i4.0
0x19af5  newarr   [mscorlib]System.Object
0x19afa  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x19aff  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string>::Add(var<u1>, !!T0)
0x19b04  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string> ServerRolesCache::_serverRolesToDisplayNameMap
0x19b09  ldc.i4   0x524800B
0x19b0e  ldstr    aServerrolesDis_1// "ServerRoles.Display.V5FullServer"
0x19b13  ldc.i4.0
0x19b14  newarr   [mscorlib]System.Object
0x19b19  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x19b1e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string>::Add(var<u1>, !!T0)
0x19b23  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string[]>::.ctor()
0x19b28  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string[]> ServerRolesCache::_serverRolesToServiceNamesMap
0x19b2d  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string[]> ServerRolesCache::_serverRolesToServiceNamesMap
0x19b32  ldc.i4.2
0x19b33  ldc.i4.2
0x19b34  newarr   [mscorlib]System.String
0x19b39  dup
0x19b3a  ldc.i4.0
0x19b3b  ldstr    aServerstateSer// "ServerState.ServiceName.Async"
0x19b40  ldc.i4.0
0x19b41  newarr   [mscorlib]System.Object
0x19b46  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x19b4b  stelem.ref
0x19b4c  dup
0x19b4d  ldc.i4.1
0x19b4e  ldstr    aServerstateSer_0// "ServerState.ServiceName.Async.Maintenan"...
0x19b53  ldc.i4.0
0x19b54  newarr   [mscorlib]System.Object
0x19b59  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x19b5e  stelem.ref
0x19b5f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string[]>::Add(var<u1>, !!T0)
0x19b64  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string[]> ServerRolesCache::_serverRolesToServiceNamesMap
0x19b69  ldc.i4   0x40000000
0x19b6e  ldc.i4.1
0x19b6f  newarr   [mscorlib]System.String
0x19b74  dup
0x19b75  ldc.i4.0
0x19b76  ldstr    aServerstateSer// "ServerState.ServiceName.Async"
0x19b7b  ldc.i4.0
0x19b7c  newarr   [mscorlib]System.Object
0x19b81  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x19b86  stelem.ref
0x19b87  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string[]>::Add(var<u1>, !!T0)
0x19b8c  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string[]> ServerRolesCache::_serverRolesToServiceNamesMap
0x19b91  ldc.i4   0x1000000
0x19b96  ldc.i4.1
0x19b97  newarr   [mscorlib]System.String
0x19b9c  dup
0x19b9d  ldc.i4.0
0x19b9e  ldstr    aServerstateSer_1// "ServerState.ServiceName.Sandbox"
0x19ba3  ldc.i4.0
0x19ba4  newarr   [mscorlib]System.Object
0x19ba9  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x19bae  stelem.ref
0x19baf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string[]>::Add(var<u1>, !!T0)
0x19bb4  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string[]> ServerRolesCache::_serverRolesToServiceNamesMap
0x19bb9  ldc.i4.1
0x19bba  ldc.i4.2
0x19bbb  newarr   [mscorlib]System.String
0x19bc0  dup
0x19bc1  ldc.i4.0
0x19bc2  ldstr    aServerstateSer_2// "ServerState.ServiceName.Unzip"
0x19bc7  ldc.i4.0
0x19bc8  newarr   [mscorlib]System.Object
0x19bcd  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x19bd2  stelem.ref
0x19bd3  dup
0x19bd4  ldc.i4.1
0x19bd5  ldstr    aServerstateSer_3// "ServerState.ServiceName.Website"
0x19bda  ldc.i4.0
0x19bdb  newarr   [mscorlib]System.Object
0x19be0  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x19be5  stelem.ref
0x19be6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string[]>::Add(var<u1>, !!T0)
0x19beb  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string[]> ServerRolesCache::_serverRolesToServiceNamesMap
0x19bf0  ldc.i4   0x248008
0x19bf5  ldc.i4.1
0x19bf6  newarr   [mscorlib]System.String
0x19bfb  dup
0x19bfc  ldc.i4.0
0x19bfd  ldstr    aServerstateSer_3// "ServerState.ServiceName.Website"
0x19c02  ldc.i4.0
0x19c03  newarr   [mscorlib]System.Object
0x19c08  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x19c0d  stelem.ref
0x19c0e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string[]>::Add(var<u1>, !!T0)
0x19c13  ret
```
