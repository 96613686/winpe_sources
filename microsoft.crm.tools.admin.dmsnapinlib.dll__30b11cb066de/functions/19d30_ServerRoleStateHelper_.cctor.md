# ServerRoleStateHelper::.cctor

- ea: `0x19d30`
- end: `0x19f83`
- name: `ServerRoleStateHelper::.cctor`
- size: `595`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1a500`

## string_xrefs

- `0x19f50`: `MSCRMAsyncService`
- `0x19f64`: `MSCRMAsyncService`
- `0x19f40`: `MSCRMUnzipService`
- `0x19f78`: `MSCRMSandboxService`

## pseudocode

```c

```

## disassembly

```asm
0x19d30  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerState, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>>::.ctor()
0x19d35  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerState, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>> ServerRoleStateHelper::dictSetStatusActions
0x19d3a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string>::.ctor()
0x19d3f  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string> ServerRoleStateHelper::dictServiceNames
0x19d44  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>::.ctor()
0x19d49  stloc.0
0x19d4a  ldloc.0
0x19d4b  ldc.i4.2
0x19d4c  ldnull
0x19d4d  ldftn    bool ServerRoleStateHelper::WindowsAsyncServiceDisable(string serverName, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles serverRole)
0x19d53  newobj   instance void SetStateAction::.ctor(object object, native int method)
0x19d58  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>::Add(var<u1>, !!T0)
0x19d5d  ldloc.0
0x19d5e  ldc.i4   0x40000000
0x19d63  ldnull
0x19d64  ldftn    bool ServerRoleStateHelper::WindowsServiceDisable(string serverName, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles serverRole)
0x19d6a  newobj   instance void SetStateAction::.ctor(object object, native int method)
0x19d6f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>::Add(var<u1>, !!T0)
0x19d74  ldloc.0
0x19d75  ldc.i4   0x1000000
0x19d7a  ldnull
0x19d7b  ldftn    bool ServerRoleStateHelper::WindowsServiceDisable(string serverName, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles serverRole)
0x19d81  newobj   instance void SetStateAction::.ctor(object object, native int method)
0x19d86  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>::Add(var<u1>, !!T0)
0x19d8b  ldloc.0
0x19d8c  ldc.i4.1
0x19d8d  ldnull
0x19d8e  ldftn    bool ServerRoleStateHelper::AppServerStop(string serverName, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles serverRole)
0x19d94  newobj   instance void SetStateAction::.ctor(object object, native int method)
0x19d99  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>::Add(var<u1>, !!T0)
0x19d9e  ldloc.0
0x19d9f  ldc.i4.8
0x19da0  ldnull
0x19da1  ldftn    bool ServerRoleStateHelper::WebsiteStop(string serverName, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles serverRole)
0x19da7  newobj   instance void SetStateAction::.ctor(object object, native int method)
0x19dac  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>::Add(var<u1>, !!T0)
0x19db1  ldloc.0
0x19db2  ldc.i4   0x8000
0x19db7  ldnull
0x19db8  ldftn    bool ServerRoleStateHelper::WebsiteStop(string serverName, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles serverRole)
0x19dbe  newobj   instance void SetStateAction::.ctor(object object, native int method)
0x19dc3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>::Add(var<u1>, !!T0)
0x19dc8  ldloc.0
0x19dc9  ldc.i4   0x200000
0x19dce  ldnull
0x19dcf  ldftn    bool ServerRoleStateHelper::WebsiteStop(string serverName, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles serverRole)
0x19dd5  newobj   instance void SetStateAction::.ctor(object object, native int method)
0x19dda  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>::Add(var<u1>, !!T0)
0x19ddf  ldloc.0
0x19de0  ldc.i4   0x40000
0x19de5  ldnull
0x19de6  ldftn    bool ServerRoleStateHelper::WebsiteStop(string serverName, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles serverRole)
0x19dec  newobj   instance void SetStateAction::.ctor(object object, native int method)
0x19df1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>::Add(var<u1>, !!T0)
0x19df6  ldloc.0
0x19df7  ldc.i4.0
0x19df8  ldnull
0x19df9  ldftn    bool ServerRoleStateHelper::NoActionSetStatus(string serverName, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles serverRole)
0x19dff  newobj   instance void SetStateAction::.ctor(object object, native int method)
0x19e04  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>::Add(var<u1>, !!T0)
0x19e09  ldloc.0
0x19e0a  ldc.i4   0x100
0x19e0f  ldnull
0x19e10  ldftn    bool ServerRoleStateHelper::NoActionSetStatus(string serverName, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles serverRole)
0x19e16  newobj   instance void SetStateAction::.ctor(object object, native int method)
0x19e1b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>::Add(var<u1>, !!T0)
0x19e20  ldloc.0
0x19e21  ldc.i4.4
0x19e22  ldnull
0x19e23  ldftn    bool ServerRoleStateHelper::NoActionSetStatus(string serverName, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles serverRole)
0x19e29  newobj   instance void SetStateAction::.ctor(object object, native int method)
0x19e2e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>::Add(var<u1>, !!T0)
0x19e33  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerState, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>> ServerRoleStateHelper::dictSetStatusActions
0x19e38  ldc.i4.0
0x19e39  ldloc.0
0x19e3a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerState, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>>::Add(var<u1>, !!T0)
0x19e3f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>::.ctor()
0x19e44  stloc.1
0x19e45  ldloc.1
0x19e46  ldc.i4.2
0x19e47  ldnull
0x19e48  ldftn    bool ServerRoleStateHelper::WindowsAsyncServiceEnable(string serverName, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles serverRole)
0x19e4e  newobj   instance void SetStateAction::.ctor(object object, native int method)
0x19e53  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>::Add(var<u1>, !!T0)
0x19e58  ldloc.1
0x19e59  ldc.i4   0x40000000
0x19e5e  ldnull
0x19e5f  ldftn    bool ServerRoleStateHelper::WindowsServiceEnable(string serverName, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles serverRole)
0x19e65  newobj   instance void SetStateAction::.ctor(object object, native int method)
0x19e6a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>::Add(var<u1>, !!T0)
0x19e6f  ldloc.1
0x19e70  ldc.i4   0x1000000
0x19e75  ldnull
0x19e76  ldftn    bool ServerRoleStateHelper::WindowsServiceEnable(string serverName, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles serverRole)
0x19e7c  newobj   instance void SetStateAction::.ctor(object object, native int method)
0x19e81  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>::Add(var<u1>, !!T0)
0x19e86  ldloc.1
0x19e87  ldc.i4.1
0x19e88  ldnull
0x19e89  ldftn    bool ServerRoleStateHelper::AppServerStart(string serverName, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles serverRole)
0x19e8f  newobj   instance void SetStateAction::.ctor(object object, native int method)
0x19e94  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>::Add(var<u1>, !!T0)
0x19e99  ldloc.1
0x19e9a  ldc.i4.8
0x19e9b  ldnull
0x19e9c  ldftn    bool ServerRoleStateHelper::WebsiteStart(string serverName, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles serverRole)
0x19ea2  newobj   instance void SetStateAction::.ctor(object object, native int method)
0x19ea7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>::Add(var<u1>, !!T0)
0x19eac  ldloc.1
0x19ead  ldc.i4   0x8000
0x19eb2  ldnull
0x19eb3  ldftn    bool ServerRoleStateHelper::WebsiteStart(string serverName, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles serverRole)
0x19eb9  newobj   instance void SetStateAction::.ctor(object object, native int method)
0x19ebe  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>::Add(var<u1>, !!T0)
0x19ec3  ldloc.1
0x19ec4  ldc.i4   0x200000
0x19ec9  ldnull
0x19eca  ldftn    bool ServerRoleStateHelper::WebsiteStart(string serverName, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles serverRole)
0x19ed0  newobj   instance void SetStateAction::.ctor(object object, native int method)
0x19ed5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>::Add(var<u1>, !!T0)
0x19eda  ldloc.1
0x19edb  ldc.i4   0x40000
0x19ee0  ldnull
0x19ee1  ldftn    bool ServerRoleStateHelper::WebsiteStart(string serverName, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles serverRole)
0x19ee7  newobj   instance void SetStateAction::.ctor(object object, native int method)
0x19eec  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>::Add(var<u1>, !!T0)
0x19ef1  ldloc.1
0x19ef2  ldc.i4.0
0x19ef3  ldnull
0x19ef4  ldftn    bool ServerRoleStateHelper::NoActionSetStatus(string serverName, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles serverRole)
0x19efa  newobj   instance void SetStateAction::.ctor(object object, native int method)
0x19eff  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>::Add(var<u1>, !!T0)
0x19f04  ldloc.1
0x19f05  ldc.i4   0x100
0x19f0a  ldnull
0x19f0b  ldftn    bool ServerRoleStateHelper::NoActionSetStatus(string serverName, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles serverRole)
0x19f11  newobj   instance void SetStateAction::.ctor(object object, native int method)
0x19f16  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>::Add(var<u1>, !!T0)
0x19f1b  ldloc.1
0x19f1c  ldc.i4.4
0x19f1d  ldnull
0x19f1e  ldftn    bool ServerRoleStateHelper::NoActionSetStatus(string serverName, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles serverRole)
0x19f24  newobj   instance void SetStateAction::.ctor(object object, native int method)
0x19f29  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>::Add(var<u1>, !!T0)
0x19f2e  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerState, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>> ServerRoleStateHelper::dictSetStatusActions
0x19f33  ldc.i4.1
0x19f34  ldloc.1
0x19f35  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerState, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, class SetStateAction>>::Add(var<u1>, !!T0)
0x19f3a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string> ServerRoleStateHelper::dictServiceNames
0x19f3f  ldc.i4.1
0x19f40  ldstr    aMscrmunzipserv// "MSCRMUnzipService"
0x19f45  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string>::Add(var<u1>, !!T0)
0x19f4a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string> ServerRoleStateHelper::dictServiceNames
0x19f4f  ldc.i4.2
0x19f50  ldstr    aMscrmasyncserv// "MSCRMAsyncService"
0x19f55  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string>::Add(var<u1>, !!T0)
0x19f5a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string> ServerRoleStateHelper::dictServiceNames
0x19f5f  ldc.i4   0x40000000
0x19f64  ldstr    aMscrmasyncserv// "MSCRMAsyncService"
0x19f69  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string>::Add(var<u1>, !!T0)
0x19f6e  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string> ServerRoleStateHelper::dictServiceNames
0x19f73  ldc.i4   0x1000000
0x19f78  ldstr    aMscrmsandboxse// "MSCRMSandboxService"
0x19f7d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles, string>::Add(var<u1>, !!T0)
0x19f82  ret
```
