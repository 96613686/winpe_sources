# McGenEventRegister_EventRegister

- ea: `0x140001d98`
- end: `0x140001dca`
- name: `McGenEventRegister_EventRegister`
- size: `50`
- prototype: `ULONG()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001938`

## callees

- `0x140001d98`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x140001dbf`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x140001dbf`

## pseudocode

```c
ULONG McGenEventRegister_EventRegister()
{
  ULONG result; // eax

  result = 0;
  if ( !MICROSOFT_WINDOWSPHONE_DATASHARING_Context )
    return EventRegister(
             &MICROSOFT_WINDOWSPHONE_DATASHARING,
             (PENABLECALLBACK)McGenControlCallbackV2,
             &MICROSOFT_WINDOWSPHONE_DATASHARING_Context,
             &MICROSOFT_WINDOWSPHONE_DATASHARING_Context);
  return result;
}

```

## disassembly

```asm
0x140001d98  sub     rsp, 28h
0x140001d9c  xor     eax, eax
0x140001d9e  cmp     cs:MICROSOFT_WINDOWSPHONE_DATASHARING_Context, rax
0x140001da5  jnz     short loc_140001DC5
0x140001da7  lea     r8, MICROSOFT_WINDOWSPHONE_DATASHARING_Context; CallbackContext
0x140001dae  mov     r9, r8; RegHandle
0x140001db1  lea     rdx, McGenControlCallbackV2; EnableCallback
0x140001db8  lea     rcx, MICROSOFT_WINDOWSPHONE_DATASHARING; ProviderId
0x140001dbf  call    cs:__imp_EventRegister
0x140001dc5  add     rsp, 28h
0x140001dc9  retn
```
