# Microsoft.Crm.Sandbox.SandboxCertificateManager::GrantAccessToCertFolder

- ea: `0x2fe0`
- end: `0x3013`
- name: `Microsoft.Crm.Sandbox.SandboxCertificateManager::GrantAccessToCertFolder`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x2d90`

## pseudocode

```c

```

## disassembly

```asm
0x2fe0  ldnull
0x2fe1  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::SandboxWorkerCertificatePath(string)
0x2fe6  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x2feb  dup
0x2fec  callvirt instance class [mscorlib]System.Security.AccessControl.DirectorySecurity [mscorlib]System.IO.DirectoryInfo::GetAccessControl()
0x2ff1  stloc.0
0x2ff2  ldstr    aSandboxworkerp// "SandboxWorkerProcess"
0x2ff7  stloc.1
0x2ff8  ldloc.0
0x2ff9  ldloc.1
0x2ffa  ldc.i4   0x20089
0x2fff  ldc.i4.3
0x3000  ldc.i4.0
0x3001  ldc.i4.0
0x3002  newobj   instance void [mscorlib]System.Security.AccessControl.FileSystemAccessRule::.ctor(string, valuetype [mscorlib]System.Security.AccessControl.FileSystemRights, valuetype [mscorlib]System.Security.AccessControl.InheritanceFlags, valuetype [mscorlib]System.Security.AccessControl.PropagationFlags, valuetype [mscorlib]System.Security.AccessControl.AccessControlType)
0x3007  callvirt instance void [mscorlib]System.Security.AccessControl.FileSystemSecurity::AddAccessRule(class [mscorlib]System.Security.AccessControl.FileSystemAccessRule)
0x300c  ldloc.0
0x300d  callvirt instance void [mscorlib]System.IO.DirectoryInfo::SetAccessControl(class [mscorlib]System.Security.AccessControl.DirectorySecurity)
0x3012  ret
```
