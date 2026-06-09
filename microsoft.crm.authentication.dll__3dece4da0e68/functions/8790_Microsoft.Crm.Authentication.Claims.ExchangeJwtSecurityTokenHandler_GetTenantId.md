# Microsoft.Crm.Authentication.Claims.ExchangeJwtSecurityTokenHandler::GetTenantId

- ea: `0x8790`
- end: `0x87b8`
- name: `Microsoft.Crm.Authentication.Claims.ExchangeJwtSecurityTokenHandler::GetTenantId`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x86c0`

## callees

- `0x8790`
- `0x87c0`

## pseudocode

```c

```

## disassembly

```asm
0x8790  ldarg.0
0x8791  ldc.i4.1
0x8792  newarr   [mscorlib]System.Char
0x8797  dup
0x8798  ldc.i4.0
0x8799  ldc.i4.s 0x40
0x879b  stelem.i2
0x879c  ldc.i4.1
0x879d  callvirt instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0x87a2  stloc.0
0x87a3  ldloc.0
0x87a4  ldlen
0x87a5  conv.i4
0x87a6  ldc.i4.1
0x87a7  blt.s    loc_87B2
0x87a9  ldloc.0
0x87aa  ldc.i4.1
0x87ab  ldelem.ref
0x87ac  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.Claims.ExchangeJwtSecurityTokenHandler::GetGuidValue(string sourceValue)
0x87b1  ret
0x87b2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x87b7  ret
```
