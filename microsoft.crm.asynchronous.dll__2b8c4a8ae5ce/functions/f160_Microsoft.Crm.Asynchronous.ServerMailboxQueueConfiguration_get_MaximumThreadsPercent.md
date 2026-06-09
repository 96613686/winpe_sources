# Microsoft.Crm.Asynchronous.ServerMailboxQueueConfiguration::get_MaximumThreadsPercent

- ea: `0xf160`
- end: `0xf171`
- name: `Microsoft.Crm.Asynchronous.ServerMailboxQueueConfiguration::get_MaximumThreadsPercent`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xe6f0`

## string_xrefs

- `0xf161`: `MailboxQueueMaximumThreadsPercent`

## pseudocode

```c

```

## disassembly

```asm
0xf160  ldarg.0
0xf161  ldstr    aMailboxqueuema// "MailboxQueueMaximumThreadsPercent"
0xf166  call     instance object Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::GetDeploymentSetting(string settingName)
0xf16b  unbox.any [mscorlib]System.Double
0xf170  ret
```
