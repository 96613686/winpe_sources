# SNIStopTimerTask

- ea: `0x1004194b0`
- end: `0x10041956c`
- name: `SNIStopTimerTask`
- size: `188`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x100434d74`
- `0x100437174`

## callees

- `0x1004194b0`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x1004194fa`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1004194fa`
- `KERNEL32!GetLastError` at `0x10041951f`
- `KERNEL32!GetLastError` at `0x10041951f`

## pseudocode

```c
__int64 __fastcall SNIStopTimerTask(__int64 a1)
{
  DWORD LastError; // ebx
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7810[0] )
    bidScopeEnterW(&v4, off_1005E7810[0], a1);
  if ( DeleteTimerQueueTimer(0, *(HANDLE *)(a1 + 16), (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
  {
    ((void (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Realloc)(g_pMO, a1);
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
  }
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E47B8[0] )
    bidTraceW(0, 2866176, off_1005E47B8[0], LastError);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v4);
  return LastError;
}

```

## disassembly

```asm
0x1004194b0  push    rbx
0x1004194b2  sub     rsp, 20h
0x1004194b6  mov     eax, cs:_bidGblFlags
0x1004194bc  mov     rbx, rcx
0x1004194bf  or      [rsp+28h+arg_0], 0FFFFFFFFFFFFFFFFh
0x1004194c5  mov     ecx, 20004h
0x1004194ca  and     eax, ecx
0x1004194cc  cmp     eax, ecx
0x1004194ce  jnz     short loc_1004194F0
0x1004194d0  mov     rax, cs:off_1005E7810; "<SNIStopTimerTask|API|SNI> hTimer: %p{T"...
0x1004194d7  test    rax, rax
0x1004194da  jz      short loc_1004194F0
0x1004194dc  mov     rdx, cs:off_1005E7810; "<SNIStopTimerTask|API|SNI> hTimer: %p{T"...
0x1004194e3  lea     rcx, [rsp+28h+arg_0]
0x1004194e8  mov     r8, rbx
0x1004194eb  call    _bidScopeEnterW
0x1004194f0  mov     rdx, [rbx+10h]; Timer
0x1004194f4  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1004194f8  xor     ecx, ecx; TimerQueue
0x1004194fa  call    cs:__imp_DeleteTimerQueueTimer
0x100419500  test    eax, eax
0x100419502  jz      short loc_10041951F
0x100419504  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x10041950b  mov     rdx, rbx
0x10041950e  mov     rax, [rcx]
0x100419511  mov     rax, [rax+68h]
0x100419515  call    cs:__guard_dispatch_icall_fptr
0x10041951b  xor     ebx, ebx
0x10041951d  jmp     short loc_100419527
0x10041951f  call    cs:__imp_GetLastError
0x100419525  mov     ebx, eax
0x100419527  mov     ecx, cs:_bidGblFlags
0x10041952d  mov     eax, 20002h
0x100419532  and     ecx, eax
0x100419534  cmp     ecx, eax
0x100419536  jnz     short loc_10041955A
0x100419538  mov     rcx, cs:off_1005E47B8; "<SNIStopTimerTask|RET|SNI> %d{WINERR}\n"
0x10041953f  test    rcx, rcx
0x100419542  jz      short loc_10041955A
0x100419544  mov     r8, cs:off_1005E47B8; "<SNIStopTimerTask|RET|SNI> %d{WINERR}\n"
0x10041954b  mov     r9d, ebx
0x10041954e  mov     edx, 2BBC00h
0x100419553  xor     ecx, ecx
0x100419555  call    _bidTraceW
0x10041955a  lea     rcx, [rsp+28h+arg_0]; this
0x10041955f  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x100419564  mov     eax, ebx
0x100419566  add     rsp, 20h
0x10041956a  pop     rbx
0x10041956b  retn
```
