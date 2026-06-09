# NcsiIsThreadpoolTimerSet(_TP_TIMER *)

- ea: `0x18002f090`
- end: `0x18002f0d3`
- name: `?NcsiIsThreadpoolTimerSet@@YAHPEAU_TP_TIMER@@@Z`
- size: `67`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180043ce8`
- `0x18005709c`

## callees

- `0x18002f090`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18002f0b6`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18002f0b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f0c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f0c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f0a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f0a0`

## pseudocode

```c
__int64 __fastcall NcsiIsThreadpoolTimerSet(PTP_TIMER pti)
{
  unsigned int v2; // ebx

  EnterCriticalSection(&stru_18009D4B8);
  if ( byte_18009DAA0 )
    v2 = IsThreadpoolTimerSet(pti);
  else
    v2 = 0;
  LeaveCriticalSection(&stru_18009D4B8);
  return v2;
}

```

## disassembly

```asm
0x18002f090  push    rbx
0x18002f092  sub     rsp, 20h
0x18002f096  mov     rbx, rcx
0x18002f099  lea     rcx, stru_18009D4B8; lpCriticalSection
0x18002f0a0  call    cs:__imp_EnterCriticalSection
0x18002f0a6  cmp     cs:byte_18009DAA0, 0
0x18002f0ad  jnz     short loc_18002F0B3
0x18002f0af  xor     ebx, ebx
0x18002f0b1  jmp     short loc_18002F0BE
0x18002f0b3  mov     rcx, rbx; pti
0x18002f0b6  call    cs:__imp_IsThreadpoolTimerSet
0x18002f0bc  mov     ebx, eax
0x18002f0be  lea     rcx, stru_18009D4B8; lpCriticalSection
0x18002f0c5  call    cs:__imp_LeaveCriticalSection
0x18002f0cb  mov     eax, ebx
0x18002f0cd  add     rsp, 20h
0x18002f0d1  pop     rbx
0x18002f0d2  retn
```
