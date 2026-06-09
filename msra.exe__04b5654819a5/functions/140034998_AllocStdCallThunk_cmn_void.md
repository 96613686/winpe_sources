# __AllocStdCallThunk_cmn(void)

- ea: `0x140034998`
- end: `0x140034a74`
- name: `?__AllocStdCallThunk_cmn@@YAPEAXXZ`
- size: `220`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140034b10`

## callees

- `0x140034998`
- `0x140034a7c`

## import_xrefs

- `KERNEL32!VirtualFree` at `0x140034a2e`
- `KERNEL32!VirtualFree` at `0x140034a2e`
- `KERNEL32!VirtualAlloc` at `0x1400349ee`
- `KERNEL32!VirtualAlloc` at `0x1400349ee`
- `KERNEL32!InterlockedPushEntrySList` at `0x140034a50`
- `KERNEL32!InterlockedPushEntrySList` at `0x140034a50`
- `KERNEL32!InterlockedPopEntrySList` at `0x1400349be`
- `KERNEL32!InterlockedPopEntrySList` at `0x140034a0f`
- `KERNEL32!InterlockedPopEntrySList` at `0x1400349be`
- `KERNEL32!InterlockedPopEntrySList` at `0x140034a0f`

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
0x140034998  mov     [rsp+arg_0], rbx
0x14003499d  push    rdi
0x14003499e  sub     rsp, 20h
0x1400349a2  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; _SLIST_HEADER * __AtlThunkPool
0x1400349a9  test    rcx, rcx
0x1400349ac  jnz     short loc_1400349BE
0x1400349ae  call    __InitializeThunkPool
0x1400349b3  test    eax, eax
0x1400349b5  jz      short loc_140034A02
0x1400349b7  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x1400349be  call    cs:__imp_InterlockedPopEntrySList
0x1400349c5  nop     dword ptr [rax+rax+00h]
0x1400349ca  xor     ecx, ecx; lpAddress
0x1400349cc  test    rax, rax
0x1400349cf  jz      short loc_1400349E0
0x1400349d1  xorps   xmm0, xmm0
0x1400349d4  movups  xmmword ptr [rax], xmm0
0x1400349d7  mov     [rax+0Eh], rcx
0x1400349db  jmp     loc_140034A68
0x1400349e0  mov     edx, 1000h; dwSize
0x1400349e5  mov     r9d, 40h ; '@'; flProtect
0x1400349eb  mov     r8d, edx; flAllocationType
0x1400349ee  call    cs:__imp_VirtualAlloc
0x1400349f5  nop     dword ptr [rax+rax+00h]
0x1400349fa  mov     rbx, rax
0x1400349fd  test    rax, rax
0x140034a00  jnz     short loc_140034A06
0x140034a02  xor     eax, eax
0x140034a04  jmp     short loc_140034A68
0x140034a06  mov     eax, [rax]
0x140034a08  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x140034a0f  call    cs:__imp_InterlockedPopEntrySList
0x140034a16  nop     dword ptr [rax+rax+00h]
0x140034a1b  mov     rdi, rax
0x140034a1e  test    rax, rax
0x140034a21  jz      short loc_140034A3F
0x140034a23  xor     edx, edx; dwSize
0x140034a25  mov     r8d, 8000h; dwFreeType
0x140034a2b  mov     rcx, rbx; lpAddress
0x140034a2e  call    cs:__imp_VirtualFree
0x140034a35  nop     dword ptr [rax+rax+00h]
0x140034a3a  mov     rax, rdi
0x140034a3d  jmp     short loc_140034A68
0x140034a3f  lea     rdi, [rbx+0FE0h]
0x140034a46  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x140034a4d  mov     rdx, rbx; ListEntry
0x140034a50  call    cs:__imp_InterlockedPushEntrySList
0x140034a57  nop     dword ptr [rax+rax+00h]
0x140034a5c  add     rbx, 20h ; ' '
0x140034a60  cmp     rbx, rdi
0x140034a63  jb      short loc_140034A46
0x140034a65  mov     rax, rbx
0x140034a68  mov     rbx, [rsp+28h+arg_0]
0x140034a6d  add     rsp, 20h
0x140034a71  pop     rdi
0x140034a72  retn
```
