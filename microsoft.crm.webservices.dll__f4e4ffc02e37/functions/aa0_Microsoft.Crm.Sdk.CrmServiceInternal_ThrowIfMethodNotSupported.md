# Microsoft.Crm.Sdk.CrmServiceInternal::ThrowIfMethodNotSupported

- ea: `0xaa0`
- end: `0xb32`
- name: `Microsoft.Crm.Sdk.CrmServiceInternal::ThrowIfMethodNotSupported`
- size: `146`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x5a0`
- `0x9d0`

## callees

- `0xa40`
- `0xaa0`
- `0xc10`

## pseudocode

```c

```

## disassembly

```asm
0xaa0  ldarg.1
0xaa1  ldarg.0
0xaa2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xaa7  ldarg.2
0xaa8  call     void Microsoft.Crm.Sdk.CrmServiceInternal::ThrowIfFilterNotSet(string methodName, string entityName, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SdkMessageFilter filter)
0xaad  ldarg.2
0xaae  ldstr    aAvailability// "availability"
0xab3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xab8  unbox.any [mscorlib]System.Int32
0xabd  stloc.0
0xabe  ldloc.0
0xabf  ldc.i4.2
0xac0  beq.s    loc_B31
0xac2  call     bool Microsoft.Crm.Sdk.CrmServiceInternal::get_IsInClientWebServer()
0xac7  brfalse.s loc_AFA
0xac9  ldloc.0
0xaca  ldc.i4.1
0xacb  beq.s    loc_AFA
0xacd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xad2  ldstr    aThe0MethodDoes// "The '{0}' method does not support entit"...
0xad7  ldc.i4.2
0xad8  newarr   [mscorlib]System.Object
0xadd  dup
0xade  ldc.i4.0
0xadf  ldarg.1
0xae0  stelem.ref
0xae1  dup
0xae2  ldc.i4.1
0xae3  ldarg.0
0xae4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xae9  stelem.ref
0xaea  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xaef  ldc.i4   0x80044181
0xaf4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xaf9  throw
0xafa  call     bool Microsoft.Crm.Sdk.CrmServiceInternal::get_IsInClientWebServer()
0xaff  brtrue.s loc_B31
0xb01  ldloc.0
0xb02  brfalse.s loc_B31
0xb04  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb09  ldstr    aThe0MethodDoes_1// "The '{0}' method does not support entit"...
0xb0e  ldc.i4.2
0xb0f  newarr   [mscorlib]System.Object
0xb14  dup
0xb15  ldc.i4.0
0xb16  ldarg.1
0xb17  stelem.ref
0xb18  dup
0xb19  ldc.i4.1
0xb1a  ldarg.0
0xb1b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xb20  stelem.ref
0xb21  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb26  ldc.i4   0x80044180
0xb2b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xb30  throw
0xb31  ret
```
