# NcsiSetThreadpoolTimer(_TP_TIMER *,_FILETIME *,ulong,ulong)

- ea: `0x18002c664`
- end: `0x18002c6b7`
- name: `?NcsiSetThreadpoolTimer@@YAXPEAU_TP_TIMER@@PEAU_FILETIME@@KK@Z`
- size: `83`
- prototype: `void __fastcall(PTP_TIMER pti, PFILETIME pftDueTime, DWORD msPeriod, DWORD msWindowLength)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000da48`
- `0x180043ce8`
- `0x18004d3c0`
- `0x18005709c`
- `0x180059e0c`
- `0x18005f454`

## callees

- `0x18002c664`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002c69b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002c69b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c6b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c680`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c680`

## pseudocode

```c
void __fastcall NcsiSetThreadpoolTimer(PTP_TIMER pti, PFILETIME pftDueTime, DWORD msPeriod, DWORD msWindowLength)
{
  EnterCriticalSection(&stru_18009D4B8);
  if ( byte_18009DAA0 )
    SetThreadpoolTimer(pti, pftDueTime, msPeriod, msWindowLength);
  LeaveCriticalSection(&stru_18009D4B8);
}

```

## disassembly

```asm
0x18002c664  push    rbx
0x18002c666  push    rbp
0x18002c667  push    rsi
0x18002c668  push    rdi
0x18002c669  sub     rsp, 28h
0x18002c66d  mov     rbx, rcx
0x18002c670  mov     ebp, r9d
0x18002c673  lea     rcx, stru_18009D4B8; lpCriticalSection
0x18002c67a  mov     esi, r8d
0x18002c67d  mov     rdi, rdx
0x18002c680  call    cs:__imp_EnterCriticalSection
0x18002c686  cmp     cs:byte_18009DAA0, 0
0x18002c68d  jz      short loc_18002C6A1
0x18002c68f  mov     r9d, ebp; msWindowLength
0x18002c692  mov     r8d, esi; msPeriod
0x18002c695  mov     rdx, rdi; pftDueTime
0x18002c698  mov     rcx, rbx; pti
0x18002c69b  call    cs:__imp_SetThreadpoolTimer
0x18002c6a1  lea     rcx, stru_18009D4B8
0x18002c6a8  add     rsp, 28h
0x18002c6ac  pop     rdi
0x18002c6ad  pop     rsi
0x18002c6ae  pop     rbp
0x18002c6af  pop     rbx
0x18002c6b0  jmp     cs:__imp_LeaveCriticalSection
```
