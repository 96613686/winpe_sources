# FileStream::open(ushort const *,bool)

- ea: `0x180044bc4`
- end: `0x180044d23`
- name: `?open@FileStream@@QEAAJPEBG_N@Z`
- size: `351`
- prototype: `int(FileStream *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800ee9a0`
- `0x1800eea0c`

## callees

- `0x18000912c`
- `0x18001f080`
- `0x180044bc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044cb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044cb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044cf1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044cf1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180044c62`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180044ca0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180044c62`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180044ca0`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180044cdb`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180044cdb`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x180044c0a`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x180044c0a`

## pseudocode

```c
__int64 __fastcall FileStream::open(FileStream *this, unsigned __int16 *a2, unsigned __int8 a3)
{
  int v4; // r15d
  WCHAR *v6; // rax
  unsigned __int16 *v7; // rdi
  int v8; // ebx
  HANDLE FileW; // rax
  signed int LastError; // eax
  DWORD FileType; // eax
  DWORD pcchPath; // [rsp+90h] [rbp+18h] BYREF

  v4 = a3;
  pcchPath = 4096;
  v6 = (WCHAR *)new_array_ne<unsigned short>(4096);
  v7 = v6;
  if ( v6 )
  {
    v8 = PathCreateFromUrlW(a2, v6, &pcchPath, 0);
    if ( v8 >= 0 )
    {
      a2 = v7;
      v8 = 0;
    }
    else
    {
      MemFreeObject(v7);
      v7 = 0;
    }
  }
  else
  {
    v8 = -2147024882;
  }
  *((_BYTE *)this + 168) = v4;
  FileW = CreateFileW(a2, ((v4 ^ 1u) + 1) << 30, 1u, 0, 3u, 0x100080u, 0);
  *((_QWORD *)this + 20) = FileW;
  if ( FileW == (HANDLE)-1LL
    && (!(_BYTE)v4
     || (FileW = CreateFileW(a2, ((v4 ^ 1u) + 1) << 30, 1u, 0, 2u, 0x100080u, 0),
         *((_QWORD *)this + 20) = FileW,
         FileW == (HANDLE)-1LL)) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( (LastError & 0xFFFFFFFD) != 0 )
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v8 = -2146697210;
    }
  }
  else
  {
    FileType = GetFileType(FileW);
    if ( !FileType || FileType == 2 )
    {
      CloseHandle(*((HANDLE *)this + 20));
      *((_QWORD *)this + 20) = -1;
      v8 = -2147024891;
    }
  }
  if ( v7 )
    MemFreeObject(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180044bc4  mov     rax, rsp
0x180044bc7  push    rbx
0x180044bc8  push    rbp
0x180044bc9  push    rsi
0x180044bca  push    rdi
0x180044bcb  push    r14
0x180044bcd  push    r15
0x180044bcf  sub     rsp, 48h
0x180044bd3  mov     rbp, rcx
0x180044bd6  movzx   r15d, r8b
0x180044bda  mov     ecx, 1000h
0x180044bdf  mov     rsi, rdx
0x180044be2  mov     [rax+18h], ecx
0x180044be5  call    ??$new_array_ne@G@@YAPEAG_J@Z; new_array_ne<ushort>(__int64)
0x180044bea  mov     rdi, rax
0x180044bed  test    rax, rax
0x180044bf0  jnz     short loc_180044BF9
0x180044bf2  mov     ebx, 8007000Eh
0x180044bf7  jmp     short loc_180044C27
0x180044bf9  xor     r9d, r9d; dwFlags
0x180044bfc  lea     r8, [rsp+78h+pcchPath]; pcchPath
0x180044c04  mov     rdx, rdi; pszPath
0x180044c07  mov     rcx, rsi; pszUrl
0x180044c0a  call    cs:__imp_PathCreateFromUrlW
0x180044c10  mov     ebx, eax
0x180044c12  test    eax, eax
0x180044c14  jns     short loc_180044C22
0x180044c16  mov     rcx, rdi; void *
0x180044c19  call    ?MemFreeObject@@YAXPEAX@Z; MemFreeObject(void *)
0x180044c1e  xor     edi, edi
0x180044c20  jmp     short loc_180044C27
0x180044c22  mov     rsi, rdi
0x180044c25  xor     ebx, ebx
0x180044c27  xor     r9d, r9d; lpSecurityAttributes
0x180044c2a  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x180044c33  mov     r14d, r15d
0x180044c36  mov     [rsp+78h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180044c3e  xor     r14d, 1
0x180044c42  mov     [rbp+0A8h], r15b
0x180044c49  inc     r14d
0x180044c4c  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180044c54  shl     r14d, 1Eh
0x180044c58  lea     r8d, [r9+1]; dwShareMode
0x180044c5c  mov     edx, r14d; dwDesiredAccess
0x180044c5f  mov     rcx, rsi; lpFileName
0x180044c62  call    cs:__imp_CreateFileW
0x180044c68  mov     [rbp+0A0h], rax
0x180044c6f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180044c73  jnz     short loc_180044CD8
0x180044c75  test    r15b, r15b
0x180044c78  jz      short loc_180044CB3
0x180044c7a  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x180044c83  lea     r8d, [rax+2]; dwShareMode
0x180044c87  mov     [rsp+78h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180044c8f  xor     r9d, r9d; lpSecurityAttributes
0x180044c92  mov     edx, r14d; dwDesiredAccess
0x180044c95  mov     [rsp+78h+dwCreationDisposition], 2; dwCreationDisposition
0x180044c9d  mov     rcx, rsi; lpFileName
0x180044ca0  call    cs:__imp_CreateFileW
0x180044ca6  mov     [rbp+0A0h], rax
0x180044cad  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180044cb1  jnz     short loc_180044CD8
0x180044cb3  call    cs:__imp_GetLastError
0x180044cb9  mov     ebx, eax
0x180044cbb  test    eax, 0FFFFFFFDh
0x180044cc0  jz      short loc_180044CD1
0x180044cc2  test    eax, eax
0x180044cc4  jle     short loc_180044D07
0x180044cc6  movzx   ebx, ax
0x180044cc9  or      ebx, 80070000h
0x180044ccf  jmp     short loc_180044D07
0x180044cd1  mov     ebx, 800C0006h
0x180044cd6  jmp     short loc_180044D07
0x180044cd8  mov     rcx, rax; hFile
0x180044cdb  call    cs:__imp_GetFileType
0x180044ce1  test    eax, eax
0x180044ce3  jz      short loc_180044CEA
0x180044ce5  cmp     eax, 2
0x180044ce8  jnz     short loc_180044D07
0x180044cea  mov     rcx, [rbp+0A0h]; hObject
0x180044cf1  call    cs:__imp_CloseHandle
0x180044cf7  mov     qword ptr [rbp+0A0h], 0FFFFFFFFFFFFFFFFh
0x180044d02  mov     ebx, 80070005h
0x180044d07  test    rdi, rdi
0x180044d0a  jz      short loc_180044D14
0x180044d0c  mov     rcx, rdi; void *
0x180044d0f  call    ?MemFreeObject@@YAXPEAX@Z; MemFreeObject(void *)
0x180044d14  mov     eax, ebx
0x180044d16  add     rsp, 48h
0x180044d1a  pop     r15
0x180044d1c  pop     r14
0x180044d1e  pop     rdi
0x180044d1f  pop     rsi
0x180044d20  pop     rbp
0x180044d21  pop     rbx
0x180044d22  retn
```
