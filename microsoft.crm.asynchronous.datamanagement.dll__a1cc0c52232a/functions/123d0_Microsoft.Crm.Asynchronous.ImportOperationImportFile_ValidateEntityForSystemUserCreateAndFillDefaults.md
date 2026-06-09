# Microsoft.Crm.Asynchronous.ImportOperationImportFile::ValidateEntityForSystemUserCreateAndFillDefaults

- ea: `0x123d0`
- end: `0x12514`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImportFile::ValidateEntityForSystemUserCreateAndFillDefaults`
- size: `324`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x11a20`

## callees

- `0x123d0`

## string_xrefs

- `0x12495`: `accessmode`
- `0x124a2`: `accessmode`
- `0x124af`: `accessmode`

## pseudocode

```c

```

## disassembly

```asm
0x123d0  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x123d5  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x123da  ldc.i4.2
0x123db  bne.un.s loc_12439
0x123dd  ldarg.1
0x123de  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x123e3  ldstr    aFirstname// "firstname"
0x123e8  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x123ed  brtrue   loc_1248F
0x123f2  ldarg.1
0x123f3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x123f8  ldstr    aLastname// "lastname"
0x123fd  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x12402  brtrue   loc_1248F
0x12407  ldarg.1
0x12408  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1240d  ldstr    aInternalemaila_0// "internalemailadress"
0x12412  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x12417  brtrue.s loc_1248F
0x12419  ldnull
0x1241a  ldarg.0
0x1241b  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x12420  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x12425  ldc.i4.s 0x18
0x12427  ldstr    aFirstnameLastn// "firstname, lastname, internalemailaddre"...
0x1242c  ldc.i4.0
0x1242d  newarr   [mscorlib]System.Object
0x12432  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x12437  ldc.i4.0
0x12438  ret
0x12439  ldarg.1
0x1243a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1243f  ldstr    aFirstname// "firstname"
0x12444  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x12449  brtrue.s loc_1248F
0x1244b  ldarg.1
0x1244c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x12451  ldstr    aLastname// "lastname"
0x12456  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x1245b  brtrue.s loc_1248F
0x1245d  ldarg.1
0x1245e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x12463  ldstr    aDomainname// "domainname"
0x12468  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x1246d  brtrue.s loc_1248F
0x1246f  ldnull
0x12470  ldarg.0
0x12471  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x12476  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x1247b  ldc.i4.s 0x18
0x1247d  ldstr    aFirstnameLastn// "firstname, lastname, internalemailaddre"...
0x12482  ldc.i4.0
0x12483  newarr   [mscorlib]System.Object
0x12488  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1248d  ldc.i4.0
0x1248e  ret
0x1248f  ldarg.1
0x12490  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x12495  ldstr    aAccessmode// "accessmode"
0x1249a  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x1249f  brfalse.s loc_124AE
0x124a1  ldarg.1
0x124a2  ldstr    aAccessmode// "accessmode"
0x124a7  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x124ac  brtrue.s loc_124BF
0x124ae  ldarg.1
0x124af  ldstr    aAccessmode// "accessmode"
0x124b4  ldc.i4.0
0x124b5  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x124ba  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x124bf  ldarg.1
0x124c0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x124c5  ldstr    aBusinessunitid// "businessunitid"
0x124ca  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x124cf  brfalse.s loc_124DE
0x124d1  ldarg.1
0x124d2  ldstr    aBusinessunitid// "businessunitid"
0x124d7  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x124dc  brtrue.s loc_124F4
0x124de  ldarg.1
0x124df  ldstr    aBusinessunitid// "businessunitid"
0x124e4  ldstr    aBusinessunit// "businessunit"
0x124e9  ldarg.2
0x124ea  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x124ef  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x124f4  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x124f9  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x124fe  ldc.i4.2
0x124ff  bne.un.s loc_12512
0x12501  ldarg.1
0x12502  ldstr    aInvitestatusco// "invitestatuscode"
0x12507  ldc.i4.0
0x12508  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x1250d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x12512  ldc.i4.1
0x12513  ret
```
