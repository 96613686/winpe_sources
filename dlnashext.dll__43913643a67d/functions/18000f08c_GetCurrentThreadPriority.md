# GetCurrentThreadPriority

- ea: `0x18000f08c`
- end: `0x18000f0a4`
- name: `GetCurrentThreadPriority`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180003fc0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000f090`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000f090`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18000f09d`

## pseudocode

```c
int GetCurrentThreadPriority()
{
  HANDLE CurrentThread; // rax

  CurrentThread = GetCurrentThread();
  return GetThreadPriority(CurrentThread);
}

```

## disassembly

```asm
0x18000f08c  sub     rsp, 28h
0x18000f090  call    cs:__imp_GetCurrentThread
0x18000f096  mov     rcx, rax
0x18000f099  add     rsp, 28h
0x18000f09d  jmp     cs:__imp_GetThreadPriority
```
