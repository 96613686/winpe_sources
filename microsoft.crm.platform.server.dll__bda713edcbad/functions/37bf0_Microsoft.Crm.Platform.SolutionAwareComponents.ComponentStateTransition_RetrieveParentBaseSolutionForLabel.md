# Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::RetrieveParentBaseSolutionForLabel

- ea: `0x37bf0`
- end: `0x37d49`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::RetrieveParentBaseSolutionForLabel`
- size: `345`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x3c5d0`
- `0x3dd90`
- `0x3e4e0`

## callees

- `0x2e10`
- `0x32c0`
- `0x355f0`
- `0x35b80`
- `0x36170`
- `0x36800`
- `0x37bf0`
- `0x66ff0`

## string_xrefs

- `0x37ce0`: `Null state returned from loader.Load({0}, {1}, ComponentStateLoadOption.RequiredColumns, context)`
- `0x37d15`: `Null state.BaseInstance returned from loader.Load({0}, {1}, ComponentStateLoadOption.RequiredColumns, context)`

## pseudocode

```c

```

## disassembly

```asm
0x37bf0  ldarg.2
0x37bf1  call     class Microsoft.Crm.Dependency.ComponentDefinition Microsoft.Crm.Dependency.ComponentDefinitionFactory::CreateFromLabelType(int32 labelType)
0x37bf6  stloc.1
0x37bf7  ldloc.1
0x37bf8  brtrue.s loc_37C43
0x37bfa  ldarg.2
0x37bfb  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCodeHelper::IsFormChildLabel(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode)
0x37c00  brfalse.s loc_37C43
0x37c02  ldarg.s  4
0x37c04  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x37c09  ldstr    aFormid// "formid"
0x37c0e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x37c13  brfalse.s loc_37C43
0x37c15  ldarg.s  4
0x37c17  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x37c1c  ldstr    aFormid// "formid"
0x37c21  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x37c26  dup
0x37c27  brtrue.s loc_37C34
0x37c29  ldstr    aFormid_0// "formId"
0x37c2e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x37c33  throw
0x37c34  unbox.any [mscorlib]System.Guid
0x37c39  starg.s  3
0x37c3b  ldc.i4.s 0x3C
0x37c3d  stloc.0
0x37c3e  br       loc_37CC7
0x37c43  ldloc.1
0x37c44  brtrue.s loc_37C89
0x37c46  ldarg.2
0x37c47  ldc.i4.s 0x13
0x37c49  bne.un.s loc_37C89
0x37c4b  ldarg.s  4
0x37c4d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x37c52  ldstr    aWorkflowid// "workflowid"
0x37c57  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x37c5c  brfalse.s loc_37C89
0x37c5e  ldarg.s  4
0x37c60  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x37c65  ldstr    aWorkflowid// "workflowid"
0x37c6a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x37c6f  dup
0x37c70  brtrue.s loc_37C7D
0x37c72  ldstr    aWorkflowid// "workflowid"
0x37c77  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x37c7c  throw
0x37c7d  unbox.any [mscorlib]System.Guid
0x37c82  starg.s  3
0x37c84  ldc.i4.s 0x1D
0x37c86  stloc.0
0x37c87  br.s     loc_37CC7
0x37c89  ldloc.1
0x37c8a  brfalse.s loc_37C95
0x37c8c  ldloc.1
0x37c8d  callvirt instance int32 Microsoft.Crm.Dependency.ComponentDefinition::get_ComponentType()
0x37c92  stloc.0
0x37c93  br.s     loc_37CC7
0x37c95  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x37c9a  ldstr    aCouldNotRetrie// "Could not retrieve parent object id for"...
0x37c9f  ldc.i4.2
0x37ca0  newarr   [mscorlib]System.Object
0x37ca5  dup
0x37ca6  ldc.i4.0
0x37ca7  ldarg.1
0x37ca8  box      [mscorlib]System.Guid
0x37cad  stelem.ref
0x37cae  dup
0x37caf  ldc.i4.1
0x37cb0  ldarg.2
0x37cb1  box      [mscorlib]System.Int32
0x37cb6  stelem.ref
0x37cb7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x37cbc  ldc.i4   0x80040203
0x37cc1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x37cc6  throw
0x37cc7  ldloc.0
0x37cc8  call     class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoader Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoaderFactory::Create(int32 componentType)
0x37ccd  ldloc.0
0x37cce  ldarg.3
0x37ccf  ldc.i4.0
0x37cd0  ldarg.s  4
0x37cd2  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoader::Load(int32 componentType, valuetype [mscorlib]System.Guid id, valuetype Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoadOption loadOption, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x37cd7  stloc.2
0x37cd8  ldloc.2
0x37cd9  brtrue.s loc_37D08
0x37cdb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x37ce0  ldstr    aNullStateRetur// "Null state returned from loader.Load({0"...
0x37ce5  ldc.i4.2
0x37ce6  newarr   [mscorlib]System.Object
0x37ceb  dup
0x37cec  ldc.i4.0
0x37ced  ldloc.0
0x37cee  box      [mscorlib]System.Int32
0x37cf3  stelem.ref
0x37cf4  dup
0x37cf5  ldc.i4.1
0x37cf6  ldarg.3
0x37cf7  box      [mscorlib]System.Guid
0x37cfc  stelem.ref
0x37cfd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x37d02  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x37d07  throw
0x37d08  ldloc.2
0x37d09  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x37d0e  brtrue.s loc_37D3D
0x37d10  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x37d15  ldstr    aNullStateBasei// "Null state.BaseInstance returned from l"...
0x37d1a  ldc.i4.2
0x37d1b  newarr   [mscorlib]System.Object
0x37d20  dup
0x37d21  ldc.i4.0
0x37d22  ldloc.0
0x37d23  box      [mscorlib]System.Int32
0x37d28  stelem.ref
0x37d29  dup
0x37d2a  ldc.i4.1
0x37d2b  ldarg.3
0x37d2c  box      [mscorlib]System.Guid
0x37d31  stelem.ref
0x37d32  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x37d37  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x37d3c  throw
0x37d3d  ldloc.2
0x37d3e  callvirt instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x37d43  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x37d48  ret
```
