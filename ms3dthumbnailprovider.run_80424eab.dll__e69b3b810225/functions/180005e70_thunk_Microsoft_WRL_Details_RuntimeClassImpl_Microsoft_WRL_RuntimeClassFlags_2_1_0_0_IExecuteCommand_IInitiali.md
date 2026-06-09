# [thunk]:Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IInitializeCommand,IObjectWithSelection>::AddRef`adjustor{16}' (void)

- ea: `0x180005e70`
- end: `0x180005e79`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIExecuteCommand@@UIInitializeCommand@@UIObjectWithSelection@@@Details@WRL@Microsoft@@WBA@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005e30`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IInitializeCommand,IObjectWithSelection>::AddRef(
        __int64 a1)
{
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IInitializeCommand,IObjectWithSelection>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x180005e70  sub     rcx, 10h
0x180005e74  jmp     ?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIExecuteCommand@@UIInitializeCommand@@UIObjectWithSelection@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IInitializeCommand,IObjectWithSelection>::AddRef(void)
```
