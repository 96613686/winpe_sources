# PuDbgCreateEvent

- ea: `0x18001f500`
- end: `0x18001f529`
- name: `PuDbgCreateEvent`
- size: `41`
- prototype: `__int64 __fastcall(int, int, int, int, BOOL bManualReset, BOOL bInitialState)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001f500`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001f512`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001f512`

## pseudocode

```c
HANDLE __fastcall PuDbgCreateEvent(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        BOOL bManualReset,
        BOOL bInitialState)
{
  HANDLE result; // rax

  result = CreateEventA(0, bManualReset, bInitialState, 0);
  if ( result )
    _InterlockedIncrement(&g_PuDbgEventsCreated);
  return result;
}

```

## disassembly

```asm
0x18001f500  sub     rsp, 28h
0x18001f504  mov     r8d, [rsp+28h+bInitialState]; bInitialState
0x18001f509  xor     r9d, r9d; lpName
0x18001f50c  mov     edx, [rsp+28h+bManualReset]; bManualReset
0x18001f510  xor     ecx, ecx; lpEventAttributes
0x18001f512  call    cs:__imp_CreateEventA
0x18001f518  test    rax, rax
0x18001f51b  jz      short loc_18001F524
0x18001f51d  lock inc cs:?g_PuDbgEventsCreated@@3JA; long g_PuDbgEventsCreated
0x18001f524  add     rsp, 28h
0x18001f528  retn
```
