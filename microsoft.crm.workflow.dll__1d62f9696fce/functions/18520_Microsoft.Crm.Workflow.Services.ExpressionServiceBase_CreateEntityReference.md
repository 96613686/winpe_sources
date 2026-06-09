# Microsoft.Crm.Workflow.Services.ExpressionServiceBase::CreateEntityReference

- ea: `0x18520`
- end: `0x18634`
- name: `Microsoft.Crm.Workflow.Services.ExpressionServiceBase::CreateEntityReference`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18230`

## callees

- `0x18520`

## string_xrefs

- `0x18530`: `Cannot create a lookup. The required parameters were not provided (expected at least 2, found {0}).`
- `0x1856f`: `Cannot create a lookup. The required parameters were not provided (expected at least 3, found {0}).`
- `0x185b8`: `CreateEntityReference: Null value provided for '{0}'`
- `0x185d9`: `Cannot create a lookup from extended list without the required parameters (expected 4, found {0}).`

## pseudocode

```c

```

## disassembly

```asm
0x18520  ldarg.1
0x18521  brtrue.s loc_18525
0x18523  ldnull
0x18524  ret
0x18525  ldarg.1
0x18526  ldlen
0x18527  conv.i4
0x18528  ldc.i4.2
0x18529  bge.s    loc_18556
0x1852b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18530  ldstr    aCannotCreateAL// "Cannot create a lookup. The required pa"...
0x18535  ldc.i4.1
0x18536  newarr   [mscorlib]System.Object
0x1853b  dup
0x1853c  ldc.i4.0
0x1853d  ldarg.1
0x1853e  ldlen
0x1853f  conv.i4
0x18540  box      [mscorlib]System.Int32
0x18545  stelem.ref
0x18546  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1854b  ldc.i4   0x80045031
0x18550  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x18555  throw
0x18556  ldarg.1
0x18557  ldc.i4.1
0x18558  ldelem.ref
0x18559  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x1855e  stloc.0
0x1855f  ldloc.0
0x18560  brfalse.s loc_18564
0x18562  ldloc.0
0x18563  ret
0x18564  ldarg.1
0x18565  ldlen
0x18566  conv.i4
0x18567  ldc.i4.3
0x18568  bge.s    loc_18595
0x1856a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1856f  ldstr    aCannotCreateAL_0// "Cannot create a lookup. The required pa"...
0x18574  ldc.i4.1
0x18575  newarr   [mscorlib]System.Object
0x1857a  dup
0x1857b  ldc.i4.0
0x1857c  ldarg.1
0x1857d  ldlen
0x1857e  conv.i4
0x1857f  box      [mscorlib]System.Int32
0x18584  stelem.ref
0x18585  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1858a  ldc.i4   0x80045031
0x1858f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x18594  throw
0x18595  ldarg.1
0x18596  ldlen
0x18597  conv.i4
0x18598  ldc.i4.3
0x18599  bne.un.s loc_185CE
0x1859b  ldarg.1
0x1859c  ldc.i4.1
0x1859d  ldelem.ref
0x1859e  brtrue.s loc_185CE
0x185a0  ldarg.1
0x185a1  ldc.i4.2
0x185a2  ldelem.ref
0x185a3  brfalse.s loc_185CE
0x185a5  ldarg.1
0x185a6  ldc.i4.2
0x185a7  ldelem.ref
0x185a8  isinst   [mscorlib]System.String
0x185ad  brfalse.s loc_185CE
0x185af  ldarg.1
0x185b0  ldc.i4.2
0x185b1  ldelem.ref
0x185b2  isinst   [mscorlib]System.String
0x185b7  stloc.2
0x185b8  ldstr    aCreateentityre// "CreateEntityReference: Null value provi"...
0x185bd  ldc.i4.1
0x185be  newarr   [mscorlib]System.Object
0x185c3  dup
0x185c4  ldc.i4.0
0x185c5  ldloc.2
0x185c6  stelem.ref
0x185c7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Warning(string, object[])
0x185cc  ldnull
0x185cd  ret
0x185ce  ldarg.1
0x185cf  ldlen
0x185d0  conv.i4
0x185d1  ldc.i4.4
0x185d2  bge.s    loc_185FF
0x185d4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x185d9  ldstr    aCannotCreateAL_1// "Cannot create a lookup from extended li"...
0x185de  ldc.i4.1
0x185df  newarr   [mscorlib]System.Object
0x185e4  dup
0x185e5  ldc.i4.0
0x185e6  ldarg.1
0x185e7  ldlen
0x185e8  conv.i4
0x185e9  box      [mscorlib]System.Int32
0x185ee  stelem.ref
0x185ef  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x185f4  ldc.i4   0x80045031
0x185f9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x185fe  throw
0x185ff  ldarg.1
0x18600  ldc.i4.3
0x18601  ldelem.ref
0x18602  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x18607  stloc.1
0x18608  ldloc.1
0x18609  brfalse.s loc_1860D
0x1860b  ldloc.1
0x1860c  ret
0x1860d  ldarg.1
0x1860e  ldc.i4.1
0x1860f  ldelem.ref
0x18610  brfalse.s loc_18632
0x18612  ldarg.1
0x18613  ldc.i4.3
0x18614  ldelem.ref
0x18615  brfalse.s loc_18632
0x18617  ldarg.1
0x18618  ldc.i4.1
0x18619  ldelem.ref
0x1861a  callvirt instance string [mscorlib]System.Object::ToString()
0x1861f  ldarg.1
0x18620  ldc.i4.3
0x18621  ldelem.ref
0x18622  callvirt instance string [mscorlib]System.Object::ToString()
0x18627  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1862c  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x18631  ret
0x18632  ldnull
0x18633  ret
```
