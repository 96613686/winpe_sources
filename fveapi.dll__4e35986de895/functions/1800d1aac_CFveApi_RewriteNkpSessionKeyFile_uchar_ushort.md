# CFveApi::RewriteNkpSessionKeyFile(uchar * *,ushort)

- ea: `0x1800d1aac`
- end: `0x1800d1d64`
- name: `?RewriteNkpSessionKeyFile@CFveApi@@AEAAJPEAPEAEG@Z`
- size: `696`
- prototype: `__int64 __fastcall(CFveApi *__hidden this, unsigned __int8 **, unsigned __int16)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180044470`

## callees

- `0x18006da20`
- `0x1800d1aac`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d1bca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d1bca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d1d13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d1d28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180128775`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180128793`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d1d13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d1d28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180128775`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180128793`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d1c18`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d1ce1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d1c18`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d1ce1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d1bb0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d1ca6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d1bb0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d1ca6`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800d1b71`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800d1c67`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800d1b71`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800d1c67`

## pseudocode

```c
__int64 __fastcall CFveApi::RewriteNkpSessionKeyFile(CFveApi *this, unsigned __int8 **a2, unsigned __int16 a3)
{
  DWORD v3; // r12d
  __int64 FileW; // rsi
  __int64 v6; // rdi
  int SystemVolume; // ebx
  signed int LastError; // eax
  unsigned __int16 i; // bx
  HANDLE v10; // rax
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp-460h] BYREF
  int Buffer; // [rsp+5Ch] [rbp-45Ch] BYREF
  WCHAR pszPathOut[264]; // [rsp+60h] [rbp-458h] BYREF
  WCHAR pszPathIn[264]; // [rsp+270h] [rbp-248h] BYREF

  v3 = a3;
  Buffer = 0;
  memset_0(pszPathIn, 0, 0x208u);
  memset_0(pszPathOut, 0, 0x208u);
  FileW = -1;
  v6 = -1;
  NumberOfBytesWritten = 0;
  if ( !a2 || !(_WORD)v3 )
  {
    SystemVolume = -2147024809;
    goto LABEL_20;
  }
  SystemVolume = GetSystemVolume(0x104u, pszPathIn);
  if ( SystemVolume >= 0 )
  {
    SystemVolume = PathCchCombine(pszPathOut, 0x104u, pszPathIn, L"EFI\\Microsoft\\Boot\\sesskeys.bin");
    if ( SystemVolume >= 0 )
    {
      FileW = (__int64)CreateFileW(pszPathOut, 0x40000000u, 0, 0, 2u, 6u, 0);
      if ( FileW == -1 )
        goto LABEL_6;
      for ( i = 0; i < 5u; ++i )
      {
        NumberOfBytesWritten = 0;
        if ( !WriteFile((HANDLE)FileW, a2[i], v3, &NumberOfBytesWritten, 0) )
          goto LABEL_6;
        if ( NumberOfBytesWritten != v3 )
          goto LABEL_12;
      }
      memset_0(pszPathOut, 0, 0x208u);
      SystemVolume = PathCchCombine(pszPathOut, 0x104u, pszPathIn, L"EFI\\Microsoft\\Boot\\keypos.bin");
      if ( SystemVolume >= 0 )
      {
        v10 = CreateFileW(pszPathOut, 0x40000000u, 0, 0, 2u, 6u, 0);
        v6 = (__int64)v10;
        if ( v10 == (HANDLE)-1LL || (NumberOfBytesWritten = 0, !WriteFile(v10, &Buffer, 4u, &NumberOfBytesWritten, 0)) )
        {
LABEL_6:
          LastError = GetLastError();
          SystemVolume = LastError;
          if ( LastError > 0 )
            SystemVolume = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_20;
        }
        if ( NumberOfBytesWritten != 4 )
LABEL_12:
          SystemVolume = -2147418113;
      }
    }
  }
LABEL_20:
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( v6 != -1 )
    CloseHandle((HANDLE)v6);
  return (unsigned int)SystemVolume;
}

```

## disassembly

```asm
0x1800d1aac  mov     [rsp+arg_0], rbx
0x1800d1ab1  mov     [rsp+arg_18], rsi
0x1800d1ab6  push    rdi
0x1800d1ab7  push    r12
0x1800d1ab9  push    r13
0x1800d1abb  push    r14
0x1800d1abd  push    r15
0x1800d1abf  sub     rsp, 490h
0x1800d1ac6  mov     rax, cs:__security_cookie
0x1800d1acd  xor     rax, rsp
0x1800d1ad0  mov     [rsp+4B8h+var_38], rax
0x1800d1ad8  movzx   r12d, r8w
0x1800d1adc  mov     r15, rdx
0x1800d1adf  xor     r13d, r13d
0x1800d1ae2  mov     [rsp+4B8h+Buffer], r13d
0x1800d1ae7  mov     ebx, 208h
0x1800d1aec  mov     r8d, ebx; Size
0x1800d1aef  xor     edx, edx; Val
0x1800d1af1  lea     rcx, [rsp+4B8h+pszPathIn]; void *
0x1800d1af9  call    memset_0
0x1800d1afe  mov     r8d, ebx; Size
0x1800d1b01  xor     edx, edx; Val
0x1800d1b03  lea     rcx, [rsp+4B8h+pszPathOut]; void *
0x1800d1b08  call    memset_0
0x1800d1b0d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800d1b11  mov     [rsp+4B8h+var_470], rsi
0x1800d1b16  or      rdi, rsi
0x1800d1b19  mov     [rsp+4B8h+var_468], rdi
0x1800d1b1e  mov     [rsp+4B8h+NumberOfBytesWritten], r13d
0x1800d1b23  test    r15, r15
0x1800d1b26  jz      loc_1800D1D01
0x1800d1b2c  test    r12w, r12w
0x1800d1b30  jz      loc_1800D1D01
0x1800d1b36  lea     rdx, [rsp+4B8h+pszPathIn]; unsigned __int16 *
0x1800d1b3e  mov     r14d, 104h
0x1800d1b44  mov     ecx, r14d; unsigned int
0x1800d1b47  call    ?GetSystemVolume@@YAJKPEAG@Z; GetSystemVolume(ulong,ushort *)
0x1800d1b4c  mov     ebx, eax
0x1800d1b4e  mov     [rsp+4B8h+var_478], eax
0x1800d1b52  test    eax, eax
0x1800d1b54  js      loc_1800D1D0A
0x1800d1b5a  lea     r9, aEfiMicrosoftBo_0; "EFI\\Microsoft\\Boot\\sesskeys.bin"
0x1800d1b61  lea     r8, [rsp+4B8h+pszPathIn]; pszPathIn
0x1800d1b69  mov     edx, r14d; cchPathOut
0x1800d1b6c  lea     rcx, [rsp+4B8h+pszPathOut]; pszPathOut
0x1800d1b71  call    cs:__imp_PathCchCombine
0x1800d1b78  nop     dword ptr [rax+rax+00h]
0x1800d1b7d  mov     ebx, eax
0x1800d1b7f  mov     [rsp+4B8h+var_478], eax
0x1800d1b83  test    eax, eax
0x1800d1b85  js      loc_1800D1D0A
0x1800d1b8b  mov     [rsp+4B8h+hTemplateFile], r13; hTemplateFile
0x1800d1b90  mov     [rsp+4B8h+dwFlagsAndAttributes], 6; dwFlagsAndAttributes
0x1800d1b98  mov     [rsp+4B8h+dwCreationDisposition], 2; dwCreationDisposition
0x1800d1ba0  xor     r9d, r9d; lpSecurityAttributes
0x1800d1ba3  xor     r8d, r8d; dwShareMode
0x1800d1ba6  mov     edx, 40000000h; dwDesiredAccess
0x1800d1bab  lea     rcx, [rsp+4B8h+pszPathOut]; lpFileName
0x1800d1bb0  call    cs:__imp_CreateFileW
0x1800d1bb7  nop     dword ptr [rax+rax+00h]
0x1800d1bbc  mov     rsi, rax
0x1800d1bbf  mov     [rsp+4B8h+var_470], rax
0x1800d1bc4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800d1bc8  jnz     short loc_1800D1BEE
0x1800d1bca  call    cs:__imp_GetLastError
0x1800d1bd1  nop     dword ptr [rax+rax+00h]
0x1800d1bd6  mov     ebx, eax
0x1800d1bd8  test    eax, eax
0x1800d1bda  jle     loc_1800D1D06
0x1800d1be0  movzx   ebx, ax
0x1800d1be3  or      ebx, 80070000h
0x1800d1be9  jmp     loc_1800D1D06
0x1800d1bee  mov     ebx, r13d
0x1800d1bf1  mov     [rsp+4B8h+var_474], bx
0x1800d1bf6  cmp     bx, 5
0x1800d1bfa  jnb     short loc_1800D1C3E
0x1800d1bfc  mov     [rsp+4B8h+NumberOfBytesWritten], r13d
0x1800d1c01  movzx   edx, bx
0x1800d1c04  mov     qword ptr [rsp+4B8h+dwCreationDisposition], r13; lpOverlapped
0x1800d1c09  lea     r9, [rsp+4B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800d1c0e  mov     r8d, r12d; nNumberOfBytesToWrite
0x1800d1c11  mov     rdx, [r15+rdx*8]; lpBuffer
0x1800d1c15  mov     rcx, rsi; hFile
0x1800d1c18  call    cs:__imp_WriteFile
0x1800d1c1f  nop     dword ptr [rax+rax+00h]
0x1800d1c24  test    eax, eax
0x1800d1c26  jz      short loc_1800D1BCA
0x1800d1c28  cmp     [rsp+4B8h+NumberOfBytesWritten], r12d
0x1800d1c2d  jz      short loc_1800D1C39
0x1800d1c2f  mov     ebx, 8000FFFFh
0x1800d1c34  jmp     loc_1800D1D06
0x1800d1c39  inc     bx
0x1800d1c3c  jmp     short loc_1800D1BF1
0x1800d1c3e  xor     edx, edx; Val
0x1800d1c40  mov     r8d, 208h; Size
0x1800d1c46  lea     rcx, [rsp+4B8h+pszPathOut]; void *
0x1800d1c4b  call    memset_0
0x1800d1c50  lea     r9, aEfiMicrosoftBo; "EFI\\Microsoft\\Boot\\keypos.bin"
0x1800d1c57  lea     r8, [rsp+4B8h+pszPathIn]; pszPathIn
0x1800d1c5f  mov     rdx, r14; cchPathOut
0x1800d1c62  lea     rcx, [rsp+4B8h+pszPathOut]; pszPathOut
0x1800d1c67  call    cs:__imp_PathCchCombine
0x1800d1c6e  nop     dword ptr [rax+rax+00h]
0x1800d1c73  mov     ebx, eax
0x1800d1c75  mov     [rsp+4B8h+var_478], eax
0x1800d1c79  test    eax, eax
0x1800d1c7b  js      loc_1800D1D0A
0x1800d1c81  mov     [rsp+4B8h+hTemplateFile], r13; hTemplateFile
0x1800d1c86  mov     [rsp+4B8h+dwFlagsAndAttributes], 6; dwFlagsAndAttributes
0x1800d1c8e  mov     [rsp+4B8h+dwCreationDisposition], 2; dwCreationDisposition
0x1800d1c96  xor     r9d, r9d; lpSecurityAttributes
0x1800d1c99  xor     r8d, r8d; dwShareMode
0x1800d1c9c  mov     edx, 40000000h; dwDesiredAccess
0x1800d1ca1  lea     rcx, [rsp+4B8h+pszPathOut]; lpFileName
0x1800d1ca6  call    cs:__imp_CreateFileW
0x1800d1cad  nop     dword ptr [rax+rax+00h]
0x1800d1cb2  mov     rdi, rax
0x1800d1cb5  mov     [rsp+4B8h+var_468], rax
0x1800d1cba  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800d1cbe  jz      loc_1800D1BCA
0x1800d1cc4  mov     [rsp+4B8h+NumberOfBytesWritten], r13d
0x1800d1cc9  mov     qword ptr [rsp+4B8h+dwCreationDisposition], r13; lpOverlapped
0x1800d1cce  lea     r9, [rsp+4B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800d1cd3  mov     r8d, 4; nNumberOfBytesToWrite
0x1800d1cd9  lea     rdx, [rsp+4B8h+Buffer]; lpBuffer
0x1800d1cde  mov     rcx, rax; hFile
0x1800d1ce1  call    cs:__imp_WriteFile
0x1800d1ce8  nop     dword ptr [rax+rax+00h]
0x1800d1ced  test    eax, eax
0x1800d1cef  jz      loc_1800D1BCA
0x1800d1cf5  cmp     [rsp+4B8h+NumberOfBytesWritten], 4
0x1800d1cfa  jz      short loc_1800D1D0A
0x1800d1cfc  jmp     loc_1800D1C2F
0x1800d1d01  mov     ebx, 80070057h
0x1800d1d06  mov     [rsp+4B8h+var_478], ebx
0x1800d1d0a  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800d1d0e  jz      short loc_1800D1D1F
0x1800d1d10  mov     rcx, rsi; hObject
0x1800d1d13  call    cs:__imp_CloseHandle
0x1800d1d1a  nop     dword ptr [rax+rax+00h]
0x1800d1d1f  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800d1d23  jz      short loc_1800D1D34
0x1800d1d25  mov     rcx, rdi; hObject
0x1800d1d28  call    cs:__imp_CloseHandle
0x1800d1d2f  nop     dword ptr [rax+rax+00h]
0x1800d1d34  mov     eax, ebx
0x1800d1d36  mov     rcx, [rsp+4B8h+var_38]
0x1800d1d3e  xor     rcx, rsp; StackCookie
0x1800d1d41  call    __security_check_cookie
0x1800d1d46  lea     r11, [rsp+4B8h+var_28]
0x1800d1d4e  mov     rbx, [r11+30h]
0x1800d1d52  mov     rsi, [r11+48h]
0x1800d1d56  mov     rsp, r11
0x1800d1d59  pop     r15
0x1800d1d5b  pop     r14
0x1800d1d5d  pop     r13
0x1800d1d5f  pop     r12
0x1800d1d61  pop     rdi
0x1800d1d62  retn
0x180128762  push    rbp
0x180128764  sub     rsp, 40h
0x180128768  mov     rbp, rdx
0x18012876b  mov     rcx, [rbp+48h]; hObject
0x18012876f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180128773  jz      short loc_180128789
0x180128775  call    cs:__imp_CloseHandle
0x18012877c  nop     dword ptr [rax+rax+00h]
0x180128781  mov     qword ptr [rbp+48h], 0FFFFFFFFFFFFFFFFh
0x180128789  mov     rcx, [rbp+50h]; hObject
0x18012878d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180128791  jz      short loc_1801287A7
0x180128793  call    cs:__imp_CloseHandle
0x18012879a  nop     dword ptr [rax+rax+00h]
0x18012879f  mov     qword ptr [rbp+50h], 0FFFFFFFFFFFFFFFFh
0x1801287a7  add     rsp, 40h
0x1801287ab  pop     rbp
0x1801287ac  retn
```
