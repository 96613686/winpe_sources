# Microsoft.Crm.Solution.SolutionComponentTypeMap::AddFirstPartySolutionAwareComponents

- ea: `0x8090`
- end: `0x8296`
- name: `Microsoft.Crm.Solution.SolutionComponentTypeMap::AddFirstPartySolutionAwareComponents`
- size: `518`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x77d0`

## callees

- `0x74c0`
- `0x82a0`

## string_xrefs

- `0x80af`: `Privilege`
- `0x80c5`: `PrivilegeObjectTypeCode`
- `0x819f`: `ComplexControl`

## pseudocode

```c

```

## disassembly

```asm
0x8090  ldarg.0
0x8091  ldc.i4   0xC9
0x8096  ldstr    aSdkmessage// "SdkMessage"
0x809b  ldc.i4   0x11FE
0x80a0  ldc.i4.0
0x80a1  ldc.i4.1
0x80a2  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x80a7  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x80ac  ldarg.0
0x80ad  ldc.i4.s 0x10
0x80af  ldstr    aPrivilege// "Privilege"
0x80b4  ldc.i4.s 9
0x80b6  ldc.i4.1
0x80b7  ldc.i4.1
0x80b8  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x80bd  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x80c2  ldarg.0
0x80c3  ldc.i4.s 0x11
0x80c5  ldstr    aPrivilegeobjec// "PrivilegeObjectTypeCode"
0x80ca  ldc.i4.s 0xA
0x80cc  ldc.i4.1
0x80cd  ldc.i4.1
0x80ce  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x80d3  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x80d8  ldarg.0
0x80d9  ldc.i4   0xCA
0x80de  ldstr    aSdkmessagefilt// "SdkMessageFilter"
0x80e3  ldc.i4   0x11FF
0x80e8  ldc.i4.0
0x80e9  ldc.i4.1
0x80ea  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x80ef  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x80f4  ldarg.0
0x80f5  ldc.i4   0xCB
0x80fa  ldstr    aSdkmessagepair// "SdkMessagePair"
0x80ff  ldc.i4   0x1205
0x8104  ldc.i4.0
0x8105  ldc.i4.0
0x8106  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x810b  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x8110  ldarg.0
0x8111  ldc.i4   0xCC
0x8116  ldstr    aSdkmessagerequ// "SdkMessageRequest"
0x811b  ldc.i4   0x1201
0x8120  ldc.i4.0
0x8121  ldc.i4.0
0x8122  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x8127  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x812c  ldarg.0
0x812d  ldc.i4   0xCD
0x8132  ldstr    aSdkmessagerequ_0// "SdkMessageRequestField"
0x8137  ldc.i4   0x1206
0x813c  ldc.i4.0
0x813d  ldc.i4.0
0x813e  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x8143  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x8148  ldarg.0
0x8149  ldc.i4   0xCE
0x814e  ldstr    aSdkmessageresp// "SdkMessageResponse"
0x8153  ldc.i4   0x1202
0x8158  ldc.i4.0
0x8159  ldc.i4.0
0x815a  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x815f  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x8164  ldarg.0
0x8165  ldc.i4   0xCF
0x816a  ldstr    aSdkmessageresp_0// "SdkMessageResponseField"
0x816f  ldc.i4   0x1203
0x8174  ldc.i4.0
0x8175  ldc.i4.0
0x8176  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x817b  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x8180  ldarg.0
0x8181  ldc.i4   0xD2
0x8186  ldstr    aWebwizard// "WebWizard"
0x818b  ldc.i4   0x12C0
0x8190  ldc.i4.0
0x8191  ldc.i4.1
0x8192  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x8197  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x819c  ldarg.0
0x819d  ldc.i4.s 0x40
0x819f  ldstr    aComplexcontrol// "ComplexControl"
0x81a4  ldc.i4   0x25B2
0x81a9  ldc.i4.0
0x81aa  ldc.i4.1
0x81ab  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x81b0  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x81b5  ldarg.0
0x81b6  ldc.i4   0xD0
0x81bb  ldstr    aImportmap// "ImportMap"
0x81c0  ldc.i4   0x113B
0x81c5  ldc.i4.0
0x81c6  ldc.i4.1
0x81c7  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x81cc  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x81d1  ldarg.0
0x81d2  ldc.i4   0xD4
0x81d7  ldstr    aImportentityma// "ImportEntityMapping"
0x81dc  ldc.i4   0x114C
0x81e1  ldc.i4.0
0x81e2  ldc.i4.0
0x81e3  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x81e8  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x81ed  ldarg.0
0x81ee  ldc.i4   0xD5
0x81f3  ldstr    aColumnmapping// "ColumnMapping"
0x81f8  ldc.i4   0x1141
0x81fd  ldc.i4.0
0x81fe  ldc.i4.0
0x81ff  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x8204  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x8209  ldarg.0
0x820a  ldc.i4   0xD6
0x820f  ldstr    aLookupmapping// "LookUpMapping"
0x8214  ldc.i4   0x1143
0x8219  ldc.i4.0
0x821a  ldc.i4.0
0x821b  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x8220  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x8225  ldarg.0
0x8226  ldc.i4   0xD7
0x822b  ldstr    aPicklistmappin// "PickListMapping"
0x8230  ldc.i4   0x1142
0x8235  ldc.i4.0
0x8236  ldc.i4.0
0x8237  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x823c  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x8241  ldarg.0
0x8242  ldc.i4   0xD8
0x8247  ldstr    aTransformation// "TransformationMapping"
0x824c  ldc.i4   0x114A
0x8251  ldc.i4.0
0x8252  ldc.i4.0
0x8253  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x8258  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x825d  ldarg.0
0x825e  ldc.i4   0xD9
0x8263  ldstr    aTransformation_0// "TransformationParameterMapping"
0x8268  ldc.i4   0x114B
0x826d  ldc.i4.0
0x826e  ldc.i4.0
0x826f  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x8274  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x8279  ldarg.0
0x827a  ldc.i4   0xDD
0x827f  ldstr    aOwnermapping// "OwnerMapping"
0x8284  ldc.i4   0x1144
0x8289  ldc.i4.0
0x828a  ldc.i4.0
0x828b  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x8290  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x8295  ret
```
