# Microsoft.Crm.Controls.Header::get_UseReadForm

- ea: `0x7860`
- end: `0x78a8`
- name: `Microsoft.Crm.Controls.Header::get_UseReadForm`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x7070`

## callees

- `0x7750`
- `0x7860`

## string_xrefs

- `0x786c`: `UseReadForm`
- `0x787e`: `UseReadForm`
- `0x7898`: `UseReadForm`

## pseudocode

```c

```

## disassembly

```asm
0x7860  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x7865  stloc.0
0x7866  ldloc.0
0x7867  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x786c  ldstr    aUsereadform// "UseReadForm"
0x7871  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x7876  brtrue.s loc_7892
0x7878  ldloc.0
0x7879  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x787e  ldstr    aUsereadform// "UseReadForm"
0x7883  call     bool Microsoft.Crm.Controls.Header::get_UseReadFormInternal()
0x7888  box      [mscorlib]System.Boolean
0x788d  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x7892  ldloc.0
0x7893  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x7898  ldstr    aUsereadform// "UseReadForm"
0x789d  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x78a2  unbox.any [mscorlib]System.Boolean
0x78a7  ret
```
