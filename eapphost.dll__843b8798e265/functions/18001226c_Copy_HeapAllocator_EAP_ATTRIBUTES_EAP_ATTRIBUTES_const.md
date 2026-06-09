# Copy<HeapAllocator>(_EAP_ATTRIBUTES &,_EAP_ATTRIBUTES const &)

- ea: `0x18001226c`
- end: `0x180012465`
- name: `??$Copy@VHeapAllocator@@@@YA_NAEAU_EAP_ATTRIBUTES@@AEBU0@@Z`
- size: `505`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180012518`

## callees

- `0x1800034cc`
- `0x180007564`
- `0x1800097e0`
- `0x18001226c`
- `0x180030994`
- `0x180035138`

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
0x18001226c  mov     [rsp+arg_0], rbx
0x180012271  mov     [rsp+arg_10], rbp
0x180012276  push    rsi
0x180012277  push    rdi
0x180012278  push    r12
0x18001227a  push    r14
0x18001227c  push    r15
0x18001227e  sub     rsp, 20h
0x180012282  xorps   xmm0, xmm0
0x180012285  lea     r15, [rdx+8]
0x180012289  movups  xmmword ptr [rcx], xmm0
0x18001228c  mov     r8d, [rdx]
0x18001228f  xor     esi, esi
0x180012291  mov     r12, rdx
0x180012294  mov     rdi, rcx
0x180012297  test    r8d, r8d
0x18001229a  jz      short loc_1800122DF
0x18001229c  cmp     [r15], rsi
0x18001229f  jnz     short loc_1800122E4
0x1800122a1  cmp     qword ptr [rdi+8], 0
0x1800122a6  jz      short loc_1800122D2
0x1800122a8  test    esi, esi
0x1800122aa  js      short loc_1800122C9
0x1800122ac  mov     rax, [rdi+8]
0x1800122b0  mov     ecx, esi
0x1800122b2  add     rcx, rcx
0x1800122b5  mov     rcx, [rax+rcx*8+8]; void *
0x1800122ba  test    rcx, rcx
0x1800122bd  jz      short loc_1800122C4
0x1800122bf  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x1800122c4  sub     esi, 1
0x1800122c7  jns     short loc_1800122AC
0x1800122c9  mov     rcx, [rdi+8]; void *
0x1800122cd  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x1800122d2  xorps   xmm0, xmm0
0x1800122d5  xor     al, al
0x1800122d7  movups  xmmword ptr [rdi], xmm0
0x1800122da  jmp     loc_18001244D
0x1800122df  cmp     [r15], rsi
0x1800122e2  jnz     short loc_1800122A1
0x1800122e4  mov     rdx, [r15]
0x1800122e7  test    rdx, rdx
0x1800122ea  jz      loc_18001244B
0x1800122f0  xor     eax, eax
0x1800122f2  mov     dword ptr [rsp+48h+Size], eax
0x1800122f6  test    r8d, r8d
0x1800122f9  jle     loc_18001244B
0x1800122ff  xor     r9d, r9d
0x180012302  xor     r10d, r10d
0x180012305  mov     rcx, r10
0x180012308  add     rcx, rcx
0x18001230b  mov     r11d, [rdx+rcx*8+4]
0x180012310  test    r11d, r11d
0x180012313  jz      short loc_18001231E
0x180012315  cmp     [rdx+rcx*8+8], rsi
0x18001231a  jnz     short loc_180012325
0x18001231c  jmp     short loc_180012327
0x18001231e  cmp     [rdx+rcx*8+8], rsi
0x180012323  jnz     short loc_180012327
0x180012325  inc     eax
0x180012327  inc     r9d
0x18001232a  inc     r10
0x18001232d  cmp     r9d, r8d
0x180012330  jl      short loc_180012305
0x180012332  mov     dword ptr [rsp+48h+Size], eax
0x180012336  test    eax, eax
0x180012338  jz      loc_18001244B
0x18001233e  mov     ecx, eax
0x180012340  lea     rdx, [rsp+48h+Size]; unsigned int *
0x180012345  shl     rcx, 4; unsigned __int64
0x180012349  mov     [rdi], eax
0x18001234b  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180012350  test    eax, eax
0x180012352  js      loc_1800122A1
0x180012358  mov     ebx, dword ptr [rsp+48h+Size]
0x18001235c  lea     rcx, ?heap@HeapAllocator@@0V?$StaticObject@VHeap@@@@A; this
0x180012363  mov     edx, ebx; unsigned __int64
0x180012365  call    ?AllocNoThrow@Heap@@QEAAPEAX_K@Z; Heap::AllocNoThrow(unsigned __int64)
0x18001236a  mov     [rdi+8], rax
0x18001236e  test    rax, rax
0x180012371  jz      loc_1800122A1
0x180012377  mov     r8d, ebx; Size
0x18001237a  xor     edx, edx; Val
0x18001237c  mov     rcx, rax; void *
0x18001237f  call    memset_0
0x180012384  xor     ebp, ebp
0x180012386  cmp     ebp, [r12]
0x18001238a  jge     loc_18001244B
0x180012390  mov     rax, [r15]
0x180012393  movsxd  r14, ebp
0x180012396  add     r14, r14
0x180012399  mov     ecx, [rax+r14*8+4]
0x18001239e  test    ecx, ecx
0x1800123a0  jz      short loc_18001240D
0x1800123a2  cmp     qword ptr [rax+r14*8+8], 0
0x1800123a8  jz      loc_180012444
0x1800123ae  mov     rax, [rdi+8]
0x1800123b2  movsxd  rbx, esi
0x1800123b5  add     rbx, rbx
0x1800123b8  mov     [rax+rbx*8+4], ecx
0x1800123bc  mov     rax, [r15]
0x1800123bf  mov     rcx, [rdi+8]
0x1800123c3  mov     eax, [rax+r14*8]
0x1800123c7  mov     [rcx+rbx*8], eax
0x1800123ca  lea     rcx, ?heap@HeapAllocator@@0V?$StaticObject@VHeap@@@@A; this
0x1800123d1  mov     rax, [r15]
0x1800123d4  mov     edx, [rax+r14*8+4]; unsigned __int64
0x1800123d9  call    ?AllocNoThrow@Heap@@QEAAPEAX_K@Z; Heap::AllocNoThrow(unsigned __int64)
0x1800123de  mov     rcx, [rdi+8]
0x1800123e2  mov     [rcx+rbx*8+8], rax
0x1800123e7  mov     rax, [rdi+8]
0x1800123eb  mov     rcx, [rax+rbx*8+8]; void *
0x1800123f0  test    rcx, rcx
0x1800123f3  jz      loc_1800122A1
0x1800123f9  mov     rdx, [r15]
0x1800123fc  mov     r8d, [rdx+r14*8+4]; Size
0x180012401  mov     rdx, [rdx+r14*8+8]; Src
0x180012406  call    memcpy_0
0x18001240b  jmp     short loc_180012442
0x18001240d  cmp     qword ptr [rax+r14*8+8], 0
0x180012413  jnz     short loc_180012444
0x180012415  mov     rax, [rdi+8]
0x180012419  movsxd  rdx, esi
0x18001241c  add     rdx, rdx
0x18001241f  mov     qword ptr [rax+rdx*8+8], 0
0x180012428  mov     rax, [rdi+8]
0x18001242c  mov     dword ptr [rax+rdx*8+4], 0
0x180012434  mov     rax, [r15]
0x180012437  mov     rcx, [rdi+8]
0x18001243b  mov     eax, [rax+r14*8]
0x18001243f  mov     [rcx+rdx*8], eax
0x180012442  inc     esi
0x180012444  inc     ebp
0x180012446  jmp     loc_180012386
0x18001244b  mov     al, 1
0x18001244d  mov     rbx, [rsp+48h+arg_0]
0x180012452  mov     rbp, [rsp+48h+arg_10]
0x180012457  add     rsp, 20h
0x18001245b  pop     r15
0x18001245d  pop     r14
0x18001245f  pop     r12
0x180012461  pop     rdi
0x180012462  pop     rsi
0x180012463  retn
```
