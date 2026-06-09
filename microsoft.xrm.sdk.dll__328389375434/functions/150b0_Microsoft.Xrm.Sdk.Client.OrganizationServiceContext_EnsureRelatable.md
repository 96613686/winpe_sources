# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::EnsureRelatable

- ea: `0x150b0`
- end: `0x151ea`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::EnsureRelatable`
- size: `314`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x136e0`
- `0x13be0`
- `0x13c70`

## callees

- `0x3880`
- `0x3b90`
- `0x3bc0`
- `0x72f0`
- `0x15070`
- `0x150b0`

## string_xrefs

- `0x150dd`: `The entity cannot link to itself.`
- `0x15133`: `The entity cannot link to itself.`
- `0x1517f`: `One or both of the ends of the '{0}' relationship is in the deleted state.`

## pseudocode

```c

```

## disassembly

```asm
0x150b0  ldarg.2
0x150b1  brtrue.s loc_150BE
0x150b3  ldstr    aRelationship_0// "relationship"
0x150b8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x150bd  throw
0x150be  ldarg.3
0x150bf  brtrue.s loc_150CC
0x150c1  ldstr    aTarget_0// "target"
0x150c6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x150cb  throw
0x150cc  ldarg.0
0x150cd  ldarg.1
0x150ce  ldstr    aSource// "source"
0x150d3  call     instance class Microsoft.Xrm.Sdk.EntityDescriptor Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::EnsureTracked(class Microsoft.Xrm.Sdk.Entity entity, string parameterName)
0x150d8  stloc.0
0x150d9  ldarg.1
0x150da  ldarg.3
0x150db  bne.un.s loc_150E8
0x150dd  ldstr    aTheEntityCanno// "The entity cannot link to itself."
0x150e2  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x150e7  throw
0x150e8  ldarg.1
0x150e9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Xrm.Sdk.Entity::get_Id()
0x150ee  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x150f3  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x150f8  brfalse.s loc_1513E
0x150fa  ldarg.3
0x150fb  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Xrm.Sdk.Entity::get_Id()
0x15100  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x15105  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1510a  brfalse.s loc_1513E
0x1510c  ldarg.1
0x1510d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Xrm.Sdk.Entity::get_Id()
0x15112  ldarg.3
0x15113  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Xrm.Sdk.Entity::get_Id()
0x15118  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1511d  brfalse.s loc_1513E
0x1511f  ldarg.1
0x15120  callvirt instance string Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x15125  ldarg.3
0x15126  callvirt instance string Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x1512b  ldc.i4.4
0x1512c  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x15131  brfalse.s loc_1513E
0x15133  ldstr    aTheEntityCanno// "The entity cannot link to itself."
0x15138  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1513d  throw
0x1513e  ldnull
0x1513f  stloc.1
0x15140  ldarg.3
0x15141  brtrue.s loc_1514E
0x15143  ldarg.s  4
0x15145  ldc.i4.s 0x10
0x15147  beq.s    loc_1515B
0x15149  ldarg.s  4
0x1514b  ldc.i4.2
0x1514c  beq.s    loc_1515B
0x1514e  ldarg.0
0x1514f  ldarg.3
0x15150  ldstr    aTarget_0// "target"
0x15155  call     instance class Microsoft.Xrm.Sdk.EntityDescriptor Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::EnsureTracked(class Microsoft.Xrm.Sdk.Entity entity, string parameterName)
0x1515a  stloc.1
0x1515b  ldarg.s  4
0x1515d  ldc.i4.4
0x1515e  beq.s    loc_15165
0x15160  ldarg.s  4
0x15162  ldc.i4.2
0x15163  bne.un.s loc_1519E
0x15165  ldloc.0
0x15166  callvirt instance valuetype Microsoft.Xrm.Sdk.EntityStates Microsoft.Xrm.Sdk.Descriptor::get_State()
0x1516b  ldc.i4.8
0x1516c  beq.s    loc_1517A
0x1516e  ldloc.1
0x1516f  brfalse.s loc_1519E
0x15171  ldloc.1
0x15172  callvirt instance valuetype Microsoft.Xrm.Sdk.EntityStates Microsoft.Xrm.Sdk.Descriptor::get_State()
0x15177  ldc.i4.8
0x15178  bne.un.s loc_1519E
0x1517a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1517f  ldstr    aOneOrBothOfThe_0// "One or both of the ends of the '{0}' re"...
0x15184  ldc.i4.1
0x15185  newarr   [mscorlib]System.Object
0x1518a  dup
0x1518b  ldc.i4.0
0x1518c  ldarg.2
0x1518d  callvirt instance string Microsoft.Xrm.Sdk.Relationship::get_SchemaName()
0x15192  stelem.ref
0x15193  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15198  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1519d  throw
0x1519e  ldarg.s  4
0x151a0  ldc.i4.8
0x151a1  beq.s    loc_151A8
0x151a3  ldarg.s  4
0x151a5  ldc.i4.2
0x151a6  bne.un.s loc_151E8
0x151a8  ldloc.0
0x151a9  callvirt instance valuetype Microsoft.Xrm.Sdk.EntityStates Microsoft.Xrm.Sdk.Descriptor::get_State()
0x151ae  ldc.i4.4
0x151af  beq.s    loc_151BD
0x151b1  ldloc.1
0x151b2  brfalse.s loc_151E8
0x151b4  ldloc.1
0x151b5  callvirt instance valuetype Microsoft.Xrm.Sdk.EntityStates Microsoft.Xrm.Sdk.Descriptor::get_State()
0x151ba  ldc.i4.4
0x151bb  bne.un.s loc_151E8
0x151bd  ldarg.s  4
0x151bf  ldc.i4.8
0x151c0  beq.s    loc_151E6
0x151c2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x151c7  ldstr    aOneOrBothOfThe// "One or both of the ends of the '{0}' re"...
0x151cc  ldc.i4.1
0x151cd  newarr   [mscorlib]System.Object
0x151d2  dup
0x151d3  ldc.i4.0
0x151d4  ldarg.2
0x151d5  callvirt instance string Microsoft.Xrm.Sdk.Relationship::get_SchemaName()
0x151da  stelem.ref
0x151db  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x151e0  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x151e5  throw
0x151e6  ldc.i4.1
0x151e7  ret
0x151e8  ldc.i4.0
0x151e9  ret
```
