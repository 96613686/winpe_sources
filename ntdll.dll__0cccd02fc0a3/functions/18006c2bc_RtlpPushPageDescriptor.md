# RtlpPushPageDescriptor

- ea: `0x18006c2bc`
- end: `0x18006c42c`
- name: `RtlpPushPageDescriptor`
- size: `368`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18006c130`
- `0x18006ca88`

## callees

- `0x180007060`
- `0x18001b984`
- `0x18006c2bc`
- `0x18006c830`
- `0x18006c87c`
- `0x180163a80`

## string_xrefs

- `0x18006c3b3`: `Unable to allocate page descriptor\n`
- `0x18006c3d2`: `Conflicting descriptors %p\n`

## pseudocode

```c
char __fastcall RtlpPushPageDescriptor(__int64 a1, __int64 a2)
{
  __int64 v3; // rsi
  const void *BlockInfo; // rax
  __int64 Heap_0; // rax
  __int64 v6; // rdi
  __int64 v7; // rbp
  __int64 v8; // r15
  __int64 v9; // rbx
  const void *v10; // rdx
  int v11; // ecx
  __int64 v12; // r9
  __int64 v13; // rax
  __int64 *v14; // r8
  __int64 **v15; // rax

  v3 = a1 << 12;
  BlockInfo = (const void *)RtlpGetBlockInfo(RtlpProcessMemoryMap, a1 << 12);
  if ( BlockInfo )
  {
    DbgPrint("Conflicting descriptors %p\n", BlockInfo);
    return 0;
  }
  Heap_0 = RtlAllocateHeap_0(RtlpLeakHeap, 0, 40LL * (RtlpLDNumBlocks - 1) + 64);
  v6 = Heap_0;
  if ( !Heap_0 )
  {
    DbgPrint("Unable to allocate page descriptor\n");
    return 0;
  }
  v7 = RtlpLDNumBlocks;
  v8 = Heap_0 + 24;
  v9 = RtlpCrtHeapAddress;
  v10 = RtlpTempBlocks;
  *(_DWORD *)Heap_0 = 2;
  *(_DWORD *)(Heap_0 + 16) = v7;
  *(_QWORD *)(Heap_0 + 8) = v9;
  memmove((void *)(Heap_0 + 24), v10, 40 * v7);
  if ( v9 != RtlpLeakHeapAddress )
  {
    v11 = 0;
    if ( (int)v7 > 0 )
    {
      v12 = RtlpPreviousStartAddress;
      do
      {
        v13 = v8 + 40LL * v11;
        v14 = (__int64 *)(v6 + 24 + 40LL * v11);
        *(_QWORD *)(v6 + 40LL * v11 + 32) = v13;
        *v14 = v13;
        if ( *(_QWORD *)(v6 + 40LL * v11 + 40) != v12 )
        {
          v15 = (__int64 **)qword_1801CBFA8;
          if ( *(__int64 **)qword_1801CBFA8 != &RtlpLeakList )
            __fastfail(3u);
          *v14 = (__int64)&RtlpLeakList;
          v14[1] = (__int64)v15;
          *v15 = v14;
          qword_1801CBFA8 = v6 + 24 + 40LL * v11;
          v12 = *(_QWORD *)(v6 + 40LL * v11 + 40);
          RtlpPreviousStartAddress = v12;
          *(_DWORD *)(v6 + 40LL * v11 + 56) = 0;
        }
        ++v11;
      }
      while ( v11 < (int)v7 );
    }
  }
  RtlpSetBlockInfo(RtlpProcessMemoryMap, v3, a2 << 12, v6);
  return 1;
}

```

## disassembly

```asm
0x18006c2bc  push    rbx
0x18006c2be  push    rbp
0x18006c2bf  push    rsi
0x18006c2c0  push    rdi
0x18006c2c1  push    r14
0x18006c2c3  push    r15
0x18006c2c5  sub     rsp, 28h
0x18006c2c9  mov     rsi, rcx
0x18006c2cc  mov     r14, rdx
0x18006c2cf  mov     rcx, cs:RtlpProcessMemoryMap
0x18006c2d6  shl     rsi, 0Ch
0x18006c2da  mov     rdx, rsi
0x18006c2dd  call    RtlpGetBlockInfo
0x18006c2e2  test    rax, rax
0x18006c2e5  jnz     loc_18006C3CF
0x18006c2eb  mov     eax, cs:RtlpLDNumBlocks
0x18006c2f1  xor     edx, edx
0x18006c2f3  dec     eax
0x18006c2f5  movsxd  rcx, eax
0x18006c2f8  lea     r8, [rcx+rcx*4]
0x18006c2fc  mov     rcx, cs:RtlpLeakHeap
0x18006c303  lea     r8, ds:40h[r8*8]
0x18006c30b  call    RtlAllocateHeap_0
0x18006c310  mov     rdi, rax
0x18006c313  test    rax, rax
0x18006c316  jz      loc_18006C3B3
0x18006c31c  movsxd  rbp, cs:RtlpLDNumBlocks
0x18006c323  lea     r15, [rax+18h]
0x18006c327  mov     rbx, cs:RtlpCrtHeapAddress
0x18006c32e  mov     rcx, r15; void *
0x18006c331  mov     rdx, cs:RtlpTempBlocks; Src
0x18006c338  mov     dword ptr [rax], 2
0x18006c33e  lea     r8, ds:0[rbp*4]
0x18006c346  mov     [rax+10h], ebp
0x18006c349  add     r8, rbp
0x18006c34c  mov     [rax+8], rbx
0x18006c350  shl     r8, 3; Size
0x18006c354  call    memmove
0x18006c359  cmp     rbx, cs:RtlpLeakHeapAddress
0x18006c360  jz      loc_18006C40F
0x18006c366  xor     ecx, ecx
0x18006c368  test    ebp, ebp
0x18006c36a  jle     loc_18006C40F
0x18006c370  mov     r9, cs:RtlpPreviousStartAddress
0x18006c377  lea     r10, RtlpLeakList
0x18006c37e  movsxd  rax, ecx
0x18006c381  lea     r8, [rdi+18h]
0x18006c385  lea     rdx, [rax+rax*4]
0x18006c389  lea     rax, [r15+rdx*8]
0x18006c38d  lea     r8, [r8+rdx*8]
0x18006c391  mov     [rdi+rdx*8+20h], rax
0x18006c396  mov     [r8], rax
0x18006c399  cmp     [rdi+rdx*8+28h], r9
0x18006c39e  jz      short loc_18006C405
0x18006c3a0  mov     rax, cs:qword_1801CBFA8
0x18006c3a7  cmp     [rax], r10
0x18006c3aa  jz      short loc_18006C3E0
0x18006c3ac  mov     ecx, 3
0x18006c3b1  int     29h; Win8: RtlFailFast(ecx)
0x18006c3b3  lea     rcx, aUnableToAlloca; "Unable to allocate page descriptor\n"
0x18006c3ba  call    DbgPrint
0x18006c3bf  xor     al, al
0x18006c3c1  add     rsp, 28h
0x18006c3c5  pop     r15
0x18006c3c7  pop     r14
0x18006c3c9  pop     rdi
0x18006c3ca  pop     rsi
0x18006c3cb  pop     rbp
0x18006c3cc  pop     rbx
0x18006c3cd  retn
0x18006c3cf  mov     rdx, rax
0x18006c3d2  lea     rcx, aConflictingDes; "Conflicting descriptors %p\n"
0x18006c3d9  call    DbgPrint
0x18006c3de  jmp     short loc_18006C3BF
0x18006c3e0  mov     [r8], r10
0x18006c3e3  mov     [r8+8], rax
0x18006c3e7  mov     [rax], r8
0x18006c3ea  mov     cs:qword_1801CBFA8, r8
0x18006c3f1  mov     r9, [rdi+rdx*8+28h]
0x18006c3f6  mov     cs:RtlpPreviousStartAddress, r9
0x18006c3fd  mov     dword ptr [rdi+rdx*8+38h], 0
0x18006c405  inc     ecx
0x18006c407  cmp     ecx, ebp
0x18006c409  jl      loc_18006C37E
0x18006c40f  mov     rcx, cs:RtlpProcessMemoryMap
0x18006c416  mov     r9, rdi
0x18006c419  shl     r14, 0Ch
0x18006c41d  mov     rdx, rsi
0x18006c420  mov     r8, r14
0x18006c423  call    RtlpSetBlockInfo
0x18006c428  mov     al, 1
0x18006c42a  jmp     short loc_18006C3C1
```
