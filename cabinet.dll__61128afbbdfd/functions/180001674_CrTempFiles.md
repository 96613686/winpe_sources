# CrTempFiles

- ea: `0x180001674`
- end: `0x1800017f2`
- name: `CrTempFiles`
- size: `382`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000137c`
- `0x180001518`
- `0x180001bd8`
- `0x1800039b8`

## callees

- `0x180001674`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall CrTempFiles(
        __int64 a1,
        int a2,
        __int64 (__fastcall *a3)(__int64, __int64, __int64, int *, __int64),
        void (__fastcall *a4)(__int64, int *, __int64),
        void (__fastcall *a5)(__int64, int *, __int64),
        unsigned int (__fastcall *a6)(__int64, __int64, __int64),
        _DWORD *a7,
        __int64 a8)
{
  int i; // ecx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r15
  int v15; // edi
  int v16; // r14d
  __int64 v17; // rbp
  _DWORD *v18; // rcx
  int v19; // eax
  int v20; // edi
  void (__fastcall *v21)(__int64, int *, __int64); // r14
  __int64 v22; // rbp
  __int64 v23; // rcx
  int v25; // [rsp+78h] [rbp+10h] BYREF
  void (__fastcall *v26)(__int64, int *, __int64); // [rsp+88h] [rbp+20h]

  v26 = a4;
  v25 = 0;
  for ( i = 0; i < a2; *(_DWORD *)(v13 + a1) = 0 )
  {
    v12 = (unsigned int)i++;
    v13 = 272 * v12;
    *(_QWORD *)(v13 + a1 + 8) = -1;
  }
  v14 = a8;
  v15 = 0;
LABEL_4:
  if ( v15 >= a2 )
    return 1;
  v16 = 101;
  v17 = 272LL * v15;
  while ( 1 )
  {
    if ( *(_QWORD *)(a1 + v17 + 8) != -1 )
    {
      ++v15;
      goto LABEL_4;
    }
    if ( !v16 )
      break;
    --v16;
    if ( a6(a1 + v17 + 16, 256, v14) )
    {
      v25 = 0;
      *(_QWORD *)(a1 + v17 + 8) = a3(a1 + v17 + 16, 34050, 384, &v25, v14);
    }
  }
  v18 = a7;
  v19 = v25;
  *a7 = 4;
  v18[1] = v19;
  v18[2] = 1;
  v20 = 0;
  if ( a2 > 0 )
  {
    v21 = v26;
    do
    {
      v22 = 272LL * (unsigned int)v20;
      v23 = *(_QWORD *)(a1 + v22 + 8);
      if ( v23 != -1 )
      {
        v25 = 0;
        v21(v23, &v25, v14);
        v25 = 0;
        a5(v22 + a1 + 16, &v25, v14);
        *(_QWORD *)(a1 + v22 + 8) = -1;
      }
      ++v20;
    }
    while ( v20 < a2 );
  }
  return 0;
}

```

## disassembly

```asm
0x180001674  mov     [rsp+arg_0], rbx
0x180001679  mov     [rsp+arg_18], r9
0x18000167e  push    rbp
0x18000167f  push    rsi
0x180001680  push    rdi
0x180001681  push    r12
0x180001683  push    r13
0x180001685  push    r14
0x180001687  push    r15
0x180001689  sub     rsp, 30h
0x18000168d  mov     rbx, rcx
0x180001690  mov     [rsp+68h+arg_8], 0
0x180001698  xor     ecx, ecx
0x18000169a  mov     r13, r8
0x18000169d  mov     esi, edx
0x18000169f  test    edx, edx
0x1800016a1  jle     short loc_1800016C2
0x1800016a3  mov     eax, ecx
0x1800016a5  inc     ecx
0x1800016a7  imul    rdx, rax, 110h
0x1800016ae  mov     qword ptr [rdx+rbx+8], 0FFFFFFFFFFFFFFFFh
0x1800016b7  mov     dword ptr [rdx+rbx], 0
0x1800016be  cmp     ecx, esi
0x1800016c0  jl      short loc_1800016A3
0x1800016c2  mov     r15, [rsp+68h+arg_38]
0x1800016ca  xor     edi, edi
0x1800016cc  cmp     edi, esi
0x1800016ce  jge     loc_1800017D8
0x1800016d4  movsxd  rax, edi
0x1800016d7  mov     r14d, 65h ; 'e'
0x1800016dd  imul    rbp, rax, 110h
0x1800016e4  jmp     short loc_18000173F
0x1800016e6  test    r14d, r14d
0x1800016e9  jz      short loc_18000174B
0x1800016eb  mov     rax, [rsp+68h+arg_28]
0x1800016f3  lea     r12, [rbx+rbp]
0x1800016f7  lea     rcx, [r12+10h]
0x1800016fc  mov     r8, r15
0x1800016ff  mov     edx, 100h
0x180001704  dec     r14d
0x180001707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000170c  test    eax, eax
0x18000170e  jz      short loc_18000173F
0x180001710  lea     r9, [rsp+68h+arg_8]
0x180001715  mov     [rsp+68h+arg_8], 0
0x18000171d  mov     edx, 8502h
0x180001722  mov     [rsp+68h+var_48], r15
0x180001727  mov     r8d, 180h
0x18000172d  lea     rcx, [r12+10h]
0x180001732  mov     rax, r13
0x180001735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000173a  mov     [rbx+rbp+8], rax
0x18000173f  cmp     qword ptr [rbx+rbp+8], 0FFFFFFFFFFFFFFFFh
0x180001745  jz      short loc_1800016E6
0x180001747  inc     edi
0x180001749  jmp     short loc_1800016CC
0x18000174b  mov     rcx, [rsp+68h+arg_30]
0x180001753  mov     eax, [rsp+68h+arg_8]
0x180001757  mov     dword ptr [rcx], 4
0x18000175d  mov     [rcx+4], eax
0x180001760  mov     dword ptr [rcx+8], 1
0x180001767  xor     edi, edi
0x180001769  test    esi, esi
0x18000176b  jle     short loc_1800017D4
0x18000176d  mov     r14, [rsp+68h+arg_18]
0x180001775  mov     eax, edi
0x180001777  imul    rbp, rax, 110h
0x18000177e  mov     rcx, [rbx+rbp+8]
0x180001783  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180001787  jz      short loc_1800017CE
0x180001789  mov     r8, r15
0x18000178c  mov     [rsp+68h+arg_8], 0
0x180001794  lea     rdx, [rsp+68h+arg_8]
0x180001799  mov     rax, r14
0x18000179c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017a1  mov     rax, [rsp+68h+arg_20]
0x1800017a9  lea     rcx, [rbx+10h]
0x1800017ad  add     rcx, rbp
0x1800017b0  mov     [rsp+68h+arg_8], 0
0x1800017b8  mov     r8, r15
0x1800017bb  lea     rdx, [rsp+68h+arg_8]
0x1800017c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017c5  mov     qword ptr [rbx+rbp+8], 0FFFFFFFFFFFFFFFFh
0x1800017ce  inc     edi
0x1800017d0  cmp     edi, esi
0x1800017d2  jl      short loc_180001775
0x1800017d4  xor     eax, eax
0x1800017d6  jmp     short loc_1800017DD
0x1800017d8  mov     eax, 1
0x1800017dd  mov     rbx, [rsp+68h+arg_0]
0x1800017e2  add     rsp, 30h
0x1800017e6  pop     r15
0x1800017e8  pop     r14
0x1800017ea  pop     r13
0x1800017ec  pop     r12
0x1800017ee  pop     rdi
0x1800017ef  pop     rsi
0x1800017f0  pop     rbp
0x1800017f1  retn
```
