# MDICreateDecompression

- ea: `0x1800092c0`
- end: `0x180009366`
- name: `MDICreateDecompression`
- size: `166`
- prototype: `__int64 __fastcall(int *, __int64 (__fastcall *)(__int64), void (__fastcall *)(__int64), _DWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800084e8`

## callees

- `0x1800090e0`
- `0x1800092c0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall MDICreateDecompression(
        int *a1,
        __int64 (__fastcall *a2)(__int64),
        void (__fastcall *a3)(__int64),
        _DWORD *a4,
        __int64 *a5)
{
  int v5; // r10d
  __int64 v10; // rbx
  __int64 v11; // rax

  v5 = *a1;
  if ( (unsigned int)(*a1 - 1) > 0x7FFF )
  {
    v5 = 0x8000;
    *a1 = 0x8000;
  }
  *a4 = v5 + 12;
  if ( !a5 )
    return 0;
  *a5 = 0;
  v10 = a2(32);
  if ( v10 )
  {
    v11 = NFMdeco_create(a2, 0, 0);
    *(_QWORD *)(v10 + 24) = v11;
    if ( v11 )
    {
      *(_QWORD *)(v10 + 8) = a3;
      *(_DWORD *)(v10 + 16) = *a1;
      *(_DWORD *)v10 = 1128875085;
      *a5 = v10;
      return 0;
    }
    a3(v10);
  }
  return 1;
}

```

## disassembly

```asm
0x1800092c0  push    rbx
0x1800092c2  push    rbp
0x1800092c3  push    rsi
0x1800092c4  push    rdi
0x1800092c5  push    r14
0x1800092c7  sub     rsp, 20h
0x1800092cb  mov     r10d, [rcx]
0x1800092ce  mov     rbp, r8
0x1800092d1  mov     r14, rdx
0x1800092d4  mov     rsi, rcx
0x1800092d7  lea     eax, [r10-1]
0x1800092db  cmp     eax, 7FFFh
0x1800092e0  ja      short loc_180009358
0x1800092e2  mov     rdi, [rsp+48h+arg_20]
0x1800092e7  lea     eax, [r10+0Ch]
0x1800092eb  mov     [r9], eax
0x1800092ee  test    rdi, rdi
0x1800092f1  jnz     short loc_180009300
0x1800092f3  xor     eax, eax
0x1800092f5  add     rsp, 20h
0x1800092f9  pop     r14
0x1800092fb  pop     rdi
0x1800092fc  pop     rsi
0x1800092fd  pop     rbp
0x1800092fe  pop     rbx
0x1800092ff  retn
0x180009300  mov     ecx, 20h ; ' '
0x180009305  mov     qword ptr [rdi], 0
0x18000930c  mov     rax, r14
0x18000930f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009314  mov     rbx, rax
0x180009317  test    rax, rax
0x18000931a  jz      short loc_180009351
0x18000931c  xor     r8d, r8d
0x18000931f  xor     edx, edx
0x180009321  mov     rcx, r14
0x180009324  call    NFMdeco_create
0x180009329  mov     [rbx+18h], rax
0x18000932d  test    rax, rax
0x180009330  jz      short loc_180009346
0x180009332  mov     [rbx+8], rbp
0x180009336  mov     eax, [rsi]
0x180009338  mov     [rbx+10h], eax
0x18000933b  mov     dword ptr [rbx], 4349444Dh
0x180009341  mov     [rdi], rbx
0x180009344  jmp     short loc_1800092F3
0x180009346  mov     rcx, rbx
0x180009349  mov     rax, rbp
0x18000934c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009351  mov     eax, 1
0x180009356  jmp     short loc_1800092F5
0x180009358  mov     r10d, 8000h
0x18000935e  mov     [rcx], r10d
0x180009361  jmp     loc_1800092E2
```
