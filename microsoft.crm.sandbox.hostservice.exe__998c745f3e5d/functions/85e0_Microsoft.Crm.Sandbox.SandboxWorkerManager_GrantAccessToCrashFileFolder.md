# Microsoft.Crm.Sandbox.SandboxWorkerManager::GrantAccessToCrashFileFolder

- ea: `0x85e0`
- end: `0x8613`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::GrantAccessToCrashFileFolder`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xc450`

## pseudocode

```c

```

## disassembly

```asm
0x85e0  ldnull
0x85e1  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::CrashFilePath(string)
0x85e6  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x85eb  dup
0x85ec  callvirt instance class [mscorlib]System.Security.AccessControl.DirectorySecurity [mscorlib]System.IO.DirectoryInfo::GetAccessControl()
0x85f1  stloc.0
0x85f2  ldstr    aSandboxworkerp// "SandboxWorkerProcess"
0x85f7  stloc.1
0x85f8  ldloc.0
0x85f9  ldloc.1
0x85fa  ldc.i4   0x301BF
0x85ff  ldc.i4.3
0x8600  ldc.i4.0
0x8601  ldc.i4.0
0x8602  newobj   instance void [mscorlib]System.Security.AccessControl.FileSystemAccessRule::.ctor(string, valuetype [mscorlib]System.Security.AccessControl.FileSystemRights, valuetype [mscorlib]System.Security.AccessControl.InheritanceFlags, valuetype [mscorlib]System.Security.AccessControl.PropagationFlags, valuetype [mscorlib]System.Security.AccessControl.AccessControlType)
0x8607  callvirt instance void [mscorlib]System.Security.AccessControl.FileSystemSecurity::AddAccessRule(class [mscorlib]System.Security.AccessControl.FileSystemAccessRule)
0x860c  ldloc.0
0x860d  callvirt instance void [mscorlib]System.IO.DirectoryInfo::SetAccessControl(class [mscorlib]System.Security.AccessControl.DirectorySecurity)
0x8612  ret
```
