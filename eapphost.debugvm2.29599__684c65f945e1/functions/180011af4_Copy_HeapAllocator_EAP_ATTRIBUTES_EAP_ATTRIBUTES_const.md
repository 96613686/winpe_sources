# Copy<HeapAllocator>(_EAP_ATTRIBUTES &,_EAP_ATTRIBUTES const &)

- ea: `0x180011af4`
- end: `0x180011cec`
- name: `??$Copy@VHeapAllocator@@@@YA_NAEAU_EAP_ATTRIBUTES@@AEBU0@@Z`
- size: `504`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180011da0`

## callees

- `0x18000343c`
- `0x1800072cc`
- `0x18000940c`
- `0x180011af4`
- `0x18002f7ec`
- `0x180033d78`

## pseudocode

```c
char __fastcall Copy<HeapAllocator>(__int64 a1, _DWORD *a2)
{
  __int64 *v2; // r15
  int v3; // r8d
  int v4; // esi
  void *v7; // rcx
  char result; // al
  __int64 v9; // rdx
  unsigned int v10; // eax
  int v11; // r9d
  __int64 v12; // r10
  unsigned int v13; // ebx
  void *v14; // rax
  int v15; // ebp
  __int64 v16; // rax
  int v17; // ecx
  __int64 v18; // rbx
  void *v19; // rcx
  __int64 v20; // rdx
  size_t Size; // [rsp+58h] [rbp+10h] BYREF

  v2 = (__int64 *)(a2 + 2);
  *(_OWORD *)a1 = 0;
  v3 = *a2;
  v4 = 0;
  if ( !*a2 )
  {
    if ( *v2 )
      goto LABEL_3;
    goto LABEL_11;
  }
  if ( *v2 )
  {
LABEL_11:
    v9 = *v2;
    if ( !*v2 )
      return 1;
    v10 = 0;
    LODWORD(Size) = 0;
    if ( v3 <= 0 )
      return 1;
    v11 = 0;
    v12 = 0;
    while ( !*(_DWORD *)(v9 + 16 * v12 + 4) )
    {
      if ( !*(_QWORD *)(v9 + 16 * v12 + 8) )
        goto LABEL_18;
LABEL_19:
      ++v11;
      ++v12;
      if ( v11 >= v3 )
      {
        LODWORD(Size) = v10;
        if ( v10 )
        {
          *(_DWORD *)a1 = v10;
          if ( (int)ULongLongToULong(16LL * v10, (unsigned int *)&Size) < 0 )
            goto LABEL_3;
          v13 = Size;
          v14 = Heap::AllocNoThrow((Heap *)&HeapAllocator::heap, (unsigned int)Size);
          *(_QWORD *)(a1 + 8) = v14;
          if ( !v14 )
            goto LABEL_3;
          memset_0(v14, 0, v13);
          v15 = 0;
          while ( 2 )
          {
            if ( v15 >= *a2 )
              return 1;
            v16 = *v2;
            v17 = *(_DWORD *)(*v2 + 16LL * v15 + 4);
            if ( v17 )
            {
              if ( *(_QWORD *)(v16 + 16LL * v15 + 8) )
              {
                v18 = 2LL * v4;
                *(_DWORD *)(*(_QWORD *)(a1 + 8) + 8 * v18 + 4) = v17;
                *(_DWORD *)(*(_QWORD *)(a1 + 8) + 8 * v18) = *(_DWORD *)(*v2 + 16LL * v15);
                *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL * v4 + 8) = Heap::AllocNoThrow(
                                                                     (Heap *)&HeapAllocator::heap,
                                                                     *(unsigned int *)(*v2 + 16LL * v15 + 4));
                v19 = *(void **)(*(_QWORD *)(a1 + 8) + 16LL * v4 + 8);
                if ( !v19 )
                  goto LABEL_3;
                memcpy_0(v19, *(const void **)(*v2 + 16LL * v15 + 8), *(unsigned int *)(*v2 + 16LL * v15 + 4));
LABEL_31:
                ++v4;
              }
            }
            else if ( !*(_QWORD *)(v16 + 16LL * v15 + 8) )
            {
              v20 = 2LL * v4;
              *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v20 + 8) = 0;
              *(_DWORD *)(*(_QWORD *)(a1 + 8) + 8 * v20 + 4) = 0;
              *(_DWORD *)(*(_QWORD *)(a1 + 8) + 8 * v20) = *(_DWORD *)(*v2 + 16LL * v15);
              goto LABEL_31;
            }
            ++v15;
            continue;
          }
        }
        return 1;
      }
    }
    if ( !*(_QWORD *)(v9 + 16 * v12 + 8) )
      goto LABEL_19;
LABEL_18:
    ++v10;
    goto LABEL_19;
  }
LABEL_3:
  if ( *(_QWORD *)(a1 + 8) )
  {
    for ( ; v4 >= 0; --v4 )
    {
      v7 = *(void **)(*(_QWORD *)(a1 + 8) + 16LL * (unsigned int)v4 + 8);
      if ( v7 )
        HeapAllocator::Free(v7);
    }
    HeapAllocator::Free(*(void **)(a1 + 8));
  }
  result = 0;
  *(_OWORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180011af4  mov     [rsp+arg_0], rbx
0x180011af9  mov     [rsp+arg_10], rbp
0x180011afe  push    rsi
0x180011aff  push    rdi
0x180011b00  push    r12
0x180011b02  push    r14
0x180011b04  push    r15
0x180011b06  sub     rsp, 20h
0x180011b0a  xorps   xmm0, xmm0
0x180011b0d  lea     r15, [rdx+8]
0x180011b11  movups  xmmword ptr [rcx], xmm0
0x180011b14  mov     r8d, [rdx]
0x180011b17  xor     esi, esi
0x180011b19  mov     r12, rdx
0x180011b1c  mov     rdi, rcx
0x180011b1f  test    r8d, r8d
0x180011b22  jz      short loc_180011B67
0x180011b24  cmp     [r15], rsi
0x180011b27  jnz     short loc_180011B6C
0x180011b29  cmp     qword ptr [rdi+8], 0
0x180011b2e  jz      short loc_180011B5A
0x180011b30  test    esi, esi
0x180011b32  js      short loc_180011B51
0x180011b34  mov     rax, [rdi+8]
0x180011b38  mov     ecx, esi
0x180011b3a  add     rcx, rcx
0x180011b3d  mov     rcx, [rax+rcx*8+8]; void *
0x180011b42  test    rcx, rcx
0x180011b45  jz      short loc_180011B4C
0x180011b47  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180011b4c  sub     esi, 1
0x180011b4f  jns     short loc_180011B34
0x180011b51  mov     rcx, [rdi+8]; void *
0x180011b55  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180011b5a  xorps   xmm0, xmm0
0x180011b5d  xor     al, al
0x180011b5f  movups  xmmword ptr [rdi], xmm0
0x180011b62  jmp     loc_180011CD5
0x180011b67  cmp     [r15], rsi
0x180011b6a  jnz     short loc_180011B29
0x180011b6c  mov     rdx, [r15]
0x180011b6f  test    rdx, rdx
0x180011b72  jz      loc_180011CD3
0x180011b78  xor     eax, eax
0x180011b7a  mov     dword ptr [rsp+48h+Size], eax
0x180011b7e  test    r8d, r8d
0x180011b81  jle     loc_180011CD3
0x180011b87  xor     r9d, r9d
0x180011b8a  xor     r10d, r10d
0x180011b8d  mov     rcx, r10
0x180011b90  add     rcx, rcx
0x180011b93  mov     r11d, [rdx+rcx*8+4]
0x180011b98  test    r11d, r11d
0x180011b9b  jz      short loc_180011BA6
0x180011b9d  cmp     [rdx+rcx*8+8], rsi
0x180011ba2  jnz     short loc_180011BAD
0x180011ba4  jmp     short loc_180011BAF
0x180011ba6  cmp     [rdx+rcx*8+8], rsi
0x180011bab  jnz     short loc_180011BAF
0x180011bad  inc     eax
0x180011baf  inc     r9d
0x180011bb2  inc     r10
0x180011bb5  cmp     r9d, r8d
0x180011bb8  jl      short loc_180011B8D
0x180011bba  mov     dword ptr [rsp+48h+Size], eax
0x180011bbe  test    eax, eax
0x180011bc0  jz      loc_180011CD3
0x180011bc6  mov     ecx, eax
0x180011bc8  lea     rdx, [rsp+48h+Size]; unsigned int *
0x180011bcd  shl     rcx, 4; unsigned __int64
0x180011bd1  mov     [rdi], eax
0x180011bd3  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180011bd8  test    eax, eax
0x180011bda  js      loc_180011B29
0x180011be0  mov     ebx, dword ptr [rsp+48h+Size]
0x180011be4  lea     rcx, ?heap@HeapAllocator@@0V?$StaticObject@VHeap@@@@A; this
0x180011beb  mov     edx, ebx; unsigned __int64
0x180011bed  call    ?AllocNoThrow@Heap@@QEAAPEAX_K@Z; Heap::AllocNoThrow(unsigned __int64)
0x180011bf2  mov     [rdi+8], rax
0x180011bf6  test    rax, rax
0x180011bf9  jz      loc_180011B29
0x180011bff  mov     r8d, ebx; Size
0x180011c02  xor     edx, edx; Val
0x180011c04  mov     rcx, rax; void *
0x180011c07  call    memset_0
0x180011c0c  xor     ebp, ebp
0x180011c0e  cmp     ebp, [r12]
0x180011c12  jge     loc_180011CD3
0x180011c18  mov     rax, [r15]
0x180011c1b  movsxd  r14, ebp
0x180011c1e  add     r14, r14
0x180011c21  mov     ecx, [rax+r14*8+4]
0x180011c26  test    ecx, ecx
0x180011c28  jz      short loc_180011C95
0x180011c2a  cmp     qword ptr [rax+r14*8+8], 0
0x180011c30  jz      loc_180011CCC
0x180011c36  mov     rax, [rdi+8]
0x180011c3a  movsxd  rbx, esi
0x180011c3d  add     rbx, rbx
0x180011c40  mov     [rax+rbx*8+4], ecx
0x180011c44  mov     rax, [r15]
0x180011c47  mov     rcx, [rdi+8]
0x180011c4b  mov     eax, [rax+r14*8]
0x180011c4f  mov     [rcx+rbx*8], eax
0x180011c52  lea     rcx, ?heap@HeapAllocator@@0V?$StaticObject@VHeap@@@@A; this
0x180011c59  mov     rax, [r15]
0x180011c5c  mov     edx, [rax+r14*8+4]; unsigned __int64
0x180011c61  call    ?AllocNoThrow@Heap@@QEAAPEAX_K@Z; Heap::AllocNoThrow(unsigned __int64)
0x180011c66  mov     rcx, [rdi+8]
0x180011c6a  mov     [rcx+rbx*8+8], rax
0x180011c6f  mov     rax, [rdi+8]
0x180011c73  mov     rcx, [rax+rbx*8+8]; void *
0x180011c78  test    rcx, rcx
0x180011c7b  jz      loc_180011B29
0x180011c81  mov     rdx, [r15]
0x180011c84  mov     r8d, [rdx+r14*8+4]; Size
0x180011c89  mov     rdx, [rdx+r14*8+8]; Src
0x180011c8e  call    memcpy_0
0x180011c93  jmp     short loc_180011CCA
0x180011c95  cmp     qword ptr [rax+r14*8+8], 0
0x180011c9b  jnz     short loc_180011CCC
0x180011c9d  mov     rax, [rdi+8]
0x180011ca1  movsxd  rdx, esi
0x180011ca4  add     rdx, rdx
0x180011ca7  mov     qword ptr [rax+rdx*8+8], 0
0x180011cb0  mov     rax, [rdi+8]
0x180011cb4  mov     dword ptr [rax+rdx*8+4], 0
0x180011cbc  mov     rax, [r15]
0x180011cbf  mov     rcx, [rdi+8]
0x180011cc3  mov     eax, [rax+r14*8]
0x180011cc7  mov     [rcx+rdx*8], eax
0x180011cca  inc     esi
0x180011ccc  inc     ebp
0x180011cce  jmp     loc_180011C0E
0x180011cd3  mov     al, 1
0x180011cd5  mov     rbx, [rsp+48h+arg_0]
0x180011cda  mov     rbp, [rsp+48h+arg_10]
0x180011cdf  add     rsp, 20h
0x180011ce3  pop     r15
0x180011ce5  pop     r14
0x180011ce7  pop     r12
0x180011ce9  pop     rdi
0x180011cea  pop     rsi
0x180011ceb  retn
```
