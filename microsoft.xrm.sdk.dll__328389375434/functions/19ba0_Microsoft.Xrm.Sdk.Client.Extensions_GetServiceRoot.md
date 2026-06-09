# Microsoft.Xrm.Sdk.Client.Extensions::GetServiceRoot

- ea: `0x19ba0`
- end: `0x19bcd`
- name: `Microsoft.Xrm.Sdk.Client.Extensions::GetServiceRoot`
- size: `45`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x16650`
- `0x16df0`
- `0x17010`
- `0x170c0`
- `0x171b0`
- `0x18470`
- `0x184b0`

## callees

- `0x7ca0`

## pseudocode

```c

```

## disassembly

```asm
0x19ba0  ldarg.0
0x19ba1  ldstr    aUrl// "url"
0x19ba6  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x19bab  ldarg.0
0x19bac  newobj   instance void [System]System.UriBuilder::.ctor(class [System]System.Uri)
0x19bb1  dup
0x19bb2  ldsfld   string [mscorlib]System.String::Empty
0x19bb7  callvirt instance void [System]System.UriBuilder::set_Query(string)
0x19bbc  dup
0x19bbd  ldsfld   string [mscorlib]System.String::Empty
0x19bc2  callvirt instance void [System]System.UriBuilder::set_Path(string)
0x19bc7  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0x19bcc  ret
```
