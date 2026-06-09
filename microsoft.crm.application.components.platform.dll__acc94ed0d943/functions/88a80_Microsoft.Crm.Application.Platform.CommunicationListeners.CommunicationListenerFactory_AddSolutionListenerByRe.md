# Microsoft.Crm.Application.Platform.CommunicationListeners.CommunicationListenerFactory::AddSolutionListenerByRequestName

- ea: `0x88a80`
- end: `0x88d5d`
- name: `Microsoft.Crm.Application.Platform.CommunicationListeners.CommunicationListenerFactory::AddSolutionListenerByRequestName`
- size: `733`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x88570`

## callees

- `0x88710`
- `0x88a80`
- `0x890b0`
- `0x9ca50`

## string_xrefs

- `0x88d04`: `CreateRequest`
- `0x88d20`: `UpdateRequest`
- `0x88bd0`: `RetrieveExternalRequiredComponentsRequest`
- `0x88be1`: `CreateEntityRequest`
- `0x88bf2`: `UpdateEntityRequest`
- `0x88c03`: `CreateAttributeRequest`
- `0x88c14`: `UpdateAttributeRequest`
- `0x88c25`: `CreateManyToManyRequest`
- `0x88c36`: `CreateOneToManyRequest`
- `0x88c47`: `UpdateRelationshipRequest`
- `0x88c58`: `CreateOptionSetRequest`
- `0x88c69`: `UpdateOptionSetRequest`
- `0x88c7a`: `DeleteOptionValueRequest`
- `0x88c9c`: `UpdateOptionValueRequest`
- `0x88ccc`: `AddPrivilegesRoleRequest`
- `0x88cda`: `ReplacePrivilegesRoleRequest`
- `0x88ce8`: `RemovePrivilegeRoleRequest`
- `0x88cf6`: `MakeAvailableToOrganizationTemplateRequest`
- `0x88d12`: `CreateFromTemplateRequest`
- `0x88d2e`: `UpdateFromTemplateRequest`
- `0x88d3c`: `CopySystemFormRequest`

## pseudocode

```c

```

## disassembly

```asm
0x88a80  ldarg.1
0x88a81  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x88a86  stloc.0
0x88a87  ldloc.0
0x88a88  ldc.i4   0x7A2570F3
0x88a8d  bgt.un   loc_88B32
0x88a92  ldloc.0
0x88a93  ldc.i4   0x4289790D
0x88a98  bgt.un.s loc_88AE6
0x88a9a  ldloc.0
0x88a9b  ldc.i4   0x1F0350AC
0x88aa0  bgt.un.s loc_88AC4
0x88aa2  ldloc.0
0x88aa3  ldc.i4   0x112CEC8D
0x88aa8  beq      loc_88D1F
0x88aad  ldloc.0
0x88aae  ldc.i4   0x1CCEEECB
0x88ab3  beq      loc_88D2D
0x88ab8  ldloc.0
0x88ab9  ldc.i4   0x1F0350AC
0x88abe  beq      loc_88CAC
0x88ac3  ret
0x88ac4  ldloc.0
0x88ac5  ldc.i4   0x224212F0
0x88aca  beq      loc_88CD9
0x88acf  ldloc.0
0x88ad0  ldc.i4   0x229DDA0F
0x88ad5  beq      loc_88C9B
0x88ada  ldloc.0
0x88adb  ldc.i4   0x4289790D
0x88ae0  beq      loc_88C79
0x88ae5  ret
0x88ae6  ldloc.0
0x88ae7  ldc.i4   0x4EF9A7CC
0x88aec  bgt.un.s loc_88B10
0x88aee  ldloc.0
0x88aef  ldc.i4   0x42CA03EF
0x88af4  beq      loc_88BE0
0x88af9  ldloc.0
0x88afa  ldc.i4   0x437BFDA4
0x88aff  beq      loc_88BCF
0x88b04  ldloc.0
0x88b05  ldc.i4   0x4EF9A7CC
0x88b0a  beq      loc_88D11
0x88b0f  ret
0x88b10  ldloc.0
0x88b11  ldc.i4   0x59BC961D
0x88b16  beq      loc_88C57
0x88b1b  ldloc.0
0x88b1c  ldc.i4   0x64B88230
0x88b21  beq      loc_88BF1
0x88b26  ldloc.0
0x88b27  ldc.i4   0x7A2570F3
0x88b2c  beq      loc_88CF5
0x88b31  ret
0x88b32  ldloc.0
0x88b33  ldc.i4   0x8A462DA3
0x88b38  bgt.un.s loc_88B86
0x88b3a  ldloc.0
0x88b3b  ldc.i4   0x7C37E1E0
0x88b40  bgt.un.s loc_88B64
0x88b42  ldloc.0
0x88b43  ldc.i4   0x7B7FD02D
0x88b48  beq      loc_88C13
0x88b4d  ldloc.0
0x88b4e  ldc.i4   0x7BDBD0ED
0x88b53  beq      loc_88CCB
0x88b58  ldloc.0
0x88b59  ldc.i4   0x7C37E1E0
0x88b5e  beq      loc_88D3B
0x88b63  ret
0x88b64  ldloc.0
0x88b65  ldc.i4   0x7E9DB0D8
0x88b6a  beq      loc_88C02
0x88b6f  ldloc.0
0x88b70  ldc.i4   0x85CA9E27
0x88b75  beq      loc_88C46
0x88b7a  ldloc.0
0x88b7b  ldc.i4   0x8A462DA3
0x88b80  beq      loc_88C8A
0x88b85  ret
0x88b86  ldloc.0
0x88b87  ldc.i4   0xC130CC22
0x88b8c  bgt.un.s loc_88BB0
0x88b8e  ldloc.0
0x88b8f  ldc.i4   0x9C93D08F
0x88b94  beq      loc_88CBD
0x88b99  ldloc.0
0x88b9a  ldc.i4   0xA8C03FD5
0x88b9f  beq      loc_88CE7
0x88ba4  ldloc.0
0x88ba5  ldc.i4   0xC130CC22
0x88baa  beq      loc_88C35
0x88baf  ret
0x88bb0  ldloc.0
0x88bb1  ldc.i4   0xEBFD0969
0x88bb6  beq.s    loc_88C24
0x88bb8  ldloc.0
0x88bb9  ldc.i4   0xF663FCDA
0x88bbe  beq      loc_88D03
0x88bc3  ldloc.0
0x88bc4  ldc.i4   0xFF84D274
0x88bc9  beq      loc_88C68
0x88bce  ret
0x88bcf  ldarg.1
0x88bd0  ldstr    aRetrieveextern// "RetrieveExternalRequiredComponentsReque"...
0x88bd5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88bda  brtrue   loc_88D49
0x88bdf  ret
0x88be0  ldarg.1
0x88be1  ldstr    aCreateentityre// "CreateEntityRequest"
0x88be6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88beb  brtrue   loc_88D49
0x88bf0  ret
0x88bf1  ldarg.1
0x88bf2  ldstr    aUpdateentityre// "UpdateEntityRequest"
0x88bf7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88bfc  brtrue   loc_88D49
0x88c01  ret
0x88c02  ldarg.1
0x88c03  ldstr    aCreateattribut_0// "CreateAttributeRequest"
0x88c08  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88c0d  brtrue   loc_88D49
0x88c12  ret
0x88c13  ldarg.1
0x88c14  ldstr    aUpdateattribut// "UpdateAttributeRequest"
0x88c19  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88c1e  brtrue   loc_88D49
0x88c23  ret
0x88c24  ldarg.1
0x88c25  ldstr    aCreatemanytoma// "CreateManyToManyRequest"
0x88c2a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88c2f  brtrue   loc_88D49
0x88c34  ret
0x88c35  ldarg.1
0x88c36  ldstr    aCreateonetoman// "CreateOneToManyRequest"
0x88c3b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88c40  brtrue   loc_88D49
0x88c45  ret
0x88c46  ldarg.1
0x88c47  ldstr    aUpdaterelation// "UpdateRelationshipRequest"
0x88c4c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88c51  brtrue   loc_88D49
0x88c56  ret
0x88c57  ldarg.1
0x88c58  ldstr    aCreateoptionse// "CreateOptionSetRequest"
0x88c5d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88c62  brtrue   loc_88D49
0x88c67  ret
0x88c68  ldarg.1
0x88c69  ldstr    aUpdateoptionse// "UpdateOptionSetRequest"
0x88c6e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88c73  brtrue   loc_88D49
0x88c78  ret
0x88c79  ldarg.1
0x88c7a  ldstr    aDeleteoptionva// "DeleteOptionValueRequest"
0x88c7f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88c84  brtrue   loc_88D49
0x88c89  ret
0x88c8a  ldarg.1
0x88c8b  ldstr    aInsertoptionva// "InsertOptionValueRequest"
0x88c90  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88c95  brtrue   loc_88D49
0x88c9a  ret
0x88c9b  ldarg.1
0x88c9c  ldstr    aUpdateoptionva// "UpdateOptionValueRequest"
0x88ca1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88ca6  brtrue   loc_88D49
0x88cab  ret
0x88cac  ldarg.1
0x88cad  ldstr    aInsertstatusva// "InsertStatusValueRequest"
0x88cb2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88cb7  brtrue   loc_88D49
0x88cbc  ret
0x88cbd  ldarg.1
0x88cbe  ldstr    aOrderoptionreq// "OrderOptionRequest"
0x88cc3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88cc8  brtrue.s loc_88D49
0x88cca  ret
0x88ccb  ldarg.1
0x88ccc  ldstr    aAddprivilegesr// "AddPrivilegesRoleRequest"
0x88cd1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88cd6  brtrue.s loc_88D49
0x88cd8  ret
0x88cd9  ldarg.1
0x88cda  ldstr    aReplaceprivile// "ReplacePrivilegesRoleRequest"
0x88cdf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88ce4  brtrue.s loc_88D49
0x88ce6  ret
0x88ce7  ldarg.1
0x88ce8  ldstr    aRemoveprivileg// "RemovePrivilegeRoleRequest"
0x88ced  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88cf2  brtrue.s loc_88D49
0x88cf4  ret
0x88cf5  ldarg.1
0x88cf6  ldstr    aMakeavailablet// "MakeAvailableToOrganizationTemplateRequ"...
0x88cfb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88d00  brtrue.s loc_88D49
0x88d02  ret
0x88d03  ldarg.1
0x88d04  ldstr    aCreaterequest// "CreateRequest"
0x88d09  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88d0e  brtrue.s loc_88D55
0x88d10  ret
0x88d11  ldarg.1
0x88d12  ldstr    aCreatefromtemp// "CreateFromTemplateRequest"
0x88d17  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88d1c  brtrue.s loc_88D55
0x88d1e  ret
0x88d1f  ldarg.1
0x88d20  ldstr    aUpdaterequest// "UpdateRequest"
0x88d25  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88d2a  brtrue.s loc_88D55
0x88d2c  ret
0x88d2d  ldarg.1
0x88d2e  ldstr    aUpdatefromtemp// "UpdateFromTemplateRequest"
0x88d33  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88d38  brtrue.s loc_88D55
0x88d3a  ret
0x88d3b  ldarg.1
0x88d3c  ldstr    aCopysystemform// "CopySystemFormRequest"
0x88d41  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88d46  brtrue.s loc_88D55
0x88d48  ret
0x88d49  ldarg.0
0x88d4a  newobj   instance void Microsoft.Crm.Application.Platform.CommunicationListeners.SolutionListener::.ctor()
0x88d4f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.CommunicationListeners.EventListener>::Add(var<u1>)
0x88d54  ret
0x88d55  ldarg.0
0x88d56  ldarg.2
0x88d57  call     void Microsoft.Crm.Application.Platform.CommunicationListeners.CommunicationListenerFactory::AddSolutionListenerBySolutionComponents(class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.CommunicationListeners.EventListener> eventListeners, string entityName)
0x88d5c  ret
```
