# Microsoft.Crm.Caching.MailboxCache::Instance

- ea: `0x96480`
- end: `0x964ca`
- name: `Microsoft.Crm.Caching.MailboxCache::Instance`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x96480`

## string_xrefs

- `0x9649f`: `Microsoft.Crm.Application.Components.Platform`
- `0x964a4`: `Microsoft.Crm.Caching.MailboxCacheLoaderProxy`
- `0x964ba`: `Microsoft.Crm.Caching.MailboxCacheLoader`

## pseudocode

```c

```

## disassembly

```asm
0x96480  ldsfld   class Microsoft.Crm.Caching.MailboxCache Microsoft.Crm.Caching.MailboxCache::_innerCache
0x96485  callvirt instance bool class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IMailboxData>::get_IsCacheLoaderInitialized()
0x9648a  brtrue.s loc_964C4
0x9648c  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x96491  brfalse.s loc_964B0
0x96493  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x96498  brtrue.s loc_964B0
0x9649a  ldsfld   class Microsoft.Crm.Caching.MailboxCache Microsoft.Crm.Caching.MailboxCache::_innerCache
0x9649f  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.Pl"...
0x964a4  ldstr    aMicrosoftCrmCa_55// "Microsoft.Crm.Caching.MailboxCacheLoade"...
0x964a9  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IMailboxData>::SetLoader(string, string)
0x964ae  br.s     loc_964C4
0x964b0  ldsfld   class Microsoft.Crm.Caching.MailboxCache Microsoft.Crm.Caching.MailboxCache::_innerCache
0x964b5  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x964ba  ldstr    aMicrosoftCrmCa_56// "Microsoft.Crm.Caching.MailboxCacheLoade"...
0x964bf  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IMailboxData>::SetLoader(string, string)
0x964c4  ldsfld   class Microsoft.Crm.Caching.MailboxCache Microsoft.Crm.Caching.MailboxCache::_innerCache
0x964c9  ret
```
