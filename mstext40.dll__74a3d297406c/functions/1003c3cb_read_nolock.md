# __read_nolock

- ea: `0x1003c3cb`
- end: `0x1003cb5c`
- name: `__read_nolock`
- size: `1937`
- prototype: `int __cdecl(int FileHandle, LPWSTR lpWideCharStr, DWORD nNumberOfBytesToRead)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1003c2b7`

## callees

- `0x1002d6a8`
- `0x1002d6bb`
- `0x1002d6dc`
- `0x1002df32`
- `0x10030870`
- `0x100336fe`
- `0x1003737e`
- `0x10037e22`
- `0x1003c3cb`

## import_xrefs

- `KERNEL32!ReadFile` at `0x1003c637`
- `KERNEL32!ReadFile` at `0x1003c6fd`
- `KERNEL32!ReadFile` at `0x1003ca06`
- `KERNEL32!ReadFile` at `0x1003c637`
- `KERNEL32!ReadFile` at `0x1003c6fd`
- `KERNEL32!ReadFile` at `0x1003ca06`
- `KERNEL32!GetLastError` at `0x1003c5fd`
- `KERNEL32!GetLastError` at `0x1003c707`
- `KERNEL32!GetLastError` at `0x1003ca10`
- `KERNEL32!GetLastError` at `0x1003cb03`
- `KERNEL32!GetLastError` at `0x1003c5fd`
- `KERNEL32!GetLastError` at `0x1003c707`
- `KERNEL32!GetLastError` at `0x1003ca10`
- `KERNEL32!GetLastError` at `0x1003cb03`
- `KERNEL32!GetConsoleMode` at `0x1003c5c7`
- `KERNEL32!GetConsoleMode` at `0x1003c5c7`
- `KERNEL32!ReadConsoleW` at `0x1003c5f3`
- `KERNEL32!ReadConsoleW` at `0x1003c5f3`
- `KERNEL32!MultiByteToWideChar` at `0x1003c8a0`
- `KERNEL32!MultiByteToWideChar` at `0x1003c8a0`

## pseudocode

```c
int __cdecl _read_nolock(int FileHandle, CHAR *lpWideCharStr, DWORD nNumberOfBytesToRead)
{
  size_t v3; // esi
  signed int v4; // edi
  int v5; // ecx
  int v6; // ebx
  int v7; // edx
  char v8; // al
  CHAR *v9; // eax
  int v10; // eax
  int v11; // ecx
  int v12; // edx
  int v13; // edx
  int v14; // ecx
  CHAR v15; // dl
  _BYTE *v16; // edx
  int v17; // eax
  char v18; // al
  _BYTE *v19; // edx
  int v20; // eax
  char v21; // al
  int v22; // eax
  bool v23; // zf
  int v24; // eax
  int v25; // ecx
  DWORD LastError; // eax
  int v27; // ebx
  CHAR *v28; // eax
  DWORD v29; // ecx
  int v30; // edx
  int v31; // esi
  char v32; // al
  char v33; // al
  CHAR *v34; // esi
  LPCCH v35; // edi
  char v36; // al
  int v37; // ecx
  char v38; // al
  CHAR *v39; // esi
  int i; // edx
  int v41; // ecx
  char v42; // al
  char *v43; // esi
  int v44; // eax
  char v45; // al
  int v46; // ecx
  char v47; // al
  int v48; // esi
  int v49; // eax
  CHAR *v51; // esi
  LPCCH v52; // ecx
  const CHAR *v53; // edx
  __int16 v54; // ax
  __int16 v55; // ax
  char v56; // al
  CHAR *v57; // esi
  LPCCH v58; // edi
  __int16 v59; // ax
  int v60; // ecx
  char v61; // al
  DWORD Mode; // [esp+14h] [ebp-20h] BYREF
  LPVOID lpBuffer; // [esp+18h] [ebp-1Ch]
  int v65; // [esp+1Ch] [ebp-18h]
  DWORD NumberOfCharsRead; // [esp+20h] [ebp-14h] BYREF
  LPCCH lpMultiByteStr; // [esp+24h] [ebp-10h]
  int v68; // [esp+28h] [ebp-Ch]
  __int16 v69; // [esp+2Ch] [ebp-8h] BYREF
  char Buffer; // [esp+33h] [ebp-1h] BYREF
  char nNumberOfBytesToRead_3; // [esp+47h] [ebp+13h]

  v3 = nNumberOfBytesToRead;
  v4 = 0;
  v65 = -2;
  Mode = 0;
  if ( FileHandle == -2 )
  {
    *__doserrno() = 0;
    *_errno() = 9;
    return -1;
  }
  if ( FileHandle < 0
    || FileHandle >= (unsigned int)_nhandle
    || (v5 = FileHandle >> 5,
        v6 = (FileHandle & 0x1F) << 6,
        v68 = FileHandle >> 5,
        v7 = __pioinfo[FileHandle >> 5],
        v8 = *(_BYTE *)(v7 + v6 + 4),
        (v8 & 1) == 0) )
  {
    *__doserrno() = 0;
    *_errno() = 9;
    goto LABEL_162;
  }
  if ( nNumberOfBytesToRead > 0x7FFFFFFF )
    goto LABEL_7;
  if ( !nNumberOfBytesToRead || (v8 & 2) != 0 )
    return 0;
  if ( !lpWideCharStr )
  {
LABEL_7:
    *__doserrno() = 0;
    *_errno() = 22;
LABEL_162:
    _invalid_parameter_noinfo();
    return -1;
  }
  nNumberOfBytesToRead_3 = (char)(2 * *(_BYTE *)(v7 + v6 + 36)) >> 1;
  if ( nNumberOfBytesToRead_3 == 1 )
  {
    if ( (v3 & 1) != 0 )
      goto LABEL_7;
    v3 >>= 1;
    if ( v3 < 4 )
      v3 = 4;
    lpMultiByteStr = (LPCCH)_malloc_crt(v3);
    if ( !lpMultiByteStr )
    {
      *_errno() = 12;
      *__doserrno() = 8;
      return -1;
    }
    v10 = _lseeki64_nolock(FileHandle, 0, 1u);
    v11 = __pioinfo[v68];
    *(_DWORD *)(v11 + v6 + 40) = v10;
    v9 = (CHAR *)lpMultiByteStr;
    *(_DWORD *)(v11 + v6 + 44) = v12;
    v5 = v68;
  }
  else
  {
    if ( nNumberOfBytesToRead_3 == 2 )
    {
      if ( (v3 & 1) != 0 )
        goto LABEL_7;
      v3 &= ~1u;
    }
    v9 = lpWideCharStr;
    lpMultiByteStr = lpWideCharStr;
  }
  v13 = __pioinfo[v5];
  v14 = v68;
  lpBuffer = v9;
  if ( (*(_BYTE *)(v13 + v6 + 4) & 0x48) != 0 )
  {
    v15 = *(_BYTE *)(v13 + v6 + 5);
    if ( v15 != 10 )
    {
      if ( v3 )
      {
        *v9 = v15;
        v16 = v9 + 1;
        v4 = 1;
        v17 = __pioinfo[v14];
        --v3;
        lpBuffer = v16;
        *(_BYTE *)(v17 + v6 + 5) = 10;
        if ( nNumberOfBytesToRead_3 )
        {
          v18 = *(_BYTE *)(__pioinfo[v14] + v6 + 37);
          if ( v18 != 10 )
          {
            if ( v3 )
            {
              *v16 = v18;
              v19 = v16 + 1;
              v20 = __pioinfo[v14];
              --v3;
              lpBuffer = v19;
              v4 = 2;
              *(_BYTE *)(v20 + v6 + 37) = 10;
              if ( nNumberOfBytesToRead_3 == 1 )
              {
                v21 = *(_BYTE *)(__pioinfo[v14] + v6 + 38);
                if ( v21 != 10 )
                {
                  if ( v3 )
                  {
                    *v19 = v21;
                    v22 = __pioinfo[v14];
                    --v3;
                    v4 = 3;
                    lpBuffer = v19 + 1;
                    *(_BYTE *)(v22 + v6 + 38) = 10;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  v23 = _isatty(FileHandle) == 0;
  v24 = v68;
  if ( v23 || (v25 = __pioinfo[v68], *(char *)(v25 + v6 + 4) >= 0) )
  {
LABEL_44:
    if ( !ReadFile(*(HANDLE *)(__pioinfo[v24] + ((FileHandle & 0x1F) << 6)), lpBuffer, v3, &NumberOfCharsRead, 0)
      || (v29 = NumberOfCharsRead, (NumberOfCharsRead & 0x80000000) != 0)
      || NumberOfCharsRead > v3 )
    {
      LastError = GetLastError();
      if ( LastError == 5 )
      {
        *_errno() = 9;
        *__doserrno() = 5;
        goto LABEL_40;
      }
      if ( LastError == 109 )
      {
        v27 = 0;
        goto LABEL_41;
      }
      goto LABEL_39;
    }
    goto LABEL_47;
  }
  Mode = GetConsoleMode(*(HANDLE *)(v25 + ((FileHandle & 0x1F) << 6)), &Mode);
  if ( !Mode || nNumberOfBytesToRead_3 != 2 )
  {
    v24 = v68;
    goto LABEL_44;
  }
  if ( ReadConsoleW(*(HANDLE *)(__pioinfo[v68] + ((FileHandle & 0x1F) << 6)), lpBuffer, v3 >> 1, &NumberOfCharsRead, 0) )
  {
    v29 = 2 * NumberOfCharsRead;
    NumberOfCharsRead *= 2;
LABEL_47:
    v30 = v68;
    v4 += v29;
    v31 = __pioinfo[v68];
    v32 = *(_BYTE *)(v31 + v6 + 4);
    if ( v32 >= 0 )
      goto LABEL_102;
    if ( nNumberOfBytesToRead_3 != 2 )
    {
      if ( v29 && *lpMultiByteStr == 10 )
        v33 = v32 | 4;
      else
        v33 = v32 & 0xFB;
      *(_BYTE *)(v31 + v6 + 4) = v33;
      v34 = (CHAR *)lpMultiByteStr;
      Mode = (DWORD)lpMultiByteStr;
      lpBuffer = (LPVOID)&lpMultiByteStr[v4];
      if ( lpMultiByteStr < &lpMultiByteStr[v4] )
      {
        v35 = lpMultiByteStr;
        do
        {
          v36 = *v35;
          if ( *v35 == 26 )
          {
            v37 = __pioinfo[v30];
            v38 = *(_BYTE *)(v37 + v6 + 4);
            if ( (v38 & 0x40) != 0 )
              *v34++ = *v35;
            else
              *(_BYTE *)(v37 + v6 + 4) = v38 | 2;
            break;
          }
          if ( v36 == 13 )
          {
            if ( v35 >= (char *)lpBuffer - 1 )
            {
              ++v35;
              if ( !ReadFile(
                      *(HANDLE *)(__pioinfo[v30] + ((FileHandle & 0x1F) << 6)),
                      &Buffer,
                      1u,
                      &NumberOfCharsRead,
                      0)
                && GetLastError()
                || !NumberOfCharsRead )
              {
                v30 = v68;
                *v34++ = 13;
                continue;
              }
              v30 = v68;
              if ( (*(_BYTE *)(__pioinfo[v68] + v6 + 4) & 0x48) != 0 )
              {
                if ( Buffer == 10 )
                {
                  *v34++ = 10;
                }
                else
                {
                  *v34++ = 13;
                  *(_BYTE *)(__pioinfo[v30] + v6 + 5) = Buffer;
                }
                continue;
              }
              if ( v34 == lpMultiByteStr && Buffer == 10 )
              {
                *v34++ = 10;
              }
              else
              {
                _lseeki64_nolock(FileHandle, (LARGE_INTEGER)-1LL, 1u);
                v30 = v68;
                if ( Buffer != 10 )
                {
                  *v34 = 13;
                  goto LABEL_76;
                }
              }
            }
            else
            {
              if ( v35[1] == 10 )
              {
                v35 += 2;
                *v34 = 10;
LABEL_76:
                ++v34;
                continue;
              }
              *v34 = 13;
              ++v35;
              ++v34;
            }
          }
          else
          {
            *v34++ = v36;
            ++v35;
          }
        }
        while ( v35 < lpBuffer );
      }
      v28 = (CHAR *)lpMultiByteStr;
      v4 = v34 - lpMultiByteStr;
      if ( nNumberOfBytesToRead_3 != 1 || !v4 )
      {
LABEL_103:
        v27 = v65;
        goto $error_return$160;
      }
      v39 = v34 - 1;
      if ( *v39 < 0 )
      {
        for ( i = 1; !_lookuptrailbytes[(unsigned __int8)*v39]; ++i )
        {
          if ( i > 4 )
            break;
          if ( v39 < lpMultiByteStr )
            break;
          --v39;
        }
        if ( !_lookuptrailbytes[(unsigned __int8)*v39] )
        {
          *_errno() = 42;
          goto LABEL_40;
        }
        if ( _lookuptrailbytes[(unsigned __int8)*v39] + 1 == i )
        {
          v39 += i;
        }
        else
        {
          v41 = __pioinfo[v68];
          if ( (*(_BYTE *)(v41 + v6 + 4) & 0x48) != 0 )
          {
            v42 = *v39;
            v43 = v39 + 1;
            *(_BYTE *)(v41 + v6 + 5) = v42;
            v44 = v68;
            if ( i >= 2 )
            {
              v45 = *v43++;
              *(_BYTE *)(__pioinfo[v68] + v6 + 37) = v45;
              v44 = v68;
            }
            if ( i == 3 )
            {
              v46 = __pioinfo[v44];
              v47 = *v43++;
              *(_BYTE *)(v46 + v6 + 38) = v47;
            }
            v39 = &v43[-i];
          }
          else
          {
            _lseeki64_nolock(FileHandle, (LARGE_INTEGER)-i, 1u);
          }
        }
      }
      else
      {
        ++v39;
      }
      v48 = v39 - lpMultiByteStr;
      v49 = MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, v48, (LPWSTR)lpWideCharStr, nNumberOfBytesToRead >> 1);
      v4 = v49;
      if ( !v49 )
        goto LABEL_38;
      v4 = 2 * v49;
      *(_DWORD *)(__pioinfo[v68] + v6 + 48) = v49 != v48;
LABEL_102:
      v28 = (CHAR *)lpMultiByteStr;
      goto LABEL_103;
    }
    if ( Mode )
    {
      v51 = (CHAR *)lpMultiByteStr;
      v52 = lpMultiByteStr;
      v53 = &lpMultiByteStr[2 * (v4 / 2)];
      if ( lpMultiByteStr < v53 )
      {
        while ( 1 )
        {
          v54 = *(_WORD *)v52;
          if ( *(_WORD *)v52 == 26 )
            break;
          if ( v54 == 13 )
          {
            if ( v52 < v53 - 2 )
            {
              v52 += 2;
              v55 = 10;
              if ( *(_WORD *)v52 != 10 )
                v55 = 13;
              *(_WORD *)v51 = v55;
              v51 += 2;
            }
          }
          else
          {
            *(_WORD *)v51 = v54;
            v51 += 2;
            v52 += 2;
          }
          if ( v52 >= v53 )
            goto LABEL_121;
        }
        *(_BYTE *)(__pioinfo[v68] + v6 + 4) |= 2u;
      }
LABEL_121:
      v28 = (CHAR *)lpMultiByteStr;
      v4 = (v51 - lpMultiByteStr) & 0xFFFFFFFE;
      goto LABEL_103;
    }
    if ( v29 && (v30 = v68, *(_WORD *)lpMultiByteStr == 10) )
      v56 = v32 | 4;
    else
      v56 = v32 & 0xFB;
    *(_BYTE *)(v31 + v6 + 4) = v56;
    v57 = (CHAR *)lpMultiByteStr;
    Mode = (DWORD)&lpMultiByteStr[v4];
    if ( lpMultiByteStr >= &lpMultiByteStr[v4] )
    {
LABEL_155:
      v28 = (CHAR *)lpMultiByteStr;
      v4 = v57 - lpMultiByteStr;
      goto LABEL_103;
    }
    v58 = lpMultiByteStr;
    while ( 1 )
    {
      v59 = *(_WORD *)v58;
      if ( *(_WORD *)v58 == 26 )
      {
        v60 = __pioinfo[v30];
        v61 = *(_BYTE *)(v60 + v6 + 4);
        if ( (v61 & 0x40) != 0 )
        {
          *(_WORD *)v57 = *(_WORD *)v58;
          v57 += 2;
        }
        else
        {
          *(_BYTE *)(v60 + v6 + 4) = v61 | 2;
        }
        goto LABEL_155;
      }
      if ( v59 != 13 )
        break;
      if ( (unsigned int)v58 < Mode - 2 )
      {
        v30 = v68;
        if ( *((_WORD *)v58 + 1) == 10 )
        {
          v58 += 4;
          *(_WORD *)v57 = 10;
LABEL_150:
          v57 += 2;
          goto LABEL_143;
        }
        *(_WORD *)v57 = 13;
        goto LABEL_135;
      }
      v58 += 2;
      if ( !ReadFile(*(HANDLE *)(__pioinfo[v30] + ((FileHandle & 0x1F) << 6)), &v69, 2u, &NumberOfCharsRead, 0)
        && GetLastError()
        || !NumberOfCharsRead )
      {
        v30 = v68;
        *(_WORD *)v57 = 13;
        v57 += 2;
        goto LABEL_143;
      }
      v30 = v68;
      if ( (*(_BYTE *)(__pioinfo[v68] + v6 + 4) & 0x48) != 0 )
      {
        if ( v69 == 10 )
        {
          *(_WORD *)v57 = 10;
          v57 += 2;
        }
        else
        {
          *(_WORD *)v57 = 13;
          v57 += 2;
          *(_BYTE *)(__pioinfo[v30] + v6 + 5) = v69;
          *(_BYTE *)(__pioinfo[v30] + v6 + 37) = HIBYTE(v69);
          *(_BYTE *)(__pioinfo[v30] + v6 + 38) = 10;
        }
        goto LABEL_143;
      }
      if ( v57 == lpMultiByteStr && v69 == 10 )
      {
        *(_WORD *)v57 = 10;
        v57 += 2;
      }
      else
      {
        _lseeki64_nolock(FileHandle, (LARGE_INTEGER)-2LL, 1u);
        v30 = v68;
        if ( v69 != 10 )
        {
          *(_WORD *)v57 = 13;
          goto LABEL_150;
        }
      }
LABEL_143:
      if ( (unsigned int)v58 >= Mode )
        goto LABEL_155;
    }
    *(_WORD *)v57 = v59;
LABEL_135:
    v57 += 2;
    v58 += 2;
    goto LABEL_143;
  }
LABEL_38:
  LastError = GetLastError();
LABEL_39:
  _dosmaperr(LastError);
LABEL_40:
  v27 = -1;
LABEL_41:
  v28 = (CHAR *)lpMultiByteStr;
$error_return$160:
  if ( v28 != lpWideCharStr )
    free(v28);
  if ( v27 != -2 )
    return v27;
  return v4;
}

```

## disassembly

```asm
0x1003c3cb  push    ebp
0x1003c3cc  mov     ebp, esp
0x1003c3ce  sub     esp, 28h
0x1003c3d1  mov     eax, [ebp+FileHandle]
0x1003c3d4  push    ebx
0x1003c3d5  push    esi
0x1003c3d6  mov     esi, [ebp+nNumberOfBytesToRead]
0x1003c3d9  push    edi
0x1003c3da  push    0FFFFFFFEh
0x1003c3dc  pop     ecx
0x1003c3dd  xor     edi, edi
0x1003c3df  mov     [ebp+var_18], ecx
0x1003c3e2  mov     [ebp+Mode], edi
0x1003c3e5  mov     [ebp+var_28], esi
0x1003c3e8  cmp     eax, ecx
0x1003c3ea  jnz     short loc_1003C403
0x1003c3ec  call    ___doserrno
0x1003c3f1  mov     [eax], edi
0x1003c3f3  call    __errno
0x1003c3f8  mov     dword ptr [eax], 9
0x1003c3fe  jmp     loc_1003CB52
0x1003c403  test    eax, eax
0x1003c405  js      loc_1003CB3B
0x1003c40b  cmp     eax, __nhandle
0x1003c411  jnb     loc_1003CB3B
0x1003c417  mov     ecx, eax
0x1003c419  mov     ebx, eax
0x1003c41b  sar     ecx, 5
0x1003c41e  and     ebx, 1Fh
0x1003c421  shl     ebx, 6
0x1003c424  mov     [ebp+var_C], ecx
0x1003c427  mov     [ebp+var_24], ebx
0x1003c42a  mov     edx, ___pioinfo[ecx*4]
0x1003c431  mov     al, [edx+ebx+4]
0x1003c435  test    al, 1
0x1003c437  jz      loc_1003CB3B
0x1003c43d  cmp     esi, 7FFFFFFFh
0x1003c443  jbe     short loc_1003C45C
0x1003c445  call    ___doserrno
0x1003c44a  mov     [eax], edi
0x1003c44c  call    __errno
0x1003c451  mov     dword ptr [eax], 16h
0x1003c457  jmp     loc_1003CB4D
0x1003c45c  test    esi, esi
0x1003c45e  jz      loc_1003CB37
0x1003c464  test    al, 2
0x1003c466  jnz     loc_1003CB37
0x1003c46c  cmp     [ebp+lpWideCharStr], edi
0x1003c46f  jnz     short loc_1003C47A
0x1003c471  call    ___doserrno
0x1003c476  and     [eax], edi
0x1003c478  jmp     short loc_1003C44C
0x1003c47a  mov     al, [edx+ebx+24h]
0x1003c47e  add     al, al
0x1003c480  sar     al, 1
0x1003c482  mov     byte ptr [ebp+nNumberOfBytesToRead+3], al
0x1003c485  movsx   eax, al
0x1003c488  dec     eax
0x1003c489  jz      short loc_1003C4A1
0x1003c48b  dec     eax
0x1003c48c  jnz     short loc_1003C499
0x1003c48e  mov     eax, esi
0x1003c490  not     eax
0x1003c492  test    al, 1
0x1003c494  jz      short loc_1003C471
0x1003c496  and     esi, 0FFFFFFFEh
0x1003c499  mov     eax, [ebp+lpWideCharStr]
0x1003c49c  mov     [ebp+lpMultiByteStr], eax
0x1003c49f  jmp     short loc_1003C505
0x1003c4a1  mov     eax, esi
0x1003c4a3  not     eax
0x1003c4a5  test    al, 1
0x1003c4a7  jz      short loc_1003C471
0x1003c4a9  shr     esi, 1
0x1003c4ab  cmp     esi, 4
0x1003c4ae  jnb     short loc_1003C4B3
0x1003c4b0  push    4
0x1003c4b2  pop     esi
0x1003c4b3  push    esi; Size
0x1003c4b4  call    __malloc_crt
0x1003c4b9  mov     [ebp+lpMultiByteStr], eax
0x1003c4bc  pop     ecx
0x1003c4bd  test    eax, eax
0x1003c4bf  jnz     short loc_1003C4DC
0x1003c4c1  call    __errno
0x1003c4c6  mov     dword ptr [eax], 0Ch
0x1003c4cc  call    ___doserrno
0x1003c4d1  mov     dword ptr [eax], 8
0x1003c4d7  jmp     loc_1003CB52
0x1003c4dc  push    1; dwMoveMethod
0x1003c4de  push    0
0x1003c4e0  push    0; liDistanceToMove
0x1003c4e2  push    [ebp+FileHandle]; FileHandle
0x1003c4e5  call    __lseeki64_nolock
0x1003c4ea  mov     ecx, [ebp+var_C]
0x1003c4ed  add     esp, 10h
0x1003c4f0  mov     ecx, ___pioinfo[ecx*4]
0x1003c4f7  mov     [ecx+ebx+28h], eax
0x1003c4fb  mov     eax, [ebp+lpMultiByteStr]
0x1003c4fe  mov     [ecx+ebx+2Ch], edx
0x1003c502  mov     ecx, [ebp+var_C]
0x1003c505  mov     edx, ___pioinfo[ecx*4]
0x1003c50c  mov     ecx, [ebp+var_C]
0x1003c50f  mov     [ebp+lpBuffer], eax
0x1003c512  test    byte ptr [edx+ebx+4], 48h
0x1003c517  jz      loc_1003C5A2
0x1003c51d  mov     dl, [edx+ebx+5]
0x1003c521  cmp     dl, 0Ah
0x1003c524  jz      short loc_1003C5A2
0x1003c526  test    esi, esi
0x1003c528  jz      short loc_1003C5A2
0x1003c52a  mov     [eax], dl
0x1003c52c  xor     edi, edi
0x1003c52e  lea     edx, [eax+1]
0x1003c531  inc     edi
0x1003c532  mov     eax, ___pioinfo[ecx*4]
0x1003c539  dec     esi
0x1003c53a  cmp     byte ptr [ebp+nNumberOfBytesToRead+3], 0
0x1003c53e  mov     [ebp+lpBuffer], edx
0x1003c541  mov     byte ptr [eax+ebx+5], 0Ah
0x1003c546  jz      short loc_1003C5A2
0x1003c548  mov     eax, ___pioinfo[ecx*4]
0x1003c54f  mov     al, [eax+ebx+25h]
0x1003c553  cmp     al, 0Ah
0x1003c555  jz      short loc_1003C5A2
0x1003c557  test    esi, esi
0x1003c559  jz      short loc_1003C5A2
0x1003c55b  mov     [edx], al
0x1003c55d  inc     edx
0x1003c55e  mov     eax, ___pioinfo[ecx*4]
0x1003c565  dec     esi
0x1003c566  cmp     byte ptr [ebp+nNumberOfBytesToRead+3], 1
0x1003c56a  push    2
0x1003c56c  mov     [ebp+lpBuffer], edx
0x1003c56f  pop     edi
0x1003c570  mov     byte ptr [eax+ebx+25h], 0Ah
0x1003c575  jnz     short loc_1003C5A2
0x1003c577  mov     eax, ___pioinfo[ecx*4]
0x1003c57e  mov     al, [eax+ebx+26h]
0x1003c582  cmp     al, 0Ah
0x1003c584  jz      short loc_1003C5A2
0x1003c586  test    esi, esi
0x1003c588  jz      short loc_1003C5A2
0x1003c58a  push    3
0x1003c58c  mov     [edx], al
0x1003c58e  inc     edx
0x1003c58f  mov     eax, ___pioinfo[ecx*4]
0x1003c596  dec     esi
0x1003c597  pop     edi
0x1003c598  push    0Ah
0x1003c59a  pop     ecx
0x1003c59b  mov     [ebp+lpBuffer], edx
0x1003c59e  mov     [eax+ebx+26h], cl
0x1003c5a2  push    [ebp+FileHandle]; FileHandle
0x1003c5a5  call    __isatty
0x1003c5aa  test    eax, eax
0x1003c5ac  mov     eax, [ebp+var_C]
0x1003c5af  pop     ecx
0x1003c5b0  jz      short loc_1003C623
0x1003c5b2  mov     ecx, ___pioinfo[eax*4]
0x1003c5b9  test    byte ptr [ecx+ebx+4], 80h
0x1003c5be  jz      short loc_1003C623
0x1003c5c0  lea     eax, [ebp+Mode]
0x1003c5c3  push    eax; lpMode
0x1003c5c4  push    dword ptr [ecx+ebx]; hConsoleHandle
0x1003c5c7  call    ds:__imp__GetConsoleMode@8
0x1003c5cd  mov     [ebp+Mode], eax
0x1003c5d0  test    eax, eax
0x1003c5d2  jz      short loc_1003C620
0x1003c5d4  cmp     byte ptr [ebp+nNumberOfBytesToRead+3], 2
0x1003c5d8  jnz     short loc_1003C620
0x1003c5da  push    0; pInputControl
0x1003c5dc  lea     eax, [ebp+NumberOfCharsRead]
0x1003c5df  shr     esi, 1
0x1003c5e1  push    eax; lpNumberOfCharsRead
0x1003c5e2  mov     eax, [ebp+var_C]
0x1003c5e5  push    esi; nNumberOfCharsToRead
0x1003c5e6  push    [ebp+lpBuffer]; lpBuffer
0x1003c5e9  mov     eax, ___pioinfo[eax*4]
0x1003c5f0  push    dword ptr [eax+ebx]; hConsoleInput
0x1003c5f3  call    ds:__imp__ReadConsoleW@20
0x1003c5f9  test    eax, eax
0x1003c5fb  jnz     short loc_1003C615
0x1003c5fd  call    ds:__imp__GetLastError@0
0x1003c603  push    eax
0x1003c604  call    __dosmaperr
0x1003c609  pop     ecx
0x1003c60a  or      ebx, 0FFFFFFFFh
0x1003c60d  mov     eax, [ebp+lpMultiByteStr]
0x1003c610  jmp     $error_return$160
0x1003c615  mov     eax, [ebp+NumberOfCharsRead]
0x1003c618  lea     ecx, [eax+eax]
0x1003c61b  mov     [ebp+NumberOfCharsRead], ecx
0x1003c61e  jmp     short loc_1003C658
0x1003c620  mov     eax, [ebp+var_C]
0x1003c623  mov     eax, ___pioinfo[eax*4]
0x1003c62a  lea     ecx, [ebp+NumberOfCharsRead]
0x1003c62d  push    0; lpOverlapped
0x1003c62f  push    ecx; lpNumberOfBytesRead
0x1003c630  push    esi; nNumberOfBytesToRead
0x1003c631  push    [ebp+lpBuffer]; lpBuffer
0x1003c634  push    dword ptr [eax+ebx]; hFile
0x1003c637  call    ds:__imp__ReadFile@20
0x1003c63d  test    eax, eax
0x1003c63f  jz      loc_1003CB03
0x1003c645  mov     ecx, [ebp+NumberOfCharsRead]
0x1003c648  test    ecx, ecx
0x1003c64a  js      loc_1003CB03
0x1003c650  cmp     ecx, esi
0x1003c652  ja      loc_1003CB03
0x1003c658  mov     edx, [ebp+var_C]
0x1003c65b  add     edi, ecx
0x1003c65d  mov     esi, ___pioinfo[edx*4]
0x1003c664  mov     al, [esi+ebx+4]
0x1003c668  test    al, al
0x1003c66a  jns     loc_1003C8C7
0x1003c670  cmp     byte ptr [ebp+nNumberOfBytesToRead+3], 2
0x1003c674  jz      loc_1003C8E7
0x1003c67a  test    ecx, ecx
0x1003c67c  jz      short loc_1003C68A
0x1003c67e  mov     ecx, [ebp+lpMultiByteStr]
0x1003c681  cmp     byte ptr [ecx], 0Ah
0x1003c684  jnz     short loc_1003C68A
0x1003c686  or      al, 4
0x1003c688  jmp     short loc_1003C68C
0x1003c68a  and     al, 0FBh
0x1003c68c  mov     [esi+ebx+4], al
0x1003c690  mov     eax, [ebp+lpMultiByteStr]
0x1003c693  mov     esi, eax
0x1003c695  mov     [ebp+Mode], eax
0x1003c698  lea     ecx, [eax+edi]
0x1003c69b  mov     [ebp+lpBuffer], ecx
0x1003c69e  cmp     eax, ecx
0x1003c6a0  jnb     loc_1003C7B4
0x1003c6a6  push    0Dh
0x1003c6a8  pop     ecx
0x1003c6a9  mov     edi, eax
0x1003c6ab  mov     al, [edi]
0x1003c6ad  cmp     al, 1Ah
0x1003c6af  jz      loc_1003C798
0x1003c6b5  cmp     al, cl
0x1003c6b7  jz      short loc_1003C6C2
0x1003c6b9  mov     [esi], al
0x1003c6bb  inc     esi
0x1003c6bc  inc     edi
0x1003c6bd  jmp     loc_1003C75E
0x1003c6c2  mov     eax, [ebp+lpBuffer]
0x1003c6c5  dec     eax
0x1003c6c6  cmp     edi, eax
0x1003c6c8  jnb     short loc_1003C6E6
0x1003c6ca  lea     eax, [edi+1]
0x1003c6cd  cmp     byte ptr [eax], 0Ah
0x1003c6d0  jnz     short loc_1003C6DF
0x1003c6d2  push    0Ah
0x1003c6d4  pop     eax
0x1003c6d5  add     edi, 2
0x1003c6d8  mov     [esi], al
0x1003c6da  jmp     loc_1003C78A
0x1003c6df  mov     [esi], cl
0x1003c6e1  mov     edi, eax
0x1003c6e3  inc     esi
0x1003c6e4  jmp     short loc_1003C75E
0x1003c6e6  push    0; lpOverlapped
0x1003c6e8  lea     eax, [ebp+NumberOfCharsRead]
0x1003c6eb  inc     edi
0x1003c6ec  push    eax; lpNumberOfBytesRead
0x1003c6ed  push    1; nNumberOfBytesToRead
0x1003c6ef  lea     eax, [ebp+Buffer]
0x1003c6f2  push    eax; lpBuffer
0x1003c6f3  mov     eax, ___pioinfo[edx*4]
0x1003c6fa  push    dword ptr [eax+ebx]; hFile
0x1003c6fd  call    ds:__imp__ReadFile@20
0x1003c703  test    eax, eax
0x1003c705  jnz     short loc_1003C711
0x1003c707  call    ds:__imp__GetLastError@0
0x1003c70d  test    eax, eax
0x1003c70f  jnz     short loc_1003C78D
0x1003c711  cmp     [ebp+NumberOfCharsRead], 0
0x1003c715  jz      short loc_1003C78D
0x1003c717  mov     edx, [ebp+var_C]
0x1003c71a  mov     eax, ___pioinfo[edx*4]
0x1003c721  test    byte ptr [eax+ebx+4], 48h
0x1003c726  jz      short loc_1003C74B
0x1003c728  push    0Ah
0x1003c72a  pop     eax
0x1003c72b  push    0Dh
0x1003c72d  cmp     [ebp+Buffer], al
0x1003c730  jnz     short loc_1003C737
0x1003c732  mov     [esi], al
0x1003c734  inc     esi
0x1003c735  jmp     short loc_1003C75D
0x1003c737  mov     byte ptr [esi], 0Dh
0x1003c73a  inc     esi
0x1003c73b  mov     ecx, ___pioinfo[edx*4]
0x1003c742  mov     al, [ebp+Buffer]
0x1003c745  mov     [ecx+ebx+5], al
0x1003c749  jmp     short loc_1003C75D
0x1003c74b  cmp     esi, [ebp+lpMultiByteStr]
0x1003c74e  jnz     short loc_1003C769
0x1003c750  push    0Ah
  ... truncated ...
```
