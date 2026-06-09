# Microsoft.Crm.CrmPluginAssemblyMetadata::GetTypeProps

- ea: `0x1e810`
- end: `0x1e8b2`
- name: `Microsoft.Crm.CrmPluginAssemblyMetadata::GetTypeProps`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1e670`

## callees

- `0x1e020`
- `0x1e030`
- `0x1e140`
- `0x1e810`
- `0x1e8c0`
- `0x1e9b0`
- `0x1ea80`

## string_xrefs

- `0x1e817`: `GetTypeProps: token: {0}`
- `0x1e897`: `GetTypeProps: ignoring token type: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1e810  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1e815  ldc.i4.s 0x14
0x1e817  ldstr    aGettypepropsTo// "GetTypeProps: token: {0}"
0x1e81c  ldc.i4.1
0x1e81d  newarr   [mscorlib]System.Object
0x1e822  dup
0x1e823  ldc.i4.0
0x1e824  ldarg.0
0x1e825  ldarg.1
0x1e826  call     instance string Microsoft.Crm.CrmPluginAssemblyMetadata::Hex(unsigned int32 value)
0x1e82b  stelem.ref
0x1e82c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e831  ldarg.2
0x1e832  ldnull
0x1e833  stind.ref
0x1e834  ldarg.3
0x1e835  ldc.i4.0
0x1e836  stind.i4
0x1e837  ldarg.s  4
0x1e839  ldc.i4.0
0x1e83a  stind.i1
0x1e83b  ldarg.s  5
0x1e83d  ldc.i4.0
0x1e83e  stind.i1
0x1e83f  ldarg.1
0x1e840  call     bool Microsoft.Crm.CrmPluginAssemblyMetadata::IsNullToken(unsigned int32 token)
0x1e845  brfalse.s loc_1E848
0x1e847  ret
0x1e848  ldarg.1
0x1e849  call     valuetype Microsoft.Crm.CorTokenType Microsoft.Crm.CrmPluginAssemblyMetadata::TokenType(unsigned int32 token)
0x1e84e  ldc.i4   0x2000000
0x1e853  bne.un.s loc_1E863
0x1e855  ldarg.0
0x1e856  ldarg.1
0x1e857  ldarg.2
0x1e858  ldarg.3
0x1e859  ldarg.s  4
0x1e85b  ldarg.s  5
0x1e85d  call     instance void Microsoft.Crm.CrmPluginAssemblyMetadata::GetTypeDefProps(unsigned int32 typeDef, [out] string& typeName, [out] unsigned int32& baseType, [out] bool& isPublic, [out] bool& isAbstract)
0x1e862  ret
0x1e863  ldarg.1
0x1e864  call     valuetype Microsoft.Crm.CorTokenType Microsoft.Crm.CrmPluginAssemblyMetadata::TokenType(unsigned int32 token)
0x1e869  ldc.i4   0x1000000
0x1e86e  bne.un.s loc_1E87A
0x1e870  ldarg.0
0x1e871  ldarg.1
0x1e872  ldarg.2
0x1e873  ldarg.3
0x1e874  call     instance void Microsoft.Crm.CrmPluginAssemblyMetadata::GetTypeRefProps(unsigned int32 typeRef, [out] string& typeName, [out] unsigned int32& moduleRef)
0x1e879  ret
0x1e87a  ldarg.1
0x1e87b  call     valuetype Microsoft.Crm.CorTokenType Microsoft.Crm.CrmPluginAssemblyMetadata::TokenType(unsigned int32 token)
0x1e880  ldc.i4   0x23000000
0x1e885  bne.un.s loc_1E890
0x1e887  ldarg.0
0x1e888  ldarg.1
0x1e889  ldarg.2
0x1e88a  call     instance void Microsoft.Crm.CrmPluginAssemblyMetadata::GetAssemblyRefProps(unsigned int32 assemblyRef, [out] string& moduleName)
0x1e88f  ret
0x1e890  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1e895  ldc.i4.s 0x14
0x1e897  ldstr    aGettypepropsIg// "GetTypeProps: ignoring token type: {0}"
0x1e89c  ldc.i4.1
0x1e89d  newarr   [mscorlib]System.Object
0x1e8a2  dup
0x1e8a3  ldc.i4.0
0x1e8a4  ldarg.0
0x1e8a5  ldarg.1
0x1e8a6  call     instance string Microsoft.Crm.CrmPluginAssemblyMetadata::Hex(unsigned int32 value)
0x1e8ab  stelem.ref
0x1e8ac  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e8b1  ret
```
