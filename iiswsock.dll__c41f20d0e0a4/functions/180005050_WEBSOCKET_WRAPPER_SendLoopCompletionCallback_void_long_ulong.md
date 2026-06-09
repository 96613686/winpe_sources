# WEBSOCKET_WRAPPER::SendLoopCompletionCallback(void *,long,ulong)

- ea: `0x180005050`
- end: `0x18000505b`
- name: `?SendLoopCompletionCallback@WEBSOCKET_WRAPPER@@CAXPEAXJK@Z`
- size: `11`
- prototype: `void __fastcall(void *, int, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004ad4`

## pseudocode

```c
void __fastcall WEBSOCKET_WRAPPER::SendLoopCompletionCallback(WEBSOCKET_WRAPPER *a1, int a2, unsigned int a3)
{
  WEBSOCKET_WRAPPER::OnSendComplete(a1, a2, a3, 1);
}

```

## disassembly

```asm
0x180005050  mov     r9d, 1; int
0x180005056  jmp     ?OnSendComplete@WEBSOCKET_WRAPPER@@AEAAJJKH@Z; WEBSOCKET_WRAPPER::OnSendComplete(long,ulong,int)
```
