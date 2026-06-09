# CWriter::FlushBufferToDisk(void)

- ea: `0x18002d868`
- end: `0x18002d9c3`
- name: `?FlushBufferToDisk@CWriter@@AEAAJXZ`
- size: `347`
- prototype: `__int64 __fastcall(CWriter *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180006420`
- `0x180006d08`

## callees

- `0x1800089c8`
- `0x180008a08`
- `0x18002d868`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18002d97e`
- `KERNEL32!WriteFile` at `0x18002d97e`
- `KERNEL32!GetLastError` at `0x18002d94d`
- `KERNEL32!GetLastError` at `0x18002d988`
- `KERNEL32!GetLastError` at `0x18002d94d`
- `KERNEL32!GetLastError` at `0x18002d988`
- `KERNEL32!WideCharToMultiByte` at `0x18002d8ba`
- `KERNEL32!WideCharToMultiByte` at `0x18002d8ee`
- `KERNEL32!WideCharToMultiByte` at `0x18002d943`
- `KERNEL32!WideCharToMultiByte` at `0x18002d8ba`
- `KERNEL32!WideCharToMultiByte` at `0x18002d8ee`
- `KERNEL32!WideCharToMultiByte` at `0x18002d943`

## pseudocode

```c
__int64 __fastcall CWriter::FlushBufferToDisk(CWriter *this)
{
  unsigned int v1; // r9d
  CHAR *lpMultiByteStr; // r14
  unsigned int v3; // ebx
  CHAR *v5; // rdi
  const WCHAR *v6; // r15
  int cbMultiByte; // ebp
  int v8; // eax
  CHAR *v9; // rax
  signed int v10; // eax
  signed int LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp+8h] BYREF

  v1 = *((_DWORD *)this + 4);
  lpMultiByteStr = (char *)this + 32788;
  v3 = 0;
  NumberOfBytesWritten = 0;
  v5 = (char *)this + 32788;
  if ( !v1 )
    goto LABEL_14;
  v6 = (const WCHAR *)((char *)this + 20);
  cbMultiByte = WideCharToMultiByte(0xFDE9u, 0, (LPCWCH)this + 10, v1 >> 1, lpMultiByteStr, 0x8000, 0, 0);
  if ( cbMultiByte )
    goto LABEL_20;
  v8 = WideCharToMultiByte(0xFDE9u, 0, v6, *((_DWORD *)this + 4) >> 1, 0, 0, 0, 0);
  cbMultiByte = v8;
  if ( !v8 )
  {
    v3 = -2147467259;
    goto LABEL_14;
  }
  v9 = (CHAR *)operator new(v8);
  v5 = v9;
  if ( !v9 )
    return (unsigned int)-2147024882;
  if ( WideCharToMultiByte(0xFDE9u, 0, v6, *((_DWORD *)this + 4) >> 1, v9, cbMultiByte, 0, 0) )
  {
LABEL_20:
    if ( WriteFile(*((HANDLE *)this + 8199), v5, cbMultiByte, &NumberOfBytesWritten, 0) )
    {
      *((_DWORD *)this + 4) = 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
LABEL_14:
    if ( !v5 )
      return v3;
    goto LABEL_15;
  }
  v10 = GetLastError();
  v3 = v10;
  if ( v10 > 0 )
    v3 = (unsigned __int16)v10 | 0x80070000;
LABEL_15:
  if ( v5 != lpMultiByteStr )
    operator delete(v5);
  return v3;
}

```

## disassembly

```asm
0x18002d868  mov     rax, rsp
0x18002d86b  push    rbx
0x18002d86c  push    rbp
0x18002d86d  push    rsi
0x18002d86e  push    rdi
0x18002d86f  push    r14
0x18002d871  push    r15
0x18002d873  sub     rsp, 48h
0x18002d877  mov     r9d, [rcx+10h]
0x18002d87b  lea     r14, [rcx+8014h]
0x18002d882  xor     ebx, ebx
0x18002d884  mov     rsi, rcx
0x18002d887  mov     [rax+8], ebx
0x18002d88a  mov     rdi, r14
0x18002d88d  test    r9d, r9d
0x18002d890  jz      loc_18002D9A2
0x18002d896  mov     [rax-40h], rbx
0x18002d89a  lea     r15, [rcx+14h]
0x18002d89e  mov     [rax-48h], rbx
0x18002d8a2  mov     r8, r15; lpWideCharStr
0x18002d8a5  mov     dword ptr [rax-50h], 8000h
0x18002d8ac  xor     edx, edx; dwFlags
0x18002d8ae  shr     r9d, 1; cchWideChar
0x18002d8b1  mov     ecx, 0FDE9h; CodePage
0x18002d8b6  mov     [rax-58h], r14
0x18002d8ba  call    cs:__imp_WideCharToMultiByte
0x18002d8c0  mov     ebp, eax
0x18002d8c2  test    eax, eax
0x18002d8c4  jnz     loc_18002D964
0x18002d8ca  mov     r9d, [rsi+10h]
0x18002d8ce  mov     r8, r15; lpWideCharStr
0x18002d8d1  mov     [rsp+78h+lpUsedDefaultChar], rbx; lpUsedDefaultChar
0x18002d8d6  xor     edx, edx; dwFlags
0x18002d8d8  mov     [rsp+78h+lpDefaultChar], rbx; lpDefaultChar
0x18002d8dd  mov     ecx, 0FDE9h; CodePage
0x18002d8e2  shr     r9d, 1; cchWideChar
0x18002d8e5  mov     [rsp+78h+cbMultiByte], ebx; cbMultiByte
0x18002d8e9  mov     [rsp+78h+lpMultiByteStr], rbx; lpMultiByteStr
0x18002d8ee  call    cs:__imp_WideCharToMultiByte
0x18002d8f4  movsxd  rbp, eax
0x18002d8f7  test    eax, eax
0x18002d8f9  jnz     short loc_18002D905
0x18002d8fb  mov     ebx, 80004005h
0x18002d900  jmp     loc_18002D9A2
0x18002d905  mov     rcx, rbp; Size
0x18002d908  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002d90d  mov     rdi, rax
0x18002d910  test    rax, rax
0x18002d913  jnz     short loc_18002D91F
0x18002d915  mov     ebx, 8007000Eh
0x18002d91a  jmp     loc_18002D9B4
0x18002d91f  mov     r9d, [rsi+10h]
0x18002d923  mov     r8, r15; lpWideCharStr
0x18002d926  mov     [rsp+78h+lpUsedDefaultChar], rbx; lpUsedDefaultChar
0x18002d92b  xor     edx, edx; dwFlags
0x18002d92d  mov     [rsp+78h+lpDefaultChar], rbx; lpDefaultChar
0x18002d932  mov     ecx, 0FDE9h; CodePage
0x18002d937  shr     r9d, 1; cchWideChar
0x18002d93a  mov     [rsp+78h+cbMultiByte], ebp; cbMultiByte
0x18002d93e  mov     [rsp+78h+lpMultiByteStr], rax; lpMultiByteStr
0x18002d943  call    cs:__imp_WideCharToMultiByte
0x18002d949  test    eax, eax
0x18002d94b  jnz     short loc_18002D964
0x18002d94d  call    cs:__imp_GetLastError
0x18002d953  mov     ebx, eax
0x18002d955  test    eax, eax
0x18002d957  jle     short loc_18002D9A7
0x18002d959  movzx   ebx, ax
0x18002d95c  or      ebx, 80070000h
0x18002d962  jmp     short loc_18002D9A7
0x18002d964  mov     rcx, [rsi+10038h]; hFile
0x18002d96b  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002d973  mov     r8d, ebp; nNumberOfBytesToWrite
0x18002d976  mov     [rsp+78h+lpMultiByteStr], rbx; lpOverlapped
0x18002d97b  mov     rdx, rdi; lpBuffer
0x18002d97e  call    cs:__imp_WriteFile
0x18002d984  test    eax, eax
0x18002d986  jnz     short loc_18002D99F
0x18002d988  call    cs:__imp_GetLastError
0x18002d98e  mov     ebx, eax
0x18002d990  test    eax, eax
0x18002d992  jle     short loc_18002D9A2
0x18002d994  movzx   ebx, ax
0x18002d997  or      ebx, 80070000h
0x18002d99d  jmp     short loc_18002D9A2
0x18002d99f  mov     [rsi+10h], ebx
0x18002d9a2  test    rdi, rdi
0x18002d9a5  jz      short loc_18002D9B4
0x18002d9a7  cmp     rdi, r14
0x18002d9aa  jz      short loc_18002D9B4
0x18002d9ac  mov     rcx, rdi; Block
0x18002d9af  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002d9b4  mov     eax, ebx
0x18002d9b6  add     rsp, 48h
0x18002d9ba  pop     r15
0x18002d9bc  pop     r14
0x18002d9be  pop     rdi
0x18002d9bf  pop     rsi
0x18002d9c0  pop     rbp
0x18002d9c1  pop     rbx
0x18002d9c2  retn
```
