# sqlite3Parser

- ea: `0x140065c88`
- end: `0x140065e3f`
- name: `sqlite3Parser`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14006c1ac`

## callees

- `0x1400560c4`
- `0x140065c88`
- `0x1400a3dbc`
- `0x1400a3e24`
- `0x1400a40bc`

## string_xrefs

- `0x140065e12`: `incomplete input`

## pseudocode

```c
unsigned __int16 __fastcall sqlite3Parser(__int64 *a1, unsigned int a2, __int128 *a3)
{
  _QWORD *v3; // rdi
  unsigned __int16 result; // ax
  unsigned __int16 v8; // dx
  __int64 v9; // r10
  int v10; // r11d
  __int64 v11; // r8
  int v12; // ecx
  __int64 v13; // rdx
  unsigned __int64 v14; // rax
  __int64 v15; // rdx
  unsigned __int64 v16; // rcx
  __int128 v17; // xmm0
  __int64 v18; // rdi
  __int64 v19; // rcx
  __int128 v20; // [rsp+30h] [rbp-58h] BYREF
  __int128 v21[4]; // [rsp+40h] [rbp-48h] BYREF

  v3 = (_QWORD *)a1[1];
  for ( result = *(_WORD *)*a1; ; result = yy_reduce(a1, v13, a2, (__int64 *)&v20, v3) )
  {
    if ( result <= 0x23Eu )
    {
      v8 = a2;
      v9 = result;
      v10 = (unsigned __int16)word_1400B51B0[result];
      v11 = v10 + (unsigned int)(unsigned __int16)a2;
      if ( word_1400B3EB0[v11] == (_WORD)a2 )
      {
LABEL_6:
        result = word_1400B2D40[v11];
      }
      else
      {
        while ( 1 )
        {
          v12 = (unsigned __int16)word_1400B5640[v8];
          if ( !(_WORD)v12 )
            break;
          v11 = (unsigned int)(v10 + v12);
          v8 = word_1400B5640[v8];
          if ( word_1400B3EB0[v11] == (_WORD)v12 )
            goto LABEL_6;
        }
        v14 = (unsigned int)v11 - (unsigned __int64)v8;
        if ( word_1400B3F7A[v14] == 101 && v8 )
          result = word_1400B2E0A[v14];
        else
          result = word_1400B18D0[v9];
      }
    }
    if ( result < 0x4D7u )
      break;
    v13 = (unsigned int)result - 1239;
    if ( !*((_BYTE *)qword_1400B1F20 + v13) && *a1 >= (unsigned __int64)a1[302] )
      return yyStackOverflow(a1);
    v20 = *a3;
  }
  if ( result > 0x4D3u )
  {
    v18 = a1[1];
    if ( result == 1237 )
    {
      *a1 -= 24;
      a1[1] = v18;
    }
    else
    {
      v19 = a1[1];
      v20 = *a3;
      v21[0] = v20;
      if ( *(_BYTE *)v20 )
        sqlite3ErrorMsg(v19, "near \"%T\": syntax error", &v20);
      else
        sqlite3ErrorMsg(v19, "incomplete input");
      a1[1] = v18;
      return yy_destructor(a1, (unsigned __int16)a2, v21);
    }
  }
  else
  {
    v15 = *a1;
    v16 = *a1 + 24;
    *a1 = v16;
    if ( v16 > a1[302] )
    {
      *a1 = v15;
      return yyStackOverflow(a1);
    }
    if ( result > 0x23Eu )
      result += 406;
    v17 = *a3;
    *(_WORD *)v16 = result;
    *(_WORD *)(v16 + 2) = a2;
    *(_OWORD *)(v16 + 8) = v17;
  }
  return result;
}

```

## disassembly

```asm
0x140065c88  push    rbx
0x140065c8a  push    rbp
0x140065c8b  push    rsi
0x140065c8c  push    rdi
0x140065c8d  push    r14
0x140065c8f  push    r15
0x140065c91  sub     rsp, 58h
0x140065c95  mov     rax, [rcx]
0x140065c98  lea     r14, __ImageBase
0x140065c9f  mov     rdi, [rcx+8]
0x140065ca3  mov     rsi, r8
0x140065ca6  mov     ebp, edx
0x140065ca8  mov     rbx, rcx
0x140065cab  mov     r15d, 23Eh
0x140065cb1  movzx   eax, word ptr [rax]
0x140065cb4  cmp     ax, r15w
0x140065cb8  ja      short loc_140065D06
0x140065cba  movzx   edx, bp
0x140065cbd  movzx   r10d, ax
0x140065cc1  movzx   r11d, ds:rva word_1400B51B0[r14+r10*2]
0x140065cca  lea     r8d, [r11+rdx]
0x140065cce  cmp     ds:rva word_1400B3EB0[r14+r8*2], dx
0x140065cd7  jz      short loc_140065CFD
0x140065cd9  movzx   r9d, dx
0x140065cdd  movzx   ecx, ds:rva word_1400B5640[r14+r9*2]
0x140065ce6  test    cx, cx
0x140065ce9  jz      short loc_140065D53
0x140065ceb  lea     r8d, [r11+rcx]
0x140065cef  movzx   edx, cx
0x140065cf2  cmp     ds:rva word_1400B3EB0[r14+r8*2], cx
0x140065cfb  jnz     short loc_140065CD9
0x140065cfd  movzx   eax, ds:rva word_1400B2D40[r14+r8*2]
0x140065d06  mov     ecx, 4D7h
0x140065d0b  cmp     ax, cx
0x140065d0e  jb      short loc_140065D80
0x140065d10  movzx   edx, ax
0x140065d13  add     edx, 0FFFFFB29h
0x140065d19  cmp     byte ptr [rdx+r14+0B1F20h], 0
0x140065d22  jnz     short loc_140065D30
0x140065d24  mov     rax, [rbx+970h]
0x140065d2b  cmp     [rbx], rax
0x140065d2e  jnb     short loc_140065DA0
0x140065d30  movups  xmm0, xmmword ptr [rsi]
0x140065d33  lea     r9, [rsp+88h+var_58]
0x140065d38  mov     [rsp+88h+var_68], rdi
0x140065d3d  mov     r8d, ebp
0x140065d40  mov     rcx, rbx
0x140065d43  movdqu  [rsp+88h+var_58], xmm0
0x140065d49  call    yy_reduce
0x140065d4e  jmp     loc_140065CB4
0x140065d53  mov     eax, r8d
0x140065d56  sub     rax, r9
0x140065d59  cmp     ds:rva word_1400B3F7A[r14+rax*2], 65h ; 'e'
0x140065d63  jnz     short loc_140065D75
0x140065d65  test    dx, dx
0x140065d68  jz      short loc_140065D75
0x140065d6a  movzx   eax, ds:rva word_1400B2E0A[r14+rax*2]
0x140065d73  jmp     short loc_140065D06
0x140065d75  movzx   eax, ds:rva word_1400B18D0[r14+r10*2]
0x140065d7e  jmp     short loc_140065D06
0x140065d80  mov     ecx, 4D3h
0x140065d85  cmp     ax, cx
0x140065d88  ja      short loc_140065DCC
0x140065d8a  mov     rdx, [rbx]
0x140065d8d  lea     rcx, [rdx+18h]
0x140065d91  mov     [rbx], rcx
0x140065d94  cmp     rcx, [rbx+970h]
0x140065d9b  jbe     short loc_140065DAD
0x140065d9d  mov     [rbx], rdx
0x140065da0  mov     rcx, rbx
0x140065da3  call    yyStackOverflow
0x140065da8  jmp     loc_140065E32
0x140065dad  cmp     ax, r15w
0x140065db1  jbe     short loc_140065DBB
0x140065db3  mov     edx, 196h
0x140065db8  add     ax, dx
0x140065dbb  movups  xmm0, xmmword ptr [rsi]
0x140065dbe  mov     [rcx], ax
0x140065dc1  mov     [rcx+2], bp
0x140065dc5  movdqu  xmmword ptr [rcx+8], xmm0
0x140065dca  jmp     short loc_140065E32
0x140065dcc  mov     rdi, [rbx+8]
0x140065dd0  mov     ecx, 4D5h
0x140065dd5  cmp     ax, cx
0x140065dd8  jnz     short loc_140065DE4
0x140065dda  add     qword ptr [rbx], 0FFFFFFFFFFFFFFE8h
0x140065dde  mov     [rbx+8], rdi
0x140065de2  jmp     short loc_140065E32
0x140065de4  movups  xmm0, xmmword ptr [rsi]
0x140065de7  mov     rcx, rdi
0x140065dea  movq    rax, xmm0
0x140065def  movaps  [rsp+88h+var_58], xmm0
0x140065df4  movdqu  [rsp+88h+var_48], xmm0
0x140065dfa  cmp     byte ptr [rax], 0
0x140065dfd  jz      short loc_140065E12
0x140065dff  lea     r8, [rsp+88h+var_58]
0x140065e04  lea     rdx, aNearTSyntaxErr; "near \"%T\": syntax error"
0x140065e0b  call    sqlite3ErrorMsg
0x140065e10  jmp     short loc_140065E1E
0x140065e12  lea     rdx, aIncompleteInpu; "incomplete input"
0x140065e19  call    sqlite3ErrorMsg
0x140065e1e  lea     r8, [rsp+88h+var_48]
0x140065e23  mov     [rbx+8], rdi
0x140065e27  movzx   edx, bp
0x140065e2a  mov     rcx, rbx
0x140065e2d  call    yy_destructor
0x140065e32  add     rsp, 58h
0x140065e36  pop     r15
0x140065e38  pop     r14
0x140065e3a  pop     rdi
0x140065e3b  pop     rsi
0x140065e3c  pop     rbp
0x140065e3d  pop     rbx
0x140065e3e  retn
```
