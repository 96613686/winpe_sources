# Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::HandleMetadataRequest

- ea: `0x3d60`
- end: `0x3de0`
- name: `Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::HandleMetadataRequest`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xfd80`

## callees

- `0x3d60`
- `0x83b0`
- `0xfe30`
- `0x10140`

## string_xrefs

- `0x3d83`: `Microsoft.Crm.SdkTypeProxy.Metadata.MetadataServiceRequest, Microsoft.Crm.SdkTypeProxy, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35`
- `0x3dce`: `Could not process legacy metadata service request`

## pseudocode

```c

```

## disassembly

```asm
0x3d60  newobj   instance void <>c__DisplayClass11_0::.ctor()
0x3d65  stloc.0
0x3d66  ldloc.0
0x3d67  ldarg.0
0x3d68  stfld    class Microsoft.Crm.Sdk.InProcessLegacySdkAdapter <>c__DisplayClass11_0::<>4__this
0x3d6d  ldloc.0
0x3d6e  ldarg.1
0x3d6f  stfld    object <>c__DisplayClass11_0::request
0x3d74  ldarg.0
0x3d75  ldfld    class [mscorlib]System.Type Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::_metadataRequestBaseType
0x3d7a  ldnull
0x3d7b  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3d80  brfalse.s loc_3D93
0x3d82  ldarg.0
0x3d83  ldstr    aMicrosoftCrmSd_7// "Microsoft.Crm.SdkTypeProxy.Metadata.Met"...
0x3d88  ldc.i4.1
0x3d89  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string, bool)
0x3d8e  stfld    class [mscorlib]System.Type Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::_metadataRequestBaseType
0x3d93  ldloc.0
0x3d94  ldfld    object <>c__DisplayClass11_0::request
0x3d99  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3d9e  ldarg.0
0x3d9f  ldfld    class [mscorlib]System.Type Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::_metadataRequestBaseType
0x3da4  callvirt instance bool [mscorlib]System.Type::IsSubclassOf(class [mscorlib]System.Type)
0x3da9  brtrue.s loc_3DAD
0x3dab  ldnull
0x3dac  ret
0x3dad  ldloc.0
0x3dae  ldnull
0x3daf  stfld    object <>c__DisplayClass11_0::metadataResponse
0x3db4  ldarg.0
0x3db5  ldloc.0
0x3db6  ldftn    instance void <>c__DisplayClass11_0::<HandleMetadataRequest>b__0()
0x3dbc  newobj   instance void ExecuteInProcessIdentityAction::.ctor(object object, native int method)
0x3dc1  call     instance void Microsoft.Crm.Sdk.LegacySdkAdapterBase::ExecuteInProcessIdentity(class ExecuteInProcessIdentityAction actions)
0x3dc6  ldloc.0
0x3dc7  ldfld    object <>c__DisplayClass11_0::metadataResponse
0x3dcc  brtrue.s loc_3DD9
0x3dce  ldstr    aCouldNotProces// "Could not process legacy metadata servi"...
0x3dd3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x3dd8  throw
0x3dd9  ldloc.0
0x3dda  ldfld    object <>c__DisplayClass11_0::metadataResponse
0x3ddf  ret
```
