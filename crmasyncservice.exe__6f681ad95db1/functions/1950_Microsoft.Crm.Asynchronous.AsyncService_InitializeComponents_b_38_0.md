# Microsoft.Crm.Asynchronous.AsyncService::<InitializeComponents>b__38_0

- ea: `0x1950`
- end: `0x19d0`
- name: `Microsoft.Crm.Asynchronous.AsyncService::<InitializeComponents>b__38_0`
- size: `128`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1950`

## string_xrefs

- `0x1995`: `Starting Async service {0} monitoring {1} active organizations out of {2} total.`

## pseudocode

```c

```

## disassembly

```asm
0x1950  ldc.i4.0
0x1951  stloc.0
0x1952  ldarg.0
0x1953  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IConfiguration Microsoft.Crm.Asynchronous.AsyncService::_config
0x1958  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationList::get_Organizations()
0x195d  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::get_Values()
0x1962  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::GetEnumerator()
0x1967  stloc.1
0x1968  br.s     loc_197C
0x196a  ldloc.1
0x196b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::get_Current()
0x1970  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationState()
0x1975  ldc.i4.1
0x1976  bne.un.s loc_197C
0x1978  ldloc.0
0x1979  ldc.i4.1
0x197a  add
0x197b  stloc.0
0x197c  ldloc.1
0x197d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1982  brtrue.s loc_196A
0x1984  leave.s  loc_1990
0x1986  ldloc.1
0x1987  brfalse.s loc_198F
0x1989  ldloc.1
0x198a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x198f  endfinally
0x1990  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1995  ldstr    aStartingAsyncS// "Starting Async service {0} monitoring {"...
0x199a  ldc.i4.3
0x199b  newarr   [mscorlib]System.Object
0x19a0  dup
0x19a1  ldc.i4.0
0x19a2  ldarg.0
0x19a3  call     instance string [System.ServiceProcess]System.ServiceProcess.ServiceBase::get_ServiceName()
0x19a8  stelem.ref
0x19a9  dup
0x19aa  ldc.i4.1
0x19ab  ldloc.0
0x19ac  box      [mscorlib]System.Int32
0x19b1  stelem.ref
0x19b2  dup
0x19b3  ldc.i4.2
0x19b4  ldarg.0
0x19b5  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IConfiguration Microsoft.Crm.Asynchronous.AsyncService::_config
0x19ba  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationList::get_Organizations()
0x19bf  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>>::get_Count()
0x19c4  box      [mscorlib]System.Int32
0x19c9  stelem.ref
0x19ca  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x19cf  ret
```
