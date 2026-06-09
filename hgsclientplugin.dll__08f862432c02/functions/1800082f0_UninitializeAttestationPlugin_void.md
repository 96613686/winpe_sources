# UninitializeAttestationPlugin(void *)

- ea: `0x1800082f0`
- end: `0x180008313`
- name: `?UninitializeAttestationPlugin@@YAJPEAX@Z`
- size: `35`
- prototype: `__int64 __fastcall(void *, const wchar_t *, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800069fc`
- `0x1800082f0`
- `0x1800085a0`

## string_xrefs

- `0x1800082f4`: `Built-in HGS plugin uninitialized`

## pseudocode

```c
__int64 __fastcall UninitializeAttestationPlugin(void *a1, const wchar_t *a2, __int64 a3, __int64 a4)
{
  Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceInfo(
    (wchar_t *)L"Built-in HGS plugin uninitialized",
    a2,
    a3,
    a4);
  McGenEventUnregister_EventUnregister();
  return 0;
}

```

## disassembly

```asm
0x1800082f0  sub     rsp, 28h
0x1800082f4  lea     rcx, aBuiltInHgsPlug; "Built-in HGS plugin uninitialized"
0x1800082fb  call    ?TraceInfo@EventUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEB_WZZ; Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceInfo(wchar_t const *,...)
0x180008300  call    McGenEventUnregister_EventUnregister
0x180008305  xor     eax, eax
0x180008307  jmp     short loc_18000830D
0x180008309  mov     eax, [rsp+28h+arg_8]
0x18000830d  add     rsp, 28h
0x180008311  retn
```
