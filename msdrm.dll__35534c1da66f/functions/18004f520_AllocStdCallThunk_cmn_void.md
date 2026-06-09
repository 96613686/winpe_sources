# __AllocStdCallThunk_cmn(void)

- ea: `0x18004f520`
- end: `0x18004f5da`
- name: `?__AllocStdCallThunk_cmn@@YAPEAXXZ`
- size: `186`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18004f65c`

## callees

- `0x18004f520`
- `0x18004f5e0`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18004f56d`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18004f56d`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18004f5a1`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18004f5a1`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18004f5bd`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18004f5bd`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18004f546`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18004f588`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18004f546`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18004f588`

## pseudocode

```c
PSLIST_ENTRY __AllocStdCallThunk_cmn(void)
{
  union _SLIST_HEADER *v0; // rcx
  PSLIST_ENTRY result; // rax
  struct _SLIST_ENTRY *v2; // rbx
  PSLIST_ENTRY v3; // rdi
  struct _SLIST_ENTRY *v4; // rdi

  v0 = __AtlThunkPool;
  if ( !__AtlThunkPool )
  {
    if ( !(unsigned int)_InitializeThunkPool() )
      return 0;
    v0 = __AtlThunkPool;
  }
  result = InterlockedPopEntrySList(v0);
  if ( result )
  {
    *result = 0;
    *(struct _SLIST_ENTRY **)((char *)&result->Next + 14) = 0;
    return result;
  }
  v2 = (struct _SLIST_ENTRY *)VirtualAlloc(0, 0x1000u, 0x1000u, 0x40u);
  if ( !v2 )
    return 0;
  v3 = InterlockedPopEntrySList(__AtlThunkPool);
  if ( v3 )
  {
    VirtualFree(v2, 0, 0x8000u);
    return v3;
  }
  else
  {
    v4 = v2 + 254;
    do
    {
      InterlockedPushEntrySList(__AtlThunkPool, v2);
      v2 += 2;
    }
    while ( v2 < v4 );
    return v2;
  }
}

```

## disassembly

```asm
0x18004f520  mov     [rsp+arg_0], rbx
0x18004f525  push    rdi
0x18004f526  sub     rsp, 20h
0x18004f52a  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; _SLIST_HEADER * __AtlThunkPool
0x18004f531  test    rcx, rcx
0x18004f534  jnz     short loc_18004F546
0x18004f536  call    __InitializeThunkPool
0x18004f53b  test    eax, eax
0x18004f53d  jz      short loc_18004F57B
0x18004f53f  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x18004f546  call    cs:__imp_InterlockedPopEntrySList
0x18004f54c  xor     ecx, ecx; lpAddress
0x18004f54e  test    rax, rax
0x18004f551  jz      short loc_18004F55F
0x18004f553  xorps   xmm0, xmm0
0x18004f556  movups  xmmword ptr [rax], xmm0
0x18004f559  mov     [rax+0Eh], rcx
0x18004f55d  jmp     short loc_18004F5CF
0x18004f55f  mov     edx, 1000h; dwSize
0x18004f564  mov     r9d, 40h ; '@'; flProtect
0x18004f56a  mov     r8d, edx; flAllocationType
0x18004f56d  call    cs:__imp_VirtualAlloc
0x18004f573  mov     rbx, rax
0x18004f576  test    rax, rax
0x18004f579  jnz     short loc_18004F57F
0x18004f57b  xor     eax, eax
0x18004f57d  jmp     short loc_18004F5CF
0x18004f57f  mov     eax, [rax]
0x18004f581  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x18004f588  call    cs:__imp_InterlockedPopEntrySList
0x18004f58e  mov     rdi, rax
0x18004f591  test    rax, rax
0x18004f594  jz      short loc_18004F5AC
0x18004f596  xor     edx, edx; dwSize
0x18004f598  mov     r8d, 8000h; dwFreeType
0x18004f59e  mov     rcx, rbx; lpAddress
0x18004f5a1  call    cs:__imp_VirtualFree
0x18004f5a7  mov     rax, rdi
0x18004f5aa  jmp     short loc_18004F5CF
0x18004f5ac  lea     rdi, [rbx+0FE0h]
0x18004f5b3  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x18004f5ba  mov     rdx, rbx; ListEntry
0x18004f5bd  call    cs:__imp_InterlockedPushEntrySList
0x18004f5c3  add     rbx, 20h ; ' '
0x18004f5c7  cmp     rbx, rdi
0x18004f5ca  jb      short loc_18004F5B3
0x18004f5cc  mov     rax, rbx
0x18004f5cf  mov     rbx, [rsp+28h+arg_0]
0x18004f5d4  add     rsp, 20h
0x18004f5d8  pop     rdi
0x18004f5d9  retn
```
