# DimsProvEntry(ulong,void const *,unsigned __int64)

- ea: `0x180001d30`
- end: `0x180001d82`
- name: `?DimsProvEntry@@YAXKPEBX_K@Z`
- size: `82`
- prototype: `void __fastcall(__int64, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001d30`
- `0x180001d90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001d36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001d4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001d67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001d36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001d4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001d67`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180001d5c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180001d5c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180001d77`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180001d3f`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180001d3f`

## pseudocode

```c
void __fastcall DimsProvEntry(__int64 a1, const void *a2)
{
  HANDLE CurrentThread; // rax
  int ThreadPriority; // ebx
  HANDLE v4; // rax
  HANDLE v5; // rax

  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  if ( ThreadPriority == 0x7FFFFFFF )
    ThreadPriority = 0;
  v4 = GetCurrentThread();
  SetThreadPriority(v4, -1);
  AEMain();
  v5 = GetCurrentThread();
  SetThreadPriority(v5, ThreadPriority);
}

```

## disassembly

```asm
0x180001d30  push    rbx
0x180001d32  sub     rsp, 20h
0x180001d36  call    cs:__imp_GetCurrentThread
0x180001d3c  mov     rcx, rax; hThread
0x180001d3f  call    cs:__imp_GetThreadPriority
0x180001d45  mov     ebx, eax
0x180001d47  cmp     eax, 7FFFFFFFh
0x180001d4c  jz      short loc_180001D7E
0x180001d4e  call    cs:__imp_GetCurrentThread
0x180001d54  mov     rcx, rax; hThread
0x180001d57  mov     edx, 0FFFFFFFFh; nPriority
0x180001d5c  call    cs:__imp_SetThreadPriority
0x180001d62  call    ?AEMain@@YAXXZ; AEMain(void)
0x180001d67  call    cs:__imp_GetCurrentThread
0x180001d6d  mov     rcx, rax
0x180001d70  mov     edx, ebx
0x180001d72  add     rsp, 20h
0x180001d76  pop     rbx
0x180001d77  jmp     cs:__imp_SetThreadPriority
0x180001d7e  xor     ebx, ebx
0x180001d80  jmp     short loc_180001D4E
```
