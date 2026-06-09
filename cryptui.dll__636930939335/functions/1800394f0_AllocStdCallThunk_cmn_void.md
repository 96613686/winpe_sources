# __AllocStdCallThunk_cmn(void)

- ea: `0x1800394f0`
- end: `0x1800395aa`
- name: `?__AllocStdCallThunk_cmn@@YAPEAXXZ`
- size: `186`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180039650`

## callees

- `0x1800394f0`
- `0x1800395d4`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18003953d`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18003953d`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180039571`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180039571`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18003958d`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18003958d`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180039516`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180039558`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180039516`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180039558`

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
0x1800394f0  mov     [rsp+arg_0], rbx
0x1800394f5  push    rdi
0x1800394f6  sub     rsp, 20h
0x1800394fa  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; _SLIST_HEADER * __AtlThunkPool
0x180039501  test    rcx, rcx
0x180039504  jnz     short loc_180039516
0x180039506  call    __InitializeThunkPool
0x18003950b  test    eax, eax
0x18003950d  jz      short loc_18003954B
0x18003950f  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x180039516  call    cs:__imp_InterlockedPopEntrySList
0x18003951c  xor     ecx, ecx; lpAddress
0x18003951e  test    rax, rax
0x180039521  jz      short loc_18003952F
0x180039523  xorps   xmm0, xmm0
0x180039526  movups  xmmword ptr [rax], xmm0
0x180039529  mov     [rax+0Eh], rcx
0x18003952d  jmp     short loc_18003959F
0x18003952f  mov     edx, 1000h; dwSize
0x180039534  mov     r9d, 40h ; '@'; flProtect
0x18003953a  mov     r8d, edx; flAllocationType
0x18003953d  call    cs:__imp_VirtualAlloc
0x180039543  mov     rbx, rax
0x180039546  test    rax, rax
0x180039549  jnz     short loc_18003954F
0x18003954b  xor     eax, eax
0x18003954d  jmp     short loc_18003959F
0x18003954f  mov     eax, [rax]
0x180039551  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x180039558  call    cs:__imp_InterlockedPopEntrySList
0x18003955e  mov     rdi, rax
0x180039561  test    rax, rax
0x180039564  jz      short loc_18003957C
0x180039566  xor     edx, edx; dwSize
0x180039568  mov     r8d, 8000h; dwFreeType
0x18003956e  mov     rcx, rbx; lpAddress
0x180039571  call    cs:__imp_VirtualFree
0x180039577  mov     rax, rdi
0x18003957a  jmp     short loc_18003959F
0x18003957c  lea     rdi, [rbx+0FE0h]
0x180039583  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x18003958a  mov     rdx, rbx; ListEntry
0x18003958d  call    cs:__imp_InterlockedPushEntrySList
0x180039593  add     rbx, 20h ; ' '
0x180039597  cmp     rbx, rdi
0x18003959a  jb      short loc_180039583
0x18003959c  mov     rax, rbx
0x18003959f  mov     rbx, [rsp+28h+arg_0]
0x1800395a4  add     rsp, 20h
0x1800395a8  pop     rdi
0x1800395a9  retn
```
