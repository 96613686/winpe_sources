# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProvider::SetLinkStateExtendedPropertyTypesForExchangeEmailMessage

- ea: `0x324d0`
- end: `0x325bd`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProvider::SetLinkStateExtendedPropertyTypesForExchangeEmailMessage`
- size: `237`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x313f0`
- `0x32320`

## callees

- `0x15850`
- `0x15870`
- `0x15930`
- `0x324d0`
- `0x32680`
- `0x32970`
- `0x32d90`
- `0x35770`
- `0x41850`
- `0x41ac0`
- `0x4da80`

## string_xrefs

- `0x324e3`: `crmLinkState`
- `0x32550`: `Invalid linkState value`
- `0x3255b`: `Invalid linkState value`
- `0x3257a`: `Mailbox: {0} - Parse Exception for LinkState in SetExtendedPropertyTypes : {1} Message: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x324d0  ldarg.2
0x324d1  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::get_ExtendedFieldURI()
0x324d6  brfalse.s loc_324EF
0x324d8  ldarg.2
0x324d9  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::get_ExtendedFieldURI()
0x324de  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType::get_PropertyName()
0x324e3  ldstr    aCrmlinkstate// "crmLinkState"
0x324e8  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x324ed  brfalse.s loc_324F0
0x324ef  ret
0x324f0  nop
0x324f1  ldc.r8   0.0
0x324fa  stloc.0
0x324fb  ldarg.2
0x324fc  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::get_Item()
0x32501  brfalse.s loc_3255B
0x32503  ldarg.2
0x32504  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::get_Item()
0x32509  isinst   [mscorlib]System.Double
0x3250e  brtrue.s loc_3251D
0x32510  ldarg.2
0x32511  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::get_Item()
0x32516  isinst   [mscorlib]System.Int32
0x3251b  brfalse.s loc_3252B
0x3251d  ldarg.2
0x3251e  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::get_Item()
0x32523  unbox.any [mscorlib]System.Double
0x32528  stloc.0
0x32529  br.s     loc_32566
0x3252b  ldarg.2
0x3252c  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::get_Item()
0x32531  isinst   [mscorlib]System.String
0x32536  brfalse.s loc_32550
0x32538  ldarg.2
0x32539  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::get_Item()
0x3253e  castclass [mscorlib]System.String
0x32543  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x32548  call     float64 [mscorlib]System.Double::Parse(string, class [mscorlib]System.IFormatProvider)
0x3254d  stloc.0
0x3254e  br.s     loc_32566
0x32550  ldstr    aInvalidLinksta// "Invalid linkState value"
0x32555  newobj   instance void [mscorlib]System.InvalidCastException::.ctor(string)
0x3255a  throw
0x3255b  ldstr    aInvalidLinksta// "Invalid linkState value"
0x32560  newobj   instance void [mscorlib]System.InvalidCastException::.ctor(string)
0x32565  throw
0x32566  ldarg.1
0x32567  ldloc.0
0x32568  conv.i4
0x32569  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::set_LinkState(valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState value)
0x3256e  leave.s  loc_325BC
0x32570  stloc.1
0x32571  ldarg.1
0x32572  ldc.i4.1
0x32573  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::set_LinkState(valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState value)
0x32578  ldarg.0
0x32579  ldc.i4.2
0x3257a  ldstr    aMailbox0ParseE_0// "Mailbox: {0} - Parse Exception for Link"...
0x3257f  ldc.i4.3
0x32580  newarr   [mscorlib]System.Object
0x32585  dup
0x32586  ldc.i4.0
0x32587  ldarg.0
0x32588  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x3258d  ldstr    aMailboxid// "mailboxid"
0x32592  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x32597  stelem.ref
0x32598  dup
0x32599  ldc.i4.1
0x3259a  ldloc.1
0x3259b  ldarg.0
0x3259c  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x325a1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x325a6  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x325ab  stelem.ref
0x325ac  dup
0x325ad  ldc.i4.2
0x325ae  ldarg.1
0x325af  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_MessageId()
0x325b4  stelem.ref
0x325b5  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x325ba  leave.s  loc_325BC
0x325bc  ret
```
