# McGenEventRegister_EventRegister

- ea: `0x180001e10`
- end: `0x180001e40`
- name: `McGenEventRegister_EventRegister`
- size: `48`
- prototype: `ULONG()`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001200`
- `0x180001290`
- `0x1800015a0`
- `0x180001810`
- `0x180002060`

## callees

- `0x180001e10`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180001e39`

## pseudocode

```c
ULONG McGenEventRegister_EventRegister()
{
  if ( MICROSOFT_WINDOWSPHONE_DATASHARING_Context )
    return 0;
  else
    return EventRegister(
             (LPCGUID)MICROSOFT_WINDOWSPHONE_DATASHARING,
             (PENABLECALLBACK)McGenControlCallbackV2,
             &MICROSOFT_WINDOWSPHONE_DATASHARING_Context,
             &MICROSOFT_WINDOWSPHONE_DATASHARING_Context);
}

```

## disassembly

```asm
0x180001e10  cmp     cs:MICROSOFT_WINDOWSPHONE_DATASHARING_Context, 0
0x180001e18  jz      short loc_180001E1D
0x180001e1a  xor     eax, eax
0x180001e1c  retn
0x180001e1d  lea     r9, MICROSOFT_WINDOWSPHONE_DATASHARING_Context
0x180001e24  lea     r8, MICROSOFT_WINDOWSPHONE_DATASHARING_Context
0x180001e2b  lea     rdx, McGenControlCallbackV2
0x180001e32  lea     rcx, MICROSOFT_WINDOWSPHONE_DATASHARING
0x180001e39  jmp     cs:__imp_EventRegister
```
