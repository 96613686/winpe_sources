# Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetEmailServerProfileColumnSet

- ea: `0x1c560`
- end: `0x1c5fc`
- name: `Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetEmailServerProfileColumnSet`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1c1e0`

## string_xrefs

- `0x1c59b`: `incomingauthenticationprotocol`
- `0x1c5a3`: `incomingcredentialretrieval`
- `0x1c5ab`: `incominguseimpersonation`
- `0x1c5b3`: `incomingusessl`
- `0x1c5bb`: `incomingportnumber`
- `0x1c5cf`: `outgoingauthenticationprotocol`
- `0x1c5df`: `outgoinguseimpersonation`

## pseudocode

```c

```

## disassembly

```asm
0x1c560  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor()
0x1c565  stloc.0
0x1c566  ldloc.0
0x1c567  ldc.i4.4
0x1c568  newarr   [mscorlib]System.String
0x1c56d  dup
0x1c56e  ldc.i4.0
0x1c56f  ldstr    aServertype// "servertype"
0x1c574  stelem.ref
0x1c575  dup
0x1c576  ldc.i4.1
0x1c577  ldstr    aUseautodiscove// "useautodiscover"
0x1c57c  stelem.ref
0x1c57d  dup
0x1c57e  ldc.i4.2
0x1c57f  ldstr    aMinpollinginte// "minpollingintervalinminutes"
0x1c584  stelem.ref
0x1c585  dup
0x1c586  ldc.i4.3
0x1c587  ldstr    aMaxconcurrentc// "maxconcurrentconnections"
0x1c58c  stelem.ref
0x1c58d  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumns(string[])
0x1c592  ldloc.0
0x1c593  ldc.i4.5
0x1c594  newarr   [mscorlib]System.String
0x1c599  dup
0x1c59a  ldc.i4.0
0x1c59b  ldstr    aIncomingauthen// "incomingauthenticationprotocol"
0x1c5a0  stelem.ref
0x1c5a1  dup
0x1c5a2  ldc.i4.1
0x1c5a3  ldstr    aIncomingcreden// "incomingcredentialretrieval"
0x1c5a8  stelem.ref
0x1c5a9  dup
0x1c5aa  ldc.i4.2
0x1c5ab  ldstr    aIncominguseimp// "incominguseimpersonation"
0x1c5b0  stelem.ref
0x1c5b1  dup
0x1c5b2  ldc.i4.3
0x1c5b3  ldstr    aIncomingusessl// "incomingusessl"
0x1c5b8  stelem.ref
0x1c5b9  dup
0x1c5ba  ldc.i4.4
0x1c5bb  ldstr    aIncomingportnu// "incomingportnumber"
0x1c5c0  stelem.ref
0x1c5c1  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumns(string[])
0x1c5c6  ldloc.0
0x1c5c7  ldc.i4.5
0x1c5c8  newarr   [mscorlib]System.String
0x1c5cd  dup
0x1c5ce  ldc.i4.0
0x1c5cf  ldstr    aOutgoingauthen// "outgoingauthenticationprotocol"
0x1c5d4  stelem.ref
0x1c5d5  dup
0x1c5d6  ldc.i4.1
0x1c5d7  ldstr    aOutgoingcreden// "outgoingcredentialretrieval"
0x1c5dc  stelem.ref
0x1c5dd  dup
0x1c5de  ldc.i4.2
0x1c5df  ldstr    aOutgoinguseimp// "outgoinguseimpersonation"
0x1c5e4  stelem.ref
0x1c5e5  dup
0x1c5e6  ldc.i4.3
0x1c5e7  ldstr    aOutgoingusessl// "outgoingusessl"
0x1c5ec  stelem.ref
0x1c5ed  dup
0x1c5ee  ldc.i4.4
0x1c5ef  ldstr    aOutgoingportnu// "outgoingportnumber"
0x1c5f4  stelem.ref
0x1c5f5  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumns(string[])
0x1c5fa  ldloc.0
0x1c5fb  ret
```
