# SafeCreateTempFile

- ea: `0x140010a20`
- end: `0x140010d5e`
- name: `SafeCreateTempFile`
- size: `830`
- prototype: `__int64 __usercall@<rax>(LPCWCH lpWideCharStr@<rcx>, LPCVOID lpBuffer@<rdx>, LPCSTR lpPathName)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140002260`
- `0x140010d64`

## callees

- `0x140009c70`
- `0x140009cb0`
- `0x140010a20`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x140010cbc`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140010cbc`
- `OLEAUT32!__imp_SysFreeString` at `0x140010d07`
- `OLEAUT32!__imp_SysFreeString` at `0x140010d07`
- `KERNEL32!MultiByteToWideChar` at `0x140010ca7`
- `KERNEL32!MultiByteToWideChar` at `0x140010ce5`
- `KERNEL32!MultiByteToWideChar` at `0x140010ca7`
- `KERNEL32!MultiByteToWideChar` at `0x140010ce5`
- `KERNEL32!CloseHandle` at `0x140010d3e`
- `KERNEL32!CloseHandle` at `0x140010d3e`
- `KERNEL32!WideCharToMultiByte` at `0x140010a8c`
- `KERNEL32!WideCharToMultiByte` at `0x140010ba9`
- `KERNEL32!WideCharToMultiByte` at `0x140010a8c`
- `KERNEL32!WideCharToMultiByte` at `0x140010ba9`
- `KERNEL32!GetTempFileNameA` at `0x140010b4b`
- `KERNEL32!GetTempFileNameA` at `0x140010b4b`
- `KERNEL32!GetLastError` at `0x140010a98`
- `KERNEL32!GetLastError` at `0x140010af7`
- `KERNEL32!GetLastError` at `0x140010b57`
- `KERNEL32!GetLastError` at `0x140010be9`
- `KERNEL32!GetLastError` at `0x140010cef`
- `KERNEL32!GetLastError` at `0x140010a98`
- `KERNEL32!GetLastError` at `0x140010af7`
- `KERNEL32!GetLastError` at `0x140010b57`
- `KERNEL32!GetLastError` at `0x140010be9`
- `KERNEL32!GetLastError` at `0x140010cef`
- `KERNEL32!WriteFile` at `0x140010c35`
- `KERNEL32!WriteFile` at `0x140010c5b`
- `KERNEL32!WriteFile` at `0x140010c35`
- `KERNEL32!WriteFile` at `0x140010c5b`
- `KERNEL32!FlushFileBuffers` at `0x140010c6c`
- `KERNEL32!FlushFileBuffers` at `0x140010c6c`
- `KERNEL32!GetTempPath2A` at `0x140010aba`
- `KERNEL32!GetTempPath2A` at `0x140010aed`
- `KERNEL32!GetTempPath2A` at `0x140010aba`
- `KERNEL32!GetTempPath2A` at `0x140010aed`
- `KERNEL32!CreateFileA` at `0x140010bd7`
- `KERNEL32!CreateFileA` at `0x140010bd7`

## pseudocode

```c
__int64 __fastcall SafeCreateTempFile(LPCWCH lpWideCharStr, _WORD *lpBuffer, int a3, _QWORD *a4, CHAR *lpPathName)
{
  CHAR *v5; // r15
  void *v6; // rdi
  int v10; // ebp
  __int64 v11; // rbx
  signed int LastError; // eax
  unsigned int v13; // ebx
  int TempPath2A; // eax
  unsigned int v15; // r14d
  const CHAR *v16; // rax
  int v17; // eax
  signed int v18; // eax
  unsigned int v19; // r14d
  CHAR *v20; // rax
  CHAR *v21; // rbp
  signed int v22; // eax
  __int64 v23; // rax
  HANDLE FileA; // rax
  signed int v25; // eax
  UINT v26; // eax
  int v27; // r14d
  WCHAR *v28; // rax
  OLECHAR *v29; // rsi
  signed int v30; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-48h] BYREF
  __int16 Buffer; // [rsp+90h] [rbp+8h] BYREF
  _QWORD *v34; // [rsp+A8h] [rbp+20h]

  v34 = a4;
  v5 = lpPathName;
  v6 = 0;
  NumberOfBytesWritten = 0;
  *a4 = 0;
  Buffer = -257;
  v10 = 0;
  if ( v5 )
    *(_QWORD *)v5 = 0;
  v11 = -1;
  if ( lpWideCharStr && (v10 = WideCharToMultiByte(0, 0, lpWideCharStr, -1, 0, 0, 0, 0)) == 0
    || (TempPath2A = GetTempPath2A(0, 0)) == 0 )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return v13;
  }
  v15 = TempPath2A + 1;
  v16 = (const CHAR *)operator new((unsigned int)(TempPath2A + 1));
  lpPathName = (CHAR *)v16;
  if ( !v16 )
    return (unsigned int)-2147024882;
  v17 = GetTempPath2A(v15, v16);
  if ( !v17 )
  {
    v18 = GetLastError();
    v13 = v18;
    if ( v18 > 0 )
      v13 = (unsigned __int16)v18 | 0x80070000;
    goto LABEL_45;
  }
  v19 = v10 + v17 + 15;
  v20 = (CHAR *)operator new(v19);
  v21 = v20;
  if ( !v20 )
  {
    v13 = -2147024882;
    goto LABEL_45;
  }
  if ( !GetTempFileNameA(lpPathName, "wsh", 0, v20) )
    goto LABEL_16;
  if ( lpWideCharStr )
  {
    v23 = -1;
    do
      ++v23;
    while ( v21[v23] );
    if ( !WideCharToMultiByte(0, 0, lpWideCharStr, -1, &v21[(unsigned int)v23], v19 - v23, 0, 0) )
      goto LABEL_16;
  }
  FileA = CreateFileA(v21, 0xC0000000, 0, 0, 2u, 0x4002100u, 0);
  if ( FileA != (HANDLE)-1LL )
    v6 = FileA;
  if ( !v6 )
  {
    v25 = GetLastError();
    v13 = v25;
    if ( v25 > 0 )
      v13 = (unsigned __int16)v25 | 0x80070000;
    v6 = 0;
    goto LABEL_44;
  }
  if ( a3 > 0
    && (*lpBuffer != Buffer && !WriteFile(v6, &Buffer, 2u, &NumberOfBytesWritten, 0)
     || !WriteFile(v6, lpBuffer, 2 * a3, &NumberOfBytesWritten, 0)
     || !FlushFileBuffers(v6)) )
  {
    goto LABEL_16;
  }
  if ( !v5 )
  {
LABEL_43:
    *v34 = v6;
    v6 = 0;
    v13 = 0;
    goto LABEL_44;
  }
  do
    ++v11;
  while ( v21[v11] );
  v26 = MultiByteToWideChar(0, 0, v21, v11, 0, 0);
  v27 = v26;
  if ( !v26 )
  {
LABEL_16:
    v22 = GetLastError();
    v13 = v22;
    if ( v22 > 0 )
      v13 = (unsigned __int16)v22 | 0x80070000;
    goto LABEL_44;
  }
  v28 = SysAllocStringLen(0, v26);
  v29 = v28;
  if ( v28 )
  {
    if ( !MultiByteToWideChar(0, 0, v21, v11, v28, v27) )
    {
      v30 = GetLastError();
      v13 = v30;
      if ( v30 > 0 )
        v13 = (unsigned __int16)v30 | 0x80070000;
      SysFreeString(v29);
      goto LABEL_44;
    }
    *(_QWORD *)v5 = v29;
    goto LABEL_43;
  }
  v13 = -2147024882;
LABEL_44:
  operator delete(v21);
LABEL_45:
  operator delete(lpPathName);
  if ( v6 )
    CloseHandle(v6);
  return v13;
}

```

## disassembly

```asm
0x140010a20  mov     rax, rsp
0x140010a23  mov     [rax+10h], rbx
0x140010a27  mov     [rax+20h], r9
0x140010a2b  push    rbp
0x140010a2c  push    rsi
0x140010a2d  push    rdi
0x140010a2e  push    r12
0x140010a30  push    r13
0x140010a32  push    r14
0x140010a34  push    r15
0x140010a36  sub     rsp, 50h
0x140010a3a  mov     r15, [rsp+88h+lpPathName]
0x140010a42  xor     edi, edi
0x140010a44  mov     [rax-48h], edi
0x140010a47  mov     rsi, rcx
0x140010a4a  mov     [r9], rdi
0x140010a4d  mov     ecx, 0FEFFh
0x140010a52  mov     [rax+8], cx
0x140010a56  mov     r12d, r8d
0x140010a59  mov     r13, rdx
0x140010a5c  mov     ebp, edi
0x140010a5e  test    r15, r15
0x140010a61  jz      short loc_140010A66
0x140010a63  mov     [r15], rdi
0x140010a66  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140010a6a  test    rsi, rsi
0x140010a6d  jz      short loc_140010AB6
0x140010a6f  mov     [rsp+88h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x140010a74  mov     r9d, ebx; cchWideChar
0x140010a77  mov     [rsp+88h+lpDefaultChar], rdi; lpDefaultChar
0x140010a7c  mov     r8, rsi; lpWideCharStr
0x140010a7f  mov     [rsp+88h+cbMultiByte], edi; cbMultiByte
0x140010a83  xor     edx, edx; dwFlags
0x140010a85  xor     ecx, ecx; CodePage
0x140010a87  mov     [rsp+88h+lpMultiByteStr], rdi; lpMultiByteStr
0x140010a8c  call    cs:__imp_WideCharToMultiByte
0x140010a92  mov     ebp, eax
0x140010a94  test    eax, eax
0x140010a96  jnz     short loc_140010AB6
0x140010a98  call    cs:__imp_GetLastError
0x140010a9e  mov     ebx, eax
0x140010aa0  test    eax, eax
0x140010aa2  jle     loc_140010D44
0x140010aa8  movzx   ebx, ax
0x140010aab  or      ebx, 80070000h
0x140010ab1  jmp     loc_140010D44
0x140010ab6  xor     edx, edx
0x140010ab8  xor     ecx, ecx
0x140010aba  call    cs:__imp_GetTempPath2A
0x140010ac0  test    eax, eax
0x140010ac2  jz      short loc_140010A98
0x140010ac4  lea     r14d, [rax+1]
0x140010ac8  mov     ecx, r14d; Size
0x140010acb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140010ad0  mov     [rsp+88h+lpPathName], rax
0x140010ad8  test    rax, rax
0x140010adb  jnz     short loc_140010AE7
0x140010add  mov     ebx, 8007000Eh
0x140010ae2  jmp     loc_140010D44
0x140010ae7  mov     rdx, rax
0x140010aea  mov     ecx, r14d
0x140010aed  call    cs:__imp_GetTempPath2A
0x140010af3  test    eax, eax
0x140010af5  jnz     short loc_140010B15
0x140010af7  call    cs:__imp_GetLastError
0x140010afd  mov     ebx, eax
0x140010aff  test    eax, eax
0x140010b01  jle     loc_140010D29
0x140010b07  movzx   ebx, ax
0x140010b0a  or      ebx, 80070000h
0x140010b10  jmp     loc_140010D29
0x140010b15  lea     r14d, [rax+0Fh]
0x140010b19  add     r14d, ebp
0x140010b1c  mov     ecx, r14d; Size
0x140010b1f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140010b24  mov     rbp, rax
0x140010b27  test    rax, rax
0x140010b2a  jnz     short loc_140010B36
0x140010b2c  mov     ebx, 8007000Eh
0x140010b31  jmp     loc_140010D29
0x140010b36  mov     rcx, [rsp+88h+lpPathName]; lpPathName
0x140010b3e  lea     rdx, PrefixString; "wsh"
0x140010b45  mov     r9, rbp; lpTempFileName
0x140010b48  xor     r8d, r8d; uUnique
0x140010b4b  call    cs:__imp_GetTempFileNameA
0x140010b51  xor     ecx, ecx; CodePage
0x140010b53  test    eax, eax
0x140010b55  jnz     short loc_140010B75
0x140010b57  call    cs:__imp_GetLastError
0x140010b5d  mov     ebx, eax
0x140010b5f  test    eax, eax
0x140010b61  jle     loc_140010D21
0x140010b67  movzx   ebx, ax
0x140010b6a  or      ebx, 80070000h
0x140010b70  jmp     loc_140010D21
0x140010b75  test    rsi, rsi
0x140010b78  jz      short loc_140010BB3
0x140010b7a  mov     rax, rbx
0x140010b7d  inc     rax
0x140010b80  cmp     [rax+rbp], cl
0x140010b83  jnz     short loc_140010B7D
0x140010b85  sub     r14d, eax
0x140010b88  mov     [rsp+88h+lpUsedDefaultChar], rcx; lpUsedDefaultChar
0x140010b8d  mov     [rsp+88h+lpDefaultChar], rcx; lpDefaultChar
0x140010b92  mov     r9d, ebx; cchWideChar
0x140010b95  mov     eax, eax
0x140010b97  mov     r8, rsi; lpWideCharStr
0x140010b9a  add     rax, rbp
0x140010b9d  mov     [rsp+88h+cbMultiByte], r14d; cbMultiByte
0x140010ba2  xor     edx, edx; dwFlags
0x140010ba4  mov     [rsp+88h+lpMultiByteStr], rax; lpMultiByteStr
0x140010ba9  call    cs:__imp_WideCharToMultiByte
0x140010baf  test    eax, eax
0x140010bb1  jz      short loc_140010B57
0x140010bb3  mov     [rsp+88h+lpDefaultChar], rdi; hTemplateFile
0x140010bb8  mov     esi, 2
0x140010bbd  mov     [rsp+88h+cbMultiByte], 4002100h; dwFlagsAndAttributes
0x140010bc5  xor     r9d, r9d; lpSecurityAttributes
0x140010bc8  xor     r8d, r8d; dwShareMode
0x140010bcb  mov     dword ptr [rsp+88h+lpMultiByteStr], esi; dwCreationDisposition
0x140010bcf  mov     edx, 0C0000000h; dwDesiredAccess
0x140010bd4  mov     rcx, rbp; lpFileName
0x140010bd7  call    cs:__imp_CreateFileA
0x140010bdd  cmp     rax, rbx
0x140010be0  cmovnz  rdi, rax
0x140010be4  test    rdi, rdi
0x140010be7  jnz     short loc_140010C05
0x140010be9  call    cs:__imp_GetLastError
0x140010bef  mov     ebx, eax
0x140010bf1  test    eax, eax
0x140010bf3  jle     short loc_140010BFE
0x140010bf5  movzx   ebx, ax
0x140010bf8  or      ebx, 80070000h
0x140010bfe  xor     edi, edi
0x140010c00  jmp     loc_140010D21
0x140010c05  test    r12d, r12d
0x140010c08  jle     short loc_140010C7A
0x140010c0a  movzx   eax, [rsp+88h+Buffer]
0x140010c12  cmp     [r13+0], ax
0x140010c17  jz      short loc_140010C43
0x140010c19  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140010c1e  mov     [rsp+88h+lpMultiByteStr], 0; lpOverlapped
0x140010c27  mov     r8d, esi; nNumberOfBytesToWrite
0x140010c2a  lea     rdx, [rsp+88h+Buffer]; lpBuffer
0x140010c32  mov     rcx, rdi; hFile
0x140010c35  call    cs:__imp_WriteFile
0x140010c3b  test    eax, eax
0x140010c3d  jz      loc_140010B57
0x140010c43  lea     r8d, [r12+r12]; nNumberOfBytesToWrite
0x140010c47  mov     [rsp+88h+lpMultiByteStr], 0; lpOverlapped
0x140010c50  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140010c55  mov     rdx, r13; lpBuffer
0x140010c58  mov     rcx, rdi; hFile
0x140010c5b  call    cs:__imp_WriteFile
0x140010c61  test    eax, eax
0x140010c63  jz      loc_140010B57
0x140010c69  mov     rcx, rdi; hFile
0x140010c6c  call    cs:__imp_FlushFileBuffers
0x140010c72  test    eax, eax
0x140010c74  jz      loc_140010B57
0x140010c7a  test    r15, r15
0x140010c7d  jz      loc_140010D12
0x140010c83  inc     rbx
0x140010c86  cmp     byte ptr [rbx+rbp], 0
0x140010c8a  jnz     short loc_140010C83
0x140010c8c  mov     [rsp+88h+cbMultiByte], 0; cchWideChar
0x140010c94  mov     r9d, ebx; cbMultiByte
0x140010c97  mov     r8, rbp; lpMultiByteStr
0x140010c9a  mov     [rsp+88h+lpMultiByteStr], 0; lpWideCharStr
0x140010ca3  xor     edx, edx; dwFlags
0x140010ca5  xor     ecx, ecx; CodePage
0x140010ca7  call    cs:__imp_MultiByteToWideChar
0x140010cad  mov     r14d, eax
0x140010cb0  test    eax, eax
0x140010cb2  jz      loc_140010B57
0x140010cb8  mov     edx, eax; ui
0x140010cba  xor     ecx, ecx; strIn
0x140010cbc  call    cs:__imp_SysAllocStringLen
0x140010cc2  mov     rsi, rax
0x140010cc5  test    rax, rax
0x140010cc8  jnz     short loc_140010CD1
0x140010cca  mov     ebx, 8007000Eh
0x140010ccf  jmp     short loc_140010D21
0x140010cd1  mov     [rsp+88h+cbMultiByte], r14d; cchWideChar
0x140010cd6  mov     r9d, ebx; cbMultiByte
0x140010cd9  mov     r8, rbp; lpMultiByteStr
0x140010cdc  mov     [rsp+88h+lpMultiByteStr], rsi; lpWideCharStr
0x140010ce1  xor     edx, edx; dwFlags
0x140010ce3  xor     ecx, ecx; CodePage
0x140010ce5  call    cs:__imp_MultiByteToWideChar
0x140010ceb  test    eax, eax
0x140010ced  jnz     short loc_140010D0F
0x140010cef  call    cs:__imp_GetLastError
0x140010cf5  mov     ebx, eax
0x140010cf7  test    eax, eax
0x140010cf9  jle     short loc_140010D04
0x140010cfb  movzx   ebx, ax
0x140010cfe  or      ebx, 80070000h
0x140010d04  mov     rcx, rsi; bstrString
0x140010d07  call    cs:__imp_SysFreeString
0x140010d0d  jmp     short loc_140010D21
0x140010d0f  mov     [r15], rsi
0x140010d12  mov     rax, [rsp+88h+arg_18]
0x140010d1a  mov     [rax], rdi
0x140010d1d  xor     edi, edi
0x140010d1f  xor     ebx, ebx
0x140010d21  mov     rcx, rbp; Block
0x140010d24  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140010d29  mov     rcx, [rsp+88h+lpPathName]; Block
0x140010d31  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140010d36  test    rdi, rdi
0x140010d39  jz      short loc_140010D44
0x140010d3b  mov     rcx, rdi; hObject
0x140010d3e  call    cs:__imp_CloseHandle
0x140010d44  mov     eax, ebx
0x140010d46  mov     rbx, [rsp+88h+arg_8]
0x140010d4e  add     rsp, 50h
0x140010d52  pop     r15
0x140010d54  pop     r14
0x140010d56  pop     r13
0x140010d58  pop     r12
0x140010d5a  pop     rdi
0x140010d5b  pop     rsi
0x140010d5c  pop     rbp
0x140010d5d  retn
```
