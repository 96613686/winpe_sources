# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::CreateUserRequest

- ea: `0x20b40`
- end: `0x20c64`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::CreateUserRequest`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1e180`

## callees

- `0x20b40`

## string_xrefs

- `0x20bc7`: `accessmode`
- `0x20bfd`: `emailrouteraccessapproval`

## pseudocode

```c

```

## disassembly

```asm
0x20b40  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.CreateRequest::.ctor()
0x20b45  stloc.0
0x20b46  ldstr    aSystemuser_0// "systemuser"
0x20b4b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x20b50  stloc.1
0x20b51  ldloc.1
0x20b52  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x20b57  ldstr    aBusinessunitid// "businessunitid"
0x20b5c  ldstr    aBusinessunit_0// "businessunit"
0x20b61  ldarg.0
0x20b62  ldstr    aBusinessunitid// "businessunitid"
0x20b67  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x20b6c  unbox.any [mscorlib]System.Guid
0x20b71  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x20b76  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x20b7b  ldarg.0
0x20b7c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Attributes()
0x20b81  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x20b86  stloc.2
0x20b87  br       loc_20C3A
0x20b8c  ldloc.2
0x20b8d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x20b92  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfo
0x20b97  stloc.3
0x20b98  ldloc.1
0x20b99  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x20b9e  ldloc.3
0x20b9f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Name()
0x20ba4  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0x20ba9  brtrue   loc_20C3A
0x20bae  ldloc.3
0x20baf  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Name()
0x20bb4  ldstr    aCaltype// "caltype"
0x20bb9  ldc.i4.5
0x20bba  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x20bbf  brtrue.s loc_20BD4
0x20bc1  ldloc.3
0x20bc2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Name()
0x20bc7  ldstr    aAccessmode// "accessmode"
0x20bcc  ldc.i4.5
0x20bcd  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x20bd2  brfalse.s loc_20BF7
0x20bd4  ldloc.1
0x20bd5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x20bda  ldloc.3
0x20bdb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Name()
0x20be0  ldloc.3
0x20be1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Value()
0x20be6  unbox.any [mscorlib]System.Int32
0x20beb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x20bf0  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x20bf5  br.s     loc_20C3A
0x20bf7  ldloc.3
0x20bf8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Name()
0x20bfd  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x20c02  ldc.i4.5
0x20c03  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x20c08  brfalse.s loc_20C23
0x20c0a  ldloc.1
0x20c0b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x20c10  ldloc.3
0x20c11  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Name()
0x20c16  ldc.i4.1
0x20c17  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x20c1c  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x20c21  br.s     loc_20C3A
0x20c23  ldloc.1
0x20c24  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x20c29  ldloc.3
0x20c2a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Name()
0x20c2f  ldloc.3
0x20c30  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Value()
0x20c35  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x20c3a  ldloc.2
0x20c3b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x20c40  brtrue   loc_20B8C
0x20c45  leave.s  loc_20C5B
0x20c47  ldloc.2
0x20c48  isinst   [mscorlib]System.IDisposable
0x20c4d  stloc.s  4
0x20c4f  ldloc.s  4
0x20c51  brfalse.s loc_20C5A
0x20c53  ldloc.s  4
0x20c55  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20c5a  endfinally
0x20c5b  ldloc.0
0x20c5c  ldloc.1
0x20c5d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.CreateRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x20c62  ldloc.0
0x20c63  ret
```
