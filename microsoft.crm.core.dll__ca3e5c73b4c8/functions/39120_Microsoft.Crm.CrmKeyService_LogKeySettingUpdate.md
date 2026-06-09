# Microsoft.Crm.CrmKeyService::LogKeySettingUpdate

- ea: `0x39120`
- end: `0x392bc`
- name: `Microsoft.Crm.CrmKeyService::LogKeySettingUpdate`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x68d80`

## callees

- `0x17d70`
- `0x17d90`
- `0x352e0`
- `0x39120`
- `0x39850`
- `0x39a90`

## string_xrefs

- `0x3917e`: `MSCRMKeyService`
- `0x3925b`: `MSCRMKeyService`

## pseudocode

```c

```

## disassembly

```asm
0x39120  ldnull
0x39121  stloc.0
0x39122  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.CrmKeyType, class Microsoft.Crm.CrmKeySetting> Microsoft.Crm.CrmKeyService::_keySettings
0x39127  ldarg.0
0x39128  callvirt instance valuetype Microsoft.Crm.CrmKeyType Microsoft.Crm.CrmKeySetting::get_KeyType()
0x3912d  ldloca.s 0
0x3912f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.CrmKeyType, class Microsoft.Crm.CrmKeySetting>::TryGetValue(var<u1>, !!T0)
0x39134  brtrue   loc_391F3
0x39139  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.CrmKeyType, class Microsoft.Crm.CrmKeySetting> Microsoft.Crm.CrmKeyService::_keySettings
0x3913e  stloc.1
0x3913f  ldc.i4.0
0x39140  stloc.2
0x39141  ldloc.1
0x39142  ldloca.s 2
0x39144  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x39149  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.CrmKeyType, class Microsoft.Crm.CrmKeySetting> Microsoft.Crm.CrmKeyService::_keySettings
0x3914e  ldarg.0
0x3914f  callvirt instance valuetype Microsoft.Crm.CrmKeyType Microsoft.Crm.CrmKeySetting::get_KeyType()
0x39154  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.CrmKeyType, class Microsoft.Crm.CrmKeySetting>::ContainsKey(var<u1>)
0x39159  brtrue   loc_391E4
0x3915e  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.CrmKeyType, class Microsoft.Crm.CrmKeySetting> Microsoft.Crm.CrmKeyService::_keySettings
0x39163  ldarg.0
0x39164  callvirt instance valuetype Microsoft.Crm.CrmKeyType Microsoft.Crm.CrmKeySetting::get_KeyType()
0x39169  ldarg.0
0x3916a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.CrmKeyType, class Microsoft.Crm.CrmKeySetting>::set_Item(var<u1>, !!T0)
0x3916f  newobj   instance void Microsoft.Crm.AutoReimpersonator::.ctor()
0x39174  stloc.3
0x39175  newobj   instance void Microsoft.Crm.CrmEventLog::.ctor()
0x3917a  stloc.s  4
0x3917c  ldloc.s  4
0x3917e  ldstr    aMscrmkeyservic// "MSCRMKeyService"
0x39183  ldc.i4.4
0x39184  ldc.i4   0x40004A10
0x39189  conv.i8
0x3918a  ldc.i4.3
0x3918b  newarr   [mscorlib]System.Object
0x39190  dup
0x39191  ldc.i4.0
0x39192  ldarg.0
0x39193  callvirt instance valuetype Microsoft.Crm.CrmKeyType Microsoft.Crm.CrmKeySetting::get_KeyType()
0x39198  box      Microsoft.Crm.CrmKeyType
0x3919d  stelem.ref
0x3919e  dup
0x3919f  ldc.i4.1
0x391a0  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.CrmKeyType, class Microsoft.Crm.CrmKeySetting> Microsoft.Crm.CrmKeyService::_keySettings
0x391a5  ldarg.0
0x391a6  callvirt instance valuetype Microsoft.Crm.CrmKeyType Microsoft.Crm.CrmKeySetting::get_KeyType()
0x391ab  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.CrmKeyType, class Microsoft.Crm.CrmKeySetting>::get_Item(void)
0x391b0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmKeySetting::get_ActiveKeyId()
0x391b5  box      [mscorlib]System.Guid
0x391ba  stelem.ref
0x391bb  dup
0x391bc  ldc.i4.2
0x391bd  ldarg.1
0x391be  box      [mscorlib]System.Guid
0x391c3  stelem.ref
0x391c4  callvirt instance void Microsoft.Crm.CrmEventLog::WriteEntry(string eventSourceName, valuetype [System]System.Diagnostics.EventLogEntryType eventType, int64 eventId, object[] values)
0x391c9  leave    loc_392BB
0x391ce  ldloc.s  4
0x391d0  brfalse.s loc_391D9
0x391d2  ldloc.s  4
0x391d4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x391d9  endfinally
0x391da  ldloc.3
0x391db  brfalse.s loc_391E3
0x391dd  ldloc.3
0x391de  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x391e3  endfinally
0x391e4  leave    loc_392BB
0x391e9  ldloc.2
0x391ea  brfalse.s loc_391F2
0x391ec  ldloc.1
0x391ed  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x391f2  endfinally
0x391f3  ldloc.0
0x391f4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmKeySetting::get_ActiveKeyId()
0x391f9  ldarg.0
0x391fa  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmKeySetting::get_ActiveKeyId()
0x391ff  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x39204  brfalse  loc_392BB
0x39209  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.CrmKeyType, class Microsoft.Crm.CrmKeySetting> Microsoft.Crm.CrmKeyService::_keySettings
0x3920e  stloc.1
0x3920f  ldc.i4.0
0x39210  stloc.2
0x39211  ldloc.1
0x39212  ldloca.s 2
0x39214  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x39219  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.CrmKeyType, class Microsoft.Crm.CrmKeySetting> Microsoft.Crm.CrmKeyService::_keySettings
0x3921e  ldarg.0
0x3921f  callvirt instance valuetype Microsoft.Crm.CrmKeyType Microsoft.Crm.CrmKeySetting::get_KeyType()
0x39224  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.CrmKeyType, class Microsoft.Crm.CrmKeySetting>::get_Item(void)
0x39229  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmKeySetting::get_ActiveKeyId()
0x3922e  ldarg.0
0x3922f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmKeySetting::get_ActiveKeyId()
0x39234  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x39239  brfalse.s loc_392AF
0x3923b  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.CrmKeyType, class Microsoft.Crm.CrmKeySetting> Microsoft.Crm.CrmKeyService::_keySettings
0x39240  ldarg.0
0x39241  callvirt instance valuetype Microsoft.Crm.CrmKeyType Microsoft.Crm.CrmKeySetting::get_KeyType()
0x39246  ldarg.0
0x39247  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.CrmKeyType, class Microsoft.Crm.CrmKeySetting>::set_Item(var<u1>, !!T0)
0x3924c  newobj   instance void Microsoft.Crm.AutoReimpersonator::.ctor()
0x39251  stloc.3
0x39252  newobj   instance void Microsoft.Crm.CrmEventLog::.ctor()
0x39257  stloc.s  5
0x39259  ldloc.s  5
0x3925b  ldstr    aMscrmkeyservic// "MSCRMKeyService"
0x39260  ldc.i4.4
0x39261  ldc.i4   0x40004A11
0x39266  conv.i8
0x39267  ldc.i4.3
0x39268  newarr   [mscorlib]System.Object
0x3926d  dup
0x3926e  ldc.i4.0
0x3926f  ldarg.0
0x39270  callvirt instance valuetype Microsoft.Crm.CrmKeyType Microsoft.Crm.CrmKeySetting::get_KeyType()
0x39275  box      Microsoft.Crm.CrmKeyType
0x3927a  stelem.ref
0x3927b  dup
0x3927c  ldc.i4.1
0x3927d  ldarg.0
0x3927e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmKeySetting::get_ActiveKeyId()
0x39283  box      [mscorlib]System.Guid
0x39288  stelem.ref
0x39289  dup
0x3928a  ldc.i4.2
0x3928b  ldarg.1
0x3928c  box      [mscorlib]System.Guid
0x39291  stelem.ref
0x39292  callvirt instance void Microsoft.Crm.CrmEventLog::WriteEntry(string eventSourceName, valuetype [System]System.Diagnostics.EventLogEntryType eventType, int64 eventId, object[] values)
0x39297  leave.s  loc_392BB
0x39299  ldloc.s  5
0x3929b  brfalse.s loc_392A4
0x3929d  ldloc.s  5
0x3929f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x392a4  endfinally
0x392a5  ldloc.3
0x392a6  brfalse.s loc_392AE
0x392a8  ldloc.3
0x392a9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x392ae  endfinally
0x392af  leave.s  loc_392BB
0x392b1  ldloc.2
0x392b2  brfalse.s loc_392BA
0x392b4  ldloc.1
0x392b5  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x392ba  endfinally
0x392bb  ret
```
