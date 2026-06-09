# Microsoft.Crm.ObjectModel.EntityDataProviderService::.ctor

- ea: `0x73e30`
- end: `0x73ec0`
- name: `Microsoft.Crm.ObjectModel.EntityDataProviderService::.ctor`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x73e60`: `Create`
- `0x73e9c`: `Update`
- `0x73eb0`: `Delete`
- `0x73e65`: `createplugin`
- `0x73e79`: `retrieveplugin`
- `0x73e8d`: `retrievemultipleplugin`
- `0x73ea1`: `updateplugin`
- `0x73eb5`: `deleteplugin`

## pseudocode

```c

```

## disassembly

```asm
0x73e30  ldarg.0
0x73e31  ldstr    aC191997900214f// "c1919979-0021-4f11-a587-a8f904bdfdf9"
0x73e36  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x73e3b  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.EntityDataProviderService::DefaultVirtualEntityPluginId
0x73e40  ldarg.0
0x73e41  ldstr    aDe0cb8f9208842// "DE0CB8F9-2088-42BE-BE6A-B82DE15D9938"
0x73e46  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x73e4b  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.EntityDataProviderService::prvReadEntityDataProvider
0x73e50  ldarg.0
0x73e51  ldstr    aEntitydataprov// "EntityDataProvider"
0x73e56  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::.ctor(string)
0x73e5b  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.ObjectModel.EntityDataProviderService::ProviderColumnToMessageMapping
0x73e60  ldstr    aCreate// "Create"
0x73e65  ldstr    aCreateplugin// "createplugin"
0x73e6a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x73e6f  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.ObjectModel.EntityDataProviderService::ProviderColumnToMessageMapping
0x73e74  ldstr    aRetrieve// "Retrieve"
0x73e79  ldstr    aRetrieveplugin// "retrieveplugin"
0x73e7e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x73e83  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.ObjectModel.EntityDataProviderService::ProviderColumnToMessageMapping
0x73e88  ldstr    aRetrievemultip// "RetrieveMultiple"
0x73e8d  ldstr    aRetrievemultip_1// "retrievemultipleplugin"
0x73e92  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x73e97  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.ObjectModel.EntityDataProviderService::ProviderColumnToMessageMapping
0x73e9c  ldstr    aUpdate// "Update"
0x73ea1  ldstr    aUpdateplugin// "updateplugin"
0x73ea6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x73eab  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.ObjectModel.EntityDataProviderService::ProviderColumnToMessageMapping
0x73eb0  ldstr    aDelete// "Delete"
0x73eb5  ldstr    aDeleteplugin// "deleteplugin"
0x73eba  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x73ebf  ret
```
