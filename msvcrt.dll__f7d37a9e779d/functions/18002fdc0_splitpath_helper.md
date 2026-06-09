# _splitpath_helper

- ea: `0x18002fdc0`
- end: `0x180030069`
- name: `_splitpath_helper`
- size: `681`
- prototype: `__int64 __usercall@<rax>(unsigned __int8 *Src@<rcx>, unsigned __int8 *Dst@<rdx>, __int64, unsigned __int8 *, __int64, unsigned __int8 *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002fd30`

## callees

- `0x180007f00`
- `0x180024ad0`
- `0x180027eb0`
- `0x18002f050`
- `0x18002fdc0`

## pseudocode

```c
__int64 __fastcall splitpath_helper(
        unsigned __int8 *Src,
        unsigned __int8 *Dst,
        unsigned __int64 a3,
        unsigned __int8 *a4,
        unsigned __int64 a5,
        unsigned __int8 *Dsta,
        unsigned __int64 a7,
        unsigned __int8 *a8,
        unsigned __int64 a9)
{
  const unsigned __int8 *v11; // rdi
  int v12; // ecx
  __int64 v13; // rax
  const unsigned __int8 *v14; // rbx
  signed __int8 v15; // al
  const unsigned __int8 *v16; // rbp
  const unsigned __int8 *v17; // rbx
  const unsigned __int8 *v18; // r14
  unsigned __int8 v19; // al
  size_t v20; // rbx
  size_t v21; // rbx
  unsigned __int64 v23; // [rsp+80h] [rbp+18h]

  v23 = a3;
  v11 = Src;
  if ( !Src )
    goto LABEL_4;
  if ( Dst )
  {
    if ( !a3 )
      goto LABEL_4;
  }
  else if ( a3 )
  {
LABEL_4:
    v12 = 1;
    goto LABEL_62;
  }
  if ( a4 )
  {
    if ( !a5 )
      goto LABEL_4;
  }
  else if ( a5 )
  {
    goto LABEL_4;
  }
  if ( Dsta )
  {
    if ( !a7 )
      goto LABEL_4;
  }
  else if ( a7 )
  {
    goto LABEL_4;
  }
  if ( a8 )
  {
    if ( !a9 )
      goto LABEL_4;
  }
  else if ( a9 )
  {
    goto LABEL_4;
  }
  v12 = 0;
  v13 = 1;
  v14 = v11;
  do
  {
    if ( !*v14 )
      break;
    ++v14;
    --v13;
  }
  while ( v13 );
  if ( *v14 == 58 )
  {
    if ( Dst )
    {
      if ( a3 < 3 )
        goto LABEL_63;
      mbsnbcpy_s(Dst, 0xFFFFFFFFFFFFFFFFuLL, v11, 2u);
    }
    v11 = v14 + 1;
  }
  else if ( Dst )
  {
    *Dst = 0;
  }
  v15 = *v11;
  v16 = 0;
  v17 = v11;
  if ( !*v11 )
    goto LABEL_43;
  v18 = 0;
  do
  {
    if ( ismbblead(v15) )
    {
      ++v17;
    }
    else
    {
      v19 = *v17;
      if ( *v17 == 47 || v19 == 92 )
      {
        v18 = v17 + 1;
      }
      else if ( v19 == 46 )
      {
        v16 = v17;
      }
    }
    v15 = *++v17;
  }
  while ( *v17 );
  if ( v18 )
  {
    if ( a4 )
    {
      if ( a5 <= v18 - v11 )
      {
        v12 = 0;
        goto LABEL_61;
      }
      mbsnbcpy_s(a4, 0xFFFFFFFFFFFFFFFFuLL, v11, v18 - v11);
    }
    v11 = v18;
  }
  else
  {
LABEL_43:
    if ( a4 )
      *a4 = 0;
  }
  if ( !v16 || v16 < v11 )
  {
    if ( Dsta )
    {
      v21 = v17 - v11;
      if ( a7 <= v21 )
        goto LABEL_59;
      mbsnbcpy_s(Dsta, 0xFFFFFFFFFFFFFFFFuLL, v11, v21);
    }
    if ( a8 )
      *a8 = 0;
    return 0;
  }
  if ( !Dsta )
  {
LABEL_50:
    if ( !a8 )
      return 0;
    v20 = v17 - v16;
    if ( a9 > v20 )
    {
      mbsnbcpy_s(a8, 0xFFFFFFFFFFFFFFFFuLL, v16, v20);
      return 0;
    }
    goto LABEL_59;
  }
  if ( a7 > v16 - v11 )
  {
    mbsnbcpy_s(Dsta, 0xFFFFFFFFFFFFFFFFuLL, v11, v16 - v11);
    goto LABEL_50;
  }
LABEL_59:
  v12 = 0;
LABEL_61:
  a3 = v23;
LABEL_62:
  if ( Dst )
  {
LABEL_63:
    if ( a3 )
      *Dst = 0;
  }
  if ( a4 && a5 )
    *a4 = 0;
  if ( Dsta && a7 )
    *Dsta = 0;
  if ( a8 && a9 )
    *a8 = 0;
  if ( !v11 || v12 )
  {
    *errno() = 22;
    invalid_parameter(0, 0, 0, 0, 0);
  }
  *errno() = 34;
  return 34;
}

```

## disassembly

```asm
0x18002fdc0  mov     [rsp+arg_8], rbx
0x18002fdc5  mov     [rsp+arg_10], r8
0x18002fdca  push    rbp
0x18002fdcb  push    rsi
0x18002fdcc  push    rdi
0x18002fdcd  push    r12
0x18002fdcf  push    r13
0x18002fdd1  push    r14
0x18002fdd3  push    r15
0x18002fdd5  sub     rsp, 30h
0x18002fdd9  mov     rsi, [rsp+68h+arg_38]
0x18002fde1  mov     r12, rdx
0x18002fde4  mov     r15, [rsp+68h+Dst]
0x18002fdec  xor     edx, edx
0x18002fdee  mov     r13, r9
0x18002fdf1  mov     rdi, rcx
0x18002fdf4  test    rcx, rcx
0x18002fdf7  jz      short loc_18002FE03
0x18002fdf9  test    r12, r12
0x18002fdfc  jnz     short loc_18002FE0D
0x18002fdfe  test    r8, r8
0x18002fe01  jz      short loc_18002FE12
0x18002fe03  mov     ecx, 1
0x18002fe08  jmp     loc_18002FFD1
0x18002fe0d  test    r8, r8
0x18002fe10  jz      short loc_18002FE03
0x18002fe12  test    r13, r13
0x18002fe15  jnz     short loc_18002FE23
0x18002fe17  cmp     [rsp+68h+arg_20], rdx
0x18002fe1f  jnz     short loc_18002FE03
0x18002fe21  jmp     short loc_18002FE2D
0x18002fe23  cmp     [rsp+68h+arg_20], rdx
0x18002fe2b  jz      short loc_18002FE03
0x18002fe2d  test    r15, r15
0x18002fe30  jnz     short loc_18002FE3E
0x18002fe32  cmp     [rsp+68h+arg_30], rdx
0x18002fe3a  jnz     short loc_18002FE03
0x18002fe3c  jmp     short loc_18002FE48
0x18002fe3e  cmp     [rsp+68h+arg_30], rdx
0x18002fe46  jz      short loc_18002FE03
0x18002fe48  test    rsi, rsi
0x18002fe4b  jnz     short loc_18002FE59
0x18002fe4d  cmp     [rsp+68h+arg_40], rdx
0x18002fe55  jnz     short loc_18002FE03
0x18002fe57  jmp     short loc_18002FE63
0x18002fe59  cmp     [rsp+68h+arg_40], rdx
0x18002fe61  jz      short loc_18002FE03
0x18002fe63  mov     ecx, edx
0x18002fe65  mov     [rsp+68h+arg_0], edx
0x18002fe69  mov     eax, 1
0x18002fe6e  mov     rbx, rdi
0x18002fe71  cmp     [rbx], dl
0x18002fe73  jz      short loc_18002FE7E
0x18002fe75  inc     rbx
0x18002fe78  sub     rax, 1
0x18002fe7c  jnz     short loc_18002FE71
0x18002fe7e  cmp     byte ptr [rbx], 3Ah ; ':'
0x18002fe81  jnz     short loc_18002FEAF
0x18002fe83  test    r12, r12
0x18002fe86  jz      short loc_18002FEA9
0x18002fe88  cmp     r8, 3
0x18002fe8c  jb      loc_18002FFD6
0x18002fe92  mov     r9d, 2; MaxCount
0x18002fe98  mov     r8, rdi; Src
0x18002fe9b  or      rdx, 0FFFFFFFFFFFFFFFFh; SizeInBytes
0x18002fe9f  mov     rcx, r12; Dst
0x18002fea2  call    _mbsnbcpy_s
0x18002fea7  xor     edx, edx
0x18002fea9  lea     rdi, [rbx+1]
0x18002fead  jmp     short loc_18002FEB8
0x18002feaf  test    r12, r12
0x18002feb2  jz      short loc_18002FEB8
0x18002feb4  mov     [r12], dl
0x18002feb8  mov     al, [rdi]
0x18002feba  mov     rbp, rdx
0x18002febd  mov     rbx, rdi
0x18002fec0  test    al, al
0x18002fec2  jz      short loc_18002FF2E
0x18002fec4  mov     r14, rdx
0x18002fec7  movsx   ecx, al; Ch
0x18002feca  call    _ismbblead
0x18002fecf  xor     edx, edx
0x18002fed1  test    eax, eax
0x18002fed3  jz      short loc_18002FEDA
0x18002fed5  inc     rbx
0x18002fed8  jmp     short loc_18002FEF1
0x18002feda  mov     al, [rbx]
0x18002fedc  cmp     al, 2Fh ; '/'
0x18002fede  jz      short loc_18002FEED
0x18002fee0  cmp     al, 5Ch ; '\'
0x18002fee2  jz      short loc_18002FEED
0x18002fee4  cmp     al, 2Eh ; '.'
0x18002fee6  jnz     short loc_18002FEF1
0x18002fee8  mov     rbp, rbx
0x18002feeb  jmp     short loc_18002FEF1
0x18002feed  lea     r14, [rbx+1]
0x18002fef1  inc     rbx
0x18002fef4  mov     al, [rbx]
0x18002fef6  test    al, al
0x18002fef8  jnz     short loc_18002FEC7
0x18002fefa  test    r14, r14
0x18002fefd  jz      short loc_18002FF2E
0x18002feff  test    r13, r13
0x18002ff02  jz      short loc_18002FF29
0x18002ff04  mov     r9, r14
0x18002ff07  sub     r9, rdi; MaxCount
0x18002ff0a  cmp     [rsp+68h+arg_20], r9
0x18002ff12  jbe     loc_18002FFC7
0x18002ff18  mov     r8, rdi; Src
0x18002ff1b  or      rdx, 0FFFFFFFFFFFFFFFFh; SizeInBytes
0x18002ff1f  mov     rcx, r13; Dst
0x18002ff22  call    _mbsnbcpy_s
0x18002ff27  xor     edx, edx
0x18002ff29  mov     rdi, r14
0x18002ff2c  jmp     short loc_18002FF37
0x18002ff2e  test    r13, r13
0x18002ff31  jz      short loc_18002FF37
0x18002ff33  mov     [r13+0], dl
0x18002ff37  test    rbp, rbp
0x18002ff3a  jz      short loc_18002FF8D
0x18002ff3c  cmp     rbp, rdi
0x18002ff3f  jb      short loc_18002FF8D
0x18002ff41  test    r15, r15
0x18002ff44  jz      short loc_18002FF67
0x18002ff46  mov     r9, rbp
0x18002ff49  sub     r9, rdi; MaxCount
0x18002ff4c  cmp     [rsp+68h+arg_30], r9
0x18002ff54  jbe     short loc_18002FFC1
0x18002ff56  mov     r8, rdi; Src
0x18002ff59  or      rdx, 0FFFFFFFFFFFFFFFFh; SizeInBytes
0x18002ff5d  mov     rcx, r15; Dst
0x18002ff60  call    _mbsnbcpy_s
0x18002ff65  xor     edx, edx
0x18002ff67  test    rsi, rsi
0x18002ff6a  jz      short loc_18002FFBA
0x18002ff6c  sub     rbx, rbp
0x18002ff6f  cmp     [rsp+68h+arg_40], rbx
0x18002ff77  jbe     short loc_18002FFC1
0x18002ff79  mov     r9, rbx; MaxCount
0x18002ff7c  mov     r8, rbp; Src
0x18002ff7f  or      rdx, 0FFFFFFFFFFFFFFFFh; SizeInBytes
0x18002ff83  mov     rcx, rsi; Dst
0x18002ff86  call    _mbsnbcpy_s
0x18002ff8b  jmp     short loc_18002FFBA
0x18002ff8d  test    r15, r15
0x18002ff90  jz      short loc_18002FFB3
0x18002ff92  sub     rbx, rdi
0x18002ff95  cmp     [rsp+68h+arg_30], rbx
0x18002ff9d  jbe     short loc_18002FFC1
0x18002ff9f  mov     r9, rbx; MaxCount
0x18002ffa2  mov     r8, rdi; Src
0x18002ffa5  or      rdx, 0FFFFFFFFFFFFFFFFh; SizeInBytes
0x18002ffa9  mov     rcx, r15; Dst
0x18002ffac  call    _mbsnbcpy_s
0x18002ffb1  xor     edx, edx
0x18002ffb3  test    rsi, rsi
0x18002ffb6  jz      short loc_18002FFBA
0x18002ffb8  mov     [rsi], dl
0x18002ffba  xor     eax, eax
0x18002ffbc  jmp     loc_180030054
0x18002ffc1  mov     ecx, [rsp+68h+arg_0]
0x18002ffc5  jmp     short loc_18002FFC9
0x18002ffc7  mov     ecx, edx
0x18002ffc9  mov     r8, [rsp+68h+arg_10]
0x18002ffd1  test    r12, r12
0x18002ffd4  jz      short loc_18002FFDF
0x18002ffd6  test    r8, r8
0x18002ffd9  jz      short loc_18002FFDF
0x18002ffdb  mov     [r12], dl
0x18002ffdf  test    r13, r13
0x18002ffe2  jz      short loc_18002FFF2
0x18002ffe4  cmp     [rsp+68h+arg_20], rdx
0x18002ffec  jbe     short loc_18002FFF2
0x18002ffee  mov     [r13+0], dl
0x18002fff2  test    r15, r15
0x18002fff5  jz      short loc_180030004
0x18002fff7  cmp     [rsp+68h+arg_30], rdx
0x18002ffff  jbe     short loc_180030004
0x180030001  mov     [r15], dl
0x180030004  test    rsi, rsi
0x180030007  jz      short loc_180030015
0x180030009  cmp     [rsp+68h+arg_40], rdx
0x180030011  jbe     short loc_180030015
0x180030013  mov     [rsi], dl
0x180030015  test    rdi, rdi
0x180030018  jnz     short loc_180030042
0x18003001a  call    _errno
0x18003001f  mov     ebx, 16h
0x180030024  mov     [rsp+68h+Reserved], 0; Reserved
0x18003002d  xor     r9d, r9d; LineNo
0x180030030  xor     r8d, r8d; FileName
0x180030033  xor     edx, edx; FunctionName
0x180030035  xor     ecx, ecx; Expression
0x180030037  mov     [rax], ebx
0x180030039  call    _invalid_parameter
0x18003003e  mov     eax, ebx
0x180030040  jmp     short loc_180030054
0x180030042  test    ecx, ecx
0x180030044  jnz     short loc_18003001A
0x180030046  call    _errno
0x18003004b  mov     ecx, 22h ; '"'
0x180030050  mov     [rax], ecx
0x180030052  mov     eax, ecx
0x180030054  mov     rbx, [rsp+68h+arg_8]
0x180030059  add     rsp, 30h
0x18003005d  pop     r15
0x18003005f  pop     r14
0x180030061  pop     r13
0x180030063  pop     r12
0x180030065  pop     rdi
0x180030066  pop     rsi
0x180030067  pop     rbp
0x180030068  retn
```
