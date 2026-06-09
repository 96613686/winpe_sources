# Microsoft.Crm.Sandbox.SandboxAppDomainHelper::ValidateArguments

- ea: `0x1060`
- end: `0x10d0`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomainHelper::ValidateArguments`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x7b0`
- `0x1240`

## callees

- `0x1060`

## string_xrefs

- `0x1093`: `CRM Sandbox Internal Error: requestContext.OwningExtension`
- `0x10a1`: `sandboxServices`
- `0x10a6`: `CRM sandbox Internal Error: sandboxServices`

## pseudocode

```c

```

## disassembly

```asm
0x1060  ldarg.1
0x1061  brtrue.s loc_1073
0x1063  ldstr    aCustomactivity// "customActivityTypeName"
0x1068  ldstr    aCrmSandboxInte_1// "CRM Sandbox Internal Error: customActiv"...
0x106d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string, string)
0x1072  throw
0x1073  ldarg.2
0x1074  brtrue.s loc_1086
0x1076  ldstr    aRequestcontext// "requestContext"
0x107b  ldstr    aCrmSandboxInte_2// "CRM Sandbox Internal Error: requestCont"...
0x1080  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string, string)
0x1085  throw
0x1086  ldarg.2
0x1087  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OwningExtension()
0x108c  brtrue.s loc_109E
0x108e  ldstr    aRequestcontext// "requestContext"
0x1093  ldstr    aCrmSandboxInte_3// "CRM Sandbox Internal Error: requestCont"...
0x1098  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string, string)
0x109d  throw
0x109e  ldarg.3
0x109f  brtrue.s loc_10B1
0x10a1  ldstr    aSandboxservice// "sandboxServices"
0x10a6  ldstr    aCrmSandboxInte_4// "CRM sandbox Internal Error: sandboxServ"...
0x10ab  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string, string)
0x10b0  throw
0x10b1  ldarg.0
0x10b2  ldfld    class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_loadedAssembly
0x10b7  ldnull
0x10b8  call     bool [mscorlib]System.Reflection.Assembly::op_Equality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x10bd  brfalse.s loc_10CF
0x10bf  ldstr    aLoadedassembly// "_loadedAssembly"
0x10c4  ldstr    aCrmSandboxInte_5// "CRM Sandbox Internal Error: _loadedAsse"...
0x10c9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string, string)
0x10ce  throw
0x10cf  ret
```
