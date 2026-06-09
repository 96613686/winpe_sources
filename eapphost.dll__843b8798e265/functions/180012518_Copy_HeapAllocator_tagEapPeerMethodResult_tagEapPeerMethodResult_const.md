# Copy<HeapAllocator>(tagEapPeerMethodResult &,tagEapPeerMethodResult const &)

- ea: `0x180012518`
- end: `0x180012659`
- name: `??$Copy@VHeapAllocator@@@@YA_NAEAUtagEapPeerMethodResult@@AEBU0@@Z`
- size: `321`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180012a6c`

## callees

- `0x1800034cc`
- `0x18001226c`
- `0x18001246c`
- `0x180012518`
- `0x180012704`
- `0x180030994`
- `0x180035138`

## pseudocode

```c
char __fastcall Copy<HeapAllocator>(_DWORD *a1, __int64 a2)
{
  void *v4; // rax
  char v5; // di
  void *v6; // rax
  void *v7; // rax
  void *v8; // rax

  memset_0(a1, 0, 0x48u);
  if ( !*(_DWORD *)(a2 + 12) )
  {
LABEL_5:
    if ( *(_DWORD *)(a2 + 28) )
    {
      v6 = Heap::AllocNoThrow((Heap *)&HeapAllocator::heap, *(unsigned int *)(a2 + 28));
      *((_QWORD *)a1 + 4) = v6;
      if ( !v6 )
        goto LABEL_3;
      memcpy_0(v6, *(const void **)(a2 + 32), *(unsigned int *)(a2 + 28));
    }
    v5 = 1;
    if ( *(_QWORD *)(a2 + 40) )
    {
      v7 = Heap::AllocNoThrow((Heap *)&HeapAllocator::heap, 0x10u);
      *((_QWORD *)a1 + 5) = v7;
      if ( !v7 )
        goto LABEL_3;
      v5 = Copy<HeapAllocator>((__int64)v7, *(_DWORD **)(a2 + 40));
      if ( !v5 )
        goto LABEL_14;
    }
    if ( *(_QWORD *)(a2 + 48) )
    {
      v8 = Heap::AllocNoThrow((Heap *)&HeapAllocator::heap, 0x58u);
      *((_QWORD *)a1 + 6) = v8;
      if ( !v8 )
        goto LABEL_3;
      v5 = Copy<HeapAllocator>(v8);
      if ( !v5 )
        goto LABEL_14;
    }
    *a1 = *(_DWORD *)a2;
    a1[1] = *(_DWORD *)(a2 + 4);
    a1[2] = *(_DWORD *)(a2 + 8);
    a1[3] = *(_DWORD *)(a2 + 12);
    a1[6] = *(_DWORD *)(a2 + 24);
    a1[7] = *(_DWORD *)(a2 + 28);
    a1[16] = *(_DWORD *)(a2 + 64);
    *((_QWORD *)a1 + 7) = *(_QWORD *)(a2 + 56);
    return v5;
  }
  v4 = Heap::AllocNoThrow((Heap *)&HeapAllocator::heap, *(unsigned int *)(a2 + 12));
  *((_QWORD *)a1 + 2) = v4;
  if ( v4 )
  {
    memcpy_0(v4, *(const void **)(a2 + 16), *(unsigned int *)(a2 + 12));
    goto LABEL_5;
  }
LABEL_3:
  v5 = 0;
LABEL_14:
  Free<HeapAllocator>(a1);
  return v5;
}

```

## disassembly

```asm
0x180012518  mov     [rsp+arg_0], rbx
0x18001251d  mov     [rsp+arg_8], rsi
0x180012522  push    rdi
0x180012523  sub     rsp, 20h
0x180012527  mov     rbx, rdx
0x18001252a  mov     rsi, rcx
0x18001252d  xor     edx, edx; Val
0x18001252f  lea     r8d, [rdx+48h]; Size
0x180012533  call    memset_0
0x180012538  cmp     dword ptr [rbx+0Ch], 0
0x18001253c  jbe     short loc_18001256E
0x18001253e  mov     edx, [rbx+0Ch]; unsigned __int64
0x180012541  lea     rcx, ?heap@HeapAllocator@@0V?$StaticObject@VHeap@@@@A; this
0x180012548  call    ?AllocNoThrow@Heap@@QEAAPEAX_K@Z; Heap::AllocNoThrow(unsigned __int64)
0x18001254d  mov     [rsi+10h], rax
0x180012551  test    rax, rax
0x180012554  jnz     short loc_18001255E
0x180012556  xor     dil, dil
0x180012559  jmp     loc_18001260B
0x18001255e  mov     r8d, [rbx+0Ch]; Size
0x180012562  mov     rcx, rax; void *
0x180012565  mov     rdx, [rbx+10h]; Src
0x180012569  call    memcpy_0
0x18001256e  cmp     dword ptr [rbx+1Ch], 0
0x180012572  jbe     short loc_18001259C
0x180012574  mov     edx, [rbx+1Ch]; unsigned __int64
0x180012577  lea     rcx, ?heap@HeapAllocator@@0V?$StaticObject@VHeap@@@@A; this
0x18001257e  call    ?AllocNoThrow@Heap@@QEAAPEAX_K@Z; Heap::AllocNoThrow(unsigned __int64)
0x180012583  mov     [rsi+20h], rax
0x180012587  test    rax, rax
0x18001258a  jz      short loc_180012556
0x18001258c  mov     r8d, [rbx+1Ch]; Size
0x180012590  mov     rcx, rax; void *
0x180012593  mov     rdx, [rbx+20h]; Src
0x180012597  call    memcpy_0
0x18001259c  cmp     qword ptr [rbx+28h], 0
0x1800125a1  mov     dil, 1
0x1800125a4  jz      short loc_1800125D3
0x1800125a6  mov     edx, 10h; unsigned __int64
0x1800125ab  lea     rcx, ?heap@HeapAllocator@@0V?$StaticObject@VHeap@@@@A; this
0x1800125b2  call    ?AllocNoThrow@Heap@@QEAAPEAX_K@Z; Heap::AllocNoThrow(unsigned __int64)
0x1800125b7  mov     [rsi+28h], rax
0x1800125bb  test    rax, rax
0x1800125be  jz      short loc_180012556
0x1800125c0  mov     rdx, [rbx+28h]
0x1800125c4  mov     rcx, rax
0x1800125c7  call    ??$Copy@VHeapAllocator@@@@YA_NAEAU_EAP_ATTRIBUTES@@AEBU0@@Z; Copy<HeapAllocator>(_EAP_ATTRIBUTES &,_EAP_ATTRIBUTES const &)
0x1800125cc  mov     dil, al
0x1800125cf  test    al, al
0x1800125d1  jz      short loc_18001260B
0x1800125d3  cmp     qword ptr [rbx+30h], 0
0x1800125d8  jz      short loc_180012615
0x1800125da  mov     edx, 58h ; 'X'; unsigned __int64
0x1800125df  lea     rcx, ?heap@HeapAllocator@@0V?$StaticObject@VHeap@@@@A; this
0x1800125e6  call    ?AllocNoThrow@Heap@@QEAAPEAX_K@Z; Heap::AllocNoThrow(unsigned __int64)
0x1800125eb  mov     [rsi+30h], rax
0x1800125ef  test    rax, rax
0x1800125f2  jz      loc_180012556
0x1800125f8  mov     rdx, [rbx+30h]
0x1800125fc  mov     rcx, rax; void *
0x1800125ff  call    ??$Copy@VHeapAllocator@@@@YA_NAEAU_EAP_ERROR@@AEBU0@@Z; Copy<HeapAllocator>(_EAP_ERROR &,_EAP_ERROR const &)
0x180012604  mov     dil, al
0x180012607  test    al, al
0x180012609  jnz     short loc_180012615
0x18001260b  mov     rcx, rsi; void *
0x18001260e  call    ??$Free@VHeapAllocator@@@@YAXAEAUtagEapPeerMethodResult@@@Z; Free<HeapAllocator>(tagEapPeerMethodResult &)
0x180012613  jmp     short loc_180012645
0x180012615  mov     eax, [rbx]
0x180012617  mov     [rsi], eax
0x180012619  mov     eax, [rbx+4]
0x18001261c  mov     [rsi+4], eax
0x18001261f  mov     eax, [rbx+8]
0x180012622  mov     [rsi+8], eax
0x180012625  mov     eax, [rbx+0Ch]
0x180012628  mov     [rsi+0Ch], eax
0x18001262b  mov     eax, [rbx+18h]
0x18001262e  mov     [rsi+18h], eax
0x180012631  mov     eax, [rbx+1Ch]
0x180012634  mov     [rsi+1Ch], eax
0x180012637  mov     eax, [rbx+40h]
0x18001263a  mov     [rsi+40h], eax
0x18001263d  mov     rax, [rbx+38h]
0x180012641  mov     [rsi+38h], rax
0x180012645  mov     rbx, [rsp+28h+arg_0]
0x18001264a  mov     al, dil
0x18001264d  mov     rsi, [rsp+28h+arg_8]
0x180012652  add     rsp, 20h
0x180012656  pop     rdi
0x180012657  retn
```
