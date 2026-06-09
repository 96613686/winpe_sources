# Microsoft.Crm.Application.Controls.MailboxHealthGridDataProvider::Evaluate

- ea: `0x5c320`
- end: `0x5c601`
- name: `Microsoft.Crm.Application.Controls.MailboxHealthGridDataProvider::Evaluate`
- size: `737`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x5c190`

## callees

- `0x5c320`
- `0x5c610`

## string_xrefs

- `0x5c36e`: `incomingemaildeliverymethod`
- `0x5c37e`: `incomingemaildeliverymethod`
- `0x5c3db`: `incomingemailstatus`
- `0x5c34d`: `testemailconfigurationscheduled`
- `0x5c35d`: `testemailconfigurationscheduled`
- `0x5c420`: `enabledforincomingemail`
- `0x5c515`: `processinglastattemptedon`
- `0x5c529`: `processinglastattemptedon`

## pseudocode

```c

```

## disassembly

```asm
0x5c320  ldarg.1
0x5c321  ldstr    aStatecode// "statecode"
0x5c326  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5c32b  brfalse.s loc_5C34C
0x5c32d  ldarg.1
0x5c32e  ldstr    aStatecode// "statecode"
0x5c333  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5c338  callvirt instance string [mscorlib]System.Object::ToString()
0x5c33d  ldloca.s 0
0x5c33f  call     T0x2B00006B
0x5c344  brfalse.s loc_5C34C
0x5c346  ldloc.0
0x5c347  ldc.i4.1
0x5c348  bne.un.s loc_5C34C
0x5c34a  ldc.i4.0
0x5c34b  ret
0x5c34c  ldarg.1
0x5c34d  ldstr    aTestemailconfi// "testemailconfigurationscheduled"
0x5c352  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5c357  brtrue.s loc_5C35C
0x5c359  ldc.i4.0
0x5c35a  br.s     loc_5C36C
0x5c35c  ldarg.1
0x5c35d  ldstr    aTestemailconfi// "testemailconfigurationscheduled"
0x5c362  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5c367  unbox.any [mscorlib]System.Boolean
0x5c36c  stloc.1
0x5c36d  ldarg.1
0x5c36e  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x5c373  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5c378  brtrue.s loc_5C37D
0x5c37a  ldc.i4.0
0x5c37b  br.s     loc_5C390
0x5c37d  ldarg.1
0x5c37e  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x5c383  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5c388  unbox.any [mscorlib]System.Int32
0x5c38d  ldc.i4.2
0x5c38e  ceq
0x5c390  stloc.2
0x5c391  ldarg.1
0x5c392  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x5c397  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5c39c  brtrue.s loc_5C3A1
0x5c39e  ldc.i4.0
0x5c39f  br.s     loc_5C3B4
0x5c3a1  ldarg.1
0x5c3a2  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x5c3a7  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5c3ac  unbox.any [mscorlib]System.Int32
0x5c3b1  ldc.i4.2
0x5c3b2  ceq
0x5c3b4  stloc.3
0x5c3b5  ldarg.1
0x5c3b6  ldstr    aActdeliverymet// "actdeliverymethod"
0x5c3bb  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5c3c0  brtrue.s loc_5C3C5
0x5c3c2  ldc.i4.0
0x5c3c3  br.s     loc_5C3D8
0x5c3c5  ldarg.1
0x5c3c6  ldstr    aActdeliverymet// "actdeliverymethod"
0x5c3cb  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5c3d0  unbox.any [mscorlib]System.Int32
0x5c3d5  ldc.i4.1
0x5c3d6  ceq
0x5c3d8  stloc.s  4
0x5c3da  ldarg.1
0x5c3db  ldstr    aIncomingemails// "incomingemailstatus"
0x5c3e0  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5c3e5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5c3ea  call     bool [mscorlib]System.Convert::ToBoolean(object, class [mscorlib]System.IFormatProvider)
0x5c3ef  stloc.s  5
0x5c3f1  ldarg.1
0x5c3f2  ldstr    aOutgoingemails// "outgoingemailstatus"
0x5c3f7  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5c3fc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5c401  call     bool [mscorlib]System.Convert::ToBoolean(object, class [mscorlib]System.IFormatProvider)
0x5c406  stloc.s  6
0x5c408  ldarg.1
0x5c409  ldstr    aActstatus// "actstatus"
0x5c40e  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5c413  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5c418  call     bool [mscorlib]System.Convert::ToBoolean(object, class [mscorlib]System.IFormatProvider)
0x5c41d  stloc.s  7
0x5c41f  ldarg.1
0x5c420  ldstr    aEnabledforinco// "enabledforincomingemail"
0x5c425  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5c42a  dup
0x5c42b  brtrue.s loc_5C434
0x5c42d  pop
0x5c42e  ldc.i4.0
0x5c42f  box      [mscorlib]System.Boolean
0x5c434  unbox.any [mscorlib]System.Boolean
0x5c439  stloc.s  8
0x5c43b  ldarg.1
0x5c43c  ldstr    aEnabledforoutg// "enabledforoutgoingemail"
0x5c441  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5c446  dup
0x5c447  brtrue.s loc_5C450
0x5c449  pop
0x5c44a  ldc.i4.0
0x5c44b  box      [mscorlib]System.Boolean
0x5c450  unbox.any [mscorlib]System.Boolean
0x5c455  stloc.s  9
0x5c457  ldarg.1
0x5c458  ldstr    aEnabledforact// "enabledforact"
0x5c45d  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5c462  dup
0x5c463  brtrue.s loc_5C46C
0x5c465  pop
0x5c466  ldc.i4.0
0x5c467  box      [mscorlib]System.Boolean
0x5c46c  unbox.any [mscorlib]System.Boolean
0x5c471  stloc.s  0xA
0x5c473  ldarg.1
0x5c474  ldstr    aTransientfailu// "transientfailurecount"
0x5c479  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5c47e  brtrue.s loc_5C483
0x5c480  ldc.i4.0
0x5c481  br.s     loc_5C493
0x5c483  ldarg.1
0x5c484  ldstr    aTransientfailu// "transientfailurecount"
0x5c489  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5c48e  unbox.any [mscorlib]System.Int32
0x5c493  dup
0x5c494  ldc.i4   0xF00000
0x5c499  and
0x5c49a  ldc.i4.s 0x14
0x5c49c  shr
0x5c49d  stloc.s  0xB
0x5c49f  dup
0x5c4a0  ldc.i4   0xF000000
0x5c4a5  and
0x5c4a6  ldc.i4.s 0x18
0x5c4a8  shr
0x5c4a9  stloc.s  0xC
0x5c4ab  ldc.i4   0xF0000
0x5c4b0  and
0x5c4b1  ldc.i4.s 0x10
0x5c4b3  shr
0x5c4b4  stloc.s  0xD
0x5c4b6  ldarg.0
0x5c4b7  ldloc.s  0xB
0x5c4b9  call     instance int32 Microsoft.Crm.Application.Controls.MailboxHealthGridDataProvider::InspectTransientFailureCount(int32 tranientFailureCount)
0x5c4be  stloc.s  0xE
0x5c4c0  ldarg.0
0x5c4c1  ldloc.s  0xC
0x5c4c3  call     instance int32 Microsoft.Crm.Application.Controls.MailboxHealthGridDataProvider::InspectTransientFailureCount(int32 tranientFailureCount)
0x5c4c8  stloc.s  0xF
0x5c4ca  ldarg.0
0x5c4cb  ldloc.s  0xD
0x5c4cd  call     instance int32 Microsoft.Crm.Application.Controls.MailboxHealthGridDataProvider::InspectTransientFailureCount(int32 tranientFailureCount)
0x5c4d2  stloc.s  0x10
0x5c4d4  ldloc.2
0x5c4d5  ldloc.s  8
0x5c4d7  and
0x5c4d8  ldloc.s  5
0x5c4da  and
0x5c4db  brfalse.s loc_5C4E1
0x5c4dd  ldloc.s  0xE
0x5c4df  brfalse.s loc_5C4E4
0x5c4e1  ldloc.2
0x5c4e2  brtrue.s loc_5C511
0x5c4e4  ldloc.3
0x5c4e5  ldloc.s  9
0x5c4e7  and
0x5c4e8  ldloc.s  6
0x5c4ea  and
0x5c4eb  brfalse.s loc_5C4F1
0x5c4ed  ldloc.s  0xF
0x5c4ef  brfalse.s loc_5C4F4
0x5c4f1  ldloc.3
0x5c4f2  brtrue.s loc_5C511
0x5c4f4  ldloc.s  4
0x5c4f6  ldloc.s  0xA
0x5c4f8  and
0x5c4f9  ldloc.s  7
0x5c4fb  and
0x5c4fc  brfalse.s loc_5C502
0x5c4fe  ldloc.s  0x10
0x5c500  brfalse.s loc_5C506
0x5c502  ldloc.s  4
0x5c504  brtrue.s loc_5C511
0x5c506  ldloc.1
0x5c507  brtrue.s loc_5C511
0x5c509  ldarg.2
0x5c50a  ldc.i4.2
0x5c50b  bne.un.s loc_5C50F
0x5c50d  ldc.i4.1
0x5c50e  ret
0x5c50f  ldc.i4.0
0x5c510  ret
0x5c511  ldloc.1
0x5c512  brfalse.s loc_5C593
0x5c514  ldarg.1
0x5c515  ldstr    aProcessinglast// "processinglastattemptedon"
0x5c51a  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5c51f  brtrue.s loc_5C528
0x5c521  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x5c526  br.s     loc_5C538
0x5c528  ldarg.1
0x5c529  ldstr    aProcessinglast// "processinglastattemptedon"
0x5c52e  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5c533  unbox.any [mscorlib]System.DateTime
0x5c538  stloc.s  0x11
0x5c53a  ldloca.s 0x11
0x5c53c  call     instance valuetype [mscorlib]System.DateTimeKind [mscorlib]System.DateTime::get_Kind()
0x5c541  ldc.i4.2
0x5c542  bne.un.s loc_5C557
0x5c544  ldloc.s  0x11
0x5c546  ldc.i4.2
0x5c547  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x5c54c  stloc.s  0x12
0x5c54e  ldloca.s 0x12
0x5c550  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0x5c555  stloc.s  0x11
0x5c557  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x5c55c  stloc.s  0x12
0x5c55e  ldloca.s 0x12
0x5c560  ldloc.s  0x11
0x5c562  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.DateTime)
0x5c567  stloc.s  0x13
0x5c569  ldloca.s 0x13
0x5c56b  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0x5c570  ldc.r8   20.0
0x5c579  ble.un.s loc_5C587
0x5c57b  ldarg.2
0x5c57c  ldc.i4.8
0x5c57d  beq.s    loc_5C583
0x5c57f  ldarg.2
0x5c580  ldc.i4.3
0x5c581  bne.un.s loc_5C585
0x5c583  ldc.i4.1
0x5c584  ret
0x5c585  ldc.i4.0
0x5c586  ret
0x5c587  ldarg.2
0x5c588  ldc.i4.7
0x5c589  beq.s    loc_5C58F
0x5c58b  ldarg.2
0x5c58c  ldc.i4.3
0x5c58d  bne.un.s loc_5C591
0x5c58f  ldc.i4.1
0x5c590  ret
0x5c591  ldc.i4.0
0x5c592  ret
0x5c593  ldloc.2
0x5c594  brfalse.s loc_5C59A
0x5c596  ldloc.s  8
0x5c598  brfalse.s loc_5C5BF
0x5c59a  ldloc.2
0x5c59b  brfalse.s loc_5C5A1
0x5c59d  ldloc.s  5
0x5c59f  brfalse.s loc_5C5BF
0x5c5a1  ldloc.3
0x5c5a2  brfalse.s loc_5C5A8
0x5c5a4  ldloc.s  9
0x5c5a6  brfalse.s loc_5C5BF
0x5c5a8  ldloc.3
0x5c5a9  brfalse.s loc_5C5AF
0x5c5ab  ldloc.s  6
0x5c5ad  brfalse.s loc_5C5BF
0x5c5af  ldloc.s  4
0x5c5b1  brfalse.s loc_5C5B7
0x5c5b3  ldloc.s  0xA
0x5c5b5  brfalse.s loc_5C5BF
0x5c5b7  ldloc.s  4
0x5c5b9  brfalse.s loc_5C5CB
0x5c5bb  ldloc.s  7
0x5c5bd  brtrue.s loc_5C5CB
0x5c5bf  ldarg.2
0x5c5c0  ldc.i4.3
0x5c5c1  beq.s    loc_5C5C7
0x5c5c3  ldarg.2
0x5c5c4  ldc.i4.6
0x5c5c5  bne.un.s loc_5C5C9
0x5c5c7  ldc.i4.1
0x5c5c8  ret
0x5c5c9  ldc.i4.0
0x5c5ca  ret
0x5c5cb  ldloc.2
0x5c5cc  ldloc.s  8
0x5c5ce  and
0x5c5cf  brfalse.s loc_5C5D6
0x5c5d1  ldloc.s  0xE
0x5c5d3  ldc.i4.7
0x5c5d4  beq.s    loc_5C5ED
0x5c5d6  ldloc.3
0x5c5d7  ldloc.s  9
0x5c5d9  and
0x5c5da  brfalse.s loc_5C5E1
0x5c5dc  ldloc.s  0xF
0x5c5de  ldc.i4.7
0x5c5df  beq.s    loc_5C5ED
0x5c5e1  ldloc.s  4
0x5c5e3  ldloc.s  0xA
0x5c5e5  and
0x5c5e6  brfalse.s loc_5C5F5
0x5c5e8  ldloc.s  0x10
0x5c5ea  ldc.i4.7
  ... truncated ...
```
