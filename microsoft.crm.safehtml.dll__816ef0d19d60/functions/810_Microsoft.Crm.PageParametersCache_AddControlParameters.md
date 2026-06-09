# Microsoft.Crm.PageParametersCache::AddControlParameters

- ea: `0x810`
- end: `0x878`
- name: `Microsoft.Crm.PageParametersCache::AddControlParameters`
- size: `104`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x7a0`
- `0x810`

## callees

- `0x7d0`
- `0x810`

## pseudocode

```c

```

## disassembly

```asm
0x810  ldarg.2
0x811  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x816  stloc.0
0x817  ldloc.0
0x818  callvirt instance string [mscorlib]System.Type::get_Namespace()
0x81d  ldstr    aMicrosoftCrm// "Microsoft.Crm"
0x822  ldc.i4.4
0x823  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x828  brtrue.s loc_832
0x82a  ldarg.2
0x82b  isinst   [System.Web]System.Web.UI.Page
0x830  brfalse.s loc_83A
0x832  ldarg.0
0x833  ldarg.1
0x834  ldloc.0
0x835  call     instance void Microsoft.Crm.PageParametersCache::AddTypeParameters(class Microsoft.Crm.PageParameters pageParameters, class [mscorlib]System.Type controlType)
0x83a  ldarg.2
0x83b  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x840  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Web]System.Web.UI.ControlCollection::GetEnumerator()
0x845  stloc.1
0x846  br.s     loc_85C
0x848  ldloc.1
0x849  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x84e  castclass [System.Web]System.Web.UI.Control
0x853  stloc.2
0x854  ldarg.0
0x855  ldarg.1
0x856  ldloc.2
0x857  call     instance void Microsoft.Crm.PageParametersCache::AddControlParameters(class Microsoft.Crm.PageParameters pageParameters, class [System.Web]System.Web.UI.Control control)
0x85c  ldloc.1
0x85d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x862  brtrue.s loc_848
0x864  leave.s  loc_877
0x866  ldloc.1
0x867  isinst   [mscorlib]System.IDisposable
0x86c  stloc.3
0x86d  ldloc.3
0x86e  brfalse.s loc_876
0x870  ldloc.3
0x871  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x876  endfinally
0x877  ret
```
