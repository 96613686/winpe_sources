# LuafvInitializePool

- ea: `0x14002a15c`
- end: `0x14002a268`
- name: `LuafvInitializePool`
- size: `268`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400291a8`

## callees

- `0x14002a15c`

## import_xrefs

- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002a1aa`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002a1e6`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002a23a`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002a1aa`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002a1e6`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002a23a`
- `FLTMGR!FltInitializePushLock` at `0x14002a16f`
- `FLTMGR!FltInitializePushLock` at `0x14002a16f`

## pseudocode

```c
__int64 LuafvInitializePool()
{
  unsigned int v0; // edi
  unsigned int v1; // esi
  struct _PAGED_LOOKASIDE_LIST *v2; // rbx
  __int64 result; // rax

  FltInitializePushLock(&PoolLock);
  ExInitializePagedLookasideList(&StoreFileLookaside, 0, 0, 0, 0x78u, 0x6661754Cu, 0x80u);
  LookasideLists[0] = (__int64)&StoreFileLookaside;
  ExInitializePagedLookasideList(&TableNodeLookaside, 0, 0, 0, 0x128u, 0x6661754Cu, 0x80u);
  v0 = 0;
  qword_14000EA88 = (__int64)&TableNodeLookaside;
  v1 = 56;
  do
  {
    v2 = (struct _PAGED_LOOKASIDE_LIST *)&StringLookaside[16 * (unsigned __int64)v0];
    ExInitializePagedLookasideList(v2, 0, 0, 0, v1 + 8LL, 0x6661754Cu, 0x80u);
    result = v0 + 2;
    v1 += 32;
    ++v0;
    LookasideLists[result] = (__int64)v2;
  }
  while ( v0 < 5 );
  return result;
}

```

## disassembly

```asm
0x14002a15c  push    rbx
0x14002a15e  push    rsi
0x14002a15f  push    rdi
0x14002a160  push    r14
0x14002a162  push    r15
0x14002a164  sub     rsp, 40h
0x14002a168  lea     rcx, PoolLock; PushLock
0x14002a16f  call    cs:__imp_FltInitializePushLock
0x14002a176  nop     dword ptr [rax+rax+00h]
0x14002a17b  mov     r14d, 80h
0x14002a181  lea     rbx, StoreFileLookaside
0x14002a188  mov     [rsp+68h+Depth], r14w; Depth
0x14002a18e  xor     r9d, r9d; Flags
0x14002a191  mov     [rsp+68h+Tag], 6661754Ch; Tag
0x14002a199  xor     r8d, r8d; Free
0x14002a19c  xor     edx, edx; Allocate
0x14002a19e  mov     [rsp+68h+Size], 78h ; 'x'; Size
0x14002a1a7  mov     rcx, rbx; Lookaside
0x14002a1aa  call    cs:__imp_ExInitializePagedLookasideList
0x14002a1b1  nop     dword ptr [rax+rax+00h]
0x14002a1b6  mov     cs:LookasideLists, rbx
0x14002a1bd  xor     r9d, r9d; Flags
0x14002a1c0  mov     [rsp+68h+Depth], r14w; Depth
0x14002a1c6  lea     rbx, TableNodeLookaside
0x14002a1cd  mov     rcx, rbx; Lookaside
0x14002a1d0  mov     [rsp+68h+Tag], 6661754Ch; Tag
0x14002a1d8  xor     r8d, r8d; Free
0x14002a1db  mov     [rsp+68h+Size], 128h; Size
0x14002a1e4  xor     edx, edx; Allocate
0x14002a1e6  call    cs:__imp_ExInitializePagedLookasideList
0x14002a1ed  nop     dword ptr [rax+rax+00h]
0x14002a1f2  xor     edi, edi
0x14002a1f4  mov     cs:qword_14000EA88, rbx
0x14002a1fb  lea     esi, [r14-48h]
0x14002a1ff  lea     r15, cs:140000000h
0x14002a206  mov     [rsp+68h+Depth], r14w; Depth
0x14002a20c  lea     rbx, rva StringLookaside[r15]
0x14002a213  mov     eax, edi
0x14002a215  xor     r9d, r9d; Flags
0x14002a218  shl     rax, 7
0x14002a21c  xor     r8d, r8d; Free
0x14002a21f  add     rbx, rax
0x14002a222  mov     [rsp+68h+Tag], 6661754Ch; Tag
0x14002a22a  mov     eax, esi
0x14002a22c  xor     edx, edx; Allocate
0x14002a22e  add     rax, 8
0x14002a232  mov     rcx, rbx; Lookaside
0x14002a235  mov     [rsp+68h+Size], rax; Size
0x14002a23a  call    cs:__imp_ExInitializePagedLookasideList
0x14002a241  nop     dword ptr [rax+rax+00h]
0x14002a246  lea     eax, [rdi+2]
0x14002a249  add     esi, 20h ; ' '
0x14002a24c  inc     edi
0x14002a24e  mov     rva LookasideLists[r15+rax*8], rbx
0x14002a256  cmp     edi, 5
0x14002a259  jb      short loc_14002A206
0x14002a25b  add     rsp, 40h
0x14002a25f  pop     r15
0x14002a261  pop     r14
0x14002a263  pop     rdi
0x14002a264  pop     rsi
0x14002a265  pop     rbx
0x14002a266  retn
```
