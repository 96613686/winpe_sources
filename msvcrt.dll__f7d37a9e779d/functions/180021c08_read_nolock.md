# _read_nolock

- ea: `0x180021c08`
- end: `0x18002254b`
- name: `_read_nolock`
- size: `2371`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180020ee8`
- `0x180021ae0`
- `0x1800227c0`

## callees

- `0x180007e80`
- `0x180007ea8`
- `0x180007f00`
- `0x18001d300`
- `0x18001d568`
- `0x180020500`
- `0x1800209f8`
- `0x180021c08`
- `0x18002f050`

## import_xrefs

- `api-ms-win-core-console-l1-1-0!GetConsoleMode` at `0x180021e50`
- `api-ms-win-core-console-l1-1-0!GetConsoleMode` at `0x180021e50`
- `api-ms-win-core-console-l1-1-0!ReadConsoleW` at `0x180021e8b`
- `api-ms-win-core-console-l1-1-0!ReadConsoleW` at `0x180021e8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800223bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800224d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800223bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800224d6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180021ef8`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180021ff6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800223b3`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180021ef8`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180021ff6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800223b3`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800221f3`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800221f3`

## pseudocode

```c
__int64 __fastcall read_nolock(int a1, WCHAR *a2, DWORD a3)
{
  int v3; // edi
  int v5; // r8d
  __int64 v7; // r12
  unsigned __int64 v8; // r14
  char v9; // dl
  __int64 v10; // rcx
  char v11; // al
  int v12; // r13d
  CHAR *v13; // rsi
  __int64 v14; // rax
  CHAR *v15; // r15
  CHAR v16; // al
  __int64 v17; // rcx
  CHAR v18; // dl
  CHAR v19; // dl
  __int64 v20; // rcx
  DWORD LastError; // eax
  unsigned int v22; // r13d
  WCHAR *v23; // r14
  DWORD v25; // edx
  __int64 v26; // r8
  char v27; // al
  char v28; // al
  CHAR *v29; // rbx
  CHAR *v30; // r15
  CHAR v31; // al
  __int64 v32; // rdi
  __int64 v33; // rcx
  char v34; // al
  char *v35; // rbx
  int i; // r8d
  __int64 v37; // rcx
  __int64 v38; // rax
  char v39; // r9
  char v40; // al
  char v41; // al
  int v42; // edi
  unsigned __int64 v43; // rbx
  int v44; // eax
  DWORD v45; // eax
  char *v46; // r8
  CHAR *v47; // r9
  CHAR *v48; // rdx
  __int16 v49; // ax
  __int64 v50; // rax
  char v51; // al
  CHAR *v52; // rbx
  CHAR *v53; // r15
  __int16 v54; // ax
  __int64 v55; // rdx
  __int64 v56; // rdx
  __int64 v57; // rdx
  char v58; // al
  DWORD NumberOfCharsRead; // [rsp+30h] [rbp-48h] BYREF
  DWORD Mode[2]; // [rsp+38h] [rbp-40h] BYREF
  int v61; // [rsp+40h] [rbp-38h]
  __int64 v62; // [rsp+48h] [rbp-30h]
  __int64 v63; // [rsp+50h] [rbp-28h]
  __int64 v64; // [rsp+58h] [rbp-20h]
  __int64 v65; // [rsp+60h] [rbp-18h]
  char Buffer; // [rsp+D0h] [rbp+58h] BYREF
  __int16 v69; // [rsp+D8h] [rbp+60h] BYREF

  v3 = 0;
  v5 = a1;
  NumberOfCharsRead = 0;
  Buffer = 0;
  v69 = 0;
  if ( a1 == -2 )
  {
    *_doserrno() = 0;
    *errno() = 9;
    return 0xFFFFFFFFLL;
  }
  if ( a1 < 0 )
    goto LABEL_157;
  if ( a1 >= (unsigned int)nhandle )
    goto LABEL_157;
  v7 = 56LL * (a1 & 0x1F);
  v8 = (unsigned __int64)a1 >> 5;
  v9 = a1;
  v65 = a1 & 0x1F;
  v64 = a1;
  v62 = v7;
  v10 = _pioinfo[v8];
  v11 = *(_BYTE *)(v7 + v10 + 8);
  if ( (v11 & 1) == 0 )
  {
LABEL_157:
    *_doserrno() = 0;
    *errno() = 9;
LABEL_158:
    invalid_parameter(0, 0, 0, 0, 0);
  }
  if ( a3 > 0x7FFFFFFF )
    goto LABEL_7;
  if ( !a3 || (v11 & 2) != 0 )
    return 0;
  if ( !a2 )
    goto LABEL_7;
  v12 = *(_DWORD *)(v7 + v10 + 12) & 3;
  LODWORD(v63) = a3;
  v61 = v12;
  if ( v12 != 1 )
  {
    if ( v12 != 2 )
    {
LABEL_15:
      v13 = (CHAR *)a2;
      goto LABEL_22;
    }
    if ( (a3 & 1) == 0 )
    {
      a3 &= ~1u;
      goto LABEL_15;
    }
    goto LABEL_7;
  }
  if ( (a3 & 1) != 0 )
  {
LABEL_7:
    *_doserrno() = 0;
    *errno() = 22;
    goto LABEL_158;
  }
  a3 >>= 1;
  if ( a3 < 4 )
    a3 = 4;
  v13 = (CHAR *)malloc_crt(a3);
  if ( !v13 )
  {
    *errno() = 12;
    *_doserrno() = 8;
    return 0xFFFFFFFFLL;
  }
  v5 = a1;
  v9 = v64;
LABEL_22:
  v14 = _pioinfo[v8];
  v15 = v13;
  Mode[0] = 0;
  if ( (*(_BYTE *)(v7 + v14 + 8) & 0x48) != 0 )
  {
    v16 = *(_BYTE *)(v7 + v14 + 9);
    if ( v16 != 10 )
    {
      if ( a3 )
      {
        *v13 = v16;
        v15 = v13 + 1;
        v3 = 1;
        --a3;
        *(_BYTE *)(v7 + _pioinfo[v8] + 9) = 10;
        if ( v12 )
        {
          v17 = 56LL * (v9 & 0x1F);
          v18 = *(_BYTE *)(v17 + _pioinfo[v8] + 10);
          if ( v18 != 10 )
          {
            if ( a3 )
            {
              *v15 = v18;
              v3 = 2;
              v15 = v13 + 2;
              --a3;
              *(_BYTE *)(v17 + _pioinfo[v8] + 10) = 10;
              if ( v12 == 1 )
              {
                v19 = *(_BYTE *)(v17 + _pioinfo[v8] + 11);
                if ( v19 != 10 )
                {
                  if ( a3 )
                  {
                    *v15 = v19;
                    v3 = 3;
                    v15 = v13 + 3;
                    --a3;
                    *(_BYTE *)(v17 + _pioinfo[v8] + 11) = 10;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( isatty(v5)
    && (v20 = _pioinfo[v8], *(char *)(v7 + v20 + 8) < 0)
    && (Mode[0] = 0, (Mode[0] = GetConsoleMode(*(HANDLE *)(v7 + v20), Mode)) != 0)
    && v12 == 2 )
  {
    if ( !ReadConsoleW(*(HANDLE *)(v7 + _pioinfo[v8]), v15, a3 >> 1, &NumberOfCharsRead, 0) )
    {
      LastError = GetLastError();
LABEL_38:
      dosmaperr(LastError);
LABEL_39:
      v22 = -1;
      goto LABEL_40;
    }
    v25 = 2 * NumberOfCharsRead;
    NumberOfCharsRead *= 2;
  }
  else if ( !ReadFile(*(HANDLE *)(v7 + _pioinfo[v8]), v15, a3, &NumberOfCharsRead, 0)
         || (v25 = NumberOfCharsRead, (NumberOfCharsRead & 0x80000000) != 0)
         || (int)NumberOfCharsRead > (unsigned __int64)a3 )
  {
    LastError = GetLastError();
    if ( LastError == 5 )
    {
      *errno() = 9;
      *_doserrno() = 5;
      goto LABEL_39;
    }
    if ( LastError == 109 )
    {
      v22 = 0;
      goto LABEL_40;
    }
    goto LABEL_38;
  }
  v3 += v25;
  v22 = -2;
  v26 = v7 + _pioinfo[v8];
  v27 = *(_BYTE *)(v26 + 8);
  if ( v27 >= 0 )
    goto LABEL_40;
  if ( v61 != 2 )
  {
    if ( v25 && *v13 == 10 )
      v28 = v27 | 4;
    else
      v28 = v27 & 0xFB;
    *(_BYTE *)(v26 + 8) = v28;
    v29 = v13;
    v30 = v13;
    *(_QWORD *)Mode = &v13[v3];
    if ( (unsigned __int64)v13 >= *(_QWORD *)Mode )
    {
LABEL_84:
      v3 = (_DWORD)v29 - (_DWORD)v13;
      if ( v61 != 1 || !v3 )
        goto LABEL_40;
      v35 = v29 - 1;
      if ( *v35 < 0 )
      {
        for ( i = 1; !*((_BYTE *)lookuptrailbytes + (unsigned __int8)*v35) && i <= 4 && v35 >= v13; ++i )
          --v35;
        v37 = (unsigned __int8)*v35;
        if ( !*((_BYTE *)lookuptrailbytes + v37) )
        {
          *errno() = 42;
          goto LABEL_39;
        }
        if ( *((char *)lookuptrailbytes + v37) + 1 == i )
        {
          LODWORD(v35) = i + (_DWORD)v35;
        }
        else
        {
          v38 = _pioinfo[v8];
          if ( (*(_BYTE *)(v7 + v38 + 8) & 0x48) != 0 )
          {
            ++v35;
            *(_BYTE *)(v7 + v38 + 9) = v37;
            if ( i >= 2 )
            {
              v39 = v64;
              v40 = *v35++;
              *(_BYTE *)(56 * (v64 & 0x1F) + _pioinfo[v8] + 10) = v40;
              if ( i == 3 )
              {
                v41 = *v35;
                LODWORD(v35) = (_DWORD)v35 + 1;
                *(_BYTE *)(56LL * (v39 & 0x1F) + _pioinfo[v8] + 11) = v41;
              }
            }
            LODWORD(v35) = (_DWORD)v35 - i;
          }
          else
          {
            lseeki64_nolock((unsigned int)a1, -i, 1);
          }
        }
      }
      else
      {
        LODWORD(v35) = (_DWORD)v35 + 1;
      }
      v23 = a2;
      v42 = (int)v35;
      v43 = (unsigned int)v63;
      v3 = v42 - (_DWORD)v13;
      v44 = MultiByteToWideChar(0xFDE9u, 0, v13, v3, a2, (unsigned int)v63 >> 1);
      if ( v44 && 2LL * v44 <= v43 )
      {
        v3 = 2 * v44;
      }
      else
      {
        v45 = GetLastError();
        dosmaperr(v45);
        v22 = -1;
      }
      goto LABEL_41;
    }
    while ( 1 )
    {
      v31 = *v30;
      if ( *v30 == 26 )
      {
        v33 = _pioinfo[v8];
        v7 = v62;
        v34 = *(_BYTE *)(v62 + v33 + 8);
        if ( (v34 & 0x40) != 0 )
          *v29++ = 26;
        else
          *(_BYTE *)(v62 + v33 + 8) = v34 | 2;
        goto LABEL_84;
      }
      if ( v31 == 13 )
      {
        if ( (unsigned __int64)v30 < *(_QWORD *)Mode - 1LL )
        {
          if ( v30[1] == 10 )
          {
            v30 += 2;
            *v29 = 10;
          }
          else
          {
            *v29 = 13;
            ++v30;
          }
          ++v29;
          goto LABEL_79;
        }
        v32 = v62;
        ++v30;
        if ( !ReadFile(*(HANDLE *)(v62 + _pioinfo[v8]), &Buffer, 1u, &NumberOfCharsRead, 0) && GetLastError()
          || !NumberOfCharsRead )
        {
LABEL_77:
          *v29 = 13;
          goto LABEL_78;
        }
        if ( (*(_BYTE *)(v32 + _pioinfo[v8] + 8) & 0x48) != 0 )
        {
          if ( Buffer == 10 )
          {
            *v29 = 10;
          }
          else
          {
            *v29 = 13;
            *(_BYTE *)(v32 + _pioinfo[v8] + 9) = Buffer;
          }
          ++v29;
          goto LABEL_79;
        }
        if ( v29 == v13 && Buffer == 10 )
        {
          *v29 = 10;
LABEL_78:
          ++v29;
          goto LABEL_79;
        }
        lseeki64_nolock((unsigned int)a1, -1, 1);
        if ( Buffer != 10 )
          goto LABEL_77;
      }
      else
      {
        *v29++ = v31;
        ++v30;
      }
LABEL_79:
      if ( (unsigned __int64)v30 >= *(_QWORD *)Mode )
      {
        v7 = v62;
        goto LABEL_84;
      }
    }
  }
  if ( !Mode[0] )
  {
    if ( v25 && *(_WORD *)v13 == 10 )
      v51 = v27 | 4;
    else
      v51 = v27 & 0xFB;
    v52 = v13;
    v53 = v13;
    *(_BYTE *)(v26 + 8) = v51;
    *(_QWORD *)Mode = &v13[v3 - 1];
    if ( (unsigned __int64)v13 >= *(_QWORD *)Mode )
      goto LABEL_151;
    while ( 1 )
    {
      v54 = *(_WORD *)v53;
      if ( *(_WORD *)v53 == 26 )
      {
        v57 = _pioinfo[v8];
        v58 = *(_BYTE *)(v57 + 56 * v65 + 8);
        if ( (v58 & 0x40) != 0 )
        {
          *(_WORD *)v52 = 26;
          LODWORD(v52) = (_DWORD)v52 + 2;
        }
        else
        {
          *(_BYTE *)(v57 + 56 * v65 + 8) = v58 | 2;
        }
LABEL_151:
        v3 = (_DWORD)v52 - (_DWORD)v13;
        goto LABEL_40;
      }
      if ( v54 == 13 )
      {
        if ( v53 < &v13[v3 - 2] )
        {
          if ( *((_WORD *)v53 + 1) == 10 )
          {
            v53 += 4;
            *(_WORD *)v52 = 10;
          }
          else
          {
            *(_WORD *)v52 = 13;
            v53 += 2;
          }
          v52 += 2;
          goto LABEL_146;
        }
        v63 = a1 & 0x1F;
        v53 += 2;
        if ( !ReadFile(*(HANDLE *)(_pioinfo[(unsigned __int64)a1 >> 5] + 56 * v63), &v69, 2u, &NumberOfCharsRead, 0)
          && GetLastError()
          || !NumberOfCharsRead )
        {
LABEL_144:
          *(_WORD *)v52 = 13;
          goto LABEL_145;
        }
        if ( (*(_BYTE *)(v62 + _pioinfo[v8] + 8) & 0x48) != 0 )
        {
          if ( v69 == 10 )
          {
LABEL_139:
            *(_WORD *)v52 = 10;
          }
          else
          {
            v55 = 56 * v63;
            *(_WORD *)v52 = 13;
            *(_BYTE *)(_pioinfo[v8] + v55 + 9) = v69;
            v56 = 56 * (v64 & 0x1F);
            *(_BYTE *)(_pioinfo[v8] + v56 + 10) = HIBYTE(v69);
            *(_BYTE *)(_pioinfo[v8] + v56 + 11) = 10;
          }
LABEL_145:
          v52 += 2;
          goto LABEL_146;
        }
        if ( v52 == v13 && v69 == 10 )
          goto LABEL_139;
        lseeki64_nolock((unsigned int)a1, -2, 1);
        if ( v69 != 10 )
          goto LABEL_144;
      }
      else
      {
        *(_WORD *)v52 = v54;
        v52 += 2;
        v53 += 2;
      }
LABEL_146:
      if ( (unsigned __int64)v53 >= *(_QWORD *)Mode )
        goto LABEL_151;
    }
  }
  v46 = v13;
  v47 = v13;
  v48 = &v13[2 * (v3 / 2)];
  if ( v13 >= v48 )
    goto LABEL_120;
  while ( 1 )
  {
    v49 = *(_WORD *)v47;
    if ( *(_WORD *)v47 == 26 )
      break;
    if ( v49 != 13 )
    {
      *(_WORD *)v46 = v49;
LABEL_116:
      v46 += 2;
      v47 += 2;
      goto LABEL_117;
    }
    if ( v47 < &v13[2 * (v3 / 2) - 2] )
    {
      if ( *((_WORD *)v47 + 1) != 10 )
      {
        *(_WORD *)v46 = 13;
        goto LABEL_116;
      }
      v47 += 2;
      *(_WORD *)v46 = 10;
      v46 += 2;
    }
LABEL_117:
    if ( v47 >= v48 )
      goto LABEL_120;
  }
  v50 = _pioinfo[(unsigned __int64)a1 >> 5];
  *(_BYTE *)(v50 + 56LL * (a1 & 0x1F) + 8) |= 2u;
LABEL_120:
  v3 = 2 * ((v46 - v13) >> 1);
LABEL_40:
  v23 = a2;
LABEL_41:
  if ( v13 != (CHAR *)v23 )
    free(v13);
  if ( v22 == -2 )
    return (unsigned int)v3;
  return v22;
}

```

## disassembly

```asm
0x180021c08  mov     [rsp-40h+lpWideCharStr], rdx
0x180021c0d  mov     [rsp-40h+arg_0], ecx
0x180021c11  push    rbp
0x180021c12  push    rbx
0x180021c13  push    rsi
0x180021c14  push    rdi
0x180021c15  push    r12
0x180021c17  push    r13
0x180021c19  push    r14
0x180021c1b  push    r15
0x180021c1d  mov     rbp, rsp
0x180021c20  sub     rsp, 78h
0x180021c24  xor     edi, edi
0x180021c26  mov     ebx, r8d
0x180021c29  movsxd  r8, ecx
0x180021c2c  mov     r9, rdx
0x180021c2f  mov     [rbp+NumberOfCharsRead], edi
0x180021c32  mov     [rbp+Buffer], dil
0x180021c36  mov     [rbp+arg_18], di
0x180021c3a  cmp     r8d, 0FFFFFFFEh
0x180021c3e  jnz     short loc_180021C57
0x180021c40  call    __doserrno
0x180021c45  mov     [rax], edi
0x180021c47  call    _errno
0x180021c4c  mov     dword ptr [rax], 9
0x180021c52  jmp     loc_180022537
0x180021c57  test    ecx, ecx
0x180021c59  js      loc_180022511
0x180021c5f  cmp     r8d, cs:_nhandle
0x180021c66  jnb     loc_180022511
0x180021c6c  mov     eax, r8d
0x180021c6f  lea     r10, cs:180000000h
0x180021c76  and     eax, 1Fh
0x180021c79  mov     r14, r8
0x180021c7c  imul    r12, rax, 38h ; '8'
0x180021c80  shr     r14, 5
0x180021c84  mov     rdx, r8
0x180021c87  mov     [rbp+var_18], rax
0x180021c8b  mov     [rbp+var_20], rdx
0x180021c8f  mov     [rbp+var_30], r12
0x180021c93  mov     rcx, rva __pioinfo[r10+r14*8]
0x180021c9b  mov     al, [r12+rcx+8]
0x180021ca0  test    al, 1
0x180021ca2  jz      loc_180022511
0x180021ca8  cmp     ebx, 7FFFFFFFh
0x180021cae  jbe     short loc_180021CC7
0x180021cb0  call    __doserrno
0x180021cb5  mov     [rax], edi
0x180021cb7  call    _errno
0x180021cbc  mov     dword ptr [rax], 16h
0x180021cc2  jmp     loc_180022523
0x180021cc7  test    ebx, ebx
0x180021cc9  jz      loc_18002250D
0x180021ccf  test    al, 2
0x180021cd1  jnz     loc_18002250D
0x180021cd7  test    r9, r9
0x180021cda  jz      short loc_180021CB0
0x180021cdc  mov     r13d, [r12+rcx+0Ch]
0x180021ce1  mov     ecx, 4
0x180021ce6  and     r13d, 3
0x180021cea  mov     dword ptr [rbp+var_28], ebx
0x180021ced  mov     eax, r13d
0x180021cf0  mov     [rbp+var_38], r13d
0x180021cf4  sub     eax, 1
0x180021cf7  jz      short loc_180021D0A
0x180021cf9  cmp     eax, 1
0x180021cfc  jnz     short loc_180021D05
0x180021cfe  test    al, bl
0x180021d00  jnz     short loc_180021CB0
0x180021d02  and     ebx, 0FFFFFFFEh
0x180021d05  mov     rsi, r9
0x180021d08  jmp     short loc_180021D4F
0x180021d0a  test    bl, 1
0x180021d0d  jnz     short loc_180021CB0
0x180021d0f  shr     ebx, 1
0x180021d11  cmp     ebx, ecx
0x180021d13  cmovb   ebx, ecx
0x180021d16  mov     ecx, ebx; Size
0x180021d18  call    _malloc_crt
0x180021d1d  mov     rsi, rax
0x180021d20  test    rax, rax
0x180021d23  jnz     short loc_180021D40
0x180021d25  call    _errno
0x180021d2a  mov     dword ptr [rax], 0Ch
0x180021d30  call    __doserrno
0x180021d35  mov     dword ptr [rax], 8
0x180021d3b  jmp     loc_180022537
0x180021d40  mov     r8d, [rbp+arg_0]
0x180021d44  lea     r10, cs:180000000h
0x180021d4b  mov     rdx, [rbp+var_20]
0x180021d4f  mov     rax, rva __pioinfo[r10+r14*8]
0x180021d57  mov     r15, rsi
0x180021d5a  mov     [rbp+Mode], edi
0x180021d5d  mov     r9d, 0Ah
0x180021d63  test    byte ptr [r12+rax+8], 48h
0x180021d69  jz      loc_180021E16
0x180021d6f  mov     al, [r12+rax+9]
0x180021d74  cmp     al, r9b
0x180021d77  jz      loc_180021E16
0x180021d7d  test    ebx, ebx
0x180021d7f  jz      loc_180021E16
0x180021d85  mov     [rsi], al
0x180021d87  lea     r15, [rsi+1]
0x180021d8b  mov     rax, rva __pioinfo[r10+r14*8]
0x180021d93  lea     edi, [r9-9]
0x180021d97  or      r11d, 0FFFFFFFFh
0x180021d9b  add     ebx, r11d
0x180021d9e  mov     [r12+rax+9], r9b
0x180021da3  test    r13d, r13d
0x180021da6  jz      short loc_180021E16
0x180021da8  mov     rax, rdx
0x180021dab  and     eax, 1Fh
0x180021dae  imul    rcx, rax, 38h ; '8'
0x180021db2  mov     rax, rva __pioinfo[r10+r14*8]
0x180021dba  mov     dl, [rcx+rax+0Ah]
0x180021dbe  cmp     dl, r9b
0x180021dc1  jz      short loc_180021E16
0x180021dc3  test    ebx, ebx
0x180021dc5  jz      short loc_180021E16
0x180021dc7  mov     [r15], dl
0x180021dca  lea     edi, [r9-8]
0x180021dce  mov     rax, rva __pioinfo[r10+r14*8]
0x180021dd6  inc     r15
0x180021dd9  add     ebx, r11d
0x180021ddc  mov     [rcx+rax+0Ah], r9b
0x180021de1  cmp     r13d, 1
0x180021de5  jnz     short loc_180021E16
0x180021de7  mov     rax, rva __pioinfo[r10+r14*8]
0x180021def  mov     dl, [rcx+rax+0Bh]
0x180021df3  cmp     dl, r9b
0x180021df6  jz      short loc_180021E16
0x180021df8  test    ebx, ebx
0x180021dfa  jz      short loc_180021E16
0x180021dfc  mov     [r15], dl
0x180021dff  lea     edi, [r9-7]
0x180021e03  mov     rax, rva __pioinfo[r10+r14*8]
0x180021e0b  inc     r15
0x180021e0e  add     ebx, r11d
0x180021e11  mov     [rcx+rax+0Bh], r9b
0x180021e16  mov     ecx, r8d; FileHandle
0x180021e19  call    _isatty
0x180021e1e  test    eax, eax
0x180021e20  jz      loc_180021ED2
0x180021e26  lea     rcx, cs:180000000h
0x180021e2d  mov     rcx, rva __pioinfo[rcx+r14*8]
0x180021e35  cmp     byte ptr [r12+rcx+8], 0
0x180021e3b  jge     loc_180021ED2
0x180021e41  mov     [rbp+Mode], 0
0x180021e48  lea     rdx, [rbp+Mode]; lpMode
0x180021e4c  mov     rcx, [r12+rcx]; hConsoleHandle
0x180021e50  call    cs:__imp_GetConsoleMode
0x180021e56  mov     [rbp+Mode], eax
0x180021e59  test    eax, eax
0x180021e5b  jz      short loc_180021ED2
0x180021e5d  cmp     r13d, 2
0x180021e61  jnz     short loc_180021ED2
0x180021e63  lea     rax, cs:180000000h
0x180021e6a  shr     ebx, 1
0x180021e6c  mov     rcx, rva __pioinfo[rax+r14*8]
0x180021e74  lea     r9, [rbp+NumberOfCharsRead]; lpNumberOfCharsRead
0x180021e78  mov     r8d, ebx; nNumberOfCharsToRead
0x180021e7b  mov     [rsp+78h+pInputControl], 0; pInputControl
0x180021e84  mov     rdx, r15; lpBuffer
0x180021e87  mov     rcx, [r12+rcx]; hConsoleInput
0x180021e8b  call    cs:__imp_ReadConsoleW
0x180021e91  test    eax, eax
0x180021e93  jnz     short loc_180021EC7
0x180021e95  call    cs:__imp_GetLastError
0x180021e9b  mov     ecx, eax
0x180021e9d  call    _dosmaperr
0x180021ea2  or      r13d, 0FFFFFFFFh
0x180021ea6  mov     r14, [rbp+lpWideCharStr]
0x180021eaa  cmp     rsi, r14
0x180021ead  jz      short loc_180021EB7
0x180021eaf  mov     rcx, rsi; Block
0x180021eb2  call    free
0x180021eb7  cmp     r13d, 0FFFFFFFEh
0x180021ebb  cmovz   r13d, edi
0x180021ebf  mov     eax, r13d
0x180021ec2  jmp     loc_18002253A
0x180021ec7  mov     eax, [rbp+NumberOfCharsRead]
0x180021eca  lea     edx, [rax+rax]
0x180021ecd  mov     [rbp+NumberOfCharsRead], edx
0x180021ed0  jmp     short loc_180021F1D
0x180021ed2  lea     rcx, cs:180000000h
0x180021ed9  mov     [rsp+78h+pInputControl], 0; lpOverlapped
0x180021ee2  mov     rcx, rva __pioinfo[rcx+r14*8]
0x180021eea  lea     r9, [rbp+NumberOfCharsRead]; lpNumberOfBytesRead
0x180021eee  mov     r8d, ebx; nNumberOfBytesToRead
0x180021ef1  mov     rdx, r15; lpBuffer
0x180021ef4  mov     rcx, [r12+rcx]; hFile
0x180021ef8  call    cs:__imp_ReadFile
0x180021efe  test    eax, eax
0x180021f00  jz      loc_1800224D6
0x180021f06  movsxd  rdx, [rbp+NumberOfCharsRead]
0x180021f0a  test    edx, edx
0x180021f0c  js      loc_1800224D6
0x180021f12  mov     eax, ebx
0x180021f14  cmp     rdx, rax
0x180021f17  ja      loc_1800224D6
0x180021f1d  lea     r11, cs:180000000h
0x180021f24  add     edi, edx
0x180021f26  mov     r8, rva __pioinfo[r11+r14*8]
0x180021f2e  mov     r13d, 0FFFFFFFEh
0x180021f34  add     r8, r12
0x180021f37  mov     al, [r8+8]
0x180021f3b  test    al, al
0x180021f3d  jns     loc_180021EA6
0x180021f43  cmp     [rbp+var_38], 2
0x180021f47  jz      loc_180022226
0x180021f4d  lea     r9d, [r13+0Ch]
0x180021f51  test    edx, edx
0x180021f53  jz      short loc_180021F5E
0x180021f55  cmp     [rsi], r9b
0x180021f58  jnz     short loc_180021F5E
0x180021f5a  or      al, 4
0x180021f5c  jmp     short loc_180021F60
0x180021f5e  and     al, 0FBh
0x180021f60  mov     [r8+8], al
0x180021f64  mov     rbx, rsi
0x180021f67  movsxd  rax, edi
0x180021f6a  mov     r15, rsi
0x180021f6d  add     rax, rsi
0x180021f70  mov     qword ptr [rbp+Mode], rax
0x180021f74  cmp     rsi, rax
0x180021f77  jnb     loc_1800220DA
0x180021f7d  mov     edx, 1Ah
0x180021f82  lea     r12d, [rdx-0Dh]
0x180021f86  mov     al, [r15]
0x180021f89  cmp     al, dl
0x180021f8b  jz      loc_1800220B7
0x180021f91  cmp     al, r12b
0x180021f94  jz      short loc_180021FA3
0x180021f96  mov     [rbx], al
0x180021f98  inc     rbx
0x180021f9b  inc     r15
0x180021f9e  jmp     loc_1800220A7
0x180021fa3  mov     rax, qword ptr [rbp+Mode]
0x180021fa7  dec     rax
0x180021faa  cmp     r15, rax
0x180021fad  jnb     short loc_180021FCC
0x180021faf  cmp     [r15+1], r9b
0x180021fb3  jnz     short loc_180021FBE
0x180021fb5  add     r15, 2
0x180021fb9  mov     [rbx], r9b
0x180021fbc  jmp     short loc_180021FC4
0x180021fbe  mov     [rbx], r12b
0x180021fc1  inc     r15
0x180021fc4  inc     rbx
0x180021fc7  jmp     loc_1800220A7
0x180021fcc  mov     rcx, rva __pioinfo[r11+r14*8]
0x180021fd4  lea     r9, [rbp+NumberOfCharsRead]; lpNumberOfBytesRead
0x180021fd8  mov     rdi, [rbp+var_30]
0x180021fdc  lea     rdx, [rbp+Buffer]; lpBuffer
0x180021fe0  mov     r8d, 1; nNumberOfBytesToRead
0x180021fe6  mov     [rsp+78h+pInputControl], 0; lpOverlapped
0x180021fef  inc     r15
0x180021ff2  mov     rcx, [rdi+rcx]; hFile
0x180021ff6  call    cs:__imp_ReadFile
0x180021ffc  test    eax, eax
0x180021ffe  jnz     short loc_18002200E
0x180022000  call    cs:__imp_GetLastError
0x180022006  test    eax, eax
0x180022008  jnz     loc_18002208F
0x18002200e  cmp     [rbp+NumberOfCharsRead], 0
0x180022012  jz      short loc_18002208F
0x180022014  lea     r11, cs:180000000h
0x18002201b  mov     rax, rva __pioinfo[r11+r14*8]
0x180022023  test    byte ptr [rdi+rax+8], 48h
0x180022028  jz      short loc_180022052
0x18002202a  mov     r9d, 0Ah
0x180022030  cmp     [rbp+Buffer], r9b
0x180022034  jnz     short loc_18002203B
0x180022036  mov     [rbx], r9b
0x180022039  jmp     short loc_18002204D
0x18002203b  mov     [rbx], r12b
0x18002203e  mov     rcx, rva __pioinfo[r11+r14*8]
0x180022046  mov     al, [rbp+Buffer]
0x180022049  mov     [rdi+rcx+9], al
0x18002204d  inc     rbx
0x180022050  jmp     short loc_1800220A2
0x180022052  cmp     rbx, rsi
0x180022055  jnz     short loc_180022068
0x180022057  mov     r9d, 0Ah
0x18002205d  cmp     [rbp+Buffer], r9b
0x180022061  jnz     short loc_180022068
0x180022063  mov     [rbx], r9b
0x180022066  jmp     short loc_18002209F
0x180022068  mov     ecx, [rbp+arg_0]
0x18002206b  mov     r8d, 1
0x180022071  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180022075  call    _lseeki64_nolock
0x18002207a  mov     r9d, 0Ah
0x180022080  lea     r11, cs:180000000h
0x180022087  cmp     [rbp+Buffer], r9b
0x18002208b  jz      short loc_1800220A2
0x18002208d  jmp     short loc_18002209C
0x18002208f  mov     r9d, 0Ah
0x180022095  lea     r11, cs:180000000h
0x18002209c  mov     [rbx], r12b
  ... truncated ...
```
