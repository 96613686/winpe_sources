# <>c__DisplayClass5_0::<Create>b__0

- ea: `0x1bc0`
- end: `0x1c25`
- name: `<>c__DisplayClass5_0::<Create>b__0`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1bc0`

## string_xrefs

- `0x1c16`: `Microsoft.Xrm.DataProvider.JsonConverter.GlobalScopedLogger`

## pseudocode

```c

```

## disassembly

```asm
0x1bc0  nop
0x1bc1  ldarg.0
0x1bc2  ldfld    class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILoggerFactory <>c__DisplayClass5_0::sdkMessageScopeContext
0x1bc7  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x1bcc  callvirt instance class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILoggerFactory [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILoggerFactory::CreateContext(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x1bd1  stloc.0
0x1bd2  ldloc.0
0x1bd3  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILoggerFactory::GetContextProperties()
0x1bd8  stloc.1
0x1bd9  ldloc.1
0x1bda  ldstr    aRequestid// "requestId"
0x1bdf  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Remove(var<u1>)
0x1be4  pop
0x1be5  ldloc.1
0x1be6  ldstr    aExecutionid// "executionId"
0x1beb  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Remove(var<u1>)
0x1bf0  pop
0x1bf1  ldloc.1
0x1bf2  ldstr    aCorrelationid// "correlationId"
0x1bf7  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Remove(var<u1>)
0x1bfc  pop
0x1bfd  ldloc.1
0x1bfe  ldstr    aSdkmessage// "sdkMessage"
0x1c03  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Remove(var<u1>)
0x1c08  pop
0x1c09  ldloc.1
0x1c0a  ldstr    aPrimaryentitym// "primaryEntityMetadataId"
0x1c0f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Remove(var<u1>)
0x1c14  pop
0x1c15  ldloc.0
0x1c16  ldstr    aMicrosoftXrmDa_2// "Microsoft.Xrm.DataProvider.JsonConverte"...
0x1c1b  callvirt instance class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILoggerFactory::GetLogger(string)
0x1c20  stloc.2
0x1c21  br.s     loc_1C23
0x1c23  ldloc.2
0x1c24  ret
```
