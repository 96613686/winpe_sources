# PerfDiagDm::ThreadPriorityContext::ThreadPriorityContext(int)

- ea: `0x1800421dc`
- end: `0x180042243`
- name: `??0ThreadPriorityContext@PerfDiagDm@@QEAA@H@Z`
- size: `103`
- prototype: `_QWORD(PerfDiagDm::ThreadPriorityContext *__hidden this, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18002b580`
- `0x180031aec`
- `0x1800ae95c`

## callees

- `0x1800421dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800421f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800421f0`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180042204`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180042204`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180042220`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180042220`

## pseudocode

```c
PerfDiagDm::ThreadPriorityContext *__fastcall PerfDiagDm::ThreadPriorityContext::ThreadPriorityContext(
        PerfDiagDm::ThreadPriorityContext *this,
        int a2)
{
  HANDLE CurrentThread; // rax
  void *v5; // rdi
  int ThreadPriority; // eax

  CurrentThread = GetCurrentThread();
  v5 = CurrentThread;
  if ( a2 == 0x10000 )
  {
    *(_DWORD *)this = 0x20000;
  }
  else
  {
    ThreadPriority = GetThreadPriority(CurrentThread);
    *(_DWORD *)this = ThreadPriority;
    if ( ThreadPriority == 0x7FFFFFFF )
      return this;
  }
  if ( !SetThreadPriority(v5, a2) )
    *(_DWORD *)this = 0x7FFFFFFF;
  return this;
}

```

## disassembly

```asm
0x1800421dc  mov     [rsp+arg_0], rbx
0x1800421e1  mov     [rsp+arg_8], rsi
0x1800421e6  push    rdi
0x1800421e7  sub     rsp, 20h
0x1800421eb  mov     esi, edx
0x1800421ed  mov     rbx, rcx
0x1800421f0  call    cs:__imp_GetCurrentThread
0x1800421f6  mov     rdi, rax
0x1800421f9  cmp     esi, 10000h
0x1800421ff  jz      short loc_180042215
0x180042201  mov     rcx, rax; hThread
0x180042204  call    cs:__imp_GetThreadPriority
0x18004220a  mov     [rbx], eax
0x18004220c  cmp     eax, 7FFFFFFFh
0x180042211  jnz     short loc_18004221B
0x180042213  jmp     short loc_180042230
0x180042215  mov     dword ptr [rbx], 20000h
0x18004221b  mov     edx, esi; nPriority
0x18004221d  mov     rcx, rdi; hThread
0x180042220  call    cs:__imp_SetThreadPriority
0x180042226  test    eax, eax
0x180042228  jnz     short loc_180042230
0x18004222a  mov     dword ptr [rbx], 7FFFFFFFh
0x180042230  mov     rsi, [rsp+28h+arg_8]
0x180042235  mov     rax, rbx
0x180042238  mov     rbx, [rsp+28h+arg_0]
0x18004223d  add     rsp, 20h
0x180042241  pop     rdi
0x180042242  retn
```
