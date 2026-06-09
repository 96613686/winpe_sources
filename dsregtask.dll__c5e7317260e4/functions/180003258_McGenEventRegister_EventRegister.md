# McGenEventRegister_EventRegister

- ea: `0x180003258`
- end: `0x18000328a`
- name: `McGenEventRegister_EventRegister`
- size: `50`
- prototype: `ULONG()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`

## callees

- `0x180003258`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000327f`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000327f`

## pseudocode

```c
ULONG McGenEventRegister_EventRegister()
{
  ULONG result; // eax

  result = 0;
  if ( !UserDeviceRegistrationEventProvider_Context )
    return EventRegister(
             &UserDeviceRegistrationEventProvider,
             (PENABLECALLBACK)McGenControlCallbackV2,
             &UserDeviceRegistrationEventProvider_Context,
             &UserDeviceRegistrationEventProvider_Context);
  return result;
}

```

## disassembly

```asm
0x180003258  sub     rsp, 28h
0x18000325c  xor     eax, eax
0x18000325e  cmp     cs:UserDeviceRegistrationEventProvider_Context, rax
0x180003265  jnz     short loc_180003285
0x180003267  lea     r8, UserDeviceRegistrationEventProvider_Context; CallbackContext
0x18000326e  mov     r9, r8; RegHandle
0x180003271  lea     rdx, McGenControlCallbackV2; EnableCallback
0x180003278  lea     rcx, UserDeviceRegistrationEventProvider; ProviderId
0x18000327f  call    cs:__imp_EventRegister
0x180003285  add     rsp, 28h
0x180003289  retn
```
