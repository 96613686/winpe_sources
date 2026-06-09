# Microsoft.Crm.Application.Platform.EntityProxy::IsNonProcessfieldUpdated

- ea: `0x5dcf0`
- end: `0x5dd6e`
- name: `Microsoft.Crm.Application.Platform.EntityProxy::IsNonProcessfieldUpdated`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x5dba0`

## callees

- `0x5b8b0`
- `0x5bae0`
- `0x5dcf0`

## string_xrefs

- `0x5dd45`: `processid`
- `0x5dd1e`: `traversedpath`

## pseudocode

```c

```

## disassembly

```asm
0x5dcf0  ldarg.0
0x5dcf1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Application.Platform.EntityBase::get_InnerEntity()
0x5dcf6  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x5dcfb  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Keys()
0x5dd00  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x5dd05  stloc.0
0x5dd06  br.s     loc_5DD56
0x5dd08  ldloc.0
0x5dd09  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x5dd0e  stloc.1
0x5dd0f  ldloc.1
0x5dd10  ldstr    aStageid// "stageid"
0x5dd15  ldc.i4.3
0x5dd16  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x5dd1b  brtrue.s loc_5DD56
0x5dd1d  ldloc.1
0x5dd1e  ldstr    aTraversedpath// "traversedpath"
0x5dd23  ldc.i4.3
0x5dd24  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x5dd29  brtrue.s loc_5DD56
0x5dd2b  ldloc.1
0x5dd2c  ldarg.0
0x5dd2d  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x5dd32  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x5dd37  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x5dd3c  ldc.i4.3
0x5dd3d  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x5dd42  brtrue.s loc_5DD56
0x5dd44  ldloc.1
0x5dd45  ldstr    aProcessid// "processid"
0x5dd4a  ldc.i4.3
0x5dd4b  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x5dd50  brtrue.s loc_5DD56
0x5dd52  ldc.i4.1
0x5dd53  stloc.2
0x5dd54  leave.s  loc_5DD6C
0x5dd56  ldloc.0
0x5dd57  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5dd5c  brtrue.s loc_5DD08
0x5dd5e  leave.s  loc_5DD6A
0x5dd60  ldloc.0
0x5dd61  brfalse.s loc_5DD69
0x5dd63  ldloc.0
0x5dd64  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5dd69  endfinally
0x5dd6a  ldc.i4.0
0x5dd6b  ret
0x5dd6c  ldloc.2
0x5dd6d  ret
```
