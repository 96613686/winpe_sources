# McGenEventUnregister_EventUnregister

- ea: `0x180008a40`
- end: `0x180008a6a`
- name: `McGenEventUnregister_EventUnregister`
- size: `42`
- prototype: `ULONG()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005a68`
- `0x180005c98`
- `0x180008720`

## callees

- `0x180008a40`

## import_xrefs

- `ADVAPI32!EventUnregister` at `0x180008a54`
- `ADVAPI32!EventUnregister` at `0x180008a54`

## pseudocode

```c
ULONG McGenEventUnregister_EventUnregister()
{
  ULONG result; // eax

  if ( !PORTABLEWORKSPACE_LAUNCHER_Context )
    return 0;
  result = EventUnregister(PORTABLEWORKSPACE_LAUNCHER_Context);
  PORTABLEWORKSPACE_LAUNCHER_Context = 0;
  return result;
}

```

## disassembly

```asm
0x180008a40  sub     rsp, 28h
0x180008a44  mov     rcx, cs:PORTABLEWORKSPACE_LAUNCHER_Context; RegHandle
0x180008a4b  test    rcx, rcx
0x180008a4e  jnz     short loc_180008A54
0x180008a50  xor     eax, eax
0x180008a52  jmp     short loc_180008A65
0x180008a54  call    cs:__imp_EventUnregister
0x180008a5a  mov     cs:PORTABLEWORKSPACE_LAUNCHER_Context, 0
0x180008a65  add     rsp, 28h
0x180008a69  retn
```
