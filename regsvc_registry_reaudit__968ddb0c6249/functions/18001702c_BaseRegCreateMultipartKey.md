# BaseRegCreateMultipartKey

- ea: `0x18001702c`
- end: `0x18001720a`
- name: `BaseRegCreateMultipartKey`
- size: `478`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, unsigned int, __int64, __int64 *, _DWORD *, int, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180016d3c`

## callees

- `0x18001702c`
- `0x18001d38c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180017096`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180017100`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800171c8`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180017096`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180017100`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800171c8`
- `ntdll!NtClose` at `0x1800171ac`
- `ntdll!NtClose` at `0x1800171ac`

## pseudocode

```c
__int64 __fastcall BaseRegCreateMultipartKey(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        __int64 *a7,
        _DWORD *a8,
        int a9,
        void *a10)
{
  wchar_t *v10; // rdi
  unsigned int v11; // esi
  void *v13; // r12
  unsigned int v14; // r14d
  const wchar_t *v15; // rcx
  wchar_t *v16; // rax
  unsigned int v17; // r15d
  __int64 v18; // rcx
  __int16 v19; // cx
  __int64 v20; // rdx
  int v21; // ebx
  __int128 v23; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v24[48]; // [rsp+50h] [rbp-30h] BYREF

  v10 = *(wchar_t **)(a2 + 8);
  v11 = 0;
  v13 = 0;
  a10 = 0;
  v14 = 1;
  v15 = v10;
  v23 = 0;
  memset(v24, 0, 44);
  while ( 1 )
  {
    v16 = wcschr(v15, 0x5Cu);
    if ( !v16 )
      break;
    ++v14;
    v15 = v16 + 1;
  }
  v17 = v14 - 1;
  while ( v11 < v14 )
  {
    if ( *v10 != 92 || v11 == v17 )
    {
      *((_QWORD *)&v23 + 1) = v10;
      if ( v11 == v17 )
      {
        v18 = -1;
        do
          ++v18;
        while ( v10[v18] );
        if ( (unsigned __int64)(2 * v18) >= 0xFFFF )
          v19 = -1;
        else
          v19 = 2 * v18;
        LOWORD(v23) = v19;
      }
      else
      {
        v19 = 2 * (wcschr(v10, 0x5Cu) - v10);
        LOWORD(v23) = v19;
      }
      *(_DWORD *)&v24[24] = a9;
      *(_QWORD *)&v24[16] = &v23;
      WORD1(v23) = v19;
      *(_DWORD *)v24 = 48;
      *(_QWORD *)&v24[8] = a1;
      if ( a6 )
        *(_OWORD *)&v24[32] = *(unsigned __int64 *)(a6 + 8);
      else
        *(_OWORD *)&v24[32] = 0;
      v20 = a5;
      if ( v11 != v17 )
      {
        v20 = a5 & 0x300;
        LODWORD(v20) = v20 | 0x2000000;
      }
      v21 = Wow64NtCreateKey(&a10, v20, v24);
      if ( v21 >= 0 && a8 )
        *a8 = 2;
      if ( v13 )
        NtClose(v13);
      if ( v21 < 0 )
        return (unsigned int)v21;
      v13 = a10;
      a1 = (__int64)a10;
      v10 = wcschr(v10, 0x5Cu);
    }
    ++v11;
    ++v10;
  }
  *a7 = a1;
  return 0;
}

```

## disassembly

```asm
0x18001702c  mov     [rsp-38h+arg_0], rbx
0x180017031  mov     [rsp-38h+arg_18], r9d
0x180017036  mov     [rsp-38h+arg_10], r8
0x18001703b  push    rbp
0x18001703c  push    rsi
0x18001703d  push    rdi
0x18001703e  push    r12
0x180017040  push    r13
0x180017042  push    r14
0x180017044  push    r15
0x180017046  mov     rbp, rsp
0x180017049  sub     rsp, 80h
0x180017050  mov     rdi, [rdx+8]
0x180017054  xorps   xmm0, xmm0
0x180017057  xor     eax, eax
0x180017059  mov     [rbp+arg_8], 2
0x180017060  xor     esi, esi
0x180017062  mov     rbx, rcx
0x180017065  movups  [rbp+var_20], xmm0
0x180017069  mov     r12d, esi
0x18001706c  mov     [rbp+arg_48], rsi
0x180017073  lea     r14d, [rax+1]
0x180017077  mov     rcx, rdi
0x18001707a  lea     r15d, [rax+5Ch]
0x18001707e  movups  [rbp+var_40], xmm0
0x180017082  movups  [rbp+var_30], xmm0
0x180017086  movups  [rbp+var_20+0Ch], xmm0
0x18001708a  jmp     short loc_180017093
0x18001708c  inc     r14d
0x18001708f  lea     rcx, [rax+2]; Str
0x180017093  mov     edx, r15d; Ch
0x180017096  call    cs:__imp_wcschr
0x18001709c  test    rax, rax
0x18001709f  jnz     short loc_18001708C
0x1800170a1  mov     r13, [rbp+arg_38]
0x1800170a5  lea     r15d, [r14-1]
0x1800170a9  mov     r8d, 0FFFFh
0x1800170af  cmp     esi, r14d
0x1800170b2  jnb     loc_1800171E6
0x1800170b8  mov     eax, 5Ch ; '\'
0x1800170bd  cmp     [rdi], ax
0x1800170c0  jnz     short loc_1800170CB
0x1800170c2  cmp     esi, r15d
0x1800170c5  jnz     loc_1800171D7
0x1800170cb  mov     qword ptr [rbp+var_40+8], rdi
0x1800170cf  cmp     esi, r15d
0x1800170d2  jnz     short loc_1800170FB
0x1800170d4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800170d8  xor     edx, edx
0x1800170da  inc     rcx
0x1800170dd  cmp     [rdi+rcx*2], dx
0x1800170e1  jnz     short loc_1800170DA
0x1800170e3  lea     rax, [rcx+rcx]
0x1800170e7  cmp     rax, r8
0x1800170ea  jnb     short loc_1800170F1
0x1800170ec  add     cx, cx
0x1800170ef  jmp     short loc_1800170F5
0x1800170f1  movzx   ecx, r8w
0x1800170f5  mov     word ptr [rbp+var_40], cx
0x1800170f9  jmp     short loc_180017118
0x1800170fb  mov     edx, eax; Ch
0x1800170fd  mov     rcx, rdi; Str
0x180017100  call    cs:__imp_wcschr
0x180017106  sub     rax, rdi
0x180017109  sar     rax, 1
0x18001710c  add     ax, ax
0x18001710f  movzx   ecx, ax
0x180017112  mov     word ptr [rbp+var_40], ax
0x180017116  xor     edx, edx
0x180017118  mov     eax, [rbp+arg_40]
0x18001711e  mov     dword ptr [rbp+var_20+8], eax
0x180017121  lea     rax, [rbp+var_40]
0x180017125  mov     qword ptr [rbp+var_20], rax
0x180017129  mov     rax, [rbp+arg_28]
0x18001712d  mov     word ptr [rbp+var_40+2], cx
0x180017131  mov     dword ptr [rbp+var_30], 30h ; '0'
0x180017138  mov     qword ptr [rbp+var_30+8], rbx
0x18001713c  test    rax, rax
0x18001713f  jz      short loc_18001714F
0x180017141  mov     rax, [rax+8]
0x180017145  mov     qword ptr [rbp+var_10], rax
0x180017149  mov     qword ptr [rbp+var_10+8], rdx
0x18001714d  jmp     short loc_180017157
0x18001714f  xorps   xmm0, xmm0
0x180017152  movdqu  [rbp+var_10], xmm0
0x180017157  mov     edx, [rbp+arg_20]
0x18001715a  cmp     esi, r15d
0x18001715d  jz      short loc_180017169
0x18001715f  and     edx, 300h
0x180017165  bts     edx, 19h
0x180017169  lea     rax, [rbp+arg_8]
0x18001716d  mov     [rsp+80h+var_48], rax
0x180017172  lea     r8, [rbp+var_30]
0x180017176  mov     eax, [rbp+arg_18]
0x180017179  lea     rcx, [rbp+arg_48]
0x180017180  mov     [rsp+80h+var_58], eax
0x180017184  mov     rax, [rbp+arg_10]
0x180017188  mov     [rsp+80h+var_60], rax
0x18001718d  call    Wow64NtCreateKey
0x180017192  mov     ebx, eax
0x180017194  test    eax, eax
0x180017196  js      short loc_1800171A4
0x180017198  test    r13, r13
0x18001719b  jz      short loc_1800171A4
0x18001719d  mov     edx, [rbp+arg_8]
0x1800171a0  mov     [r13+0], edx
0x1800171a4  test    r12, r12
0x1800171a7  jz      short loc_1800171B2
0x1800171a9  mov     rcx, r12; Handle
0x1800171ac  call    cs:__imp_NtClose
0x1800171b2  test    ebx, ebx
0x1800171b4  js      short loc_1800171E2
0x1800171b6  mov     r12, [rbp+arg_48]
0x1800171bd  mov     edx, 5Ch ; '\'; Ch
0x1800171c2  mov     rcx, rdi; Str
0x1800171c5  mov     rbx, r12
0x1800171c8  call    cs:__imp_wcschr
0x1800171ce  mov     rdi, rax
0x1800171d1  mov     r8d, 0FFFFh
0x1800171d7  inc     esi
0x1800171d9  add     rdi, 2
0x1800171dd  jmp     loc_1800170AF
0x1800171e2  mov     eax, ebx
0x1800171e4  jmp     short loc_1800171EF
0x1800171e6  mov     rax, [rbp+arg_30]
0x1800171ea  mov     [rax], rbx
0x1800171ed  xor     eax, eax
0x1800171ef  mov     rbx, [rsp+80h+arg_0]
0x1800171f7  add     rsp, 80h
0x1800171fe  pop     r15
0x180017200  pop     r14
0x180017202  pop     r13
0x180017204  pop     r12
0x180017206  pop     rdi
0x180017207  pop     rsi
0x180017208  pop     rbp
0x180017209  retn
```
