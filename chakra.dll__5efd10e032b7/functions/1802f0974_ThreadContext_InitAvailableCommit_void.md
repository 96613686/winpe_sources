# ThreadContext::InitAvailableCommit(void)

- ea: `0x1802f0974`
- end: `0x1802f09e5`
- name: `?InitAvailableCommit@ThreadContext@@QEAAXXZ`
- size: `113`
- prototype: `void __fastcall(ThreadContext *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1802ef044`

## callees

- `0x1802f0974`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1802f09af`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1802f09af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802f09c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802f09c3`

## pseudocode

```c
void __fastcall ThreadContext::InitAvailableCommit(ThreadContext *this)
{
  const WCHAR *v1; // rax

  if ( !qword_18073F6A8 )
  {
    if ( !*((_BYTE *)this + 80) )
    {
      v1 = (const WCHAR *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 8) + 8LL))((char *)this + 64);
      *((_QWORD *)this + 9) = LoadLibraryExW(v1, 0, 0x800u);
      *((_BYTE *)this + 80) = 1;
    }
    GetCurrentProcess();
    _InterlockedCompareExchange64(&qword_18073F6A8, -1, 0);
  }
}

```

## disassembly

```asm
0x1802f0974  mov     [rsp+arg_0], rcx
0x1802f0979  push    rbx
0x1802f097a  sub     rsp, 20h
0x1802f097e  cmp     cs:qword_18073F6A8, 0
0x1802f0986  jnz     short loc_1802F09DE
0x1802f0988  mov     rbx, [rsp+28h+arg_0]
0x1802f098d  cmp     byte ptr [rbx+50h], 0
0x1802f0991  jnz     short loc_1802F09C3
0x1802f0993  mov     rax, [rbx+40h]
0x1802f0997  lea     rcx, [rbx+40h]
0x1802f099b  mov     rax, [rax+8]
0x1802f099f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802f09a4  mov     rcx, rax; lpLibFileName
0x1802f09a7  xor     edx, edx; hFile
0x1802f09a9  mov     r8d, 800h; dwFlags
0x1802f09af  call    cs:__imp_LoadLibraryExW
0x1802f09b6  nop     dword ptr [rax+rax+00h]
0x1802f09bb  mov     [rbx+48h], rax
0x1802f09bf  mov     byte ptr [rbx+50h], 1
0x1802f09c3  call    cs:__imp_GetCurrentProcess
0x1802f09ca  nop     dword ptr [rax+rax+00h]
0x1802f09cf  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1802f09d3  xor     eax, eax
0x1802f09d5  lock cmpxchg cs:qword_18073F6A8, rcx
0x1802f09de  add     rsp, 20h
0x1802f09e2  pop     rbx
0x1802f09e3  retn
```
