# Microsoft.Crm.Service.ObjectModel.IncidentService::ValidateIfEntitlementIsValid

- ea: `0x1210`
- end: `0x1452`
- name: `Microsoft.Crm.Service.ObjectModel.IncidentService::ValidateIfEntitlementIsValid`
- size: `578`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1210`
- `0xb4f0`
- `0xb8e0`

## pseudocode

```c

```

## disassembly

```asm
0x1210  ldnull
0x1211  stloc.0
0x1212  ldnull
0x1213  stloc.1
0x1214  ldnull
0x1215  stloc.2
0x1216  ldnull
0x1217  stloc.3
0x1218  ldnull
0x1219  stloc.s  4
0x121b  ldstr    aEntitlement// "Entitlement"
0x1220  ldarg.2
0x1221  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1226  stloc.s  5
0x1228  ldarg.1
0x1229  ldstr    aCustomerid// "customerid"
0x122e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1233  brfalse.s loc_125D
0x1235  ldarg.1
0x1236  ldstr    aCustomerid// "customerid"
0x123b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1240  callvirt instance string [mscorlib]System.Object::ToString()
0x1245  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x124a  brtrue.s loc_125D
0x124c  ldarg.1
0x124d  ldstr    aCustomerid// "customerid"
0x1252  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1257  callvirt instance string [mscorlib]System.Object::ToString()
0x125c  stloc.1
0x125d  ldarg.1
0x125e  ldstr    aProductid// "productid"
0x1263  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1268  brfalse.s loc_127B
0x126a  ldarg.1
0x126b  ldstr    aProductid// "productid"
0x1270  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1275  callvirt instance string [mscorlib]System.Object::ToString()
0x127a  stloc.0
0x127b  ldarg.1
0x127c  ldstr    aEntitlementid// "entitlementid"
0x1281  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1286  brfalse.s loc_1299
0x1288  ldarg.1
0x1289  ldstr    aEntitlementid// "entitlementid"
0x128e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1293  callvirt instance string [mscorlib]System.Object::ToString()
0x1298  stloc.2
0x1299  ldarg.1
0x129a  ldstr    aPrimarycontact// "primarycontactid"
0x129f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x12a4  brfalse.s loc_12B7
0x12a6  ldarg.1
0x12a7  ldstr    aPrimarycontact// "primarycontactid"
0x12ac  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x12b1  callvirt instance string [mscorlib]System.Object::ToString()
0x12b6  stloc.3
0x12b7  ldarg.3
0x12b8  brfalse  loc_1424
0x12bd  ldloc.1
0x12be  brtrue.s loc_12CC
0x12c0  ldloc.0
0x12c1  brtrue.s loc_12CC
0x12c3  ldloc.2
0x12c4  brtrue.s loc_12CC
0x12c6  ldloc.3
0x12c7  brfalse  loc_1424
0x12cc  ldstr    aIncident// "Incident"
0x12d1  ldarg.2
0x12d2  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x12d7  stloc.s  6
0x12d9  ldloc.s  6
0x12db  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x12e0  ldc.i4.4
0x12e1  newarr   [mscorlib]System.String
0x12e6  dup
0x12e7  ldc.i4.0
0x12e8  ldstr    aCustomerid// "customerid"
0x12ed  stelem.ref
0x12ee  dup
0x12ef  ldc.i4.1
0x12f0  ldstr    aProductid// "productid"
0x12f5  stelem.ref
0x12f6  dup
0x12f7  ldc.i4.2
0x12f8  ldstr    aEntitlementid// "entitlementid"
0x12fd  stelem.ref
0x12fe  dup
0x12ff  ldc.i4.3
0x1300  ldstr    aPrimarycontact// "primarycontactid"
0x1305  stelem.ref
0x1306  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x130b  ldloc.s  6
0x130d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1312  ldstr    aIncidentid// "incidentid"
0x1317  ldc.i4.0
0x1318  ldarg.1
0x1319  ldstr    aIncidentid// "incidentid"
0x131e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1323  unbox.any [mscorlib]System.Guid
0x1328  box      [mscorlib]System.Guid
0x132d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1332  pop
0x1333  ldarg.3
0x1334  brfalse.s loc_135C
0x1336  ldc.i4.2
0x1337  newarr   [mscorlib]System.String
0x133c  dup
0x133d  ldc.i4.0
0x133e  ldstr    aStatecode// "statecode"
0x1343  stelem.ref
0x1344  dup
0x1345  ldc.i4.1
0x1346  ldstr    aStatuscode// "statuscode"
0x134b  stelem.ref
0x134c  stloc.s  7
0x134e  ldloc.s  6
0x1350  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1355  ldloc.s  7
0x1357  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x135c  ldarg.2
0x135d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1362  stloc.s  8
0x1364  ldarg.0
0x1365  ldarg.1
0x1366  ldstr    aIncidentid// "incidentid"
0x136b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1370  unbox.any [mscorlib]System.Guid
0x1375  ldstr    aIncident// "Incident"
0x137a  ldarg.2
0x137b  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1380  ldloc.s  6
0x1382  ldarg.2
0x1383  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1388  stloc.s  4
0x138a  leave.s  loc_1398
0x138c  ldloc.s  8
0x138e  brfalse.s loc_1397
0x1390  ldloc.s  8
0x1392  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1397  endfinally
0x1398  ldloc.1
0x1399  brtrue.s loc_13BB
0x139b  ldloc.s  4
0x139d  ldstr    aCustomerid// "customerid"
0x13a2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x13a7  brfalse.s loc_13BB
0x13a9  ldloc.s  4
0x13ab  ldstr    aCustomerid// "customerid"
0x13b0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x13b5  callvirt instance string [mscorlib]System.Object::ToString()
0x13ba  stloc.1
0x13bb  ldloc.0
0x13bc  brtrue.s loc_13DE
0x13be  ldloc.s  4
0x13c0  ldstr    aProductid// "productid"
0x13c5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x13ca  brfalse.s loc_13DE
0x13cc  ldloc.s  4
0x13ce  ldstr    aProductid// "productid"
0x13d3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x13d8  callvirt instance string [mscorlib]System.Object::ToString()
0x13dd  stloc.0
0x13de  ldloc.2
0x13df  brtrue.s loc_1401
0x13e1  ldloc.s  4
0x13e3  ldstr    aEntitlementid// "entitlementid"
0x13e8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x13ed  brfalse.s loc_1401
0x13ef  ldloc.s  4
0x13f1  ldstr    aEntitlementid// "entitlementid"
0x13f6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x13fb  callvirt instance string [mscorlib]System.Object::ToString()
0x1400  stloc.2
0x1401  ldloc.3
0x1402  brtrue.s loc_1424
0x1404  ldloc.s  4
0x1406  ldstr    aPrimarycontact// "primarycontactid"
0x140b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1410  brfalse.s loc_1424
0x1412  ldloc.s  4
0x1414  ldstr    aPrimarycontact// "primarycontactid"
0x1419  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x141e  callvirt instance string [mscorlib]System.Object::ToString()
0x1423  stloc.3
0x1424  ldloc.2
0x1425  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x142a  brtrue.s loc_144F
0x142c  newobj   instance void Microsoft.Crm.Service.ObjectModel.EntitlementService::.ctor()
0x1431  ldloc.2
0x1432  ldloc.1
0x1433  ldloc.3
0x1434  ldloc.0
0x1435  ldloc.s  5
0x1437  ldarg.2
0x1438  callvirt instance bool Microsoft.Crm.Service.ObjectModel.EntitlementService::IsEntitlementValidForCase(string entitlementId, string customerId, string contactId, string productId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression query, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x143d  brtrue.s loc_144F
0x143f  ldstr    aSelectAnActive// "Select an active entitlement that belon"...
0x1444  ldc.i4   0x8004F866
0x1449  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x144e  throw
0x144f  ldloc.s  4
0x1451  ret
```
