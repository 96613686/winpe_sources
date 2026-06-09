# Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildGuidedHelpCommand

- ea: `0x1f9760`
- end: `0x1f99aa`
- name: `Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCommandBarMetadata::BuildGuidedHelpCommand`
- size: `586`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1f9530`
- `0x1f9f50`

## callees

- `0x1f9760`

## string_xrefs

- `0x1f978a`: `GuidedHelpCommand`
- `0x1f9838`: `GuidedHelpCommand`
- `0x1f988e`: `ContentLibraryCommand`
- `0x1f994e`: `ContentLibraryCommand`
- `0x1f9795`: `IsEntityCommand`
- `0x1f989a`: `IsEntityCommand`
- `0x1f9966`: `Learning Path privilege missing for userId: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1f9760  ldc.i4.0
0x1f9761  newarr   [mscorlib]System.Object
0x1f9766  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0x1f976b  stloc.0
0x1f976c  ldc.i4.0
0x1f976d  newarr   [mscorlib]System.Object
0x1f9772  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0x1f9777  stloc.1
0x1f9778  ldc.i4.0
0x1f9779  newarr   [mscorlib]System.Object
0x1f977e  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0x1f9783  stloc.2
0x1f9784  ldloc.2
0x1f9785  ldstr    aId_0// "Id"
0x1f978a  ldstr    aGuidedhelpcomm// "GuidedHelpCommand"
0x1f978f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1f9794  ldloc.2
0x1f9795  ldstr    aIsentitycomman// "IsEntityCommand"
0x1f979a  ldc.i4.0
0x1f979b  box      [mscorlib]System.Boolean
0x1f97a0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1f97a5  newobj   instance void class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]System.Dictionary>::.ctor()
0x1f97aa  stloc.3
0x1f97ab  ldc.i4.0
0x1f97ac  newarr   [mscorlib]System.Object
0x1f97b1  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0x1f97b6  stloc.s  4
0x1f97b8  ldloc.s  4
0x1f97ba  ldstr    aActiontype// "ActionType"
0x1f97bf  ldc.i4.3
0x1f97c0  box      [mscorlib]System.Int32
0x1f97c5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1f97ca  ldc.i4.0
0x1f97cb  newarr   [mscorlib]System.Object
0x1f97d0  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0x1f97d5  stloc.s  5
0x1f97d7  ldloc.s  5
0x1f97d9  ldstr    aFunctionname_0// "FunctionName"
0x1f97de  ldstr    aCheckforguided// "checkForGuidedHelp"
0x1f97e3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1f97e8  ldloc.s  5
0x1f97ea  ldstr    aLibrary_0// "Library"
0x1f97ef  ldstr    aWebresourceMsd// "$webresource:msdyn_LoadGuidedHelpMoCA.j"...
0x1f97f4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1f97f9  ldloc.s  4
0x1f97fb  ldstr    aAttributes_1// "Attributes"
0x1f9800  ldloc.s  5
0x1f9802  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1f9807  ldloc.3
0x1f9808  ldloc.s  4
0x1f980a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]System.Dictionary>::Add(var<u1>)
0x1f980f  ldloc.2
0x1f9810  ldstr    aActions// "Actions"
0x1f9815  ldloc.3
0x1f9816  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1f981b  ldloc.2
0x1f981c  ldstr    aEnablerules// "EnableRules"
0x1f9821  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x1f9826  dup
0x1f9827  ldstr    aIsguidedhelpen// "IsGuidedHelpEnabled"
0x1f982c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x1f9831  pop
0x1f9832  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1f9837  ldloc.1
0x1f9838  ldstr    aGuidedhelpcomm// "GuidedHelpCommand"
0x1f983d  ldloc.2
0x1f983e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1f9843  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetCallerAndBusinessGuids()
0x1f9848  stloc.s  6
0x1f984a  ldloc.s  6
0x1f984c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_OrganizationId()
0x1f9851  ldc.i4.0
0x1f9852  ldc.i4.0
0x1f9853  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1f9858  stloc.s  7
0x1f985a  ldloc.s  7
0x1f985c  ldc.i4.0
0x1f985d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(bool)
0x1f9862  ldloc.s  6
0x1f9864  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_UserId()
0x1f9869  ldstr    a9fd3540fE2c14e// "{9FD3540F-E2C1-4EEA-B7E2-620C3719DDC5}"
0x1f986e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1f9873  ldloc.s  7
0x1f9875  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilege(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1f987a  ldc.i4.0
0x1f987b  newarr   [mscorlib]System.Object
0x1f9880  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0x1f9885  stloc.s  8
0x1f9887  ldloc.s  8
0x1f9889  ldstr    aId_0// "Id"
0x1f988e  ldstr    aContentlibrary_0// "ContentLibraryCommand"
0x1f9893  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1f9898  ldloc.s  8
0x1f989a  ldstr    aIsentitycomman// "IsEntityCommand"
0x1f989f  ldc.i4.0
0x1f98a0  box      [mscorlib]System.Boolean
0x1f98a5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1f98aa  newobj   instance void class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]System.Dictionary>::.ctor()
0x1f98af  stloc.s  9
0x1f98b1  ldc.i4.0
0x1f98b2  newarr   [mscorlib]System.Object
0x1f98b7  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0x1f98bc  stloc.s  0xA
0x1f98be  ldloc.s  0xA
0x1f98c0  ldstr    aActiontype// "ActionType"
0x1f98c5  ldc.i4.3
0x1f98c6  box      [mscorlib]System.Int32
0x1f98cb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1f98d0  ldc.i4.0
0x1f98d1  newarr   [mscorlib]System.Object
0x1f98d6  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0x1f98db  stloc.s  0xB
0x1f98dd  ldloc.s  0xB
0x1f98df  ldstr    aFunctionname_0// "FunctionName"
0x1f98e4  ldstr    aLaunchlplibrar// "launchLPLibrary"
0x1f98e9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1f98ee  ldloc.s  0xB
0x1f98f0  ldstr    aLibrary_0// "Library"
0x1f98f5  ldstr    aWebresourceMsd// "$webresource:msdyn_LoadGuidedHelpMoCA.j"...
0x1f98fa  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1f98ff  ldloc.s  0xA
0x1f9901  ldstr    aAttributes_1// "Attributes"
0x1f9906  ldloc.s  0xB
0x1f9908  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1f990d  ldloc.s  9
0x1f990f  ldloc.s  0xA
0x1f9911  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]System.Dictionary>::Add(var<u1>)
0x1f9916  ldloc.s  8
0x1f9918  ldstr    aActions// "Actions"
0x1f991d  ldloc.s  9
0x1f991f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1f9924  ldloc.s  8
0x1f9926  ldstr    aEnablerules// "EnableRules"
0x1f992b  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x1f9930  dup
0x1f9931  ldstr    aIsguidedhelpen// "IsGuidedHelpEnabled"
0x1f9936  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x1f993b  pop
0x1f993c  dup
0x1f993d  ldstr    aLplibraryenabl// "LPLibraryEnabled"
0x1f9942  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x1f9947  pop
0x1f9948  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1f994d  ldloc.1
0x1f994e  ldstr    aContentlibrary_0// "ContentLibraryCommand"
0x1f9953  ldloc.s  8
0x1f9955  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1f995a  leave.s  loc_1F9987
0x1f995c  pop
0x1f995d  ldloc.s  7
0x1f995f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1f9964  ldc.i4.s 0x11
0x1f9966  ldstr    aLearningPathPr// "Learning Path privilege missing for use"...
0x1f996b  ldc.i4.1
0x1f996c  newarr   [mscorlib]System.Object
0x1f9971  dup
0x1f9972  ldc.i4.0
0x1f9973  ldloc.s  6
0x1f9975  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_UserId()
0x1f997a  box      [mscorlib]System.Guid
0x1f997f  stelem.ref
0x1f9980  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1f9985  leave.s  loc_1F9987
0x1f9987  ldloc.s  7
0x1f9989  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x1f998e  leave.s  loc_1F999C
0x1f9990  ldloc.s  7
0x1f9992  brfalse.s loc_1F999B
0x1f9994  ldloc.s  7
0x1f9996  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f999b  endfinally
0x1f999c  ldloc.0
0x1f999d  ldstr    aNull// "null"
0x1f99a2  ldloc.1
0x1f99a3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1f99a8  ldloc.0
0x1f99a9  ret
```
