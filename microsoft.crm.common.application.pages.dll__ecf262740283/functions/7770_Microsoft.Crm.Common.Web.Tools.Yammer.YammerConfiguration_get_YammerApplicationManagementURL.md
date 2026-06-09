# Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::get_YammerApplicationManagementURL

- ea: `0x7770`
- end: `0x77a1`
- name: `Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::get_YammerApplicationManagementURL`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7840`

## string_xrefs

- `0x777a`: `https://www.yammer.com`

## pseudocode

```c

```

## disassembly

```asm
0x7770  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x7775  ldstr    aYammersiteurl// "YammerSiteURL"
0x777a  ldstr    aHttpsWwwYammer// "https://www.yammer.com"
0x777f  callvirt T0x2B000003
0x7784  newobj   instance void [System]System.Uri::.ctor(string)
0x7789  ldstr    aAccountApplica// "/account/applications/"
0x778e  ldc.i4.2
0x778f  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x7794  stloc.0
0x7795  ldloc.0
0x7796  newobj   instance void [System]System.Uri::.ctor(class [System]System.Uri, class [System]System.Uri)
0x779b  call     instance string [System]System.Uri::get_AbsoluteUri()
0x77a0  ret
```
