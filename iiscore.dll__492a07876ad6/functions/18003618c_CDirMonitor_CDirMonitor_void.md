# CDirMonitor::~CDirMonitor(void)

- ea: `0x18003618c`
- end: `0x1800361c5`
- name: `??1CDirMonitor@@QEAA@XZ`
- size: `57`
- prototype: `void __fastcall(CDirMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18001c268`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036199`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036199`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x1800361b9`
- `W3TP!ThreadPoolTerminate` at `0x1800361a5`
- `W3TP!ThreadPoolTerminate` at `0x1800361a5`

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
0x18003618c  push    rbx
0x18003618e  sub     rsp, 20h
0x180036192  mov     rbx, rcx
0x180036195  add     rcx, 48h ; 'H'; lpCriticalSection
0x180036199  call    cs:__imp_DeleteCriticalSection
0x1800361a0  nop     dword ptr [rax+rax+00h]
0x1800361a5  call    cs:__imp_?ThreadPoolTerminate@@YAJXZ; ThreadPoolTerminate(void)
0x1800361ac  nop     dword ptr [rax+rax+00h]
0x1800361b1  mov     rcx, rbx
0x1800361b4  add     rsp, 20h
0x1800361b8  pop     rbx
0x1800361b9  jmp     cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
```
