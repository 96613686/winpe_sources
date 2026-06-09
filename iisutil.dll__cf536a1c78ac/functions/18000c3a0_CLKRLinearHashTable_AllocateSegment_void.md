# CLKRLinearHashTable::_AllocateSegment(void)

- ea: `0x18000c3a0`
- end: `0x18000c575`
- name: `?_AllocateSegment@CLKRLinearHashTable@@AEBAQEAVCSegment@@XZ`
- size: `469`
- prototype: `struct CSegment *__fastcall(CLKRLinearHashTable *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180008f60`
- `0x18000a420`

## callees

- `0x180008d30`
- `0x1800093dc`
- `0x18000c3a0`
- `0x18000c580`
- `0x18000c5b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c478`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c478`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c3cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c3cc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c449`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c449`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000c3ea`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000c3ea`

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
0x18000c3a0  mov     [rsp+arg_8], rbx
0x18000c3a5  push    rdi
0x18000c3a6  sub     rsp, 20h
0x18000c3aa  mov     edx, [rcx+40h]
0x18000c3ad  cmp     edx, 2
0x18000c3b0  jnz     loc_18000C488
0x18000c3b6  mov     rdi, cs:?sm_palloc@CMediumSegment@@1PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CMediumSegment::sm_palloc
0x18000c3bd  mov     [rsp+28h+arg_0], rsi
0x18000c3c2  cmp     dword ptr [rdi+0Ch], 0
0x18000c3c6  jle     short loc_18000C43C
0x18000c3c8  mov     rbx, [rdi+18h]
0x18000c3cc  call    cs:__imp_GetCurrentThreadId
0x18000c3d3  nop     dword ptr [rax+rax+00h]
0x18000c3d8  mov     eax, eax
0x18000c3da  xor     edx, edx
0x18000c3dc  div     qword ptr [rbx+10h]
0x18000c3e0  mov     ecx, edx
0x18000c3e2  imul    rcx, [rbx+8]
0x18000c3e7  add     rcx, [rbx]; ListHead
0x18000c3ea  call    cs:__imp_InterlockedPopEntrySList
0x18000c3f1  nop     dword ptr [rax+rax+00h]
0x18000c3f6  mov     rsi, rax
0x18000c3f9  test    rax, rax
0x18000c3fc  jz      short loc_18000C43C
0x18000c3fe  lock inc dword ptr [rdi+80h]
0x18000c405  mov     rcx, rsi; this
0x18000c408  call    ??0CBucket@@QEAA@XZ; CBucket::CBucket(void)
0x18000c40d  lea     rdi, [rsi+40h]
0x18000c411  mov     ebx, 3Fh ; '?'
0x18000c416  mov     rcx, rdi; this
0x18000c419  call    ??0CBucket@@QEAA@XZ; CBucket::CBucket(void)
0x18000c41e  add     rdi, 40h ; '@'
0x18000c422  sub     rbx, 1
0x18000c426  jnz     short loc_18000C416
0x18000c428  mov     rax, rsi
0x18000c42b  mov     rsi, [rsp+28h+arg_0]
0x18000c430  mov     rbx, [rsp+28h+arg_8]
0x18000c435  add     rsp, 20h
0x18000c439  pop     rdi
0x18000c43a  retn
0x18000c43c  mov     r8d, [rdi+10h]; dwBytes
0x18000c440  xor     edx, edx; dwFlags
0x18000c442  mov     rcx, cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA; hHeap
0x18000c449  call    cs:__imp_HeapAlloc
0x18000c450  nop     dword ptr [rax+rax+00h]
0x18000c455  mov     rsi, rax
0x18000c458  test    rax, rax
0x18000c45b  jz      short loc_18000C463
0x18000c45d  lock inc dword ptr [rdi+40h]
0x18000c461  jmp     short loc_18000C3FE
0x18000c463  mov     rcx, rdi; this
0x18000c466  call    ?PopAnyFreeListEntry@ALLOC_CACHE_HANDLER@@AEAAPEAXXZ; ALLOC_CACHE_HANDLER::PopAnyFreeListEntry(void)
0x18000c46b  mov     rsi, rax
0x18000c46e  test    rax, rax
0x18000c471  jnz     short loc_18000C3FE
0x18000c473  mov     ecx, 8; dwErrCode
0x18000c478  call    cs:__imp_SetLastError
0x18000c47f  nop     dword ptr [rax+rax+00h]
0x18000c484  xor     eax, eax
0x18000c486  jmp     short loc_18000C42B
0x18000c488  sub     edx, 1
0x18000c48b  jnz     loc_18000C51B
0x18000c491  mov     rcx, cs:?sm_palloc@CSmallSegment@@1PEAVALLOC_CACHE_HANDLER@@EA; this
0x18000c498  call    ?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18000c49d  mov     rdi, rax
0x18000c4a0  test    rax, rax
0x18000c4a3  jz      short loc_18000C50D
0x18000c4a5  mov     rcx, rax; this
0x18000c4a8  call    ??0CBucket@@QEAA@XZ; CBucket::CBucket(void)
0x18000c4ad  lea     rcx, [rdi+40h]; this
0x18000c4b1  call    ??0CBucket@@QEAA@XZ; CBucket::CBucket(void)
0x18000c4b6  lea     rcx, [rdi+80h]; this
0x18000c4bd  call    ??0CBucket@@QEAA@XZ; CBucket::CBucket(void)
0x18000c4c2  lea     rcx, [rdi+0C0h]; this
0x18000c4c9  call    ??0CBucket@@QEAA@XZ; CBucket::CBucket(void)
0x18000c4ce  lea     rcx, [rdi+100h]; this
0x18000c4d5  call    ??0CBucket@@QEAA@XZ; CBucket::CBucket(void)
0x18000c4da  lea     rcx, [rdi+140h]; this
0x18000c4e1  call    ??0CBucket@@QEAA@XZ; CBucket::CBucket(void)
0x18000c4e6  lea     rcx, [rdi+180h]; this
0x18000c4ed  call    ??0CBucket@@QEAA@XZ; CBucket::CBucket(void)
0x18000c4f2  lea     rcx, [rdi+1C0h]; this
0x18000c4f9  call    ??0CBucket@@QEAA@XZ; CBucket::CBucket(void)
0x18000c4fe  mov     rax, rdi
0x18000c501  mov     rbx, [rsp+28h+arg_8]
0x18000c506  add     rsp, 20h
0x18000c50a  pop     rdi
0x18000c50b  retn
0x18000c50d  mov     rbx, [rsp+28h+arg_8]
0x18000c512  xor     eax, eax
0x18000c514  add     rsp, 20h
0x18000c518  pop     rdi
0x18000c519  retn
0x18000c51b  cmp     edx, 2
0x18000c51e  jnz     loc_18000C3B6
0x18000c524  mov     rcx, cs:?sm_palloc@CLargeSegment@@1PEAVALLOC_CACHE_HANDLER@@EA; this
0x18000c52b  call    ?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18000c530  mov     rbx, rax
0x18000c533  test    rax, rax
0x18000c536  jz      short loc_18000C50D
0x18000c538  lea     r9, ??0CBucket@@QEAA@XZ; void *(*)(void *)
0x18000c53f  mov     edx, 40h ; '@'; unsigned __int64
0x18000c544  mov     r8d, 1; unsigned __int64
0x18000c54a  mov     rcx, rax; void *
0x18000c54d  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18000c552  lea     rcx, [rbx+40h]; void *
0x18000c556  mov     edx, 40h ; '@'; unsigned __int64
0x18000c55b  lea     r9, ??0CBucket@@QEAA@XZ; void *(*)(void *)
0x18000c562  mov     r8d, 1FFh; unsigned __int64
0x18000c568  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18000c56d  mov     rax, rbx
0x18000c570  jmp     loc_18000C430
```
