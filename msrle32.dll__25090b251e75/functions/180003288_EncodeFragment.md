# EncodeFragment

- ea: `0x180003288`
- end: `0x180003417`
- name: `EncodeFragment`
- size: `399`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002ee8`

## callees

- `0x1800031d8`
- `0x180003288`

## pseudocode

```c
_WORD *__fastcall EncodeFragment(
        _BYTE *a1,
        int a2,
        _WORD *a3,
        unsigned int a4,
        unsigned int *a5,
        __int64 a6,
        unsigned int a7,
        int a8)
{
  int v8; // ebx
  unsigned int v10; // r15d
  __int64 v11; // r12
  int v12; // ebp
  __int64 v13; // r11
  int v14; // edi
  int v15; // eax
  int v16; // edx
  _BYTE *v17; // r13
  _BYTE *v18; // r11
  __int64 v19; // rsi
  _BYTE *v20; // r14
  int v21; // ecx
  __int64 v22; // rax
  unsigned int v24; // [rsp+98h] [rbp+20h] BYREF

  v24 = a4;
  v8 = a2;
  if ( a2 <= 0 )
  {
LABEL_27:
    *a5 = a4;
    return a3;
  }
  v10 = a7;
  v11 = a6;
  v12 = a8;
  while ( 1 )
  {
LABEL_3:
    v13 = (unsigned __int8)*a1;
    v14 = v8;
    if ( v8 > 255 )
      v14 = 255;
    v15 = v14;
    if ( v12 < v14 )
      v15 = v12;
    v16 = 0;
    v12 = v15;
    if ( v14 <= 0 )
      goto LABEL_13;
    do
    {
      if ( (_BYTE)v13 != *a1 && (*(_DWORD *)(v11 + 4 * ((unsigned __int8)*a1 + (v13 << 8))) > v10 || v16 >= v15) )
        break;
      ++v16;
      ++a1;
    }
    while ( v16 < v14 );
    if ( v16 <= 1 )
    {
LABEL_13:
      if ( v8 >= 3 )
      {
        v17 = a1;
        v18 = a1--;
        v19 = 0;
        if ( v14 > 0 )
        {
          while ( v14 - (int)v19 >= 4 )
          {
            v20 = &a1[v19];
            v21 = (unsigned __int8)a1[v19] << 8;
            if ( *(_DWORD *)(v11 + 4LL * (v21 + (unsigned int)(unsigned __int8)v18[v19])) <= v10
              && *(_DWORD *)(v11 + 4LL * (v21 + (unsigned int)(unsigned __int8)v18[v19 + 1])) <= v10
              && *(_DWORD *)(v11 + 4LL * (v21 + (unsigned int)(unsigned __int8)v18[v19 + 2])) <= v10 )
            {
              v22 = EncodeAbsolute((_DWORD)a1, v19, (_DWORD)a3, a4, (__int64)&v24);
              a1 = v20;
              v8 -= v19;
              goto LABEL_23;
            }
            v19 = (unsigned int)(v19 + 1);
            if ( (int)v19 >= v14 )
              goto LABEL_3;
          }
          v22 = EncodeAbsolute((_DWORD)a1, v14, (_DWORD)a3, a4, (__int64)&v24);
          a1 = &v17[v14 - 1];
          v8 -= v14;
LABEL_23:
          a4 = v24;
          a3 = (_WORD *)v22;
        }
        goto LABEL_26;
      }
    }
    if ( a4 < 2 )
      return 0;
    a4 -= 2;
    v24 = a4;
    *a3++ = v16 | ((_WORD)v13 << 8);
    v8 -= v16;
LABEL_26:
    if ( v8 <= 0 )
      goto LABEL_27;
  }
}

```

## disassembly

```asm
0x180003288  mov     [rsp+arg_18], r9d
0x18000328d  push    rbx
0x18000328e  push    rbp
0x18000328f  push    rsi
0x180003290  push    rdi
0x180003291  push    r12
0x180003293  push    r13
0x180003295  push    r14
0x180003297  push    r15
0x180003299  sub     rsp, 38h
0x18000329d  mov     ebx, edx
0x18000329f  mov     r10, rcx
0x1800032a2  test    edx, edx
0x1800032a4  jle     loc_1800033F4
0x1800032aa  mov     r15d, [rsp+78h+arg_30]
0x1800032b2  mov     r12, [rsp+78h+arg_28]
0x1800032ba  mov     ebp, [rsp+78h+arg_38]
0x1800032c1  mov     eax, 0FFh
0x1800032c6  movzx   r11d, byte ptr [r10]
0x1800032ca  cmp     ebx, eax
0x1800032cc  mov     edi, ebx
0x1800032ce  cmovg   edi, eax
0x1800032d1  cmp     ebp, edi
0x1800032d3  mov     eax, edi
0x1800032d5  cmovl   eax, ebp
0x1800032d8  xor     edx, edx
0x1800032da  mov     ebp, eax
0x1800032dc  test    edi, edi
0x1800032de  jle     short loc_18000330F
0x1800032e0  cmp     r11b, [r10]
0x1800032e3  jz      short loc_1800032FD
0x1800032e5  movzx   eax, byte ptr [r10]
0x1800032e9  mov     rcx, r11
0x1800032ec  shl     rcx, 8
0x1800032f0  add     rcx, rax
0x1800032f3  cmp     [r12+rcx*4], r15d
0x1800032f7  ja      short loc_180003306
0x1800032f9  cmp     edx, ebp
0x1800032fb  jge     short loc_180003306
0x1800032fd  inc     edx
0x1800032ff  inc     r10
0x180003302  cmp     edx, edi
0x180003304  jl      short loc_1800032E0
0x180003306  cmp     edx, 1
0x180003309  jg      loc_1800033C0
0x18000330f  cmp     ebx, 3
0x180003312  jl      loc_1800033C0
0x180003318  mov     r13, r10
0x18000331b  mov     r11, r10
0x18000331e  dec     r10
0x180003321  xor     esi, esi
0x180003323  test    edi, edi
0x180003325  jle     loc_1800033E7
0x18000332b  mov     eax, edi
0x18000332d  sub     eax, esi
0x18000332f  cmp     eax, 4
0x180003332  jl      short loc_180003391
0x180003334  movzx   eax, byte ptr [rsi+r11]
0x180003339  lea     r14, [rsi+r10]
0x18000333d  movzx   ecx, byte ptr [r14]
0x180003341  shl     ecx, 8
0x180003344  add     eax, ecx
0x180003346  cmp     [r12+rax*4], r15d
0x18000334a  ja      short loc_180003368
0x18000334c  movzx   eax, byte ptr [rsi+r11+1]
0x180003352  add     eax, ecx
0x180003354  cmp     [r12+rax*4], r15d
0x180003358  ja      short loc_180003368
0x18000335a  movzx   eax, byte ptr [rsi+r11+2]
0x180003360  add     eax, ecx
0x180003362  cmp     [r12+rax*4], r15d
0x180003366  jbe     short loc_180003373
0x180003368  inc     esi
0x18000336a  cmp     esi, edi
0x18000336c  jl      short loc_18000332B
0x18000336e  jmp     loc_1800032C1
0x180003373  lea     rax, [rsp+78h+arg_18]
0x18000337b  mov     edx, esi
0x18000337d  mov     rcx, r10
0x180003380  mov     [rsp+78h+var_58], rax
0x180003385  call    EncodeAbsolute
0x18000338a  mov     r10, r14
0x18000338d  sub     ebx, esi
0x18000338f  jmp     short loc_1800033B3
0x180003391  lea     rax, [rsp+78h+arg_18]
0x180003399  mov     edx, edi
0x18000339b  mov     rcx, r10
0x18000339e  mov     [rsp+78h+var_58], rax
0x1800033a3  call    EncodeAbsolute
0x1800033a8  movsxd  r10, edi
0x1800033ab  dec     r10
0x1800033ae  add     r10, r13
0x1800033b1  sub     ebx, edi
0x1800033b3  mov     r9d, [rsp+78h+arg_18]
0x1800033bb  mov     r8, rax
0x1800033be  jmp     short loc_1800033E7
0x1800033c0  cmp     r9d, 2
0x1800033c4  jb      short loc_180003413
0x1800033c6  add     r9d, 0FFFFFFFEh
0x1800033ca  movzx   eax, r11w
0x1800033ce  shl     ax, 8
0x1800033d2  or      ax, dx
0x1800033d5  mov     [rsp+78h+arg_18], r9d
0x1800033dd  mov     [r8], ax
0x1800033e1  add     r8, 2
0x1800033e5  sub     ebx, edx
0x1800033e7  mov     eax, 0FFh
0x1800033ec  test    ebx, ebx
0x1800033ee  jg      loc_1800032C6
0x1800033f4  mov     rax, [rsp+78h+arg_20]
0x1800033fc  mov     [rax], r9d
0x1800033ff  mov     rax, r8
0x180003402  add     rsp, 38h
0x180003406  pop     r15
0x180003408  pop     r14
0x18000340a  pop     r13
0x18000340c  pop     r12
0x18000340e  pop     rdi
0x18000340f  pop     rsi
0x180003410  pop     rbp
0x180003411  pop     rbx
0x180003412  retn
0x180003413  xor     eax, eax
0x180003415  jmp     short loc_180003402
```
