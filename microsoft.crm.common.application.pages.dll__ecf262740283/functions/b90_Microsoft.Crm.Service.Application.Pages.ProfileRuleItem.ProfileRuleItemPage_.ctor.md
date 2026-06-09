# Microsoft.Crm.Service.Application.Pages.ProfileRuleItem.ProfileRuleItemPage::.ctor

- ea: `0xb90`
- end: `0xbab`
- name: `Microsoft.Crm.Service.Application.Pages.ProfileRuleItem.ProfileRuleItemPage::.ctor`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0xb91`: `channelaccessprofileruleitem`
- `0xb9b`: `channelaccessprofilerule`
- `0xba0`: `channelaccessprofileruleid`

## pseudocode

```c

```

## disassembly

```asm
0xb90  ldarg.0
0xb91  ldstr    aChannelaccessp// "channelaccessprofileruleitem"
0xb96  ldc.i4   0x24B9
0xb9b  ldstr    aChannelaccessp_0// "channelaccessprofilerule"
0xba0  ldstr    aChannelaccessp_1// "channelaccessprofileruleid"
0xba5  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Core.Application.Pages.ServiceItemPage::.ctor(string, int32, string, string)
0xbaa  ret
```
