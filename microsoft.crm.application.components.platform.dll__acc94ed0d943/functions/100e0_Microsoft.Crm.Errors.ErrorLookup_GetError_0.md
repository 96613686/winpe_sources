# Microsoft.Crm.Errors.ErrorLookup::GetError_0

- ea: `0x100e0`
- end: `0x104be`
- name: `Microsoft.Crm.Errors.ErrorLookup::GetError_0`
- size: `990`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x100d0`
- `0x104c0`

## callees

- `0xfdd0`
- `0xfe20`
- `0xfe40`
- `0x100e0`
- `0x11760`
- `0x30260`
- `0x47280`
- `0x47350`

## string_xrefs

- `0x10413`: `Web._common.error.unsupported.action`
- `0x1042a`: `Web._common.error.unsupported.action`
- `0x1041e`: `Web._common.error.unsupported.aspx_48`
- `0x10445`: `Error_Title_Workflow_External_Service`
- `0x10450`: `Error_Message_Workflow_External_Service`

## pseudocode

```c

```

## disassembly

```asm
0x100e0  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x100e5  stloc.0
0x100e6  ldarg.1
0x100e7  ldc.i4   0x80040217
0x100ec  bne.un.s loc_100FC
0x100ee  call     bool Microsoft.Crm.Application.Utility.Util::IsOnline()
0x100f3  brtrue.s loc_100FC
0x100f5  ldc.i4   0x8063110F
0x100fa  starg.s  1
0x100fc  ldarg.1
0x100fd  ldc.i4   0x8004263A
0x10102  bgt      loc_1032D
0x10107  ldarg.1
0x10108  ldc.i4   0x8004140C
0x1010d  bgt      loc_101D1
0x10112  ldarg.1
0x10113  ldc.i4   0x80040217
0x10118  bgt.s    loc_10135
0x1011a  ldarg.1
0x1011b  ldc.i4   0x80040207
0x10120  beq      loc_10400
0x10125  ldarg.1
0x10126  ldc.i4   0x80040217
0x1012b  beq      loc_10409
0x10130  br       loc_10462
0x10135  ldarg.1
0x10136  ldc.i4   0x80040220
0x1013b  beq      loc_10400
0x10140  ldarg.1
0x10141  ldc.i4   0x80040500
0x10146  sub
0x10147  switch   loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_10462, loc_1043B, loc_1043B, loc_1043B
0x101a0  ldarg.1
0x101a1  ldc.i4   0x80041405
0x101a6  sub
0x101a7  switch   loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B
0x101cc  br       loc_10462
0x101d1  ldarg.1
0x101d2  ldc.i4   0x80042606
0x101d7  bgt      loc_102DD
0x101dc  ldarg.1
0x101dd  ldc.i4   0x80041700
0x101e2  sub
0x101e3  switch   loc_1043B, loc_1043B, loc_10462, loc_10462, loc_1043B
0x101fc  ldarg.1
0x101fd  ldc.i4   0x80041D00
0x10202  sub
0x10203  switch   loc_1043B, loc_1043B, loc_1043B, loc_10462, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_10462, loc_10462, loc_1043B, loc_10462, loc_10462, loc_10462, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_10462, loc_10462, loc_10462, loc_10462, loc_10462, loc_10462, loc_1043B, loc_10462, loc_10462, loc_10462, loc_1043B, loc_1043B, loc_10462, loc_10462, loc_1043B, loc_1043B, loc_10462, loc_1043B
0x102b0  ldarg.1
0x102b1  ldc.i4   0x80042600
0x102b6  sub
0x102b7  switch   loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B
0x102d8  br       loc_10462
0x102dd  ldarg.1
0x102de  ldc.i4   0x80042623
0x102e3  sub
0x102e4  switch   loc_1043B, loc_1043B, loc_10462, loc_10462, loc_1043B
0x102fd  ldarg.1
0x102fe  ldc.i4   0x80042631
0x10303  beq      loc_1043B
0x10308  ldarg.1
0x10309  ldc.i4   0x80042636
0x1030e  sub
0x1030f  switch   loc_1043B, loc_1043B, loc_10462, loc_1043B, loc_1043B
0x10328  br       loc_10462
0x1032d  ldarg.1
0x1032e  ldc.i4   0x8004440A
0x10333  bgt      loc_103C4
0x10338  ldarg.1
0x10339  ldc.i4   0x80042F07
0x1033e  bgt.s    loc_103A1
0x10340  ldarg.1
0x10341  ldc.i4   0x80042800
0x10346  sub
0x10347  switch   loc_10444, loc_10444, loc_10444, loc_10444, loc_10444, loc_10444, loc_10444, loc_10444, loc_10444
0x10370  ldarg.1
0x10371  ldc.i4   0x80042F00
0x10376  sub
0x10377  switch   loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B, loc_1043B
0x1039c  br       loc_10462
0x103a1  ldarg.1
0x103a2  ldc.i4   0x80043B09
0x103a7  beq      loc_1043B
0x103ac  ldarg.1
0x103ad  ldc.i4   0x80043E01
0x103b2  beq      loc_1043B
0x103b7  ldarg.1
0x103b8  ldc.i4   0x8004440A
0x103bd  beq.s    loc_1043B
0x103bf  br       loc_10462
0x103c4  ldarg.1
0x103c5  ldc.i4   0x80045317
0x103ca  bgt.s    loc_103E6
0x103cc  ldarg.1
0x103cd  ldc.i4   0x8004440E
0x103d2  beq.s    loc_1043B
0x103d4  ldarg.1
0x103d5  ldc.i4   0x80045316
0x103da  beq.s    loc_1043B
0x103dc  ldarg.1
0x103dd  ldc.i4   0x80045317
0x103e2  beq.s    loc_1043B
0x103e4  br.s     loc_10462
0x103e6  ldarg.1
0x103e7  ldc.i4   0x8004D255
0x103ec  beq.s    loc_10412
0x103ee  ldarg.1
0x103ef  ldc.i4   0x80070005
0x103f4  beq.s    loc_1043B
0x103f6  ldarg.1
0x103f7  ldc.i4   0x8063110F
0x103fc  beq.s    loc_10409
0x103fe  br.s     loc_10462
0x10400  ldarg.1
0x10401  ldc.i4.3
0x10402  ldarg.2
0x10403  newobj   instance void Microsoft.Crm.Errors.ErrorData::.ctor(int32 errorCode, valuetype Microsoft.Crm.Errors.ErrorSeverity severity, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x10408  ret
0x10409  ldarg.1
0x1040a  ldc.i4.5
0x1040b  ldarg.2
0x1040c  newobj   instance void Microsoft.Crm.Errors.ErrorData::.ctor(int32 errorCode, valuetype Microsoft.Crm.Errors.ErrorSeverity severity, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x10411  ret
0x10412  ldloc.0
0x10413  ldstr    aWebCommonError// "Web._common.error.unsupported.action"
0x10418  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x1041d  ldloc.0
0x1041e  ldstr    aWebCommonError_0// "Web._common.error.unsupported.aspx_48"
0x10423  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x10428  ldc.i4.4
0x10429  ldloc.0
0x1042a  ldstr    aWebCommonError// "Web._common.error.unsupported.action"
0x1042f  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x10434  ldarg.2
0x10435  newobj   instance void Microsoft.Crm.Errors.ErrorData::.ctor(string message, string title, valuetype Microsoft.Crm.Errors.ErrorSeverity severity, string messageHtml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x1043a  ret
0x1043b  ldarg.1
0x1043c  ldc.i4.2
0x1043d  ldarg.2
0x1043e  newobj   instance void Microsoft.Crm.Errors.ErrorData::.ctor(int32 errorCode, valuetype Microsoft.Crm.Errors.ErrorSeverity severity, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x10443  ret
0x10444  ldloc.0
0x10445  ldstr    aErrorTitleWork// "Error_Title_Workflow_External_Service"
0x1044a  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x1044f  ldloc.0
0x10450  ldstr    aErrorMessageWo// "Error_Message_Workflow_External_Service"
0x10455  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x1045a  ldc.i4.4
0x1045b  ldarg.2
0x1045c  newobj   instance void Microsoft.Crm.Errors.ErrorData::.ctor(string message, string title, valuetype Microsoft.Crm.Errors.ErrorSeverity severity, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x10461  ret
0x10462  call     bool Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x10467  brfalse.s loc_104B5
0x10469  ldarg.1
0x1046a  ldc.i4   0x80004005
0x1046f  beq.s    loc_104AC
0x10471  ldarg.1
0x10472  ldc.i4   0x80044104
0x10477  beq.s    loc_104AC
0x10479  ldarg.1
0x1047a  ldc.i4   0x80044200
0x1047f  sub
0x10480  switch   loc_104A3, loc_104A3, loc_104A3, loc_104A3, loc_104A3, loc_104A3, loc_104A3
0x104a1  br.s     loc_104B5
0x104a3  ldarg.1
0x104a4  ldc.i4.2
0x104a5  ldarg.2
0x104a6  newobj   instance void Microsoft.Crm.Errors.ErrorData::.ctor(int32 errorCode, valuetype Microsoft.Crm.Errors.ErrorSeverity severity, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x104ab  ret
0x104ac  ldarg.1
0x104ad  ldc.i4.1
0x104ae  ldarg.2
0x104af  newobj   instance void Microsoft.Crm.Errors.ErrorData::.ctor(int32 errorCode, valuetype Microsoft.Crm.Errors.ErrorSeverity severity, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x104b4  ret
0x104b5  ldarg.1
0x104b6  ldc.i4.4
0x104b7  ldarg.2
0x104b8  newobj   instance void Microsoft.Crm.Errors.ErrorData::.ctor(int32 errorCode, valuetype Microsoft.Crm.Errors.ErrorSeverity severity, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x104bd  ret
```
