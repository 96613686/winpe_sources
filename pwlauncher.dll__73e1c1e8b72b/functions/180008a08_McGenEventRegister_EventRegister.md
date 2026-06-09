# McGenEventRegister_EventRegister

- ea: `0x180008a08`
- end: `0x180008a3a`
- name: `McGenEventRegister_EventRegister`
- size: `50`
- prototype: `ULONG()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005a68`
- `0x180005c98`
- `0x180008720`

## callees

- `0x180008a08`

## import_xrefs

- `ADVAPI32!EventRegister` at `0x180008a2f`
- `ADVAPI32!EventRegister` at `0x180008a2f`

## pseudocode

```c
ULONG McGenEventRegister_EventRegister()
{
  ULONG result; // eax

  result = 0;
  if ( !PORTABLEWORKSPACE_LAUNCHER_Context )
    return EventRegister(
             &PORTABLEWORKSPACE_LAUNCHER,
             (PENABLECALLBACK)McGenControlCallbackV2,
             &PORTABLEWORKSPACE_LAUNCHER_Context,
             &PORTABLEWORKSPACE_LAUNCHER_Context);
  return result;
}

```

## disassembly

```asm
0x180008a08  sub     rsp, 28h
0x180008a0c  xor     eax, eax
0x180008a0e  cmp     cs:PORTABLEWORKSPACE_LAUNCHER_Context, rax
0x180008a15  jnz     short loc_180008A35
0x180008a17  lea     r8, PORTABLEWORKSPACE_LAUNCHER_Context; CallbackContext
0x180008a1e  mov     r9, r8; RegHandle
0x180008a21  lea     rdx, McGenControlCallbackV2; EnableCallback
0x180008a28  lea     rcx, PORTABLEWORKSPACE_LAUNCHER; ProviderId
0x180008a2f  call    cs:__imp_EventRegister
0x180008a35  add     rsp, 28h
0x180008a39  retn
```
