# CConsoleHost::WriteLine(void *,ushort const *)

- ea: `0x140002a70`
- end: `0x14000314f`
- name: `?WriteLine@CConsoleHost@@IEAAJPEAXPEBG@Z`
- size: `1759`
- prototype: `__int64 __fastcall(CConsoleHost *__hidden this, void *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1400029e4`
- `0x140002a20`
- `0x14000a200`

## callees

- `0x1400028b0`
- `0x140002a70`
- `0x140006250`
- `0x140009c70`
- `0x140009cb0`
- `0x14000a0f0`
- `0x140016182`
- `0x1400161d0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140002b40`
- `KERNEL32!HeapFree` at `0x140002b40`
- `KERNEL32!HeapAlloc` at `0x140002b60`
- `KERNEL32!HeapAlloc` at `0x140002b60`
- `KERNEL32!WideCharToMultiByte` at `0x140002d23`
- `KERNEL32!WideCharToMultiByte` at `0x140002d67`
- `KERNEL32!WideCharToMultiByte` at `0x140002d23`
- `KERNEL32!WideCharToMultiByte` at `0x140002d67`
- `KERNEL32!WriteConsoleW` at `0x1400030b9`
- `KERNEL32!WriteConsoleW` at `0x1400030b9`
- `KERNEL32!GetLastError` at `0x140002da1`
- `KERNEL32!GetLastError` at `0x140002ff8`
- `KERNEL32!GetLastError` at `0x140003021`
- `KERNEL32!GetLastError` at `0x1400030c3`
- `KERNEL32!GetLastError` at `0x140002da1`
- `KERNEL32!GetLastError` at `0x140002ff8`
- `KERNEL32!GetLastError` at `0x140003021`
- `KERNEL32!GetLastError` at `0x1400030c3`
- `KERNEL32!WriteFile` at `0x140002d93`
- `KERNEL32!WriteFile` at `0x1400030ef`
- `KERNEL32!WriteFile` at `0x140002d93`
- `KERNEL32!WriteFile` at `0x1400030ef`
- `KERNEL32!GetProcessHeap` at `0x140002b32`
- `KERNEL32!GetProcessHeap` at `0x140002b52`
- `KERNEL32!GetProcessHeap` at `0x140002ebf`
- `KERNEL32!GetProcessHeap` at `0x140002f55`
- `KERNEL32!GetProcessHeap` at `0x140002fd0`
- `KERNEL32!GetProcessHeap` at `0x140002b32`
- `KERNEL32!GetProcessHeap` at `0x140002b52`
- `KERNEL32!GetProcessHeap` at `0x140002ebf`
- `KERNEL32!GetProcessHeap` at `0x140002f55`
- `KERNEL32!GetProcessHeap` at `0x140002fd0`
- `KERNEL32!HeapReAlloc` at `0x140002ed2`
- `KERNEL32!HeapReAlloc` at `0x140002f68`
- `KERNEL32!HeapReAlloc` at `0x140002fe3`
- `KERNEL32!HeapReAlloc` at `0x140002ed2`
- `KERNEL32!HeapReAlloc` at `0x140002f68`
- `KERNEL32!HeapReAlloc` at `0x140002fe3`

## pseudocode

```c
__int64 __fastcall CConsoleHost::WriteLine(CConsoleHost *this, void *a2, const unsigned __int16 *a3)
{
  int v3; // r14d
  const OLECHAR *v4; // rbx
  char *v5; // r12
  unsigned int v6; // r15d
  __int64 v7; // rax
  const OLECHAR *v8; // r13
  signed int v10; // edi
  HANDLE v11; // rax
  HANDLE ProcessHeap; // rax
  char *v13; // rax
  unsigned int v14; // edi
  int v15; // eax
  __int64 v16; // rsi
  __int64 v17; // rbx
  unsigned int v18; // esi
  __int64 v19; // rbx
  char *v20; // rsi
  unsigned int v21; // eax
  unsigned int cbMultiByte; // ebx
  void *v23; // r13
  CHAR *lpMultiByteStr; // r14
  DWORD v25; // ebx
  HANDLE v26; // rsi
  signed int v27; // eax
  int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // esi
  unsigned __int64 v31; // rdi
  unsigned int v32; // ecx
  unsigned __int64 v33; // rdx
  unsigned __int64 v34; // rdx
  HANDLE v35; // rax
  char *v36; // rax
  unsigned int v37; // ecx
  unsigned __int64 v38; // rdx
  unsigned __int64 v39; // rdx
  HANDLE v40; // rax
  char *v41; // rax
  unsigned int v42; // r8d
  unsigned __int64 v43; // rdx
  unsigned __int64 v44; // rdx
  HANDLE v45; // rax
  char *v46; // rax
  signed int LastError; // eax
  HANDLE v48; // r14
  DWORD v49; // r8d
  __int64 v50; // rax
  void *v51; // rax
  unsigned __int16 Src; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v54; // [rsp+4Ch] [rbp-B4h]
  SIZE_T dwBytes; // [rsp+50h] [rbp-B0h] BYREF
  char *v56; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v57; // [rsp+60h] [rbp-A0h]
  unsigned int v58; // [rsp+64h] [rbp-9Ch]
  HANDLE hFile; // [rsp+68h] [rbp-98h]
  CConsoleHost *v60; // [rsp+70h] [rbp-90h]
  CHAR MultiByteStr; // [rsp+80h] [rbp-80h] BYREF

  v3 = 0;
  hFile = a2;
  v60 = this;
  v4 = &Default;
  v57 = 0;
  if ( a3 )
    v4 = a3;
  NumberOfBytesWritten = 0;
  v5 = 0;
  v6 = 0;
  if ( !v4 )
    return 2147942487LL;
  v7 = -1;
  do
    ++v7;
  while ( v4[v7] );
  v8 = &v4[(unsigned int)v7];
  if ( !v8 || v4 > v8 )
    return 2147942487LL;
  v30 = v7 + 10;
  v31 = 2LL * (unsigned int)(v7 + 10);
  v54 = v7 + 10;
  v58 = v7 + 10;
  if ( v31 > 0xFFFFFFFF )
    goto LABEL_9;
  ProcessHeap = GetProcessHeap();
  v13 = (char *)HeapAlloc(ProcessHeap, 0, (unsigned int)v31);
  v56 = v13;
  v5 = v13;
  if ( !v13 )
  {
LABEL_78:
    v10 = -2147024882;
    goto LABEL_10;
  }
  *(_WORD *)v13 = 0;
  v14 = v30;
  while ( 1 )
  {
    v15 = v3;
    if ( v4 >= v8 )
      break;
    v3 = *v4;
    if ( (_WORD)v3 == 10 && v15 != 13 )
    {
      Src = 13;
      v28 = CCharSink::Emit((CCharSink *)&v56, &Src, 1u);
      v5 = v56;
      v10 = v28;
      if ( v28 < 0 )
        goto LABEL_10;
      v14 = v58;
      v6 = v57;
      v54 = v58;
    }
    v16 = v6 + 1;
    Src = v3;
    if ( (unsigned int)v16 < v6 || v6 + 2 < v6 + 1 )
      goto LABEL_9;
    if ( v6 + 2 >= v14 )
    {
      v32 = v14 + 1;
      if ( v14 + 1 < v14 )
        goto LABEL_9;
      v33 = 50LL * v32;
      v58 = v14 + 1;
      if ( v33 > 0xFFFFFFFF )
        goto LABEL_9;
      v34 = (unsigned int)v33 / 0x64;
      v54 = v34 + v32;
      if ( (unsigned int)v34 + v32 < v32 )
        goto LABEL_9;
      v58 = v34 + v32;
      dwBytes = 0;
      v10 = ULongLongMult((unsigned int)v34 + v32, v34, &dwBytes);
      if ( v10 < 0 )
        goto LABEL_10;
      v35 = GetProcessHeap();
      v36 = (char *)HeapReAlloc(v35, 0, v5, dwBytes);
      if ( !v36 )
        goto LABEL_78;
      v14 = v54;
      v5 = v36;
      v56 = v36;
    }
    if ( v5 )
    {
      dwBytes = 0;
      if ( !is_mul_ok(1u, 2u) )
        goto LABEL_9;
      memcpy_0(&v5[2 * v6], &Src, 2u);
      v57 = v6 + 1;
      *(_WORD *)&v5[2 * v16] = 0;
      ++v6;
    }
    ++v4;
  }
  v17 = v6 + 1;
  Src = 13;
  if ( (unsigned int)v17 < v6 || v6 + 2 < v6 + 1 )
    goto LABEL_9;
  v18 = v54;
  if ( v6 + 2 >= v54 )
  {
    v37 = v54 + 1;
    if ( v54 + 1 < v54 )
      goto LABEL_9;
    v38 = 50LL * v37;
    if ( v38 > 0xFFFFFFFF )
      goto LABEL_9;
    v39 = (unsigned int)v38 / 0x64;
    v18 = v39 + v37;
    if ( (unsigned int)v39 + v37 < v37 )
      goto LABEL_9;
    dwBytes = 0;
    v10 = ULongLongMult(v18, v39, &dwBytes);
    if ( v10 < 0 )
      goto LABEL_10;
    v40 = GetProcessHeap();
    v41 = (char *)HeapReAlloc(v40, 0, v5, dwBytes);
    if ( !v41 )
    {
      v10 = -2147024882;
      goto LABEL_10;
    }
    v5 = v41;
  }
  if ( v5 )
  {
    dwBytes = 0;
    if ( !is_mul_ok(1u, 2u) )
      goto LABEL_9;
    memcpy_0(&v5[2 * v6], &Src, 2u);
    *(_WORD *)&v5[2 * v17] = 0;
    ++v6;
  }
  v19 = v6 + 1;
  Src = 10;
  if ( (unsigned int)v19 < v6 || v6 + 2 < v6 + 1 )
    goto LABEL_9;
  if ( v6 + 2 >= v18 )
  {
    v42 = v18 + 1;
    if ( v18 + 1 < v18 )
      goto LABEL_9;
    v43 = 50LL * v42;
    if ( v43 > 0xFFFFFFFF )
      goto LABEL_9;
    v44 = (unsigned int)v43 / 0x64;
    if ( (unsigned int)v44 + v42 < v42 )
      goto LABEL_9;
    dwBytes = 0;
    v10 = ULongLongMult((unsigned int)v44 + v42, v44, &dwBytes);
    if ( v10 < 0 )
      goto LABEL_10;
    v45 = GetProcessHeap();
    v46 = (char *)HeapReAlloc(v45, 0, v5, dwBytes);
    if ( !v46 )
    {
      v10 = -2147024882;
      goto LABEL_10;
    }
    v5 = v46;
  }
  if ( v5 )
  {
    if ( is_mul_ok(1u, 2u) )
    {
      memcpy_0(&v5[2 * v6++], &Src, 2u);
      *(_WORD *)&v5[2 * v19] = 0;
      goto LABEL_36;
    }
LABEL_9:
    v10 = -2147024362;
    goto LABEL_10;
  }
LABEL_36:
  v20 = v5;
  if ( Global::g_fWindowsNT )
  {
    v48 = hFile;
    if ( *((_BYTE *)v60 + 73) || IsConsole(hFile) )
    {
      v10 = 0;
      while ( v6 )
      {
        v49 = v6;
        if ( v6 > 0x3FFF )
          v49 = 0x3FFF;
        if ( !WriteConsoleW(v48, v20, v49, &NumberOfBytesWritten, 0) )
        {
          LastError = GetLastError();
          if ( LastError == 6 )
          {
            while ( v6 )
            {
              if ( !WriteFile(v48, v20, 2 * v6, &NumberOfBytesWritten, 0) )
                goto LABEL_72;
              v50 = NumberOfBytesWritten >> 1;
              NumberOfBytesWritten = v50;
              v6 -= v50;
              v20 += 2 * v50;
            }
          }
          else
          {
            if ( LastError > 0 )
              goto LABEL_73;
            v10 = LastError;
          }
          goto LABEL_10;
        }
        v6 -= NumberOfBytesWritten;
        v20 += 2 * NumberOfBytesWritten;
      }
      goto LABEL_10;
    }
  }
  v21 = WideCharToMultiByte(1u, 0, (LPCWCH)v5, v6, 0, 0, 0, 0);
  cbMultiByte = v21;
  if ( v21 )
  {
    if ( v21 < 0x200 )
    {
      v23 = 0;
      lpMultiByteStr = &MultiByteStr;
LABEL_40:
      v10 = 0;
      v25 = WideCharToMultiByte(1u, 0, (LPCWCH)v5, v6, lpMultiByteStr, cbMultiByte, 0, 0);
      if ( v25 )
      {
        v26 = hFile;
        while ( v25 )
        {
          if ( !WriteFile(v26, lpMultiByteStr, v25, &NumberOfBytesWritten, 0) )
          {
            v27 = GetLastError();
            v10 = v27;
            if ( v27 > 0 )
              goto LABEL_77;
            break;
          }
          lpMultiByteStr += NumberOfBytesWritten;
          v25 -= NumberOfBytesWritten;
        }
      }
      else
      {
        v27 = GetLastError();
        v10 = v27;
        if ( v27 > 0 )
LABEL_77:
          v10 = (unsigned __int16)v27 | 0x80070000;
      }
      if ( v23 )
        operator delete(v23);
      goto LABEL_10;
    }
    v29 = v21 + 1;
    if ( v29 >= cbMultiByte )
    {
      v51 = operator new(v29);
      v23 = v51;
      if ( v51 )
      {
        lpMultiByteStr = (CHAR *)v51;
        goto LABEL_40;
      }
      v10 = -2147024882;
    }
    else
    {
      v10 = -2147024882;
    }
  }
  else
  {
LABEL_72:
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
LABEL_73:
      v10 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_10:
  if ( v5 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v5);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140002a70  mov     [rsp-8+arg_18], rbx
0x140002a75  push    rbp
0x140002a76  push    r12
0x140002a78  push    r13
0x140002a7a  push    r14
0x140002a7c  push    r15
0x140002a7e  lea     rbp, [rsp-190h]
0x140002a86  sub     rsp, 290h
0x140002a8d  mov     rax, cs:__security_cookie
0x140002a94  xor     rax, rsp
0x140002a97  mov     [rbp+1B0h+var_30], rax
0x140002a9e  xor     r14d, r14d
0x140002aa1  mov     [rsp+2B0h+hFile], rdx
0x140002aa6  test    r8, r8
0x140002aa9  mov     [rsp+2B0h+var_240], rcx
0x140002aae  lea     rbx, Default
0x140002ab5  mov     [rsp+2B0h+var_250], r14d
0x140002aba  cmovnz  rbx, r8
0x140002abe  mov     [rsp+2B0h+NumberOfBytesWritten], r14d
0x140002ac3  mov     r12d, r14d
0x140002ac6  mov     r15d, r14d
0x140002ac9  test    rbx, rbx
0x140002acc  jz      short loc_140002AF3
0x140002ace  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140002ad5  inc     rax
0x140002ad8  cmp     [rbx+rax*2], r14w
0x140002add  jnz     short loc_140002AD5
0x140002adf  mov     ecx, eax
0x140002ae1  lea     r13, [rbx+rcx*2]
0x140002ae5  test    r13, r13
0x140002ae8  jz      short loc_140002AF3
0x140002aea  cmp     rbx, r13
0x140002aed  jbe     loc_140002E2D
0x140002af3  mov     eax, 80070057h
0x140002af8  mov     rcx, [rbp+1B0h+var_30]
0x140002aff  xor     rcx, rsp; StackCookie
0x140002b02  call    __security_check_cookie
0x140002b07  mov     rbx, [rsp+2B0h+arg_18]
0x140002b0f  add     rsp, 290h
0x140002b16  pop     r15
0x140002b18  pop     r14
0x140002b1a  pop     r13
0x140002b1c  pop     r12
0x140002b1e  pop     rbp
0x140002b1f  retn
0x140002b20  mov     edi, 80070216h
0x140002b25  mov     rsi, [rsp+2B0h+arg_0]
0x140002b2d  test    r12, r12
0x140002b30  jz      short loc_140002B46
0x140002b32  call    cs:__imp_GetProcessHeap
0x140002b38  mov     r8, r12; lpMem
0x140002b3b  xor     edx, edx; dwFlags
0x140002b3d  mov     rcx, rax; hHeap
0x140002b40  call    cs:__imp_HeapFree
0x140002b46  mov     eax, edi
0x140002b48  mov     rdi, [rsp+2B0h+arg_10]
0x140002b50  jmp     short loc_140002AF8
0x140002b52  call    cs:__imp_GetProcessHeap
0x140002b58  mov     r8d, edi; dwBytes
0x140002b5b  xor     edx, edx; dwFlags
0x140002b5d  mov     rcx, rax; hHeap
0x140002b60  call    cs:__imp_HeapAlloc
0x140002b66  mov     [rsp+2B0h+var_258], rax
0x140002b6b  mov     r12, rax
0x140002b6e  test    rax, rax
0x140002b71  jz      loc_14000303F
0x140002b77  mov     [rax], r14w
0x140002b7b  mov     ecx, 0Ah
0x140002b80  mov     edx, 1
0x140002b85  mov     r8d, 0Dh
0x140002b8b  mov     edi, esi
0x140002b8d  mov     eax, r14d
0x140002b90  cmp     rbx, r13
0x140002b93  jnb     loc_140002C27
0x140002b99  movzx   r14d, word ptr [rbx]
0x140002b9d  cmp     cx, r14w
0x140002ba1  jz      loc_140002DC7
0x140002ba7  lea     esi, [r15+1]
0x140002bab  mov     [rsp+2B0h+Src], r14w
0x140002bb1  cmp     esi, r15d
0x140002bb4  jb      loc_140002B20
0x140002bba  lea     eax, [rsi+1]
0x140002bbd  cmp     eax, esi
0x140002bbf  jb      loc_140002B20
0x140002bc5  cmp     eax, edi
0x140002bc7  jnb     loc_140002E60
0x140002bcd  test    r12, r12
0x140002bd0  jz      short loc_140002C1E
0x140002bd2  mov     eax, 2
0x140002bd7  mov     [rsp+2B0h+dwBytes], 0
0x140002be0  mul     rdx
0x140002be3  mov     r8, rax; Size
0x140002be6  test    rdx, rdx
0x140002be9  jnz     loc_140002B20
0x140002bef  mov     eax, r15d
0x140002bf2  lea     rdx, [rsp+2B0h+Src]; Src
0x140002bf7  lea     rcx, [r12+rax*2]; void *
0x140002bfb  call    memcpy_0
0x140002c00  xor     eax, eax
0x140002c02  mov     [rsp+2B0h+var_250], esi
0x140002c06  mov     [r12+rsi*2], ax
0x140002c0b  mov     r15d, esi
0x140002c0e  mov     ecx, 0Ah
0x140002c13  mov     edx, 1
0x140002c18  mov     r8d, 0Dh
0x140002c1e  add     rbx, 2
0x140002c22  jmp     loc_140002B8D
0x140002c27  lea     ebx, [r15+1]
0x140002c2b  mov     [rsp+2B0h+Src], r8w
0x140002c31  cmp     ebx, r15d
0x140002c34  jb      loc_140002B20
0x140002c3a  lea     eax, [rbx+1]
0x140002c3d  cmp     eax, ebx
0x140002c3f  jb      loc_140002B20
0x140002c45  mov     esi, [rsp+2B0h+var_264]
0x140002c49  cmp     eax, esi
0x140002c4b  jnb     loc_140002F02
0x140002c51  xor     r14d, r14d
0x140002c54  mov     r13d, 0FFFFFFFFh
0x140002c5a  test    r12, r12
0x140002c5d  jz      short loc_140002C9B
0x140002c5f  mov     eax, 2
0x140002c64  mov     [rsp+2B0h+dwBytes], r14
0x140002c69  mul     rdx
0x140002c6c  mov     r8, rax; Size
0x140002c6f  test    rdx, rdx
0x140002c72  jnz     loc_140002B20
0x140002c78  mov     eax, r15d
0x140002c7b  lea     rdx, [rsp+2B0h+Src]; Src
0x140002c80  lea     rcx, [r12+rax*2]; void *
0x140002c84  call    memcpy_0
0x140002c89  mov     ecx, 0Ah
0x140002c8e  mov     [r12+rbx*2], r14w
0x140002c93  mov     edx, 1
0x140002c98  mov     r15d, ebx
0x140002c9b  lea     ebx, [r15+1]
0x140002c9f  mov     [rsp+2B0h+Src], cx
0x140002ca4  cmp     ebx, r15d
0x140002ca7  jb      loc_140002B20
0x140002cad  lea     eax, [rbx+1]
0x140002cb0  cmp     eax, ebx
0x140002cb2  jb      loc_140002B20
0x140002cb8  cmp     eax, esi
0x140002cba  jnb     loc_140002F81
0x140002cc0  test    r12, r12
0x140002cc3  jz      short loc_140002CF2
0x140002cc5  mov     eax, 2
0x140002cca  mul     rdx
0x140002ccd  mov     r8, rax; Size
0x140002cd0  test    rdx, rdx
0x140002cd3  jnz     loc_140002B20
0x140002cd9  mov     eax, r15d
0x140002cdc  lea     rdx, [rsp+2B0h+Src]; Src
0x140002ce1  lea     rcx, [r12+rax*2]; void *
0x140002ce5  call    memcpy_0
0x140002cea  mov     r15d, ebx
0x140002ced  mov     [r12+rbx*2], r14w
0x140002cf2  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x140002cf9  mov     rsi, r12
0x140002cfc  jnz     loc_140003068
0x140002d02  mov     [rsp+2B0h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x140002d07  mov     r9d, r15d; cchWideChar
0x140002d0a  mov     [rsp+2B0h+lpDefaultChar], r14; lpDefaultChar
0x140002d0f  mov     r8, r12; lpWideCharStr
0x140002d12  mov     [rsp+2B0h+cbMultiByte], r14d; cbMultiByte
0x140002d17  xor     edx, edx; dwFlags
0x140002d19  mov     ecx, 1; CodePage
0x140002d1e  mov     [rsp+2B0h+lpMultiByteStr], r14; lpMultiByteStr
0x140002d23  call    cs:__imp_WideCharToMultiByte
0x140002d29  mov     ebx, eax
0x140002d2b  test    eax, eax
0x140002d2d  jz      loc_140002FF8
0x140002d33  cmp     eax, 200h
0x140002d38  jnb     loc_140002E19
0x140002d3e  mov     r13, r14
0x140002d41  lea     r14, [rbp+1B0h+MultiByteStr]
0x140002d45  xor     edi, edi
0x140002d47  mov     r9d, r15d; cchWideChar
0x140002d4a  mov     [rsp+2B0h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x140002d4f  mov     r8, r12; lpWideCharStr
0x140002d52  mov     [rsp+2B0h+lpDefaultChar], rdi; lpDefaultChar
0x140002d57  xor     edx, edx; dwFlags
0x140002d59  mov     [rsp+2B0h+cbMultiByte], ebx; cbMultiByte
0x140002d5d  mov     ecx, 1; CodePage
0x140002d62  mov     [rsp+2B0h+lpMultiByteStr], r14; lpMultiByteStr
0x140002d67  call    cs:__imp_WideCharToMultiByte
0x140002d6d  mov     ebx, eax
0x140002d6f  test    eax, eax
0x140002d71  jz      loc_140003021
0x140002d77  mov     rsi, [rsp+2B0h+hFile]
0x140002d7c  test    ebx, ebx
0x140002d7e  jz      short loc_140002DB1
0x140002d80  lea     r9, [rsp+2B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140002d85  mov     [rsp+2B0h+lpMultiByteStr], rdi; lpOverlapped
0x140002d8a  mov     r8d, ebx; nNumberOfBytesToWrite
0x140002d8d  mov     rdx, r14; lpBuffer
0x140002d90  mov     rcx, rsi; hFile
0x140002d93  call    cs:__imp_WriteFile
0x140002d99  test    eax, eax
0x140002d9b  jnz     loc_140003141
0x140002da1  call    cs:__imp_GetLastError
0x140002da7  mov     edi, eax
0x140002da9  test    eax, eax
0x140002dab  jg      loc_140003031
0x140002db1  test    r13, r13
0x140002db4  jz      loc_140002B25
0x140002dba  mov     rcx, r13; Block
0x140002dbd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002dc2  jmp     loc_140002B25
0x140002dc7  cmp     eax, 0Dh
0x140002dca  jz      loc_140002BA7
0x140002dd0  mov     [rsp+2B0h+Src], r8w
0x140002dd6  lea     rcx, [rsp+2B0h+var_258]; this
0x140002ddb  mov     r8d, edx; unsigned int
0x140002dde  lea     rdx, [rsp+2B0h+Src]; unsigned __int16 *
0x140002de3  call    ?Emit@CCharSink@@QEAAJPEBGK@Z; CCharSink::Emit(ushort const *,ulong)
0x140002de8  mov     r12, [rsp+2B0h+var_258]
0x140002ded  mov     edi, eax
0x140002def  test    eax, eax
0x140002df1  js      loc_140002B25
0x140002df7  mov     edi, [rsp+2B0h+var_24C]
0x140002dfb  mov     ecx, 0Ah
0x140002e00  mov     r15d, [rsp+2B0h+var_250]
0x140002e05  mov     edx, 1
0x140002e0a  mov     [rsp+2B0h+var_264], edi
0x140002e0e  mov     r8d, 0Dh
0x140002e14  jmp     loc_140002BA7
0x140002e19  inc     eax
0x140002e1b  cmp     eax, ebx
0x140002e1d  jnb     loc_140003120
0x140002e23  mov     edi, 8007000Eh
0x140002e28  jmp     loc_140002B25
0x140002e2d  mov     [rsp+2B0h+arg_0], rsi
0x140002e35  lea     esi, [rax+0Ah]
0x140002e38  mov     [rsp+2B0h+arg_10], rdi
0x140002e40  mov     eax, 0FFFFFFFFh
0x140002e45  mov     edi, esi
0x140002e47  add     rdi, rdi
0x140002e4a  mov     [rsp+2B0h+var_264], esi
0x140002e4e  mov     [rsp+2B0h+var_24C], esi
0x140002e52  cmp     rdi, rax
0x140002e55  ja      loc_140002B20
0x140002e5b  jmp     loc_140002B52
0x140002e60  lea     ecx, [rdi+1]
0x140002e63  cmp     ecx, edi
0x140002e65  jb      loc_140002B20
0x140002e6b  mov     eax, ecx
0x140002e6d  imul    rdx, rax, 32h ; '2'
0x140002e71  mov     eax, 0FFFFFFFFh
0x140002e76  mov     [rsp+2B0h+var_24C], ecx
0x140002e7a  cmp     rdx, rax
0x140002e7d  ja      loc_140002B20
0x140002e83  mov     eax, 51EB851Fh
0x140002e88  mul     edx
0x140002e8a  shr     edx, 5; unsigned __int64
0x140002e8d  lea     eax, [rdx+rcx]
0x140002e90  mov     [rsp+2B0h+var_264], eax
0x140002e94  cmp     eax, ecx
0x140002e96  jb      loc_140002B20
0x140002e9c  mov     ecx, eax; unsigned __int64
0x140002e9e  lea     r8, [rsp+2B0h+dwBytes]; unsigned __int64 *
0x140002ea3  mov     [rsp+2B0h+var_24C], eax
0x140002ea7  mov     [rsp+2B0h+dwBytes], 0
0x140002eb0  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x140002eb5  mov     edi, eax
0x140002eb7  test    eax, eax
0x140002eb9  js      loc_140002B25
0x140002ebf  call    cs:__imp_GetProcessHeap
0x140002ec5  mov     r9, [rsp+2B0h+dwBytes]; dwBytes
0x140002eca  mov     r8, r12; lpMem
0x140002ecd  mov     rcx, rax; hHeap
0x140002ed0  xor     edx, edx; dwFlags
0x140002ed2  call    cs:__imp_HeapReAlloc
0x140002ed8  test    rax, rax
0x140002edb  jz      loc_14000303F
0x140002ee1  mov     edi, [rsp+2B0h+var_264]
0x140002ee5  mov     r12, rax
0x140002ee8  mov     [rsp+2B0h+var_258], rax
0x140002eed  mov     ecx, 0Ah
0x140002ef2  mov     edx, 1
0x140002ef7  mov     r8d, 0Dh
0x140002efd  jmp     loc_140002BCD
0x140002f02  lea     ecx, [rsi+1]
0x140002f05  cmp     ecx, esi
0x140002f07  jb      loc_140002B20
0x140002f0d  mov     eax, ecx
0x140002f0f  mov     r13d, 0FFFFFFFFh
0x140002f15  imul    rdx, rax, 32h ; '2'
0x140002f19  cmp     rdx, r13
0x140002f1c  ja      loc_140002B20
0x140002f22  mov     eax, 51EB851Fh
0x140002f27  mul     edx
0x140002f29  shr     edx, 5; unsigned __int64
0x140002f2c  lea     esi, [rdx+rcx]
0x140002f2f  cmp     esi, ecx
0x140002f31  jb      loc_140002B20
0x140002f37  xor     r14d, r14d
0x140002f3a  mov     ecx, esi; unsigned __int64
0x140002f3c  lea     r8, [rsp+2B0h+dwBytes]; unsigned __int64 *
0x140002f41  mov     [rsp+2B0h+dwBytes], r14
  ... truncated ...
```
