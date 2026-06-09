# <>c__DisplayClass2_0::<Execute>b__0

- ea: `0xfb50`
- end: `0xfbc2`
- name: `<>c__DisplayClass2_0::<Execute>b__0`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x30f0`

## string_xrefs

- `0xfb5c`: `InProcessCrmService starts processing request for user:{1}{0}As user:{2}{0}Request Xml:{0}`

## pseudocode

```c

```

## disassembly

```asm
0xfb50  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xfb55  stloc.0
0xfb56  ldloc.0
0xfb57  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfb5c  ldstr    aInprocesscrmse_0// "InProcessCrmService starts processing r"...
0xfb61  ldc.i4.4
0xfb62  newarr   [mscorlib]System.Object
0xfb67  dup
0xfb68  ldc.i4.0
0xfb69  call     string [mscorlib]System.Environment::get_NewLine()
0xfb6e  stelem.ref
0xfb6f  dup
0xfb70  ldc.i4.1
0xfb71  ldarg.0
0xfb72  ldfld    object <>c__DisplayClass2_0::request
0xfb77  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xfb7c  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xfb81  stelem.ref
0xfb82  dup
0xfb83  ldc.i4.2
0xfb84  ldarg.0
0xfb85  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth <>c__DisplayClass2_0::userAuth
0xfb8a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_UserId()
0xfb8f  box      [mscorlib]System.Guid
0xfb94  stelem.ref
0xfb95  dup
0xfb96  ldc.i4.3
0xfb97  ldarg.0
0xfb98  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass2_0::targetUserId
0xfb9d  box      [mscorlib]System.Guid
0xfba2  stelem.ref
0xfba3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xfba8  pop
0xfba9  ldarg.0
0xfbaa  ldfld    class Microsoft.Crm.Sdk.InProcessCrmService <>c__DisplayClass2_0::<>4__this
0xfbaf  ldarg.0
0xfbb0  ldfld    object <>c__DisplayClass2_0::request
0xfbb5  ldloc.0
0xfbb6  call     instance void Microsoft.Crm.Sdk.InProcessCrmService::SerializeRequest(object request, class [mscorlib]System.Text.StringBuilder sb)
0xfbbb  ldloc.0
0xfbbc  callvirt instance string [mscorlib]System.Object::ToString()
0xfbc1  ret
```
