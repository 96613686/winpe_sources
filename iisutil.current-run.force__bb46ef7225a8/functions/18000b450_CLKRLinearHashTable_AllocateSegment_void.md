# CLKRLinearHashTable::_AllocateSegment(void)

- ea: `0x18000b450`
- end: `0x18000b610`
- name: `?_AllocateSegment@CLKRLinearHashTable@@AEBAQEAVCSegment@@XZ`
- size: `448`
- prototype: `struct CSegment *__fastcall(CLKRLinearHashTable *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180008220`
- `0x180009700`

## callees

- `0x180008000`
- `0x18000869c`
- `0x18000b450`
- `0x18000b620`
- `0x18000b650`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b51b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b51b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b47c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b47c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b4f2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b4f2`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000b494`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000b494`

## pseudocode

```c
struct CSegment *__fastcall CLKRLinearHashTable::_AllocateSegment(CLKRLinearHashTable *this)
{
  int v1; // edx
  ALLOC_CACHE_HANDLER *v2; // rdi
  _QWORD *v3; // rbx
  DWORD CurrentThreadId; // eax
  CBucket *v5; // rsi
  CBucket *v6; // rdi
  __int64 v7; // rbx
  int v9; // edx
  CBucket *v10; // rax
  CBucket *v11; // rdi
  char *v12; // rax
  char *v13; // rbx

  v1 = *((_DWORD *)this + 16);
  if ( v1 == 2 )
    goto LABEL_2;
  v9 = v1 - 1;
  if ( !v9 )
  {
    v10 = (CBucket *)ALLOC_CACHE_HANDLER::Alloc(CSmallSegment::sm_palloc);
    v11 = v10;
    if ( v10 )
    {
      CBucket::CBucket(v10);
      CBucket::CBucket((CBucket *)((char *)v11 + 64));
      CBucket::CBucket((CBucket *)((char *)v11 + 128));
      CBucket::CBucket((CBucket *)((char *)v11 + 192));
      CBucket::CBucket((CBucket *)((char *)v11 + 256));
      CBucket::CBucket((CBucket *)((char *)v11 + 320));
      CBucket::CBucket((CBucket *)((char *)v11 + 384));
      CBucket::CBucket((CBucket *)((char *)v11 + 448));
      return v11;
    }
    return 0;
  }
  if ( v9 == 2 )
  {
    v12 = (char *)ALLOC_CACHE_HANDLER::Alloc(CLargeSegment::sm_palloc);
    v13 = v12;
    if ( v12 )
    {
      `vector constructor iterator'(v12, 0x40u, 1u, (void *(*)(void *))CBucket::CBucket);
      `vector constructor iterator'(v13 + 64, 0x40u, 0x1FFu, (void *(*)(void *))CBucket::CBucket);
      return (struct CSegment *)v13;
    }
    return 0;
  }
LABEL_2:
  v2 = CMediumSegment::sm_palloc;
  if ( *((int *)CMediumSegment::sm_palloc + 3) <= 0
    || (v3 = (_QWORD *)*((_QWORD *)CMediumSegment::sm_palloc + 3),
        CurrentThreadId = GetCurrentThreadId(),
        (v5 = (CBucket *)InterlockedPopEntrySList((PSLIST_HEADER)(*v3
                                                                + v3[1] * ((unsigned __int64)CurrentThreadId % v3[2])))) == 0) )
  {
    v5 = (CBucket *)HeapAlloc(ALLOC_CACHE_HANDLER::sm_hHeap, 0, *((unsigned int *)v2 + 4));
    if ( v5 )
    {
      _InterlockedIncrement((volatile signed __int32 *)v2 + 16);
    }
    else
    {
      v5 = (CBucket *)ALLOC_CACHE_HANDLER::PopAnyFreeListEntry(v2);
      if ( !v5 )
      {
        SetLastError(8u);
        return 0;
      }
    }
  }
  _InterlockedIncrement((volatile signed __int32 *)v2 + 32);
  CBucket::CBucket(v5);
  v6 = (CBucket *)((char *)v5 + 64);
  v7 = 63;
  do
  {
    CBucket::CBucket(v6);
    v6 = (CBucket *)((char *)v6 + 64);
    --v7;
  }
  while ( v7 );
  return v5;
}

```

## disassembly

```asm
0x18000b450  mov     [rsp+arg_8], rbx
0x18000b455  push    rdi
0x18000b456  sub     rsp, 20h
0x18000b45a  mov     edx, [rcx+40h]
0x18000b45d  cmp     edx, 2
0x18000b460  jnz     loc_18000B525
0x18000b466  mov     rdi, cs:?sm_palloc@CMediumSegment@@1PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CMediumSegment::sm_palloc
0x18000b46d  mov     [rsp+28h+arg_0], rsi
0x18000b472  cmp     dword ptr [rdi+0Ch], 0
0x18000b476  jle     short loc_18000B4E5
0x18000b478  mov     rbx, [rdi+18h]
0x18000b47c  call    cs:__imp_GetCurrentThreadId
0x18000b482  mov     eax, eax
0x18000b484  xor     edx, edx
0x18000b486  div     qword ptr [rbx+10h]
0x18000b48a  mov     ecx, edx
0x18000b48c  imul    rcx, [rbx+8]
0x18000b491  add     rcx, [rbx]; ListHead
0x18000b494  call    cs:__imp_InterlockedPopEntrySList
0x18000b49a  mov     rsi, rax
0x18000b49d  test    rax, rax
0x18000b4a0  jz      short loc_18000B4E5
0x18000b4a2  lock inc dword ptr [rdi+80h]
0x18000b4a9  mov     rcx, rsi; this
0x18000b4ac  call    ??0CBucket@@QEAA@XZ; CBucket::CBucket(void)
0x18000b4b1  lea     rdi, [rsi+40h]
0x18000b4b5  mov     ebx, 3Fh ; '?'
0x18000b4ba  nop     word ptr [rax+rax+00h]
0x18000b4c0  mov     rcx, rdi; this
0x18000b4c3  call    ??0CBucket@@QEAA@XZ; CBucket::CBucket(void)
0x18000b4c8  add     rdi, 40h ; '@'
0x18000b4cc  sub     rbx, 1
0x18000b4d0  jnz     short loc_18000B4C0
0x18000b4d2  mov     rax, rsi
0x18000b4d5  mov     rsi, [rsp+28h+arg_0]
0x18000b4da  mov     rbx, [rsp+28h+arg_8]
0x18000b4df  add     rsp, 20h
0x18000b4e3  pop     rdi
0x18000b4e4  retn
0x18000b4e5  mov     r8d, [rdi+10h]; dwBytes
0x18000b4e9  xor     edx, edx; dwFlags
0x18000b4eb  mov     rcx, cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA; hHeap
0x18000b4f2  call    cs:__imp_HeapAlloc
0x18000b4f8  mov     rsi, rax
0x18000b4fb  test    rax, rax
0x18000b4fe  jz      short loc_18000B506
0x18000b500  lock inc dword ptr [rdi+40h]
0x18000b504  jmp     short loc_18000B4A2
0x18000b506  mov     rcx, rdi; this
0x18000b509  call    ?PopAnyFreeListEntry@ALLOC_CACHE_HANDLER@@AEAAPEAXXZ; ALLOC_CACHE_HANDLER::PopAnyFreeListEntry(void)
0x18000b50e  mov     rsi, rax
0x18000b511  test    rax, rax
0x18000b514  jnz     short loc_18000B4A2
0x18000b516  mov     ecx, 8; dwErrCode
0x18000b51b  call    cs:__imp_SetLastError
0x18000b521  xor     eax, eax
0x18000b523  jmp     short loc_18000B4D5
0x18000b525  sub     edx, 1
0x18000b528  jnz     loc_18000B5B6
0x18000b52e  mov     rcx, cs:?sm_palloc@CSmallSegment@@1PEAVALLOC_CACHE_HANDLER@@EA; this
0x18000b535  call    ?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18000b53a  mov     rdi, rax
0x18000b53d  test    rax, rax
0x18000b540  jz      short loc_18000B5A9
0x18000b542  mov     rcx, rax; this
0x18000b545  call    ??0CBucket@@QEAA@XZ; CBucket::CBucket(void)
0x18000b54a  lea     rcx, [rdi+40h]; this
0x18000b54e  call    ??0CBucket@@QEAA@XZ; CBucket::CBucket(void)
0x18000b553  lea     rcx, [rdi+80h]; this
0x18000b55a  call    ??0CBucket@@QEAA@XZ; CBucket::CBucket(void)
0x18000b55f  lea     rcx, [rdi+0C0h]; this
0x18000b566  call    ??0CBucket@@QEAA@XZ; CBucket::CBucket(void)
0x18000b56b  lea     rcx, [rdi+100h]; this
0x18000b572  call    ??0CBucket@@QEAA@XZ; CBucket::CBucket(void)
0x18000b577  lea     rcx, [rdi+140h]; this
0x18000b57e  call    ??0CBucket@@QEAA@XZ; CBucket::CBucket(void)
0x18000b583  lea     rcx, [rdi+180h]; this
0x18000b58a  call    ??0CBucket@@QEAA@XZ; CBucket::CBucket(void)
0x18000b58f  lea     rcx, [rdi+1C0h]; this
0x18000b596  call    ??0CBucket@@QEAA@XZ; CBucket::CBucket(void)
0x18000b59b  mov     rax, rdi
0x18000b59e  mov     rbx, [rsp+28h+arg_8]
0x18000b5a3  add     rsp, 20h
0x18000b5a7  pop     rdi
0x18000b5a8  retn
0x18000b5a9  mov     rbx, [rsp+28h+arg_8]
0x18000b5ae  xor     eax, eax
0x18000b5b0  add     rsp, 20h
0x18000b5b4  pop     rdi
0x18000b5b5  retn
0x18000b5b6  cmp     edx, 2
0x18000b5b9  jnz     loc_18000B466
0x18000b5bf  mov     rcx, cs:?sm_palloc@CLargeSegment@@1PEAVALLOC_CACHE_HANDLER@@EA; this
0x18000b5c6  call    ?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18000b5cb  mov     rbx, rax
0x18000b5ce  test    rax, rax
0x18000b5d1  jz      short loc_18000B5A9
0x18000b5d3  lea     r9, ??0CBucket@@QEAA@XZ; void *(*)(void *)
0x18000b5da  mov     edx, 40h ; '@'; unsigned __int64
0x18000b5df  mov     r8d, 1; unsigned __int64
0x18000b5e5  mov     rcx, rax; void *
0x18000b5e8  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18000b5ed  lea     rcx, [rbx+40h]; void *
0x18000b5f1  mov     edx, 40h ; '@'; unsigned __int64
0x18000b5f6  lea     r9, ??0CBucket@@QEAA@XZ; void *(*)(void *)
0x18000b5fd  mov     r8d, 1FFh; unsigned __int64
0x18000b603  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18000b608  mov     rax, rbx
0x18000b60b  jmp     loc_18000B4DA
```
