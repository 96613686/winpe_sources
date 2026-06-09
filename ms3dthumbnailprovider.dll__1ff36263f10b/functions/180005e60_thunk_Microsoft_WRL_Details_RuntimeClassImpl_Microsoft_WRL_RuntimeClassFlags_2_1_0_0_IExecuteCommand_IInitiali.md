# [thunk]:Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IInitializeCommand,IObjectWithSelection>::AddRef`adjustor{8}' (void)

- ea: `0x180005e60`
- end: `0x180005e69`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIExecuteCommand@@UIInitializeCommand@@UIObjectWithSelection@@@Details@WRL@Microsoft@@W7EAAKXZ`
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
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IInitializeCommand,IObjectWithSelection>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180005e60  sub     rcx, 8
0x180005e64  jmp     ?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIExecuteCommand@@UIInitializeCommand@@UIObjectWithSelection@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IInitializeCommand,IObjectWithSelection>::AddRef(void)
```
