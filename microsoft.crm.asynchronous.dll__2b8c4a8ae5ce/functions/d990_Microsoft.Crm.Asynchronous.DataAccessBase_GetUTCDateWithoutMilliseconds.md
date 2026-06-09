# Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds

- ea: `0xd990`
- end: `0xd9ac`
- name: `Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds`
- size: `28`
- prototype: ``
- caller_count: `9`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x3230`
- `0x3490`
- `0x36b0`
- `0x3960`
- `0x3cc0`
- `0x3dc0`
- `0x3f70`
- `0x4030`
- `0x4240`

## pseudocode

```c

```

## disassembly

```asm
0xd990  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xd995  stloc.0
0xd996  ldloc.0
0xd997  ldloca.s 0
0xd999  call     instance int32 [mscorlib]System.DateTime::get_Millisecond()
0xd99e  conv.r8
0xd99f  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMilliseconds(float64)
0xd9a4  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0xd9a9  stloc.0
0xd9aa  ldloc.0
0xd9ab  ret
```
