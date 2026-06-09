# Microsoft.Crm.Asynchronous.EmailConnector.EmailAccessConfigurationFactory::GetEmailAccessConfiguration

- ea: `0x7450`
- end: `0x751b`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.EmailAccessConfigurationFactory::GetEmailAccessConfiguration`
- size: `203`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x92b0`
- `0x43490`
- `0x49b50`
- `0x75cb0`
- `0x83720`

## callees

- `0x7450`
- `0x7f80`
- `0x7fb0`
- `0x82a0`
- `0x82d0`

## string_xrefs

- `0x74e9`: `No access configuration found for MailboxId: {0} and EmailServerProfileId: {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x7450  ldarg.0
0x7451  brfalse.s loc_7459
0x7453  ldarg.1
0x7454  ldnull
0x7455  cgt.un
0x7457  br.s     loc_745A
0x7459  ldc.i4.0
0x745a  ldstr    aMailboxAndEmai// "Mailbox and EmailServerProfile cannot b"...
0x745f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x7464  ldarg.0
0x7465  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_EmailServerProfileId()
0x746a  ldarg.1
0x746b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile::get_EmailServerProfileId()
0x7470  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x7475  ldstr    aParentEmailSer// "Parent email server profile of input ma"...
0x747a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x747f  ldarg.2
0x7480  brfalse.s loc_74B5
0x7482  ldarg.2
0x7483  ldc.i4.1
0x7484  bne.un.s loc_74E4
0x7486  ldarg.1
0x7487  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailServerType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile::get_ServerType()
0x748c  stloc.0
0x748d  ldloc.0
0x748e  switch   loc_74A5, loc_74AD, loc_74A5, loc_74A5
0x74a3  br.s     loc_74E4
0x74a5  ldarg.0
0x74a6  ldarg.1
0x74a7  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailAccessConfiguration::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData mailbox, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile profile)
0x74ac  ret
0x74ad  ldarg.0
0x74ae  ldarg.1
0x74af  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.SmtpOutgoingEmailAccessConfiguration::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData mailbox, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile profile)
0x74b4  ret
0x74b5  ldarg.1
0x74b6  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailServerType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile::get_ServerType()
0x74bb  stloc.0
0x74bc  ldloc.0
0x74bd  switch   loc_74D4, loc_74DC, loc_74D4, loc_74D4
0x74d2  br.s     loc_74E4
0x74d4  ldarg.0
0x74d5  ldarg.1
0x74d6  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailAccessConfiguration::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData mailbox, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile profile)
0x74db  ret
0x74dc  ldarg.0
0x74dd  ldarg.1
0x74de  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailAccessConfiguration::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData mailbox, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile profile)
0x74e3  ret
0x74e4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x74e9  ldstr    aNoAccessConfig// "No access configuration found for Mailb"...
0x74ee  ldc.i4.2
0x74ef  newarr   [mscorlib]System.Object
0x74f4  dup
0x74f5  ldc.i4.0
0x74f6  ldarg.0
0x74f7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_MailboxId()
0x74fc  box      [mscorlib]System.Guid
0x7501  stelem.ref
0x7502  dup
0x7503  ldc.i4.1
0x7504  ldarg.1
0x7505  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile::get_EmailServerProfileId()
0x750a  box      [mscorlib]System.Guid
0x750f  stelem.ref
0x7510  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7515  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x751a  throw
```
