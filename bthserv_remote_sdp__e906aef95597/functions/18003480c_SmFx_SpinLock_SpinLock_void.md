# SmFx::SpinLock::~SpinLock(void)

- ea: `0x18003480c`
- end: `0x180034832`
- name: `??1SpinLock@SmFx@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(SmFx::SpinLock *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180032ed8`

## callees

- `0x18003480c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003481b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003481b`

## pseudocode

```c
void __fastcall SmFx::SpinLock::~SpinLock(struct _RTL_CRITICAL_SECTION *this)
{
  if ( LOBYTE(this[1].DebugInfo) )
  {
    DeleteCriticalSection(this);
    LOBYTE(this[1].DebugInfo) = 0;
  }
}

```

## disassembly

```asm
0x18003480c  push    rbx
0x18003480e  sub     rsp, 20h
0x180034812  cmp     byte ptr [rcx+28h], 0
0x180034816  mov     rbx, rcx
0x180034819  jz      short loc_18003482B
0x18003481b  call    cs:__imp_DeleteCriticalSection
0x180034822  nop     dword ptr [rax+rax+00h]
0x180034827  mov     byte ptr [rbx+28h], 0
0x18003482b  add     rsp, 20h
0x18003482f  pop     rbx
0x180034830  retn
```
