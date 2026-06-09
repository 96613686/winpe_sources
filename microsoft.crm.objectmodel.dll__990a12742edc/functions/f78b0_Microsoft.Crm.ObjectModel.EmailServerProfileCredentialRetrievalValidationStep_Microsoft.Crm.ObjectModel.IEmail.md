# Microsoft.Crm.ObjectModel.EmailServerProfileCredentialRetrievalValidationStep::Microsoft.Crm.ObjectModel.IEmailServerProfileValidationStep.Execute

- ea: `0xf78b0`
- end: `0xf7917`
- name: `Microsoft.Crm.ObjectModel.EmailServerProfileCredentialRetrievalValidationStep::Microsoft.Crm.ObjectModel.IEmailServerProfileValidationStep.Execute`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xf7920`
- `0xf79b0`
- `0xf7aa0`

## string_xrefs

- `0xf78b2`: `incomingcredentialretrieval`
- `0xf78d4`: `incomingcredentialretrieval`
- `0xf78ec`: `incomingcredentialretrieval`
- `0xf78b7`: `incomingauthenticationprotocol`
- `0xf78f6`: `incomingpassword`
- `0xf78f1`: `incomingusername`
- `0xf78c8`: `outgoingauthenticationprotocol`

## pseudocode

```c

```

## disassembly

```asm
0xf78b0  ldarg.0
0xf78b1  ldarg.1
0xf78b2  ldstr    aIncomingcreden// "incomingcredentialretrieval"
0xf78b7  ldstr    aIncomingauthen// "incomingauthenticationprotocol"
0xf78bc  call     instance void Microsoft.Crm.ObjectModel.EmailServerProfileCredentialRetrievalValidationStep::ValidateAuthenticationProtocol(class Microsoft.Crm.ObjectModel.EmailServerProfileValidationContext context, string testAttribute, string resultAttribute)
0xf78c1  ldarg.0
0xf78c2  ldarg.1
0xf78c3  ldstr    aOutgoingcreden// "outgoingcredentialretrieval"
0xf78c8  ldstr    aOutgoingauthen// "outgoingauthenticationprotocol"
0xf78cd  call     instance void Microsoft.Crm.ObjectModel.EmailServerProfileCredentialRetrievalValidationStep::ValidateAuthenticationProtocol(class Microsoft.Crm.ObjectModel.EmailServerProfileValidationContext context, string testAttribute, string resultAttribute)
0xf78d2  ldarg.0
0xf78d3  ldarg.1
0xf78d4  ldstr    aIncomingcreden// "incomingcredentialretrieval"
0xf78d9  call     instance void Microsoft.Crm.ObjectModel.EmailServerProfileCredentialRetrievalValidationStep::ValidateS2SSetting(class Microsoft.Crm.ObjectModel.EmailServerProfileValidationContext context, string testAttribute)
0xf78de  ldarg.0
0xf78df  ldarg.1
0xf78e0  ldstr    aOutgoingcreden// "outgoingcredentialretrieval"
0xf78e5  call     instance void Microsoft.Crm.ObjectModel.EmailServerProfileCredentialRetrievalValidationStep::ValidateS2SSetting(class Microsoft.Crm.ObjectModel.EmailServerProfileValidationContext context, string testAttribute)
0xf78ea  ldarg.0
0xf78eb  ldarg.1
0xf78ec  ldstr    aIncomingcreden// "incomingcredentialretrieval"
0xf78f1  ldstr    aIncominguserna// "incomingusername"
0xf78f6  ldstr    aIncomingpasswo// "incomingpassword"
0xf78fb  call     instance void Microsoft.Crm.ObjectModel.EmailServerProfileCredentialRetrievalValidationStep::ValidateCredentialViaESP(class Microsoft.Crm.ObjectModel.EmailServerProfileValidationContext context, string testAttribute, string userName, string password)
0xf7900  ldarg.0
0xf7901  ldarg.1
0xf7902  ldstr    aOutgoingcreden// "outgoingcredentialretrieval"
0xf7907  ldstr    aOutgoinguserna// "outgoingusername"
0xf790c  ldstr    aOutgoingpasswo// "outgoingpassword"
0xf7911  call     instance void Microsoft.Crm.ObjectModel.EmailServerProfileCredentialRetrievalValidationStep::ValidateCredentialViaESP(class Microsoft.Crm.ObjectModel.EmailServerProfileValidationContext context, string testAttribute, string userName, string password)
0xf7916  ret
```
