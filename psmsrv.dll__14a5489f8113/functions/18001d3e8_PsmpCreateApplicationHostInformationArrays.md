# PsmpCreateApplicationHostInformationArrays

- ea: `0x18001d3e8`
- end: `0x18001d67f`
- name: `PsmpCreateApplicationHostInformationArrays`
- size: `663`
- prototype: `__int64 __fastcall(_QWORD *, char, _QWORD *, _QWORD *, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001d840`

## callees

- `0x18001d3e8`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18001d51a`
- `ntdll!RtlFreeHeap` at `0x18001d53b`
- `ntdll!RtlFreeHeap` at `0x18001d51a`
- `ntdll!RtlFreeHeap` at `0x18001d53b`
- `ntdll!RtlAllocateHeap` at `0x18001d488`
- `ntdll!RtlAllocateHeap` at `0x18001d4c0`
- `ntdll!RtlAllocateHeap` at `0x18001d4f0`
- `ntdll!RtlAllocateHeap` at `0x18001d488`
- `ntdll!RtlAllocateHeap` at `0x18001d4c0`
- `ntdll!RtlAllocateHeap` at `0x18001d4f0`

## pseudocode

```c
__int64 __fastcall PsmpCreateApplicationHostInformationArrays(
        _QWORD *a1,
        char a2,
        _QWORD *a3,
        _QWORD *a4,
        _QWORD *a5,
        _DWORD *a6)
{
  __int64 v6; // rbp
  int v8; // r12d
  int v9; // r13d
  _QWORD **v10; // rcx
  _QWORD *v11; // rax
  unsigned int v12; // ebx
  _QWORD *v13; // rdi
  _DWORD *Heap; // rsi
  _QWORD *v15; // r9
  unsigned int v16; // edx
  _QWORD **v17; // rbx
  _QWORD *v18; // rcx
  int v20; // [rsp+68h] [rbp+10h]

  v6 = 0;
  v8 = a2 & 2;
  if ( (a2 & 2) != 0 )
    v6 = a1[850] != -1;
  v20 = a2 & 8;
  if ( (a2 & 8) != 0 && a1[851] != -1 )
    v6 = (unsigned int)(v6 + 1);
  v9 = a2 & 4;
  if ( (a2 & 4) != 0 )
  {
    v10 = (_QWORD **)(a1 + 852);
    v11 = *v10;
    while ( v11 != v10 )
    {
      v11 = (_QWORD *)*v11;
      v6 = (unsigned int)(v6 + 1);
    }
  }
  if ( (_DWORD)v6 )
  {
    v13 = 0;
    if ( !a4 || (v13 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 8 * v6)) != 0 )
    {
      Heap = 0;
      if ( (!a3 || (Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 4 * v6)) != 0)
        && ((v15 = 0, !a5) || (v15 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 8 * v6)) != 0) )
      {
        v16 = 0;
        if ( v8 && a1[850] != -1 )
        {
          if ( Heap )
            *Heap = 2;
          if ( v13 )
            *v13 = a1[850];
          if ( v15 )
            *v15 = a1[24];
          v16 = 1;
        }
        if ( v20 && a1[851] != -1 )
        {
          if ( Heap )
            Heap[v16] = 8;
          if ( v13 )
            v13[v16] = a1[851];
          if ( v15 )
            v15[v16] = a1[25];
          ++v16;
        }
        if ( v9 )
        {
          v17 = (_QWORD **)(a1 + 852);
          v18 = *v17;
          if ( Heap )
          {
            while ( v18 != v17 )
            {
              Heap[v16] = 4;
              if ( v13 )
                v13[v16] = *(v18 - 2);
              if ( v15 )
                v15[v16] = *(v18 - 1);
              v18 = (_QWORD *)*v18;
              ++v16;
            }
          }
          else
          {
            while ( v18 != v17 )
            {
              if ( v13 )
                v13[v16] = *(v18 - 2);
              if ( v15 )
                v15[v16] = *(v18 - 1);
              v18 = (_QWORD *)*v18;
              ++v16;
            }
          }
        }
        if ( a3 )
          *a3 = Heap;
        if ( a4 )
          *a4 = v13;
        if ( a5 )
          *a5 = v15;
        v12 = 0;
        *a6 = v6;
      }
      else
      {
        v12 = -1073741670;
        if ( v13 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
        if ( Heap )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      }
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  else
  {
    return (unsigned int)-2147483622;
  }
  return v12;
}

```

## disassembly

```asm
0x18001d3e8  mov     [rsp+arg_0], rbx
0x18001d3ed  mov     [rsp+arg_18], r9
0x18001d3f2  mov     [rsp+arg_10], r8
0x18001d3f7  push    rbp
0x18001d3f8  push    rsi
0x18001d3f9  push    rdi
0x18001d3fa  push    r12
0x18001d3fc  push    r13
0x18001d3fe  push    r14
0x18001d400  push    r15
0x18001d402  sub     rsp, 20h
0x18001d406  xor     ebp, ebp
0x18001d408  mov     r12d, edx
0x18001d40b  mov     r13d, edx
0x18001d40e  mov     rbx, rcx
0x18001d411  lea     edx, [rbp+1]
0x18001d414  and     r12d, 2
0x18001d418  jz      short loc_18001D425
0x18001d41a  cmp     qword ptr [rcx+1A90h], 0FFFFFFFFFFFFFFFFh
0x18001d422  cmovnz  ebp, edx
0x18001d425  mov     eax, r13d
0x18001d428  and     eax, 8
0x18001d42b  mov     [rsp+58h+arg_8], eax
0x18001d42f  jz      short loc_18001D43D
0x18001d431  cmp     qword ptr [rcx+1A98h], 0FFFFFFFFFFFFFFFFh
0x18001d439  jz      short loc_18001D43D
0x18001d43b  add     ebp, edx
0x18001d43d  and     r13d, 4
0x18001d441  jz      short loc_18001D459
0x18001d443  add     rcx, 1AA0h
0x18001d44a  mov     rax, [rcx]
0x18001d44d  jmp     short loc_18001D454
0x18001d44f  mov     rax, [rax]
0x18001d452  add     ebp, edx
0x18001d454  cmp     rax, rcx
0x18001d457  jnz     short loc_18001D44F
0x18001d459  test    ebp, ebp
0x18001d45b  jnz     short loc_18001D467
0x18001d45d  mov     ebx, 8000001Ah
0x18001d462  jmp     loc_18001D668
0x18001d467  xor     edi, edi
0x18001d469  lea     r15, ds:0[rbp*8]
0x18001d471  test    r9, r9
0x18001d474  jz      short loc_18001D4A0
0x18001d476  mov     rcx, gs:60h
0x18001d47f  mov     r8, r15; Size
0x18001d482  xor     edx, edx; Flags
0x18001d484  mov     rcx, [rcx+30h]; HeapHandle
0x18001d488  call    cs:__imp_RtlAllocateHeap
0x18001d48e  mov     rdi, rax
0x18001d491  test    rax, rax
0x18001d494  jnz     short loc_18001D4A0
0x18001d496  mov     ebx, 0C000009Ah
0x18001d49b  jmp     loc_18001D668
0x18001d4a0  xor     esi, esi
0x18001d4a2  cmp     [rsp+58h+arg_10], rsi
0x18001d4a7  jz      short loc_18001D4CE
0x18001d4a9  mov     rcx, gs:60h
0x18001d4b2  lea     r8, ds:0[rbp*4]; Size
0x18001d4ba  xor     edx, edx; Flags
0x18001d4bc  mov     rcx, [rcx+30h]; HeapHandle
0x18001d4c0  call    cs:__imp_RtlAllocateHeap
0x18001d4c6  mov     rsi, rax
0x18001d4c9  test    rax, rax
0x18001d4cc  jz      short loc_18001D4FE
0x18001d4ce  mov     r14, [rsp+58h+arg_20]
0x18001d4d6  xor     r9d, r9d
0x18001d4d9  test    r14, r14
0x18001d4dc  jz      short loc_18001D546
0x18001d4de  mov     rcx, gs:60h
0x18001d4e7  mov     r8, r15; Size
0x18001d4ea  xor     edx, edx; Flags
0x18001d4ec  mov     rcx, [rcx+30h]; HeapHandle
0x18001d4f0  call    cs:__imp_RtlAllocateHeap
0x18001d4f6  mov     r9, rax
0x18001d4f9  test    rax, rax
0x18001d4fc  jnz     short loc_18001D546
0x18001d4fe  mov     ebx, 0C000009Ah
0x18001d503  test    rdi, rdi
0x18001d506  jz      short loc_18001D520
0x18001d508  mov     rcx, gs:60h
0x18001d511  mov     r8, rdi; P
0x18001d514  xor     edx, edx; Flags
0x18001d516  mov     rcx, [rcx+30h]; HeapHandle
0x18001d51a  call    cs:__imp_RtlFreeHeap
0x18001d520  test    rsi, rsi
0x18001d523  jz      loc_18001D668
0x18001d529  mov     rcx, gs:60h
0x18001d532  mov     r8, rsi; P
0x18001d535  xor     edx, edx; Flags
0x18001d537  mov     rcx, [rcx+30h]; HeapHandle
0x18001d53b  call    cs:__imp_RtlFreeHeap
0x18001d541  jmp     loc_18001D668
0x18001d546  xor     edx, edx
0x18001d548  test    r12d, r12d
0x18001d54b  jz      short loc_18001D585
0x18001d54d  cmp     qword ptr [rbx+1A90h], 0FFFFFFFFFFFFFFFFh
0x18001d555  jz      short loc_18001D585
0x18001d557  test    rsi, rsi
0x18001d55a  jz      short loc_18001D562
0x18001d55c  mov     dword ptr [rsi], 2
0x18001d562  test    rdi, rdi
0x18001d565  jz      short loc_18001D571
0x18001d567  mov     rax, [rbx+1A90h]
0x18001d56e  mov     [rdi], rax
0x18001d571  test    r9, r9
0x18001d574  jz      short loc_18001D580
0x18001d576  mov     rax, [rbx+0C0h]
0x18001d57d  mov     [r9], rax
0x18001d580  mov     edx, 1
0x18001d585  cmp     [rsp+58h+arg_8], 0
0x18001d58a  jz      short loc_18001D5C6
0x18001d58c  cmp     qword ptr [rbx+1A98h], 0FFFFFFFFFFFFFFFFh
0x18001d594  jz      short loc_18001D5C6
0x18001d596  mov     ecx, edx
0x18001d598  test    rsi, rsi
0x18001d59b  jz      short loc_18001D5A4
0x18001d59d  mov     dword ptr [rsi+rcx*4], 8
0x18001d5a4  test    rdi, rdi
0x18001d5a7  jz      short loc_18001D5B4
0x18001d5a9  mov     rax, [rbx+1A98h]
0x18001d5b0  mov     [rdi+rcx*8], rax
0x18001d5b4  test    r9, r9
0x18001d5b7  jz      short loc_18001D5C4
0x18001d5b9  mov     rax, [rbx+0C8h]
0x18001d5c0  mov     [r9+rcx*8], rax
0x18001d5c4  inc     edx
0x18001d5c6  test    r13d, r13d
0x18001d5c9  jz      short loc_18001D63A
0x18001d5cb  add     rbx, 1AA0h
0x18001d5d2  mov     rcx, [rbx]
0x18001d5d5  test    rsi, rsi
0x18001d5d8  jnz     short loc_18001D635
0x18001d5da  jmp     short loc_18001D5FE
0x18001d5dc  mov     r8d, edx
0x18001d5df  test    rdi, rdi
0x18001d5e2  jz      short loc_18001D5EC
0x18001d5e4  mov     rax, [rcx-10h]
0x18001d5e8  mov     [rdi+r8*8], rax
0x18001d5ec  test    r9, r9
0x18001d5ef  jz      short loc_18001D5F9
0x18001d5f1  mov     rax, [rcx-8]
0x18001d5f5  mov     [r9+r8*8], rax
0x18001d5f9  mov     rcx, [rcx]
0x18001d5fc  inc     edx
0x18001d5fe  cmp     rcx, rbx
0x18001d601  jnz     short loc_18001D5DC
0x18001d603  jmp     short loc_18001D63A
0x18001d605  mov     eax, edx
0x18001d607  mov     dword ptr [rsi+rax*4], 4
0x18001d60e  lea     r8, ds:0[rax*8]
0x18001d616  test    rdi, rdi
0x18001d619  jz      short loc_18001D623
0x18001d61b  mov     rax, [rcx-10h]
0x18001d61f  mov     [r8+rdi], rax
0x18001d623  test    r9, r9
0x18001d626  jz      short loc_18001D630
0x18001d628  mov     rax, [rcx-8]
0x18001d62c  mov     [r9+r8], rax
0x18001d630  mov     rcx, [rcx]
0x18001d633  inc     edx
0x18001d635  cmp     rcx, rbx
0x18001d638  jnz     short loc_18001D605
0x18001d63a  mov     rax, [rsp+58h+arg_10]
0x18001d63f  test    rax, rax
0x18001d642  jz      short loc_18001D647
0x18001d644  mov     [rax], rsi
0x18001d647  mov     rax, [rsp+58h+arg_18]
0x18001d64c  test    rax, rax
0x18001d64f  jz      short loc_18001D654
0x18001d651  mov     [rax], rdi
0x18001d654  test    r14, r14
0x18001d657  jz      short loc_18001D65C
0x18001d659  mov     [r14], r9
0x18001d65c  mov     rax, [rsp+58h+arg_28]
0x18001d664  xor     ebx, ebx
0x18001d666  mov     [rax], ebp
0x18001d668  mov     eax, ebx
0x18001d66a  mov     rbx, [rsp+58h+arg_0]
0x18001d66f  add     rsp, 20h
0x18001d673  pop     r15
0x18001d675  pop     r14
0x18001d677  pop     r13
0x18001d679  pop     r12
0x18001d67b  pop     rdi
0x18001d67c  pop     rsi
0x18001d67d  pop     rbp
0x18001d67e  retn
```
