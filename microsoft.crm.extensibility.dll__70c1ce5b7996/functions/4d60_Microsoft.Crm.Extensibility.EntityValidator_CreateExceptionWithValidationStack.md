# Microsoft.Crm.Extensibility.EntityValidator::CreateExceptionWithValidationStack

- ea: `0x4d60`
- end: `0x4d78`
- name: `Microsoft.Crm.Extensibility.EntityValidator::CreateExceptionWithValidationStack`
- size: `24`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4920`
- `0x4b30`
- `0x4d80`

## callees

- `0x4e80`

## string_xrefs

- `0x4d66`: `ValidationPath`

## pseudocode

```c

```

## disassembly

```asm
0x4d60  ldarg.1
0x4d61  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x4d66  ldstr    aValidationpath// "ValidationPath"
0x4d6b  ldarg.0
0x4d6c  call     instance string Microsoft.Crm.Extensibility.EntityValidator::get_ValidationStack()
0x4d71  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x4d76  ldarg.1
0x4d77  ret
```
