# TestFTPWrite

- ea: `0x1000fc70`
- end: `0x1000fe6b`
- name: `TestFTPWrite`
- size: `507`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1000f0e0`

## callees

- `0x1000a1f0`
- `0x1000ad60`
- `0x1000b3f0`
- `0x1000b410`
- `0x1000b5f0`
- `0x1000bd80`
- `0x1000d1c0`
- `0x1000dfa0`
- `0x1000e3b0`
- `0x1000fc70`
- `0x1002b81a`

## pseudocode

```c
int __stdcall TestFTPWrite(int a1)
{
  wchar_t *v1; // ecx
  int v2; // edx
  wchar_t v3; // ax
  wchar_t *v4; // ecx
  int v5; // edx
  wchar_t v6; // ax
  int v7; // eax
  void *v8; // ecx
  int v9; // esi
  int v10; // eax
  int v11; // eax
  HANDLE hObject; // [esp+8h] [ebp-420h] BYREF
  wchar_t pszSrc[262]; // [esp+Ch] [ebp-41Ch] BYREF
  wchar_t pszDest[262]; // [esp+218h] [ebp-210h] BYREF

  v1 = pszSrc;
  hObject = 0;
  v2 = 261;
  while ( v2 != -2147483385 )
  {
    v3 = *(wchar_t *)((char *)v1 + a1 + 578 - (_DWORD)pszSrc);
    if ( !v3 )
      break;
    *v1++ = v3;
    if ( !--v2 )
    {
      --v1;
      break;
    }
  }
  *v1 = 0;
  v4 = pszDest;
  v5 = 261;
  while ( v5 != -2147483385 )
  {
    v6 = *(wchar_t *)((char *)v4 + a1 + 56 - (_DWORD)pszDest);
    if ( !v6 )
      break;
    *v4++ = v6;
    if ( !--v5 )
    {
      --v4;
      break;
    }
  }
  *v4 = 0;
  StringCchCatW(pszDest, 0x105u, L"Test.txt");
  v7 = DOSCreateFile(pszDest, (int)&hObject);
  if ( v7 )
  {
    if ( v7 == -4 )
    {
      v9 = -1807;
    }
    else if ( v7 == -5 )
    {
      v9 = -1032;
    }
    else
    {
      v9 = -5036;
      if ( v7 == -3 )
        v9 = -1023;
    }
  }
  else if ( DOSWriteFile(v8, hObject, L"T", 2u) == 2 )
  {
    v10 = DOSCloseFile(hObject);
    hObject = 0;
    if ( v10 )
    {
      v9 = -5036;
      goto LABEL_33;
    }
    v11 = NetUploadToNet(pszDest, 0, (int)pszSrc);
    v9 = v11;
    if ( v11 )
    {
      switch ( v11 )
      {
        case -1032:
          ErrorSetExtendedInfoSz1(-8160, pszSrc, 0);
          break;
        case -1023:
          ErrorSetExtendedInfoSz1(-8161, pszSrc, 0);
          break;
        case -1305:
          ErrorSetExtendedInfoSz1(-8300, pszSrc, 0);
          break;
      }
    }
    else
    {
      NetDeleteFile(pszSrc);
    }
  }
  else
  {
    v9 = -5036;
  }
  if ( hObject )
    DOSCloseFile(hObject);
LABEL_33:
  DOSFileDelete(pszDest);
  NetLocalCleanup((wchar_t *)(a1 + 56), 0);
  return v9;
}

```

## disassembly

```asm
0x1000fc70  sub     esp, 420h
0x1000fc76  mov     eax, ___security_cookie
0x1000fc7b  xor     eax, esp
0x1000fc7d  mov     [esp+420h+var_4], eax
0x1000fc84  push    esi
0x1000fc85  push    edi
0x1000fc86  mov     edi, [esp+428h+arg_0]
0x1000fc8d  lea     ecx, [esp+428h+pszSrc]
0x1000fc91  mov     eax, ecx
0x1000fc93  mov     [esp+428h+hObject], 0
0x1000fc9b  mov     edx, 105h
0x1000fca0  lea     esi, [edi+242h]
0x1000fca6  sub     esi, eax
0x1000fca8  jmp     short loc_1000FCB0
0x1000fcb0  lea     eax, [edx+7FFFFEF9h]
0x1000fcb6  test    eax, eax
0x1000fcb8  jz      short loc_1000FCCE
0x1000fcba  movzx   eax, word ptr [esi+ecx]
0x1000fcbe  test    ax, ax
0x1000fcc1  jz      short loc_1000FCCE
0x1000fcc3  mov     [ecx], ax
0x1000fcc6  add     ecx, 2
0x1000fcc9  dec     edx
0x1000fcca  jnz     short loc_1000FCB0
0x1000fccc  jmp     short loc_1000FCD2
0x1000fcce  test    edx, edx
0x1000fcd0  jnz     short loc_1000FCD5
0x1000fcd2  sub     ecx, 2
0x1000fcd5  xor     eax, eax
0x1000fcd7  add     edi, 38h ; '8'
0x1000fcda  mov     [ecx], ax
0x1000fcdd  mov     esi, edi
0x1000fcdf  lea     ecx, [esp+428h+pszDest]
0x1000fce6  mov     edx, 105h
0x1000fceb  mov     eax, ecx
0x1000fced  sub     esi, eax
0x1000fcef  nop
0x1000fcf0  lea     eax, [edx+7FFFFEF9h]
0x1000fcf6  test    eax, eax
0x1000fcf8  jz      short loc_1000FD0E
0x1000fcfa  movzx   eax, word ptr [esi+ecx]
0x1000fcfe  test    ax, ax
0x1000fd01  jz      short loc_1000FD0E
0x1000fd03  mov     [ecx], ax
0x1000fd06  add     ecx, 2
0x1000fd09  dec     edx
0x1000fd0a  jnz     short loc_1000FCF0
0x1000fd0c  jmp     short loc_1000FD12
0x1000fd0e  test    edx, edx
0x1000fd10  jnz     short loc_1000FD15
0x1000fd12  sub     ecx, 2
0x1000fd15  xor     eax, eax
0x1000fd17  push    offset aTestTxt; "Test.txt"
0x1000fd1c  mov     [ecx], ax
0x1000fd1f  lea     eax, [esp+42Ch+pszDest]
0x1000fd26  push    105h; cchDest
0x1000fd2b  push    eax; pszDest
0x1000fd2c  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1000fd31  lea     eax, [esp+428h+hObject]
0x1000fd35  push    eax; int
0x1000fd36  lea     eax, [esp+42Ch+pszDest]
0x1000fd3d  push    eax; lpFileName
0x1000fd3e  call    _DOSCreateFile@8; DOSCreateFile(x,x)
0x1000fd43  test    eax, eax
0x1000fd45  jz      short loc_1000FD7A
0x1000fd47  cmp     eax, 0FFFFFFFCh
0x1000fd4a  jnz     short loc_1000FD56
0x1000fd4c  mov     esi, 0FFFFF8F1h
0x1000fd51  jmp     loc_1000FE2D
0x1000fd56  cmp     eax, 0FFFFFFFBh
0x1000fd59  jnz     short loc_1000FD65
0x1000fd5b  mov     esi, 0FFFFFBF8h
0x1000fd60  jmp     loc_1000FE2D
0x1000fd65  cmp     eax, 0FFFFFFFDh
0x1000fd68  mov     esi, 0FFFFEC54h
0x1000fd6d  mov     ecx, 0FFFFFC01h
0x1000fd72  cmovz   esi, ecx
0x1000fd75  jmp     loc_1000FE2D
0x1000fd7a  push    2; nNumberOfBytesToWrite
0x1000fd7c  push    offset aT; "T"
0x1000fd81  push    [esp+430h+hObject]; hFile
0x1000fd85  call    _DOSWriteFile@12; DOSWriteFile(x,x,x)
0x1000fd8a  cmp     eax, 2
0x1000fd8d  jz      short loc_1000FD99
0x1000fd8f  mov     esi, 0FFFFEC54h
0x1000fd94  jmp     loc_1000FE2D
0x1000fd99  push    [esp+428h+hObject]; hObject
0x1000fd9d  call    _DOSCloseFile@4; DOSCloseFile(x)
0x1000fda2  mov     [esp+428h+hObject], 0
0x1000fdaa  test    eax, eax
0x1000fdac  jz      short loc_1000FDB8
0x1000fdae  mov     esi, 0FFFFEC54h
0x1000fdb3  jmp     loc_1000FE3B
0x1000fdb8  lea     eax, [esp+428h+pszSrc]
0x1000fdbc  push    eax; int
0x1000fdbd  push    0; int
0x1000fdbf  lea     eax, [esp+430h+pszDest]
0x1000fdc6  push    eax; lpWideCharStr
0x1000fdc7  call    _NetUploadToNet@12; NetUploadToNet(x,x,x)
0x1000fdcc  mov     esi, eax
0x1000fdce  test    esi, esi
0x1000fdd0  jz      short loc_1000FE23
0x1000fdd2  cmp     esi, 0FFFFFBF8h
0x1000fdd8  jnz     short loc_1000FDED
0x1000fdda  push    0; int
0x1000fddc  lea     eax, [esp+42Ch+pszSrc]
0x1000fde0  push    eax; pszSrc
0x1000fde1  push    0FFFFE020h; int
0x1000fde6  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
0x1000fdeb  jmp     short loc_1000FE2D
0x1000fded  cmp     esi, 0FFFFFC01h
0x1000fdf3  jnz     short loc_1000FE08
0x1000fdf5  push    0; int
0x1000fdf7  lea     eax, [esp+42Ch+pszSrc]
0x1000fdfb  push    eax; pszSrc
0x1000fdfc  push    0FFFFE01Fh; int
0x1000fe01  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
0x1000fe06  jmp     short loc_1000FE2D
0x1000fe08  cmp     esi, 0FFFFFAE7h
0x1000fe0e  jnz     short loc_1000FE2D
0x1000fe10  push    0; int
0x1000fe12  lea     eax, [esp+42Ch+pszSrc]
0x1000fe16  push    eax; pszSrc
0x1000fe17  push    0FFFFDF94h; int
0x1000fe1c  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
0x1000fe21  jmp     short loc_1000FE2D
0x1000fe23  lea     eax, [esp+428h+pszSrc]
0x1000fe27  push    eax; lpWideCharStr
0x1000fe28  call    _NetDeleteFile@4; NetDeleteFile(x)
0x1000fe2d  mov     eax, [esp+428h+hObject]
0x1000fe31  test    eax, eax
0x1000fe33  jz      short loc_1000FE3B
0x1000fe35  push    eax; hObject
0x1000fe36  call    _DOSCloseFile@4; DOSCloseFile(x)
0x1000fe3b  lea     eax, [esp+428h+pszDest]
0x1000fe42  push    eax
0x1000fe43  call    _DOSFileDelete@4; DOSFileDelete(x)
0x1000fe48  push    0; int
0x1000fe4a  push    edi; FullPath
0x1000fe4b  call    _NetLocalCleanup@8; NetLocalCleanup(x,x)
0x1000fe50  mov     ecx, [esp+428h+var_4]
0x1000fe57  mov     eax, esi
0x1000fe59  pop     edi
0x1000fe5a  pop     esi
0x1000fe5b  xor     ecx, esp; StackCookie
0x1000fe5d  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000fe62  add     esp, 420h
0x1000fe68  retn    4
```
