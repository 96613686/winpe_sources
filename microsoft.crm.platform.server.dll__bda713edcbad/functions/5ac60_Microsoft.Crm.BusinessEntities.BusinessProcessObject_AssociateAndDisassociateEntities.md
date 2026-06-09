# Microsoft.Crm.BusinessEntities.BusinessProcessObject::AssociateAndDisassociateEntities

- ea: `0x5ac60`
- end: `0x5ad6f`
- name: `Microsoft.Crm.BusinessEntities.BusinessProcessObject::AssociateAndDisassociateEntities`
- size: `271`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5ad70`
- `0x5ae20`

## callees

- `0x5ac60`

## string_xrefs

- `0x5ac60`: `Microsoft.Crm.Common.ObjectModel`
- `0x5ac7d`: `Microsoft.Crm.Common.ObjectModel.ProductAssociationService`
- `0x5accb`: `Microsoft.Crm.Common.ObjectModel.ProductAssociationService`
- `0x5aca4`: `Microsoft.Crm.Common.ObjectModel.ProductSubstituteService`
- `0x5acf2`: `Microsoft.Crm.Common.ObjectModel.ProductSubstituteService`

## pseudocode

```c

```

## disassembly

```asm
0x5ac60  ldstr    aMicrosoftCrmCo// "Microsoft.Crm.Common.ObjectModel"
0x5ac65  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x5ac6a  stloc.0
0x5ac6b  ldnull
0x5ac6c  stloc.1
0x5ac6d  ldnull
0x5ac6e  stloc.2
0x5ac6f  ldarg.1
0x5ac70  ldstr    aProductassocia// "productassociation_association"
0x5ac75  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5ac7a  brfalse.s loc_5AC96
0x5ac7c  ldloc.0
0x5ac7d  ldstr    aMicrosoftCrmCo_0// "Microsoft.Crm.Common.ObjectModel.Produc"...
0x5ac82  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x5ac87  stloc.1
0x5ac88  ldloc.1
0x5ac89  ldstr    aAssociateprodu// "AssociateProductAssociationEntities"
0x5ac8e  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string)
0x5ac93  stloc.2
0x5ac94  br.s     loc_5AD09
0x5ac96  ldarg.1
0x5ac97  ldstr    aProductsubstit// "productsubstitute_association"
0x5ac9c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5aca1  brfalse.s loc_5ACBD
0x5aca3  ldloc.0
0x5aca4  ldstr    aMicrosoftCrmCo_1// "Microsoft.Crm.Common.ObjectModel.Produc"...
0x5aca9  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x5acae  stloc.1
0x5acaf  ldloc.1
0x5acb0  ldstr    aAssociateprodu_0// "AssociateProductSubstituteEntities"
0x5acb5  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string)
0x5acba  stloc.2
0x5acbb  br.s     loc_5AD09
0x5acbd  ldarg.1
0x5acbe  ldstr    aProductdisasso// "productDisassociation_association"
0x5acc3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5acc8  brfalse.s loc_5ACE4
0x5acca  ldloc.0
0x5accb  ldstr    aMicrosoftCrmCo_0// "Microsoft.Crm.Common.ObjectModel.Produc"...
0x5acd0  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x5acd5  stloc.1
0x5acd6  ldloc.1
0x5acd7  ldstr    aDisassociatepr// "DisassociateProductAssociationEntities"
0x5acdc  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string)
0x5ace1  stloc.2
0x5ace2  br.s     loc_5AD09
0x5ace4  ldarg.1
0x5ace5  ldstr    aProductdissubs// "productDissubstitute_association"
0x5acea  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5acef  brfalse.s loc_5AD09
0x5acf1  ldloc.0
0x5acf2  ldstr    aMicrosoftCrmCo_1// "Microsoft.Crm.Common.ObjectModel.Produc"...
0x5acf7  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x5acfc  stloc.1
0x5acfd  ldloc.1
0x5acfe  ldstr    aDisassociatepr_0// "DisassociateProductSubstituteEntities"
0x5ad03  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string)
0x5ad08  stloc.2
0x5ad09  ldloc.1
0x5ad0a  ldnull
0x5ad0b  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x5ad10  brtrue.s loc_5AD1B
0x5ad12  ldloc.2
0x5ad13  ldnull
0x5ad14  call     bool [mscorlib]System.Reflection.MethodInfo::op_Equality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0x5ad19  brfalse.s loc_5AD4D
0x5ad1b  ldnull
0x5ad1c  ldarg.s  4
0x5ad1e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5ad23  ldc.i4.s 0x14
0x5ad25  ldstr    a0// "{0}"
0x5ad2a  ldc.i4.1
0x5ad2b  newarr   [mscorlib]System.Object
0x5ad30  dup
0x5ad31  ldc.i4.0
0x5ad32  ldstr    aInvalidAssocia// "Invalid association type found in Assoc"...
0x5ad37  stelem.ref
0x5ad38  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5ad3d  ldstr    aInvalidOperati_7// "Invalid operation : Unsupported associa"...
0x5ad42  ldc.i4   0x8004023B
0x5ad47  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x5ad4c  throw
0x5ad4d  ldloc.2
0x5ad4e  ldloc.1
0x5ad4f  ldnull
0x5ad50  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type, object[])
0x5ad55  ldc.i4.3
0x5ad56  newarr   [mscorlib]System.Object
0x5ad5b  dup
0x5ad5c  ldc.i4.0
0x5ad5d  ldarg.2
0x5ad5e  stelem.ref
0x5ad5f  dup
0x5ad60  ldc.i4.1
0x5ad61  ldarg.3
0x5ad62  stelem.ref
0x5ad63  dup
0x5ad64  ldc.i4.2
0x5ad65  ldarg.s  4
0x5ad67  stelem.ref
0x5ad68  callvirt instance object [mscorlib]System.Reflection.MethodBase::Invoke(object, object[])
0x5ad6d  pop
0x5ad6e  ret
```
