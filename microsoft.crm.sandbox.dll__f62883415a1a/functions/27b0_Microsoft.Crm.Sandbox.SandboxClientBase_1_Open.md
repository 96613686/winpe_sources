# Microsoft.Crm.Sandbox.SandboxClientBase`1::Open

- ea: `0x27b0`
- end: `0x27fd`
- name: `Microsoft.Crm.Sandbox.SandboxClientBase`1::Open`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x27b0`

## pseudocode

```c

```

## disassembly

```asm
0x27b0  ldarg.0
0x27b1  ldfld    bool class Microsoft.Crm.Sandbox.SandboxClientBase`1<var<u1>>::_opened
0x27b6  brfalse.s loc_27B9
0x27b8  ret
0x27b9  ldarg.0
0x27ba  ldfld    object class Microsoft.Crm.Sandbox.SandboxClientBase`1<var<u1>>::_openedLock
0x27bf  stloc.0
0x27c0  ldc.i4.0
0x27c1  stloc.1
0x27c2  ldloc.0
0x27c3  ldloca.s 1
0x27c5  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x27ca  ldarg.0
0x27cb  ldfld    bool class Microsoft.Crm.Sandbox.SandboxClientBase`1<var<u1>>::_opened
0x27d0  brfalse.s loc_27D4
0x27d2  leave.s  loc_27FC
0x27d4  ldarg.0
0x27d5  ldfld    var<u1> class Microsoft.Crm.Sandbox.SandboxClientBase`1<var<u1>>::_proxy
0x27da  box      var<u1>
0x27df  castclass [System.ServiceModel]System.ServiceModel.IClientChannel
0x27e4  callvirt instance void [System.ServiceModel]System.ServiceModel.ICommunicationObject::Open()
0x27e9  ldarg.0
0x27ea  ldc.i4.1
0x27eb  stfld    bool class Microsoft.Crm.Sandbox.SandboxClientBase`1<var<u1>>::_opened
0x27f0  leave.s  loc_27FC
0x27f2  ldloc.1
0x27f3  brfalse.s loc_27FB
0x27f5  ldloc.0
0x27f6  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x27fb  endfinally
0x27fc  ret
```
