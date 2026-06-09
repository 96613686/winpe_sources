# _free_base

- ea: `0x180015c20`
- end: `0x180015c5c`
- name: `_free_base`
- size: `60`
- prototype: `void __cdecl(void *Block)`
- caller_count: `21`
- callee_count: `3`
- tags: ``

## callers

- `0x1800152bc`
- `0x180015d18`
- `0x180015eb8`
- `0x180016490`
- `0x180016a3c`
- `0x180016cb4`
- `0x1800170b0`
- `0x1800171c0`
- `0x180017234`
- `0x18001726c`
- `0x1800173e4`
- `0x1800177b4`
- `0x180017bf8`
- `0x180018910`
- `0x18001950c`
- `0x18001b0d0`
- `0x18001b740`
- `0x18001b850`
- `0x18001b910`
- `0x18001bd3c`
- `0x18001bff8`

## callees

- `0x180014fac`
- `0x1800150d0`
- `0x180015c20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015c36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015c36`

## pseudocode

```c
void __cdecl free_base(void *Block)
{
  DWORD LastError; // eax
  int v2; // ebx

  if ( Block )
  {
    if ( !HeapFree(_acrt_heap, 0, Block) )
    {
      LastError = GetLastError();
      v2 = _acrt_errno_from_os_error(LastError);
      *errno() = v2;
    }
  }
}

```

## disassembly

```asm
0x180015c20  test    rcx, rcx
0x180015c23  jz      short locret_180015C5B
0x180015c25  push    rbx
0x180015c26  sub     rsp, 20h
0x180015c2a  mov     r8, rcx; lpMem
0x180015c2d  xor     edx, edx; dwFlags
0x180015c2f  mov     rcx, cs:__acrt_heap; hHeap
0x180015c36  call    cs:__imp_HeapFree
0x180015c3c  test    eax, eax
0x180015c3e  jnz     short loc_180015C56
0x180015c40  call    cs:__imp_GetLastError
0x180015c46  mov     ecx, eax
0x180015c48  call    __acrt_errno_from_os_error
0x180015c4d  mov     ebx, eax
0x180015c4f  call    _errno
0x180015c54  mov     [rax], ebx
0x180015c56  add     rsp, 20h
0x180015c5a  pop     rbx
0x180015c5b  retn
```
