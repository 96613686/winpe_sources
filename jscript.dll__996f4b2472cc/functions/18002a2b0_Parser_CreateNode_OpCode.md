# Parser::CreateNode(OpCode)

- ea: `0x18002a2b0`
- end: `0x18002a400`
- name: `?CreateNode@Parser@@AEAAPEAUParseNode@@W4OpCode@@@Z`
- size: `336`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b870`
- `0x180020170`
- `0x180029160`
- `0x180029228`
- `0x18002931c`
- `0x1800293d8`
- `0x180029550`
- `0x180029648`
- `0x18002a0dc`

## callees

- `0x18001d9e4`
- `0x18002a2b0`

## import_xrefs

- `msvcrt!malloc` at `0x18002a38c`
- `msvcrt!malloc` at `0x18002a3cc`
- `msvcrt!malloc` at `0x18002a38c`
- `msvcrt!malloc` at `0x18002a3cc`

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

  v4 = *((int *)qword_1800A2800 + a2);
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
      v6 = *((_DWORD *)qword_1800A2800 + a2);
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
0x18002a2b0  push    rbx
0x18002a2b2  push    rbp
0x18002a2b3  push    rsi
0x18002a2b4  push    rdi
0x18002a2b5  push    r12
0x18002a2b7  push    r13
0x18002a2b9  push    r14
0x18002a2bb  push    r15
0x18002a2bd  sub     rsp, 28h
0x18002a2c1  movsxd  r14, edx
0x18002a2c4  lea     rsi, qword_1800A2800
0x18002a2cb  mov     rbx, rcx
0x18002a2ce  movsxd  rsi, dword ptr [rsi+r14*4]
0x18002a2d2  test    esi, esi
0x18002a2d4  jle     loc_18002A3B3
0x18002a2da  mov     rax, [rcx+150h]
0x18002a2e1  mov     r15d, [rcx+14h]
0x18002a2e5  mov     ebp, [rcx+10h]
0x18002a2e8  mov     rdi, [rax+20h]
0x18002a2ec  mov     r12, [rax+10h]
0x18002a2f0  mov     eax, r15d
0x18002a2f3  sub     eax, ebp
0x18002a2f5  cmp     esi, eax
0x18002a2f7  jg      short loc_18002A34F
0x18002a2f9  lea     eax, [rsi+7]
0x18002a2fc  and     eax, 0FFFFFFF8h
0x18002a2ff  add     eax, ebp
0x18002a301  mov     [rbx+10h], eax
0x18002a304  movsxd  rax, ebp
0x18002a307  add     rax, [rbx+8]
0x18002a30b  add     rax, 8
0x18002a30f  jz      loc_18002A3B3
0x18002a315  mov     [rax], r14d
0x18002a318  sub     rdi, r12
0x18002a31b  mov     dword ptr [rax+4], 0
0x18002a322  sar     rdi, 1
0x18002a325  mov     [rax+8], edi
0x18002a328  mov     rcx, [rbx+150h]
0x18002a32f  mov     rdx, [rcx+28h]
0x18002a333  sub     rdx, [rcx+10h]
0x18002a337  sar     rdx, 1
0x18002a33a  mov     [rax+0Ch], edx
0x18002a33d  add     rsp, 28h
0x18002a341  pop     r15
0x18002a343  pop     r14
0x18002a345  pop     r13
0x18002a347  pop     r12
0x18002a349  pop     rdi
0x18002a34a  pop     rsi
0x18002a34b  pop     rbp
0x18002a34c  pop     rbx
0x18002a34d  retn
0x18002a34f  mov     r13d, [rcx+1Ch]
0x18002a353  cmp     esi, r13d
0x18002a356  jge     short loc_18002A3C1
0x18002a358  mov     eax, [rcx+18h]
0x18002a35b  cmp     r15d, esi
0x18002a35e  cmovle  r15d, esi
0x18002a362  add     r15d, r15d
0x18002a365  cmp     eax, r15d
0x18002a368  cmovle  eax, r15d
0x18002a36c  cmp     eax, r13d
0x18002a36f  cmovle  r13d, eax
0x18002a373  cmp     esi, r13d
0x18002a376  jg      short loc_18002A3B3
0x18002a378  lea     eax, [r13+8]
0x18002a37c  cmp     eax, r13d
0x18002a37f  jl      short loc_18002A3B3
0x18002a381  cmp     eax, esi
0x18002a383  jl      short loc_18002A3B3
0x18002a385  movsxd  rcx, r13d
0x18002a388  add     rcx, 8; Size
0x18002a38c  call    cs:__imp_malloc
0x18002a393  nop     dword ptr [rax+rax+00h]
0x18002a398  test    rax, rax
0x18002a39b  jz      short loc_18002A3B3
0x18002a39d  mov     rcx, [rbx+8]
0x18002a3a1  xor     ebp, ebp
0x18002a3a3  mov     [rax], rcx
0x18002a3a6  mov     [rbx+8], rax
0x18002a3aa  mov     [rbx+14h], r13d
0x18002a3ae  jmp     loc_18002A2F9
0x18002a3b3  mov     edx, 3E9h; int
0x18002a3b8  mov     rcx, rbx; this
0x18002a3bb  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
0x18002a3c1  lea     eax, [rsi+8]
0x18002a3c4  cmp     eax, esi
0x18002a3c6  jl      short loc_18002A3B3
0x18002a3c8  lea     rcx, [rsi+8]; Size
0x18002a3cc  call    cs:__imp_malloc
0x18002a3d3  nop     dword ptr [rax+rax+00h]
0x18002a3d8  test    rax, rax
0x18002a3db  jz      short loc_18002A3B3
0x18002a3dd  mov     rdx, [rbx+8]
0x18002a3e1  cmp     ebp, r15d
0x18002a3e4  jge     short loc_18002A3F4
0x18002a3e6  mov     rcx, [rdx]
0x18002a3e9  mov     [rax], rcx
0x18002a3ec  mov     [rdx], rax
0x18002a3ef  jmp     loc_18002A30B
0x18002a3f4  mov     [rax], rdx
0x18002a3f7  mov     [rbx+8], rax
0x18002a3fb  jmp     loc_18002A30B
```
