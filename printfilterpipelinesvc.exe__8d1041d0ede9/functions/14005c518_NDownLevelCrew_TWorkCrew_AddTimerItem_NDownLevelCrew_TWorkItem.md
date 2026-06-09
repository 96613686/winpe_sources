# NDownLevelCrew::TWorkCrew::AddTimerItem(NDownLevelCrew::TWorkItem *)

- ea: `0x14005c518`
- end: `0x14005c5ba`
- name: `?AddTimerItem@TWorkCrew@NDownLevelCrew@@AEAAJPEAVTWorkItem@2@@Z`
- size: `162`
- prototype: `int(NDownLevelCrew::TWorkCrew *__hidden this, struct NDownLevelCrew::TWorkItem *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14005c400`

## callees

- `0x140011728`
- `0x14005c518`

## import_xrefs

- `KERNEL32!CreateTimerQueue` at `0x14005c540`
- `KERNEL32!CreateTimerQueue` at `0x14005c540`
- `KERNEL32!DeleteTimerQueueEx` at `0x14005c563`
- `KERNEL32!DeleteTimerQueueEx` at `0x14005c563`
- `KERNEL32!CreateTimerQueueTimer` at `0x14005c590`
- `KERNEL32!CreateTimerQueueTimer` at `0x14005c590`

## pseudocode

```c
__int64 __fastcall NDownLevelCrew::TWorkCrew::AddTimerItem(
        NDownLevelCrew::TWorkCrew *this,
        struct NDownLevelCrew::TWorkItem *a2)
{
  HANDLE TimerQueue; // rax
  NCoreLibrary *v6; // rcx

  if ( !a2 || *((_QWORD *)a2 + 13) )
    return 2147942487LL;
  if ( !*((_QWORD *)this + 3) )
  {
    TimerQueue = CreateTimerQueue();
    if ( !TimerQueue )
      return 2147500037LL;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 3, (signed __int64)TimerQueue, 0) )
      DeleteTimerQueueEx(TimerQueue, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  }
  if ( CreateTimerQueueTimer(
         (PHANDLE)a2 + 13,
         *((HANDLE *)this + 3),
         NDownLevelCrew::TWorkCrew::WaitOrTimerCallback,
         a2,
         *((_DWORD *)a2 + 23),
         *((_DWORD *)a2 + 22),
         *((_DWORD *)a2 + 24)) )
  {
    return 0;
  }
  else
  {
    return NCoreLibrary::GetLastErrorAsFailHRNoBreak(v6);
  }
}

```

## disassembly

```asm
0x14005c518  mov     [rsp+arg_0], rbx
0x14005c51d  mov     [rsp+arg_8], rsi
0x14005c522  push    rdi
0x14005c523  sub     rsp, 40h
0x14005c527  mov     rbx, rdx
0x14005c52a  mov     rdi, rcx
0x14005c52d  test    rdx, rdx
0x14005c530  jz      short loc_14005C5A5
0x14005c532  cmp     qword ptr [rdx+68h], 0
0x14005c537  jnz     short loc_14005C5A5
0x14005c539  cmp     qword ptr [rcx+18h], 0
0x14005c53e  jnz     short loc_14005C569
0x14005c540  call    cs:__imp_CreateTimerQueue
0x14005c546  mov     rcx, rax; TimerQueue
0x14005c549  test    rax, rax
0x14005c54c  jnz     short loc_14005C555
0x14005c54e  mov     eax, 80004005h
0x14005c553  jmp     short loc_14005C5AA
0x14005c555  xor     eax, eax
0x14005c557  lock cmpxchg [rdi+18h], rcx
0x14005c55d  jz      short loc_14005C569
0x14005c55f  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x14005c563  call    cs:__imp_DeleteTimerQueueEx
0x14005c569  mov     eax, [rbx+60h]
0x14005c56c  lea     r8, ?WaitOrTimerCallback@TWorkCrew@NDownLevelCrew@@CAXPEAXE@Z; Callback
0x14005c573  mov     rdx, [rdi+18h]; TimerQueue
0x14005c577  lea     rcx, [rbx+68h]; phNewTimer
0x14005c57b  mov     [rsp+48h+Flags], eax; Flags
0x14005c57f  mov     r9, rbx; Parameter
0x14005c582  mov     eax, [rbx+58h]
0x14005c585  mov     [rsp+48h+Period], eax; Period
0x14005c589  mov     eax, [rbx+5Ch]
0x14005c58c  mov     [rsp+48h+DueTime], eax; DueTime
0x14005c590  call    cs:__imp_CreateTimerQueueTimer
0x14005c596  test    eax, eax
0x14005c598  jz      short loc_14005C59E
0x14005c59a  xor     eax, eax
0x14005c59c  jmp     short loc_14005C5AA
0x14005c59e  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x14005c5a3  jmp     short loc_14005C5AA
0x14005c5a5  mov     eax, 80070057h
0x14005c5aa  mov     rbx, [rsp+48h+arg_0]
0x14005c5af  mov     rsi, [rsp+48h+arg_8]
0x14005c5b4  add     rsp, 40h
0x14005c5b8  pop     rdi
0x14005c5b9  retn
```
