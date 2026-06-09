# Microsoft.Crm.Sandbox.InternalSandboxSdkClient::GetProcessName

- ea: `0x450`
- end: `0x4e6`
- name: `Microsoft.Crm.Sandbox.InternalSandboxSdkClient::GetProcessName`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1e0`

## callees

- `0xa0`
- `0xe0`
- `0x450`

## string_xrefs

- `0x4b7`: `CrmAsyncService`

## pseudocode

```c

```

## disassembly

```asm
0x450  ldarg.0
0x451  call     instance string Microsoft.Crm.Sandbox.InternalSandboxSdkClient::get_PreferredProcessName()
0x456  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x45b  brtrue.s loc_464
0x45d  ldarg.0
0x45e  call     instance string Microsoft.Crm.Sandbox.InternalSandboxSdkClient::get_PreferredProcessName()
0x463  ret
0x464  ldarg.0
0x465  call     instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles Microsoft.Crm.Sandbox.InternalSandboxSdkClient::get_ServerRole()
0x46a  stloc.0
0x46b  ldloc.0
0x46c  ldc.i4.1
0x46d  beq.s    loc_47B
0x46f  ldloc.0
0x470  ldc.i4.2
0x471  beq.s    loc_4B7
0x473  ldloc.0
0x474  ldc.i4   0x8000
0x479  bne.un.s loc_4BD
0x47b  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x480  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x485  ldc.i4.2
0x486  bne.un.s loc_4B1
0x488  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x48d  ldstr    aInvalidServerR// "Invalid server role {0} for CRM Online"
0x492  ldc.i4.1
0x493  newarr   [mscorlib]System.Object
0x498  dup
0x499  ldc.i4.0
0x49a  ldarg.0
0x49b  call     instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles Microsoft.Crm.Sandbox.InternalSandboxSdkClient::get_ServerRole()
0x4a0  box      [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles
0x4a5  stelem.ref
0x4a6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4ab  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x4b0  throw
0x4b1  ldstr    aW3wp// "w3wp"
0x4b6  ret
0x4b7  ldstr    aCrmasyncservic// "CrmAsyncService"
0x4bc  ret
0x4bd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4c2  ldstr    aInvalidServerR_0// "Invalid server role {0} chosen for retr"...
0x4c7  ldc.i4.1
0x4c8  newarr   [mscorlib]System.Object
0x4cd  dup
0x4ce  ldc.i4.0
0x4cf  ldarg.0
0x4d0  call     instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles Microsoft.Crm.Sandbox.InternalSandboxSdkClient::get_ServerRole()
0x4d5  box      [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles
0x4da  stelem.ref
0x4db  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4e0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x4e5  throw
```
