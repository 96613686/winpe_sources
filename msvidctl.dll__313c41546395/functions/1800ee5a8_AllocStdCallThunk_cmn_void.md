# __AllocStdCallThunk_cmn(void)

- ea: `0x1800ee5a8`
- end: `0x1800ee662`
- name: `?__AllocStdCallThunk_cmn@@YAPEAXXZ`
- size: `186`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800ee708`

## callees

- `0x1800ee5a8`
- `0x1800ee68c`

## import_xrefs

- `KERNEL32!VirtualFree` at `0x1800ee629`
- `KERNEL32!VirtualFree` at `0x1800ee629`
- `KERNEL32!VirtualAlloc` at `0x1800ee5f5`
- `KERNEL32!VirtualAlloc` at `0x1800ee5f5`
- `KERNEL32!InterlockedPushEntrySList` at `0x1800ee645`
- `KERNEL32!InterlockedPushEntrySList` at `0x1800ee645`
- `KERNEL32!InterlockedPopEntrySList` at `0x1800ee5ce`
- `KERNEL32!InterlockedPopEntrySList` at `0x1800ee610`
- `KERNEL32!InterlockedPopEntrySList` at `0x1800ee5ce`
- `KERNEL32!InterlockedPopEntrySList` at `0x1800ee610`

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
0x1800ee5a8  mov     [rsp+arg_0], rbx
0x1800ee5ad  push    rdi
0x1800ee5ae  sub     rsp, 20h
0x1800ee5b2  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; _SLIST_HEADER * __AtlThunkPool
0x1800ee5b9  test    rcx, rcx
0x1800ee5bc  jnz     short loc_1800EE5CE
0x1800ee5be  call    __InitializeThunkPool
0x1800ee5c3  test    eax, eax
0x1800ee5c5  jz      short loc_1800EE603
0x1800ee5c7  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x1800ee5ce  call    cs:__imp_InterlockedPopEntrySList
0x1800ee5d4  xor     ecx, ecx; lpAddress
0x1800ee5d6  test    rax, rax
0x1800ee5d9  jz      short loc_1800EE5E7
0x1800ee5db  xorps   xmm0, xmm0
0x1800ee5de  movups  xmmword ptr [rax], xmm0
0x1800ee5e1  mov     [rax+0Eh], rcx
0x1800ee5e5  jmp     short loc_1800EE657
0x1800ee5e7  mov     edx, 1000h; dwSize
0x1800ee5ec  mov     r9d, 40h ; '@'; flProtect
0x1800ee5f2  mov     r8d, edx; flAllocationType
0x1800ee5f5  call    cs:__imp_VirtualAlloc
0x1800ee5fb  mov     rbx, rax
0x1800ee5fe  test    rax, rax
0x1800ee601  jnz     short loc_1800EE607
0x1800ee603  xor     eax, eax
0x1800ee605  jmp     short loc_1800EE657
0x1800ee607  mov     eax, [rax]
0x1800ee609  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x1800ee610  call    cs:__imp_InterlockedPopEntrySList
0x1800ee616  mov     rdi, rax
0x1800ee619  test    rax, rax
0x1800ee61c  jz      short loc_1800EE634
0x1800ee61e  xor     edx, edx; dwSize
0x1800ee620  mov     r8d, 8000h; dwFreeType
0x1800ee626  mov     rcx, rbx; lpAddress
0x1800ee629  call    cs:__imp_VirtualFree
0x1800ee62f  mov     rax, rdi
0x1800ee632  jmp     short loc_1800EE657
0x1800ee634  lea     rdi, [rbx+0FE0h]
0x1800ee63b  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x1800ee642  mov     rdx, rbx; ListEntry
0x1800ee645  call    cs:__imp_InterlockedPushEntrySList
0x1800ee64b  add     rbx, 20h ; ' '
0x1800ee64f  cmp     rbx, rdi
0x1800ee652  jb      short loc_1800EE63B
0x1800ee654  mov     rax, rbx
0x1800ee657  mov     rbx, [rsp+28h+arg_0]
0x1800ee65c  add     rsp, 20h
0x1800ee660  pop     rdi
0x1800ee661  retn
```
