# Microsoft.Crm.ObjectModel.DependencyFilter::SetDependencyValues

- ea: `0x1afe60`
- end: `0x1aff5d`
- name: `Microsoft.Crm.ObjectModel.DependencyFilter::SetDependencyValues`
- size: `253`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1aea00`
- `0x1aec80`
- `0x1afbe0`
- `0x1afce0`
- `0x1aff60`
- `0x1affa0`
- `0x1b0160`

## callees

- `0x1afe60`

## string_xrefs

- `0x1afe80`: `componenttype`
- `0x1afefe`: `componenttype`
- `0x1afe90`: `requiredcomponentobjectid`
- `0x1afe7a`: `requiredcomponenttype`
- `0x1aff0e`: `dependentcomponentobjectid`
- `0x1afef8`: `dependentcomponenttype`
- `0x1afee2`: `dependentcomponentnodeid`
- `0x1afe64`: `requiredcomponentnodeid`
- `0x1aff24`: `dependentcomponentbasesolutionid`
- `0x1aff47`: `dependentcomponentparentid`
- `0x1afec9`: `requiredcomponentparentid`
- `0x1afea6`: `requiredcomponentbasesolutionid`

## pseudocode

```c

```

## disassembly

```asm
0x1afe60  ldarg.2
0x1afe61  brfalse.s loc_1AFEDE
0x1afe63  ldarg.1
0x1afe64  ldstr    aRequiredcompon_1// "requiredcomponentnodeid"
0x1afe69  ldarg.2
0x1afe6a  ldstr    aDependencynode_0// "dependencynodeid"
0x1afe6f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1afe74  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1afe79  ldarg.1
0x1afe7a  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x1afe7f  ldarg.2
0x1afe80  ldstr    aComponenttype// "componenttype"
0x1afe85  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1afe8a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1afe8f  ldarg.1
0x1afe90  ldstr    aRequiredcompon// "requiredcomponentobjectid"
0x1afe95  ldarg.2
0x1afe96  ldstr    aObjectid// "objectid"
0x1afe9b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1afea0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1afea5  ldarg.1
0x1afea6  ldstr    aRequiredcompon_12// "requiredcomponentbasesolutionid"
0x1afeab  ldarg.2
0x1afeac  ldstr    aBasesolutionid// "basesolutionid"
0x1afeb1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1afeb6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1afebb  ldarg.2
0x1afebc  ldstr    aParentid// "parentid"
0x1afec1  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1afec6  brtrue.s loc_1AFEDE
0x1afec8  ldarg.1
0x1afec9  ldstr    aRequiredcompon_11// "requiredcomponentparentid"
0x1afece  ldarg.2
0x1afecf  ldstr    aParentid// "parentid"
0x1afed4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1afed9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1afede  ldarg.3
0x1afedf  brfalse.s loc_1AFF5C
0x1afee1  ldarg.1
0x1afee2  ldstr    aDependentcompo_1// "dependentcomponentnodeid"
0x1afee7  ldarg.3
0x1afee8  ldstr    aDependencynode_0// "dependencynodeid"
0x1afeed  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1afef2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1afef7  ldarg.1
0x1afef8  ldstr    aDependentcompo_0// "dependentcomponenttype"
0x1afefd  ldarg.3
0x1afefe  ldstr    aComponenttype// "componenttype"
0x1aff03  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1aff08  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1aff0d  ldarg.1
0x1aff0e  ldstr    aDependentcompo// "dependentcomponentobjectid"
0x1aff13  ldarg.3
0x1aff14  ldstr    aObjectid// "objectid"
0x1aff19  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1aff1e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1aff23  ldarg.1
0x1aff24  ldstr    aDependentcompo_3// "dependentcomponentbasesolutionid"
0x1aff29  ldarg.3
0x1aff2a  ldstr    aBasesolutionid// "basesolutionid"
0x1aff2f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1aff34  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1aff39  ldarg.3
0x1aff3a  ldstr    aParentid// "parentid"
0x1aff3f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1aff44  brtrue.s loc_1AFF5C
0x1aff46  ldarg.1
0x1aff47  ldstr    aDependentcompo_4// "dependentcomponentparentid"
0x1aff4c  ldarg.3
0x1aff4d  ldstr    aParentid// "parentid"
0x1aff52  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1aff57  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1aff5c  ret
```
