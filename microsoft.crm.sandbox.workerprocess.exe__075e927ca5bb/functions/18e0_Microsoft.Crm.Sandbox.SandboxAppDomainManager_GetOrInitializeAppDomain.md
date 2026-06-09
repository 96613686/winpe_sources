# Microsoft.Crm.Sandbox.SandboxAppDomainManager::GetOrInitializeAppDomain

- ea: `0x18e0`
- end: `0x1a2e`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomainManager::GetOrInitializeAppDomain`
- size: `334`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18b0`
- `0x1a30`

## callees

- `0xdf0`
- `0xe30`
- `0xe40`
- `0x18e0`
- `0x1af0`

## string_xrefs

- `0x198b`: `Don't expect warmup initialize the appDomain, it should already be created. This will trigger a deadlock.`

## pseudocode

```c

```

## disassembly

```asm
0x18e0  ldarg.0
0x18e1  ldc.i4.s 0x21
0x18e3  ldstr    aSandboxappdoma_21// "SandboxAppDomainManager.GetAppDomain"
0x18e8  ldc.i4.0
0x18e9  newarr   [mscorlib]System.Object
0x18ee  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x18f3  ldarg.1
0x18f4  callvirt instance void [System.Core]System.Threading.ReaderWriterLockSlim::EnterReadLock()
0x18f9  ldarg.2
0x18fa  ldind.ref
0x18fb  brfalse.s loc_197A
0x18fd  ldarg.0
0x18fe  ldc.i4.s 0x21
0x1900  ldstr    aSandboxappdoma_22// "SandboxAppDomainManager.GetAppDomain: E"...
0x1905  ldc.i4.0
0x1906  newarr   [mscorlib]System.Object
0x190b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1910  ldstr    aSandboxappdoma_23// "SandboxAppDomainManager.GetAppDomain: O"...
0x1915  stloc.0
0x1916  ldarg.0
0x1917  ldc.i4.s 0x21
0x1919  ldloc.0
0x191a  ldnull
0x191b  ldloca.s 2
0x191d  ldloca.s 1
0x191f  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::GetSandboxMessagePrefix(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[], string&, object[]&)
0x1924  ldarg.2
0x1925  ldind.ref
0x1926  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAppDomain::get_OrganizationId()
0x192b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1930  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1935  brfalse.s loc_194C
0x1937  ldarg.0
0x1938  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x193d  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1942  brfalse.s loc_194C
0x1944  ldarg.2
0x1945  ldind.ref
0x1946  ldarg.0
0x1947  callvirt instance void Microsoft.Crm.Sandbox.SandboxAppDomain::set_OrganizationId(valuetype [mscorlib]System.Guid value)
0x194c  ldarg.0
0x194d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1952  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1957  brfalse.s loc_1972
0x1959  ldarg.0
0x195a  ldarg.2
0x195b  ldind.ref
0x195c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAppDomain::get_OrganizationId()
0x1961  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1966  ldloc.2
0x1967  ldloc.1
0x1968  call     string [mscorlib]System.String::Format(string, object[])
0x196d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1972  ldarg.2
0x1973  ldind.ref
0x1974  stloc.3
0x1975  leave    loc_1A2C
0x197a  leave.s  loc_1983
0x197c  ldarg.1
0x197d  callvirt instance void [System.Core]System.Threading.ReaderWriterLockSlim::ExitReadLock()
0x1982  endfinally
0x1983  ldsfld   bool Microsoft.Crm.Sandbox.SandboxAppDomainManager::WarmUpInProgress
0x1988  ldc.i4.0
0x1989  ceq
0x198b  ldstr    aDonTExpectWarm// "Don't expect warmup initialize the appD"...
0x1990  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1995  ldarg.1
0x1996  callvirt instance void [System.Core]System.Threading.ReaderWriterLockSlim::EnterWriteLock()
0x199b  ldarg.2
0x199c  ldind.ref
0x199d  brtrue.s loc_19C4
0x199f  ldarg.0
0x19a0  ldc.i4.s 0x21
0x19a2  ldstr    aSandboxappdoma_24// "SandboxAppDomainManager.GetAppDomain: N"...
0x19a7  ldc.i4.0
0x19a8  newarr   [mscorlib]System.Object
0x19ad  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x19b2  ldarg.2
0x19b3  ldarg.0
0x19b4  newobj   instance void Microsoft.Crm.Sandbox.SandboxAppDomain::.ctor(valuetype [mscorlib]System.Guid organizationId)
0x19b9  stind.ref
0x19ba  ldarg.2
0x19bb  ldind.ref
0x19bc  ldarg.0
0x19bd  callvirt instance void Microsoft.Crm.Sandbox.SandboxAppDomain::set_OrganizationId(valuetype [mscorlib]System.Guid value)
0x19c2  leave.s  loc_1A1E
0x19c4  ldstr    aSandboxappdoma_23// "SandboxAppDomainManager.GetAppDomain: O"...
0x19c9  stloc.s  4
0x19cb  ldarg.0
0x19cc  ldc.i4.s 0x21
0x19ce  ldloc.s  4
0x19d0  ldnull
0x19d1  ldloca.s 6
0x19d3  ldloca.s 5
0x19d5  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::GetSandboxMessagePrefix(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[], string&, object[]&)
0x19da  ldarg.0
0x19db  ldc.i4.s 0x21
0x19dd  ldstr    aSandboxappdoma_25// "SandboxAppDomainManager.GetAppDomain: E"...
0x19e2  ldc.i4.0
0x19e3  newarr   [mscorlib]System.Object
0x19e8  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x19ed  ldarg.0
0x19ee  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x19f3  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x19f8  brfalse.s loc_1A15
0x19fa  ldarg.0
0x19fb  ldarg.2
0x19fc  ldind.ref
0x19fd  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAppDomain::get_OrganizationId()
0x1a02  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1a07  ldloc.s  6
0x1a09  ldloc.s  5
0x1a0b  call     string [mscorlib]System.String::Format(string, object[])
0x1a10  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1a15  leave.s  loc_1A1E
0x1a17  ldarg.1
0x1a18  callvirt instance void [System.Core]System.Threading.ReaderWriterLockSlim::ExitWriteLock()
0x1a1d  endfinally
0x1a1e  ldarg.2
0x1a1f  ldind.ref
0x1a20  brfalse.s loc_1A29
0x1a22  ldarg.2
0x1a23  ldind.ref
0x1a24  call     void Microsoft.Crm.Sandbox.SandboxAppDomainManager::WarmUpAppDomain(class Microsoft.Crm.Sandbox.SandboxAppDomain appDomain)
0x1a29  ldarg.2
0x1a2a  ldind.ref
0x1a2b  ret
0x1a2c  ldloc.3
0x1a2d  ret
```
