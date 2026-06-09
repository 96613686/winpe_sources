# ALLOC_CACHE_HANDLER::Alloc(void)

- ea: `0x180008d30`
- end: `0x180008dd7`
- name: `?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ`
- size: `167`
- prototype: `void *__fastcall(ALLOC_CACHE_HANDLER *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800080f0`
- `0x180008470`
- `0x18000ade0`
- `0x18000c3a0`
- `0x18000e280`
- `0x1800106e0`
- `0x1800128d0`
- `0x180013580`
- `0x18002d140`

## callees

- `0x180008d30`
- `0x18000c5b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008dc9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008dc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008d47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008d47`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008d9c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008d9c`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180008d65`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180008d65`

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
0x180008d30  mov     [rsp+arg_0], rbx
0x180008d35  push    rdi
0x180008d36  sub     rsp, 20h
0x180008d3a  cmp     dword ptr [rcx+0Ch], 0
0x180008d3e  mov     rdi, rcx
0x180008d41  jle     short loc_180008D8F
0x180008d43  mov     rbx, [rcx+18h]
0x180008d47  call    cs:__imp_GetCurrentThreadId
0x180008d4e  nop     dword ptr [rax+rax+00h]
0x180008d53  mov     eax, eax
0x180008d55  xor     edx, edx
0x180008d57  div     qword ptr [rbx+10h]
0x180008d5b  mov     ecx, edx
0x180008d5d  imul    rcx, [rbx+8]
0x180008d62  add     rcx, [rbx]; ListHead
0x180008d65  call    cs:__imp_InterlockedPopEntrySList
0x180008d6c  nop     dword ptr [rax+rax+00h]
0x180008d71  mov     rbx, rax
0x180008d74  test    rax, rax
0x180008d77  jz      short loc_180008D8F
0x180008d79  lock inc dword ptr [rdi+80h]
0x180008d80  mov     rax, rbx
0x180008d83  mov     rbx, [rsp+28h+arg_0]
0x180008d88  add     rsp, 20h
0x180008d8c  pop     rdi
0x180008d8d  retn
0x180008d8f  mov     r8d, [rdi+10h]; dwBytes
0x180008d93  xor     edx, edx; dwFlags
0x180008d95  mov     rcx, cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA; hHeap
0x180008d9c  call    cs:__imp_HeapAlloc
0x180008da3  nop     dword ptr [rax+rax+00h]
0x180008da8  mov     rbx, rax
0x180008dab  test    rax, rax
0x180008dae  jz      short loc_180008DB6
0x180008db0  lock inc dword ptr [rdi+40h]
0x180008db4  jmp     short loc_180008D79
0x180008db6  mov     rcx, rdi; this
0x180008db9  call    ?PopAnyFreeListEntry@ALLOC_CACHE_HANDLER@@AEAAPEAXXZ; ALLOC_CACHE_HANDLER::PopAnyFreeListEntry(void)
0x180008dbe  mov     rbx, rax
0x180008dc1  test    rax, rax
0x180008dc4  jnz     short loc_180008D79
0x180008dc6  lea     ecx, [rax+8]; dwErrCode
0x180008dc9  call    cs:__imp_SetLastError
0x180008dd0  nop     dword ptr [rax+rax+00h]
0x180008dd5  jmp     short loc_180008D80
```
