# Microsoft.Crm.Common.Application.Commands.ApplicationCommand::IsOnlyOneState

- ea: `0x25b0`
- end: `0x262a`
- name: `Microsoft.Crm.Common.Application.Commands.ApplicationCommand::IsOnlyOneState`
- size: `122`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2570`
- `0x2590`

## callees

- `0x25b0`

## pseudocode

```c

```

## disassembly

```asm
0x25b0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x25b5  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x25ba  ldc.i4.4
0x25bb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x25c0  ldstr    aStatuscode// "statuscode"
0x25c5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x25ca  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusAttributeMetadata
0x25cf  ldstr    aLead// "lead"
0x25d4  ldarg.0
0x25d5  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x25da  stloc.0
0x25db  ldc.i4.0
0x25dc  stloc.1
0x25dd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::get_OptionSet()
0x25e2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_OptionsInDisplayOrder()
0x25e7  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::GetEnumerator()
0x25ec  stloc.2
0x25ed  br.s     loc_2611
0x25ef  ldloc.2
0x25f0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Current()
0x25f5  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusOption
0x25fa  stloc.3
0x25fb  ldloc.0
0x25fc  ldloc.3
0x25fd  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusOption::get_State()
0x2602  bne.un.s loc_2608
0x2604  ldloc.1
0x2605  ldc.i4.1
0x2606  add
0x2607  stloc.1
0x2608  ldloc.1
0x2609  ldc.i4.1
0x260a  ble.s    loc_2611
0x260c  ldc.i4.0
0x260d  stloc.s  4
0x260f  leave.s  loc_2627
0x2611  ldloc.2
0x2612  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2617  brtrue.s loc_25EF
0x2619  leave.s  loc_2625
0x261b  ldloc.2
0x261c  brfalse.s loc_2624
0x261e  ldloc.2
0x261f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2624  endfinally
0x2625  ldc.i4.1
0x2626  ret
0x2627  ldloc.s  4
0x2629  ret
```
