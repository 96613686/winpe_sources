# decodeRPE

- ea: `0x180003f8c`
- end: `0x1800041ad`
- name: `decodeRPE`
- size: `545`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004f60`

## callees

- `0x180003f8c`

## pseudocode

```c
__int64 __fastcall decodeRPE(__int64 a1, __int16 a2, __int16 a3, __int64 a4, _WORD *a5)
{
  int v6; // esi
  int v7; // edx
  int v8; // edi
  int v9; // ecx
  __int16 v10; // di
  int v11; // r8d
  int v12; // eax
  int v13; // eax
  int v14; // r9d
  int v15; // ecx
  __int16 v16; // di
  char v17; // r8
  int v18; // eax
  int v19; // eax
  int v20; // r11d
  __int64 v21; // rdx
  int v22; // r9d
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  __int64 v27; // rcx
  _WORD *v28; // rdi
  unsigned int i; // r8d
  __int64 v30; // rdi
  __int64 v31; // rcx
  __int64 result; // rax
  _WORD v33[52]; // [rsp+0h] [rbp-68h]

  v6 = a2;
  if ( a3 <= 15 )
  {
    LOWORD(v7) = 0;
  }
  else
  {
    v7 = (a3 >> 3) - 1;
    if ( v7 >= -32768 )
    {
      if ( v7 > 0x7FFF )
        LOWORD(v7) = 0x7FFF;
    }
    else
    {
      LOWORD(v7) = 0x8000;
    }
  }
  v8 = a3 - (__int16)(8 * v7);
  if ( v8 >= -32768 )
  {
    if ( v8 <= 0x7FFF )
    {
      if ( !(_WORD)v8 )
      {
        LOWORD(v7) = -4;
        LOWORD(v9) = 15;
        goto LABEL_28;
      }
      LOWORD(v9) = a3 - 8 * v7;
    }
    else
    {
      LOWORD(v9) = 0x7FFF;
    }
  }
  else
  {
    LOWORD(v9) = 0x8000;
  }
  v10 = 0;
  v11 = 3;
  do
  {
    if ( (__int16)v9 <= 7 )
    {
      if ( !v10 )
      {
        v9 = (__int16)(2 * v9) + 1;
        if ( v9 >= -32768 )
        {
          if ( v9 > 0x7FFF )
            LOWORD(v9) = 0x7FFF;
        }
        else
        {
          LOWORD(v9) = 0x8000;
        }
        v12 = (__int16)v7 - 1;
        if ( v12 >= -32768 )
        {
          if ( v12 > 0x7FFF )
            LOWORD(v12) = 0x7FFF;
        }
        else
        {
          LOWORD(v12) = 0x8000;
        }
        LOWORD(v7) = v12;
      }
    }
    else
    {
      v10 = 1;
    }
    --v11;
  }
  while ( v11 );
LABEL_28:
  v13 = (__int16)v9 - 8;
  if ( v13 >= -32768 )
  {
    if ( v13 > 0x7FFF )
      LOWORD(v13) = 0x7FFF;
  }
  else
  {
    LOWORD(v13) = 0x8000;
  }
  v14 = FAC[(__int16)v13];
  v15 = 6 - (__int16)v7;
  if ( v15 >= -32768 )
  {
    if ( v15 <= 0x7FFF )
      v16 = 6 - v7;
    else
      v16 = 0x7FFF;
  }
  else
  {
    v16 = 0x8000;
  }
  v17 = v16;
  v18 = v16 - 1;
  if ( v18 >= -32768 )
  {
    if ( v18 <= 0x7FFF )
    {
      if ( (v18 & 0x8000u) != 0 )
        goto LABEL_39;
    }
    else
    {
      LOBYTE(v18) = -1;
    }
    v19 = 1 << v18;
    goto LABEL_40;
  }
  LOWORD(v18) = 0x8000;
LABEL_39:
  v19 = 1 >> -(__int16)v18;
LABEL_40:
  v20 = v14;
  v21 = 0;
  v22 = (__int16)v19;
  do
  {
    v23 = (__int16)(2 * *(_WORD *)(a4 + 2 * v21)) - 7;
    if ( v23 >= -32768 )
    {
      if ( v23 > 0x7FFF )
        LOWORD(v23) = 0x7FFF;
    }
    else
    {
      LOWORD(v23) = 0x8000;
    }
    v24 = v20 * (__int16)((_WORD)v23 << 12) + 0x4000;
    if ( v24 >= 0x40000000 )
      v24 = 0x3FFFFFFF;
    v25 = v22 + (__int16)((unsigned int)v24 >> 15);
    if ( v25 >= -32768 )
    {
      if ( v25 > 0x7FFF )
        LOWORD(v25) = 0x7FFF;
    }
    else
    {
      LOWORD(v25) = 0x8000;
    }
    if ( v16 < 0 )
    {
      v26 = (__int16)v25 << -v17;
    }
    else
    {
      v17 = v16;
      v26 = (__int16)v25 >> v16;
    }
    v33[v21++] = v26;
  }
  while ( v21 != 13 );
  v27 = 40;
  v28 = a5;
  while ( v27 )
  {
    *v28++ = 0;
    --v27;
  }
  for ( i = 0; i <= 0xC; ++i )
  {
    v30 = i;
    v31 = i + v6 + 2 * i;
    result = (unsigned __int16)v33[v30];
    a5[v31] = result;
  }
  return result;
}

```

## disassembly

```asm
0x180003f8c  push    rbx
0x180003f8e  push    rbp
0x180003f8f  push    rsi
0x180003f90  push    rdi
0x180003f91  push    r12
0x180003f93  push    r13
0x180003f95  push    r14
0x180003f97  push    r15
0x180003f99  sub     rsp, 28h
0x180003f9d  mov     rbx, [rsp+68h+arg_20]
0x180003fa5  xor     r12d, r12d
0x180003fa8  mov     r14, r9
0x180003fab  movsx   esi, dx
0x180003fae  movsx   edi, r8w
0x180003fb2  mov     ebp, 7FFFh
0x180003fb7  mov     r15d, 0FFFF8000h
0x180003fbd  lea     r9d, [r12+0Fh]
0x180003fc2  cmp     r8w, r9w
0x180003fc6  jle     short loc_180003FE2
0x180003fc8  mov     edx, edi
0x180003fca  sar     edx, 3
0x180003fcd  dec     edx
0x180003fcf  cmp     edx, r15d
0x180003fd2  jge     short loc_180003FDA
0x180003fd4  movzx   edx, r15w
0x180003fd8  jmp     short loc_180003FE5
0x180003fda  cmp     edx, ebp
0x180003fdc  jle     short loc_180003FE5
0x180003fde  mov     edx, ebp
0x180003fe0  jmp     short loc_180003FE5
0x180003fe2  mov     edx, r12d
0x180003fe5  movzx   eax, dx
0x180003fe8  mov     r13d, 1
0x180003fee  shl     ax, 3
0x180003ff2  movsx   ecx, ax
0x180003ff5  sub     edi, ecx
0x180003ff7  cmp     edi, r15d
0x180003ffa  jge     short loc_180004002
0x180003ffc  movzx   ecx, r15w
0x180004000  jmp     short loc_18000401D
0x180004002  cmp     edi, ebp
0x180004004  jle     short loc_18000400A
0x180004006  mov     ecx, ebp
0x180004008  jmp     short loc_18000401D
0x18000400a  test    di, di
0x18000400d  jnz     short loc_18000401A
0x18000400f  mov     edx, 0FFFFFFFCh
0x180004014  movzx   ecx, r9w
0x180004018  jmp     short loc_180004070
0x18000401a  movzx   ecx, di
0x18000401d  mov     edi, r12d
0x180004020  mov     r8d, 3
0x180004026  cmp     cx, 7
0x18000402a  jle     short loc_180004032
0x18000402c  movzx   edi, r13w
0x180004030  jmp     short loc_18000406A
0x180004032  test    di, di
0x180004035  jnz     short loc_18000406A
0x180004037  add     cx, cx
0x18000403a  movsx   ecx, cx
0x18000403d  inc     ecx
0x18000403f  cmp     ecx, r15d
0x180004042  jge     short loc_18000404A
0x180004044  movzx   ecx, r15w
0x180004048  jmp     short loc_180004051
0x18000404a  cmp     ecx, ebp
0x18000404c  jle     short loc_180004051
0x18000404e  movzx   ecx, bp
0x180004051  movsx   eax, dx
0x180004054  dec     eax
0x180004056  cmp     eax, r15d
0x180004059  jge     short loc_180004061
0x18000405b  movzx   eax, r15w
0x18000405f  jmp     short loc_180004067
0x180004061  cmp     eax, ebp
0x180004063  jle     short loc_180004067
0x180004065  mov     eax, ebp
0x180004067  movzx   edx, ax
0x18000406a  add     r8d, 0FFFFFFFFh
0x18000406e  jnz     short loc_180004026
0x180004070  movsx   eax, cx
0x180004073  add     eax, 0FFFFFFF8h
0x180004076  cmp     eax, r15d
0x180004079  jge     short loc_180004081
0x18000407b  movzx   eax, r15w
0x18000407f  jmp     short loc_180004087
0x180004081  cmp     eax, ebp
0x180004083  jle     short loc_180004087
0x180004085  mov     eax, ebp
0x180004087  movsx   rax, ax
0x18000408b  lea     r9, FAC
0x180004092  mov     ecx, 6
0x180004097  movsx   r9d, word ptr [r9+rax*2]
0x18000409c  movsx   eax, dx
0x18000409f  sub     ecx, eax
0x1800040a1  cmp     ecx, r15d
0x1800040a4  jge     short loc_1800040AC
0x1800040a6  movzx   edi, r15w
0x1800040aa  jmp     short loc_1800040B7
0x1800040ac  cmp     ecx, ebp
0x1800040ae  jle     short loc_1800040B4
0x1800040b0  mov     edi, ebp
0x1800040b2  jmp     short loc_1800040B7
0x1800040b4  movzx   edi, cx
0x1800040b7  movsx   r8d, di
0x1800040bb  mov     r10d, r8d
0x1800040be  lea     eax, [r8-1]
0x1800040c2  cmp     eax, r15d
0x1800040c5  jge     short loc_1800040F6
0x1800040c7  movzx   eax, r15w
0x1800040cb  movsx   ecx, ax
0x1800040ce  mov     eax, r13d
0x1800040d1  neg     ecx
0x1800040d3  sar     eax, cl
0x1800040d5  mov     r11d, r9d
0x1800040d8  mov     rdx, r12
0x1800040db  movsx   r9d, ax
0x1800040df  movzx   eax, word ptr [r14+rdx*2]
0x1800040e4  add     ax, ax
0x1800040e7  cwde
0x1800040e8  add     eax, 0FFFFFFF9h
0x1800040eb  cmp     eax, r15d
0x1800040ee  jge     short loc_18000410D
0x1800040f0  movzx   eax, r15w
0x1800040f4  jmp     short loc_180004113
0x1800040f6  cmp     eax, ebp
0x1800040f8  jle     short loc_1800040FF
0x1800040fa  movzx   eax, bp
0x1800040fd  jmp     short loc_180004104
0x1800040ff  test    ax, ax
0x180004102  js      short loc_1800040CB
0x180004104  mov     cl, al
0x180004106  mov     eax, r13d
0x180004109  shl     eax, cl
0x18000410b  jmp     short loc_1800040D5
0x18000410d  cmp     eax, ebp
0x18000410f  jle     short loc_180004113
0x180004111  mov     eax, ebp
0x180004113  shl     ax, 0Ch
0x180004117  mov     ecx, 3FFFFFFFh
0x18000411c  cwde
0x18000411d  imul    eax, r11d
0x180004121  add     eax, 4000h
0x180004126  cmp     eax, 40000000h
0x18000412b  cmovge  eax, ecx
0x18000412e  shr     eax, 0Fh
0x180004131  cwde
0x180004132  add     eax, r9d
0x180004135  cmp     eax, r15d
0x180004138  jge     short loc_180004140
0x18000413a  movzx   eax, r15w
0x18000413e  jmp     short loc_180004146
0x180004140  cmp     eax, ebp
0x180004142  jle     short loc_180004146
0x180004144  mov     eax, ebp
0x180004146  cwde
0x180004147  test    di, di
0x18000414a  js      short loc_180004156
0x18000414c  mov     ecx, r10d
0x18000414f  mov     r8d, r10d
0x180004152  sar     eax, cl
0x180004154  jmp     short loc_18000415D
0x180004156  mov     ecx, r8d
0x180004159  neg     ecx
0x18000415b  shl     eax, cl
0x18000415d  mov     [rsp+rdx*2+68h+var_68], ax
0x180004161  add     rdx, r13
0x180004164  cmp     rdx, 0Dh
0x180004168  jnz     loc_1800040DF
0x18000416e  movsxd  rax, r12d
0x180004171  lea     ecx, [rdx+1Bh]
0x180004174  movsx   rax, ax
0x180004178  mov     rdi, rbx
0x18000417b  rep stosw
0x18000417e  mov     r8d, r12d
0x180004181  lea     ecx, [rsi+r8*2]
0x180004185  mov     edi, r8d
0x180004188  add     ecx, r8d
0x18000418b  add     r8d, r13d
0x18000418e  movzx   eax, [rsp+rdi*2+68h+var_68]
0x180004192  mov     [rbx+rcx*2], ax
0x180004196  cmp     r8d, 0Ch
0x18000419a  jbe     short loc_180004181
0x18000419c  add     rsp, 28h
0x1800041a0  pop     r15
0x1800041a2  pop     r14
0x1800041a4  pop     r13
0x1800041a6  pop     r12
0x1800041a8  pop     rdi
0x1800041a9  pop     rsi
0x1800041aa  pop     rbp
0x1800041ab  pop     rbx
0x1800041ac  retn
```
