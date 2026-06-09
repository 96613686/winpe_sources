# Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstanceBase::ToString

- ea: `0x35e00`
- end: `0x35ee6`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstanceBase::ToString`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x35fa0`

## callees

- `0x35b40`
- `0x35b60`
- `0x35b80`
- `0x35ba0`
- `0x35bc0`
- `0x35be0`

## string_xrefs

- `0x35e31`: `ComponentStateName = {0} `
- `0x35ea0`: `ComponentState = {0} `
- `0x35ec5`: `OverwriteTime = {0} `

## pseudocode

```c

```

## disassembly

```asm
0x35e00  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x35e05  stloc.0
0x35e06  ldloc.0
0x35e07  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x35e0c  ldstr    aRowguid0// "RowGuid = {0} "
0x35e11  ldc.i4.1
0x35e12  newarr   [mscorlib]System.Object
0x35e17  dup
0x35e18  ldc.i4.0
0x35e19  ldarg.0
0x35e1a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_RowGuidId()
0x35e1f  box      [mscorlib]System.Guid
0x35e24  stelem.ref
0x35e25  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x35e2a  pop
0x35e2b  ldloc.0
0x35e2c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x35e31  ldstr    aComponentstate_0// "ComponentStateName = {0} "
0x35e36  ldc.i4.1
0x35e37  newarr   [mscorlib]System.Object
0x35e3c  dup
0x35e3d  ldc.i4.0
0x35e3e  ldarg.0
0x35e3f  callvirt instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_Name()
0x35e44  box      Microsoft.Crm.Platform.ComponentStateNames
0x35e49  stelem.ref
0x35e4a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x35e4f  pop
0x35e50  ldloc.0
0x35e51  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x35e56  ldstr    aSolutionid0// "SolutionId = {0} "
0x35e5b  ldc.i4.1
0x35e5c  newarr   [mscorlib]System.Object
0x35e61  dup
0x35e62  ldc.i4.0
0x35e63  ldarg.0
0x35e64  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x35e69  box      [mscorlib]System.Guid
0x35e6e  stelem.ref
0x35e6f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x35e74  pop
0x35e75  ldloc.0
0x35e76  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x35e7b  ldstr    aSupportingsolu_0// "SupportingSolutionId = {0} "
0x35e80  ldc.i4.1
0x35e81  newarr   [mscorlib]System.Object
0x35e86  dup
0x35e87  ldc.i4.0
0x35e88  ldarg.0
0x35e89  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SupportingSolutionId()
0x35e8e  box      [mscorlib]System.Guid
0x35e93  stelem.ref
0x35e94  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x35e99  pop
0x35e9a  ldloc.0
0x35e9b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x35ea0  ldstr    aComponentstate_1// "ComponentState = {0} "
0x35ea5  ldc.i4.1
0x35ea6  newarr   [mscorlib]System.Object
0x35eab  dup
0x35eac  ldc.i4.0
0x35ead  ldarg.0
0x35eae  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x35eb3  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x35eb8  stelem.ref
0x35eb9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x35ebe  pop
0x35ebf  ldloc.0
0x35ec0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x35ec5  ldstr    aOverwritetime0// "OverwriteTime = {0} "
0x35eca  ldc.i4.1
0x35ecb  newarr   [mscorlib]System.Object
0x35ed0  dup
0x35ed1  ldc.i4.0
0x35ed2  ldarg.0
0x35ed3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_OverwriteTime()
0x35ed8  stelem.ref
0x35ed9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x35ede  pop
0x35edf  ldloc.0
0x35ee0  callvirt instance string [mscorlib]System.Object::ToString()
0x35ee5  ret
```
