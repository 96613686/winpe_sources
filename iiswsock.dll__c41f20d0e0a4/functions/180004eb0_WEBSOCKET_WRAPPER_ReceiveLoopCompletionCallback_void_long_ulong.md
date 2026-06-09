# WEBSOCKET_WRAPPER::ReceiveLoopCompletionCallback(void *,long,ulong)

- ea: `0x180004eb0`
- end: `0x180004eb5`
- name: `?ReceiveLoopCompletionCallback@WEBSOCKET_WRAPPER@@CAXPEAXJK@Z`
- size: `5`
- prototype: `void __fastcall(WEBSOCKET_WRAPPER *, int, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000477c`

## pseudocode

```c
// attributes: thunk
void __fastcall WEBSOCKET_WRAPPER::ReceiveLoopCompletionCallback(WEBSOCKET_WRAPPER *a1, int a2, unsigned int a3)
{
  WEBSOCKET_WRAPPER::OnReceiveComplete(a1, a2, a3);
}

```

## disassembly

```asm
0x180004eb0  jmp     ?OnReceiveComplete@WEBSOCKET_WRAPPER@@AEAAJJK@Z; WEBSOCKET_WRAPPER::OnReceiveComplete(long,ulong)
```
