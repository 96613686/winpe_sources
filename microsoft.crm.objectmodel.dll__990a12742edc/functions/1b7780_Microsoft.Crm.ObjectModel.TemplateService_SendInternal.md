# Microsoft.Crm.ObjectModel.TemplateService::SendInternal

- ea: `0x1b7780`
- end: `0x1b7a81`
- name: `Microsoft.Crm.ObjectModel.TemplateService::SendInternal`
- size: `769`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1b7160`

## callees

- `0x1b6b20`
- `0x1b6b90`
- `0x1b7090`
- `0x1b7780`
- `0x1b7a90`
- `0x1b7c20`
- `0x1b7de0`
- `0x1b84d0`

## string_xrefs

- `0x1b778b`: `templatetypecode`
- `0x1b77ac`: `templatetypecode`
- `0x1b77c4`: `templatetypecode`
- `0x1b77d9`: `templatetypecode`
- `0x1b780a`: `templatetypecode`
- `0x1b7868`: `templatetypecode`
- `0x1b77f3`: `recipientType {0} != {1} template.templatetypecode and not GlobalTemplate`
- `0x1b7850`: `regardingType {0} != {1} template.templatetypecode`

## pseudocode

```c

```

## disassembly

```asm
0x1b7780  ldarg.0
0x1b7781  ldarg.1
0x1b7782  ldarg.s  8
0x1b7784  call     instance class [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.Template Microsoft.Crm.ObjectModel.TemplateService::RetriveForInstantiate(valuetype [mscorlib]System.Guid templateId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1b7789  stloc.0
0x1b778a  ldloc.0
0x1b778b  ldstr    aTemplatetypeco// "templatetypecode"
0x1b7790  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1b7795  unbox.any [mscorlib]System.Int32
0x1b779a  ldc.i4   0x125C
0x1b779f  ceq
0x1b77a1  stloc.1
0x1b77a2  ldloc.1
0x1b77a3  brtrue   loc_1B782F
0x1b77a8  ldarg.3
0x1b77a9  brtrue.s loc_1B77C2
0x1b77ab  ldloc.0
0x1b77ac  ldstr    aTemplatetypeco// "templatetypecode"
0x1b77b1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1b77b6  unbox.any [mscorlib]System.Int32
0x1b77bb  starg.s  3
0x1b77bd  br       loc_1B788D
0x1b77c2  ldarg.3
0x1b77c3  ldloc.0
0x1b77c4  ldstr    aTemplatetypeco// "templatetypecode"
0x1b77c9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1b77ce  unbox.any [mscorlib]System.Int32
0x1b77d3  beq      loc_1B788D
0x1b77d8  ldloc.0
0x1b77d9  ldstr    aTemplatetypeco// "templatetypecode"
0x1b77de  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1b77e3  unbox.any [mscorlib]System.Int32
0x1b77e8  ldc.i4.8
0x1b77e9  beq      loc_1B788D
0x1b77ee  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b77f3  ldstr    aRecipienttype0// "recipientType {0} != {1} template.templ"...
0x1b77f8  ldc.i4.2
0x1b77f9  newarr   [mscorlib]System.Object
0x1b77fe  dup
0x1b77ff  ldc.i4.0
0x1b7800  ldarg.3
0x1b7801  box      [mscorlib]System.Int32
0x1b7806  stelem.ref
0x1b7807  dup
0x1b7808  ldc.i4.1
0x1b7809  ldloc.0
0x1b780a  ldstr    aTemplatetypeco// "templatetypecode"
0x1b780f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1b7814  unbox.any [mscorlib]System.Int32
0x1b7819  box      [mscorlib]System.Int32
0x1b781e  stelem.ref
0x1b781f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b7824  ldc.i4   0x80040203
0x1b7829  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1b782e  throw
0x1b782f  ldarg.3
0x1b7830  brtrue.s loc_1B7835
0x1b7832  ldc.i4.8
0x1b7833  starg.s  3
0x1b7835  ldarg.s  5
0x1b7837  brtrue.s loc_1B7842
0x1b7839  ldc.i4   0x125C
0x1b783e  starg.s  5
0x1b7840  br.s     loc_1B788D
0x1b7842  ldarg.s  5
0x1b7844  ldc.i4   0x125C
0x1b7849  beq.s    loc_1B788D
0x1b784b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b7850  ldstr    aRegardingtype0// "regardingType {0} != {1} template.templ"...
0x1b7855  ldc.i4.2
0x1b7856  newarr   [mscorlib]System.Object
0x1b785b  dup
0x1b785c  ldc.i4.0
0x1b785d  ldarg.s  5
0x1b785f  box      [mscorlib]System.Int32
0x1b7864  stelem.ref
0x1b7865  dup
0x1b7866  ldc.i4.1
0x1b7867  ldloc.0
0x1b7868  ldstr    aTemplatetypeco// "templatetypecode"
0x1b786d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1b7872  unbox.any [mscorlib]System.Int32
0x1b7877  box      [mscorlib]System.Int32
0x1b787c  stelem.ref
0x1b787d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b7882  ldc.i4   0x80040203
0x1b7887  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1b788c  throw
0x1b788d  ldarg.0
0x1b788e  ldloc.0
0x1b788f  ldstr    aBody// "body"
0x1b7894  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1b7899  brtrue.s loc_1B78AD
0x1b789b  ldloc.0
0x1b789c  ldstr    aBody// "body"
0x1b78a1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1b78a6  castclass [mscorlib]System.String
0x1b78ab  br.s     loc_1B78AE
0x1b78ad  ldnull
0x1b78ae  call     instance class [System.Xml]System.Xml.Xsl.XslCompiledTransform Microsoft.Crm.ObjectModel.TemplateService::GetXslTransform(string xslXml)
0x1b78b3  stloc.2
0x1b78b4  ldarg.0
0x1b78b5  ldloc.0
0x1b78b6  ldstr    aSubject// "subject"
0x1b78bb  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1b78c0  brtrue.s loc_1B78D4
0x1b78c2  ldloc.0
0x1b78c3  ldstr    aSubject// "subject"
0x1b78c8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1b78cd  castclass [mscorlib]System.String
0x1b78d2  br.s     loc_1B78D5
0x1b78d4  ldnull
0x1b78d5  call     instance class [System.Xml]System.Xml.Xsl.XslCompiledTransform Microsoft.Crm.ObjectModel.TemplateService::GetXslTransform(string xslXml)
0x1b78da  stloc.3
0x1b78db  ldarg.0
0x1b78dc  ldarg.2
0x1b78dd  ldarg.s  8
0x1b78df  call     instance class [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.ActivityParty Microsoft.Crm.ObjectModel.TemplateService::PrepareSenderParty(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker sender, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1b78e4  stloc.s  4
0x1b78e6  ldloc.s  4
0x1b78e8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x1b78ed  ldarg.s  8
0x1b78ef  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1b78f4  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x1b78f9  stloc.s  5
0x1b78fb  ldloc.s  5
0x1b78fd  ldloc.s  4
0x1b78ff  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x1b7904  pop
0x1b7905  ldc.i4.0
0x1b7906  stloc.s  6
0x1b7908  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x1b790d  stloc.s  7
0x1b790f  ldloc.s  7
0x1b7911  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1b7916  box      [mscorlib]System.Guid
0x1b791b  ldc.i4.1
0x1b791c  box      [mscorlib]System.Boolean
0x1b7921  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1b7926  ldc.i4.0
0x1b7927  stloc.s  8
0x1b7929  br       loc_1B7A60
0x1b792e  ldloc.s  7
0x1b7930  ldarg.s  4
0x1b7932  ldloc.s  8
0x1b7934  ldelem   [mscorlib]System.Guid
0x1b7939  box      [mscorlib]System.Guid
0x1b793e  callvirt instance bool [mscorlib]System.Collections.Hashtable::ContainsKey(object)
0x1b7943  brtrue   loc_1B7A5A
0x1b7948  ldloc.s  7
0x1b794a  ldarg.s  4
0x1b794c  ldloc.s  8
0x1b794e  ldelem   [mscorlib]System.Guid
0x1b7953  box      [mscorlib]System.Guid
0x1b7958  ldc.i4.1
0x1b7959  box      [mscorlib]System.Boolean
0x1b795e  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1b7963  ldnull
0x1b7964  stloc.s  9
0x1b7966  ldnull
0x1b7967  stloc.s  0xA
0x1b7969  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.RecipientEmailAddress>::.ctor()
0x1b796e  stloc.s  0xB
0x1b7970  ldloc.1
0x1b7971  brtrue.s loc_1B7990
0x1b7973  ldarg.0
0x1b7974  ldloc.3
0x1b7975  ldloc.2
0x1b7976  ldarg.3
0x1b7977  ldarg.s  4
0x1b7979  ldloc.s  8
0x1b797b  ldelem   [mscorlib]System.Guid
0x1b7980  ldloca.s 9
0x1b7982  ldloca.s 0xB
0x1b7984  ldarg.s  8
0x1b7986  ldloc.0
0x1b7987  call     instance string Microsoft.Crm.ObjectModel.TemplateService::InstantiateInternal(class [System.Xml]System.Xml.Xsl.XslCompiledTransform subjectTransform, class [System.Xml]System.Xml.Xsl.XslCompiledTransform bodyTransform, int32 objectType, valuetype [mscorlib]System.Guid objectId, [out] string& subjectOut, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.RecipientEmailAddress>& listAddresses, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.Template template)
0x1b798c  stloc.s  0xA
0x1b798e  br.s     loc_1B79BD
0x1b7990  ldnull
0x1b7991  stloc.s  0xE
0x1b7993  ldarg.0
0x1b7994  ldloc.3
0x1b7995  ldloc.2
0x1b7996  ldarg.s  5
0x1b7998  ldarg.s  6
0x1b799a  ldloca.s 9
0x1b799c  ldloca.s 0xE
0x1b799e  ldarg.s  8
0x1b79a0  ldloc.0
0x1b79a1  call     instance string Microsoft.Crm.ObjectModel.TemplateService::InstantiateInternal(class [System.Xml]System.Xml.Xsl.XslCompiledTransform subjectTransform, class [System.Xml]System.Xml.Xsl.XslCompiledTransform bodyTransform, int32 objectType, valuetype [mscorlib]System.Guid objectId, [out] string& subjectOut, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.RecipientEmailAddress>& listAddresses, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.Template template)
0x1b79a6  stloc.s  0xA
0x1b79a8  ldarg.0
0x1b79a9  ldloca.s 0xB
0x1b79ab  ldarg.3
0x1b79ac  ldarg.s  4
0x1b79ae  ldloc.s  8
0x1b79b0  ldelem   [mscorlib]System.Guid
0x1b79b5  ldarg.s  8
0x1b79b7  ldloc.0
0x1b79b8  call     instance void Microsoft.Crm.ObjectModel.TemplateService::GetEmailAddress(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.RecipientEmailAddress>& listAddresses, int32 recipientType, valuetype [mscorlib]System.Guid recipientId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.Template template)
0x1b79bd  leave.s  loc_1B79D2
0x1b79bf  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x1b79c4  ldc.i4   0x80040B00
0x1b79c9  bne.un.s loc_1B79D0
0x1b79cb  leave    loc_1B7A5A
0x1b79d0  leave.s  loc_1B79D2
0x1b79d2  ldloc.s  0xB
0x1b79d4  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.RecipientEmailAddress>::get_Count()
0x1b79d9  brfalse.s loc_1B7A5A
0x1b79db  ldnull
0x1b79dc  stloc.s  0xC
0x1b79de  ldnull
0x1b79df  stloc.s  0xD
0x1b79e1  ldloc.s  0xA
0x1b79e3  ldloc.s  9
0x1b79e5  ldloca.s 0xC
0x1b79e7  ldloca.s 0xD
0x1b79e9  call     void Microsoft.Crm.ObjectModel.TemplateServiceUtility::GetParsedXML(string bodyXml, string subjectXml, [out] string[]& bodies, [out] string[]& subjects)
0x1b79ee  ldc.i4.0
0x1b79ef  stloc.s  0xF
0x1b79f1  br.s     loc_1B7A52
0x1b79f3  ldloc.s  0xD
0x1b79f5  ldloc.s  0xF
0x1b79f7  ldelem.ref
0x1b79f8  stloc.s  0x10
0x1b79fa  ldloc.s  0x10
0x1b79fc  brfalse.s loc_1B7A19
0x1b79fe  ldloc.s  0x10
0x1b7a00  ldc.i4.0
0x1b7a01  ldc.i4   0xC8
0x1b7a06  ldloc.s  0x10
0x1b7a08  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1b7a0d  call     int32 [mscorlib]System.Math::Min(int32, int32)
0x1b7a12  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x1b7a17  stloc.s  0x10
0x1b7a19  ldarg.0
0x1b7a1a  ldarg.1
0x1b7a1b  ldloc.s  5
0x1b7a1d  ldarg.3
0x1b7a1e  ldarg.s  4
0x1b7a20  ldloc.s  8
0x1b7a22  ldelem   [mscorlib]System.Guid
0x1b7a27  ldarg.s  5
0x1b7a29  ldarg.s  6
0x1b7a2b  ldloc.s  0xC
0x1b7a2d  ldloc.s  0xF
0x1b7a2f  ldelem.ref
0x1b7a30  ldloc.s  0x10
0x1b7a32  ldloc.s  0xB
0x1b7a34  ldloc.s  0xF
0x1b7a36  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.RecipientEmailAddress>::get_Item(!!T0)
0x1b7a3b  ldarg.s  7
0x1b7a3d  ldarg.s  8
0x1b7a3f  ldarg.s  9
0x1b7a41  call     instance void Microsoft.Crm.ObjectModel.TemplateService::SendEmail(valuetype [mscorlib]System.Guid templateId, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection senders, int32 recipientType, valuetype [mscorlib]System.Guid recipientId, int32 regardingType, valuetype [mscorlib]System.Guid regardingId, string body, string subject, class Microsoft.Crm.ObjectModel.RecipientEmailAddress recipientAddress, int32 deliveryPriorityCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.ObjectModel.IEmailService emailSendEmailService)
0x1b7a46  ldloc.s  6
0x1b7a48  ldc.i4.1
0x1b7a49  add
0x1b7a4a  stloc.s  6
0x1b7a4c  ldloc.s  0xF
0x1b7a4e  ldc.i4.1
0x1b7a4f  add
0x1b7a50  stloc.s  0xF
0x1b7a52  ldloc.s  0xF
0x1b7a54  ldloc.s  0xC
0x1b7a56  ldlen
0x1b7a57  conv.i4
0x1b7a58  blt.s    loc_1B79F3
0x1b7a5a  ldloc.s  8
0x1b7a5c  ldc.i4.1
0x1b7a5d  add
0x1b7a5e  stloc.s  8
0x1b7a60  ldloc.s  8
0x1b7a62  ldarg.s  4
0x1b7a64  ldlen
0x1b7a65  conv.i4
0x1b7a66  blt      loc_1B792E
0x1b7a6b  ldloc.s  6
0x1b7a6d  brtrue.s loc_1B7A80
0x1b7a6f  ldc.i4   0x80040B00
0x1b7a74  ldc.i4.0
0x1b7a75  newarr   [mscorlib]System.Object
0x1b7a7a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1b7a7f  throw
0x1b7a80  ret
```
