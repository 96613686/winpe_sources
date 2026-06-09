# Microsoft.Crm.CrmLive.Provisioning.SyncUserUpdateHandler::FormatEventSourceMessage

- ea: `0x118a0`
- end: `0x119c4`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncUserUpdateHandler::FormatEventSourceMessage`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x11170`

## string_xrefs

- `0x11947`: `crmServiceAdminInTheOrg = `
- `0x11968`: `isDeleted = `
- `0x11989`: `isSoftDeleted = `

## pseudocode

```c

```

## disassembly

```asm
0x118a0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x118a5  dup
0x118a6  ldstr    aShouldsync// "shouldSync = "
0x118ab  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x118b0  pop
0x118b1  dup
0x118b2  ldarg.0
0x118b3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(bool)
0x118b8  pop
0x118b9  dup
0x118ba  ldstr    asc_3F5CC// ", "
0x118bf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x118c4  pop
0x118c5  dup
0x118c6  ldstr    aIslicensedinor// "isLicensedInOrg = "
0x118cb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x118d0  pop
0x118d1  dup
0x118d2  ldarg.1
0x118d3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(bool)
0x118d8  pop
0x118d9  dup
0x118da  ldstr    asc_3F5CC// ", "
0x118df  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x118e4  pop
0x118e5  dup
0x118e6  ldstr    aIsdisabledinor// "isDisabledInOrg = "
0x118eb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x118f0  pop
0x118f1  dup
0x118f2  ldarg.2
0x118f3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(bool)
0x118f8  pop
0x118f9  dup
0x118fa  ldstr    asc_3F5CC// ", "
0x118ff  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x11904  pop
0x11905  dup
0x11906  ldstr    aIslicensedincl// "isLicensedInCloudSync = "
0x1190b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x11910  pop
0x11911  dup
0x11912  ldarg.3
0x11913  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(bool)
0x11918  pop
0x11919  dup
0x1191a  ldstr    asc_3F5CC// ", "
0x1191f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x11924  pop
0x11925  dup
0x11926  ldstr    aIsdisabledincl// "isDisabledInCloudSync = "
0x1192b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x11930  pop
0x11931  dup
0x11932  ldarg.s  4
0x11934  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(bool)
0x11939  pop
0x1193a  dup
0x1193b  ldstr    asc_3F5CC// ", "
0x11940  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x11945  pop
0x11946  dup
0x11947  ldstr    aCrmserviceadmi// "crmServiceAdminInTheOrg = "
0x1194c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x11951  pop
0x11952  dup
0x11953  ldarg.s  5
0x11955  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(bool)
0x1195a  pop
0x1195b  dup
0x1195c  ldstr    asc_3F5CC// ", "
0x11961  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x11966  pop
0x11967  dup
0x11968  ldstr    aIsdeleted// "isDeleted = "
0x1196d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x11972  pop
0x11973  dup
0x11974  ldarg.s  6
0x11976  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(bool)
0x1197b  pop
0x1197c  dup
0x1197d  ldstr    asc_3F5CC// ", "
0x11982  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x11987  pop
0x11988  dup
0x11989  ldstr    aIssoftdeleted// "isSoftDeleted = "
0x1198e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x11993  pop
0x11994  dup
0x11995  ldarg.s  7
0x11997  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(bool)
0x1199c  pop
0x1199d  dup
0x1199e  ldstr    asc_3F5CC// ", "
0x119a3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x119a8  pop
0x119a9  dup
0x119aa  ldstr    aIsusercapabili// "isUserCapabilityValidAndCapabilityEnabl"...
0x119af  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x119b4  pop
0x119b5  dup
0x119b6  ldarg.s  8
0x119b8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(bool)
0x119bd  pop
0x119be  callvirt instance string [mscorlib]System.Object::ToString()
0x119c3  ret
```
