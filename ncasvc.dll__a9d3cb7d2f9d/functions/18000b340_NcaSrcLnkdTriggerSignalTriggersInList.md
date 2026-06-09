# NcaSrcLnkdTriggerSignalTriggersInList

- ea: `0x18000b340`
- end: `0x18000b3a1`
- name: `NcaSrcLnkdTriggerSignalTriggersInList`
- size: `97`
- prototype: `void __fastcall(__int64)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bb40`
- `0x18000c1d0`
- `0x18000c770`
- `0x18000c790`
- `0x18000d480`
- `0x18000f090`
- `0x18000f8d0`

## callees

- `0x18000b340`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b395`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b36f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b36f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b352`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b352`

## pseudocode

```c
void __fastcall NcaSrcLnkdTriggerSignalTriggersInList(__int64 a1)
{
  _QWORD *i; // rbx

  EnterCriticalSection((LPCRITICAL_SECTION)a1);
  for ( i = *(_QWORD **)(a1 + 48); i != (_QWORD *)(a1 + 48); i = (_QWORD *)*i )
    SetEvent(*(HANDLE *)(i[3] + 8LL));
  LeaveCriticalSection((LPCRITICAL_SECTION)a1);
}

```

## disassembly

```asm
0x18000b340  mov     [rsp+arg_0], rbx
0x18000b345  mov     [rsp+arg_8], rsi
0x18000b34a  push    rdi
0x18000b34b  sub     rsp, 20h
0x18000b34f  mov     rdi, rcx
0x18000b352  call    cs:__imp_EnterCriticalSection
0x18000b359  nop     dword ptr [rax+rax+00h]
0x18000b35e  lea     rsi, [rdi+30h]
0x18000b362  mov     rbx, [rsi]
0x18000b365  jmp     short loc_18000B37E
0x18000b367  mov     rcx, [rbx+18h]
0x18000b36b  mov     rcx, [rcx+8]; hEvent
0x18000b36f  call    cs:__imp_SetEvent
0x18000b376  nop     dword ptr [rax+rax+00h]
0x18000b37b  mov     rbx, [rbx]
0x18000b37e  cmp     rbx, rsi
0x18000b381  jnz     short loc_18000B367
0x18000b383  mov     rcx, rdi
0x18000b386  mov     rbx, [rsp+28h+arg_0]
0x18000b38b  mov     rsi, [rsp+28h+arg_8]
0x18000b390  add     rsp, 20h
0x18000b394  pop     rdi
0x18000b395  jmp     cs:__imp_LeaveCriticalSection
```
