# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDOServiceCallback,IDOServiceCallback2>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDOServiceCallback,IDOServiceCallback2>(void)

- ea: `0x18000401c`
- end: `0x180004027`
- name: `??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDOServiceCallback@@UIDOServiceCallback2@@@Details@WRL@Microsoft@@IEAA@XZ`
- size: `11`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002110`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDOServiceCallback,IDOServiceCallback2>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDOServiceCallback,IDOServiceCallback2>(
        __int64 a1)
{
  *(_DWORD *)(a1 + 20) = 1;
  return a1;
}

```

## disassembly

```asm
0x18000401c  mov     dword ptr [rcx+14h], 1
0x180004023  mov     rax, rcx
0x180004026  retn
```
