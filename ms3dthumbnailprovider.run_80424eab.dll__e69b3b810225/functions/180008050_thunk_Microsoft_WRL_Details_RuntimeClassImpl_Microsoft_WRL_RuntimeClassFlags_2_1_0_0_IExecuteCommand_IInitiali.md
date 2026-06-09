# [thunk]:Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IInitializeCommand,IObjectWithSelection>::Release`adjustor{8}' (void)

- ea: `0x180008050`
- end: `0x180008059`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIExecuteCommand@@UIInitializeCommand@@UIObjectWithSelection@@@Details@WRL@Microsoft@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007fe0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IInitializeCommand,IObjectWithSelection>::Release(
        __int64 a1)
{
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IInitializeCommand,IObjectWithSelection>::Release((volatile signed __int32 *)(a1 - 8));
}

```

## disassembly

```asm
0x180008050  sub     rcx, 8
0x180008054  jmp     ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIExecuteCommand@@UIInitializeCommand@@UIObjectWithSelection@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IInitializeCommand,IObjectWithSelection>::Release(void)
```
