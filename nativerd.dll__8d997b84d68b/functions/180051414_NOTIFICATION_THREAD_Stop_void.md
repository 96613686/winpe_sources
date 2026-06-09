# NOTIFICATION_THREAD::Stop(void)

- ea: `0x180051414`
- end: `0x1800514fd`
- name: `?Stop@NOTIFICATION_THREAD@@QEAAJXZ`
- size: `233`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001a450`

## callees

- `0x180051090`
- `0x180051414`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051492`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051492`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800514c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800514e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800514c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800514e2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800514b7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800514b7`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180051488`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180051488`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18005145d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18005145d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180051454`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180051454`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180051449`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180051449`

## pseudocode

```c
__int64 __fastcall NOTIFICATION_THREAD::Stop(PVOID Context)
{
  unsigned int v2; // ebx
  struct _TP_TIMER *v3; // rcx
  void *v4; // rcx
  signed int LastError; // eax
  void *v6; // rcx
  void *v7; // rcx

  if ( _InterlockedCompareExchange((volatile signed __int32 *)Context + 14, 1, 0) )
    return (unsigned int)-2147023781;
  v3 = *(struct _TP_TIMER **)Context;
  if ( v3 )
  {
    SetThreadpoolTimer(v3, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*(PTP_TIMER *)Context, 1);
    CloseThreadpoolTimer(*(PTP_TIMER *)Context);
    *(_QWORD *)Context = 0;
  }
  NOTIFICATION_THREAD::ProcessPollingList(0, Context, 0);
  v4 = (void *)*((_QWORD *)Context + 6);
  if ( !v4 || PostQueuedCompletionStatus(v4, 0, 0, 0) )
  {
    v6 = (void *)*((_QWORD *)Context + 5);
    if ( v6 )
    {
      if ( WaitForSingleObject(v6, 0xFFFFFFFF) == -1 || !CloseHandle(*((HANDLE *)Context + 5)) )
        goto LABEL_7;
      *((_QWORD *)Context + 5) = 0;
    }
    v7 = (void *)*((_QWORD *)Context + 6);
    v2 = 0;
    if ( !v7 )
      return v2;
    if ( CloseHandle(v7) )
    {
      *((_QWORD *)Context + 6) = 0;
      return v2;
    }
  }
LABEL_7:
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return v2;
}

```

## disassembly

```asm
0x180051414  mov     [rsp+arg_8], rbx
0x180051419  push    rdi
0x18005141a  sub     rsp, 20h
0x18005141e  mov     rdi, rcx
0x180051421  mov     ebx, 1
0x180051426  xor     eax, eax
0x180051428  lock cmpxchg [rcx+38h], ebx
0x18005142d  jz      short loc_180051439
0x18005142f  mov     ebx, 8007045Bh
0x180051434  jmp     loc_1800514F0
0x180051439  mov     rcx, [rcx]; pti
0x18005143c  test    rcx, rcx
0x18005143f  jz      short loc_18005146A
0x180051441  xor     r9d, r9d; msWindowLength
0x180051444  xor     r8d, r8d; msPeriod
0x180051447  xor     edx, edx; pftDueTime
0x180051449  call    cs:__imp_SetThreadpoolTimer
0x18005144f  mov     rcx, [rdi]; pti
0x180051452  mov     edx, ebx; fCancelPendingCallbacks
0x180051454  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18005145a  mov     rcx, [rdi]; pti
0x18005145d  call    cs:__imp_CloseThreadpoolTimer
0x180051463  mov     qword ptr [rdi], 0
0x18005146a  xor     r8d, r8d; Timer
0x18005146d  mov     rdx, rdi; Context
0x180051470  xor     ecx, ecx; Instance
0x180051472  call    ?ProcessPollingList@NOTIFICATION_THREAD@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; NOTIFICATION_THREAD::ProcessPollingList(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)
0x180051477  mov     rcx, [rdi+30h]; CompletionPort
0x18005147b  test    rcx, rcx
0x18005147e  jz      short loc_1800514A9
0x180051480  xor     r9d, r9d; lpOverlapped
0x180051483  xor     r8d, r8d; dwCompletionKey
0x180051486  xor     edx, edx; dwNumberOfBytesTransferred
0x180051488  call    cs:__imp_PostQueuedCompletionStatus
0x18005148e  test    eax, eax
0x180051490  jnz     short loc_1800514A9
0x180051492  call    cs:__imp_GetLastError
0x180051498  mov     ebx, eax
0x18005149a  test    eax, eax
0x18005149c  jle     short loc_1800514F0
0x18005149e  movzx   ebx, ax
0x1800514a1  or      ebx, 80070000h
0x1800514a7  jmp     short loc_1800514F0
0x1800514a9  mov     rcx, [rdi+28h]; hHandle
0x1800514ad  test    rcx, rcx
0x1800514b0  jz      short loc_1800514D7
0x1800514b2  or      ebx, 0FFFFFFFFh
0x1800514b5  mov     edx, ebx; dwMilliseconds
0x1800514b7  call    cs:__imp_WaitForSingleObject
0x1800514bd  cmp     eax, ebx
0x1800514bf  jz      short loc_180051492
0x1800514c1  mov     rcx, [rdi+28h]; hObject
0x1800514c5  call    cs:__imp_CloseHandle
0x1800514cb  test    eax, eax
0x1800514cd  jz      short loc_180051492
0x1800514cf  mov     qword ptr [rdi+28h], 0
0x1800514d7  mov     rcx, [rdi+30h]; hObject
0x1800514db  xor     ebx, ebx
0x1800514dd  test    rcx, rcx
0x1800514e0  jz      short loc_1800514F0
0x1800514e2  call    cs:__imp_CloseHandle
0x1800514e8  test    eax, eax
0x1800514ea  jz      short loc_180051492
0x1800514ec  mov     [rdi+30h], rbx
0x1800514f0  mov     eax, ebx
0x1800514f2  mov     rbx, [rsp+28h+arg_8]
0x1800514f7  add     rsp, 20h
0x1800514fb  pop     rdi
0x1800514fc  retn
```
