# SURFSWITCHLOCK::SURFSWITCHLOCK(_SURFOBJ *,_SURFOBJ *)

- ea: `0x140025030`
- end: `0x140025086`
- name: `??0SURFSWITCHLOCK@@QEAA@PEAU_SURFOBJ@@0@Z`
- size: `86`
- prototype: `SURFSWITCHLOCK *__fastcall(SURFSWITCHLOCK *__hidden this, struct _SURFOBJ *, struct _SURFOBJ *)`
- caller_count: `24`
- callee_count: `0`
- tags: ``

## callers

- `0x140021660`
- `0x1400217b0`
- `0x140025090`
- `0x1400255b0`
- `0x140025c90`
- `0x1400261a0`
- `0x1400267f0`
- `0x140026d40`
- `0x140027370`
- `0x140034a60`
- `0x140034b30`
- `0x1400355b0`
- `0x140035630`
- `0x1400357a0`
- `0x1400358d0`
- `0x1400359f0`
- `0x140035a90`
- `0x1400361e0`
- `0x1400363d0`
- `0x140036510`
- `0x1400365a0`
- `0x140036670`
- `0x140036830`
- `0x1400368b0`

## import_xrefs

- `WIN32K!W32GetSessionState` at `0x140025048`
- `WIN32K!W32GetSessionState` at `0x140025048`
- `WIN32K!EngAcquireSemaphore` at `0x14002505f`
- `WIN32K!EngAcquireSemaphore` at `0x14002505f`

## pseudocode

```c
SURFSWITCHLOCK *__fastcall SURFSWITCHLOCK::SURFSWITCHLOCK(
        SURFSWITCHLOCK *this,
        struct _SURFOBJ *a2,
        struct _SURFOBJ *a3)
{
  __int64 SessionState; // rax
  SURFSWITCHLOCK *result; // rax

  SessionState = W32GetSessionState(this, a2);
  EngAcquireSemaphore(*(HSEMAPHORE *)(*(_QWORD *)(SessionState + 72) + 3344LL));
  *(_QWORD *)this = a2;
  result = this;
  *((_QWORD *)this + 1) = a3;
  return result;
}

```

## disassembly

```asm
0x140025030  mov     [rsp+arg_0], rbx
0x140025035  mov     [rsp+arg_8], rsi
0x14002503a  push    rdi
0x14002503b  sub     rsp, 20h
0x14002503f  mov     rsi, r8
0x140025042  mov     rbx, rdx
0x140025045  mov     rdi, rcx
0x140025048  call    cs:__imp_W32GetSessionState
0x14002504f  nop     dword ptr [rax+rax+00h]
0x140025054  mov     rcx, [rax+48h]
0x140025058  mov     rcx, [rcx+0D10h]; hsem
0x14002505f  call    cs:__imp_EngAcquireSemaphore
0x140025066  nop     dword ptr [rax+rax+00h]
0x14002506b  mov     [rdi], rbx
0x14002506e  mov     rax, rdi
0x140025071  mov     rbx, [rsp+28h+arg_0]
0x140025076  mov     [rdi+8], rsi
0x14002507a  mov     rsi, [rsp+28h+arg_8]
0x14002507f  add     rsp, 20h
0x140025083  pop     rdi
0x140025084  retn
```
