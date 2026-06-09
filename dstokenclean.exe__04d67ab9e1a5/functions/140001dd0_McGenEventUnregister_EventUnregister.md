# McGenEventUnregister_EventUnregister

- ea: `0x140001dd0`
- end: `0x140001dfa`
- name: `McGenEventUnregister_EventUnregister`
- size: `42`
- prototype: `ULONG()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001aa0`

## callees

- `0x140001dd0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x140001de4`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x140001de4`

## pseudocode

```c
ULONG McGenEventUnregister_EventUnregister()
{
  ULONG result; // eax

  if ( !MICROSOFT_WINDOWSPHONE_DATASHARING_Context )
    return 0;
  result = EventUnregister(MICROSOFT_WINDOWSPHONE_DATASHARING_Context);
  MICROSOFT_WINDOWSPHONE_DATASHARING_Context = 0;
  return result;
}

```

## disassembly

```asm
0x140001dd0  sub     rsp, 28h
0x140001dd4  mov     rcx, cs:MICROSOFT_WINDOWSPHONE_DATASHARING_Context; RegHandle
0x140001ddb  test    rcx, rcx
0x140001dde  jnz     short loc_140001DE4
0x140001de0  xor     eax, eax
0x140001de2  jmp     short loc_140001DF5
0x140001de4  call    cs:__imp_EventUnregister
0x140001dea  mov     cs:MICROSOFT_WINDOWSPHONE_DATASHARING_Context, 0
0x140001df5  add     rsp, 28h
0x140001df9  retn
```
