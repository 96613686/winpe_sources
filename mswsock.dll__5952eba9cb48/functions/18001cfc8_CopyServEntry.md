# CopyServEntry

- ea: `0x18001cfc8`
- end: `0x18001d162`
- name: `CopyServEntry`
- size: `410`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001f4e0`

## callees

- `0x18001cfc8`
- `0x18001d594`
- `0x180037195`
- `0x180038104`

## import_xrefs

- `DNSAPI!DnsApiAllocZero` at `0x18001d03c`
- `DNSAPI!DnsApiAllocZero` at `0x18001d03c`

## pseudocode

```c
__int64 __fastcall CopyServEntry(__int64 a1, __int64 a2, signed int a3, unsigned int *a4)
{
  __int64 v8; // rax
  __int64 v9; // r13
  __int64 v10; // rax
  _QWORD *v11; // rcx
  unsigned int v12; // r12d
  __int64 v13; // rbp
  int v14; // edx
  unsigned int v15; // ebx
  int v17; // r8d
  __int64 v18; // rdx
  _QWORD *v19; // r15
  const void **v20; // rsi
  char *v21; // rbp
  __int64 v22; // rbx
  size_t v23; // rbx

  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_(1025, 24, WPP_32eac39b2eb031c68cbf204d083572e1_Traceguids);
  v8 = -1;
  do
    ++v8;
  while ( *(_BYTE *)(*(_QWORD *)a1 + v8) );
  v9 = (unsigned int)(v8 + 1);
  v10 = -1;
  do
    ++v10;
  while ( *(_BYTE *)(*(_QWORD *)(a1 + 16) + v10) );
  v11 = *(_QWORD **)(a1 + 8);
  v12 = v10 + 1;
  v13 = 1;
  v14 = 8;
  if ( v11 )
  {
    while ( *v11 )
    {
      v17 = v14 + 8;
      v18 = -1;
      do
        ++v18;
      while ( *(_BYTE *)(*v11 + v18) );
      v13 = (unsigned int)(v13 + 1);
      v14 = v17 + v18 + 1;
      ++v11;
    }
  }
  v15 = v9 + v12 + v14 + 32;
  if ( a2 )
  {
    v15 = (v15 + 1) & 0xFFFFFFFE;
    if ( a3 < (int)v15 )
    {
      *a4 = v15;
      return 0;
    }
  }
  else
  {
    a2 = DnsApiAllocZero(v15);
  }
  *a4 = v15;
  if ( !a2 )
    return 0;
  v19 = (_QWORD *)(a2 + 32);
  *(_QWORD *)(a2 + 8) = a2 + 32;
  *(_WORD *)(a2 + 24) = *(_WORD *)(a1 + 24);
  v20 = *(const void ***)(a1 + 8);
  v21 = (char *)(a2 + 8 * (v13 + 4));
  if ( v20 )
  {
    while ( *v20 )
    {
      v22 = -1;
      do
        ++v22;
      while ( *((_BYTE *)*v20 + v22) );
      *v19 = v21;
      v23 = v22 + 1;
      memcpy_0(v21, *v20, v23);
      v21 += v23;
      ++v19;
      ++v20;
    }
  }
  *v19 = 0;
  *(_QWORD *)a2 = v21;
  memcpy_0(v21, *(const void **)a1, (unsigned int)v9);
  *(_QWORD *)(a2 + 16) = &v21[v9];
  memcpy_0(&v21[v9], *(const void **)(a1 + 16), v12);
  *(_QWORD *)a2 -= a2;
  *(_QWORD *)(a2 + 16) -= a2;
  PtrArrayToOffsetArray(a2 + 8, a2);
  return a2;
}

```

## disassembly

```asm
0x18001cfc8  push    rbx
0x18001cfca  push    rbp
0x18001cfcb  push    rsi
0x18001cfcc  push    rdi
0x18001cfcd  push    r12
0x18001cfcf  push    r13
0x18001cfd1  push    r14
0x18001cfd3  push    r15
0x18001cfd5  sub     rsp, 28h
0x18001cfd9  mov     rsi, r9
0x18001cfdc  mov     r15d, r8d
0x18001cfdf  mov     rdi, rdx
0x18001cfe2  mov     r14, rcx
0x18001cfe5  test    byte ptr cs:xmmword_180063D60, 2
0x18001cfec  jnz     short loc_18001D06D
0x18001cfee  mov     rdx, [r14]
0x18001cff1  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001cff5  mov     rax, r9
0x18001cff8  inc     rax
0x18001cffb  cmp     byte ptr [rdx+rax], 0
0x18001cfff  jnz     short loc_18001CFF8
0x18001d001  mov     rcx, [r14+10h]
0x18001d005  lea     r13d, [rax+1]
0x18001d009  mov     rax, r9
0x18001d00c  inc     rax
0x18001d00f  cmp     byte ptr [rcx+rax], 0
0x18001d013  jnz     short loc_18001D00C
0x18001d015  mov     rcx, [r14+8]
0x18001d019  lea     r12d, [rax+1]
0x18001d01d  mov     ebp, 1
0x18001d022  mov     edx, 8
0x18001d027  test    rcx, rcx
0x18001d02a  jnz     short loc_18001D0A3
0x18001d02c  lea     ebx, [rdx+20h]
0x18001d02f  add     ebx, r12d
0x18001d032  add     ebx, r13d
0x18001d035  test    rdi, rdi
0x18001d038  jnz     short loc_18001D0B0
0x18001d03a  mov     ecx, ebx
0x18001d03c  call    cs:__imp_DnsApiAllocZero
0x18001d043  nop     dword ptr [rax+rax+00h]
0x18001d048  mov     rdi, rax
0x18001d04b  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001d04f  mov     [rsi], ebx
0x18001d051  test    rdi, rdi
0x18001d054  jnz     short loc_18001D0BE
0x18001d056  xor     edi, edi
0x18001d058  mov     rax, rdi
0x18001d05b  add     rsp, 28h
0x18001d05f  pop     r15
0x18001d061  pop     r14
0x18001d063  pop     r13
0x18001d065  pop     r12
0x18001d067  pop     rdi
0x18001d068  pop     rsi
0x18001d069  pop     rbp
0x18001d06a  pop     rbx
0x18001d06b  retn
0x18001d06d  mov     edx, 18h
0x18001d072  lea     r8, WPP_32eac39b2eb031c68cbf204d083572e1_Traceguids
0x18001d079  mov     ecx, 401h
0x18001d07e  call    WPP_SF_
0x18001d083  jmp     loc_18001CFEE
0x18001d088  lea     r8d, [rdx+8]
0x18001d08c  mov     rdx, r9
0x18001d08f  inc     rdx
0x18001d092  cmp     byte ptr [rax+rdx], 0
0x18001d096  jnz     short loc_18001D08F
0x18001d098  inc     edx
0x18001d09a  inc     ebp
0x18001d09c  add     edx, r8d
0x18001d09f  add     rcx, 8
0x18001d0a3  mov     rax, [rcx]
0x18001d0a6  test    rax, rax
0x18001d0a9  jnz     short loc_18001D088
0x18001d0ab  jmp     loc_18001D02C
0x18001d0b0  inc     ebx
0x18001d0b2  and     ebx, 0FFFFFFFEh
0x18001d0b5  cmp     r15d, ebx
0x18001d0b8  jge     short loc_18001D04F
0x18001d0ba  mov     [rsi], ebx
0x18001d0bc  jmp     short loc_18001D056
0x18001d0be  add     rbp, 4
0x18001d0c2  lea     r15, [rdi+20h]
0x18001d0c6  mov     [rdi+8], r15
0x18001d0ca  movzx   eax, word ptr [r14+18h]
0x18001d0cf  mov     [rdi+18h], ax
0x18001d0d3  mov     rsi, [r14+8]
0x18001d0d7  lea     rbp, [rdi+rbp*8]
0x18001d0db  test    rsi, rsi
0x18001d0de  jnz     short loc_18001D114
0x18001d0e0  jmp     short loc_18001D11C
0x18001d0e2  mov     rbx, r9
0x18001d0e5  inc     rbx
0x18001d0e8  cmp     byte ptr [rax+rbx], 0
0x18001d0ec  jnz     short loc_18001D0E5
0x18001d0ee  mov     [r15], rbp
0x18001d0f1  inc     rbx
0x18001d0f4  mov     rdx, [rsi]; Src
0x18001d0f7  mov     r8, rbx; Size
0x18001d0fa  mov     rcx, rbp; void *
0x18001d0fd  call    memcpy_0
0x18001d102  add     rbp, rbx
0x18001d105  add     r15, 8
0x18001d109  add     rsi, 8
0x18001d10d  mov     r9, 0FFFFFFFFFFFFFFFFh
0x18001d114  mov     rax, [rsi]
0x18001d117  test    rax, rax
0x18001d11a  jnz     short loc_18001D0E2
0x18001d11c  mov     qword ptr [r15], 0
0x18001d123  mov     rcx, rbp; void *
0x18001d126  mov     [rdi], rbp
0x18001d129  mov     rdx, [r14]; Src
0x18001d12c  mov     r8d, r13d; Size
0x18001d12f  call    memcpy_0
0x18001d134  mov     rcx, r13
0x18001d137  mov     r8d, r12d; Size
0x18001d13a  add     rcx, rbp; void *
0x18001d13d  mov     [rdi+10h], rcx
0x18001d141  mov     rdx, [r14+10h]; Src
0x18001d145  call    memcpy_0
0x18001d14a  sub     [rdi], rdi
0x18001d14d  lea     rcx, [rdi+8]
0x18001d151  sub     [rdi+10h], rdi
0x18001d155  mov     rdx, rdi
0x18001d158  call    PtrArrayToOffsetArray
0x18001d15d  jmp     loc_18001D058
```
