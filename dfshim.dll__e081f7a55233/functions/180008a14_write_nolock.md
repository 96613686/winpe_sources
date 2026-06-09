# _write_nolock

- ea: `0x180008a14`
- end: `0x180009170`
- name: `_write_nolock`
- size: `1884`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x180008910`

## callees

- `0x180001cb8`
- `0x1800034dc`
- `0x180003504`
- `0x180003558`
- `0x1800035c8`
- `0x180006204`
- `0x180008888`
- `0x180008898`
- `0x180008a14`
- `0x180009280`
- `0x18000b5f8`
- `0x180127dc0`
- `0x180127e80`

## import_xrefs

- `KERNEL32!GetConsoleMode` at `0x180008b35`
- `KERNEL32!GetConsoleMode` at `0x180008b35`
- `KERNEL32!GetLastError` at `0x180008d4c`
- `KERNEL32!GetLastError` at `0x180008d56`
- `KERNEL32!GetLastError` at `0x18000907f`
- `KERNEL32!GetLastError` at `0x1800090d6`
- `KERNEL32!GetLastError` at `0x180008d4c`
- `KERNEL32!GetLastError` at `0x180008d56`
- `KERNEL32!GetLastError` at `0x18000907f`
- `KERNEL32!GetLastError` at `0x1800090d6`
- `KERNEL32!GetConsoleCP` at `0x180008b51`
- `KERNEL32!GetConsoleCP` at `0x180008b51`
- `KERNEL32!WideCharToMultiByte` at `0x180008c0a`
- `KERNEL32!WideCharToMultiByte` at `0x18000901b`
- `KERNEL32!WideCharToMultiByte` at `0x180008c0a`
- `KERNEL32!WideCharToMultiByte` at `0x18000901b`
- `KERNEL32!WriteFile` at `0x180008c46`
- `KERNEL32!WriteFile` at `0x180008ca5`
- `KERNEL32!WriteFile` at `0x180008e27`
- `KERNEL32!WriteFile` at `0x180008f1e`
- `KERNEL32!WriteFile` at `0x180009069`
- `KERNEL32!WriteFile` at `0x1800090c1`
- `KERNEL32!WriteFile` at `0x180008c46`
- `KERNEL32!WriteFile` at `0x180008ca5`
- `KERNEL32!WriteFile` at `0x180008e27`
- `KERNEL32!WriteFile` at `0x180008f1e`
- `KERNEL32!WriteFile` at `0x180009069`
- `KERNEL32!WriteFile` at `0x1800090c1`

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
0x180008a14  mov     [rsp-8+arg_18], rbx
0x180008a19  push    rbp
0x180008a1a  push    rsi
0x180008a1b  push    rdi
0x180008a1c  push    r12
0x180008a1e  push    r13
0x180008a20  push    r14
0x180008a22  push    r15
0x180008a24  lea     rbp, [rsp-3B90h]
0x180008a2c  mov     eax, 3C90h
0x180008a31  call    _alloca_probe
0x180008a36  sub     rsp, rax
0x180008a39  mov     rax, cs:__security_cookie
0x180008a40  xor     rax, rsp
0x180008a43  mov     [rbp+3BC0h+var_40], rax
0x180008a4a  xor     ebx, ebx
0x180008a4c  mov     r15d, r8d
0x180008a4f  movsxd  rdi, ecx
0x180008a52  mov     r12, rdx
0x180008a55  mov     [rsp+3CC0h+NumberOfBytesWritten], ebx
0x180008a59  test    r8d, r8d
0x180008a5c  jz      loc_180009144
0x180008a62  test    rdx, rdx
0x180008a65  jnz     short loc_180008A95
0x180008a67  call    __doserrno
0x180008a6c  mov     [rax], ebx
0x180008a6e  call    _errno
0x180008a73  xor     r9d, r9d; LineNo
0x180008a76  mov     [rsp+3CC0h+Reserved], rbx; Reserved
0x180008a7b  xor     r8d, r8d; FileName
0x180008a7e  xor     edx, edx; FunctionName
0x180008a80  xor     ecx, ecx; Expression
0x180008a82  mov     dword ptr [rax], 16h
0x180008a88  call    _invalid_parameter
0x180008a8d  or      eax, 0FFFFFFFFh
0x180008a90  jmp     loc_180009146
0x180008a95  mov     eax, edi
0x180008a97  lea     rcx, __pioinfo
0x180008a9e  and     eax, 1Fh
0x180008aa1  mov     r14, rdi
0x180008aa4  imul    r13, rax, 38h ; '8'
0x180008aa8  sar     r14, 5
0x180008aac  mov     [rsp+3CC0h+var_3C68], r14
0x180008ab1  mov     [rsp+3CC0h+var_3C70], r13
0x180008ab6  mov     rcx, [rcx+r14*8]
0x180008aba  mov     esi, [rcx+r13+0Ch]
0x180008abf  and     esi, 3
0x180008ac2  lea     eax, [rsi-1]
0x180008ac5  cmp     eax, 1
0x180008ac8  ja      short loc_180008AD0
0x180008aca  test    r15b, 1
0x180008ace  jnz     short loc_180008A67
0x180008ad0  test    byte ptr [rcx+r13+8], 20h
0x180008ad6  mov     [rsp+3CC0h+var_3C78], ebx
0x180008ada  jz      short loc_180008AE9
0x180008adc  xor     edx, edx
0x180008ade  mov     ecx, edi
0x180008ae0  lea     r8d, [rdx+2]
0x180008ae4  call    _lseeki64_nolock
0x180008ae9  mov     ecx, edi; FileHandle
0x180008aeb  call    _isatty
0x180008af0  test    eax, eax
0x180008af2  jz      loc_180008D76
0x180008af8  lea     rax, __pioinfo
0x180008aff  mov     rax, [rax+r14*8]
0x180008b03  cmp     [rax+r13+8], bl
0x180008b08  jge     loc_180008D76
0x180008b0e  mov     [rsp+3CC0h+Mode], ebx
0x180008b12  call    _getptd
0x180008b17  lea     rdx, [rsp+3CC0h+Mode]; lpMode
0x180008b1c  mov     rcx, [rax+0C0h]
0x180008b23  lea     rax, __pioinfo
0x180008b2a  mov     edi, [rcx+14h]
0x180008b2d  mov     rcx, [rax+r14*8]
0x180008b31  mov     rcx, [rcx+r13]; hConsoleHandle
0x180008b35  call    cs:__imp_GetConsoleMode
0x180008b3b  test    eax, eax
0x180008b3d  jz      loc_180008D76
0x180008b43  test    edi, edi
0x180008b45  jnz     short loc_180008B4F
0x180008b47  test    esi, esi
0x180008b49  jz      loc_180008D76
0x180008b4f  xor     edi, edi
0x180008b51  call    cs:__imp_GetConsoleCP
0x180008b57  xor     ecx, ecx
0x180008b59  mov     [rsp+3CC0h+CodePage], eax
0x180008b5d  mov     word ptr [rsp+3CC0h+Mode], cx
0x180008b62  mov     r14, r12
0x180008b65  test    r15d, r15d
0x180008b68  jz      loc_18000910A
0x180008b6e  lea     ecx, [rdi+0Ah]
0x180008b71  test    esi, esi
0x180008b73  jnz     loc_180008CCB
0x180008b79  movsx   eax, byte ptr [r14]
0x180008b7d  mov     ecx, eax; C
0x180008b7f  mov     [rsp+3CC0h+var_3C5C], eax
0x180008b83  call    isleadbyte
0x180008b88  test    eax, eax
0x180008b8a  jnz     short loc_180008BA8
0x180008b8c  lea     r8d, [rsi+1]; SrcSizeInBytes
0x180008b90  mov     rdx, r14; SrcCh
0x180008b93  lea     rcx, [rsp+3CC0h+Mode]; DstCh
0x180008b98  call    mbtowc
0x180008b9d  cmp     eax, 0FFFFFFFFh
0x180008ba0  jz      loc_180008D63
0x180008ba6  jmp     short loc_180008BDA
0x180008ba8  mov     rax, r15
0x180008bab  sub     rax, r14
0x180008bae  add     rax, r12
0x180008bb1  cmp     rax, 1
0x180008bb5  jle     loc_180008D63
0x180008bbb  mov     r8d, 2; SrcSizeInBytes
0x180008bc1  lea     rcx, [rsp+3CC0h+Mode]; DstCh
0x180008bc6  mov     rdx, r14; SrcCh
0x180008bc9  call    mbtowc
0x180008bce  cmp     eax, 0FFFFFFFFh
0x180008bd1  jz      loc_180008D63
0x180008bd7  inc     r14
0x180008bda  mov     ecx, [rsp+3CC0h+CodePage]; CodePage
0x180008bde  lea     rax, [rsp+3CC0h+MultiByteStr]
0x180008be3  mov     [rsp+3CC0h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x180008be8  lea     r8, [rsp+3CC0h+Mode]; lpWideCharStr
0x180008bed  mov     [rsp+3CC0h+lpDefaultChar], rdi; lpDefaultChar
0x180008bf2  mov     r9d, 1; cchWideChar
0x180008bf8  mov     [rsp+3CC0h+cbMultiByte], 5; cbMultiByte
0x180008c00  xor     edx, edx; dwFlags
0x180008c02  mov     [rsp+3CC0h+Reserved], rax; lpMultiByteStr
0x180008c07  inc     r14
0x180008c0a  call    cs:__imp_WideCharToMultiByte
0x180008c10  mov     r13d, eax
0x180008c13  test    eax, eax
0x180008c15  jz      loc_180008D5E
0x180008c1b  mov     rax, [rsp+3CC0h+var_3C68]
0x180008c20  lea     rcx, __pioinfo
0x180008c27  lea     r9, [rsp+3CC0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180008c2c  mov     [rsp+3CC0h+Reserved], rdi; lpOverlapped
0x180008c31  mov     r8d, r13d; nNumberOfBytesToWrite
0x180008c34  lea     rdx, [rsp+3CC0h+MultiByteStr]; lpBuffer
0x180008c39  mov     rcx, [rcx+rax*8]
0x180008c3d  mov     rax, [rsp+3CC0h+var_3C70]
0x180008c42  mov     rcx, [rcx+rax]; hFile
0x180008c46  call    cs:__imp_WriteFile
0x180008c4c  test    eax, eax
0x180008c4e  jz      loc_180008D56
0x180008c54  add     ebx, [rsp+3CC0h+NumberOfBytesWritten]
0x180008c58  cmp     [rsp+3CC0h+NumberOfBytesWritten], r13d
0x180008c5d  jl      loc_180008D5E
0x180008c63  mov     r13, [rsp+3CC0h+var_3C70]
0x180008c68  mov     ecx, 0Ah
0x180008c6d  cmp     [rsp+3CC0h+var_3C5C], ecx
0x180008c71  jnz     loc_180008D3B
0x180008c77  mov     rax, [rsp+3CC0h+var_3C68]
0x180008c7c  lea     rcx, __pioinfo
0x180008c83  mov     [rsp+3CC0h+MultiByteStr], 0Dh
0x180008c88  lea     r9, [rsp+3CC0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180008c8d  mov     r8d, 1; nNumberOfBytesToWrite
0x180008c93  mov     [rsp+3CC0h+Reserved], rdi; lpOverlapped
0x180008c98  lea     rdx, [rsp+3CC0h+MultiByteStr]; lpBuffer
0x180008c9d  mov     rcx, [rcx+rax*8]
0x180008ca1  mov     rcx, [rcx+r13]; hFile
0x180008ca5  call    cs:__imp_WriteFile
0x180008cab  test    eax, eax
0x180008cad  jz      loc_180008D4C
0x180008cb3  cmp     [rsp+3CC0h+NumberOfBytesWritten], 1
0x180008cb8  jl      loc_180008D63
0x180008cbe  inc     [rsp+3CC0h+var_3C78]
0x180008cc2  mov     ecx, 0Ah
0x180008cc7  inc     ebx
0x180008cc9  jmp     short loc_180008D3B
0x180008ccb  cmp     esi, 1
0x180008cce  jz      short loc_180008CD8
0x180008cd0  xor     r13d, r13d
0x180008cd3  cmp     esi, 2
0x180008cd6  jnz     short loc_180008CEF
0x180008cd8  movzx   eax, word ptr [r14]
0x180008cdc  xor     r13d, r13d
0x180008cdf  cmp     ax, cx
0x180008ce2  mov     word ptr [rsp+3CC0h+Mode], ax
0x180008ce7  setz    r13b
0x180008ceb  add     r14, 2
0x180008cef  lea     eax, [rsi-1]
0x180008cf2  cmp     eax, 1
0x180008cf5  ja      short loc_180008D36
0x180008cf7  movzx   ecx, word ptr [rsp+3CC0h+Mode]; Character
0x180008cfc  call    _putwch_nolock
0x180008d01  cmp     ax, word ptr [rsp+3CC0h+Mode]
0x180008d06  jnz     short loc_180008D56
0x180008d08  add     ebx, 2
0x180008d0b  test    r13d, r13d
0x180008d0e  jz      short loc_180008D31
0x180008d10  mov     r13d, 0Dh
0x180008d16  mov     ecx, r13d; Character
0x180008d19  mov     word ptr [rsp+3CC0h+Mode], r13w
0x180008d1f  call    _putwch_nolock
0x180008d24  cmp     ax, word ptr [rsp+3CC0h+Mode]
0x180008d29  jnz     short loc_180008D56
0x180008d2b  inc     ebx
0x180008d2d  inc     [rsp+3CC0h+var_3C78]
0x180008d31  mov     ecx, 0Ah
0x180008d36  mov     r13, [rsp+3CC0h+var_3C70]
0x180008d3b  mov     eax, r14d
0x180008d3e  sub     eax, r12d
0x180008d41  cmp     eax, r15d
0x180008d44  jb      loc_180008B71
0x180008d4a  jmp     short loc_180008D63
0x180008d4c  call    cs:__imp_GetLastError
0x180008d52  mov     edi, eax
0x180008d54  jmp     short loc_180008D63
0x180008d56  call    cs:__imp_GetLastError
0x180008d5c  mov     edi, eax
0x180008d5e  mov     r13, [rsp+3CC0h+var_3C70]
0x180008d63  test    ebx, ebx
0x180008d65  jz      loc_1800090DE
0x180008d6b  sub     ebx, [rsp+3CC0h+var_3C78]
0x180008d6f  mov     eax, ebx
0x180008d71  jmp     loc_180009146
0x180008d76  lea     rax, __pioinfo
0x180008d7d  mov     rcx, [rax+r14*8]
0x180008d81  cmp     [rcx+r13+8], bl
0x180008d86  jge     loc_1800090AD
0x180008d8c  xor     edi, edi
0x180008d8e  test    esi, esi
0x180008d90  jnz     loc_180008E6D
0x180008d96  mov     r14, r12
0x180008d99  test    r15d, r15d
0x180008d9c  jz      loc_18000910A
0x180008da2  lea     edx, [rdi+0Ah]
0x180008da5  lea     ecx, [rdi+0Dh]
0x180008da8  mov     r13d, [rsp+3CC0h+var_3C78]
0x180008dad  lea     rsi, [rbp+3BC0h+Buffer]
0x180008db4  mov     eax, r14d
0x180008db7  sub     eax, r12d
0x180008dba  cmp     eax, r15d
0x180008dbd  jnb     short loc_180008DEB
0x180008dbf  mov     al, [r14]
0x180008dc2  inc     r14
0x180008dc5  cmp     al, dl
0x180008dc7  jnz     short loc_180008DD1
0x180008dc9  inc     r13d
0x180008dcc  mov     [rsi], cl
0x180008dce  inc     rsi
0x180008dd1  mov     [rsi], al
0x180008dd3  lea     r8, [rbp+3BC0h+Buffer]
0x180008dda  inc     rsi
0x180008ddd  mov     rax, rsi
0x180008de0  sub     rax, r8
0x180008de3  cmp     rax, 13FFh
0x180008de9  jb      short loc_180008DB4
0x180008deb  lea     rax, [rbp+3BC0h+Buffer]
0x180008df2  mov     [rsp+3CC0h+var_3C78], r13d
0x180008df7  mov     r13, [rsp+3CC0h+var_3C70]
0x180008dfc  lea     rcx, __pioinfo
0x180008e03  mov     r8d, esi
0x180008e06  mov     [rsp+3CC0h+Reserved], rdi; lpOverlapped
0x180008e0b  sub     r8d, eax; nNumberOfBytesToWrite
0x180008e0e  lea     r9, [rsp+3CC0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180008e13  mov     rax, [rsp+3CC0h+var_3C68]
0x180008e18  lea     rdx, [rbp+3BC0h+Buffer]; lpBuffer
0x180008e1f  mov     rcx, [rcx+rax*8]
0x180008e23  mov     rcx, [rcx+r13]; hFile
0x180008e27  call    cs:__imp_WriteFile
0x180008e2d  test    eax, eax
0x180008e2f  jz      loc_180008D4C
0x180008e35  add     ebx, [rsp+3CC0h+NumberOfBytesWritten]
0x180008e39  lea     rax, [rbp+3BC0h+Buffer]
0x180008e40  sub     rsi, rax
0x180008e43  movsxd  rax, [rsp+3CC0h+NumberOfBytesWritten]
0x180008e48  cmp     rax, rsi
0x180008e4b  jl      loc_180008D63
0x180008e51  mov     eax, r14d
0x180008e54  mov     ecx, 0Dh
0x180008e59  sub     eax, r12d
0x180008e5c  lea     edx, [rcx-3]
0x180008e5f  cmp     eax, r15d
0x180008e62  jb      loc_180008DA8
0x180008e68  jmp     loc_180008D63
0x180008e6d  cmp     esi, 2
0x180008e70  jnz     loc_180008F6B
0x180008e76  mov     r14, r12
0x180008e79  test    r15d, r15d
0x180008e7c  jz      loc_18000910A
0x180008e82  lea     edx, [rsi+0Bh]
0x180008e85  lea     r8d, [rsi+8]
0x180008e89  lea     rsi, [rbp+3BC0h+var_35A0]
0x180008e90  mov     eax, r14d
0x180008e93  sub     eax, r12d
0x180008e96  cmp     eax, r15d
0x180008e99  jnb     short loc_180008EEC
0x180008e9b  movzx   ecx, word ptr [r14]
0x180008e9f  add     r14, 2
0x180008ea3  cmp     cx, r8w
0x180008ea7  jnz     short loc_180008ECA
0x180008ea9  lea     r9, [rbp+3BC0h+var_35A0]
0x180008eb0  mov     rax, rsi
0x180008eb3  sub     rax, r9
0x180008eb6  cmp     rax, 13FCh
0x180008ebc  ja      short loc_180008EE8
0x180008ebe  add     [rsp+3CC0h+var_3C78], 2
0x180008ec3  mov     [rsi], dx
0x180008ec6  add     rsi, 2
  ... truncated ...
```
