# Microsoft.Crm.Sdk.CrmServiceInternal::ThrowIfMessageNotSupported

- ea: `0xb70`
- end: `0xc09`
- name: `Microsoft.Crm.Sdk.CrmServiceInternal::ThrowIfMessageNotSupported`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x5a0`
- `0x920`

## callees

- `0xb70`
- `0xc10`
- `0x4a50`
- `0x4a80`

## string_xrefs

- `0xb7e`: `Client web services should not be called when online`

## pseudocode

```c

```

## disassembly

```asm
0xb70  call     bool Microsoft.Crm.Sdk.CrmServiceInternal::get_IsInClientWebServer()
0xb75  brfalse.s loc_B8E
0xb77  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::get_IsOffline()
0xb7c  brtrue.s loc_B8E
0xb7e  ldstr    aClientWebServi// "Client web services should not be calle"...
0xb83  ldc.i4   0x8004410E
0xb88  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xb8d  throw
0xb8e  ldarg.1
0xb8f  callvirt instance int32 Microsoft.Crm.Sdk.IRequestBuilder::get_Availability()
0xb94  ldc.i4.2
0xb95  beq.s    loc_C08
0xb97  call     bool Microsoft.Crm.Sdk.CrmServiceInternal::get_IsInClientWebServer()
0xb9c  brfalse.s loc_BD0
0xb9e  ldarg.1
0xb9f  callvirt instance int32 Microsoft.Crm.Sdk.IRequestBuilder::get_Availability()
0xba4  ldc.i4.1
0xba5  beq.s    loc_BD0
0xba7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbac  ldstr    aThe0MessageIsN// "The {0} message is not supported on the"...
0xbb1  ldc.i4.1
0xbb2  newarr   [mscorlib]System.Object
0xbb7  dup
0xbb8  ldc.i4.0
0xbb9  ldarg.1
0xbba  callvirt instance string Microsoft.Crm.Sdk.IRequestBuilder::get_RequestName()
0xbbf  stelem.ref
0xbc0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbc5  ldc.i4   0x80044181
0xbca  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xbcf  throw
0xbd0  call     bool Microsoft.Crm.Sdk.CrmServiceInternal::get_IsInClientWebServer()
0xbd5  brtrue.s loc_C08
0xbd7  ldarg.1
0xbd8  callvirt instance int32 Microsoft.Crm.Sdk.IRequestBuilder::get_Availability()
0xbdd  brfalse.s loc_C08
0xbdf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbe4  ldstr    aThe0MessageIsN_0// "The {0} message is not supported on the"...
0xbe9  ldc.i4.1
0xbea  newarr   [mscorlib]System.Object
0xbef  dup
0xbf0  ldc.i4.0
0xbf1  ldarg.1
0xbf2  callvirt instance string Microsoft.Crm.Sdk.IRequestBuilder::get_RequestName()
0xbf7  stelem.ref
0xbf8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbfd  ldc.i4   0x80044180
0xc02  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xc07  throw
0xc08  ret
```
