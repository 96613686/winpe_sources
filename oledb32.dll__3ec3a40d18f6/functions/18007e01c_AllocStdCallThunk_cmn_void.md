# __AllocStdCallThunk_cmn(void)

- ea: `0x18007e01c`
- end: `0x18007e0d6`
- name: `?__AllocStdCallThunk_cmn@@YAPEAXXZ`
- size: `186`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18007e17c`

## callees

- `0x18007e01c`
- `0x18007e100`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x18007e0b9`
- `KERNEL32!InterlockedPushEntrySList` at `0x18007e0b9`
- `KERNEL32!VirtualFree` at `0x18007e09d`
- `KERNEL32!VirtualFree` at `0x18007e09d`
- `KERNEL32!InterlockedPopEntrySList` at `0x18007e042`
- `KERNEL32!InterlockedPopEntrySList` at `0x18007e084`
- `KERNEL32!InterlockedPopEntrySList` at `0x18007e042`
- `KERNEL32!InterlockedPopEntrySList` at `0x18007e084`
- `KERNEL32!VirtualAlloc` at `0x18007e069`
- `KERNEL32!VirtualAlloc` at `0x18007e069`

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
0x18007e01c  mov     [rsp+arg_0], rbx
0x18007e021  push    rdi
0x18007e022  sub     rsp, 20h
0x18007e026  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; _SLIST_HEADER * __AtlThunkPool
0x18007e02d  test    rcx, rcx
0x18007e030  jnz     short loc_18007E042
0x18007e032  call    __InitializeThunkPool
0x18007e037  test    eax, eax
0x18007e039  jz      short loc_18007E077
0x18007e03b  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x18007e042  call    cs:__imp_InterlockedPopEntrySList
0x18007e048  xor     ecx, ecx; lpAddress
0x18007e04a  test    rax, rax
0x18007e04d  jz      short loc_18007E05B
0x18007e04f  xorps   xmm0, xmm0
0x18007e052  movups  xmmword ptr [rax], xmm0
0x18007e055  mov     [rax+0Eh], rcx
0x18007e059  jmp     short loc_18007E0CB
0x18007e05b  mov     edx, 1000h; dwSize
0x18007e060  mov     r9d, 40h ; '@'; flProtect
0x18007e066  mov     r8d, edx; flAllocationType
0x18007e069  call    cs:__imp_VirtualAlloc
0x18007e06f  mov     rbx, rax
0x18007e072  test    rax, rax
0x18007e075  jnz     short loc_18007E07B
0x18007e077  xor     eax, eax
0x18007e079  jmp     short loc_18007E0CB
0x18007e07b  mov     eax, [rax]
0x18007e07d  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x18007e084  call    cs:__imp_InterlockedPopEntrySList
0x18007e08a  mov     rdi, rax
0x18007e08d  test    rax, rax
0x18007e090  jz      short loc_18007E0A8
0x18007e092  xor     edx, edx; dwSize
0x18007e094  mov     r8d, 8000h; dwFreeType
0x18007e09a  mov     rcx, rbx; lpAddress
0x18007e09d  call    cs:__imp_VirtualFree
0x18007e0a3  mov     rax, rdi
0x18007e0a6  jmp     short loc_18007E0CB
0x18007e0a8  lea     rdi, [rbx+0FE0h]
0x18007e0af  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x18007e0b6  mov     rdx, rbx; ListEntry
0x18007e0b9  call    cs:__imp_InterlockedPushEntrySList
0x18007e0bf  add     rbx, 20h ; ' '
0x18007e0c3  cmp     rbx, rdi
0x18007e0c6  jb      short loc_18007E0AF
0x18007e0c8  mov     rax, rbx
0x18007e0cb  mov     rbx, [rsp+28h+arg_0]
0x18007e0d0  add     rsp, 20h
0x18007e0d4  pop     rdi
0x18007e0d5  retn
```
