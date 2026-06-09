# Parser::CreateNode(OpCode)

- ea: `0x18002d030`
- end: `0x18002d173`
- name: `?CreateNode@Parser@@AEAAPEAUParseNode@@W4OpCode@@@Z`
- size: `323`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x18001e880`
- `0x1800230f0`
- `0x18002bf20`
- `0x18002bfe4`
- `0x18002c0d8`
- `0x18002c194`
- `0x18002c30c`
- `0x18002c400`
- `0x18002ce60`

## callees

- `0x1800209a0`
- `0x18002d030`

## import_xrefs

- `msvcrt!malloc` at `0x18002d10b`
- `msvcrt!malloc` at `0x18002d145`
- `msvcrt!malloc` at `0x18002d10b`
- `msvcrt!malloc` at `0x18002d145`

## pseudocode

```c
_DWORD *__fastcall Parser::CreateNode(__int64 a1, int a2)
{
  __int64 v4; // rsi
  __int64 v5; // rax
  int v6; // r15d
  int v7; // ebp
  __int64 v8; // rdi
  __int64 v9; // r12
  _QWORD *v10; // rax
  _DWORD *result; // rax
  int v12; // r13d
  int v13; // eax
  int v14; // r15d
  _QWORD *v15; // rax
  _QWORD *v16; // rdx

  v4 = *((int *)qword_1800A0820 + a2);
  if ( (int)v4 <= 0 )
    goto LABEL_18;
  v5 = *(_QWORD *)(a1 + 336);
  v6 = *(_DWORD *)(a1 + 20);
  v7 = *(_DWORD *)(a1 + 16);
  v8 = *(_QWORD *)(v5 + 32);
  v9 = *(_QWORD *)(v5 + 16);
  if ( (int)v4 <= v6 - v7 )
  {
LABEL_3:
    *(_DWORD *)(a1 + 16) = v7 + ((v4 + 7) & 0xFFFFFFF8);
    v10 = (_QWORD *)(*(_QWORD *)(a1 + 8) + v7);
    goto LABEL_4;
  }
  v12 = *(_DWORD *)(a1 + 28);
  if ( (int)v4 < v12 )
  {
    v13 = *(_DWORD *)(a1 + 24);
    if ( v6 <= (int)v4 )
      v6 = *((_DWORD *)qword_1800A0820 + a2);
    v14 = 2 * v6;
    if ( v13 <= v14 )
      v13 = v14;
    if ( v13 <= v12 )
      v12 = v13;
    if ( (int)v4 <= v12 && v12 + 8 > v12 && v12 + 8 >= (int)v4 )
    {
      v15 = malloc(v12 + 8LL);
      if ( v15 )
      {
        v7 = 0;
        *v15 = *(_QWORD *)(a1 + 8);
        *(_QWORD *)(a1 + 8) = v15;
        *(_DWORD *)(a1 + 20) = v12;
        goto LABEL_3;
      }
    }
LABEL_18:
    Parser::Error((Parser *)a1, 1001);
  }
  if ( (int)v4 + 8 <= (int)v4 )
    goto LABEL_18;
  v10 = malloc(v4 + 8);
  if ( !v10 )
    goto LABEL_18;
  v16 = *(_QWORD **)(a1 + 8);
  if ( v7 >= v6 )
  {
    *v10 = v16;
    *(_QWORD *)(a1 + 8) = v10;
  }
  else
  {
    *v10 = *v16;
    *v16 = v10;
  }
LABEL_4:
  result = v10 + 1;
  if ( !result )
    goto LABEL_18;
  *result = a2;
  result[1] = 0;
  result[2] = (v8 - v9) >> 1;
  result[3] = (__int64)(*(_QWORD *)(*(_QWORD *)(a1 + 336) + 40LL) - *(_QWORD *)(*(_QWORD *)(a1 + 336) + 16LL)) >> 1;
  return result;
}

```

## disassembly

```asm
0x18002d030  push    rbx
0x18002d032  push    rbp
0x18002d033  push    rsi
0x18002d034  push    rdi
0x18002d035  push    r12
0x18002d037  push    r13
0x18002d039  push    r14
0x18002d03b  push    r15
0x18002d03d  sub     rsp, 28h
0x18002d041  movsxd  r14, edx
0x18002d044  lea     rsi, qword_1800A0820
0x18002d04b  mov     rbx, rcx
0x18002d04e  movsxd  rsi, dword ptr [rsi+r14*4]
0x18002d052  test    esi, esi
0x18002d054  jle     loc_18002D12C
0x18002d05a  mov     rax, [rcx+150h]
0x18002d061  mov     r15d, [rcx+14h]
0x18002d065  mov     ebp, [rcx+10h]
0x18002d068  mov     rdi, [rax+20h]
0x18002d06c  mov     r12, [rax+10h]
0x18002d070  mov     eax, r15d
0x18002d073  sub     eax, ebp
0x18002d075  cmp     esi, eax
0x18002d077  jg      short loc_18002D0CE
0x18002d079  lea     eax, [rsi+7]
0x18002d07c  and     eax, 0FFFFFFF8h
0x18002d07f  add     eax, ebp
0x18002d081  mov     [rbx+10h], eax
0x18002d084  movsxd  rax, ebp
0x18002d087  add     rax, [rbx+8]
0x18002d08b  add     rax, 8
0x18002d08f  jz      loc_18002D12C
0x18002d095  mov     [rax], r14d
0x18002d098  sub     rdi, r12
0x18002d09b  mov     dword ptr [rax+4], 0
0x18002d0a2  sar     rdi, 1
0x18002d0a5  mov     [rax+8], edi
0x18002d0a8  mov     rcx, [rbx+150h]
0x18002d0af  mov     rdx, [rcx+28h]
0x18002d0b3  sub     rdx, [rcx+10h]
0x18002d0b7  sar     rdx, 1
0x18002d0ba  mov     [rax+0Ch], edx
0x18002d0bd  add     rsp, 28h
0x18002d0c1  pop     r15
0x18002d0c3  pop     r14
0x18002d0c5  pop     r13
0x18002d0c7  pop     r12
0x18002d0c9  pop     rdi
0x18002d0ca  pop     rsi
0x18002d0cb  pop     rbp
0x18002d0cc  pop     rbx
0x18002d0cd  retn
0x18002d0ce  mov     r13d, [rcx+1Ch]
0x18002d0d2  cmp     esi, r13d
0x18002d0d5  jge     short loc_18002D13A
0x18002d0d7  mov     eax, [rcx+18h]
0x18002d0da  cmp     r15d, esi
0x18002d0dd  cmovle  r15d, esi
0x18002d0e1  add     r15d, r15d
0x18002d0e4  cmp     eax, r15d
0x18002d0e7  cmovle  eax, r15d
0x18002d0eb  cmp     eax, r13d
0x18002d0ee  cmovle  r13d, eax
0x18002d0f2  cmp     esi, r13d
0x18002d0f5  jg      short loc_18002D12C
0x18002d0f7  lea     eax, [r13+8]
0x18002d0fb  cmp     eax, r13d
0x18002d0fe  jl      short loc_18002D12C
0x18002d100  cmp     eax, esi
0x18002d102  jl      short loc_18002D12C
0x18002d104  movsxd  rcx, r13d
0x18002d107  add     rcx, 8; Size
0x18002d10b  call    cs:__imp_malloc
0x18002d111  test    rax, rax
0x18002d114  jz      short loc_18002D12C
0x18002d116  mov     rcx, [rbx+8]
0x18002d11a  xor     ebp, ebp
0x18002d11c  mov     [rax], rcx
0x18002d11f  mov     [rbx+8], rax
0x18002d123  mov     [rbx+14h], r13d
0x18002d127  jmp     loc_18002D079
0x18002d12c  mov     edx, 3E9h; int
0x18002d131  mov     rcx, rbx; this
0x18002d134  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
0x18002d13a  lea     eax, [rsi+8]
0x18002d13d  cmp     eax, esi
0x18002d13f  jl      short loc_18002D12C
0x18002d141  lea     rcx, [rsi+8]; Size
0x18002d145  call    cs:__imp_malloc
0x18002d14b  test    rax, rax
0x18002d14e  jz      short loc_18002D12C
0x18002d150  mov     rdx, [rbx+8]
0x18002d154  cmp     ebp, r15d
0x18002d157  jge     short loc_18002D167
0x18002d159  mov     rcx, [rdx]
0x18002d15c  mov     [rax], rcx
0x18002d15f  mov     [rdx], rax
0x18002d162  jmp     loc_18002D08B
0x18002d167  mov     [rax], rdx
0x18002d16a  mov     [rbx+8], rax
0x18002d16e  jmp     loc_18002D08B
```
