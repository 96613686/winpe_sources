# Microsoft.Crm.Workflow.Services.ActivityServiceBase::AttachMimeEmailAttachment

- ea: `0x14ca0`
- end: `0x14dcb`
- name: `Microsoft.Crm.Workflow.Services.ActivityServiceBase::AttachMimeEmailAttachment`
- size: `299`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2ea90`
- `0x2ee70`
- `0x2f190`

## callees

- `0x14ca0`
- `0x14dd0`

## pseudocode

```c

```

## disassembly

```asm
0x14ca0  ldarg.0
0x14ca1  ldarg.1
0x14ca2  ldarg.2
0x14ca3  ldarg.s  4
0x14ca5  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection Microsoft.Crm.Workflow.Services.ActivityServiceBase::GetWorkflowStepAttachments(valuetype [mscorlib]System.Guid workflowActivationId, string stepId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService sdkService)
0x14caa  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x14caf  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x14cb4  stloc.0
0x14cb5  br       loc_14DB3
0x14cba  ldloc.0
0x14cbb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x14cc0  stloc.1
0x14cc1  ldstr    aActivitymimeat// "activitymimeattachment"
0x14cc6  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x14ccb  stloc.2
0x14ccc  ldloc.2
0x14ccd  ldstr    aActivityid// "activityid"
0x14cd2  ldstr    aEmail// "email"
0x14cd7  ldarg.3
0x14cd8  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x14cdd  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x14ce2  ldloc.1
0x14ce3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x14ce8  ldstr    aDocumentbody// "documentbody"
0x14ced  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x14cf2  brfalse.s loc_14D0A
0x14cf4  ldloc.2
0x14cf5  ldstr    aBody// "body"
0x14cfa  ldloc.1
0x14cfb  ldstr    aDocumentbody// "documentbody"
0x14d00  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x14d05  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x14d0a  ldloc.1
0x14d0b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x14d10  ldstr    aFilename// "filename"
0x14d15  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x14d1a  brfalse.s loc_14D32
0x14d1c  ldloc.2
0x14d1d  ldstr    aFilename// "filename"
0x14d22  ldloc.1
0x14d23  ldstr    aFilename// "filename"
0x14d28  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x14d2d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x14d32  ldloc.1
0x14d33  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x14d38  ldstr    aFilesize// "filesize"
0x14d3d  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x14d42  brfalse.s loc_14D5A
0x14d44  ldloc.2
0x14d45  ldstr    aFilesize// "filesize"
0x14d4a  ldloc.1
0x14d4b  ldstr    aFilesize// "filesize"
0x14d50  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x14d55  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x14d5a  ldloc.1
0x14d5b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x14d60  ldstr    aMimetype// "mimetype"
0x14d65  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x14d6a  brfalse.s loc_14D82
0x14d6c  ldloc.2
0x14d6d  ldstr    aMimetype// "mimetype"
0x14d72  ldloc.1
0x14d73  ldstr    aMimetype// "mimetype"
0x14d78  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x14d7d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x14d82  ldloc.1
0x14d83  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x14d88  ldstr    aSubject// "subject"
0x14d8d  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x14d92  brfalse.s loc_14DAA
0x14d94  ldloc.2
0x14d95  ldstr    aSubject// "subject"
0x14d9a  ldloc.1
0x14d9b  ldstr    aSubject// "subject"
0x14da0  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x14da5  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x14daa  ldarg.s  4
0x14dac  ldloc.2
0x14dad  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Create(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x14db2  pop
0x14db3  ldloc.0
0x14db4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x14db9  brtrue   loc_14CBA
0x14dbe  leave.s  loc_14DCA
0x14dc0  ldloc.0
0x14dc1  brfalse.s loc_14DC9
0x14dc3  ldloc.0
0x14dc4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14dc9  endfinally
0x14dca  ret
```
