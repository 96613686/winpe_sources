# Copy<HeapAllocator>(tagEapPeerMethodResult &,tagEapPeerMethodResult const &)

- ea: `0x180011da0`
- end: `0x180011ee0`
- name: `??$Copy@VHeapAllocator@@@@YA_NAEAUtagEapPeerMethodResult@@AEBU0@@Z`
- size: `320`
- prototype: `char __fastcall(_DWORD *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800122ec`

## callees

- `0x18000343c`
- `0x180011af4`
- `0x180011cf4`
- `0x180011da0`
- `0x180011f8c`
- `0x18002f7ec`
- `0x180033d78`

## pseudocode

```c
char __fastcall Copy<HeapAllocator>(_DWORD *a1, __int64 a2)
{
  void *v4; // rax
  char v5; // di
  void *v6; // rax
  void *v7; // rax
  _OWORD *v8; // rax

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
      v5 = Copy<HeapAllocator>(v8, *(_QWORD *)(a2 + 48));
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
0x180011da0  mov     [rsp+arg_0], rbx
0x180011da5  mov     [rsp+arg_8], rsi
0x180011daa  push    rdi
0x180011dab  sub     rsp, 20h
0x180011daf  mov     rbx, rdx
0x180011db2  mov     rsi, rcx
0x180011db5  xor     edx, edx; Val
0x180011db7  lea     r8d, [rdx+48h]; Size
0x180011dbb  call    memset_0
0x180011dc0  cmp     dword ptr [rbx+0Ch], 0
0x180011dc4  jbe     short loc_180011DF6
0x180011dc6  mov     edx, [rbx+0Ch]; unsigned __int64
0x180011dc9  lea     rcx, ?heap@HeapAllocator@@0V?$StaticObject@VHeap@@@@A; this
0x180011dd0  call    ?AllocNoThrow@Heap@@QEAAPEAX_K@Z; Heap::AllocNoThrow(unsigned __int64)
0x180011dd5  mov     [rsi+10h], rax
0x180011dd9  test    rax, rax
0x180011ddc  jnz     short loc_180011DE6
0x180011dde  xor     dil, dil
0x180011de1  jmp     loc_180011E93
0x180011de6  mov     r8d, [rbx+0Ch]; Size
0x180011dea  mov     rcx, rax; void *
0x180011ded  mov     rdx, [rbx+10h]; Src
0x180011df1  call    memcpy_0
0x180011df6  cmp     dword ptr [rbx+1Ch], 0
0x180011dfa  jbe     short loc_180011E24
0x180011dfc  mov     edx, [rbx+1Ch]; unsigned __int64
0x180011dff  lea     rcx, ?heap@HeapAllocator@@0V?$StaticObject@VHeap@@@@A; this
0x180011e06  call    ?AllocNoThrow@Heap@@QEAAPEAX_K@Z; Heap::AllocNoThrow(unsigned __int64)
0x180011e0b  mov     [rsi+20h], rax
0x180011e0f  test    rax, rax
0x180011e12  jz      short loc_180011DDE
0x180011e14  mov     r8d, [rbx+1Ch]; Size
0x180011e18  mov     rcx, rax; void *
0x180011e1b  mov     rdx, [rbx+20h]; Src
0x180011e1f  call    memcpy_0
0x180011e24  cmp     qword ptr [rbx+28h], 0
0x180011e29  mov     dil, 1
0x180011e2c  jz      short loc_180011E5B
0x180011e2e  mov     edx, 10h; unsigned __int64
0x180011e33  lea     rcx, ?heap@HeapAllocator@@0V?$StaticObject@VHeap@@@@A; this
0x180011e3a  call    ?AllocNoThrow@Heap@@QEAAPEAX_K@Z; Heap::AllocNoThrow(unsigned __int64)
0x180011e3f  mov     [rsi+28h], rax
0x180011e43  test    rax, rax
0x180011e46  jz      short loc_180011DDE
0x180011e48  mov     rdx, [rbx+28h]
0x180011e4c  mov     rcx, rax
0x180011e4f  call    ??$Copy@VHeapAllocator@@@@YA_NAEAU_EAP_ATTRIBUTES@@AEBU0@@Z; Copy<HeapAllocator>(_EAP_ATTRIBUTES &,_EAP_ATTRIBUTES const &)
0x180011e54  mov     dil, al
0x180011e57  test    al, al
0x180011e59  jz      short loc_180011E93
0x180011e5b  cmp     qword ptr [rbx+30h], 0
0x180011e60  jz      short loc_180011E9D
0x180011e62  mov     edx, 58h ; 'X'; unsigned __int64
0x180011e67  lea     rcx, ?heap@HeapAllocator@@0V?$StaticObject@VHeap@@@@A; this
0x180011e6e  call    ?AllocNoThrow@Heap@@QEAAPEAX_K@Z; Heap::AllocNoThrow(unsigned __int64)
0x180011e73  mov     [rsi+30h], rax
0x180011e77  test    rax, rax
0x180011e7a  jz      loc_180011DDE
0x180011e80  mov     rdx, [rbx+30h]
0x180011e84  mov     rcx, rax; void *
0x180011e87  call    ??$Copy@VHeapAllocator@@@@YA_NAEAU_EAP_ERROR@@AEBU0@@Z; Copy<HeapAllocator>(_EAP_ERROR &,_EAP_ERROR const &)
0x180011e8c  mov     dil, al
0x180011e8f  test    al, al
0x180011e91  jnz     short loc_180011E9D
0x180011e93  mov     rcx, rsi; void *
0x180011e96  call    ??$Free@VHeapAllocator@@@@YAXAEAUtagEapPeerMethodResult@@@Z; Free<HeapAllocator>(tagEapPeerMethodResult &)
0x180011e9b  jmp     short loc_180011ECD
0x180011e9d  mov     eax, [rbx]
0x180011e9f  mov     [rsi], eax
0x180011ea1  mov     eax, [rbx+4]
0x180011ea4  mov     [rsi+4], eax
0x180011ea7  mov     eax, [rbx+8]
0x180011eaa  mov     [rsi+8], eax
0x180011ead  mov     eax, [rbx+0Ch]
0x180011eb0  mov     [rsi+0Ch], eax
0x180011eb3  mov     eax, [rbx+18h]
0x180011eb6  mov     [rsi+18h], eax
0x180011eb9  mov     eax, [rbx+1Ch]
0x180011ebc  mov     [rsi+1Ch], eax
0x180011ebf  mov     eax, [rbx+40h]
0x180011ec2  mov     [rsi+40h], eax
0x180011ec5  mov     rax, [rbx+38h]
0x180011ec9  mov     [rsi+38h], rax
0x180011ecd  mov     rbx, [rsp+28h+arg_0]
0x180011ed2  mov     al, dil
0x180011ed5  mov     rsi, [rsp+28h+arg_8]
0x180011eda  add     rsp, 20h
0x180011ede  pop     rdi
0x180011edf  retn
```
