# Microsoft.Crm.Extensibility.ODataV4.Throttling.ODataThrottlingHandler::GetUserAndOrganizationContext

- ea: `0x2bad0`
- end: `0x2bba6`
- name: `Microsoft.Crm.Extensibility.ODataV4.Throttling.ODataThrottlingHandler::GetUserAndOrganizationContext`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x2b9d0`

## callees

- `0x2bad0`

## string_xrefs

- `0x2bb2b`: `Ignore Error - Odata Throttling handler: failed to get userId: {0}, orgId: {1}, Path: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x2bad0  ldnull
0x2bad1  stloc.0
0x2bad2  call     class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Current()
0x2bad7  stloc.1
0x2bad8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2badd  stloc.2
0x2bade  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2bae3  stloc.3
0x2bae4  ldloc.1
0x2bae5  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0x2baea  call     bool [Microsoft.Crm.Core]IdentityExtensions::GetIsUserAuthenticated(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0x2baef  brfalse.s loc_2BB09
0x2baf1  ldloc.1
0x2baf2  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0x2baf7  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]IdentityExtensions::GetUserId(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0x2bafc  stloc.2
0x2bafd  ldloc.1
0x2bafe  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0x2bb03  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]IdentityExtensions::GetOrganizationId(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0x2bb08  stloc.3
0x2bb09  ldloc.2
0x2bb0a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2bb0f  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2bb14  brtrue.s loc_2BB23
0x2bb16  ldloc.3
0x2bb17  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2bb1c  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2bb21  brfalse.s loc_2BB73
0x2bb23  ldnull
0x2bb24  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2bb29  ldc.i4.s 0x14
0x2bb2b  ldstr    aIgnoreErrorOda// "Ignore Error - Odata Throttling handler"...
0x2bb30  ldc.i4.3
0x2bb31  newarr   [mscorlib]System.Object
0x2bb36  dup
0x2bb37  ldc.i4.0
0x2bb38  ldloc.2
0x2bb39  box      [mscorlib]System.Guid
0x2bb3e  stelem.ref
0x2bb3f  dup
0x2bb40  ldc.i4.1
0x2bb41  ldloc.3
0x2bb42  box      [mscorlib]System.Guid
0x2bb47  stelem.ref
0x2bb48  dup
0x2bb49  ldc.i4.2
0x2bb4a  ldarg.1
0x2bb4b  brtrue.s loc_2BB50
0x2bb4d  ldnull
0x2bb4e  br.s     loc_2BB62
0x2bb50  ldarg.1
0x2bb51  call     instance class [System]System.Uri [System.Net.Http]System.Net.Http.HttpRequestMessage::get_RequestUri()
0x2bb56  dup
0x2bb57  brtrue.s loc_2BB5D
0x2bb59  pop
0x2bb5a  ldnull
0x2bb5b  br.s     loc_2BB62
0x2bb5d  call     instance string [System]System.Uri::get_AbsolutePath()
0x2bb62  dup
0x2bb63  brtrue.s loc_2BB6B
0x2bb65  pop
0x2bb66  ldsfld   string [mscorlib]System.String::Empty
0x2bb6b  stelem.ref
0x2bb6c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2bb71  br.s     loc_2BB7B
0x2bb73  ldloc.2
0x2bb74  ldloc.3
0x2bb75  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.UserAndOrganizationContext::.ctor(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2bb7a  stloc.0
0x2bb7b  leave.s  loc_2BBA4
0x2bb7d  stloc.s  4
0x2bb7f  ldloc.s  4
0x2bb81  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2bb86  ldc.i4.s 0x14
0x2bb88  ldstr    aThrottlingHand// "Throttling Handler GetUserAndOrganizati"...
0x2bb8d  ldc.i4.1
0x2bb8e  newarr   [mscorlib]System.Object
0x2bb93  dup
0x2bb94  ldc.i4.0
0x2bb95  ldloc.s  4
0x2bb97  callvirt instance string [mscorlib]System.Object::ToString()
0x2bb9c  stelem.ref
0x2bb9d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2bba2  leave.s  loc_2BBA4
0x2bba4  ldloc.0
0x2bba5  ret
```
