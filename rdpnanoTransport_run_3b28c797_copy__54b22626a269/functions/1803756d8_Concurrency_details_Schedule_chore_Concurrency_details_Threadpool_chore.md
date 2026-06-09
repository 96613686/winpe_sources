# Concurrency::details::_Schedule_chore(Concurrency::details::_Threadpool_chore *)

- ea: `0x1803756d8`
- end: `0x180375715`
- name: `?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z`
- size: `61`
- prototype: `__int64 __fastcall(Concurrency::details *__hidden this, struct Concurrency::details::_Threadpool_chore *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18036fa94`

## callees

- `0x1803756a0`
- `0x1803756d8`

## import_xrefs

- `KERNEL32!CreateThreadpoolWork` at `0x1803756ee`
- `KERNEL32!CreateThreadpoolWork` at `0x1803756ee`
- `KERNEL32!GetLastError` at `0x18037570e`

## pseudocode

```c
DWORD __fastcall Concurrency::details::_Schedule_chore(
        Concurrency::details *this,
        struct Concurrency::details::_Threadpool_chore *a2)
{
  PTP_WORK ThreadpoolWork; // rax
  const struct Concurrency::details::_Threadpool_chore *v4; // rdx

  ThreadpoolWork = CreateThreadpoolWork(Concurrency::details::_anonymous_namespace_::_Task_scheduler_callback, this, 0);
  *(_QWORD *)this = ThreadpoolWork;
  if ( ThreadpoolWork )
    return Concurrency::details::_Reschedule_chore((LPCWSTR *)this, v4);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x1803756d8  push    rbx
0x1803756da  sub     rsp, 20h
0x1803756de  mov     rbx, rcx
0x1803756e1  mov     rdx, rcx; pv
0x1803756e4  lea     rcx, Concurrency__details___anonymous_namespace____Task_scheduler_callback; pfnwk
0x1803756eb  xor     r8d, r8d; pcbe
0x1803756ee  call    cs:__imp_CreateThreadpoolWork
0x1803756f4  mov     [rbx], rax
0x1803756f7  test    rax, rax
0x1803756fa  jz      short loc_180375709
0x1803756fc  mov     rcx, rbx; this
0x1803756ff  add     rsp, 20h
0x180375703  pop     rbx
0x180375704  jmp     ?_Reschedule_chore@details@Concurrency@@YAHPEBU_Threadpool_chore@12@@Z; Concurrency::details::_Reschedule_chore(Concurrency::details::_Threadpool_chore const *)
0x180375709  add     rsp, 20h
0x18037570d  pop     rbx
0x18037570e  jmp     cs:__imp_GetLastError
```
