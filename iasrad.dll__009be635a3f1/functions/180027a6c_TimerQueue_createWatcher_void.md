# TimerQueue::createWatcher(void)

- ea: `0x180027a6c`
- end: `0x180027aad`
- name: `?createWatcher@TimerQueue@@AEAAXXZ`
- size: `65`
- prototype: `void __fastcall(TimerQueue *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180023af8`
- `0x180027d7c`

## callees

- `0x180027a6c`

## import_xrefs

- `iassvcs!IASRequestThread` at `0x180027a86`
- `iassvcs!IASRequestThread` at `0x180027a86`
- `KERNEL32!EnterCriticalSection` at `0x180027a7d`
- `KERNEL32!EnterCriticalSection` at `0x180027a7d`
- `KERNEL32!LeaveCriticalSection` at `0x180027aa6`

## pseudocode

```c
void __fastcall TimerQueue::createWatcher(TimerQueue *this)
{
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( (unsigned int)IASRequestThread(this) )
  {
    *((_BYTE *)this + 84) = 1;
    _InterlockedIncrement((volatile signed __int32 *)this + 20);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x180027a6c  mov     [rsp+arg_0], rbx
0x180027a71  push    rdi
0x180027a72  sub     rsp, 20h
0x180027a76  mov     rbx, rcx
0x180027a79  add     rcx, 8; lpCriticalSection
0x180027a7d  call    cs:__imp_EnterCriticalSection
0x180027a83  mov     rcx, rbx
0x180027a86  call    cs:__imp_IASRequestThread
0x180027a8c  test    eax, eax
0x180027a8e  jz      short loc_180027A98
0x180027a90  mov     byte ptr [rbx+54h], 1
0x180027a94  lock inc dword ptr [rbx+50h]
0x180027a98  lea     rcx, [rbx+8]
0x180027a9c  mov     rbx, [rsp+28h+arg_0]
0x180027aa1  add     rsp, 20h
0x180027aa5  pop     rdi
0x180027aa6  jmp     cs:__imp_LeaveCriticalSection
```
