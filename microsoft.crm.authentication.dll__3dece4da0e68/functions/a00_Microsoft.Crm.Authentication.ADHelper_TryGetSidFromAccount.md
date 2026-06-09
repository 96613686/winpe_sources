# Microsoft.Crm.Authentication.ADHelper::TryGetSidFromAccount

- ea: `0xa00`
- end: `0xaed`
- name: `Microsoft.Crm.Authentication.ADHelper::TryGetSidFromAccount`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xc580`

## callees

- `0xa00`
- `0xb00`

## string_xrefs

- `0xa23`: `Retrieving SID from account {0}.`
- `0xa99`: `SID for account {0} is null.`
- `0xac5`: `Retrieved SID {0} for account {1}.`

## pseudocode

```c

```

## disassembly

```asm
0xa00  ldarg.1
0xa01  ldnull
0xa02  stind.ref
0xa03  ldarg.0
0xa04  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa09  brtrue   loc_AE8
0xa0e  ldnull
0xa0f  stloc.0
0xa10  ldc.i4.0
0xa11  stloc.1
0xa12  ldnull
0xa13  stloc.2
0xa14  ldc.i4.0
0xa15  stloc.3
0xa16  ldc.i4.0
0xa17  stloc.s  4
0xa19  ldc.i4.0
0xa1a  stloc.s  5
0xa1c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xa21  ldc.i4.s 0x16
0xa23  ldstr    aRetrievingSidF// "Retrieving SID from account {0}."
0xa28  ldc.i4.1
0xa29  newarr   [mscorlib]System.Object
0xa2e  dup
0xa2f  ldc.i4.0
0xa30  ldarg.0
0xa31  stelem.ref
0xa32  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa37  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0xa3c  stloc.s  6
0xa3e  ldnull
0xa3f  ldarg.0
0xa40  ldnull
0xa41  ldloca.s 1
0xa43  ldnull
0xa44  ldloca.s 3
0xa46  ldloca.s 4
0xa48  call     int32 Microsoft.Crm.Authentication.NativeMethods::LookupAccountNameW([hasfieldmarshal] string systemName, [hasfieldmarshal] string accountName, [out] unsigned int8[] pSid, unsigned int32& cbSid, class [mscorlib]System.Text.StringBuilder domainName, unsigned int32& cchReferencedDomainName, int32& nameUse)
0xa4d  stloc.s  5
0xa4f  ldloc.s  5
0xa51  brtrue.s loc_A80
0xa53  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0xa58  ldc.i4.s 0x7A
0xa5a  bne.un.s loc_A80
0xa5c  ldloc.1
0xa5d  newarr   [mscorlib]System.Byte
0xa62  stloc.0
0xa63  ldloc.3
0xa64  call     int32 [mscorlib]System.Convert::ToInt32(unsigned int32)
0xa69  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0xa6e  stloc.2
0xa6f  ldnull
0xa70  ldarg.0
0xa71  ldloc.0
0xa72  ldloca.s 1
0xa74  ldloc.2
0xa75  ldloca.s 3
0xa77  ldloca.s 4
0xa79  call     int32 Microsoft.Crm.Authentication.NativeMethods::LookupAccountNameW([hasfieldmarshal] string systemName, [hasfieldmarshal] string accountName, [out] unsigned int8[] pSid, unsigned int32& cbSid, class [mscorlib]System.Text.StringBuilder domainName, unsigned int32& cchReferencedDomainName, int32& nameUse)
0xa7e  stloc.s  5
0xa80  leave.s  loc_A8E
0xa82  ldloc.s  6
0xa84  brfalse.s loc_A8D
0xa86  ldloc.s  6
0xa88  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa8d  endfinally
0xa8e  ldloc.s  5
0xa90  brtrue.s loc_AB2
0xa92  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xa97  ldc.i4.s 0x16
0xa99  ldstr    aSidForAccount0// "SID for account {0} is null."
0xa9e  ldc.i4.1
0xa9f  newarr   [mscorlib]System.Object
0xaa4  dup
0xaa5  ldc.i4.0
0xaa6  ldarg.0
0xaa7  stelem.ref
0xaa8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xaad  ldc.i4.0
0xaae  stloc.s  7
0xab0  leave.s  loc_AEA
0xab2  ldloc.0
0xab3  brfalse.s loc_AE3
0xab5  ldarg.1
0xab6  ldloc.0
0xab7  ldc.i4.0
0xab8  newobj   instance void [mscorlib]System.Security.Principal.SecurityIdentifier::.ctor(unsigned int8[], int32)
0xabd  stind.ref
0xabe  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xac3  ldc.i4.s 0x16
0xac5  ldstr    aRetrievedSid0F// "Retrieved SID {0} for account {1}."
0xaca  ldc.i4.2
0xacb  newarr   [mscorlib]System.Object
0xad0  dup
0xad1  ldc.i4.0
0xad2  ldarg.1
0xad3  ldind.ref
0xad4  stelem.ref
0xad5  dup
0xad6  ldc.i4.1
0xad7  ldarg.0
0xad8  stelem.ref
0xad9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xade  ldc.i4.1
0xadf  stloc.s  7
0xae1  leave.s  loc_AEA
0xae3  leave.s  loc_AE8
0xae5  pop
0xae6  leave.s  loc_AE8
0xae8  ldc.i4.0
0xae9  ret
0xaea  ldloc.s  7
0xaec  ret
```
