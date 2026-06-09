# Microsoft.Crm.Asynchronous.ImportOperation::SetImportStatus

- ea: `0xb0e0`
- end: `0xb124`
- name: `Microsoft.Crm.Asynchronous.ImportOperation::SetImportStatus`
- size: `68`
- prototype: ``
- caller_count: `8`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0xab30`
- `0xbe90`
- `0xe550`
- `0x10b00`
- `0x14370`
- `0x14ad0`
- `0x16570`
- `0x16bf0`

## callees

- `0x41e0`
- `0xb0e0`
- `0xb130`
- `0xb400`
- `0xb6b0`
- `0xb850`
- `0xbae0`

## pseudocode

```c

```

## disassembly

```asm
0xb0e0  ldarg.2
0xb0e1  ldc.i4.4
0xb0e2  beq.s    loc_B0E8
0xb0e4  ldarg.2
0xb0e5  ldc.i4.5
0xb0e6  bne.un.s loc_B116
0xb0e8  ldarg.0
0xb0e9  ldarg.1
0xb0ea  ldarg.2
0xb0eb  call     instance void Microsoft.Crm.Asynchronous.ImportOperation::SetStatusOnLinkedImportFiles(valuetype [mscorlib]System.Guid importId, int32 importStatus)
0xb0f0  ldarg.0
0xb0f1  ldarg.1
0xb0f2  call     instance void Microsoft.Crm.Asynchronous.ImportOperation::CleanupInternalImportFiles(valuetype [mscorlib]System.Guid importId)
0xb0f7  ldarg.0
0xb0f8  ldarg.1
0xb0f9  call     instance void Microsoft.Crm.Asynchronous.ImportOperation::CleanupImportMap(valuetype [mscorlib]System.Guid importId)
0xb0fe  ldarg.3
0xb0ff  brfalse.s loc_B108
0xb101  ldarg.0
0xb102  ldarg.1
0xb103  call     instance void Microsoft.Crm.Asynchronous.ImportOperation::CleanupImportFileContent(valuetype [mscorlib]System.Guid importId)
0xb108  ldarg.0
0xb109  ldarg.2
0xb10a  ldc.i4.4
0xb10b  beq.s    loc_B110
0xb10d  ldc.i4.6
0xb10e  br.s     loc_B111
0xb110  ldc.i4.5
0xb111  call     instance void Microsoft.Crm.Asynchronous.ImportOperation::SendEmail(int32 generationTypeCode)
0xb116  ldarg.0
0xb117  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0xb11c  ldarg.1
0xb11d  ldarg.2
0xb11e  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::SetImportStatus(valuetype [mscorlib]System.Guid importId, int32 status)
0xb123  ret
```
