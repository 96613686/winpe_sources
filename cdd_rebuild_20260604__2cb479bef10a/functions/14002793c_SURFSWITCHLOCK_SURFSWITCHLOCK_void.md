# SURFSWITCHLOCK::~SURFSWITCHLOCK(void)

- ea: `0x14002793c`
- end: `0x140027969`
- name: `??1SURFSWITCHLOCK@@QEAA@XZ`
- size: `45`
- prototype: `void __fastcall(SURFSWITCHLOCK *__hidden this)`
- caller_count: `22`
- callee_count: `0`
- tags: ``

## callers

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

- `WIN32K!W32GetSessionState` at `0x140027940`
- `WIN32K!W32GetSessionState` at `0x140027940`
- `WIN32K!EngReleaseSemaphore` at `0x140027957`
- `WIN32K!EngReleaseSemaphore` at `0x140027957`

## pseudocode

```c
void __fastcall SURFSWITCHLOCK::~SURFSWITCHLOCK(SURFSWITCHLOCK *this, __int64 a2)
{
  __int64 SessionState; // rax

  SessionState = W32GetSessionState(this, a2);
  EngReleaseSemaphore(*(HSEMAPHORE *)(*(_QWORD *)(SessionState + 72) + 3344LL));
}

```

## disassembly

```asm
0x14002793c  sub     rsp, 28h
0x140027940  call    cs:__imp_W32GetSessionState
0x140027947  nop     dword ptr [rax+rax+00h]
0x14002794c  mov     rcx, [rax+48h]
0x140027950  mov     rcx, [rcx+0D10h]; hsem
0x140027957  call    cs:__imp_EngReleaseSemaphore
0x14002795e  nop     dword ptr [rax+rax+00h]
0x140027963  add     rsp, 28h
0x140027967  retn
```
