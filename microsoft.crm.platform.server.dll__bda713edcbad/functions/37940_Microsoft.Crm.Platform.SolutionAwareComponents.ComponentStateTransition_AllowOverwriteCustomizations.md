# Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::AllowOverwriteCustomizations

- ea: `0x37940`
- end: `0x379e6`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::AllowOverwriteCustomizations`
- size: `166`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3dd90`
- `0x3e4e0`

## callees

- `0x2fd0`
- `0x35b20`
- `0x36040`
- `0x37940`
- `0x37ab0`
- `0x66ff0`

## string_xrefs

- `0x3794a`: `updateForCustomizableSystemForm`
- `0x3795c`: `updateForCustomizableSystemForm`
- `0x379a7`: `systemFormComponentInstance`

## pseudocode

```c

```

## disassembly

```asm
0x37940  ldarg.1
0x37941  ldc.i4.7
0x37942  bne.un.s loc_37992
0x37944  ldarg.3
0x37945  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x3794a  ldstr    aUpdateforcusto// "updateForCustomizableSystemForm"
0x3794f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x37954  brfalse.s loc_3796F
0x37956  ldarg.3
0x37957  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x3795c  ldstr    aUpdateforcusto// "updateForCustomizableSystemForm"
0x37961  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x37966  unbox.any [mscorlib]System.Boolean
0x3796b  brfalse.s loc_3796F
0x3796d  ldc.i4.1
0x3796e  ret
0x3796f  ldarg.2
0x37970  ldstr    aLabeltypecode// "labeltypecode"
0x37975  callvirt instance object Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_Item(string name)
0x3797a  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode
0x3797f  stloc.1
0x37980  ldloc.1
0x37981  ldc.i4.5
0x37982  beq.s    loc_37990
0x37984  ldloc.1
0x37985  ldc.i4.6
0x37986  beq.s    loc_37990
0x37988  ldloc.1
0x37989  ldc.i4.7
0x3798a  beq.s    loc_37990
0x3798c  ldloc.1
0x3798d  ldc.i4.8
0x3798e  bne.un.s loc_37992
0x37990  ldc.i4.0
0x37991  ret
0x37992  ldarg.0
0x37993  ldarg.1
0x37994  ldarg.2
0x37995  call     instance class Microsoft.Crm.Dependency.ComponentDefinition Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::GetComponentDefinitionForComponentType(int32 componentType, class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance instance)
0x3799a  stloc.0
0x3799b  ldarg.1
0x3799c  ldc.i4.s 0x3C
0x3799e  bne.un.s loc_379DA
0x379a0  ldarg.2
0x379a1  isinst   Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentInstance
0x379a6  dup
0x379a7  ldstr    aSystemformcomp// "systemFormComponentInstance"
0x379ac  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x379b1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentInstance::get_Entity()
0x379b6  ldstr    aType// "type"
0x379bb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x379c0  stloc.2
0x379c1  ldloc.2
0x379c2  brfalse.s loc_379D8
0x379c4  ldloc.2
0x379c5  unbox.any [mscorlib]System.Int32
0x379ca  brfalse.s loc_379D6
0x379cc  ldloc.2
0x379cd  unbox.any [mscorlib]System.Int32
0x379d2  ldc.i4.8
0x379d3  ceq
0x379d5  ret
0x379d6  ldc.i4.1
0x379d7  ret
0x379d8  ldc.i4.0
0x379d9  ret
0x379da  ldloc.0
0x379db  brfalse.s loc_379E4
0x379dd  ldloc.0
0x379de  callvirt instance bool Microsoft.Crm.Dependency.ComponentDefinition::get_AllowOverwriteCustomizations()
0x379e3  ret
0x379e4  ldc.i4.1
0x379e5  ret
```
