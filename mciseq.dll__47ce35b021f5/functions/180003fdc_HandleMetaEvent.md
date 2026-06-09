# HandleMetaEvent

- ea: `0x180003fdc`
- end: `0x1800042a7`
- name: `HandleMetaEvent`
- size: `715`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180004588`
- `0x1800048fc`
- `0x180005a1c`

## callees

- `0x180003a34`
- `0x180003f68`
- `0x180003fdc`
- `0x180004fa4`
- `0x1800058bc`

## pseudocode

```c
__int64 __fastcall HandleMetaEvent(__int64 a1, __int64 a2, int a3)
{
  unsigned __int64 v6; // r14
  int VarLen; // eax
  int v8; // r12d
  int v9; // esi
  int v10; // ecx
  __int64 v11; // r14
  char v12; // al
  int v13; // r15d
  int v14; // r14d
  int v15; // esi
  unsigned __int8 v16; // al
  char v17; // r15
  char v18; // r14
  char v19; // si
  char v20; // al
  int v21; // r14d
  int v22; // esi
  int v23; // edx
  int v24; // eax
  unsigned int v25; // eax
  __int64 result; // rax
  int v27; // ebp
  int v28; // ebp
  int v29; // ebp
  _BYTE v30[8]; // [rsp+20h] [rbp-48h]
  __int64 v31; // [rsp+28h] [rbp-40h]

  v31 = 0;
  v6 = (unsigned __int8)LookByte(a2);
  if ( !*(_DWORD *)a2 )
    ++*(_QWORD *)(a2 + 24);
  VarLen = GetVarLen(a2);
  v8 = VarLen;
  v9 = 0;
  v10 = *(unsigned __int16 *)(a1 + 2 * (v6 >> 4) + 140);
  if ( !_bittest(&v10, v6 & 0xF) )
    goto LABEL_49;
  if ( *(_DWORD *)a2 )
    return 1;
  if ( (_BYTE)v6 == 47 )
  {
    *(_DWORD *)(a2 + 56) = 1;
    goto LABEL_49;
  }
  if ( (_BYTE)v6 != 81 )
  {
    if ( (_BYTE)v6 != 84 )
    {
      if ( (_BYTE)v6 != 88 )
      {
        if ( (_BYTE)v6 == 127 && VarLen >= 3 && !*(_DWORD *)(a2 + 4) )
        {
          v11 = 0;
          do
          {
            v12 = LookByte(a2);
            if ( !*(_DWORD *)a2 )
              ++*(_QWORD *)(a2 + 24);
            v30[v11] = v12;
            ++v9;
            ++v11;
          }
          while ( v9 < 3 );
          if ( !v30[0] && !v30[1] && v30[2] == 65 )
            *(_DWORD *)(a1 + 2096) |= 2u;
        }
        goto LABEL_49;
      }
      v13 = (unsigned __int8)LookByte(a2);
      if ( !*(_DWORD *)a2 )
        ++*(_QWORD *)(a2 + 24);
      v14 = (unsigned __int8)LookByte(a2);
      if ( !*(_DWORD *)a2 )
        ++*(_QWORD *)(a2 + 24);
      v15 = (unsigned __int8)LookByte(a2);
      if ( !*(_DWORD *)a2 )
        ++*(_QWORD *)(a2 + 24);
      v16 = LookByte(a2);
      if ( !*(_DWORD *)a2 )
      {
        ++*(_QWORD *)(a2 + 24);
        *(_DWORD *)(a1 + 56) = v13;
        *(_DWORD *)(a1 + 60) = v14;
        *(_DWORD *)(a1 + 64) = v15;
        *(_DWORD *)(a1 + 68) = v16;
      }
      goto LABEL_37;
    }
    if ( a2 == *(_QWORD *)(a1 + 88) )
    {
      v17 = LookByte(a2);
      if ( !*(_DWORD *)a2 )
        ++*(_QWORD *)(a2 + 24);
      v18 = LookByte(a2);
      if ( !*(_DWORD *)a2 )
        ++*(_QWORD *)(a2 + 24);
      v19 = LookByte(a2);
      if ( !*(_DWORD *)a2 )
        ++*(_QWORD *)(a2 + 24);
      v20 = LookByte(a2);
      if ( !*(_DWORD *)a2 )
      {
        ++*(_QWORD *)(a2 + 24);
        *(_BYTE *)(a1 + 51) = v20;
        *(_DWORD *)(a1 + 52) = v31;
        *(_DWORD *)(a1 + 44) = 0;
        *(_BYTE *)(a1 + 48) = v17;
        *(_BYTE *)(a1 + 49) = v18;
        *(_BYTE *)(a1 + 50) = v19;
      }
LABEL_37:
      v9 = 4;
    }
LABEL_49:
    if ( !*(_DWORD *)a2 )
    {
      SkipBytes(a2, v8 - v9);
      if ( *(_DWORD *)a2 )
      {
        v27 = a3 - 1;
        if ( v27 )
        {
          v28 = v27 - 1;
          if ( v28 && (v29 = v28 - 1) != 0 )
          {
            if ( v29 == 1 )
              *(_DWORD *)a2 = 279;
          }
          else
          {
            *(_DWORD *)a2 = 280;
          }
        }
        else
        {
          *(_DWORD *)a2 = 278;
        }
      }
    }
    return 1;
  }
  if ( a2 != *(_QWORD *)(a1 + 88) )
    goto LABEL_49;
  v21 = (unsigned __int8)LookByte(a2);
  if ( !*(_DWORD *)a2 )
    ++*(_QWORD *)(a2 + 24);
  v22 = (unsigned __int8)LookByte(a2);
  if ( !*(_DWORD *)a2 )
    ++*(_QWORD *)(a2 + 24);
  v23 = (unsigned __int8)LookByte(a2);
  if ( *(_DWORD *)a2 )
  {
    v9 = 3;
    goto LABEL_49;
  }
  ++*(_QWORD *)(a2 + 24);
  v24 = v22 + (v21 << 8);
  v9 = 3;
  v25 = (unsigned int)(v23 + (v24 << 8)) / *(_DWORD *)(a1 + 4);
  *(_DWORD *)(a1 + 40) = v25;
  if ( a3 != 4 )
    goto LABEL_49;
  result = AddTempoMapItem(a1, v25, *(_DWORD *)(a2 + 8));
  if ( (_DWORD)result )
    goto LABEL_49;
  return result;
}

```

## disassembly

```asm
0x180003fdc  mov     [rsp+arg_10], rbx
0x180003fe1  push    rbp
0x180003fe2  push    rsi
0x180003fe3  push    rdi
0x180003fe4  push    r12
0x180003fe6  push    r13
0x180003fe8  push    r14
0x180003fea  push    r15
0x180003fec  sub     rsp, 30h
0x180003ff0  mov     rdi, rcx
0x180003ff3  xor     eax, eax
0x180003ff5  xor     r15d, r15d
0x180003ff8  mov     [rsp+68h+var_40], rax
0x180003ffd  mov     rcx, rdx
0x180004000  mov     r13d, r15d
0x180004003  mov     ebp, r8d
0x180004006  mov     rbx, rdx
0x180004009  call    LookByte
0x18000400e  movzx   r14d, al
0x180004012  cmp     [rbx], r15d
0x180004015  jnz     short loc_18000401B
0x180004017  inc     qword ptr [rbx+18h]
0x18000401b  mov     rcx, rbx
0x18000401e  call    GetVarLen
0x180004023  mov     rcx, r14
0x180004026  mov     edx, r14d
0x180004029  shr     rcx, 4
0x18000402d  and     edx, 0Fh
0x180004030  mov     r12d, eax
0x180004033  mov     esi, r15d
0x180004036  movzx   ecx, word ptr [rdi+rcx*2+8Ch]
0x18000403e  bt      ecx, edx
0x180004041  jnb     loc_180004248
0x180004047  cmp     [rbx], r15d
0x18000404a  jnz     loc_18000428A
0x180004050  cmp     r14b, 2Fh ; '/'
0x180004054  jz      loc_180004241
0x18000405a  cmp     r14b, 51h ; 'Q'
0x18000405e  jz      loc_1800041C4
0x180004064  cmp     r14b, 54h ; 'T'
0x180004068  jz      loc_180004147
0x18000406e  cmp     r14b, 58h ; 'X'
0x180004072  jz      short loc_1800040E1
0x180004074  cmp     r14b, 7Fh
0x180004078  jnz     loc_180004248
0x18000407e  cmp     eax, 3
0x180004081  jl      loc_180004248
0x180004087  cmp     [rbx+4], r15d
0x18000408b  jnz     loc_180004248
0x180004091  mov     r14, r15
0x180004094  mov     rcx, rbx
0x180004097  call    LookByte
0x18000409c  cmp     [rbx], r15d
0x18000409f  jnz     short loc_1800040A5
0x1800040a1  inc     qword ptr [rbx+18h]
0x1800040a5  mov     [rsp+r14+68h+var_48], al
0x1800040aa  inc     esi
0x1800040ac  inc     r14
0x1800040af  cmp     esi, 3
0x1800040b2  jl      short loc_180004094
0x1800040b4  cmp     [rsp+68h+var_48], r15b
0x1800040b9  jnz     loc_180004248
0x1800040bf  cmp     [rsp+68h+var_47], r15b
0x1800040c4  jnz     loc_180004248
0x1800040ca  cmp     [rsp+68h+var_46], 41h ; 'A'
0x1800040cf  jnz     loc_180004248
0x1800040d5  or      dword ptr [rdi+830h], 2
0x1800040dc  jmp     loc_180004248
0x1800040e1  mov     rcx, rbx
0x1800040e4  call    LookByte
0x1800040e9  movzx   r15d, al
0x1800040ed  cmp     [rbx], r13d
0x1800040f0  jnz     short loc_1800040F6
0x1800040f2  inc     qword ptr [rbx+18h]
0x1800040f6  mov     rcx, rbx
0x1800040f9  call    LookByte
0x1800040fe  movzx   r14d, al
0x180004102  cmp     [rbx], r13d
0x180004105  jnz     short loc_18000410B
0x180004107  inc     qword ptr [rbx+18h]
0x18000410b  mov     rcx, rbx
0x18000410e  call    LookByte
0x180004113  movzx   esi, al
0x180004116  cmp     [rbx], r13d
0x180004119  jnz     short loc_18000411F
0x18000411b  inc     qword ptr [rbx+18h]
0x18000411f  mov     rcx, rbx
0x180004122  call    LookByte
0x180004127  cmp     [rbx], r13d
0x18000412a  jnz     loc_1800041B7
0x180004130  inc     qword ptr [rbx+18h]
0x180004134  mov     [rdi+38h], r15d
0x180004138  mov     [rdi+3Ch], r14d
0x18000413c  movzx   eax, al
0x18000413f  mov     [rdi+40h], esi
0x180004142  mov     [rdi+44h], eax
0x180004145  jmp     short loc_1800041B7
0x180004147  cmp     rbx, [rdi+58h]
0x18000414b  jnz     loc_180004248
0x180004151  mov     rcx, rbx
0x180004154  call    LookByte
0x180004159  mov     r15b, al
0x18000415c  cmp     [rbx], esi
0x18000415e  jnz     short loc_180004164
0x180004160  inc     qword ptr [rbx+18h]
0x180004164  mov     rcx, rbx
0x180004167  call    LookByte
0x18000416c  mov     r14b, al
0x18000416f  cmp     [rbx], esi
0x180004171  jnz     short loc_180004177
0x180004173  inc     qword ptr [rbx+18h]
0x180004177  mov     rcx, rbx
0x18000417a  call    LookByte
0x18000417f  mov     sil, al
0x180004182  cmp     [rbx], r13d
0x180004185  jnz     short loc_18000418B
0x180004187  inc     qword ptr [rbx+18h]
0x18000418b  mov     rcx, rbx
0x18000418e  call    LookByte
0x180004193  cmp     [rbx], r13d
0x180004196  jnz     short loc_1800041B7
0x180004198  inc     qword ptr [rbx+18h]
0x18000419c  mov     [rdi+33h], al
0x18000419f  mov     rax, [rsp+68h+var_40]
0x1800041a4  mov     [rdi+34h], eax
0x1800041a7  mov     [rdi+2Ch], r13d
0x1800041ab  mov     [rdi+30h], r15b
0x1800041af  mov     [rdi+31h], r14b
0x1800041b3  mov     [rdi+32h], sil
0x1800041b7  mov     esi, 4
0x1800041bc  xor     r15d, r15d
0x1800041bf  jmp     loc_180004248
0x1800041c4  cmp     rbx, [rdi+58h]
0x1800041c8  jnz     short loc_180004248
0x1800041ca  mov     rcx, rbx
0x1800041cd  call    LookByte
0x1800041d2  movzx   r14d, al
0x1800041d6  cmp     [rbx], r15d
0x1800041d9  jnz     short loc_1800041DF
0x1800041db  inc     qword ptr [rbx+18h]
0x1800041df  mov     rcx, rbx
0x1800041e2  call    LookByte
0x1800041e7  movzx   esi, al
0x1800041ea  cmp     [rbx], r15d
0x1800041ed  jnz     short loc_1800041F3
0x1800041ef  inc     qword ptr [rbx+18h]
0x1800041f3  mov     rcx, rbx
0x1800041f6  call    LookByte
0x1800041fb  movzx   edx, al
0x1800041fe  cmp     [rbx], r15d
0x180004201  jnz     short loc_18000423A
0x180004203  inc     qword ptr [rbx+18h]
0x180004207  mov     eax, r14d
0x18000420a  shl     eax, 8
0x18000420d  add     eax, esi
0x18000420f  mov     esi, 3
0x180004214  shl     eax, 8
0x180004217  add     eax, edx
0x180004219  xor     edx, edx
0x18000421b  div     dword ptr [rdi+4]
0x18000421e  mov     [rdi+28h], eax
0x180004221  cmp     ebp, 4
0x180004224  jnz     short loc_180004248
0x180004226  mov     r8d, [rbx+8]
0x18000422a  mov     edx, eax
0x18000422c  mov     rcx, rdi
0x18000422f  call    AddTempoMapItem
0x180004234  test    eax, eax
0x180004236  jnz     short loc_180004248
0x180004238  jmp     short loc_18000428F
0x18000423a  mov     esi, 3
0x18000423f  jmp     short loc_180004248
0x180004241  mov     dword ptr [rbx+38h], 1
0x180004248  cmp     [rbx], r15d
0x18000424b  jnz     short loc_18000428A
0x18000424d  sub     r12d, esi
0x180004250  mov     rcx, rbx
0x180004253  mov     edx, r12d
0x180004256  call    SkipBytes
0x18000425b  cmp     [rbx], r15d
0x18000425e  jz      short loc_18000428A
0x180004260  sub     ebp, 1
0x180004263  jz      short loc_180004284
0x180004265  sub     ebp, 1
0x180004268  jz      short loc_18000427C
0x18000426a  sub     ebp, 1
0x18000426d  jz      short loc_18000427C
0x18000426f  cmp     ebp, 1
0x180004272  jnz     short loc_18000428A
0x180004274  mov     dword ptr [rbx], 117h
0x18000427a  jmp     short loc_18000428A
0x18000427c  mov     dword ptr [rbx], 118h
0x180004282  jmp     short loc_18000428A
0x180004284  mov     dword ptr [rbx], 116h
0x18000428a  mov     eax, 1
0x18000428f  mov     rbx, [rsp+68h+arg_10]
0x180004297  add     rsp, 30h
0x18000429b  pop     r15
0x18000429d  pop     r14
0x18000429f  pop     r13
0x1800042a1  pop     r12
0x1800042a3  pop     rdi
0x1800042a4  pop     rsi
0x1800042a5  pop     rbp
0x1800042a6  retn
```
