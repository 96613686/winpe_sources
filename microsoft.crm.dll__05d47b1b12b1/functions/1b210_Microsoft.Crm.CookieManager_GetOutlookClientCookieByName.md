# Microsoft.Crm.CookieManager::GetOutlookClientCookieByName

- ea: `0x1b210`
- end: `0x1b277`
- name: `Microsoft.Crm.CookieManager::GetOutlookClientCookieByName`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1b1d0`

## callees

- `0x1b210`

## string_xrefs

- `0x1b211`: `targetUri`

## pseudocode

```c

```

## disassembly

```asm
0x1b210  ldarg.0
0x1b211  ldstr    aTargeturi// "targetUri"
0x1b216  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1b21b  ldarg.1
0x1b21c  ldstr    aClientcookiena// "clientCookieName"
0x1b221  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1b226  ldc.i4   0x400
0x1b22b  stloc.0
0x1b22c  ldloc.0
0x1b22d  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x1b232  stloc.1
0x1b233  ldarg.0
0x1b234  callvirt instance string [mscorlib]System.Object::ToString()
0x1b239  ldarg.1
0x1b23a  ldloc.1
0x1b23b  ldloca.s 0
0x1b23d  call     bool [Microsoft.Crm.Core]Microsoft.Crm.NativeMethods::InternetGetCookie(string, string, class [mscorlib]System.Text.StringBuilder, int32&)
0x1b242  stloc.2
0x1b243  ldloc.2
0x1b244  brtrue.s loc_1B267
0x1b246  ldc.i4   0x400
0x1b24b  ldloc.0
0x1b24c  bge.s    loc_1B267
0x1b24e  ldloc.0
0x1b24f  ldc.i4.1
0x1b250  add
0x1b251  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x1b256  stloc.1
0x1b257  ldarg.0
0x1b258  callvirt instance string [mscorlib]System.Object::ToString()
0x1b25d  ldarg.1
0x1b25e  ldloc.1
0x1b25f  ldloca.s 0
0x1b261  call     bool [Microsoft.Crm.Core]Microsoft.Crm.NativeMethods::InternetGetCookie(string, string, class [mscorlib]System.Text.StringBuilder, int32&)
0x1b266  stloc.2
0x1b267  ldloc.2
0x1b268  brtrue.s loc_1B270
0x1b26a  ldsfld   string [mscorlib]System.String::Empty
0x1b26f  ret
0x1b270  ldloc.1
0x1b271  callvirt instance string [mscorlib]System.Object::ToString()
0x1b276  ret
```
