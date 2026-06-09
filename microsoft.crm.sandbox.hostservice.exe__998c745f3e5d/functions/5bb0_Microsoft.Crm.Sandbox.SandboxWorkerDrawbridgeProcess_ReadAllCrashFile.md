# Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::ReadAllCrashFile

- ea: `0x5bb0`
- end: `0x5c55`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::ReadAllCrashFile`
- size: `165`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x5a60`
- `0x5bb0`

## pseudocode

```c

```

## disassembly

```asm
0x5bb0  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::BasePackagePath()
0x5bb5  dup
0x5bb6  ldarg.0
0x5bb7  call     instance string Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::get_WorkerPath()
0x5bbc  ldstr    aOutputLog// "output.log"
0x5bc1  call     string [mscorlib]System.IO.Path::Combine(string, string, string)
0x5bc6  stloc.0
0x5bc7  ldarg.0
0x5bc8  call     instance string Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::get_WorkerPath()
0x5bcd  ldstr    aOutputErr// "output.err"
0x5bd2  call     string [mscorlib]System.IO.Path::Combine(string, string, string)
0x5bd7  stloc.1
0x5bd8  ldloc.0
0x5bd9  call     bool [mscorlib]System.IO.File::Exists(string)
0x5bde  brtrue.s loc_5BE7
0x5be0  ldsfld   string [mscorlib]System.String::Empty
0x5be5  br.s     loc_5BED
0x5be7  ldloc.0
0x5be8  call     string [mscorlib]System.IO.File::ReadAllText(string)
0x5bed  stloc.2
0x5bee  ldloc.1
0x5bef  call     bool [mscorlib]System.IO.File::Exists(string)
0x5bf4  brtrue.s loc_5BFD
0x5bf6  ldsfld   string [mscorlib]System.String::Empty
0x5bfb  br.s     loc_5C03
0x5bfd  ldloc.1
0x5bfe  call     string [mscorlib]System.IO.File::ReadAllText(string)
0x5c03  stloc.3
0x5c04  ldloc.2
0x5c05  ldsfld   string [mscorlib]System.String::Empty
0x5c0a  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x5c0f  brtrue.s loc_5C1E
0x5c11  ldloc.3
0x5c12  ldsfld   string [mscorlib]System.String::Empty
0x5c17  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x5c1c  brfalse.s loc_5C4F
0x5c1e  ldstr    aStandardOutput// "Standard output:{0}{1}{2}Error output:{"...
0x5c23  ldc.i4.5
0x5c24  newarr   [mscorlib]System.Object
0x5c29  dup
0x5c2a  ldc.i4.0
0x5c2b  call     string [mscorlib]System.Environment::get_NewLine()
0x5c30  stelem.ref
0x5c31  dup
0x5c32  ldc.i4.1
0x5c33  ldloc.2
0x5c34  stelem.ref
0x5c35  dup
0x5c36  ldc.i4.2
0x5c37  call     string [mscorlib]System.Environment::get_NewLine()
0x5c3c  stelem.ref
0x5c3d  dup
0x5c3e  ldc.i4.3
0x5c3f  call     string [mscorlib]System.Environment::get_NewLine()
0x5c44  stelem.ref
0x5c45  dup
0x5c46  ldc.i4.4
0x5c47  ldloc.3
0x5c48  stelem.ref
0x5c49  call     string [mscorlib]System.String::Format(string, object[])
0x5c4e  ret
0x5c4f  ldsfld   string [mscorlib]System.String::Empty
0x5c54  ret
```
