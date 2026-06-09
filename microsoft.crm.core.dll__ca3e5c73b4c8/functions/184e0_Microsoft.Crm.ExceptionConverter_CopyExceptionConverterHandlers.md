# Microsoft.Crm.ExceptionConverter::CopyExceptionConverterHandlers

- ea: `0x184e0`
- end: `0x18737`
- name: `Microsoft.Crm.ExceptionConverter::CopyExceptionConverterHandlers`
- size: `599`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18420`
- `0x18480`
- `0x184e0`
- `0x18780`
- `0x187a0`
- `0x66b20`
- `0x66b70`
- `0x66c50`
- `0x66c90`

## string_xrefs

- `0x185cc`: ` does not match CrmExceptionCreated`
- `0x186f5`: ` does not match FaultExceptionCreated`

## pseudocode

```c

```

## disassembly

```asm
0x184e0  ldarg.1
0x184e1  brtrue.s loc_184E4
0x184e3  ret
0x184e4  ldarg.0
0x184e5  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Delegate> Microsoft.Crm.ExceptionConverter::get_CrmExceptionCreatedEvents()
0x184ea  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Delegate>::GetEnumerator()
0x184ef  stloc.0
0x184f0  br       loc_185F6
0x184f5  newobj   instance void <>c__DisplayClass8_0::.ctor()
0x184fa  stloc.1
0x184fb  ldloc.1
0x184fc  ldloc.0
0x184fd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Delegate>::get_Current()
0x18502  stfld    class [mscorlib]System.Delegate <>c__DisplayClass8_0::d
0x18507  ldloc.1
0x18508  ldfld    class [mscorlib]System.Delegate <>c__DisplayClass8_0::d
0x1850d  dup
0x1850e  brtrue.s loc_18514
0x18510  pop
0x18511  ldnull
0x18512  br.s     loc_1853A
0x18514  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Delegate::get_Method()
0x18519  dup
0x1851a  brtrue.s loc_18520
0x1851c  pop
0x1851d  ldnull
0x1851e  br.s     loc_1853A
0x18520  callvirt instance class [mscorlib]System.Reflection.ParameterInfo[] [mscorlib]System.Reflection.MethodBase::GetParameters()
0x18525  dup
0x18526  brtrue.s loc_1852C
0x18528  pop
0x18529  ldnull
0x1852a  br.s     loc_1853A
0x1852c  ldc.i4.1
0x1852d  ldelem.ref
0x1852e  dup
0x1852f  brtrue.s loc_18535
0x18531  pop
0x18532  ldnull
0x18533  br.s     loc_1853A
0x18535  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.ParameterInfo::get_ParameterType()
0x1853a  ldtoken  Microsoft.Crm.CrmExceptionCreated
0x1853f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18544  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x18549  brfalse  loc_185E4
0x1854e  ldarg.0
0x1854f  ldfld    class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.ExceptionConverter::Logger
0x18554  ldc.i4.5
0x18555  newarr   [mscorlib]System.String
0x1855a  dup
0x1855b  ldc.i4.0
0x1855c  ldstr    aSkippingRegist// "Skipping registerting "
0x18561  stelem.ref
0x18562  dup
0x18563  ldc.i4.1
0x18564  ldloc.1
0x18565  ldfld    class [mscorlib]System.Delegate <>c__DisplayClass8_0::d
0x1856a  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Delegate::get_Method()
0x1856f  dup
0x18570  brtrue.s loc_18576
0x18572  pop
0x18573  ldnull
0x18574  br.s     loc_1857B
0x18576  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1857b  dup
0x1857c  brtrue.s loc_18584
0x1857e  pop
0x1857f  ldstr    aUnknown// "Unknown"
0x18584  stelem.ref
0x18585  dup
0x18586  ldc.i4.2
0x18587  ldstr    aBecauseType// " because type "
0x1858c  stelem.ref
0x1858d  dup
0x1858e  ldc.i4.3
0x1858f  ldloc.1
0x18590  ldfld    class [mscorlib]System.Delegate <>c__DisplayClass8_0::d
0x18595  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Delegate::get_Method()
0x1859a  dup
0x1859b  brtrue.s loc_185A1
0x1859d  pop
0x1859e  ldnull
0x1859f  br.s     loc_185C0
0x185a1  callvirt instance class [mscorlib]System.Reflection.ParameterInfo[] [mscorlib]System.Reflection.MethodBase::GetParameters()
0x185a6  dup
0x185a7  brtrue.s loc_185AD
0x185a9  pop
0x185aa  ldnull
0x185ab  br.s     loc_185C0
0x185ad  ldc.i4.1
0x185ae  ldelem.ref
0x185af  dup
0x185b0  brtrue.s loc_185B6
0x185b2  pop
0x185b3  ldnull
0x185b4  br.s     loc_185C0
0x185b6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.ParameterInfo::get_ParameterType()
0x185bb  callvirt instance string [mscorlib]System.Object::ToString()
0x185c0  dup
0x185c1  brtrue.s loc_185C9
0x185c3  pop
0x185c4  ldstr    aUnknown// "Unknown"
0x185c9  stelem.ref
0x185ca  dup
0x185cb  ldc.i4.4
0x185cc  ldstr    aDoesNotMatchCr// " does not match CrmExceptionCreated"
0x185d1  stelem.ref
0x185d2  call     string [mscorlib]System.String::Concat(string[])
0x185d7  ldc.i4.0
0x185d8  newarr   [mscorlib]System.Object
0x185dd  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogError(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x185e2  br.s     loc_185F6
0x185e4  ldarg.1
0x185e5  ldloc.1
0x185e6  ldftn    instance void <>c__DisplayClass8_0::<CopyExceptionConverterHandlers>b__0(object sender, class Microsoft.Crm.CrmExceptionCreated e)
0x185ec  newobj   instance void CrmExceptionCreatedHandler::.ctor(object object, native int method)
0x185f1  callvirt instance void Microsoft.Crm.ExceptionConverter::add_CrmExceptionCreated(class CrmExceptionCreatedHandler value)
0x185f6  ldloc.0
0x185f7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x185fc  brtrue   loc_184F5
0x18601  leave.s  loc_1860D
0x18603  ldloc.0
0x18604  brfalse.s loc_1860C
0x18606  ldloc.0
0x18607  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1860c  endfinally
0x1860d  ldarg.0
0x1860e  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Delegate> Microsoft.Crm.ExceptionConverter::get_FaultExceptionCreatedEvents()
0x18613  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Delegate>::GetEnumerator()
0x18618  stloc.0
0x18619  br       loc_1871F
0x1861e  newobj   instance void <>c__DisplayClass8_1::.ctor()
0x18623  stloc.2
0x18624  ldloc.2
0x18625  ldloc.0
0x18626  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Delegate>::get_Current()
0x1862b  stfld    class [mscorlib]System.Delegate <>c__DisplayClass8_1::d
0x18630  ldloc.2
0x18631  ldfld    class [mscorlib]System.Delegate <>c__DisplayClass8_1::d
0x18636  dup
0x18637  brtrue.s loc_1863D
0x18639  pop
0x1863a  ldnull
0x1863b  br.s     loc_18663
0x1863d  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Delegate::get_Method()
0x18642  dup
0x18643  brtrue.s loc_18649
0x18645  pop
0x18646  ldnull
0x18647  br.s     loc_18663
0x18649  callvirt instance class [mscorlib]System.Reflection.ParameterInfo[] [mscorlib]System.Reflection.MethodBase::GetParameters()
0x1864e  dup
0x1864f  brtrue.s loc_18655
0x18651  pop
0x18652  ldnull
0x18653  br.s     loc_18663
0x18655  ldc.i4.1
0x18656  ldelem.ref
0x18657  dup
0x18658  brtrue.s loc_1865E
0x1865a  pop
0x1865b  ldnull
0x1865c  br.s     loc_18663
0x1865e  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.ParameterInfo::get_ParameterType()
0x18663  ldtoken  Microsoft.Crm.FaultExceptionCreated
0x18668  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1866d  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x18672  brfalse  loc_1870D
0x18677  ldarg.0
0x18678  ldfld    class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.ExceptionConverter::Logger
0x1867d  ldc.i4.5
0x1867e  newarr   [mscorlib]System.String
0x18683  dup
0x18684  ldc.i4.0
0x18685  ldstr    aSkippingRegist// "Skipping registerting "
0x1868a  stelem.ref
0x1868b  dup
0x1868c  ldc.i4.1
0x1868d  ldloc.2
0x1868e  ldfld    class [mscorlib]System.Delegate <>c__DisplayClass8_1::d
0x18693  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Delegate::get_Method()
0x18698  dup
0x18699  brtrue.s loc_1869F
0x1869b  pop
0x1869c  ldnull
0x1869d  br.s     loc_186A4
0x1869f  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x186a4  dup
0x186a5  brtrue.s loc_186AD
0x186a7  pop
0x186a8  ldstr    aUnknown// "Unknown"
0x186ad  stelem.ref
0x186ae  dup
0x186af  ldc.i4.2
0x186b0  ldstr    aBecauseType// " because type "
0x186b5  stelem.ref
0x186b6  dup
0x186b7  ldc.i4.3
0x186b8  ldloc.2
0x186b9  ldfld    class [mscorlib]System.Delegate <>c__DisplayClass8_1::d
0x186be  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Delegate::get_Method()
0x186c3  dup
0x186c4  brtrue.s loc_186CA
0x186c6  pop
0x186c7  ldnull
0x186c8  br.s     loc_186E9
0x186ca  callvirt instance class [mscorlib]System.Reflection.ParameterInfo[] [mscorlib]System.Reflection.MethodBase::GetParameters()
0x186cf  dup
0x186d0  brtrue.s loc_186D6
0x186d2  pop
0x186d3  ldnull
0x186d4  br.s     loc_186E9
0x186d6  ldc.i4.1
0x186d7  ldelem.ref
0x186d8  dup
0x186d9  brtrue.s loc_186DF
0x186db  pop
0x186dc  ldnull
0x186dd  br.s     loc_186E9
0x186df  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.ParameterInfo::get_ParameterType()
0x186e4  callvirt instance string [mscorlib]System.Object::ToString()
0x186e9  dup
0x186ea  brtrue.s loc_186F2
0x186ec  pop
0x186ed  ldstr    aUnknown// "Unknown"
0x186f2  stelem.ref
0x186f3  dup
0x186f4  ldc.i4.4
0x186f5  ldstr    aDoesNotMatchFa// " does not match FaultExceptionCreated"
0x186fa  stelem.ref
0x186fb  call     string [mscorlib]System.String::Concat(string[])
0x18700  ldc.i4.0
0x18701  newarr   [mscorlib]System.Object
0x18706  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogError(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x1870b  br.s     loc_1871F
0x1870d  ldarg.1
0x1870e  ldloc.2
0x1870f  ldftn    instance void <>c__DisplayClass8_1::<CopyExceptionConverterHandlers>b__1(object sender, class Microsoft.Crm.FaultExceptionCreated e)
0x18715  newobj   instance void FaultExceptionCreatedHandler::.ctor(object object, native int method)
0x1871a  callvirt instance void Microsoft.Crm.ExceptionConverter::add_FaultExceptionCreated(class FaultExceptionCreatedHandler value)
0x1871f  ldloc.0
0x18720  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x18725  brtrue   loc_1861E
0x1872a  leave.s  loc_18736
0x1872c  ldloc.0
0x1872d  brfalse.s loc_18735
0x1872f  ldloc.0
0x18730  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18735  endfinally
0x18736  ret
```
