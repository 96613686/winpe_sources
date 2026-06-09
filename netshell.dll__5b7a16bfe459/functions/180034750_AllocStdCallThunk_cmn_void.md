# __AllocStdCallThunk_cmn(void)

- ea: `0x180034750`
- end: `0x18003480a`
- name: `?__AllocStdCallThunk_cmn@@YAPEAXXZ`
- size: `186`
- prototype: `PSLIST_ENTRY(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800348b0`

## callees

- `0x180034750`
- `0x180034834`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800347d1`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800347d1`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18003479d`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18003479d`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180034776`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x1800347b8`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180034776`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x1800347b8`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x1800347ed`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x1800347ed`

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
0x180034750  mov     [rsp+arg_0], rbx
0x180034755  push    rdi
0x180034756  sub     rsp, 20h
0x18003475a  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; _SLIST_HEADER * __AtlThunkPool
0x180034761  test    rcx, rcx
0x180034764  jnz     short loc_180034776
0x180034766  call    __InitializeThunkPool
0x18003476b  test    eax, eax
0x18003476d  jz      short loc_1800347AB
0x18003476f  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x180034776  call    cs:__imp_InterlockedPopEntrySList
0x18003477c  xor     ecx, ecx; lpAddress
0x18003477e  test    rax, rax
0x180034781  jz      short loc_18003478F
0x180034783  xorps   xmm0, xmm0
0x180034786  movups  xmmword ptr [rax], xmm0
0x180034789  mov     [rax+0Eh], rcx
0x18003478d  jmp     short loc_1800347FF
0x18003478f  mov     edx, 1000h; dwSize
0x180034794  mov     r9d, 40h ; '@'; flProtect
0x18003479a  mov     r8d, edx; flAllocationType
0x18003479d  call    cs:__imp_VirtualAlloc
0x1800347a3  mov     rbx, rax
0x1800347a6  test    rax, rax
0x1800347a9  jnz     short loc_1800347AF
0x1800347ab  xor     eax, eax
0x1800347ad  jmp     short loc_1800347FF
0x1800347af  mov     eax, [rax]
0x1800347b1  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x1800347b8  call    cs:__imp_InterlockedPopEntrySList
0x1800347be  mov     rdi, rax
0x1800347c1  test    rax, rax
0x1800347c4  jz      short loc_1800347DC
0x1800347c6  xor     edx, edx; dwSize
0x1800347c8  mov     r8d, 8000h; dwFreeType
0x1800347ce  mov     rcx, rbx; lpAddress
0x1800347d1  call    cs:__imp_VirtualFree
0x1800347d7  mov     rax, rdi
0x1800347da  jmp     short loc_1800347FF
0x1800347dc  lea     rdi, [rbx+0FE0h]
0x1800347e3  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x1800347ea  mov     rdx, rbx; ListEntry
0x1800347ed  call    cs:__imp_InterlockedPushEntrySList
0x1800347f3  add     rbx, 20h ; ' '
0x1800347f7  cmp     rbx, rdi
0x1800347fa  jb      short loc_1800347E3
0x1800347fc  mov     rax, rbx
0x1800347ff  mov     rbx, [rsp+28h+arg_0]
0x180034804  add     rsp, 20h
0x180034808  pop     rdi
0x180034809  retn
```
