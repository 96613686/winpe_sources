# __AllocStdCallThunk_cmn(void)

- ea: `0x18002d4d4`
- end: `0x18002d58e`
- name: `?__AllocStdCallThunk_cmn@@YAPEAXXZ`
- size: `186`
- prototype: `PSLIST_ENTRY(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002d634`

## callees

- `0x18002d4d4`
- `0x18002d5b8`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18002d555`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18002d555`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18002d521`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18002d521`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18002d4fa`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18002d53c`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18002d4fa`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18002d53c`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18002d571`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18002d571`

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
0x18002d4d4  mov     [rsp+arg_0], rbx
0x18002d4d9  push    rdi
0x18002d4da  sub     rsp, 20h
0x18002d4de  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; _SLIST_HEADER * __AtlThunkPool
0x18002d4e5  test    rcx, rcx
0x18002d4e8  jnz     short loc_18002D4FA
0x18002d4ea  call    __InitializeThunkPool
0x18002d4ef  test    eax, eax
0x18002d4f1  jz      short loc_18002D52F
0x18002d4f3  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x18002d4fa  call    cs:__imp_InterlockedPopEntrySList
0x18002d500  xor     ecx, ecx; lpAddress
0x18002d502  test    rax, rax
0x18002d505  jz      short loc_18002D513
0x18002d507  xorps   xmm0, xmm0
0x18002d50a  movups  xmmword ptr [rax], xmm0
0x18002d50d  mov     [rax+0Eh], rcx
0x18002d511  jmp     short loc_18002D583
0x18002d513  mov     edx, 1000h; dwSize
0x18002d518  mov     r9d, 40h ; '@'; flProtect
0x18002d51e  mov     r8d, edx; flAllocationType
0x18002d521  call    cs:__imp_VirtualAlloc
0x18002d527  mov     rbx, rax
0x18002d52a  test    rax, rax
0x18002d52d  jnz     short loc_18002D533
0x18002d52f  xor     eax, eax
0x18002d531  jmp     short loc_18002D583
0x18002d533  mov     eax, [rax]
0x18002d535  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x18002d53c  call    cs:__imp_InterlockedPopEntrySList
0x18002d542  mov     rdi, rax
0x18002d545  test    rax, rax
0x18002d548  jz      short loc_18002D560
0x18002d54a  xor     edx, edx; dwSize
0x18002d54c  mov     r8d, 8000h; dwFreeType
0x18002d552  mov     rcx, rbx; lpAddress
0x18002d555  call    cs:__imp_VirtualFree
0x18002d55b  mov     rax, rdi
0x18002d55e  jmp     short loc_18002D583
0x18002d560  lea     rdi, [rbx+0FE0h]
0x18002d567  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x18002d56e  mov     rdx, rbx; ListEntry
0x18002d571  call    cs:__imp_InterlockedPushEntrySList
0x18002d577  add     rbx, 20h ; ' '
0x18002d57b  cmp     rbx, rdi
0x18002d57e  jb      short loc_18002D567
0x18002d580  mov     rax, rbx
0x18002d583  mov     rbx, [rsp+28h+arg_0]
0x18002d588  add     rsp, 20h
0x18002d58c  pop     rdi
0x18002d58d  retn
```
