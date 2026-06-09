# CWriter::FlushBufferToDisk(void)

- ea: `0x18002a500`
- end: `0x18002a65d`
- name: `?FlushBufferToDisk@CWriter@@AEAAJXZ`
- size: `349`
- prototype: `__int64 __fastcall(CWriter *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, service_task`

## callers

- `0x18002ac94`

## callees

- `0x18002a500`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x18002a552`
- `KERNEL32!WideCharToMultiByte` at `0x18002a586`
- `KERNEL32!WideCharToMultiByte` at `0x18002a5dc`
- `KERNEL32!WideCharToMultiByte` at `0x18002a552`
- `KERNEL32!WideCharToMultiByte` at `0x18002a586`
- `KERNEL32!WideCharToMultiByte` at `0x18002a5dc`
- `KERNEL32!WriteFile` at `0x18002a617`
- `KERNEL32!WriteFile` at `0x18002a617`
- `KERNEL32!GetLastError` at `0x18002a5e6`
- `KERNEL32!GetLastError` at `0x18002a621`
- `KERNEL32!GetLastError` at `0x18002a5e6`
- `KERNEL32!GetLastError` at `0x18002a621`
- `ole32!CoTaskMemFree` at `0x18002a648`
- `ole32!CoTaskMemFree` at `0x18002a648`
- `ole32!CoTaskMemAlloc` at `0x18002a5a0`
- `ole32!CoTaskMemAlloc` at `0x18002a5a0`

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
  v9 = (CHAR *)CoTaskMemAlloc(v8);
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
    CoTaskMemFree(v5);
  return v3;
}

```

## disassembly

```asm
0x18002a500  mov     rax, rsp
0x18002a503  push    rbx
0x18002a504  push    rbp
0x18002a505  push    rsi
0x18002a506  push    rdi
0x18002a507  push    r14
0x18002a509  push    r15
0x18002a50b  sub     rsp, 48h
0x18002a50f  mov     r9d, [rcx+10h]
0x18002a513  lea     r14, [rcx+8014h]
0x18002a51a  xor     ebx, ebx
0x18002a51c  mov     rsi, rcx
0x18002a51f  mov     [rax+8], ebx
0x18002a522  mov     rdi, r14
0x18002a525  test    r9d, r9d
0x18002a528  jz      loc_18002A63B
0x18002a52e  mov     [rax-40h], rbx
0x18002a532  lea     r15, [rcx+14h]
0x18002a536  mov     [rax-48h], rbx
0x18002a53a  mov     r8, r15; lpWideCharStr
0x18002a53d  mov     dword ptr [rax-50h], 8000h
0x18002a544  xor     edx, edx; dwFlags
0x18002a546  shr     r9d, 1; cchWideChar
0x18002a549  mov     ecx, 0FDE9h; CodePage
0x18002a54e  mov     [rax-58h], r14
0x18002a552  call    cs:__imp_WideCharToMultiByte
0x18002a558  mov     ebp, eax
0x18002a55a  test    eax, eax
0x18002a55c  jnz     loc_18002A5FD
0x18002a562  mov     r9d, [rsi+10h]
0x18002a566  mov     r8, r15; lpWideCharStr
0x18002a569  mov     [rsp+78h+lpUsedDefaultChar], rbx; lpUsedDefaultChar
0x18002a56e  xor     edx, edx; dwFlags
0x18002a570  mov     [rsp+78h+lpDefaultChar], rbx; lpDefaultChar
0x18002a575  mov     ecx, 0FDE9h; CodePage
0x18002a57a  shr     r9d, 1; cchWideChar
0x18002a57d  mov     [rsp+78h+cbMultiByte], ebx; cbMultiByte
0x18002a581  mov     [rsp+78h+lpMultiByteStr], rbx; lpMultiByteStr
0x18002a586  call    cs:__imp_WideCharToMultiByte
0x18002a58c  movsxd  rbp, eax
0x18002a58f  test    eax, eax
0x18002a591  jnz     short loc_18002A59D
0x18002a593  mov     ebx, 80004005h
0x18002a598  jmp     loc_18002A63B
0x18002a59d  mov     rcx, rbp; cb
0x18002a5a0  call    cs:__imp_CoTaskMemAlloc
0x18002a5a6  mov     rdi, rax
0x18002a5a9  test    rax, rax
0x18002a5ac  jnz     short loc_18002A5B8
0x18002a5ae  mov     ebx, 8007000Eh
0x18002a5b3  jmp     loc_18002A64E
0x18002a5b8  mov     r9d, [rsi+10h]
0x18002a5bc  mov     r8, r15; lpWideCharStr
0x18002a5bf  mov     [rsp+78h+lpUsedDefaultChar], rbx; lpUsedDefaultChar
0x18002a5c4  xor     edx, edx; dwFlags
0x18002a5c6  mov     [rsp+78h+lpDefaultChar], rbx; lpDefaultChar
0x18002a5cb  mov     ecx, 0FDE9h; CodePage
0x18002a5d0  shr     r9d, 1; cchWideChar
0x18002a5d3  mov     [rsp+78h+cbMultiByte], ebp; cbMultiByte
0x18002a5d7  mov     [rsp+78h+lpMultiByteStr], rax; lpMultiByteStr
0x18002a5dc  call    cs:__imp_WideCharToMultiByte
0x18002a5e2  test    eax, eax
0x18002a5e4  jnz     short loc_18002A5FD
0x18002a5e6  call    cs:__imp_GetLastError
0x18002a5ec  mov     ebx, eax
0x18002a5ee  test    eax, eax
0x18002a5f0  jle     short loc_18002A640
0x18002a5f2  movzx   ebx, ax
0x18002a5f5  or      ebx, 80070000h
0x18002a5fb  jmp     short loc_18002A640
0x18002a5fd  mov     rcx, [rsi+10038h]; hFile
0x18002a604  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002a60c  mov     r8d, ebp; nNumberOfBytesToWrite
0x18002a60f  mov     [rsp+78h+lpMultiByteStr], rbx; lpOverlapped
0x18002a614  mov     rdx, rdi; lpBuffer
0x18002a617  call    cs:__imp_WriteFile
0x18002a61d  test    eax, eax
0x18002a61f  jnz     short loc_18002A638
0x18002a621  call    cs:__imp_GetLastError
0x18002a627  mov     ebx, eax
0x18002a629  test    eax, eax
0x18002a62b  jle     short loc_18002A63B
0x18002a62d  movzx   ebx, ax
0x18002a630  or      ebx, 80070000h
0x18002a636  jmp     short loc_18002A63B
0x18002a638  mov     [rsi+10h], ebx
0x18002a63b  test    rdi, rdi
0x18002a63e  jz      short loc_18002A64E
0x18002a640  cmp     rdi, r14
0x18002a643  jz      short loc_18002A64E
0x18002a645  mov     rcx, rdi; pv
0x18002a648  call    cs:__imp_CoTaskMemFree
0x18002a64e  mov     eax, ebx
0x18002a650  add     rsp, 48h
0x18002a654  pop     r15
0x18002a656  pop     r14
0x18002a658  pop     rdi
0x18002a659  pop     rsi
0x18002a65a  pop     rbp
0x18002a65b  pop     rbx
0x18002a65c  retn
```
