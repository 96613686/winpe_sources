# CRtfToHtmlConverter::StringHtmlToStringRtf(char *,void * *)

- ea: `0x1808750c8`
- end: `0x1808752cd`
- name: `?StringHtmlToStringRtf@CRtfToHtmlConverter@@IEAAJPEADPEAPEAX@Z`
- size: `517`
- prototype: `__int64 __fastcall(CDoc **this, _BYTE *lpBuffer, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180decef0`

## callees

- `0x180874c78`
- `0x1808750c8`
- `0x1810c2d60`

## import_xrefs

- `KERNEL32!GlobalLock` at `0x180875241`
- `KERNEL32!GlobalLock` at `0x180875241`
- `KERNEL32!GlobalUnlock` at `0x180875293`
- `KERNEL32!GlobalUnlock` at `0x180875293`
- `KERNEL32!WriteFile` at `0x1808751b0`
- `KERNEL32!WriteFile` at `0x1808751b0`
- `KERNEL32!ReadFile` at `0x180875266`
- `KERNEL32!ReadFile` at `0x180875266`
- `KERNEL32!GlobalAlloc` at `0x180875235`
- `KERNEL32!GlobalAlloc` at `0x180875235`
- `KERNEL32!GetTempPath2W` at `0x18087511b`
- `KERNEL32!GetTempPath2W` at `0x18087511b`
- `KERNEL32!GetTempFileNameW` at `0x180875137`
- `KERNEL32!GetTempFileNameW` at `0x180875155`
- `KERNEL32!GetTempFileNameW` at `0x180875137`
- `KERNEL32!GetTempFileNameW` at `0x180875155`
- `KERNEL32!CreateFileW` at `0x180875180`
- `KERNEL32!CreateFileW` at `0x18087520f`
- `KERNEL32!CreateFileW` at `0x180875180`
- `KERNEL32!CreateFileW` at `0x18087520f`
- `KERNEL32!GetFileSize` at `0x180875223`
- `KERNEL32!GetFileSize` at `0x180875223`
- `KERNEL32!DeleteFileW` at `0x18087529e`
- `KERNEL32!DeleteFileW` at `0x18087529e`
- `KERNEL32!CloseHandle` at `0x1808751bb`
- `KERNEL32!CloseHandle` at `0x180875271`
- `KERNEL32!CloseHandle` at `0x1808751bb`
- `KERNEL32!CloseHandle` at `0x180875271`

## pseudocode

```c
__int64 __fastcall CRtfToHtmlConverter::StringHtmlToStringRtf(CDoc **this, _BYTE *lpBuffer, void **a3)
{
  _BYTE *v6; // rdi
  HANDLE FileW; // rax
  void *v8; // rsi
  __int64 v9; // r8
  BOOL v10; // ebx
  unsigned int v11; // r14d
  HANDLE v12; // rax
  void *v13; // rsi
  DWORD FileSize; // eax
  DWORD v15; // ebx
  HGLOBAL v16; // rax
  _BYTE *v17; // rax
  BOOL v18; // ebx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-BCh] BYREF
  WCHAR TempFileName[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR PathName[264]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR FileName[264]; // [rsp+470h] [rbp+370h] BYREF

  NumberOfBytesRead = 0;
  NumberOfBytesWritten = 0;
  v6 = 0;
  GetTempPath2W(260, PathName);
  GetTempFileNameW(PathName, L"h2r", 0, TempFileName);
  GetTempFileNameW(PathName, L"h2r", 0, FileName);
  FileW = CreateFileW(TempFileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  v8 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    v9 = -1;
    do
      ++v9;
    while ( lpBuffer[v9] );
    v10 = WriteFile(FileW, lpBuffer, v9, &NumberOfBytesWritten, 0);
    CloseHandle(v8);
    if ( v10 )
    {
      v11 = CRtfToHtmlConverter::InternalHtmlToExternalRtf(this, FileName, TempFileName);
      if ( !v11 )
      {
        v12 = CreateFileW(FileName, 0x80000000, 0, 0, 3u, 0x4000000u, 0);
        v13 = v12;
        if ( v12 != (HANDLE)-1LL )
        {
          FileSize = GetFileSize(v12, 0);
          v15 = FileSize;
          if ( FileSize != -1 )
          {
            v16 = GlobalAlloc(0, FileSize + 1);
            *a3 = v16;
            v17 = GlobalLock(v16);
            v6 = v17;
            if ( v17 )
            {
              v18 = ReadFile(v13, v17, v15, &NumberOfBytesRead, 0);
              CloseHandle(v13);
              if ( v18 )
              {
                v6[NumberOfBytesRead] = 0;
LABEL_12:
                GlobalUnlock(*a3);
                goto LABEL_13;
              }
            }
          }
        }
      }
    }
  }
  v11 = -2147467259;
  if ( v6 )
    goto LABEL_12;
LABEL_13:
  DeleteFileW(TempFileName);
  return v11;
}

```

## disassembly

```asm
0x1808750c8  mov     [rsp-8+arg_18], rbx
0x1808750cd  push    rbp
0x1808750ce  push    rsi
0x1808750cf  push    rdi
0x1808750d0  push    r14
0x1808750d2  push    r15
0x1808750d4  lea     rbp, [rsp-590h]
0x1808750dc  sub     rsp, 690h
0x1808750e3  mov     rax, cs:__security_cookie
0x1808750ea  xor     rax, rsp
0x1808750ed  mov     [rbp+5B0h+var_30], rax
0x1808750f4  mov     rbx, rdx
0x1808750f7  mov     [rsp+6B0h+NumberOfBytesRead], 0
0x1808750ff  mov     r14, rcx
0x180875102  mov     [rsp+6B0h+NumberOfBytesWritten], 0
0x18087510a  lea     rdx, [rbp+5B0h+PathName]
0x180875111  mov     ecx, 104h
0x180875116  mov     r15, r8
0x180875119  xor     edi, edi
0x18087511b  call    cs:__imp_GetTempPath2W
0x180875121  lea     r9, [rsp+6B0h+TempFileName]; lpTempFileName
0x180875126  xor     r8d, r8d; uUnique
0x180875129  lea     rdx, aH2r; "h2r"
0x180875130  lea     rcx, [rbp+5B0h+PathName]; lpPathName
0x180875137  call    cs:__imp_GetTempFileNameW
0x18087513d  lea     r9, [rbp+5B0h+FileName]; lpTempFileName
0x180875144  xor     r8d, r8d; uUnique
0x180875147  lea     rdx, aH2r; "h2r"
0x18087514e  lea     rcx, [rbp+5B0h+PathName]; lpPathName
0x180875155  call    cs:__imp_GetTempFileNameW
0x18087515b  mov     [rsp+6B0h+hTemplateFile], rdi; hTemplateFile
0x180875160  lea     rcx, [rsp+6B0h+TempFileName]; lpFileName
0x180875165  mov     [rsp+6B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18087516d  xor     r9d, r9d; lpSecurityAttributes
0x180875170  xor     r8d, r8d; dwShareMode
0x180875173  mov     [rsp+6B0h+dwCreationDisposition], 2; dwCreationDisposition
0x18087517b  mov     edx, 40000000h; dwDesiredAccess
0x180875180  call    cs:__imp_CreateFileW
0x180875186  mov     rsi, rax
0x180875189  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18087518d  jz      loc_180875285
0x180875193  or      r8, 0FFFFFFFFFFFFFFFFh
0x180875197  inc     r8; nNumberOfBytesToWrite
0x18087519a  cmp     [rbx+r8], dil
0x18087519e  jnz     short loc_180875197
0x1808751a0  lea     r9, [rsp+6B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1808751a5  mov     qword ptr [rsp+6B0h+dwCreationDisposition], rdi; lpOverlapped
0x1808751aa  mov     rdx, rbx; lpBuffer
0x1808751ad  mov     rcx, rsi; hFile
0x1808751b0  call    cs:__imp_WriteFile
0x1808751b6  mov     rcx, rsi; hObject
0x1808751b9  mov     ebx, eax
0x1808751bb  call    cs:__imp_CloseHandle
0x1808751c1  test    ebx, ebx
0x1808751c3  jz      loc_180875285
0x1808751c9  lea     r8, [rsp+6B0h+TempFileName]; unsigned __int16 *
0x1808751ce  mov     rcx, r14; this
0x1808751d1  lea     rdx, [rbp+5B0h+FileName]; unsigned __int16 *
0x1808751d8  call    ?InternalHtmlToExternalRtf@CRtfToHtmlConverter@@IEAAJPEBG0@Z; CRtfToHtmlConverter::InternalHtmlToExternalRtf(ushort const *,ushort const *)
0x1808751dd  mov     r14d, eax
0x1808751e0  test    eax, eax
0x1808751e2  jnz     loc_180875285
0x1808751e8  mov     [rsp+6B0h+hTemplateFile], rdi; hTemplateFile
0x1808751ed  lea     rcx, [rbp+5B0h+FileName]; lpFileName
0x1808751f4  mov     [rsp+6B0h+dwFlagsAndAttributes], 4000000h; dwFlagsAndAttributes
0x1808751fc  xor     r9d, r9d; lpSecurityAttributes
0x1808751ff  xor     r8d, r8d; dwShareMode
0x180875202  mov     [rsp+6B0h+dwCreationDisposition], 3; dwCreationDisposition
0x18087520a  mov     edx, 80000000h; dwDesiredAccess
0x18087520f  call    cs:__imp_CreateFileW
0x180875215  mov     rsi, rax
0x180875218  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18087521c  jz      short loc_180875285
0x18087521e  xor     edx, edx; lpFileSizeHigh
0x180875220  mov     rcx, rax; hFile
0x180875223  call    cs:__imp_GetFileSize
0x180875229  mov     ebx, eax
0x18087522b  cmp     eax, 0FFFFFFFFh
0x18087522e  jz      short loc_180875285
0x180875230  lea     edx, [rax+1]; dwBytes
0x180875233  xor     ecx, ecx; uFlags
0x180875235  call    cs:__imp_GlobalAlloc
0x18087523b  mov     rcx, rax; hMem
0x18087523e  mov     [r15], rax
0x180875241  call    cs:__imp_GlobalLock
0x180875247  mov     rdi, rax
0x18087524a  test    rax, rax
0x18087524d  jz      short loc_180875285
0x18087524f  lea     r9, [rsp+6B0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180875254  mov     qword ptr [rsp+6B0h+dwCreationDisposition], 0; lpOverlapped
0x18087525d  mov     r8d, ebx; nNumberOfBytesToRead
0x180875260  mov     rdx, rax; lpBuffer
0x180875263  mov     rcx, rsi; hFile
0x180875266  call    cs:__imp_ReadFile
0x18087526c  mov     rcx, rsi; hObject
0x18087526f  mov     ebx, eax
0x180875271  call    cs:__imp_CloseHandle
0x180875277  test    ebx, ebx
0x180875279  jz      short loc_180875285
0x18087527b  mov     eax, [rsp+6B0h+NumberOfBytesRead]
0x18087527f  mov     [rax+rdi], r14b
0x180875283  jmp     short loc_180875290
0x180875285  mov     r14d, 80004005h
0x18087528b  test    rdi, rdi
0x18087528e  jz      short loc_180875299
0x180875290  mov     rcx, [r15]; hMem
0x180875293  call    cs:__imp_GlobalUnlock
0x180875299  lea     rcx, [rsp+6B0h+TempFileName]; lpFileName
0x18087529e  call    cs:__imp_DeleteFileW
0x1808752a4  mov     eax, r14d
0x1808752a7  mov     rcx, [rbp+5B0h+var_30]
0x1808752ae  xor     rcx, rsp; StackCookie
0x1808752b1  call    __security_check_cookie
0x1808752b6  mov     rbx, [rsp+6B0h+arg_18]
0x1808752be  add     rsp, 690h
0x1808752c5  pop     r15
0x1808752c7  pop     r14
0x1808752c9  pop     rdi
0x1808752ca  pop     rsi
0x1808752cb  pop     rbp
0x1808752cc  retn
```
