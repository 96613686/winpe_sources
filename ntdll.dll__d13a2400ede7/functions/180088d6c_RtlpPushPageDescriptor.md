# RtlpPushPageDescriptor

- ea: `0x180088d6c`
- end: `0x180088edc`
- name: `RtlpPushPageDescriptor`
- size: `368`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180088be0`
- `0x180089538`

## callees

- `0x180007060`
- `0x18001b984`
- `0x180088d6c`
- `0x1800892e0`
- `0x18008932c`
- `0x180164280`

## string_xrefs

- `0x180088e63`: `Unable to allocate page descriptor\n`
- `0x180088e82`: `Conflicting descriptors %p\n`

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
0x180088d6c  push    rbx
0x180088d6e  push    rbp
0x180088d6f  push    rsi
0x180088d70  push    rdi
0x180088d71  push    r14
0x180088d73  push    r15
0x180088d75  sub     rsp, 28h
0x180088d79  mov     rsi, rcx
0x180088d7c  mov     r14, rdx
0x180088d7f  mov     rcx, cs:RtlpProcessMemoryMap
0x180088d86  shl     rsi, 0Ch
0x180088d8a  mov     rdx, rsi
0x180088d8d  call    RtlpGetBlockInfo
0x180088d92  test    rax, rax
0x180088d95  jnz     loc_180088E7F
0x180088d9b  mov     eax, cs:RtlpLDNumBlocks
0x180088da1  xor     edx, edx
0x180088da3  dec     eax
0x180088da5  movsxd  rcx, eax
0x180088da8  lea     r8, [rcx+rcx*4]
0x180088dac  mov     rcx, cs:RtlpLeakHeap
0x180088db3  lea     r8, ds:40h[r8*8]
0x180088dbb  call    RtlAllocateHeap_0
0x180088dc0  mov     rdi, rax
0x180088dc3  test    rax, rax
0x180088dc6  jz      loc_180088E63
0x180088dcc  movsxd  rbp, cs:RtlpLDNumBlocks
0x180088dd3  lea     r15, [rax+18h]
0x180088dd7  mov     rbx, cs:RtlpCrtHeapAddress
0x180088dde  mov     rcx, r15; void *
0x180088de1  mov     rdx, cs:RtlpTempBlocks; Src
0x180088de8  mov     dword ptr [rax], 2
0x180088dee  lea     r8, ds:0[rbp*4]
0x180088df6  mov     [rax+10h], ebp
0x180088df9  add     r8, rbp
0x180088dfc  mov     [rax+8], rbx
0x180088e00  shl     r8, 3; Size
0x180088e04  call    memmove
0x180088e09  cmp     rbx, cs:RtlpLeakHeapAddress
0x180088e10  jz      loc_180088EBF
0x180088e16  xor     ecx, ecx
0x180088e18  test    ebp, ebp
0x180088e1a  jle     loc_180088EBF
0x180088e20  mov     r9, cs:RtlpPreviousStartAddress
0x180088e27  lea     r10, RtlpLeakList
0x180088e2e  movsxd  rax, ecx
0x180088e31  lea     r8, [rdi+18h]
0x180088e35  lea     rdx, [rax+rax*4]
0x180088e39  lea     rax, [r15+rdx*8]
0x180088e3d  lea     r8, [r8+rdx*8]
0x180088e41  mov     [rdi+rdx*8+20h], rax
0x180088e46  mov     [r8], rax
0x180088e49  cmp     [rdi+rdx*8+28h], r9
0x180088e4e  jz      short loc_180088EB5
0x180088e50  mov     rax, cs:qword_1801CBFA8
0x180088e57  cmp     [rax], r10
0x180088e5a  jz      short loc_180088E90
0x180088e5c  mov     ecx, 3
0x180088e61  int     29h; Win8: RtlFailFast(ecx)
0x180088e63  lea     rcx, aUnableToAlloca; "Unable to allocate page descriptor\n"
0x180088e6a  call    DbgPrint
0x180088e6f  xor     al, al
0x180088e71  add     rsp, 28h
0x180088e75  pop     r15
0x180088e77  pop     r14
0x180088e79  pop     rdi
0x180088e7a  pop     rsi
0x180088e7b  pop     rbp
0x180088e7c  pop     rbx
0x180088e7d  retn
0x180088e7f  mov     rdx, rax
0x180088e82  lea     rcx, aConflictingDes; "Conflicting descriptors %p\n"
0x180088e89  call    DbgPrint
0x180088e8e  jmp     short loc_180088E6F
0x180088e90  mov     [r8], r10
0x180088e93  mov     [r8+8], rax
0x180088e97  mov     [rax], r8
0x180088e9a  mov     cs:qword_1801CBFA8, r8
0x180088ea1  mov     r9, [rdi+rdx*8+28h]
0x180088ea6  mov     cs:RtlpPreviousStartAddress, r9
0x180088ead  mov     dword ptr [rdi+rdx*8+38h], 0
0x180088eb5  inc     ecx
0x180088eb7  cmp     ecx, ebp
0x180088eb9  jl      loc_180088E2E
0x180088ebf  mov     rcx, cs:RtlpProcessMemoryMap
0x180088ec6  mov     r9, rdi
0x180088ec9  shl     r14, 0Ch
0x180088ecd  mov     rdx, rsi
0x180088ed0  mov     r8, r14
0x180088ed3  call    RtlpSetBlockInfo
0x180088ed8  mov     al, 1
0x180088eda  jmp     short loc_180088E71
```
