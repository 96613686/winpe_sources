# _write_nolock

- ea: `0x18001b808`
- end: `0x18001bf64`
- name: `_write_nolock`
- size: `1884`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x18001b704`

## callees

- `0x18000e0bc`
- `0x18000e448`
- `0x18000e470`
- `0x18000e4c4`
- `0x18000f878`
- `0x180010a08`
- `0x18001b3b8`
- `0x18001b68c`
- `0x18001b808`
- `0x18001c074`
- `0x18001ec28`
- `0x180041ac0`
- `0x180041b20`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x18001b9fe`
- `KERNEL32!WideCharToMultiByte` at `0x18001be0f`
- `KERNEL32!WideCharToMultiByte` at `0x18001b9fe`
- `KERNEL32!WideCharToMultiByte` at `0x18001be0f`
- `KERNEL32!GetLastError` at `0x18001bb40`
- `KERNEL32!GetLastError` at `0x18001bb4a`
- `KERNEL32!GetLastError` at `0x18001be73`
- `KERNEL32!GetLastError` at `0x18001beca`
- `KERNEL32!GetLastError` at `0x18001bb40`
- `KERNEL32!GetLastError` at `0x18001bb4a`
- `KERNEL32!GetLastError` at `0x18001be73`
- `KERNEL32!GetLastError` at `0x18001beca`
- `KERNEL32!WriteFile` at `0x18001ba3a`
- `KERNEL32!WriteFile` at `0x18001ba99`
- `KERNEL32!WriteFile` at `0x18001bc1b`
- `KERNEL32!WriteFile` at `0x18001bd12`
- `KERNEL32!WriteFile` at `0x18001be5d`
- `KERNEL32!WriteFile` at `0x18001beb5`
- `KERNEL32!WriteFile` at `0x18001ba3a`
- `KERNEL32!WriteFile` at `0x18001ba99`
- `KERNEL32!WriteFile` at `0x18001bc1b`
- `KERNEL32!WriteFile` at `0x18001bd12`
- `KERNEL32!WriteFile` at `0x18001be5d`
- `KERNEL32!WriteFile` at `0x18001beb5`
- `KERNEL32!GetConsoleCP` at `0x18001b945`
- `KERNEL32!GetConsoleCP` at `0x18001b945`
- `KERNEL32!GetConsoleMode` at `0x18001b929`
- `KERNEL32!GetConsoleMode` at `0x18001b929`

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
0x18001b808  mov     [rsp-8+arg_18], rbx
0x18001b80d  push    rbp
0x18001b80e  push    rsi
0x18001b80f  push    rdi
0x18001b810  push    r12
0x18001b812  push    r13
0x18001b814  push    r14
0x18001b816  push    r15
0x18001b818  lea     rbp, [rsp-3B90h]
0x18001b820  mov     eax, 3C90h
0x18001b825  call    _alloca_probe
0x18001b82a  sub     rsp, rax
0x18001b82d  mov     rax, cs:__security_cookie
0x18001b834  xor     rax, rsp
0x18001b837  mov     [rbp+3BC0h+var_40], rax
0x18001b83e  xor     ebx, ebx
0x18001b840  mov     r15d, r8d
0x18001b843  movsxd  rdi, ecx
0x18001b846  mov     r12, rdx
0x18001b849  mov     [rsp+3CC0h+NumberOfBytesWritten], ebx
0x18001b84d  test    r8d, r8d
0x18001b850  jz      loc_18001BF38
0x18001b856  test    rdx, rdx
0x18001b859  jnz     short loc_18001B889
0x18001b85b  call    __doserrno
0x18001b860  mov     [rax], ebx
0x18001b862  call    _errno
0x18001b867  xor     r9d, r9d; LineNo
0x18001b86a  mov     [rsp+3CC0h+Reserved], rbx; Reserved
0x18001b86f  xor     r8d, r8d; FileName
0x18001b872  xor     edx, edx; FunctionName
0x18001b874  xor     ecx, ecx; Expression
0x18001b876  mov     dword ptr [rax], 16h
0x18001b87c  call    _invalid_parameter
0x18001b881  or      eax, 0FFFFFFFFh
0x18001b884  jmp     loc_18001BF3A
0x18001b889  mov     eax, edi
0x18001b88b  lea     rcx, __pioinfo
0x18001b892  and     eax, 1Fh
0x18001b895  mov     r14, rdi
0x18001b898  imul    r13, rax, 38h ; '8'
0x18001b89c  sar     r14, 5
0x18001b8a0  mov     [rsp+3CC0h+var_3C68], r14
0x18001b8a5  mov     [rsp+3CC0h+var_3C70], r13
0x18001b8aa  mov     rcx, [rcx+r14*8]
0x18001b8ae  mov     esi, [rcx+r13+0Ch]
0x18001b8b3  and     esi, 3
0x18001b8b6  lea     eax, [rsi-1]
0x18001b8b9  cmp     eax, 1
0x18001b8bc  ja      short loc_18001B8C4
0x18001b8be  test    r15b, 1
0x18001b8c2  jnz     short loc_18001B85B
0x18001b8c4  test    byte ptr [rcx+r13+8], 20h
0x18001b8ca  mov     [rsp+3CC0h+var_3C78], ebx
0x18001b8ce  jz      short loc_18001B8DD
0x18001b8d0  xor     edx, edx
0x18001b8d2  mov     ecx, edi
0x18001b8d4  lea     r8d, [rdx+2]
0x18001b8d8  call    _lseeki64_nolock
0x18001b8dd  mov     ecx, edi; FileHandle
0x18001b8df  call    _isatty
0x18001b8e4  test    eax, eax
0x18001b8e6  jz      loc_18001BB6A
0x18001b8ec  lea     rax, __pioinfo
0x18001b8f3  mov     rax, [rax+r14*8]
0x18001b8f7  cmp     [rax+r13+8], bl
0x18001b8fc  jge     loc_18001BB6A
0x18001b902  mov     [rsp+3CC0h+Mode], ebx
0x18001b906  call    _getptd
0x18001b90b  lea     rdx, [rsp+3CC0h+Mode]; lpMode
0x18001b910  mov     rcx, [rax+0C0h]
0x18001b917  lea     rax, __pioinfo
0x18001b91e  mov     edi, [rcx+14h]
0x18001b921  mov     rcx, [rax+r14*8]
0x18001b925  mov     rcx, [rcx+r13]; hConsoleHandle
0x18001b929  call    cs:__imp_GetConsoleMode
0x18001b92f  test    eax, eax
0x18001b931  jz      loc_18001BB6A
0x18001b937  test    edi, edi
0x18001b939  jnz     short loc_18001B943
0x18001b93b  test    esi, esi
0x18001b93d  jz      loc_18001BB6A
0x18001b943  xor     edi, edi
0x18001b945  call    cs:__imp_GetConsoleCP
0x18001b94b  xor     ecx, ecx
0x18001b94d  mov     [rsp+3CC0h+CodePage], eax
0x18001b951  mov     word ptr [rsp+3CC0h+Mode], cx
0x18001b956  mov     r14, r12
0x18001b959  test    r15d, r15d
0x18001b95c  jz      loc_18001BEFE
0x18001b962  lea     ecx, [rdi+0Ah]
0x18001b965  test    esi, esi
0x18001b967  jnz     loc_18001BABF
0x18001b96d  movsx   eax, byte ptr [r14]
0x18001b971  mov     ecx, eax; C
0x18001b973  mov     [rsp+3CC0h+var_3C5C], eax
0x18001b977  call    isleadbyte
0x18001b97c  test    eax, eax
0x18001b97e  jnz     short loc_18001B99C
0x18001b980  lea     r8d, [rsi+1]; SrcSizeInBytes
0x18001b984  mov     rdx, r14; SrcCh
0x18001b987  lea     rcx, [rsp+3CC0h+Mode]; DstCh
0x18001b98c  call    mbtowc
0x18001b991  cmp     eax, 0FFFFFFFFh
0x18001b994  jz      loc_18001BB57
0x18001b99a  jmp     short loc_18001B9CE
0x18001b99c  mov     rax, r15
0x18001b99f  sub     rax, r14
0x18001b9a2  add     rax, r12
0x18001b9a5  cmp     rax, 1
0x18001b9a9  jle     loc_18001BB57
0x18001b9af  mov     r8d, 2; SrcSizeInBytes
0x18001b9b5  lea     rcx, [rsp+3CC0h+Mode]; DstCh
0x18001b9ba  mov     rdx, r14; SrcCh
0x18001b9bd  call    mbtowc
0x18001b9c2  cmp     eax, 0FFFFFFFFh
0x18001b9c5  jz      loc_18001BB57
0x18001b9cb  inc     r14
0x18001b9ce  mov     ecx, [rsp+3CC0h+CodePage]; CodePage
0x18001b9d2  lea     rax, [rsp+3CC0h+MultiByteStr]
0x18001b9d7  mov     [rsp+3CC0h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x18001b9dc  lea     r8, [rsp+3CC0h+Mode]; lpWideCharStr
0x18001b9e1  mov     [rsp+3CC0h+lpDefaultChar], rdi; lpDefaultChar
0x18001b9e6  mov     r9d, 1; cchWideChar
0x18001b9ec  mov     [rsp+3CC0h+cbMultiByte], 5; cbMultiByte
0x18001b9f4  xor     edx, edx; dwFlags
0x18001b9f6  mov     [rsp+3CC0h+Reserved], rax; lpMultiByteStr
0x18001b9fb  inc     r14
0x18001b9fe  call    cs:__imp_WideCharToMultiByte
0x18001ba04  mov     r13d, eax
0x18001ba07  test    eax, eax
0x18001ba09  jz      loc_18001BB52
0x18001ba0f  mov     rax, [rsp+3CC0h+var_3C68]
0x18001ba14  lea     rcx, __pioinfo
0x18001ba1b  lea     r9, [rsp+3CC0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001ba20  mov     [rsp+3CC0h+Reserved], rdi; lpOverlapped
0x18001ba25  mov     r8d, r13d; nNumberOfBytesToWrite
0x18001ba28  lea     rdx, [rsp+3CC0h+MultiByteStr]; lpBuffer
0x18001ba2d  mov     rcx, [rcx+rax*8]
0x18001ba31  mov     rax, [rsp+3CC0h+var_3C70]
0x18001ba36  mov     rcx, [rcx+rax]; hFile
0x18001ba3a  call    cs:__imp_WriteFile
0x18001ba40  test    eax, eax
0x18001ba42  jz      loc_18001BB4A
0x18001ba48  add     ebx, [rsp+3CC0h+NumberOfBytesWritten]
0x18001ba4c  cmp     [rsp+3CC0h+NumberOfBytesWritten], r13d
0x18001ba51  jl      loc_18001BB52
0x18001ba57  mov     r13, [rsp+3CC0h+var_3C70]
0x18001ba5c  mov     ecx, 0Ah
0x18001ba61  cmp     [rsp+3CC0h+var_3C5C], ecx
0x18001ba65  jnz     loc_18001BB2F
0x18001ba6b  mov     rax, [rsp+3CC0h+var_3C68]
0x18001ba70  lea     rcx, __pioinfo
0x18001ba77  mov     [rsp+3CC0h+MultiByteStr], 0Dh
0x18001ba7c  lea     r9, [rsp+3CC0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001ba81  mov     r8d, 1; nNumberOfBytesToWrite
0x18001ba87  mov     [rsp+3CC0h+Reserved], rdi; lpOverlapped
0x18001ba8c  lea     rdx, [rsp+3CC0h+MultiByteStr]; lpBuffer
0x18001ba91  mov     rcx, [rcx+rax*8]
0x18001ba95  mov     rcx, [rcx+r13]; hFile
0x18001ba99  call    cs:__imp_WriteFile
0x18001ba9f  test    eax, eax
0x18001baa1  jz      loc_18001BB40
0x18001baa7  cmp     [rsp+3CC0h+NumberOfBytesWritten], 1
0x18001baac  jl      loc_18001BB57
0x18001bab2  inc     [rsp+3CC0h+var_3C78]
0x18001bab6  mov     ecx, 0Ah
0x18001babb  inc     ebx
0x18001babd  jmp     short loc_18001BB2F
0x18001babf  cmp     esi, 1
0x18001bac2  jz      short loc_18001BACC
0x18001bac4  xor     r13d, r13d
0x18001bac7  cmp     esi, 2
0x18001baca  jnz     short loc_18001BAE3
0x18001bacc  movzx   eax, word ptr [r14]
0x18001bad0  xor     r13d, r13d
0x18001bad3  cmp     ax, cx
0x18001bad6  mov     word ptr [rsp+3CC0h+Mode], ax
0x18001badb  setz    r13b
0x18001badf  add     r14, 2
0x18001bae3  lea     eax, [rsi-1]
0x18001bae6  cmp     eax, 1
0x18001bae9  ja      short loc_18001BB2A
0x18001baeb  movzx   ecx, word ptr [rsp+3CC0h+Mode]; Character
0x18001baf0  call    _putwch_nolock
0x18001baf5  cmp     ax, word ptr [rsp+3CC0h+Mode]
0x18001bafa  jnz     short loc_18001BB4A
0x18001bafc  add     ebx, 2
0x18001baff  test    r13d, r13d
0x18001bb02  jz      short loc_18001BB25
0x18001bb04  mov     r13d, 0Dh
0x18001bb0a  mov     ecx, r13d; Character
0x18001bb0d  mov     word ptr [rsp+3CC0h+Mode], r13w
0x18001bb13  call    _putwch_nolock
0x18001bb18  cmp     ax, word ptr [rsp+3CC0h+Mode]
0x18001bb1d  jnz     short loc_18001BB4A
0x18001bb1f  inc     ebx
0x18001bb21  inc     [rsp+3CC0h+var_3C78]
0x18001bb25  mov     ecx, 0Ah
0x18001bb2a  mov     r13, [rsp+3CC0h+var_3C70]
0x18001bb2f  mov     eax, r14d
0x18001bb32  sub     eax, r12d
0x18001bb35  cmp     eax, r15d
0x18001bb38  jb      loc_18001B965
0x18001bb3e  jmp     short loc_18001BB57
0x18001bb40  call    cs:__imp_GetLastError
0x18001bb46  mov     edi, eax
0x18001bb48  jmp     short loc_18001BB57
0x18001bb4a  call    cs:__imp_GetLastError
0x18001bb50  mov     edi, eax
0x18001bb52  mov     r13, [rsp+3CC0h+var_3C70]
0x18001bb57  test    ebx, ebx
0x18001bb59  jz      loc_18001BED2
0x18001bb5f  sub     ebx, [rsp+3CC0h+var_3C78]
0x18001bb63  mov     eax, ebx
0x18001bb65  jmp     loc_18001BF3A
0x18001bb6a  lea     rax, __pioinfo
0x18001bb71  mov     rcx, [rax+r14*8]
0x18001bb75  cmp     [rcx+r13+8], bl
0x18001bb7a  jge     loc_18001BEA1
0x18001bb80  xor     edi, edi
0x18001bb82  test    esi, esi
0x18001bb84  jnz     loc_18001BC61
0x18001bb8a  mov     r14, r12
0x18001bb8d  test    r15d, r15d
0x18001bb90  jz      loc_18001BEFE
0x18001bb96  lea     edx, [rdi+0Ah]
0x18001bb99  lea     ecx, [rdi+0Dh]
0x18001bb9c  mov     r13d, [rsp+3CC0h+var_3C78]
0x18001bba1  lea     rsi, [rbp+3BC0h+Buffer]
0x18001bba8  mov     eax, r14d
0x18001bbab  sub     eax, r12d
0x18001bbae  cmp     eax, r15d
0x18001bbb1  jnb     short loc_18001BBDF
0x18001bbb3  mov     al, [r14]
0x18001bbb6  inc     r14
0x18001bbb9  cmp     al, dl
0x18001bbbb  jnz     short loc_18001BBC5
0x18001bbbd  inc     r13d
0x18001bbc0  mov     [rsi], cl
0x18001bbc2  inc     rsi
0x18001bbc5  mov     [rsi], al
0x18001bbc7  lea     r8, [rbp+3BC0h+Buffer]
0x18001bbce  inc     rsi
0x18001bbd1  mov     rax, rsi
0x18001bbd4  sub     rax, r8
0x18001bbd7  cmp     rax, 13FFh
0x18001bbdd  jb      short loc_18001BBA8
0x18001bbdf  lea     rax, [rbp+3BC0h+Buffer]
0x18001bbe6  mov     [rsp+3CC0h+var_3C78], r13d
0x18001bbeb  mov     r13, [rsp+3CC0h+var_3C70]
0x18001bbf0  lea     rcx, __pioinfo
0x18001bbf7  mov     r8d, esi
0x18001bbfa  mov     [rsp+3CC0h+Reserved], rdi; lpOverlapped
0x18001bbff  sub     r8d, eax; nNumberOfBytesToWrite
0x18001bc02  lea     r9, [rsp+3CC0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001bc07  mov     rax, [rsp+3CC0h+var_3C68]
0x18001bc0c  lea     rdx, [rbp+3BC0h+Buffer]; lpBuffer
0x18001bc13  mov     rcx, [rcx+rax*8]
0x18001bc17  mov     rcx, [rcx+r13]; hFile
0x18001bc1b  call    cs:__imp_WriteFile
0x18001bc21  test    eax, eax
0x18001bc23  jz      loc_18001BB40
0x18001bc29  add     ebx, [rsp+3CC0h+NumberOfBytesWritten]
0x18001bc2d  lea     rax, [rbp+3BC0h+Buffer]
0x18001bc34  sub     rsi, rax
0x18001bc37  movsxd  rax, [rsp+3CC0h+NumberOfBytesWritten]
0x18001bc3c  cmp     rax, rsi
0x18001bc3f  jl      loc_18001BB57
0x18001bc45  mov     eax, r14d
0x18001bc48  mov     ecx, 0Dh
0x18001bc4d  sub     eax, r12d
0x18001bc50  lea     edx, [rcx-3]
0x18001bc53  cmp     eax, r15d
0x18001bc56  jb      loc_18001BB9C
0x18001bc5c  jmp     loc_18001BB57
0x18001bc61  cmp     esi, 2
0x18001bc64  jnz     loc_18001BD5F
0x18001bc6a  mov     r14, r12
0x18001bc6d  test    r15d, r15d
0x18001bc70  jz      loc_18001BEFE
0x18001bc76  lea     edx, [rsi+0Bh]
0x18001bc79  lea     r8d, [rsi+8]
0x18001bc7d  lea     rsi, [rbp+3BC0h+var_35A0]
0x18001bc84  mov     eax, r14d
0x18001bc87  sub     eax, r12d
0x18001bc8a  cmp     eax, r15d
0x18001bc8d  jnb     short loc_18001BCE0
0x18001bc8f  movzx   ecx, word ptr [r14]
0x18001bc93  add     r14, 2
0x18001bc97  cmp     cx, r8w
0x18001bc9b  jnz     short loc_18001BCBE
0x18001bc9d  lea     r9, [rbp+3BC0h+var_35A0]
0x18001bca4  mov     rax, rsi
0x18001bca7  sub     rax, r9
0x18001bcaa  cmp     rax, 13FCh
0x18001bcb0  ja      short loc_18001BCDC
0x18001bcb2  add     [rsp+3CC0h+var_3C78], 2
0x18001bcb7  mov     [rsi], dx
0x18001bcba  add     rsi, 2
  ... truncated ...
```
