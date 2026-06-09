# __wsplitpath_s

- ea: `0x1002c520`
- end: `0x1002c71a`
- name: `__wsplitpath_s`
- size: `506`
- prototype: `errno_t __cdecl(const wchar_t *FullPath, wchar_t *Drive, size_t DriveCount, wchar_t *Dir, size_t DirCount, wchar_t *Filename, size_t FilenameCount, wchar_t *Ext, size_t ExtCount)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1000bfc0`
- `0x1000c2f0`

## callees

- `0x1002c520`
- `0x1002d6dc`
- `0x10030870`
- `0x100308ab`

## pseudocode

```c
errno_t __cdecl _wsplitpath_s(
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
  const wchar_t *v9; // edi
  unsigned int v10; // ebx
  wchar_t *v11; // edx
  wchar_t *v12; // eax
  const wchar_t *v13; // esi
  int v14; // eax
  wchar_t v15; // ax
  const wchar_t *v16; // ecx
  const wchar_t *v17; // esi
  rsize_t v18; // esi
  rsize_t v19; // esi
  int *v21; // eax
  const wchar_t *FullPatha; // [esp+14h] [ebp+8h]

  v9 = FullPath;
  v10 = 0;
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
    v11 = Filename;
$error_einval$79:
    v10 = 1;
LABEL_6:
    v12 = Ext;
    goto $error_erange$80;
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
  v11 = Filename;
  if ( Filename )
  {
    if ( !FilenameCount )
      goto $error_einval$79;
  }
  else if ( FilenameCount )
  {
    goto $error_einval$79;
  }
  if ( Ext )
  {
    if ( !ExtCount )
      goto $error_einval$79;
  }
  else if ( ExtCount )
  {
    goto $error_einval$79;
  }
  v13 = FullPath;
  v14 = 1;
  do
  {
    if ( !*v13 )
      break;
    ++v13;
    --v14;
  }
  while ( v14 );
  if ( *v13 == 58 )
  {
    if ( Drive )
    {
      if ( DriveCount < 3 )
        goto LABEL_6;
      wcsncpy_s(Drive, DriveCount, FullPath, 2u);
      v11 = Filename;
    }
    v9 = v13 + 1;
  }
  else if ( Drive )
  {
    *Drive = 0;
  }
  v15 = *v9;
  v16 = 0;
  v17 = v9;
  if ( !*v9 )
    goto LABEL_42;
  do
  {
    if ( v15 == 47 || v15 == 92 )
    {
      v16 = v17 + 1;
    }
    else if ( v15 == 46 )
    {
      v10 = (unsigned int)v17;
    }
    v15 = *++v17;
  }
  while ( *v17 );
  FullPatha = v16;
  if ( v16 )
  {
    if ( Dir )
    {
      if ( DirCount <= v16 - v9 )
        goto LABEL_58;
      wcsncpy_s(Dir, DirCount, v9, v16 - v9);
      v16 = FullPatha;
    }
    v9 = v16;
  }
  else
  {
LABEL_42:
    if ( Dir )
      *Dir = 0;
  }
  if ( !v10 || v10 < (unsigned int)v9 )
  {
    v11 = Filename;
    if ( Filename )
    {
      v19 = v17 - v9;
      if ( FilenameCount <= v19 )
        goto LABEL_58;
      wcsncpy_s(Filename, FilenameCount, v9, v19);
    }
    if ( Ext )
      *Ext = 0;
    return 0;
  }
  v11 = Filename;
  if ( Filename )
  {
    if ( FilenameCount > (int)(v10 - (_DWORD)v9) >> 1 )
    {
      wcsncpy_s(Filename, FilenameCount, v9, (int)(v10 - (_DWORD)v9) >> 1);
      v11 = Filename;
      goto LABEL_49;
    }
LABEL_58:
    v12 = Ext;
    goto LABEL_59;
  }
LABEL_49:
  v12 = Ext;
  if ( !Ext )
    return 0;
  v18 = (int)((int)v17 - v10) >> 1;
  if ( ExtCount > v18 )
  {
    wcsncpy_s(Ext, ExtCount, (const wchar_t *)v10, v18);
    return 0;
  }
LABEL_59:
  v10 = 0;
$error_erange$80:
  if ( Drive && DriveCount )
    *Drive = 0;
  if ( Dir && DirCount )
    *Dir = 0;
  if ( v11 && FilenameCount )
    *v11 = 0;
  if ( v12 && ExtCount )
    *v12 = 0;
  v21 = _errno();
  if ( !v9 || v10 )
  {
    *v21 = 22;
    _invalid_parameter_noinfo();
    return 22;
  }
  else
  {
    *v21 = 34;
    return 34;
  }
}

```

## disassembly

```asm
0x1002c520  push    ebp
0x1002c521  mov     ebp, esp
0x1002c523  push    ebx
0x1002c524  push    esi
0x1002c525  push    edi
0x1002c526  mov     edi, [ebp+FullPath]
0x1002c529  xor     ebx, ebx
0x1002c52b  test    edi, edi
0x1002c52d  jz      short loc_1002C53B
0x1002c52f  mov     ecx, [ebp+Drive]
0x1002c532  test    ecx, ecx
0x1002c534  jnz     short loc_1002C549
0x1002c536  cmp     [ebp+DriveCount], ebx
0x1002c539  jz      short loc_1002C54E
0x1002c53b  mov     edx, [ebp+Filename]
0x1002c53e  xor     ebx, ebx
0x1002c540  inc     ebx
0x1002c541  mov     eax, [ebp+Ext]
0x1002c544  jmp     $error_erange$80
0x1002c549  cmp     [ebp+DriveCount], ebx
0x1002c54c  jz      short loc_1002C53B
0x1002c54e  cmp     [ebp+Dir], ebx
0x1002c551  jnz     short loc_1002C55A
0x1002c553  cmp     [ebp+DirCount], ebx
0x1002c556  jnz     short loc_1002C53B
0x1002c558  jmp     short loc_1002C55F
0x1002c55a  cmp     [ebp+DirCount], ebx
0x1002c55d  jz      short loc_1002C53B
0x1002c55f  mov     edx, [ebp+Filename]
0x1002c562  test    edx, edx
0x1002c564  jnz     short loc_1002C56D
0x1002c566  cmp     [ebp+FilenameCount], ebx
0x1002c569  jnz     short $error_einval$79
0x1002c56b  jmp     short loc_1002C572
0x1002c56d  cmp     [ebp+FilenameCount], ebx
0x1002c570  jz      short $error_einval$79
0x1002c572  cmp     [ebp+Ext], ebx
0x1002c575  jnz     short loc_1002C57E
0x1002c577  cmp     [ebp+ExtCount], ebx
0x1002c57a  jnz     short $error_einval$79
0x1002c57c  jmp     short loc_1002C583
0x1002c57e  cmp     [ebp+ExtCount], ebx
0x1002c581  jz      short $error_einval$79
0x1002c583  xor     eax, eax
0x1002c585  mov     esi, edi
0x1002c587  inc     eax
0x1002c588  cmp     [esi], bx
0x1002c58b  jz      short loc_1002C593
0x1002c58d  add     esi, 2
0x1002c590  dec     eax
0x1002c591  jnz     short loc_1002C588
0x1002c593  cmp     word ptr [esi], 3Ah ; ':'
0x1002c597  jnz     short loc_1002C5BA
0x1002c599  test    ecx, ecx
0x1002c59b  jz      short loc_1002C5B5
0x1002c59d  cmp     [ebp+DriveCount], 3
0x1002c5a1  jb      short loc_1002C541
0x1002c5a3  push    2; MaxCount
0x1002c5a5  push    edi; Source
0x1002c5a6  push    [ebp+DriveCount]; SizeInWords
0x1002c5a9  push    ecx; Destination
0x1002c5aa  call    _wcsncpy_s
0x1002c5af  mov     edx, [ebp+Filename]
0x1002c5b2  add     esp, 10h
0x1002c5b5  lea     edi, [esi+2]
0x1002c5b8  jmp     short loc_1002C5C3
0x1002c5ba  test    ecx, ecx
0x1002c5bc  jz      short loc_1002C5C3
0x1002c5be  xor     eax, eax
0x1002c5c0  mov     [ecx], ax
0x1002c5c3  movzx   eax, word ptr [edi]
0x1002c5c6  mov     ecx, ebx
0x1002c5c8  mov     esi, edi
0x1002c5ca  test    ax, ax
0x1002c5cd  jz      short loc_1002C627
0x1002c5cf  cmp     ax, 2Fh ; '/'
0x1002c5d3  jz      short loc_1002C5E5
0x1002c5d5  cmp     ax, 5Ch ; '\'
0x1002c5d9  jz      short loc_1002C5E5
0x1002c5db  cmp     ax, 2Eh ; '.'
0x1002c5df  jnz     short loc_1002C5E8
0x1002c5e1  mov     ebx, esi
0x1002c5e3  jmp     short loc_1002C5E8
0x1002c5e5  lea     ecx, [esi+2]
0x1002c5e8  add     esi, 2
0x1002c5eb  movzx   eax, word ptr [esi]
0x1002c5ee  test    ax, ax
0x1002c5f1  jnz     short loc_1002C5CF
0x1002c5f3  mov     [ebp+FullPath], ecx
0x1002c5f6  test    ecx, ecx
0x1002c5f8  jz      short loc_1002C627
0x1002c5fa  mov     eax, [ebp+Dir]
0x1002c5fd  test    eax, eax
0x1002c5ff  jz      short loc_1002C623
0x1002c601  mov     eax, ecx
0x1002c603  sub     eax, edi
0x1002c605  sar     eax, 1
0x1002c607  cmp     [ebp+DirCount], eax
0x1002c60a  jbe     loc_1002C6AC
0x1002c610  push    eax; MaxCount
0x1002c611  push    edi; Source
0x1002c612  push    [ebp+DirCount]; SizeInWords
0x1002c615  push    [ebp+Dir]; Destination
0x1002c618  call    _wcsncpy_s
0x1002c61d  mov     ecx, [ebp+FullPath]
0x1002c620  add     esp, 10h
0x1002c623  mov     edi, ecx
0x1002c625  jmp     short loc_1002C633
0x1002c627  mov     eax, [ebp+Dir]
0x1002c62a  test    eax, eax
0x1002c62c  jz      short loc_1002C633
0x1002c62e  xor     ecx, ecx
0x1002c630  mov     [eax], cx
0x1002c633  test    ebx, ebx
0x1002c635  jz      short loc_1002C67E
0x1002c637  cmp     ebx, edi
0x1002c639  jb      short loc_1002C67E
0x1002c63b  mov     edx, [ebp+Filename]
0x1002c63e  test    edx, edx
0x1002c640  jz      short loc_1002C65E
0x1002c642  mov     eax, ebx
0x1002c644  sub     eax, edi
0x1002c646  sar     eax, 1
0x1002c648  cmp     [ebp+FilenameCount], eax
0x1002c64b  jbe     short loc_1002C6AC
0x1002c64d  push    eax; MaxCount
0x1002c64e  push    edi; Source
0x1002c64f  push    [ebp+FilenameCount]; SizeInWords
0x1002c652  push    edx; Destination
0x1002c653  call    _wcsncpy_s
0x1002c658  mov     edx, [ebp+Filename]
0x1002c65b  add     esp, 10h
0x1002c65e  mov     eax, [ebp+Ext]
0x1002c661  test    eax, eax
0x1002c663  jz      short loc_1002C6A8
0x1002c665  sub     esi, ebx
0x1002c667  sar     esi, 1
0x1002c669  cmp     [ebp+ExtCount], esi
0x1002c66c  jbe     short loc_1002C6AF
0x1002c66e  push    esi; MaxCount
0x1002c66f  push    ebx; Source
0x1002c670  push    [ebp+ExtCount]; SizeInWords
0x1002c673  push    eax; Destination
0x1002c674  call    _wcsncpy_s
0x1002c679  add     esp, 10h
0x1002c67c  jmp     short loc_1002C6A8
0x1002c67e  mov     edx, [ebp+Filename]
0x1002c681  test    edx, edx
0x1002c683  jz      short loc_1002C69C
0x1002c685  sub     esi, edi
0x1002c687  sar     esi, 1
0x1002c689  cmp     [ebp+FilenameCount], esi
0x1002c68c  jbe     short loc_1002C6AC
0x1002c68e  push    esi; MaxCount
0x1002c68f  push    edi; Source
0x1002c690  push    [ebp+FilenameCount]; SizeInWords
0x1002c693  push    edx; Destination
0x1002c694  call    _wcsncpy_s
0x1002c699  add     esp, 10h
0x1002c69c  mov     eax, [ebp+Ext]
0x1002c69f  test    eax, eax
0x1002c6a1  jz      short loc_1002C6A8
0x1002c6a3  xor     ecx, ecx
0x1002c6a5  mov     [eax], cx
0x1002c6a8  xor     eax, eax
0x1002c6aa  jmp     short loc_1002C715
0x1002c6ac  mov     eax, [ebp+Ext]
0x1002c6af  xor     ebx, ebx
0x1002c6b1  mov     ecx, [ebp+Drive]
0x1002c6b4  test    ecx, ecx
0x1002c6b6  jz      short loc_1002C6C3
0x1002c6b8  cmp     [ebp+DriveCount], 0
0x1002c6bc  jbe     short loc_1002C6C3
0x1002c6be  xor     esi, esi
0x1002c6c0  mov     [ecx], si
0x1002c6c3  mov     ecx, [ebp+Dir]
0x1002c6c6  test    ecx, ecx
0x1002c6c8  jz      short loc_1002C6D5
0x1002c6ca  cmp     [ebp+DirCount], 0
0x1002c6ce  jbe     short loc_1002C6D5
0x1002c6d0  xor     esi, esi
0x1002c6d2  mov     [ecx], si
0x1002c6d5  test    edx, edx
0x1002c6d7  jz      short loc_1002C6E4
0x1002c6d9  cmp     [ebp+FilenameCount], 0
0x1002c6dd  jbe     short loc_1002C6E4
0x1002c6df  xor     ecx, ecx
0x1002c6e1  mov     [edx], cx
0x1002c6e4  test    eax, eax
0x1002c6e6  jz      short loc_1002C6F3
0x1002c6e8  cmp     [ebp+ExtCount], 0
0x1002c6ec  jbe     short loc_1002C6F3
0x1002c6ee  xor     ecx, ecx
0x1002c6f0  mov     [eax], cx
0x1002c6f3  call    __errno
0x1002c6f8  test    edi, edi
0x1002c6fa  jnz     short loc_1002C70A
0x1002c6fc  push    16h
0x1002c6fe  pop     esi
0x1002c6ff  mov     [eax], esi
0x1002c701  call    __invalid_parameter_noinfo
0x1002c706  mov     eax, esi
0x1002c708  jmp     short loc_1002C715
0x1002c70a  test    ebx, ebx
0x1002c70c  jnz     short loc_1002C6FC
0x1002c70e  push    22h ; '"'
0x1002c710  pop     ecx
0x1002c711  mov     [eax], ecx
0x1002c713  mov     eax, ecx
0x1002c715  pop     edi
0x1002c716  pop     esi
0x1002c717  pop     ebx
0x1002c718  pop     ebp
0x1002c719  retn
```
