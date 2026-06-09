# StgSetTimes

- ea: `0x18004a450`
- end: `0x18004a4f9`
- name: `StgSetTimes`
- size: `169`
- prototype: `HRESULT __stdcall(const WCHAR *lpszName, const FILETIME *pctime, const FILETIME *patime, const FILETIME *pmtime)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180026bc4`
- `0x180034f28`
- `0x18004a450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a4ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a4d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a4ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a4d4`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18004a4ca`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18004a4ca`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004a49e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004a49e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a4e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a4e6`

## pseudocode

```c
HRESULT __stdcall StgSetTimes(
        const WCHAR *lpszName,
        const FILETIME *pctime,
        const FILETIME *patime,
        const FILETIME *pmtime)
{
  HRESULT v7; // ebx
  const WCHAR *v8; // r10
  HANDLE FileW; // rax
  void *v10; // rdi
  DWORD LastError; // eax
  DWORD v12; // eax

  v7 = ValidateNameW(lpszName, 0x104u);
  if ( v7 >= 0 )
  {
    FileW = CreateFileW(v8, 0x40000000u, 3u, 0, 3u, 0x80u, 0);
    v10 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      return Win32ErrorToScode(LastError);
    }
    else
    {
      if ( !SetFileTime(FileW, pctime, patime, pmtime) )
      {
        v12 = GetLastError();
        v7 = Win32ErrorToScode(v12);
      }
      CloseHandle(v10);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18004a450  push    rbx
0x18004a452  push    rbp
0x18004a453  push    rsi
0x18004a454  push    rdi
0x18004a455  push    r14
0x18004a457  sub     rsp, 40h
0x18004a45b  mov     r14, rdx
0x18004a45e  mov     rsi, r9
0x18004a461  mov     edx, 104h; unsigned int
0x18004a466  mov     rbp, r8
0x18004a469  mov     r10, rcx
0x18004a46c  call    ?ValidateNameW@@YAJPEBGI@Z; ValidateNameW(ushort const *,uint)
0x18004a471  mov     ebx, eax
0x18004a473  test    eax, eax
0x18004a475  js      short loc_18004A4EC
0x18004a477  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18004a480  mov     r8d, 3; dwShareMode
0x18004a486  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18004a48e  xor     r9d, r9d; lpSecurityAttributes
0x18004a491  mov     edx, 40000000h; dwDesiredAccess
0x18004a496  mov     [rsp+68h+dwCreationDisposition], r8d; dwCreationDisposition
0x18004a49b  mov     rcx, r10; lpFileName
0x18004a49e  call    cs:__imp_CreateFileW
0x18004a4a4  mov     rdi, rax
0x18004a4a7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004a4ab  jnz     short loc_18004A4BE
0x18004a4ad  call    cs:__imp_GetLastError
0x18004a4b3  mov     ecx, eax; unsigned int
0x18004a4b5  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x18004a4ba  mov     ebx, eax
0x18004a4bc  jmp     short loc_18004A4EC
0x18004a4be  mov     r9, rsi; lpLastWriteTime
0x18004a4c1  mov     r8, rbp; lpLastAccessTime
0x18004a4c4  mov     rdx, r14; lpCreationTime
0x18004a4c7  mov     rcx, rdi; hFile
0x18004a4ca  call    cs:__imp_SetFileTime
0x18004a4d0  test    eax, eax
0x18004a4d2  jnz     short loc_18004A4E3
0x18004a4d4  call    cs:__imp_GetLastError
0x18004a4da  mov     ecx, eax; unsigned int
0x18004a4dc  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x18004a4e1  mov     ebx, eax
0x18004a4e3  mov     rcx, rdi; hObject
0x18004a4e6  call    cs:__imp_CloseHandle
0x18004a4ec  mov     eax, ebx
0x18004a4ee  add     rsp, 40h
0x18004a4f2  pop     r14
0x18004a4f4  pop     rdi
0x18004a4f5  pop     rsi
0x18004a4f6  pop     rbp
0x18004a4f7  pop     rbx
0x18004a4f8  retn
```
