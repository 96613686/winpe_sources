# Microsoft.Crm.BusinessEntities.SecurityLibrary::TryCheckPrivilege_0

- ea: `0x62290`
- end: `0x62316`
- name: `Microsoft.Crm.BusinessEntities.SecurityLibrary::TryCheckPrivilege_0`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x61fd0`
- `0x73260`

## callees

- `0x61160`
- `0x61180`
- `0x611e0`
- `0x62250`
- `0x62290`
- `0x62320`

## string_xrefs

- `0x62297`: `Privilege`
- `0x622df`: `SecLib::ValidateSecurityPrincipal failed. Invalid SecurityPrincipalType={0} for PrincipalId={1}`

## pseudocode

```c

```

## disassembly

```asm
0x62290  ldarg.0
0x62291  call     void Microsoft.Crm.BusinessEntities.SecurityPrincipal::ValidateSecurityPrincipal(class Microsoft.Crm.BusinessEntities.SecurityPrincipal principal)
0x62296  ldarg.1
0x62297  ldstr    aPrivilege// "Privilege"
0x6229c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x622a1  ldarg.2
0x622a2  ldstr    aContext// "context"
0x622a7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x622ac  ldarg.0
0x622ad  callvirt instance int32 Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_Type()
0x622b2  stloc.0
0x622b3  ldloc.0
0x622b4  ldc.i4.8
0x622b5  beq.s    loc_622BE
0x622b7  ldloc.0
0x622b8  ldc.i4.s 9
0x622ba  beq.s    loc_622CC
0x622bc  br.s     loc_622DA
0x622be  ldarg.0
0x622bf  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0x622c4  ldarg.1
0x622c5  ldarg.2
0x622c6  call     int32 Microsoft.Crm.BusinessEntities.SecurityLibrary::TryCheckPrivilege(valuetype [mscorlib]System.Guid user, valuetype [mscorlib]System.Guid privilege, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x622cb  ret
0x622cc  ldarg.0
0x622cd  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0x622d2  ldarg.1
0x622d3  ldarg.2
0x622d4  call     int32 Microsoft.Crm.BusinessEntities.SecurityLibrary::TryCheckPrivilegeTeam(valuetype [mscorlib]System.Guid team, valuetype [mscorlib]System.Guid privilege, class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext context)
0x622d9  ret
0x622da  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x622df  ldstr    aSeclibValidate// "SecLib::ValidateSecurityPrincipal faile"...
0x622e4  ldc.i4.2
0x622e5  newarr   [mscorlib]System.Object
0x622ea  dup
0x622eb  ldc.i4.0
0x622ec  ldarg.0
0x622ed  callvirt instance int32 Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_Type()
0x622f2  box      [mscorlib]System.Int32
0x622f7  stelem.ref
0x622f8  dup
0x622f9  ldc.i4.1
0x622fa  ldarg.0
0x622fb  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0x62300  box      [mscorlib]System.Guid
0x62305  stelem.ref
0x62306  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6230b  ldc.i4   0x8004049E
0x62310  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmSecurityException::.ctor(string, int32)
0x62315  throw
```
