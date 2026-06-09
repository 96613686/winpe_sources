# Microsoft.Crm.Application.WebServices.WorkflowWebService::FormatOptionsXml

- ea: `0x8940`
- end: `0x89e1`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::FormatOptionsXml`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x83c0`

## callees

- `0x8940`

## pseudocode

```c

```

## disassembly

```asm
0x8940  ldstr    aSelect// "<select>"
0x8945  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x894a  stloc.0
0x894b  ldarg.1
0x894c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::get_Keys()
0x8951  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<int32, string>::GetEnumerator()
0x8956  stloc.1
0x8957  br.s     loc_89B0
0x8959  ldloca.s 1
0x895b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<int32, string>::get_Current()
0x8960  stloc.2
0x8961  ldloc.0
0x8962  ldstr    aOptionValue// "<option value=\""
0x8967  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x896c  pop
0x896d  ldloc.0
0x896e  ldloca.s 2
0x8970  ldstr    aD// "D"
0x8975  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x897a  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x897f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8984  pop
0x8985  ldloc.0
0x8986  ldstr    asc_BF64// "\">"
0x898b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8990  pop
0x8991  ldloc.0
0x8992  ldarg.1
0x8993  ldloc.2
0x8994  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::get_Item(void)
0x8999  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x899e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x89a3  pop
0x89a4  ldloc.0
0x89a5  ldstr    aOption// "</option>"
0x89aa  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x89af  pop
0x89b0  ldloca.s 1
0x89b2  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<int32, string>::MoveNext()
0x89b7  brtrue.s loc_8959
0x89b9  leave.s  loc_89C9
0x89bb  ldloca.s 1
0x89bd  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<int32, string>
0x89c3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x89c8  endfinally
0x89c9  ldloc.0
0x89ca  ldstr    aSelect_0// "</select>"
0x89cf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x89d4  pop
0x89d5  ldloc.0
0x89d6  callvirt instance string [mscorlib]System.Object::ToString()
0x89db  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0x89e0  ret
```
