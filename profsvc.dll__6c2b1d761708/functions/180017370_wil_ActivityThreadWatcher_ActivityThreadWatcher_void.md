# wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)

- ea: `0x180017370`
- end: `0x180017429`
- name: `??1ActivityThreadWatcher@wil@@QEAA@XZ`
- size: `185`
- prototype: `void __fastcall(wil::ActivityThreadWatcher *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800156ec`
- `0x180016150`
- `0x180054650`
- `0x18005477f`
- `0x180054800`

## callees

- `0x180017370`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800173cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800173cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800173b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800173b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001738d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001738d`

## string_xrefs

- `0x180017403`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180017370  mov     [rsp+arg_0], rbx
0x180017375  mov     [rsp+arg_8], rsi
0x18001737a  push    rdi
0x18001737b  sub     rsp, 20h
0x18001737f  mov     rdi, rcx
0x180017382  lea     rbx, [rcx+20h]
0x180017386  xor     esi, esi
0x180017388  cmp     [rbx+18h], esi
0x18001738b  jz      short loc_1800173AF
0x18001738d  call    cs:__imp_GetCurrentThreadId
0x180017394  nop     dword ptr [rax+rax+00h]
0x180017399  cmp     [rbx+18h], eax
0x18001739c  jnz     short loc_1800173F2
0x18001739e  mov     [rbx+18h], esi
0x1800173a1  mov     rcx, [rbx]
0x1800173a4  mov     rax, [rcx]
0x1800173a7  test    rax, rax
0x1800173aa  jnz     short loc_180017411
0x1800173ac  mov     [rbx], rsi
0x1800173af  cmp     byte ptr [rdi+18h], 0
0x1800173b3  jz      short loc_1800173DD
0x1800173b5  mov     rbx, [rdi+10h]
0x1800173b9  call    cs:__imp_GetProcessHeap
0x1800173c0  nop     dword ptr [rax+rax+00h]
0x1800173c5  mov     r8, rbx; lpMem
0x1800173c8  xor     edx, edx; dwFlags
0x1800173ca  mov     rcx, rax; hHeap
0x1800173cd  call    cs:__imp_HeapFree
0x1800173d4  nop     dword ptr [rax+rax+00h]
0x1800173d9  mov     byte ptr [rdi+18h], 0
0x1800173dd  mov     [rdi+10h], rsi
0x1800173e1  mov     rbx, [rsp+28h+arg_0]
0x1800173e6  mov     rsi, [rsp+28h+arg_8]
0x1800173eb  add     rsp, 20h
0x1800173ef  pop     rdi
0x1800173f0  retn
0x1800173f2  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800173f9  test    rax, rax
0x1800173fc  jz      short loc_18001739E
0x1800173fe  mov     rdx, [rsp+28h]
0x180017403  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18001740a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001740f  jmp     short loc_18001739E
0x180017411  cmp     rax, rbx
0x180017414  jz      short loc_18001741F
0x180017416  add     rax, 10h
0x18001741a  mov     [rbx], rax
0x18001741d  jmp     short loc_1800173A1
0x18001741f  mov     rax, [rbx+10h]
0x180017423  mov     [rcx], rax
0x180017426  jmp     short loc_1800173AC
```
