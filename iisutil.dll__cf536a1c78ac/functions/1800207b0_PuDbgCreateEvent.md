# PuDbgCreateEvent

- ea: `0x1800207b0`
- end: `0x1800207e0`
- name: `PuDbgCreateEvent`
- size: `48`
- prototype: `__int64 __fastcall(int, int, int, int, BOOL bManualReset, BOOL bInitialState)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800207b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800207c2`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800207c2`

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
0x1800207b0  sub     rsp, 28h
0x1800207b4  mov     r8d, [rsp+28h+bInitialState]; bInitialState
0x1800207b9  xor     r9d, r9d; lpName
0x1800207bc  mov     edx, [rsp+28h+bManualReset]; bManualReset
0x1800207c0  xor     ecx, ecx; lpEventAttributes
0x1800207c2  call    cs:__imp_CreateEventA
0x1800207c9  nop     dword ptr [rax+rax+00h]
0x1800207ce  test    rax, rax
0x1800207d1  jz      short loc_1800207DA
0x1800207d3  lock inc cs:?g_PuDbgEventsCreated@@3JA; long g_PuDbgEventsCreated
0x1800207da  add     rsp, 28h
0x1800207de  retn
```
