# _read_nolock

- ea: `0x18001f024`
- end: `0x18001f947`
- name: `_read_nolock`
- size: `2339`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18001eefc`

## callees

- `0x18000e448`
- `0x18000e470`
- `0x18000e4c4`
- `0x18000f1a8`
- `0x18000f264`
- `0x180010a08`
- `0x18001b68c`
- `0x18001c074`
- `0x18001f024`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x18001f5ea`
- `KERNEL32!MultiByteToWideChar` at `0x18001f5ea`
- `KERNEL32!GetLastError` at `0x18001f2b5`
- `KERNEL32!GetLastError` at `0x18001f3fe`
- `KERNEL32!GetLastError` at `0x18001f60a`
- `KERNEL32!GetLastError` at `0x18001f7b0`
- `KERNEL32!GetLastError` at `0x18001f8d6`
- `KERNEL32!GetLastError` at `0x18001f2b5`
- `KERNEL32!GetLastError` at `0x18001f3fe`
- `KERNEL32!GetLastError` at `0x18001f60a`
- `KERNEL32!GetLastError` at `0x18001f7b0`
- `KERNEL32!GetLastError` at `0x18001f8d6`
- `KERNEL32!ReadFile` at `0x18001f2ff`
- `KERNEL32!ReadFile` at `0x18001f3f4`
- `KERNEL32!ReadFile` at `0x18001f7a6`
- `KERNEL32!ReadFile` at `0x18001f2ff`
- `KERNEL32!ReadFile` at `0x18001f3f4`
- `KERNEL32!ReadFile` at `0x18001f7a6`
- `KERNEL32!GetConsoleMode` at `0x18001f270`
- `KERNEL32!GetConsoleMode` at `0x18001f270`
- `KERNEL32!ReadConsoleW` at `0x18001f2ab`
- `KERNEL32!ReadConsoleW` at `0x18001f2ab`

## pseudocode

```c
__int64 __fastcall read_nolock(int a1, WCHAR *a2, unsigned int a3)
{
  int v3; // edi
  unsigned __int64 v4; // r9
  DWORD v5; // ebx
  __int64 v7; // rcx
  unsigned __int64 v8; // r12
  char v9; // dl
  __int64 v10; // r13
  char v11; // r15
  int v12; // r8d
  CHAR *v13; // rsi
  CHAR *v14; // r14
  CHAR v15; // al
  CHAR *v16; // r13
  __int64 v17; // rcx
  CHAR v18; // dl
  CHAR v19; // dl
  __int64 v20; // rcx
  DWORD ConsoleMode; // r15d
  DWORD LastError; // eax
  DWORD v23; // ebx
  DWORD v24; // edx
  CHAR *v25; // r8
  char v26; // al
  CHAR v27; // al
  CHAR *v28; // rbx
  CHAR *v29; // rdi
  CHAR *v30; // r14
  CHAR v31; // al
  __int64 v32; // rcx
  CHAR v33; // al
  char *v34; // rbx
  int i; // r8d
  __int64 v36; // rcx
  __int64 v37; // rax
  char v38; // r9
  char v39; // al
  char v40; // al
  WCHAR *v41; // r14
  int v42; // edi
  unsigned __int64 v43; // rbx
  int v44; // eax
  DWORD v45; // eax
  char *v46; // r8
  CHAR *v47; // r9
  CHAR *v48; // rdx
  __int16 v49; // ax
  __int64 v50; // rax
  CHAR v51; // al
  CHAR *v52; // rbx
  CHAR *v53; // r14
  __int16 v54; // ax
  __int64 v55; // rdx
  __int64 v56; // rcx
  CHAR v57; // al
  DWORD NumberOfCharsRead; // [rsp+30h] [rbp-28h] BYREF
  int v60; // [rsp+34h] [rbp-24h]
  DWORD Mode; // [rsp+38h] [rbp-20h] BYREF
  DWORD v62; // [rsp+3Ch] [rbp-1Ch]
  CHAR *v63; // [rsp+40h] [rbp-18h]
  unsigned __int64 v64; // [rsp+48h] [rbp-10h]
  CHAR Buffer; // [rsp+B0h] [rbp+58h] BYREF
  __int16 v68; // [rsp+B8h] [rbp+60h] BYREF

  v3 = 0;
  v4 = a1;
  NumberOfCharsRead = 0;
  v5 = a3;
  Buffer = 0;
  v68 = 0;
  if ( a1 == -2 )
  {
    *_doserrno() = 0;
    *errno() = 9;
    return 0xFFFFFFFFLL;
  }
  if ( a1 < 0
    || a1 >= (unsigned int)nhandle
    || (v7 = 56LL * (a1 & 0x1F),
        v8 = v4 >> 5,
        v9 = v4,
        v64 = v4,
        v63 = (CHAR *)v7,
        v10 = _pioinfo[v4 >> 5],
        v11 = *(_BYTE *)(v7 + v10 + 8),
        (v11 & 1) == 0) )
  {
    *_doserrno() = 0;
    *errno() = 9;
LABEL_161:
    invalid_parameter(0, 0, 0, 0, 0);
  }
  if ( a3 > 0x7FFFFFFF )
    goto LABEL_7;
  if ( !a3 || (v11 & 2) != 0 )
    return 0;
  if ( !a2 )
    goto LABEL_7;
  v12 = *(_DWORD *)(v7 + v10 + 12) & 3;
  v62 = v5;
  v60 = v12;
  if ( v12 != 1 )
  {
    if ( v12 != 2 )
    {
LABEL_15:
      v13 = (CHAR *)a2;
      goto LABEL_22;
    }
    if ( (v5 & 1) == 0 )
    {
      v5 &= ~1u;
      goto LABEL_15;
    }
    goto LABEL_7;
  }
  if ( (v5 & 1) != 0 )
  {
LABEL_7:
    *_doserrno() = 0;
    *errno() = 22;
    goto LABEL_161;
  }
  v5 >>= 1;
  if ( v5 < 4 )
    v5 = 4;
  v13 = (CHAR *)malloc(v5);
  if ( !v13 )
  {
    *errno() = 12;
    *_doserrno() = 8;
    return 0xFFFFFFFFLL;
  }
  v7 = (__int64)v63;
  v12 = v60;
  LODWORD(v4) = a1;
  v9 = v64;
LABEL_22:
  Mode = 0;
  v14 = v13;
  if ( (v11 & 0x48) == 0 || (v15 = *(_BYTE *)(v7 + v10 + 9), v15 == 10) )
  {
    v16 = v63;
  }
  else
  {
    v16 = v63;
    if ( v5 )
    {
      *v13 = v15;
      v14 = v13 + 1;
      v3 = 1;
      --v5;
      v16[_pioinfo[v8] + 9] = 10;
      if ( v12 )
      {
        v17 = 56LL * (v9 & 0x1F);
        v18 = *(_BYTE *)(v17 + _pioinfo[v8] + 10);
        if ( v18 != 10 )
        {
          if ( v5 )
          {
            *v14 = v18;
            v3 = 2;
            v14 = v13 + 2;
            --v5;
            *(_BYTE *)(v17 + _pioinfo[v8] + 10) = 10;
            if ( v12 == 1 )
            {
              v19 = *(_BYTE *)(v17 + _pioinfo[v8] + 11);
              if ( v19 != 10 )
              {
                if ( v5 )
                {
                  *v14 = v19;
                  v3 = 3;
                  v14 = v13 + 3;
                  --v5;
                  *(_BYTE *)(v17 + _pioinfo[v8] + 11) = 10;
                }
              }
            }
          }
        }
      }
    }
  }
  if ( isatty(v4) && (v20 = _pioinfo[v8], v16[v20 + 8] < 0) )
  {
    Mode = 0;
    ConsoleMode = GetConsoleMode(*(HANDLE *)&v16[v20], &Mode);
    if ( ConsoleMode && v60 == 2 )
    {
      if ( !ReadConsoleW(*(HANDLE *)&v16[_pioinfo[v8]], v14, v5 >> 1, &NumberOfCharsRead, 0) )
      {
        LastError = GetLastError();
LABEL_39:
        dosmaperr(LastError);
LABEL_40:
        v23 = -1;
        goto LABEL_149;
      }
      v24 = 2 * NumberOfCharsRead;
      NumberOfCharsRead *= 2;
      goto LABEL_46;
    }
  }
  else
  {
    ConsoleMode = Mode;
  }
  if ( !ReadFile(*(HANDLE *)&v16[_pioinfo[v8]], v14, v5, &NumberOfCharsRead, 0)
    || (v24 = NumberOfCharsRead, (NumberOfCharsRead & 0x80000000) != 0)
    || (int)NumberOfCharsRead > (unsigned __int64)v5 )
  {
    LastError = GetLastError();
    if ( LastError == 5 )
    {
      *errno() = 9;
      *_doserrno() = 5;
      goto LABEL_40;
    }
    if ( LastError == 109 )
    {
      v23 = 0;
      goto LABEL_149;
    }
    goto LABEL_39;
  }
LABEL_46:
  v3 += v24;
  v23 = -2;
  v25 = &v16[_pioinfo[v8]];
  Mode = -2;
  v26 = v25[8];
  if ( v26 >= 0 )
    goto LABEL_149;
  if ( v60 != 2 )
  {
    if ( v24 && *v13 == 10 )
      v27 = v26 | 4;
    else
      v27 = v26 & 0xFB;
    v28 = v13;
    v29 = &v13[v3];
    v25[8] = v27;
    v30 = v13;
    while ( v30 < v29 )
    {
      v31 = *v30;
      if ( *v30 == 26 )
      {
        v32 = _pioinfo[v8];
        v33 = v16[v32 + 8];
        if ( (v33 & 0x40) != 0 )
          *v28++ = 26;
        else
          v16[v32 + 8] = v33 | 2;
        break;
      }
      if ( v31 == 13 )
      {
        if ( v30 < v29 - 1 )
        {
          if ( v30[1] == 10 )
          {
            v30 += 2;
            *v28 = 10;
          }
          else
          {
            *v28 = 13;
            ++v30;
          }
          ++v28;
          continue;
        }
        ++v30;
        if ( !ReadFile(*(HANDLE *)&v16[_pioinfo[v8]], &Buffer, 1u, &NumberOfCharsRead, 0) && GetLastError()
          || !NumberOfCharsRead )
        {
LABEL_73:
          *v28 = 13;
          goto LABEL_74;
        }
        if ( (v16[_pioinfo[v8] + 8] & 0x48) != 0 )
        {
          if ( Buffer == 10 )
          {
            *v28 = 10;
          }
          else
          {
            *v28 = 13;
            v16[_pioinfo[v8] + 9] = Buffer;
          }
          ++v28;
          continue;
        }
        if ( v28 == v13 && Buffer == 10 )
        {
          *v28 = 10;
LABEL_74:
          ++v28;
          continue;
        }
        lseeki64_nolock((unsigned int)a1, -1, 1);
        if ( Buffer != 10 )
          goto LABEL_73;
      }
      else
      {
        *v28++ = v31;
        ++v30;
      }
    }
    v3 = (_DWORD)v28 - (_DWORD)v13;
    if ( v60 == 1 && v3 )
    {
      v34 = v28 - 1;
      if ( *v34 < 0 )
      {
        for ( i = 1; !lookuptrailbytes[(unsigned __int8)*v34] && i <= 4 && v34 >= v13; ++i )
          --v34;
        v36 = (unsigned __int8)*v34;
        if ( !lookuptrailbytes[v36] )
        {
          *errno() = 42;
          goto LABEL_40;
        }
        if ( lookuptrailbytes[v36] + 1 == i )
        {
          LODWORD(v34) = i + (_DWORD)v34;
        }
        else
        {
          v37 = _pioinfo[v8];
          if ( (v16[v37 + 8] & 0x48) != 0 )
          {
            ++v34;
            v16[v37 + 9] = v36;
            if ( i >= 2 )
            {
              v38 = v64;
              v39 = *v34++;
              *(_BYTE *)(56 * (v64 & 0x1F) + _pioinfo[v8] + 10) = v39;
              if ( i == 3 )
              {
                v40 = *v34;
                LODWORD(v34) = (_DWORD)v34 + 1;
                *(_BYTE *)(56LL * (v38 & 0x1F) + _pioinfo[v8] + 11) = v40;
              }
            }
            LODWORD(v34) = (_DWORD)v34 - i;
          }
          else
          {
            lseeki64_nolock((unsigned int)a1, -i, 1);
          }
        }
      }
      else
      {
        LODWORD(v34) = (_DWORD)v34 + 1;
      }
      v41 = a2;
      v42 = (int)v34;
      v43 = v62;
      v3 = v42 - (_DWORD)v13;
      v44 = MultiByteToWideChar(0xFDE9u, 0, v13, v3, a2, v62 >> 1);
      if ( v44 && 2LL * v44 <= v43 )
      {
        v23 = Mode;
        v3 = 2 * v44;
      }
      else
      {
        v45 = GetLastError();
        dosmaperr(v45);
        v23 = -1;
      }
      goto LABEL_150;
    }
LABEL_148:
    v23 = Mode;
    goto LABEL_149;
  }
  if ( !ConsoleMode )
  {
    if ( v24 && *(_WORD *)v13 == 10 )
      v51 = v26 | 4;
    else
      v51 = v26 & 0xFB;
    v52 = v13;
    v53 = v13;
    v25[8] = v51;
    v63 = &v13[v3 - 1];
    if ( v13 >= v63 )
    {
LABEL_147:
      v3 = (_DWORD)v52 - (_DWORD)v13;
      goto LABEL_148;
    }
    while ( 1 )
    {
      v54 = *(_WORD *)v53;
      if ( *(_WORD *)v53 == 26 )
      {
        v56 = _pioinfo[v8];
        v57 = v16[v56 + 8];
        if ( (v57 & 0x40) != 0 )
        {
          *(_WORD *)v52 = 26;
          LODWORD(v52) = (_DWORD)v52 + 2;
        }
        else
        {
          v16[v56 + 8] = v57 | 2;
        }
        goto LABEL_147;
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
          goto LABEL_142;
        }
        v53 += 2;
        if ( !ReadFile(
                *(HANDLE *)(_pioinfo[(unsigned __int64)a1 >> 5] + 56LL * (a1 & 0x1F)),
                &v68,
                2u,
                &NumberOfCharsRead,
                0)
          && GetLastError()
          || !NumberOfCharsRead )
        {
LABEL_140:
          *(_WORD *)v52 = 13;
          goto LABEL_141;
        }
        if ( (v16[_pioinfo[v8] + 8] & 0x48) != 0 )
        {
          if ( v68 == 10 )
          {
LABEL_135:
            *(_WORD *)v52 = 10;
          }
          else
          {
            *(_WORD *)v52 = 13;
            v16[_pioinfo[v8] + 9] = v68;
            v55 = 56 * (v64 & 0x1F);
            *(_BYTE *)(v55 + _pioinfo[v8] + 10) = HIBYTE(v68);
            *(_BYTE *)(v55 + _pioinfo[v8] + 11) = 10;
          }
LABEL_141:
          v52 += 2;
          goto LABEL_142;
        }
        if ( v52 == v13 && v68 == 10 )
          goto LABEL_135;
        lseeki64_nolock((unsigned int)a1, -2, 1);
        if ( v68 != 10 )
          goto LABEL_140;
      }
      else
      {
        *(_WORD *)v52 = v54;
        v52 += 2;
        v53 += 2;
      }
LABEL_142:
      if ( v53 >= v63 )
        goto LABEL_147;
    }
  }
  v46 = v13;
  v47 = v13;
  v48 = &v13[2 * (v3 / 2)];
  if ( v13 >= v48 )
    goto LABEL_116;
  while ( 1 )
  {
    v49 = *(_WORD *)v47;
    if ( *(_WORD *)v47 == 26 )
      break;
    if ( v49 != 13 )
    {
      *(_WORD *)v46 = v49;
LABEL_112:
      v46 += 2;
      v47 += 2;
      goto LABEL_113;
    }
    if ( v47 < &v13[2 * (v3 / 2) - 2] )
    {
      if ( *((_WORD *)v47 + 1) != 10 )
      {
        *(_WORD *)v46 = 13;
        goto LABEL_112;
      }
      v47 += 2;
      *(_WORD *)v46 = 10;
      v46 += 2;
    }
LABEL_113:
    if ( v47 >= v48 )
      goto LABEL_116;
  }
  v50 = _pioinfo[(unsigned __int64)a1 >> 5];
  *(_BYTE *)(v50 + 56LL * (a1 & 0x1F) + 8) |= 2u;
LABEL_116:
  v3 = 2 * ((v46 - v13) >> 1);
LABEL_149:
  v41 = a2;
LABEL_150:
  if ( v13 != (CHAR *)v41 )
    free(v13);
  if ( v23 == -2 )
    return (DWORD)v3;
  return v23;
}

```

## disassembly

```asm
0x18001f024  mov     [rsp-40h+lpWideCharStr], rdx
0x18001f029  mov     [rsp-40h+arg_0], ecx
0x18001f02d  push    rbp
0x18001f02e  push    rbx
0x18001f02f  push    rsi
0x18001f030  push    rdi
0x18001f031  push    r12
0x18001f033  push    r13
0x18001f035  push    r14
0x18001f037  push    r15
0x18001f039  mov     rbp, rsp
0x18001f03c  sub     rsp, 58h
0x18001f040  xor     edi, edi
0x18001f042  movsxd  r9, ecx
0x18001f045  mov     [rbp+NumberOfCharsRead], edi
0x18001f048  mov     ebx, r8d
0x18001f04b  mov     [rbp+Buffer], dil
0x18001f04f  mov     r10, rdx
0x18001f052  mov     [rbp+arg_18], di
0x18001f056  cmp     r9d, 0FFFFFFFEh
0x18001f05a  jnz     short loc_18001F073
0x18001f05c  call    __doserrno
0x18001f061  mov     [rax], edi
0x18001f063  call    _errno
0x18001f068  mov     dword ptr [rax], 9
0x18001f06e  jmp     loc_18001F933
0x18001f073  test    ecx, ecx
0x18001f075  js      loc_18001F90D
0x18001f07b  cmp     r9d, cs:_nhandle
0x18001f082  jnb     loc_18001F90D
0x18001f088  mov     eax, r9d
0x18001f08b  lea     r11, __ImageBase
0x18001f092  and     eax, 1Fh
0x18001f095  mov     r12, r9
0x18001f098  imul    rcx, rax, 38h ; '8'
0x18001f09c  shr     r12, 5
0x18001f0a0  mov     rdx, r9
0x18001f0a3  mov     [rbp+var_10], rdx
0x18001f0a7  mov     [rbp+var_18], rcx
0x18001f0ab  mov     r13, rva __pioinfo[r11+r12*8]
0x18001f0b3  mov     r15b, [rcx+r13+8]
0x18001f0b8  test    r15b, 1
0x18001f0bc  jz      loc_18001F90D
0x18001f0c2  cmp     ebx, 7FFFFFFFh
0x18001f0c8  jbe     short loc_18001F0E1
0x18001f0ca  call    __doserrno
0x18001f0cf  mov     [rax], edi
0x18001f0d1  call    _errno
0x18001f0d6  mov     dword ptr [rax], 16h
0x18001f0dc  jmp     loc_18001F91F
0x18001f0e1  test    ebx, ebx
0x18001f0e3  jz      loc_18001F909
0x18001f0e9  test    r15b, 2
0x18001f0ed  jnz     loc_18001F909
0x18001f0f3  test    r10, r10
0x18001f0f6  jz      short loc_18001F0CA
0x18001f0f8  mov     r8d, [rcx+r13+0Ch]
0x18001f0fd  mov     esi, 4
0x18001f102  and     r8d, 3
0x18001f106  mov     [rbp+var_1C], ebx
0x18001f109  mov     eax, r8d
0x18001f10c  mov     [rbp+var_24], r8d
0x18001f110  sub     eax, 1
0x18001f113  jz      short loc_18001F126
0x18001f115  cmp     eax, 1
0x18001f118  jnz     short loc_18001F121
0x18001f11a  test    al, bl
0x18001f11c  jnz     short loc_18001F0CA
0x18001f11e  and     ebx, 0FFFFFFFEh
0x18001f121  mov     rsi, r10
0x18001f124  jmp     short loc_18001F173
0x18001f126  test    bl, 1
0x18001f129  jnz     short loc_18001F0CA
0x18001f12b  shr     ebx, 1
0x18001f12d  cmp     ebx, esi
0x18001f12f  cmovb   ebx, esi
0x18001f132  mov     ecx, ebx; Size
0x18001f134  call    malloc
0x18001f139  mov     rsi, rax
0x18001f13c  test    rax, rax
0x18001f13f  jnz     short loc_18001F15C
0x18001f141  call    _errno
0x18001f146  mov     dword ptr [rax], 0Ch
0x18001f14c  call    __doserrno
0x18001f151  mov     dword ptr [rax], 8
0x18001f157  jmp     loc_18001F933
0x18001f15c  mov     rcx, [rbp+var_18]
0x18001f160  lea     r11, __ImageBase
0x18001f167  mov     r8d, [rbp+var_24]
0x18001f16b  mov     r9d, [rbp+arg_0]
0x18001f16f  mov     rdx, [rbp+var_10]
0x18001f173  mov     [rbp+Mode], edi
0x18001f176  mov     r14, rsi
0x18001f179  mov     r10d, 0Ah
0x18001f17f  test    r15b, 48h
0x18001f183  jz      loc_18001F236
0x18001f189  mov     al, [rcx+r13+9]
0x18001f18e  cmp     al, r10b
0x18001f191  jz      loc_18001F236
0x18001f197  mov     r13, [rbp+var_18]
0x18001f19b  test    ebx, ebx
0x18001f19d  jz      loc_18001F23A
0x18001f1a3  mov     [rsi], al
0x18001f1a5  lea     r14, [rsi+1]
0x18001f1a9  mov     rax, rva __pioinfo[r11+r12*8]
0x18001f1b1  lea     edi, [r10-9]
0x18001f1b5  or      r15d, 0FFFFFFFFh
0x18001f1b9  add     ebx, r15d
0x18001f1bc  mov     [rax+r13+9], r10b
0x18001f1c1  test    r8d, r8d
0x18001f1c4  jz      short loc_18001F23A
0x18001f1c6  mov     rax, rdx
0x18001f1c9  and     eax, 1Fh
0x18001f1cc  imul    rcx, rax, 38h ; '8'
0x18001f1d0  mov     rax, rva __pioinfo[r11+r12*8]
0x18001f1d8  mov     dl, [rcx+rax+0Ah]
0x18001f1dc  cmp     dl, r10b
0x18001f1df  jz      short loc_18001F23A
0x18001f1e1  test    ebx, ebx
0x18001f1e3  jz      short loc_18001F23A
0x18001f1e5  mov     [r14], dl
0x18001f1e8  lea     edi, [r10-8]
0x18001f1ec  mov     rax, rva __pioinfo[r11+r12*8]
0x18001f1f4  inc     r14
0x18001f1f7  add     ebx, r15d
0x18001f1fa  mov     [rcx+rax+0Ah], r10b
0x18001f1ff  cmp     r8d, 1
0x18001f203  jnz     short loc_18001F23A
0x18001f205  mov     rax, rva __pioinfo[r11+r12*8]
0x18001f20d  mov     dl, [rcx+rax+0Bh]
0x18001f211  cmp     dl, r10b
0x18001f214  jz      short loc_18001F23A
0x18001f216  test    ebx, ebx
0x18001f218  jz      short loc_18001F23A
0x18001f21a  mov     [r14], dl
0x18001f21d  lea     edi, [r10-7]
0x18001f221  mov     rax, rva __pioinfo[r11+r12*8]
0x18001f229  inc     r14
0x18001f22c  add     ebx, r15d
0x18001f22f  mov     [rcx+rax+0Bh], r10b
0x18001f234  jmp     short loc_18001F23A
0x18001f236  mov     r13, [rbp+var_18]
0x18001f23a  mov     ecx, r9d; FileHandle
0x18001f23d  call    _isatty
0x18001f242  test    eax, eax
0x18001f244  jz      loc_18001F2D5
0x18001f24a  lea     rcx, __ImageBase
0x18001f251  mov     rcx, rva __pioinfo[rcx+r12*8]
0x18001f259  cmp     byte ptr [rcx+r13+8], 0
0x18001f25f  jge     short loc_18001F2D5
0x18001f261  mov     [rbp+Mode], 0
0x18001f268  lea     rdx, [rbp+Mode]; lpMode
0x18001f26c  mov     rcx, [rcx+r13]; hConsoleHandle
0x18001f270  call    cs:__imp_GetConsoleMode
0x18001f276  mov     r15d, eax
0x18001f279  test    eax, eax
0x18001f27b  jz      short loc_18001F2D9
0x18001f27d  cmp     [rbp+var_24], 2
0x18001f281  jnz     short loc_18001F2D9
0x18001f283  lea     rax, __ImageBase
0x18001f28a  shr     ebx, 1
0x18001f28c  mov     rcx, rva __pioinfo[rax+r12*8]
0x18001f294  lea     r9, [rbp+NumberOfCharsRead]; lpNumberOfCharsRead
0x18001f298  mov     r8d, ebx; nNumberOfCharsToRead
0x18001f29b  mov     [rsp+58h+pInputControl], 0; pInputControl
0x18001f2a4  mov     rdx, r14; lpBuffer
0x18001f2a7  mov     rcx, [rcx+r13]; hConsoleInput
0x18001f2ab  call    cs:__imp_ReadConsoleW
0x18001f2b1  test    eax, eax
0x18001f2b3  jnz     short loc_18001F2CA
0x18001f2b5  call    cs:__imp_GetLastError
0x18001f2bb  mov     ecx, eax
0x18001f2bd  call    _dosmaperr
0x18001f2c2  or      ebx, 0FFFFFFFFh
0x18001f2c5  jmp     loc_18001F8BB
0x18001f2ca  mov     eax, [rbp+NumberOfCharsRead]
0x18001f2cd  lea     edx, [rax+rax]
0x18001f2d0  mov     [rbp+NumberOfCharsRead], edx
0x18001f2d3  jmp     short loc_18001F324
0x18001f2d5  mov     r15d, [rbp+Mode]
0x18001f2d9  lea     rcx, __ImageBase
0x18001f2e0  mov     [rsp+58h+pInputControl], 0; lpOverlapped
0x18001f2e9  mov     rcx, rva __pioinfo[rcx+r12*8]
0x18001f2f1  lea     r9, [rbp+NumberOfCharsRead]; lpNumberOfBytesRead
0x18001f2f5  mov     r8d, ebx; nNumberOfBytesToRead
0x18001f2f8  mov     rdx, r14; lpBuffer
0x18001f2fb  mov     rcx, [rcx+r13]; hFile
0x18001f2ff  call    cs:__imp_ReadFile
0x18001f305  test    eax, eax
0x18001f307  jz      loc_18001F8D6
0x18001f30d  movsxd  rdx, [rbp+NumberOfCharsRead]
0x18001f311  test    edx, edx
0x18001f313  js      loc_18001F8D6
0x18001f319  mov     eax, ebx
0x18001f31b  cmp     rdx, rax
0x18001f31e  ja      loc_18001F8D6
0x18001f324  lea     r11, __ImageBase
0x18001f32b  add     edi, edx
0x18001f32d  mov     r8, rva __pioinfo[r11+r12*8]
0x18001f335  mov     ebx, 0FFFFFFFEh
0x18001f33a  add     r8, r13
0x18001f33d  mov     [rbp+Mode], ebx
0x18001f340  mov     al, [r8+8]
0x18001f344  test    al, al
0x18001f346  jns     loc_18001F8BB
0x18001f34c  cmp     [rbp+var_24], 2
0x18001f350  jz      loc_18001F61F
0x18001f356  lea     r9d, [rbx+0Ch]
0x18001f35a  test    edx, edx
0x18001f35c  jz      short loc_18001F367
0x18001f35e  cmp     [rsi], r9b
0x18001f361  jnz     short loc_18001F367
0x18001f363  or      al, 4
0x18001f365  jmp     short loc_18001F369
0x18001f367  and     al, 0FBh
0x18001f369  movsxd  rdi, edi
0x18001f36c  mov     rbx, rsi
0x18001f36f  add     rdi, rsi
0x18001f372  mov     [r8+8], al
0x18001f376  mov     r14, rsi
0x18001f379  cmp     rsi, rdi
0x18001f37c  jnb     loc_18001F4D1
0x18001f382  mov     edx, 1Ah
0x18001f387  lea     r15d, [rdx-0Dh]
0x18001f38b  mov     al, [r14]
0x18001f38e  cmp     al, dl
0x18001f390  jz      loc_18001F4B2
0x18001f396  cmp     al, r15b
0x18001f399  jz      short loc_18001F3A8
0x18001f39b  mov     [rbx], al
0x18001f39d  inc     rbx
0x18001f3a0  inc     r14
0x18001f3a3  jmp     loc_18001F4A7
0x18001f3a8  lea     rax, [rdi-1]
0x18001f3ac  cmp     r14, rax
0x18001f3af  jnb     short loc_18001F3CE
0x18001f3b1  cmp     [r14+1], r9b
0x18001f3b5  jnz     short loc_18001F3C0
0x18001f3b7  add     r14, 2
0x18001f3bb  mov     [rbx], r9b
0x18001f3be  jmp     short loc_18001F3C6
0x18001f3c0  mov     [rbx], r15b
0x18001f3c3  inc     r14
0x18001f3c6  inc     rbx
0x18001f3c9  jmp     loc_18001F4A7
0x18001f3ce  mov     rcx, rva __pioinfo[r11+r12*8]
0x18001f3d6  lea     r9, [rbp+NumberOfCharsRead]; lpNumberOfBytesRead
0x18001f3da  mov     r8d, 1; nNumberOfBytesToRead
0x18001f3e0  mov     [rsp+58h+pInputControl], 0; lpOverlapped
0x18001f3e9  lea     rdx, [rbp+Buffer]; lpBuffer
0x18001f3ed  inc     r14
0x18001f3f0  mov     rcx, [rcx+r13]; hFile
0x18001f3f4  call    cs:__imp_ReadFile
0x18001f3fa  test    eax, eax
0x18001f3fc  jnz     short loc_18001F40C
0x18001f3fe  call    cs:__imp_GetLastError
0x18001f404  test    eax, eax
0x18001f406  jnz     loc_18001F48F
0x18001f40c  cmp     [rbp+NumberOfCharsRead], 0
0x18001f410  jz      short loc_18001F48F
0x18001f412  lea     r11, __ImageBase
0x18001f419  mov     rax, rva __pioinfo[r11+r12*8]
0x18001f421  test    byte ptr [rax+r13+8], 48h
0x18001f427  jz      short loc_18001F452
0x18001f429  mov     r9d, 0Ah
0x18001f42f  cmp     [rbp+Buffer], r9b
0x18001f433  jnz     short loc_18001F43A
0x18001f435  mov     [rbx], r9b
0x18001f438  jmp     short loc_18001F44D
0x18001f43a  mov     [rbx], r15b
0x18001f43d  mov     rcx, rva __pioinfo[r11+r12*8]
0x18001f445  mov     al, [rbp+Buffer]
0x18001f448  mov     [rcx+r13+9], al
0x18001f44d  inc     rbx
0x18001f450  jmp     short loc_18001F4A2
0x18001f452  cmp     rbx, rsi
0x18001f455  jnz     short loc_18001F468
0x18001f457  mov     r9d, 0Ah
0x18001f45d  cmp     [rbp+Buffer], r9b
0x18001f461  jnz     short loc_18001F468
0x18001f463  mov     [rbx], r9b
0x18001f466  jmp     short loc_18001F49F
0x18001f468  mov     ecx, [rbp+arg_0]
0x18001f46b  mov     r8d, 1
0x18001f471  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001f475  call    _lseeki64_nolock
0x18001f47a  mov     r9d, 0Ah
0x18001f480  lea     r11, __ImageBase
0x18001f487  cmp     [rbp+Buffer], r9b
0x18001f48b  jz      short loc_18001F4A2
0x18001f48d  jmp     short loc_18001F49C
0x18001f48f  mov     r9d, 0Ah
0x18001f495  lea     r11, __ImageBase
0x18001f49c  mov     [rbx], r15b
0x18001f49f  inc     rbx
0x18001f4a2  mov     edx, 1Ah
0x18001f4a7  cmp     r14, rdi
0x18001f4aa  jb      loc_18001F38B
0x18001f4b0  jmp     short loc_18001F4D1
0x18001f4b2  mov     rcx, rva __pioinfo[r11+r12*8]
  ... truncated ...
```
