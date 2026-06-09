# wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)

- ea: `0x180012320`
- end: `0x1800123c6`
- name: `??1ActivityThreadWatcher@wil@@QEAA@XZ`
- size: `166`
- prototype: `void __fastcall(wil::ActivityThreadWatcher *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180011200`
- `0x180013048`
- `0x180051460`
- `0x1800514e0`
- `0x18005160f`

## callees

- `0x180012320`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012371`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012371`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012363`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012363`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001233d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001233d`

## string_xrefs

- `0x1800123a0`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::ActivityThreadWatcher::~ActivityThreadWatcher(wil::ActivityThreadWatcher *this)
{
  char *v2; // rbx
  char *v3; // rax
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (char *)this + 32;
  if ( *((_DWORD *)this + 14) )
  {
    if ( *((_DWORD *)this + 14) != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
      wil::details::g_pfnReportFatalUsageError(
        "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
        retaddr);
    *((_DWORD *)v2 + 6) = 0;
    while ( 1 )
    {
      v3 = **(char ***)v2;
      if ( !v3 )
        break;
      if ( v3 == v2 )
      {
        **(_QWORD **)v2 = *((_QWORD *)v2 + 2);
        break;
      }
      *(_QWORD *)v2 = v3 + 16;
    }
    *(_QWORD *)v2 = 0;
  }
  if ( *((_BYTE *)this + 24) )
  {
    v4 = (void *)*((_QWORD *)this + 2);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    *((_BYTE *)this + 24) = 0;
  }
  *((_QWORD *)this + 2) = 0;
}

```

## disassembly

```asm
0x180012320  mov     [rsp+arg_0], rbx
0x180012325  mov     [rsp+arg_8], rsi
0x18001232a  push    rdi
0x18001232b  sub     rsp, 20h
0x18001232f  mov     rdi, rcx
0x180012332  lea     rbx, [rcx+20h]
0x180012336  xor     esi, esi
0x180012338  cmp     [rbx+18h], esi
0x18001233b  jz      short loc_180012359
0x18001233d  call    cs:__imp_GetCurrentThreadId
0x180012343  cmp     [rbx+18h], eax
0x180012346  jnz     short loc_18001238F
0x180012348  mov     [rbx+18h], esi
0x18001234b  mov     rcx, [rbx]
0x18001234e  mov     rax, [rcx]
0x180012351  test    rax, rax
0x180012354  jnz     short loc_1800123AE
0x180012356  mov     [rbx], rsi
0x180012359  cmp     byte ptr [rdi+18h], 0
0x18001235d  jz      short loc_18001237B
0x18001235f  mov     rbx, [rdi+10h]
0x180012363  call    cs:__imp_GetProcessHeap
0x180012369  mov     r8, rbx; lpMem
0x18001236c  xor     edx, edx; dwFlags
0x18001236e  mov     rcx, rax; hHeap
0x180012371  call    cs:__imp_HeapFree
0x180012377  mov     byte ptr [rdi+18h], 0
0x18001237b  mov     [rdi+10h], rsi
0x18001237f  mov     rbx, [rsp+28h+arg_0]
0x180012384  mov     rsi, [rsp+28h+arg_8]
0x180012389  add     rsp, 20h
0x18001238d  pop     rdi
0x18001238e  retn
0x18001238f  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180012396  test    rax, rax
0x180012399  jz      short loc_180012348
0x18001239b  mov     rdx, [rsp+28h]
0x1800123a0  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800123a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123ac  jmp     short loc_180012348
0x1800123ae  cmp     rax, rbx
0x1800123b1  jz      short loc_1800123BC
0x1800123b3  add     rax, 10h
0x1800123b7  mov     [rbx], rax
0x1800123ba  jmp     short loc_18001234B
0x1800123bc  mov     rax, [rbx+10h]
0x1800123c0  mov     [rcx], rax
0x1800123c3  jmp     short loc_180012356
```
