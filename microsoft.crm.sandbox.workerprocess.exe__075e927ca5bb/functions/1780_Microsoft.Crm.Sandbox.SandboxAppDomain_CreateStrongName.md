# Microsoft.Crm.Sandbox.SandboxAppDomain::CreateStrongName

- ea: `0x1780`
- end: `0x17ce`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomain::CreateStrongName`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x17d0`

## callees

- `0x1780`

## pseudocode

```c

```

## disassembly

```asm
0x1780  ldarg.0
0x1781  ldstr    aAssembly// "assembly"
0x1786  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x178b  ldarg.0
0x178c  callvirt instance class [mscorlib]System.Reflection.AssemblyName [mscorlib]System.Reflection.Assembly::GetName()
0x1791  stloc.0
0x1792  ldloc.0
0x1793  ldstr    aAssemblyname// "assemblyName"
0x1798  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x179d  ldloc.0
0x179e  callvirt instance unsigned int8[] [mscorlib]System.Reflection.AssemblyName::GetPublicKey()
0x17a3  stloc.1
0x17a4  ldloc.1
0x17a5  brfalse.s loc_17AB
0x17a7  ldloc.1
0x17a8  ldlen
0x17a9  brtrue.s loc_17B6
0x17ab  ldstr    aAssemblyDoesNo// "Assembly does not have a strong name."
0x17b0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x17b5  throw
0x17b6  ldloc.1
0x17b7  newobj   instance void [mscorlib]System.Security.Permissions.StrongNamePublicKeyBlob::.ctor(unsigned int8[])
0x17bc  ldloc.0
0x17bd  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_Name()
0x17c2  ldloc.0
0x17c3  callvirt instance class [mscorlib]System.Version [mscorlib]System.Reflection.AssemblyName::get_Version()
0x17c8  newobj   instance void [mscorlib]System.Security.Policy.StrongName::.ctor(class [mscorlib]System.Security.Permissions.StrongNamePublicKeyBlob, string, class [mscorlib]System.Version)
0x17cd  ret
```
