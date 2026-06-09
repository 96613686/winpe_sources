# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetDisplayAreaParams

- ea: `0x2b10`
- end: `0x2b66`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetDisplayAreaParams`
- size: `86`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x26f0`
- `0x3450`

## callees

- `0x190`
- `0x1c0`
- `0x220`
- `0x2b0`
- `0x2b10`

## pseudocode

```c

```

## disassembly

```asm
0x2b10  ldnull
0x2b11  stloc.0
0x2b12  ldarg.0
0x2b13  ldstr    aDisplayarea// "displayarea"
0x2b18  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x2b1d  brfalse.s loc_2B64
0x2b1f  newobj   instance void [System]System.Collections.Specialized.HybridDictionary::.ctor()
0x2b24  stloc.0
0x2b25  ldarg.0
0x2b26  ldstr    aDisplayarea// "displayarea"
0x2b2b  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag[] Microsoft.Crm.Application.WebServices.ParameterBag::GetBagArray(string name)
0x2b30  stloc.1
0x2b31  ldc.i4.0
0x2b32  stloc.2
0x2b33  br.s     loc_2B5E
0x2b35  ldloc.1
0x2b36  ldloc.2
0x2b37  ldelem.ref
0x2b38  stloc.3
0x2b39  ldloc.0
0x2b3a  ldloc.3
0x2b3b  ldstr    aId// "id"
0x2b40  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x2b45  ldloc.3
0x2b46  ldstr    aDisplayed// "displayed"
0x2b4b  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2b50  box      [mscorlib]System.Boolean
0x2b55  callvirt instance void [System]System.Collections.Specialized.HybridDictionary::Add(object, object)
0x2b5a  ldloc.2
0x2b5b  ldc.i4.1
0x2b5c  add
0x2b5d  stloc.2
0x2b5e  ldloc.2
0x2b5f  ldloc.1
0x2b60  ldlen
0x2b61  conv.i4
0x2b62  blt.s    loc_2B35
0x2b64  ldloc.0
0x2b65  ret
```
