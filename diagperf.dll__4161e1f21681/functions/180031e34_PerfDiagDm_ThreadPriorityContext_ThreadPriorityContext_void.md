# PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext(void)

- ea: `0x180031e34`
- end: `0x180031e5c`
- name: `??1ThreadPriorityContext@PerfDiagDm@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(PerfDiagDm::ThreadPriorityContext *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800279d8`
- `0x18002b580`
- `0x180031aec`
- `0x1800ae95c`
- `0x1800d1380`
- `0x1800d1652`

## callees

- `0x180031e34`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180031e3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180031e3d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180031e50`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180031e50`

## pseudocode

```c
void __fastcall PerfDiagDm::ThreadPriorityContext::~ThreadPriorityContext(PerfDiagDm::ThreadPriorityContext *this)
{
  HANDLE CurrentThread; // rax

  CurrentThread = GetCurrentThread();
  if ( *(_DWORD *)this != 0x7FFFFFFF )
    SetThreadPriority(CurrentThread, *(_DWORD *)this);
}

```

## disassembly

```asm
0x180031e34  push    rbx
0x180031e36  sub     rsp, 20h
0x180031e3a  mov     rbx, rcx
0x180031e3d  call    cs:__imp_GetCurrentThread
0x180031e43  cmp     dword ptr [rbx], 7FFFFFFFh
0x180031e49  jz      short loc_180031E56
0x180031e4b  mov     edx, [rbx]; nPriority
0x180031e4d  mov     rcx, rax; hThread
0x180031e50  call    cs:__imp_SetThreadPriority
0x180031e56  add     rsp, 20h
0x180031e5a  pop     rbx
0x180031e5b  retn
```
