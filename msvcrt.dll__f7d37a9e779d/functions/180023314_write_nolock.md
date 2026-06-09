# _write_nolock

- ea: `0x180023314`
- end: `0x180023a70`
- name: `_write_nolock`
- size: `1884`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x18001df6c`
- `0x180023210`
- `0x180031450`
- `0x180032c30`

## callees

- `0x1800034e0`
- `0x180003f70`
- `0x180007e80`
- `0x180007ea8`
- `0x180007f00`
- `0x18001e648`
- `0x180020500`
- `0x1800209f8`
- `0x180023314`
- `0x18002f050`
- `0x18003e048`
- `0x180079760`
- `0x180079910`

## import_xrefs

- `api-ms-win-core-console-l1-1-0!GetConsoleMode` at `0x180023435`
- `api-ms-win-core-console-l1-1-0!GetConsoleMode` at `0x180023435`
- `api-ms-win-core-console-l1-1-0!GetConsoleCP` at `0x180023451`
- `api-ms-win-core-console-l1-1-0!GetConsoleCP` at `0x180023451`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002364c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023656`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002397f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800239d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002364c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023656`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002397f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800239d6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180023546`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800235a5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180023727`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002381e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180023969`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800239c1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180023546`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800235a5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180023727`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002381e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180023969`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800239c1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002350a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002391b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002350a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002391b`

## pseudocode

```c
__int64 __fastcall write_nolock(int a1, const char *a2, unsigned int a3)
{
  DWORD v3; // ebx
  __int64 v4; // r15
  __int64 v8; // r13
  __int64 v9; // r14
  __int64 v10; // rcx
  int v11; // esi
  bool v12; // zf
  int v13; // edi
  DWORD LastError; // edi
  const char *v15; // r14
  int v16; // ecx
  DWORD v17; // eax
  signed int v18; // r13d
  BOOL v19; // r13d
  __int64 v20; // rcx
  const char *v21; // r14
  int v22; // r13d
  _BYTE *v23; // rsi
  char v24; // al
  const char *v25; // r14
  CHAR *v26; // rsi
  __int16 v27; // cx
  WCHAR *v28; // rsi
  WCHAR *v29; // rcx
  WCHAR v30; // dx
  int v31; // esp
  int v32; // kr00_4
  int v33; // r13d
  int v34; // r14d
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Mode; // [rsp+44h] [rbp-BCh] BYREF
  int v37; // [rsp+48h] [rbp-B8h]
  __int64 v38; // [rsp+50h] [rbp-B0h]
  __int64 v39; // [rsp+58h] [rbp-A8h]
  UINT CodePage; // [rsp+60h] [rbp-A0h]
  int v41; // [rsp+64h] [rbp-9Ch]
  CHAR MultiByteStr[8]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR WideCharStr[72]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v44[1568]; // [rsp+100h] [rbp+0h] BYREF
  CHAR v45[5120]; // [rsp+720h] [rbp+620h] BYREF
  CHAR v46[3424]; // [rsp+1B20h] [rbp+1A20h] BYREF
  _BYTE Buffer[5120]; // [rsp+2880h] [rbp+2780h] BYREF

  v3 = 0;
  v4 = a3;
  NumberOfBytesWritten = 0;
  if ( a3 )
  {
    if ( !a2
      || (v8 = 56LL * (a1 & 0x1F),
          v9 = (__int64)a1 >> 5,
          v39 = v9,
          v38 = v8,
          v10 = _pioinfo[v9],
          v11 = *(_DWORD *)(v10 + v8 + 12) & 3,
          (unsigned int)(v11 - 1) <= 1)
      && (a3 & 1) != 0 )
    {
      *_doserrno() = 0;
      *errno() = 22;
      invalid_parameter(0, 0, 0, 0, 0);
    }
    v12 = (*(_BYTE *)(v10 + v8 + 8) & 0x20) == 0;
    v37 = 0;
    if ( !v12 )
      lseeki64_nolock((unsigned int)a1, 0, 2);
    if ( isatty(a1) )
    {
      if ( *(char *)(_pioinfo[v9] + v8 + 8) < 0 )
      {
        Mode = 0;
        v13 = *(_DWORD *)(*(_QWORD *)(getptd() + 192) + 20LL);
        if ( GetConsoleMode(*(HANDLE *)(_pioinfo[v9] + v8), &Mode) )
        {
          if ( v13 || v11 )
          {
            LastError = 0;
            CodePage = GetConsoleCP();
            LOWORD(Mode) = 0;
            v15 = a2;
            if ( (_DWORD)v4 )
            {
              while ( 1 )
              {
                if ( v11 )
                {
                  if ( v11 == 1 || (v19 = 0, v11 == 2) )
                  {
                    LOWORD(Mode) = *(_WORD *)v15;
                    v19 = (_WORD)Mode == 10;
                    v15 += 2;
                  }
                  if ( (unsigned int)(v11 - 1) <= 1 )
                  {
                    if ( putwch_nolock(Mode) != (_WORD)Mode )
                      goto LABEL_41;
                    v3 += 2;
                    if ( v19 )
                    {
                      LOWORD(Mode) = 13;
                      if ( putwch_nolock(0xDu) != 13 )
                        goto LABEL_41;
                      ++v3;
                      ++v37;
                    }
                  }
                  v8 = v38;
                }
                else
                {
                  v16 = *v15;
                  v41 = v16;
                  if ( isleadbyte(v16) )
                  {
                    if ( (__int64)&a2[v4 - (_QWORD)v15] <= 1 || mbtowc((wchar_t *)&Mode, v15, 2u) == -1 )
                      goto LABEL_43;
                    ++v15;
                  }
                  else if ( mbtowc((wchar_t *)&Mode, v15, 1u) == -1 )
                  {
                    goto LABEL_43;
                  }
                  ++v15;
                  v17 = WideCharToMultiByte(CodePage, 0, (LPCWCH)&Mode, 1, MultiByteStr, 5, 0, 0);
                  v18 = v17;
                  if ( !v17 )
                    goto LABEL_42;
                  if ( !WriteFile(*(HANDLE *)(_pioinfo[v39] + v38), MultiByteStr, v17, &NumberOfBytesWritten, 0) )
                    goto LABEL_41;
                  v3 += NumberOfBytesWritten;
                  if ( (int)NumberOfBytesWritten < v18 )
                    goto LABEL_42;
                  v8 = v38;
                  if ( v41 == 10 )
                  {
                    MultiByteStr[0] = 13;
                    if ( !WriteFile(*(HANDLE *)(_pioinfo[v39] + v38), MultiByteStr, 1u, &NumberOfBytesWritten, 0) )
                      goto LABEL_40;
                    if ( (int)NumberOfBytesWritten < 1 )
                      goto LABEL_43;
                    ++v37;
                    ++v3;
                  }
                }
                if ( (int)v15 - (int)a2 >= (unsigned int)v4 )
                  goto LABEL_43;
              }
            }
LABEL_96:
            if ( (*(_BYTE *)(_pioinfo[v39] + v8 + 8) & 0x40) == 0 || *a2 != 26 )
            {
              *errno() = 28;
              *_doserrno() = 0;
              return 0xFFFFFFFFLL;
            }
            return 0;
          }
        }
      }
    }
    v20 = _pioinfo[v9];
    if ( *(char *)(v20 + v8 + 8) >= 0 )
    {
      if ( !WriteFile(*(HANDLE *)(v20 + v8), a2, v4, &NumberOfBytesWritten, 0) )
      {
        LastError = GetLastError();
LABEL_92:
        if ( LastError )
        {
          if ( LastError == 5 )
          {
            *errno() = 9;
            *_doserrno() = 5;
          }
          else
          {
            dosmaperr(LastError);
          }
          return 0xFFFFFFFFLL;
        }
        goto LABEL_96;
      }
      v3 = NumberOfBytesWritten;
      LastError = 0;
    }
    else
    {
      LastError = 0;
      if ( v11 )
      {
        if ( v11 != 2 )
        {
          v28 = (WCHAR *)a2;
          if ( !(_DWORD)v4 )
            goto LABEL_96;
          while ( 1 )
          {
            v29 = WideCharStr;
            while ( (int)v28 - (int)a2 < (unsigned int)v4 )
            {
              v30 = *v28++;
              if ( v30 == 10 )
              {
                if ( (unsigned __int64)((char *)v29 - (char *)WideCharStr) > 0x6A6 )
                {
                  --v28;
                  break;
                }
                *v29++ = 13;
              }
              *v29++ = v30;
              if ( (unsigned __int64)((char *)v29 - (char *)WideCharStr) >= 0x6A8 )
                break;
            }
            v32 = (_DWORD)v29 - (v31 + 112);
            v33 = WideCharToMultiByte(0xFDE9u, 0, WideCharStr, v32 / 2, v46, 3413, 0, 0);
            if ( !v33 )
              break;
            v34 = 0;
            while ( WriteFile(*(HANDLE *)(_pioinfo[v39] + v38), &v46[v34], v33 - v34, &NumberOfBytesWritten, 0) )
            {
              v34 += NumberOfBytesWritten;
              if ( v33 <= v34 )
                goto LABEL_87;
            }
            LastError = GetLastError();
            if ( v33 > v34 )
              goto LABEL_42;
LABEL_87:
            v3 = (_DWORD)v28 - (_DWORD)a2;
            if ( (int)v28 - (int)a2 >= (unsigned int)v4 )
              goto LABEL_42;
          }
LABEL_41:
          LastError = GetLastError();
LABEL_42:
          v8 = v38;
          goto LABEL_43;
        }
        v25 = a2;
        if ( !(_DWORD)v4 )
          goto LABEL_96;
        while ( 1 )
        {
          v26 = v45;
          while ( (int)v25 - (int)a2 < (unsigned int)v4 )
          {
            v27 = *(_WORD *)v25;
            v25 += 2;
            if ( v27 == 10 )
            {
              if ( (unsigned __int64)(v26 - v45) > 0x13FC )
              {
                v25 -= 2;
                break;
              }
              v37 += 2;
              *(_WORD *)v26 = 13;
              v26 += 2;
            }
            *(_WORD *)v26 = v27;
            v26 += 2;
            if ( (unsigned __int64)(v26 - v45) >= 0x13FE )
              break;
          }
          if ( !WriteFile(
                  *(HANDLE *)(_pioinfo[v39] + v8),
                  v45,
                  (_DWORD)v26 - ((unsigned int)v44 + 1568),
                  &NumberOfBytesWritten,
                  0) )
            break;
          v3 += NumberOfBytesWritten;
          if ( (int)NumberOfBytesWritten < v26 - v45 || !NumberOfBytesWritten || (int)v25 - (int)a2 >= (unsigned int)v4 )
            goto LABEL_43;
        }
      }
      else
      {
        v21 = a2;
        if ( !(_DWORD)v4 )
          goto LABEL_96;
        while ( 1 )
        {
          v22 = v37;
          v23 = Buffer;
          do
          {
            if ( (int)v21 - (int)a2 >= (unsigned int)v4 )
              break;
            v24 = *v21++;
            if ( v24 == 10 )
            {
              ++v22;
              *v23++ = 13;
            }
            *v23++ = v24;
          }
          while ( (unsigned __int64)(v23 - Buffer) < 0x13FF );
          v37 = v22;
          v8 = v38;
          if ( !WriteFile(
                  *(HANDLE *)(_pioinfo[v39] + v38),
                  Buffer,
                  (_DWORD)v23 - ((unsigned int)v44 + 10112),
                  &NumberOfBytesWritten,
                  0) )
            break;
          v3 += NumberOfBytesWritten;
          if ( (int)NumberOfBytesWritten < v23 - Buffer || (int)v21 - (int)a2 >= (unsigned int)v4 )
            goto LABEL_43;
        }
      }
LABEL_40:
      LastError = GetLastError();
    }
LABEL_43:
    if ( v3 )
      return v3 - v37;
    goto LABEL_92;
  }
  return 0;
}

```

## disassembly

```asm
0x180023314  mov     [rsp-8+arg_18], rbx
0x180023319  push    rbp
0x18002331a  push    rsi
0x18002331b  push    rdi
0x18002331c  push    r12
0x18002331e  push    r13
0x180023320  push    r14
0x180023322  push    r15
0x180023324  lea     rbp, [rsp-3B90h]
0x18002332c  mov     eax, 3C90h
0x180023331  call    _alloca_probe
0x180023336  sub     rsp, rax
0x180023339  mov     rax, cs:__security_cookie
0x180023340  xor     rax, rsp
0x180023343  mov     [rbp+3BC0h+var_40], rax
0x18002334a  xor     ebx, ebx
0x18002334c  mov     r15d, r8d
0x18002334f  movsxd  rdi, ecx
0x180023352  mov     r12, rdx
0x180023355  mov     [rsp+3CC0h+NumberOfBytesWritten], ebx
0x180023359  test    r8d, r8d
0x18002335c  jz      loc_180023A44
0x180023362  test    rdx, rdx
0x180023365  jnz     short loc_180023395
0x180023367  call    __doserrno
0x18002336c  mov     [rax], ebx
0x18002336e  call    _errno
0x180023373  xor     r9d, r9d; LineNo
0x180023376  mov     [rsp+3CC0h+Reserved], rbx; Reserved
0x18002337b  xor     r8d, r8d; FileName
0x18002337e  xor     edx, edx; FunctionName
0x180023380  xor     ecx, ecx; Expression
0x180023382  mov     dword ptr [rax], 16h
0x180023388  call    _invalid_parameter
0x18002338d  or      eax, 0FFFFFFFFh
0x180023390  jmp     loc_180023A46
0x180023395  mov     eax, edi
0x180023397  lea     rcx, __pioinfo
0x18002339e  and     eax, 1Fh
0x1800233a1  mov     r14, rdi
0x1800233a4  imul    r13, rax, 38h ; '8'
0x1800233a8  sar     r14, 5
0x1800233ac  mov     [rsp+3CC0h+var_3C68], r14
0x1800233b1  mov     [rsp+3CC0h+var_3C70], r13
0x1800233b6  mov     rcx, [rcx+r14*8]
0x1800233ba  mov     esi, [rcx+r13+0Ch]
0x1800233bf  and     esi, 3
0x1800233c2  lea     eax, [rsi-1]
0x1800233c5  cmp     eax, 1
0x1800233c8  ja      short loc_1800233D0
0x1800233ca  test    r15b, 1
0x1800233ce  jnz     short loc_180023367
0x1800233d0  test    byte ptr [rcx+r13+8], 20h
0x1800233d6  mov     [rsp+3CC0h+var_3C78], ebx
0x1800233da  jz      short loc_1800233E9
0x1800233dc  xor     edx, edx
0x1800233de  mov     ecx, edi
0x1800233e0  lea     r8d, [rdx+2]
0x1800233e4  call    _lseeki64_nolock
0x1800233e9  mov     ecx, edi; FileHandle
0x1800233eb  call    _isatty
0x1800233f0  test    eax, eax
0x1800233f2  jz      loc_180023676
0x1800233f8  lea     rax, __pioinfo
0x1800233ff  mov     rax, [rax+r14*8]
0x180023403  cmp     [rax+r13+8], bl
0x180023408  jge     loc_180023676
0x18002340e  mov     [rsp+3CC0h+Mode], ebx
0x180023412  call    _getptd
0x180023417  lea     rdx, [rsp+3CC0h+Mode]; lpMode
0x18002341c  mov     rcx, [rax+0C0h]
0x180023423  lea     rax, __pioinfo
0x18002342a  mov     edi, [rcx+14h]
0x18002342d  mov     rcx, [rax+r14*8]
0x180023431  mov     rcx, [rcx+r13]; hConsoleHandle
0x180023435  call    cs:__imp_GetConsoleMode
0x18002343b  test    eax, eax
0x18002343d  jz      loc_180023676
0x180023443  test    edi, edi
0x180023445  jnz     short loc_18002344F
0x180023447  test    esi, esi
0x180023449  jz      loc_180023676
0x18002344f  xor     edi, edi
0x180023451  call    cs:__imp_GetConsoleCP
0x180023457  xor     ecx, ecx
0x180023459  mov     [rsp+3CC0h+CodePage], eax
0x18002345d  mov     word ptr [rsp+3CC0h+Mode], cx
0x180023462  mov     r14, r12
0x180023465  test    r15d, r15d
0x180023468  jz      loc_180023A0A
0x18002346e  lea     ecx, [rdi+0Ah]
0x180023471  test    esi, esi
0x180023473  jnz     loc_1800235CB
0x180023479  movsx   eax, byte ptr [r14]
0x18002347d  mov     ecx, eax; C
0x18002347f  mov     [rsp+3CC0h+var_3C5C], eax
0x180023483  call    isleadbyte
0x180023488  test    eax, eax
0x18002348a  jnz     short loc_1800234A8
0x18002348c  lea     r8d, [rsi+1]; SrcSizeInBytes
0x180023490  mov     rdx, r14; SrcCh
0x180023493  lea     rcx, [rsp+3CC0h+Mode]; DstCh
0x180023498  call    mbtowc
0x18002349d  cmp     eax, 0FFFFFFFFh
0x1800234a0  jz      loc_180023663
0x1800234a6  jmp     short loc_1800234DA
0x1800234a8  mov     rax, r15
0x1800234ab  sub     rax, r14
0x1800234ae  add     rax, r12
0x1800234b1  cmp     rax, 1
0x1800234b5  jle     loc_180023663
0x1800234bb  mov     r8d, 2; SrcSizeInBytes
0x1800234c1  lea     rcx, [rsp+3CC0h+Mode]; DstCh
0x1800234c6  mov     rdx, r14; SrcCh
0x1800234c9  call    mbtowc
0x1800234ce  cmp     eax, 0FFFFFFFFh
0x1800234d1  jz      loc_180023663
0x1800234d7  inc     r14
0x1800234da  mov     ecx, [rsp+3CC0h+CodePage]; CodePage
0x1800234de  lea     rax, [rsp+3CC0h+MultiByteStr]
0x1800234e3  mov     [rsp+3CC0h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x1800234e8  lea     r8, [rsp+3CC0h+Mode]; lpWideCharStr
0x1800234ed  mov     [rsp+3CC0h+lpDefaultChar], rdi; lpDefaultChar
0x1800234f2  mov     r9d, 1; cchWideChar
0x1800234f8  mov     [rsp+3CC0h+cbMultiByte], 5; cbMultiByte
0x180023500  xor     edx, edx; dwFlags
0x180023502  mov     [rsp+3CC0h+Reserved], rax; lpMultiByteStr
0x180023507  inc     r14
0x18002350a  call    cs:__imp_WideCharToMultiByte
0x180023510  mov     r13d, eax
0x180023513  test    eax, eax
0x180023515  jz      loc_18002365E
0x18002351b  mov     rax, [rsp+3CC0h+var_3C68]
0x180023520  lea     rcx, __pioinfo
0x180023527  lea     r9, [rsp+3CC0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002352c  mov     [rsp+3CC0h+Reserved], rdi; lpOverlapped
0x180023531  mov     r8d, r13d; nNumberOfBytesToWrite
0x180023534  lea     rdx, [rsp+3CC0h+MultiByteStr]; lpBuffer
0x180023539  mov     rcx, [rcx+rax*8]
0x18002353d  mov     rax, [rsp+3CC0h+var_3C70]
0x180023542  mov     rcx, [rcx+rax]; hFile
0x180023546  call    cs:__imp_WriteFile
0x18002354c  test    eax, eax
0x18002354e  jz      loc_180023656
0x180023554  add     ebx, [rsp+3CC0h+NumberOfBytesWritten]
0x180023558  cmp     [rsp+3CC0h+NumberOfBytesWritten], r13d
0x18002355d  jl      loc_18002365E
0x180023563  mov     r13, [rsp+3CC0h+var_3C70]
0x180023568  mov     ecx, 0Ah
0x18002356d  cmp     [rsp+3CC0h+var_3C5C], ecx
0x180023571  jnz     loc_18002363B
0x180023577  mov     rax, [rsp+3CC0h+var_3C68]
0x18002357c  lea     rcx, __pioinfo
0x180023583  mov     [rsp+3CC0h+MultiByteStr], 0Dh
0x180023588  lea     r9, [rsp+3CC0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002358d  mov     r8d, 1; nNumberOfBytesToWrite
0x180023593  mov     [rsp+3CC0h+Reserved], rdi; lpOverlapped
0x180023598  lea     rdx, [rsp+3CC0h+MultiByteStr]; lpBuffer
0x18002359d  mov     rcx, [rcx+rax*8]
0x1800235a1  mov     rcx, [rcx+r13]; hFile
0x1800235a5  call    cs:__imp_WriteFile
0x1800235ab  test    eax, eax
0x1800235ad  jz      loc_18002364C
0x1800235b3  cmp     [rsp+3CC0h+NumberOfBytesWritten], 1
0x1800235b8  jl      loc_180023663
0x1800235be  inc     [rsp+3CC0h+var_3C78]
0x1800235c2  mov     ecx, 0Ah
0x1800235c7  inc     ebx
0x1800235c9  jmp     short loc_18002363B
0x1800235cb  cmp     esi, 1
0x1800235ce  jz      short loc_1800235D8
0x1800235d0  xor     r13d, r13d
0x1800235d3  cmp     esi, 2
0x1800235d6  jnz     short loc_1800235EF
0x1800235d8  movzx   eax, word ptr [r14]
0x1800235dc  xor     r13d, r13d
0x1800235df  cmp     ax, cx
0x1800235e2  mov     word ptr [rsp+3CC0h+Mode], ax
0x1800235e7  setz    r13b
0x1800235eb  add     r14, 2
0x1800235ef  lea     eax, [rsi-1]
0x1800235f2  cmp     eax, 1
0x1800235f5  ja      short loc_180023636
0x1800235f7  movzx   ecx, word ptr [rsp+3CC0h+Mode]; Character
0x1800235fc  call    _putwch_nolock
0x180023601  cmp     ax, word ptr [rsp+3CC0h+Mode]
0x180023606  jnz     short loc_180023656
0x180023608  add     ebx, 2
0x18002360b  test    r13d, r13d
0x18002360e  jz      short loc_180023631
0x180023610  mov     r13d, 0Dh
0x180023616  mov     ecx, r13d; Character
0x180023619  mov     word ptr [rsp+3CC0h+Mode], r13w
0x18002361f  call    _putwch_nolock
0x180023624  cmp     ax, word ptr [rsp+3CC0h+Mode]
0x180023629  jnz     short loc_180023656
0x18002362b  inc     ebx
0x18002362d  inc     [rsp+3CC0h+var_3C78]
0x180023631  mov     ecx, 0Ah
0x180023636  mov     r13, [rsp+3CC0h+var_3C70]
0x18002363b  mov     eax, r14d
0x18002363e  sub     eax, r12d
0x180023641  cmp     eax, r15d
0x180023644  jb      loc_180023471
0x18002364a  jmp     short loc_180023663
0x18002364c  call    cs:__imp_GetLastError
0x180023652  mov     edi, eax
0x180023654  jmp     short loc_180023663
0x180023656  call    cs:__imp_GetLastError
0x18002365c  mov     edi, eax
0x18002365e  mov     r13, [rsp+3CC0h+var_3C70]
0x180023663  test    ebx, ebx
0x180023665  jz      loc_1800239DE
0x18002366b  sub     ebx, [rsp+3CC0h+var_3C78]
0x18002366f  mov     eax, ebx
0x180023671  jmp     loc_180023A46
0x180023676  lea     rax, __pioinfo
0x18002367d  mov     rcx, [rax+r14*8]
0x180023681  cmp     [rcx+r13+8], bl
0x180023686  jge     loc_1800239AD
0x18002368c  xor     edi, edi
0x18002368e  test    esi, esi
0x180023690  jnz     loc_18002376D
0x180023696  mov     r14, r12
0x180023699  test    r15d, r15d
0x18002369c  jz      loc_180023A0A
0x1800236a2  lea     edx, [rdi+0Ah]
0x1800236a5  lea     ecx, [rdi+0Dh]
0x1800236a8  mov     r13d, [rsp+3CC0h+var_3C78]
0x1800236ad  lea     rsi, [rbp+3BC0h+Buffer]
0x1800236b4  mov     eax, r14d
0x1800236b7  sub     eax, r12d
0x1800236ba  cmp     eax, r15d
0x1800236bd  jnb     short loc_1800236EB
0x1800236bf  mov     al, [r14]
0x1800236c2  inc     r14
0x1800236c5  cmp     al, dl
0x1800236c7  jnz     short loc_1800236D1
0x1800236c9  inc     r13d
0x1800236cc  mov     [rsi], cl
0x1800236ce  inc     rsi
0x1800236d1  mov     [rsi], al
0x1800236d3  lea     r8, [rbp+3BC0h+Buffer]
0x1800236da  inc     rsi
0x1800236dd  mov     rax, rsi
0x1800236e0  sub     rax, r8
0x1800236e3  cmp     rax, 13FFh
0x1800236e9  jb      short loc_1800236B4
0x1800236eb  lea     rax, [rbp+3BC0h+Buffer]
0x1800236f2  mov     [rsp+3CC0h+var_3C78], r13d
0x1800236f7  mov     r13, [rsp+3CC0h+var_3C70]
0x1800236fc  lea     rcx, __pioinfo
0x180023703  mov     r8d, esi
0x180023706  mov     [rsp+3CC0h+Reserved], rdi; lpOverlapped
0x18002370b  sub     r8d, eax; nNumberOfBytesToWrite
0x18002370e  lea     r9, [rsp+3CC0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180023713  mov     rax, [rsp+3CC0h+var_3C68]
0x180023718  lea     rdx, [rbp+3BC0h+Buffer]; lpBuffer
0x18002371f  mov     rcx, [rcx+rax*8]
0x180023723  mov     rcx, [rcx+r13]; hFile
0x180023727  call    cs:__imp_WriteFile
0x18002372d  test    eax, eax
0x18002372f  jz      loc_18002364C
0x180023735  add     ebx, [rsp+3CC0h+NumberOfBytesWritten]
0x180023739  lea     rax, [rbp+3BC0h+Buffer]
0x180023740  sub     rsi, rax
0x180023743  movsxd  rax, [rsp+3CC0h+NumberOfBytesWritten]
0x180023748  cmp     rax, rsi
0x18002374b  jl      loc_180023663
0x180023751  mov     eax, r14d
0x180023754  mov     ecx, 0Dh
0x180023759  sub     eax, r12d
0x18002375c  lea     edx, [rcx-3]
0x18002375f  cmp     eax, r15d
0x180023762  jb      loc_1800236A8
0x180023768  jmp     loc_180023663
0x18002376d  cmp     esi, 2
0x180023770  jnz     loc_18002386B
0x180023776  mov     r14, r12
0x180023779  test    r15d, r15d
0x18002377c  jz      loc_180023A0A
0x180023782  lea     edx, [rsi+0Bh]
0x180023785  lea     r8d, [rsi+8]
0x180023789  lea     rsi, [rbp+3BC0h+var_35A0]
0x180023790  mov     eax, r14d
0x180023793  sub     eax, r12d
0x180023796  cmp     eax, r15d
0x180023799  jnb     short loc_1800237EC
0x18002379b  movzx   ecx, word ptr [r14]
0x18002379f  add     r14, 2
0x1800237a3  cmp     cx, r8w
0x1800237a7  jnz     short loc_1800237CA
0x1800237a9  lea     r9, [rbp+3BC0h+var_35A0]
0x1800237b0  mov     rax, rsi
0x1800237b3  sub     rax, r9
0x1800237b6  cmp     rax, 13FCh
0x1800237bc  ja      short loc_1800237E8
0x1800237be  add     [rsp+3CC0h+var_3C78], 2
0x1800237c3  mov     [rsi], dx
0x1800237c6  add     rsi, 2
  ... truncated ...
```
