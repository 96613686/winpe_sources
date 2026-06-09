# Microsoft.Crm.Core.SqlAccess.SqlDataAccesser::BuildCommandExecutedInfoString

- ea: `0x588a0`
- end: `0x5890a`
- name: `Microsoft.Crm.Core.SqlAccess.SqlDataAccesser::BuildCommandExecutedInfoString`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x586f0`
- `0x6c6a0`

## string_xrefs

- `0x588a0`: `SqlCommand executed. `
- `0x588ab`: `Command timeout: `

## pseudocode

```c

```

## disassembly

```asm
0x588a0  ldstr    aSqlcommandExec// "SqlCommand executed. "
0x588a5  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x588aa  dup
0x588ab  ldstr    aCommandTimeout// "Command timeout: "
0x588b0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x588b5  pop
0x588b6  dup
0x588b7  ldarg.1
0x588b8  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::get_CommandTimeout()
0x588bd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(int32)
0x588c2  pop
0x588c3  dup
0x588c4  ldstr    aDatabase_1// "; Database: "
0x588c9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x588ce  pop
0x588cf  dup
0x588d0  ldarg.1
0x588d1  callvirt instance class [System.Data]System.Data.SqlClient.SqlConnection [System.Data]System.Data.SqlClient.SqlCommand::get_Connection()
0x588d6  callvirt instance string [System.Data]System.Data.Common.DbConnection::get_Database()
0x588db  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x588e0  pop
0x588e1  dup
0x588e2  ldstr    aClientconnecti_0// "; ClientConnectionId: "
0x588e7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x588ec  pop
0x588ed  dup
0x588ee  ldarg.1
0x588ef  callvirt instance class [System.Data]System.Data.SqlClient.SqlConnection [System.Data]System.Data.SqlClient.SqlCommand::get_Connection()
0x588f4  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.SqlClient.SqlConnection::get_ClientConnectionId()
0x588f9  box      [mscorlib]System.Guid
0x588fe  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x58903  pop
0x58904  callvirt instance string [mscorlib]System.Object::ToString()
0x58909  ret
```
