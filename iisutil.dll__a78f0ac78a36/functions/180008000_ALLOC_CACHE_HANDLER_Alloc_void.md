# ALLOC_CACHE_HANDLER::Alloc(void)

- ea: `0x180008000`
- end: `0x18000808e`
- name: `?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ`
- size: `142`
- prototype: `void *__fastcall(ALLOC_CACHE_HANDLER *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800073e0`
- `0x180007750`
- `0x180009ee0`
- `0x18000b450`
- `0x18000d1a0`
- `0x18000f3a0`
- `0x180011fa0`
- `0x180012c20`
- `0x18002b1e0`

## callees

- `0x180008000`
- `0x18000b650`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008086`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008086`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008017`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008017`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000805f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000805f`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000802f`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000802f`

## pseudocode

```c
void *__fastcall ALLOC_CACHE_HANDLER::Alloc(ALLOC_CACHE_HANDLER *this)
{
  _QWORD *v2; // rbx
  DWORD CurrentThreadId; // eax
  void *v4; // rbx

  if ( *((int *)this + 3) <= 0
    || (v2 = (_QWORD *)*((_QWORD *)this + 3),
        CurrentThreadId = GetCurrentThreadId(),
        (v4 = InterlockedPopEntrySList((PSLIST_HEADER)(*v2 + v2[1] * ((unsigned __int64)CurrentThreadId % v2[2])))) == 0) )
  {
    v4 = HeapAlloc(ALLOC_CACHE_HANDLER::sm_hHeap, 0, *((unsigned int *)this + 4));
    if ( v4 )
    {
      _InterlockedIncrement((volatile signed __int32 *)this + 16);
    }
    else
    {
      v4 = ALLOC_CACHE_HANDLER::PopAnyFreeListEntry(this);
      if ( !v4 )
      {
        SetLastError(8u);
        return v4;
      }
    }
  }
  _InterlockedIncrement((volatile signed __int32 *)this + 32);
  return v4;
}

```

## disassembly

```asm
0x180008000  mov     [rsp+arg_0], rbx
0x180008005  push    rdi
0x180008006  sub     rsp, 20h
0x18000800a  cmp     dword ptr [rcx+0Ch], 0
0x18000800e  mov     rdi, rcx
0x180008011  jle     short loc_180008052
0x180008013  mov     rbx, [rcx+18h]
0x180008017  call    cs:__imp_GetCurrentThreadId
0x18000801d  mov     eax, eax
0x18000801f  xor     edx, edx
0x180008021  div     qword ptr [rbx+10h]
0x180008025  mov     ecx, edx
0x180008027  imul    rcx, [rbx+8]
0x18000802c  add     rcx, [rbx]; ListHead
0x18000802f  call    cs:__imp_InterlockedPopEntrySList
0x180008035  mov     rbx, rax
0x180008038  test    rax, rax
0x18000803b  jz      short loc_180008052
0x18000803d  lock inc dword ptr [rdi+80h]
0x180008044  mov     rax, rbx
0x180008047  mov     rbx, [rsp+28h+arg_0]
0x18000804c  add     rsp, 20h
0x180008050  pop     rdi
0x180008051  retn
0x180008052  mov     r8d, [rdi+10h]; dwBytes
0x180008056  xor     edx, edx; dwFlags
0x180008058  mov     rcx, cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA; hHeap
0x18000805f  call    cs:__imp_HeapAlloc
0x180008065  mov     rbx, rax
0x180008068  test    rax, rax
0x18000806b  jz      short loc_180008073
0x18000806d  lock inc dword ptr [rdi+40h]
0x180008071  jmp     short loc_18000803D
0x180008073  mov     rcx, rdi; this
0x180008076  call    ?PopAnyFreeListEntry@ALLOC_CACHE_HANDLER@@AEAAPEAXXZ; ALLOC_CACHE_HANDLER::PopAnyFreeListEntry(void)
0x18000807b  mov     rbx, rax
0x18000807e  test    rax, rax
0x180008081  jnz     short loc_18000803D
0x180008083  lea     ecx, [rax+8]; dwErrCode
0x180008086  call    cs:__imp_SetLastError
0x18000808c  jmp     short loc_180008044
```
