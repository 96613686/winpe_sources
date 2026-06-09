# Microsoft.Xrm.Tools.OwinJobManager.Server.Startup::Start

- ea: `0x1200`
- end: `0x124a`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.Startup::Start`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1200`

## pseudocode

```c

```

## disassembly

```asm
0x1200  ldstr    aHttpLocalhost0// "http://localhost:{0}/"
0x1205  ldarg.0
0x1206  box      [mscorlib]System.Int32
0x120b  call     string [mscorlib]System.String::Format(string, object)
0x1210  call     T0x2B00000A
0x1215  stloc.0
0x1216  ldstr    aListeningAtHtt// "Listening at http://localhost:{0}"
0x121b  ldarg.0
0x121c  box      [mscorlib]System.Int32
0x1221  call     string [mscorlib]System.String::Format(string, object)
0x1226  call     void [mscorlib]System.Console::WriteLine(string)
0x122b  ldarg.1
0x122c  brtrue.s loc_1236
0x122e  call     string [mscorlib]System.Console::ReadLine()
0x1233  pop
0x1234  leave.s  loc_1249
0x1236  ldarg.1
0x1237  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne()
0x123c  pop
0x123d  leave.s  loc_1249
0x123f  ldloc.0
0x1240  brfalse.s loc_1248
0x1242  ldloc.0
0x1243  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1248  endfinally
0x1249  ret
```
