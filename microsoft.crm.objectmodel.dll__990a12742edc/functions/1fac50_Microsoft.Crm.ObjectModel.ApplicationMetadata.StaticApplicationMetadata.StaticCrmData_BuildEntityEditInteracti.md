# Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCrmData::BuildEntityEditInteractionCentricForm

- ea: `0x1fac50`
- end: `0x1fae3f`
- name: `Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCrmData::BuildEntityEditInteractionCentricForm`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0xa17c0`

## callees

- `0x1fac50`
- `0x1fae40`
- `0x1fca40`

## string_xrefs

- `0x1fad69`: `ModelUpdateActionProvider`
- `0x1fad73`: `UpdateRecord`
- `0x1fad86`: `RetrieveEditFormDataXmlActionProvider`
- `0x1fad90`: `EditRootRetrieveFormDataXml`
- `0x1fada3`: `CreateRecordActionProvider`
- `0x1fadad`: `CreateRecord`
- `0x1fadce`: `SetInteractionCentricCreateEntityReference`

## pseudocode

```c

```

## disassembly

```asm
0x1fac50  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ComponentDefinitionDescriptor::.ctor()
0x1fac55  stloc.0
0x1fac56  ldarg.2
0x1fac57  ldarg.s  6
0x1fac59  ldarg.s  9
0x1fac5b  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticForm::BuildInteractionCentricFormHeaderViewModel(bool isProcessControlEnabled, string primaryAttribute, class [Microsoft.Crm.Client.Shared]System.Dictionary tabNameLabelMap)
0x1fac60  stloc.1
0x1fac61  ldarg.s  5
0x1fac63  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticCrmData::CreateProcessStagePaneFlyoutViewModelDescriptor(int32 userLanguageCode)
0x1fac68  stloc.2
0x1fac69  ldloc.2
0x1fac6a  brfalse.s loc_1FAC73
0x1fac6c  ldarg.0
0x1fac6d  ldloc.2
0x1fac6e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::Add(var<u1>)
0x1fac73  ldarg.s  0xA
0x1fac75  brfalse.s loc_1FAC7F
0x1fac77  ldarg.0
0x1fac78  ldarg.s  0xA
0x1fac7a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::Add(var<u1>)
0x1fac7f  ldstr    aInteractioncen_22// "InteractionCentricFormBodyViewModel"
0x1fac84  ldstr    aInteractioncen_23// "InteractionCentricFormBody"
0x1fac89  ldstr    aInteractioncen_23// "InteractionCentricFormBody"
0x1fac8e  ldnull
0x1fac8f  ldnull
0x1fac90  ldarg.0
0x1fac91  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::ToArray()
0x1fac96  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor::.ctor(string, string, string, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[], class [Microsoft.Crm.Client.Shared]System.Dictionary, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor[])
0x1fac9b  stloc.3
0x1fac9c  ldstr    aInteractioncen_24// "InteractionCentricFormFooterViewModel"
0x1faca1  ldstr    aInteractioncen_25// "InteractionCentricFormFooter"
0x1faca6  ldstr    aInteractioncen_25// "InteractionCentricFormFooter"
0x1facab  ldnull
0x1facac  ldnull
0x1facad  ldc.i4.1
0x1facae  newarr   [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor
0x1facb3  dup
0x1facb4  ldc.i4.0
0x1facb5  ldstr    aLabel_0// "Label"
0x1facba  ldstr    aLabel// "label"
0x1facbf  ldstr    aEntitystatecod// "EntityStateCode"
0x1facc4  ldc.i4.1
0x1facc5  newarr   [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor
0x1facca  dup
0x1faccb  ldc.i4.0
0x1faccc  ldstr    aData// "Data"
0x1facd1  ldstr    aStatecode// "statecode"
0x1facd6  ldnull
0x1facd7  ldc.i4.0
0x1facd8  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ReferencePropertyDescriptor::.ctor(string, string, string, valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Validation.ValidatorType)
0x1facdd  stelem.ref
0x1facde  ldnull
0x1facdf  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor::.ctor(string, string, string, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[], class [Microsoft.Crm.Client.Shared]System.Dictionary)
0x1face4  stelem.ref
0x1face5  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor::.ctor(string, string, string, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[], class [Microsoft.Crm.Client.Shared]System.Dictionary, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor[])
0x1facea  stloc.s  4
0x1facec  newobj   instance void class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::.ctor()
0x1facf1  stloc.s  5
0x1facf3  ldloc.s  5
0x1facf5  ldloc.1
0x1facf6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::Add(var<u1>)
0x1facfb  ldloc.s  5
0x1facfd  ldloc.3
0x1facfe  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::Add(var<u1>)
0x1fad03  ldloc.s  5
0x1fad05  ldloc.s  4
0x1fad07  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::Add(var<u1>)
0x1fad0c  ldarg.1
0x1fad0d  brfalse.s loc_1FAD17
0x1fad0f  ldloc.s  5
0x1fad11  ldarg.1
0x1fad12  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::Add(var<u1>)
0x1fad17  ldstr    aInteractioncen_26// "InteractionCentricFormViewModel"
0x1fad1c  ldstr    aEditrootview// "EditRootView"
0x1fad21  ldstr    aEntityeditform// "EntityEditFormRootViewModel"
0x1fad26  ldc.i4.s 0xA
0x1fad28  newarr   [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor
0x1fad2d  dup
0x1fad2e  ldc.i4.0
0x1fad2f  ldstr    aAttributefield// "AttributeFieldNames"
0x1fad34  ldarg.3
0x1fad35  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0x1fad3a  stelem.ref
0x1fad3b  dup
0x1fad3c  ldc.i4.1
0x1fad3d  ldstr    aLabel_0// "Label"
0x1fad42  ldarg.s  7
0x1fad44  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0x1fad49  stelem.ref
0x1fad4a  dup
0x1fad4b  ldc.i4.2
0x1fad4c  ldstr    aGetmodelaction// "GetModelActionProvider"
0x1fad51  ldstr    aActionprovider// "ActionProvider"
0x1fad56  ldstr    aRetrieverecord// "RetrieveRecord"
0x1fad5b  ldnull
0x1fad5c  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.QueryDescriptor::.ctor(string, object)
0x1fad61  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ActionProviderPropertyDescriptor::.ctor(string, string, object)
0x1fad66  stelem.ref
0x1fad67  dup
0x1fad68  ldc.i4.3
0x1fad69  ldstr    aModelupdateact// "ModelUpdateActionProvider"
0x1fad6e  ldstr    aActionprovider// "ActionProvider"
0x1fad73  ldstr    aUpdaterecord// "UpdateRecord"
0x1fad78  ldnull
0x1fad79  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.QueryDescriptor::.ctor(string, object)
0x1fad7e  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ActionProviderPropertyDescriptor::.ctor(string, string, object)
0x1fad83  stelem.ref
0x1fad84  dup
0x1fad85  ldc.i4.4
0x1fad86  ldstr    aRetrieveeditfo// "RetrieveEditFormDataXmlActionProvider"
0x1fad8b  ldstr    aActionprovider// "ActionProvider"
0x1fad90  ldstr    aEditrootretrie// "EditRootRetrieveFormDataXml"
0x1fad95  ldnull
0x1fad96  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.QueryDescriptor::.ctor(string, object)
0x1fad9b  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ActionProviderPropertyDescriptor::.ctor(string, string, object)
0x1fada0  stelem.ref
0x1fada1  dup
0x1fada2  ldc.i4.5
0x1fada3  ldstr    aCreaterecordac// "CreateRecordActionProvider"
0x1fada8  ldstr    aActionprovider// "ActionProvider"
0x1fadad  ldstr    aCreaterecord// "CreateRecord"
0x1fadb2  ldsfld   string [mscorlib]System.String::Empty
0x1fadb7  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.QueryDescriptor::.ctor(string, object)
0x1fadbc  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ActionProviderPropertyDescriptor::.ctor(string, string, object)
0x1fadc1  stelem.ref
0x1fadc2  dup
0x1fadc3  ldc.i4.6
0x1fadc4  ldstr    aSetentityrefer// "SetEntityReferenceActionProvider"
0x1fadc9  ldstr    aActionprovider// "ActionProvider"
0x1fadce  ldstr    aSetinteraction// "SetInteractionCentricCreateEntityRefere"...
0x1fadd3  ldnull
0x1fadd4  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.QueryDescriptor::.ctor(string, object)
0x1fadd9  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ActionProviderPropertyDescriptor::.ctor(string, string, object)
0x1fadde  stelem.ref
0x1faddf  dup
0x1fade0  ldc.i4.7
0x1fade1  ldarg.2
0x1fade2  brtrue.s loc_1FADE7
0x1fade4  ldnull
0x1fade5  br.s     loc_1FAE01
0x1fade7  ldstr    aRetrieveproces_0// "RetrieveProcessActionProvider"
0x1fadec  ldstr    aActionprovider// "ActionProvider"
0x1fadf1  ldstr    aRetrieveintera// "RetrieveInteractionCentricProcessContro"...
0x1fadf6  ldnull
0x1fadf7  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.QueryDescriptor::.ctor(string, object)
0x1fadfc  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ActionProviderPropertyDescriptor::.ctor(string, string, object)
0x1fae01  stelem.ref
0x1fae02  dup
0x1fae03  ldc.i4.8
0x1fae04  ldstr    aHiddendatafiel// "HiddenDataFieldNames"
0x1fae09  ldarg.s  4
0x1fae0b  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0x1fae10  stelem.ref
0x1fae11  dup
0x1fae12  ldc.i4.s 9
0x1fae14  ldstr    aIscustomcontro// "IsCustomControlExists"
0x1fae19  ldarg.s  0xB
0x1fae1b  box      [mscorlib]System.Boolean
0x1fae20  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0x1fae25  stelem.ref
0x1fae26  ldnull
0x1fae27  ldloc.s  5
0x1fae29  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::ToArray()
0x1fae2e  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor::.ctor(string, string, string, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[], class [Microsoft.Crm.Client.Shared]System.Dictionary, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor[])
0x1fae33  stloc.s  6
0x1fae35  ldloc.0
0x1fae36  ldloc.s  6
0x1fae38  stfld    class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ComponentDefinitionDescriptor::ViewModelDescriptor
0x1fae3d  ldloc.0
0x1fae3e  ret
```
