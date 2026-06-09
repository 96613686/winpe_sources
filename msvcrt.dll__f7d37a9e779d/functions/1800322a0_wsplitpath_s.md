# _wsplitpath_s

- ea: `0x1800322a0`
- end: `0x180032569`
- name: `_wsplitpath_s`
- size: `713`
- prototype: `errno_t __cdecl(const wchar_t *FullPath, wchar_t *Drive, size_t DriveCount, wchar_t *Dir, size_t DirCount, wchar_t *Filename, size_t FilenameCount, wchar_t *Ext, size_t ExtCount)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180007f00`
- `0x18002f050`
- `0x1800322a0`
- `0x180061e50`

## pseudocode

```c
errno_t __cdecl wsplitpath_s(
        const wchar_t *FullPath,
        wchar_t *Drive,
        size_t DriveCount,
        wchar_t *Dir,
        size_t DirCount,
        wchar_t *Filename,
        size_t FilenameCount,
        wchar_t *Ext,
        size_t ExtCount)
{
  size_t v11; // rsi
  const wchar_t *v12; // rdi
  int v13; // ecx
  __int64 v14; // rax
  const wchar_t *v15; // rbx
  wchar_t v16; // ax
  const wchar_t *v17; // rsi
  const wchar_t *v18; // rbx
  const wchar_t *v19; // rbp
  rsize_t v20; // r9
  rsize_t v21; // r9
  rsize_t v22; // rbx
  rsize_t v23; // rbx

  v11 = DriveCount;
  v12 = FullPath;
  if ( !FullPath )
    goto LABEL_4;
  if ( Drive )
  {
    if ( !DriveCount )
      goto LABEL_4;
  }
  else if ( DriveCount )
  {
LABEL_4:
    v13 = 1;
    goto LABEL_59;
  }
  if ( Dir )
  {
    if ( !DirCount )
      goto LABEL_4;
  }
  else if ( DirCount )
  {
    goto LABEL_4;
  }
  if ( Filename )
  {
    if ( !FilenameCount )
      goto LABEL_4;
  }
  else if ( FilenameCount )
  {
    goto LABEL_4;
  }
  if ( Ext )
  {
    if ( !ExtCount )
      goto LABEL_4;
  }
  else if ( ExtCount )
  {
    goto LABEL_4;
  }
  v13 = 0;
  v14 = 1;
  v15 = v12;
  do
  {
    if ( !*v15 )
      break;
    ++v15;
    --v14;
  }
  while ( v14 );
  if ( *v15 == 58 )
  {
    if ( Drive )
    {
      if ( DriveCount < 3 )
        goto LABEL_60;
      wcsncpy_s(Drive, DriveCount, v12, 2u);
      v13 = 0;
    }
    v12 = v15 + 1;
  }
  else if ( Drive )
  {
    *Drive = 0;
  }
  v16 = *v12;
  v17 = 0;
  v18 = v12;
  if ( !*v12 )
    goto LABEL_41;
  v19 = 0;
  do
  {
    if ( v16 == 47 || v16 == 92 )
    {
      v19 = v18 + 1;
    }
    else if ( v16 == 46 )
    {
      v17 = v18;
    }
    v16 = *++v18;
  }
  while ( *v18 );
  if ( !v19 )
  {
LABEL_41:
    if ( Dir )
      *Dir = 0;
LABEL_43:
    if ( v17 && v17 >= v12 )
    {
      if ( !Filename )
      {
LABEL_48:
        if ( !Ext )
          return 0;
        v22 = v18 - v17;
        if ( ExtCount > v22 )
        {
          wcsncpy_s(Ext, ExtCount, v17, v22);
          return 0;
        }
        goto LABEL_57;
      }
      v21 = v17 - v12;
      if ( FilenameCount > v21 )
      {
        wcsncpy_s(Filename, FilenameCount, v12, v21);
        goto LABEL_48;
      }
LABEL_57:
      v13 = 0;
      goto LABEL_58;
    }
    if ( Filename )
    {
      v23 = v18 - v12;
      if ( FilenameCount <= v23 )
        goto LABEL_57;
      wcsncpy_s(Filename, FilenameCount, v12, v23);
    }
    if ( Ext )
      *Ext = 0;
    return 0;
  }
  if ( !Dir )
  {
LABEL_40:
    v12 = v19;
    goto LABEL_43;
  }
  v20 = v19 - v12;
  if ( DirCount > v20 )
  {
    wcsncpy_s(Dir, DirCount, v12, v20);
    goto LABEL_40;
  }
LABEL_58:
  v11 = DriveCount;
LABEL_59:
  if ( Drive )
  {
LABEL_60:
    if ( v11 )
      *Drive = 0;
  }
  if ( Dir && DirCount )
    *Dir = 0;
  if ( Filename && FilenameCount )
    *Filename = 0;
  if ( Ext && ExtCount )
    *Ext = 0;
  if ( !v12 || v13 )
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
0x1800322a0  mov     [rsp+arg_8], rbx
0x1800322a5  mov     [rsp+arg_10], r8
0x1800322aa  push    rbp
0x1800322ab  push    rsi
0x1800322ac  push    rdi
0x1800322ad  push    r12
0x1800322af  push    r13
0x1800322b1  push    r14
0x1800322b3  push    r15
0x1800322b5  sub     rsp, 30h
0x1800322b9  mov     r14, [rsp+68h+Ext]
0x1800322c1  mov     r12, rdx
0x1800322c4  mov     r15, [rsp+68h+Filename]
0x1800322cc  xor     edx, edx
0x1800322ce  mov     r13, r9
0x1800322d1  mov     rsi, r8
0x1800322d4  mov     rdi, rcx
0x1800322d7  test    rcx, rcx
0x1800322da  jz      short loc_1800322E6
0x1800322dc  test    r12, r12
0x1800322df  jnz     short loc_1800322F0
0x1800322e1  test    r8, r8
0x1800322e4  jz      short loc_1800322F5
0x1800322e6  mov     ecx, 1
0x1800322eb  jmp     loc_1800324CC
0x1800322f0  test    rsi, rsi
0x1800322f3  jz      short loc_1800322E6
0x1800322f5  test    r13, r13
0x1800322f8  jnz     short loc_180032306
0x1800322fa  cmp     [rsp+68h+DirCount], rdx
0x180032302  jnz     short loc_1800322E6
0x180032304  jmp     short loc_180032310
0x180032306  cmp     [rsp+68h+DirCount], rdx
0x18003230e  jz      short loc_1800322E6
0x180032310  test    r15, r15
0x180032313  jnz     short loc_180032321
0x180032315  cmp     [rsp+68h+FilenameCount], rdx
0x18003231d  jnz     short loc_1800322E6
0x18003231f  jmp     short loc_18003232B
0x180032321  cmp     [rsp+68h+FilenameCount], rdx
0x180032329  jz      short loc_1800322E6
0x18003232b  test    r14, r14
0x18003232e  jnz     short loc_18003233C
0x180032330  cmp     [rsp+68h+ExtCount], rdx
0x180032338  jnz     short loc_1800322E6
0x18003233a  jmp     short loc_180032346
0x18003233c  cmp     [rsp+68h+ExtCount], rdx
0x180032344  jz      short loc_1800322E6
0x180032346  mov     ecx, edx
0x180032348  mov     [rsp+68h+arg_0], edx
0x18003234c  mov     eax, 1
0x180032351  mov     rbx, rdi
0x180032354  cmp     [rbx], dx
0x180032357  jz      short loc_180032363
0x180032359  add     rbx, 2
0x18003235d  sub     rax, 1
0x180032361  jnz     short loc_180032354
0x180032363  cmp     word ptr [rbx], 3Ah ; ':'
0x180032367  jnz     short loc_180032398
0x180032369  test    r12, r12
0x18003236c  jz      short loc_180032392
0x18003236e  cmp     rsi, 3
0x180032372  jb      loc_1800324D1
0x180032378  mov     r9d, 2; MaxCount
0x18003237e  mov     r8, rdi; Source
0x180032381  mov     rdx, rsi; SizeInWords
0x180032384  mov     rcx, r12; Destination
0x180032387  call    wcsncpy_s
0x18003238c  mov     ecx, [rsp+68h+arg_0]
0x180032390  xor     edx, edx
0x180032392  lea     rdi, [rbx+2]
0x180032396  jmp     short loc_1800323A2
0x180032398  test    r12, r12
0x18003239b  jz      short loc_1800323A2
0x18003239d  mov     [r12], dx
0x1800323a2  movzx   eax, word ptr [rdi]
0x1800323a5  mov     rsi, rdx
0x1800323a8  mov     rbx, rdi
0x1800323ab  test    ax, ax
0x1800323ae  jz      short loc_180032415
0x1800323b0  mov     rbp, rdx
0x1800323b3  cmp     ax, 2Fh ; '/'
0x1800323b7  jz      short loc_1800323CA
0x1800323b9  cmp     ax, 5Ch ; '\'
0x1800323bd  jz      short loc_1800323CA
0x1800323bf  cmp     ax, 2Eh ; '.'
0x1800323c3  jnz     short loc_1800323CE
0x1800323c5  mov     rsi, rbx
0x1800323c8  jmp     short loc_1800323CE
0x1800323ca  lea     rbp, [rbx+2]
0x1800323ce  add     rbx, 2
0x1800323d2  movzx   eax, word ptr [rbx]
0x1800323d5  test    ax, ax
0x1800323d8  jnz     short loc_1800323B3
0x1800323da  test    rbp, rbp
0x1800323dd  jz      short loc_180032415
0x1800323df  test    r13, r13
0x1800323e2  jz      short loc_180032410
0x1800323e4  mov     r9, rbp
0x1800323e7  sub     r9, rdi
0x1800323ea  sar     r9, 1; MaxCount
0x1800323ed  cmp     [rsp+68h+DirCount], r9
0x1800323f5  jbe     loc_1800324C4
0x1800323fb  mov     rdx, [rsp+68h+DirCount]; SizeInWords
0x180032403  mov     r8, rdi; Source
0x180032406  mov     rcx, r13; Destination
0x180032409  call    wcsncpy_s
0x18003240e  xor     edx, edx
0x180032410  mov     rdi, rbp
0x180032413  jmp     short loc_18003241F
0x180032415  test    r13, r13
0x180032418  jz      short loc_18003241F
0x18003241a  mov     [r13+0], dx
0x18003241f  test    rsi, rsi
0x180032422  jz      short loc_180032483
0x180032424  cmp     rsi, rdi
0x180032427  jb      short loc_180032483
0x180032429  test    r15, r15
0x18003242c  jz      short loc_180032456
0x18003242e  mov     r9, rsi
0x180032431  sub     r9, rdi
0x180032434  sar     r9, 1; MaxCount
0x180032437  cmp     [rsp+68h+FilenameCount], r9
0x18003243f  jbe     short loc_1800324C0
0x180032441  mov     rdx, [rsp+68h+FilenameCount]; SizeInWords
0x180032449  mov     r8, rdi; Source
0x18003244c  mov     rcx, r15; Destination
0x18003244f  call    wcsncpy_s
0x180032454  xor     edx, edx
0x180032456  test    r14, r14
0x180032459  jz      short loc_1800324B9
0x18003245b  sub     rbx, rsi
0x18003245e  sar     rbx, 1
0x180032461  cmp     [rsp+68h+ExtCount], rbx
0x180032469  jbe     short loc_1800324C0
0x18003246b  mov     rdx, [rsp+68h+ExtCount]; SizeInWords
0x180032473  mov     r9, rbx; MaxCount
0x180032476  mov     r8, rsi; Source
0x180032479  mov     rcx, r14; Destination
0x18003247c  call    wcsncpy_s
0x180032481  jmp     short loc_1800324B9
0x180032483  test    r15, r15
0x180032486  jz      short loc_1800324B0
0x180032488  sub     rbx, rdi
0x18003248b  sar     rbx, 1
0x18003248e  cmp     [rsp+68h+FilenameCount], rbx
0x180032496  jbe     short loc_1800324C0
0x180032498  mov     rdx, [rsp+68h+FilenameCount]; SizeInWords
0x1800324a0  mov     r9, rbx; MaxCount
0x1800324a3  mov     r8, rdi; Source
0x1800324a6  mov     rcx, r15; Destination
0x1800324a9  call    wcsncpy_s
0x1800324ae  xor     edx, edx
0x1800324b0  test    r14, r14
0x1800324b3  jz      short loc_1800324B9
0x1800324b5  mov     [r14], dx
0x1800324b9  xor     eax, eax
0x1800324bb  jmp     loc_180032554
0x1800324c0  mov     ecx, [rsp+68h+arg_0]
0x1800324c4  mov     rsi, [rsp+68h+arg_10]
0x1800324cc  test    r12, r12
0x1800324cf  jz      short loc_1800324DB
0x1800324d1  test    rsi, rsi
0x1800324d4  jz      short loc_1800324DB
0x1800324d6  mov     [r12], dx
0x1800324db  test    r13, r13
0x1800324de  jz      short loc_1800324EF
0x1800324e0  cmp     [rsp+68h+DirCount], rdx
0x1800324e8  jbe     short loc_1800324EF
0x1800324ea  mov     [r13+0], dx
0x1800324ef  test    r15, r15
0x1800324f2  jz      short loc_180032502
0x1800324f4  cmp     [rsp+68h+FilenameCount], rdx
0x1800324fc  jbe     short loc_180032502
0x1800324fe  mov     [r15], dx
0x180032502  test    r14, r14
0x180032505  jz      short loc_180032515
0x180032507  cmp     [rsp+68h+ExtCount], rdx
0x18003250f  jbe     short loc_180032515
0x180032511  mov     [r14], dx
0x180032515  test    rdi, rdi
0x180032518  jnz     short loc_180032542
0x18003251a  call    _errno
0x18003251f  mov     ebx, 16h
0x180032524  mov     [rsp+68h+Reserved], 0; Reserved
0x18003252d  xor     r9d, r9d; LineNo
0x180032530  xor     r8d, r8d; FileName
0x180032533  xor     edx, edx; FunctionName
0x180032535  xor     ecx, ecx; Expression
0x180032537  mov     [rax], ebx
0x180032539  call    _invalid_parameter
0x18003253e  mov     eax, ebx
0x180032540  jmp     short loc_180032554
0x180032542  test    ecx, ecx
0x180032544  jnz     short loc_18003251A
0x180032546  call    _errno
0x18003254b  mov     ecx, 22h ; '"'
0x180032550  mov     [rax], ecx
0x180032552  mov     eax, ecx
0x180032554  mov     rbx, [rsp+68h+arg_8]
0x180032559  add     rsp, 30h
0x18003255d  pop     r15
0x18003255f  pop     r14
0x180032561  pop     r13
0x180032563  pop     r12
0x180032565  pop     rdi
0x180032566  pop     rsi
0x180032567  pop     rbp
0x180032568  retn
```
