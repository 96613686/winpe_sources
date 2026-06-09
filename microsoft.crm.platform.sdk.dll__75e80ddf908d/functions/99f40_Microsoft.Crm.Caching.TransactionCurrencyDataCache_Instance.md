# Microsoft.Crm.Caching.TransactionCurrencyDataCache::Instance

- ea: `0x99f40`
- end: `0x99f8a`
- name: `Microsoft.Crm.Caching.TransactionCurrencyDataCache::Instance`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x91a0`

## callees

- `0x99f40`

## string_xrefs

- `0x99f5f`: `Microsoft.Crm.Application.Components.Platform`
- `0x99f64`: `Microsoft.Crm.Caching.TransactionCurrencyDataCacheLoaderProxy`
- `0x99f7a`: `Microsoft.Crm.Caching.TransactionCurrencyDataCacheLoader`

## pseudocode

```c

```

## disassembly

```asm
0x99f40  ldsfld   class Microsoft.Crm.Caching.TransactionCurrencyDataCache Microsoft.Crm.Caching.TransactionCurrencyDataCache::_innerCache
0x99f45  callvirt instance bool class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.ITransactionCurrency>::get_IsCacheLoaderInitialized()
0x99f4a  brtrue.s loc_99F84
0x99f4c  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x99f51  brfalse.s loc_99F70
0x99f53  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x99f58  brtrue.s loc_99F70
0x99f5a  ldsfld   class Microsoft.Crm.Caching.TransactionCurrencyDataCache Microsoft.Crm.Caching.TransactionCurrencyDataCache::_innerCache
0x99f5f  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.Pl"...
0x99f64  ldstr    aMicrosoftCrmCa_100// "Microsoft.Crm.Caching.TransactionCurren"...
0x99f69  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.ITransactionCurrency>::SetLoader(string, string)
0x99f6e  br.s     loc_99F84
0x99f70  ldsfld   class Microsoft.Crm.Caching.TransactionCurrencyDataCache Microsoft.Crm.Caching.TransactionCurrencyDataCache::_innerCache
0x99f75  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x99f7a  ldstr    aMicrosoftCrmCa_101// "Microsoft.Crm.Caching.TransactionCurren"...
0x99f7f  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.ITransactionCurrency>::SetLoader(string, string)
0x99f84  ldsfld   class Microsoft.Crm.Caching.TransactionCurrencyDataCache Microsoft.Crm.Caching.TransactionCurrencyDataCache::_innerCache
0x99f89  ret
```
