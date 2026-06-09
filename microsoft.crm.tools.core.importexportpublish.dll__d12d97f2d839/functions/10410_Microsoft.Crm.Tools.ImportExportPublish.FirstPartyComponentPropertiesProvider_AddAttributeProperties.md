# Microsoft.Crm.Tools.ImportExportPublish.FirstPartyComponentPropertiesProvider::AddAttributeProperties

- ea: `0x10410`
- end: `0x10523`
- name: `Microsoft.Crm.Tools.ImportExportPublish.FirstPartyComponentPropertiesProvider::AddAttributeProperties`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x102a0`

## callees

- `0x10dc0`

## string_xrefs

- `0x1044d`: `xmlabbreviation`
- `0x10479`: `isidentity`
- `0x104bb`: `linkedattributeid`
- `0x104d1`: `managedpropertyparentcomponenttype`

## pseudocode

```c

```

## disassembly

```asm
0x10410  ldarg.0
0x10411  ldstr    aAttribute// "Attribute"
0x10416  ldstr    aAttribute_0// "attribute"
0x1041b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x10420  dup
0x10421  ldstr    aAttributerowid// "attributerowid"
0x10426  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1042b  dup
0x1042c  ldstr    aColumnnumber// "columnnumber"
0x10431  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10436  dup
0x10437  ldstr    aOptionsetid_0// "optionsetid"
0x1043c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10441  dup
0x10442  ldstr    aTablecolumnnam// "tablecolumnname"
0x10447  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1044c  dup
0x1044d  ldstr    aXmlabbreviatio// "xmlabbreviation"
0x10452  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10457  dup
0x10458  ldstr    aEntityid_1// "entityid"
0x1045d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10462  dup
0x10463  ldstr    aColumnnumber// "columnnumber"
0x10468  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1046d  dup
0x1046e  ldstr    aValuesfromrela// "valuesfromrelationshipattribute"
0x10473  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10478  dup
0x10479  ldstr    aIsidentity// "isidentity"
0x1047e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10483  dup
0x10484  ldstr    aIsreplicated// "isreplicated"
0x10489  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1048e  dup
0x1048f  ldstr    aYomiof// "yomiof"
0x10494  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10499  dup
0x1049a  ldstr    aIsbasecurrency// "isbasecurrency"
0x1049f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x104a4  dup
0x104a5  ldstr    aCalculationof// "calculationof"
0x104aa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x104af  dup
0x104b0  ldstr    aOptionsetid_0// "optionsetid"
0x104b5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x104ba  dup
0x104bb  ldstr    aLinkedattribut// "linkedattributeid"
0x104c0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x104c5  dup
0x104c6  ldstr    aManagedpropert// "managedpropertylogicalname"
0x104cb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x104d0  dup
0x104d1  ldstr    aManagedpropert_0// "managedpropertyparentcomponenttype"
0x104d6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x104db  dup
0x104dc  ldstr    aManagedpropert_1// "managedpropertyparentattributename"
0x104e1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x104e6  dup
0x104e7  ldstr    aAttributeimemo// "attributeimemodeid"
0x104ec  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x104f1  dup
0x104f2  ldstr    aAttributerequi// "attributerequiredlevelid"
0x104f7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x104fc  dup
0x104fd  ldstr    aAccuracysource// "accuracysource"
0x10502  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10507  dup
0x10508  ldstr    aSourcetypemask// "sourcetypemask"
0x1050d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10512  dup
0x10513  ldstr    aIsactive// "isactive"
0x10518  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1051d  call     void Microsoft.Crm.Tools.ImportExportPublish.FirstPartyComponentPropertiesProvider::AddPropertiesForMetadataForMetadata(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string metadataEntityName, string componentName, class [mscorlib]System.Collections.Generic.List`1<string> ignoreColumnsList)
0x10522  ret
```
