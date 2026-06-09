# Microsoft.Crm.ObjectModel.EmailServerProfileServiceInternal`1::GetPreImage

- ea: `0xf6560`
- end: `0xf667c`
- name: `Microsoft.Crm.ObjectModel.EmailServerProfileServiceInternal`1::GetPreImage`
- size: `284`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xf6560`

## string_xrefs

- `0xf657b`: `incomingcredentialretrieval`
- `0xf659b`: `incomingauthenticationprotocol`
- `0xf65b3`: `incomingpassword`
- `0xf658b`: `incomingportnumber`
- `0xf6583`: `incomingserverlocation`
- `0xf65ab`: `incomingusername`
- `0xf6593`: `incomingusessl`
- `0xf65a3`: `incominguseimpersonation`
- `0xf65f1`: `outgoingauthenticationprotocol`
- `0xf65c4`: `outgoinguseimpersonation`
- `0xf65cd`: `outgoingautograntdelegateaccess`

## pseudocode

```c

```

## disassembly

```asm
0xf6560  ldstr    aEmailserverpro// "EmailServerProfile"
0xf6565  ldarg.2
0xf6566  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xf656b  stloc.0
0xf656c  ldloc.0
0xf656d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xf6572  ldc.i4.s 0x18
0xf6574  newarr   [mscorlib]System.String
0xf6579  dup
0xf657a  ldc.i4.0
0xf657b  ldstr    aIncomingcreden// "incomingcredentialretrieval"
0xf6580  stelem.ref
0xf6581  dup
0xf6582  ldc.i4.1
0xf6583  ldstr    aIncomingserver// "incomingserverlocation"
0xf6588  stelem.ref
0xf6589  dup
0xf658a  ldc.i4.2
0xf658b  ldstr    aIncomingportnu// "incomingportnumber"
0xf6590  stelem.ref
0xf6591  dup
0xf6592  ldc.i4.3
0xf6593  ldstr    aIncomingusessl// "incomingusessl"
0xf6598  stelem.ref
0xf6599  dup
0xf659a  ldc.i4.4
0xf659b  ldstr    aIncomingauthen// "incomingauthenticationprotocol"
0xf65a0  stelem.ref
0xf65a1  dup
0xf65a2  ldc.i4.5
0xf65a3  ldstr    aIncominguseimp// "incominguseimpersonation"
0xf65a8  stelem.ref
0xf65a9  dup
0xf65aa  ldc.i4.6
0xf65ab  ldstr    aIncominguserna// "incomingusername"
0xf65b0  stelem.ref
0xf65b1  dup
0xf65b2  ldc.i4.7
0xf65b3  ldstr    aIncomingpasswo// "incomingpassword"
0xf65b8  stelem.ref
0xf65b9  dup
0xf65ba  ldc.i4.8
0xf65bb  ldstr    aOutgoingcreden// "outgoingcredentialretrieval"
0xf65c0  stelem.ref
0xf65c1  dup
0xf65c2  ldc.i4.s 9
0xf65c4  ldstr    aOutgoinguseimp// "outgoinguseimpersonation"
0xf65c9  stelem.ref
0xf65ca  dup
0xf65cb  ldc.i4.s 0xA
0xf65cd  ldstr    aOutgoingautogr// "outgoingautograntdelegateaccess"
0xf65d2  stelem.ref
0xf65d3  dup
0xf65d4  ldc.i4.s 0xB
0xf65d6  ldstr    aOutgoingserver// "outgoingserverlocation"
0xf65db  stelem.ref
0xf65dc  dup
0xf65dd  ldc.i4.s 0xC
0xf65df  ldstr    aOutgoingportnu// "outgoingportnumber"
0xf65e4  stelem.ref
0xf65e5  dup
0xf65e6  ldc.i4.s 0xD
0xf65e8  ldstr    aOutgoingusessl// "outgoingusessl"
0xf65ed  stelem.ref
0xf65ee  dup
0xf65ef  ldc.i4.s 0xE
0xf65f1  ldstr    aOutgoingauthen// "outgoingauthenticationprotocol"
0xf65f6  stelem.ref
0xf65f7  dup
0xf65f8  ldc.i4.s 0xF
0xf65fa  ldstr    aOutgoinguserna// "outgoingusername"
0xf65ff  stelem.ref
0xf6600  dup
0xf6601  ldc.i4.s 0x10
0xf6603  ldstr    aOutgoingpasswo// "outgoingpassword"
0xf6608  stelem.ref
0xf6609  dup
0xf660a  ldc.i4.s 0x11
0xf660c  ldstr    aUseautodiscove// "useautodiscover"
0xf6611  stelem.ref
0xf6612  dup
0xf6613  ldc.i4.s 0x12
0xf6615  ldstr    aServertype// "servertype"
0xf661a  stelem.ref
0xf661b  dup
0xf661c  ldc.i4.s 0x13
0xf661e  ldstr    aUsesamesetting// "usesamesettingsforoutgoingconnections"
0xf6623  stelem.ref
0xf6624  dup
0xf6625  ldc.i4.s 0x14
0xf6627  ldstr    aOwnerid// "ownerid"
0xf662c  stelem.ref
0xf662d  dup
0xf662e  ldc.i4.s 0x15
0xf6630  ldstr    aOwneremailaddr// "owneremailaddress"
0xf6635  stelem.ref
0xf6636  dup
0xf6637  ldc.i4.s 0x16
0xf6639  ldstr    aExchangeonline// "exchangeonlinetenantid"
0xf663e  stelem.ref
0xf663f  dup
0xf6640  ldc.i4.s 0x17
0xf6642  ldstr    aUsedefaulttena// "usedefaulttenantid"
0xf6647  stelem.ref
0xf6648  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0xf664d  ldarg.2
0xf664e  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xf6653  stloc.1
0xf6654  ldarg.0
0xf6655  ldarg.1
0xf6656  ldstr    aEmailserverpro// "EmailServerProfile"
0xf665b  ldarg.2
0xf665c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xf6661  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0xf6666  ldloc.0
0xf6667  ldarg.2
0xf6668  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xf666d  stloc.2
0xf666e  leave.s  loc_F667A
0xf6670  ldloc.1
0xf6671  brfalse.s loc_F6679
0xf6673  ldloc.1
0xf6674  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf6679  endfinally
0xf667a  ldloc.2
0xf667b  ret
```
