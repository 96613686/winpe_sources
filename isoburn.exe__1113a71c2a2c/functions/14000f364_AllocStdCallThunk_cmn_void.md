# __AllocStdCallThunk_cmn(void)

- ea: `0x14000f364`
- end: `0x14000f41e`
- name: `?__AllocStdCallThunk_cmn@@YAPEAXXZ`
- size: `186`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f4a0`

## callees

- `0x14000f364`
- `0x14000f424`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x14000f3b1`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x14000f3b1`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x14000f3e5`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x14000f3e5`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x14000f401`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x14000f401`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x14000f38a`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x14000f3cc`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x14000f38a`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x14000f3cc`

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
0x14000f364  mov     [rsp+arg_0], rbx
0x14000f369  push    rdi
0x14000f36a  sub     rsp, 20h
0x14000f36e  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; _SLIST_HEADER * __AtlThunkPool
0x14000f375  test    rcx, rcx
0x14000f378  jnz     short loc_14000F38A
0x14000f37a  call    __InitializeThunkPool
0x14000f37f  test    eax, eax
0x14000f381  jz      short loc_14000F3BF
0x14000f383  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x14000f38a  call    cs:__imp_InterlockedPopEntrySList
0x14000f390  xor     ecx, ecx; lpAddress
0x14000f392  test    rax, rax
0x14000f395  jz      short loc_14000F3A3
0x14000f397  xorps   xmm0, xmm0
0x14000f39a  movups  xmmword ptr [rax], xmm0
0x14000f39d  mov     [rax+0Eh], rcx
0x14000f3a1  jmp     short loc_14000F413
0x14000f3a3  mov     edx, 1000h; dwSize
0x14000f3a8  mov     r9d, 40h ; '@'; flProtect
0x14000f3ae  mov     r8d, edx; flAllocationType
0x14000f3b1  call    cs:__imp_VirtualAlloc
0x14000f3b7  mov     rbx, rax
0x14000f3ba  test    rax, rax
0x14000f3bd  jnz     short loc_14000F3C3
0x14000f3bf  xor     eax, eax
0x14000f3c1  jmp     short loc_14000F413
0x14000f3c3  mov     eax, [rax]
0x14000f3c5  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x14000f3cc  call    cs:__imp_InterlockedPopEntrySList
0x14000f3d2  mov     rdi, rax
0x14000f3d5  test    rax, rax
0x14000f3d8  jz      short loc_14000F3F0
0x14000f3da  xor     edx, edx; dwSize
0x14000f3dc  mov     r8d, 8000h; dwFreeType
0x14000f3e2  mov     rcx, rbx; lpAddress
0x14000f3e5  call    cs:__imp_VirtualFree
0x14000f3eb  mov     rax, rdi
0x14000f3ee  jmp     short loc_14000F413
0x14000f3f0  lea     rdi, [rbx+0FE0h]
0x14000f3f7  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x14000f3fe  mov     rdx, rbx; ListEntry
0x14000f401  call    cs:__imp_InterlockedPushEntrySList
0x14000f407  add     rbx, 20h ; ' '
0x14000f40b  cmp     rbx, rdi
0x14000f40e  jb      short loc_14000F3F7
0x14000f410  mov     rax, rbx
0x14000f413  mov     rbx, [rsp+28h+arg_0]
0x14000f418  add     rsp, 20h
0x14000f41c  pop     rdi
0x14000f41d  retn
```
