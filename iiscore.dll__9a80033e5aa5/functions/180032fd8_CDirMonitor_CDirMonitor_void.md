# CDirMonitor::~CDirMonitor(void)

- ea: `0x180032fd8`
- end: `0x180033000`
- name: `??1CDirMonitor@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(CDirMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18001ab68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180032fe5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180032fe5`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180032ff9`
- `W3TP!ThreadPoolTerminate` at `0x180032feb`
- `W3TP!ThreadPoolTerminate` at `0x180032feb`

## pseudocode

```c
void __fastcall CDirMonitor::~CDirMonitor(CDirMonitor *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  ThreadPoolTerminate();
  CLKRHashTable::~CLKRHashTable(this);
}

```

## disassembly

```asm
0x180032fd8  push    rbx
0x180032fda  sub     rsp, 20h
0x180032fde  mov     rbx, rcx
0x180032fe1  add     rcx, 48h ; 'H'; lpCriticalSection
0x180032fe5  call    cs:__imp_DeleteCriticalSection
0x180032feb  call    cs:__imp_?ThreadPoolTerminate@@YAJXZ; ThreadPoolTerminate(void)
0x180032ff1  mov     rcx, rbx
0x180032ff4  add     rsp, 20h
0x180032ff8  pop     rbx
0x180032ff9  jmp     cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
```
