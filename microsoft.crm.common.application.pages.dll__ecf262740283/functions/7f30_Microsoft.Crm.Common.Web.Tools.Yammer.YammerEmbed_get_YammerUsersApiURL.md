# Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::get_YammerUsersApiURL

- ea: `0x7f30`
- end: `0x7f61`
- name: `Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::get_YammerUsersApiURL`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x7f3a`: `https://www.yammer.com`

## pseudocode

```c

```

## disassembly

```asm
0x7f30  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x7f35  ldstr    aYammersiteurl// "YammerSiteURL"
0x7f3a  ldstr    aHttpsWwwYammer// "https://www.yammer.com"
0x7f3f  callvirt T0x2B000003
0x7f44  newobj   instance void [System]System.Uri::.ctor(string)
0x7f49  ldstr    aApiV1Users// "/api/v1/users/"
0x7f4e  ldc.i4.2
0x7f4f  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x7f54  stloc.0
0x7f55  ldloc.0
0x7f56  newobj   instance void [System]System.Uri::.ctor(class [System]System.Uri, class [System]System.Uri)
0x7f5b  call     instance string [System]System.Uri::get_AbsoluteUri()
0x7f60  ret
```
