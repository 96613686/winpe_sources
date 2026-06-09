# EapTreeTraverse

- ea: `0x180001970`
- end: `0x180001c1f`
- name: `EapTreeTraverse`
- size: `687`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800017b0`
- `0x1800018a0`
- `0x180005030`
- `0x180005cc0`
- `0x1800062e0`
- `0x1800083b0`
- `0x1800085c4`
- `0x1800088d0`
- `0x180009070`
- `0x180009ad8`
- `0x180009d38`
- `0x18000ab7c`

## callees

- `0x180001970`
- `0x18000bde9`
- `0x18000c010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180001ab9`
- `ntdll!RtlFreeHeap` at `0x180001b80`
- `ntdll!RtlFreeHeap` at `0x180001ab9`
- `ntdll!RtlFreeHeap` at `0x180001b80`
- `ntdll!RtlAllocateHeap` at `0x1800019bc`
- `ntdll!RtlAllocateHeap` at `0x180001b52`
- `ntdll!RtlAllocateHeap` at `0x1800019bc`
- `ntdll!RtlAllocateHeap` at `0x180001b52`

## pseudocode

```c
__int64 __fastcall EapTreeTraverse(_QWORD *a1, __int64 a2)
{
  _QWORD *Heap; // rax
  _QWORD *v5; // rsi
  unsigned __int16 v6; // di
  unsigned __int16 v7; // r13
  char i; // cl
  __int64 (__fastcall *v9)(_QWORD, _QWORD, _QWORD); // rax
  __int64 v10; // r15
  int v11; // ebp
  __int64 (__fastcall *v12)(_QWORD, _QWORD, _QWORD); // rax
  __int64 (__fastcall *v13)(_QWORD, _QWORD); // rax
  __int64 v15; // r14
  _QWORD *v16; // rax
  _QWORD *v17; // r12
  __int64 v18; // [rsp+60h] [rbp+8h] BYREF

  v18 = 0;
  if ( !a1 || !a1[1] )
    return 3221225485LL;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x50u);
  v5 = Heap;
  if ( !Heap )
    return 3221225495LL;
  *Heap = a2;
  v6 = 1;
  v7 = 5;
  *((_DWORD *)Heap + 2) = 0;
  while ( 1 )
  {
    for ( i = 0; ; i = 1 )
    {
      if ( !v6 )
      {
        v11 = 0;
        goto LABEL_15;
      }
      v9 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))a1[3];
      if ( v9 )
      {
        if ( !i )
        {
          v11 = v9(*a1, v5[2 * v6 - 2], LOWORD(v5[2 * v6 - 1]));
          if ( v11 < 0 )
            goto LABEL_15;
        }
      }
      v10 = 2LL * v6;
      v11 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, __int64 *))a1[1])(
              *a1,
              v5[v10 - 2],
              WORD1(v5[v10 - 1]),
              &v18);
      if ( v11 < 0 )
        goto LABEL_15;
      if ( v18 )
        break;
      v12 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))a1[4];
      if ( v12 )
      {
        v11 = v12(*a1, v5[v10 - 2], LOWORD(v5[v10 - 1]));
        if ( v11 < 0 )
          goto LABEL_15;
      }
      v13 = (__int64 (__fastcall *)(_QWORD, _QWORD))a1[2];
      if ( v13 )
      {
        if ( v6 > 1u )
        {
          v11 = v13(*a1, v5[v10 - 2]);
          if ( v11 < 0 )
            goto LABEL_15;
        }
      }
      --v6;
    }
    if ( v6 == v7 )
      break;
LABEL_21:
    ++WORD1(v5[v10 - 1]);
    v15 = 2LL * v6;
    v5[v15] = v18;
    LOWORD(v5[v15 + 1]) = LOWORD(v5[v10 - 1]) + 1;
    WORD1(v5[v15 + 1]) = 0;
    ++v6;
  }
  v16 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 16LL * v7 + 80);
  v17 = v16;
  if ( v16 )
  {
    memcpy_0(v16, v5, 16LL * v7);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
    v5 = v17;
    v7 += 5;
    goto LABEL_21;
  }
  v11 = -1073741801;
LABEL_15:
  if ( v5 )
  {
    if ( a1[2] && v6 > 1u )
    {
      do
        ((void (__fastcall *)(_QWORD, _QWORD))a1[2])(*a1, v5[2 * v6-- - 2]);
      while ( v6 > 1u );
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180001970  push    rbx
0x180001972  push    rdi
0x180001973  sub     rsp, 48h
0x180001977  mov     [rsp+58h+arg_0], 0
0x180001980  mov     rdi, rdx
0x180001983  mov     rbx, rcx
0x180001986  test    rcx, rcx
0x180001989  jz      loc_180001BC9
0x18000198f  cmp     qword ptr [rcx+8], 0
0x180001994  jz      loc_180001BC9
0x18000199a  mov     rcx, gs:60h
0x1800019a3  mov     edx, 8; Flags
0x1800019a8  mov     [rsp+58h+arg_10], rsi
0x1800019ad  mov     r8d, 50h ; 'P'; Size
0x1800019b3  mov     [rsp+58h+arg_8], rbp
0x1800019b8  mov     rcx, [rcx+30h]; HeapHandle
0x1800019bc  call    cs:__imp_RtlAllocateHeap
0x1800019c2  mov     rsi, rax
0x1800019c5  test    rax, rax
0x1800019c8  jz      loc_180001BE5
0x1800019ce  mov     [rsp+58h+arg_18], r12
0x1800019d3  mov     r12d, 0FFFFh
0x1800019d9  mov     [rax], rdi
0x1800019dc  xor     eax, eax
0x1800019de  mov     [rsp+58h+var_18], r13
0x1800019e3  mov     edi, 1
0x1800019e8  mov     [rsp+58h+var_20], r14
0x1800019ed  mov     r13d, 5
0x1800019f3  mov     [rsi+8], eax
0x1800019f6  mov     [rsp+58h+var_28], r15
0x1800019fb  xor     cl, cl
0x1800019fd  test    di, di
0x180001a00  jz      loc_180001A86
0x180001a06  mov     rax, [rbx+18h]
0x180001a0a  test    rax, rax
0x180001a0d  jnz     loc_180001B99
0x180001a13  mov     rcx, [rbx]
0x180001a16  lea     r9, [rsp+58h+arg_0]
0x180001a1b  mov     rax, [rbx+8]
0x180001a1f  movzx   r14d, di
0x180001a23  mov     r15d, r14d
0x180001a26  shl     r15, 4
0x180001a2a  movzx   r8d, word ptr [r15+rsi-6]
0x180001a30  mov     rdx, [r15+rsi-10h]
0x180001a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a3a  mov     ebp, eax
0x180001a3c  test    eax, eax
0x180001a3e  js      short loc_180001A88
0x180001a40  cmp     [rsp+58h+arg_0], 0
0x180001a46  jnz     loc_180001AD7
0x180001a4c  mov     rax, [rbx+20h]
0x180001a50  test    rax, rax
0x180001a53  jz      short loc_180001A6E
0x180001a55  movzx   r8d, word ptr [r15+rsi-8]
0x180001a5b  mov     rdx, [r15+rsi-10h]
0x180001a60  mov     rcx, [rbx]
0x180001a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a68  mov     ebp, eax
0x180001a6a  test    eax, eax
0x180001a6c  js      short loc_180001A88
0x180001a6e  mov     rax, [rbx+10h]
0x180001a72  test    rax, rax
0x180001a75  jnz     loc_180001B0E
0x180001a7b  add     di, r12w
0x180001a7f  mov     cl, 1
0x180001a81  jmp     loc_1800019FD
0x180001a86  xor     ebp, ebp
0x180001a88  mov     r15, [rsp+58h+var_28]
0x180001a8d  mov     r14, [rsp+58h+var_20]
0x180001a92  mov     r13, [rsp+58h+var_18]
0x180001a97  test    rsi, rsi
0x180001a9a  jz      short loc_180001ABF
0x180001a9c  cmp     qword ptr [rbx+10h], 0
0x180001aa1  jnz     loc_180001BEF
0x180001aa7  mov     rcx, gs:60h
0x180001ab0  mov     r8, rsi; P
0x180001ab3  xor     edx, edx; Flags
0x180001ab5  mov     rcx, [rcx+30h]; HeapHandle
0x180001ab9  call    cs:__imp_RtlFreeHeap
0x180001abf  mov     r12, [rsp+58h+arg_18]
0x180001ac4  mov     eax, ebp
0x180001ac6  mov     rbp, [rsp+58h+arg_8]
0x180001acb  mov     rsi, [rsp+58h+arg_10]
0x180001ad0  add     rsp, 48h
0x180001ad4  pop     rdi
0x180001ad5  pop     rbx
0x180001ad6  retn
0x180001ad7  cmp     di, r13w
0x180001adb  jz      short loc_180001B34
0x180001add  inc     word ptr [r15+rsi-6]
0x180001ae3  add     r14, r14
0x180001ae6  mov     rax, [rsp+58h+arg_0]
0x180001aeb  mov     [rsi+r14*8], rax
0x180001aef  movzx   eax, word ptr [r15+rsi-8]
0x180001af5  inc     ax
0x180001af8  mov     [rsi+r14*8+8], ax
0x180001afe  xor     eax, eax
0x180001b00  mov     [rsi+r14*8+0Ah], ax
0x180001b06  inc     di
0x180001b09  jmp     loc_1800019FB
0x180001b0e  cmp     di, 1
0x180001b12  jbe     loc_180001A7B
0x180001b18  mov     rdx, [r15+rsi-10h]
0x180001b1d  mov     rcx, [rbx]
0x180001b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b25  mov     ebp, eax
0x180001b27  test    eax, eax
0x180001b29  jns     loc_180001A7B
0x180001b2f  jmp     loc_180001A88
0x180001b34  mov     rcx, gs:60h
0x180001b3d  mov     edx, 8; Flags
0x180001b42  movzx   ebp, r13w
0x180001b46  shl     rbp, 4
0x180001b4a  mov     rcx, [rcx+30h]; HeapHandle
0x180001b4e  lea     r8, [rbp+50h]; Size
0x180001b52  call    cs:__imp_RtlAllocateHeap
0x180001b58  mov     r12, rax
0x180001b5b  test    rax, rax
0x180001b5e  jz      short loc_180001BD5
0x180001b60  mov     r8, rbp; Size
0x180001b63  mov     rdx, rsi; Src
0x180001b66  mov     rcx, rax; void *
0x180001b69  call    memcpy_0
0x180001b6e  mov     rcx, gs:60h
0x180001b77  mov     r8, rsi; P
0x180001b7a  xor     edx, edx; Flags
0x180001b7c  mov     rcx, [rcx+30h]; HeapHandle
0x180001b80  call    cs:__imp_RtlFreeHeap
0x180001b86  mov     rsi, r12
0x180001b89  add     r13w, 5
0x180001b8e  mov     r12d, 0FFFFh
0x180001b94  jmp     loc_180001ADD
0x180001b99  test    cl, cl
0x180001b9b  jnz     loc_180001A13
0x180001ba1  movzx   ecx, di
0x180001ba4  add     rcx, rcx
0x180001ba7  movzx   r8d, word ptr [rsi+rcx*8-8]
0x180001bad  mov     rdx, [rsi+rcx*8-10h]
0x180001bb2  mov     rcx, [rbx]
0x180001bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bba  mov     ebp, eax
0x180001bbc  test    eax, eax
0x180001bbe  jns     loc_180001A13
0x180001bc4  jmp     loc_180001A88
0x180001bc9  mov     eax, 0C000000Dh
0x180001bce  add     rsp, 48h
0x180001bd2  pop     rdi
0x180001bd3  pop     rbx
0x180001bd4  retn
0x180001bd5  mov     ebp, 0C0000017h
0x180001bda  mov     r12d, 0FFFFh
0x180001be0  jmp     loc_180001A88
0x180001be5  mov     eax, 0C0000017h
0x180001bea  jmp     loc_180001AC6
0x180001bef  cmp     di, 1
0x180001bf3  jbe     loc_180001AA7
0x180001bf9  mov     rcx, [rbx]
0x180001bfc  mov     rax, [rbx+10h]
0x180001c00  movzx   edx, di
0x180001c03  add     rdx, rdx
0x180001c06  mov     rdx, [rsi+rdx*8-10h]
0x180001c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c10  add     di, r12w
0x180001c14  cmp     di, 1
0x180001c18  ja      short loc_180001BF9
0x180001c1a  jmp     loc_180001AA7
```
