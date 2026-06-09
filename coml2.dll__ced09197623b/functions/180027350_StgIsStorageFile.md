# StgIsStorageFile

- ea: `0x180027350`
- end: `0x1800273f0`
- name: `StgIsStorageFile`
- size: `160`
- prototype: `HRESULT __stdcall(const WCHAR *pwcsName)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180023e70`
- `0x180026bc4`
- `0x180027350`
- `0x180033ec0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800273bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800273bf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800273b0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800273b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800273e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800273e6`

## pseudocode

```c
HRESULT __stdcall StgIsStorageFile(const WCHAR *pwcsName)
{
  __int64 v1; // rdx
  const WCHAR *v2; // rcx
  const WCHAR *v3; // rax
  HANDLE FileW; // rax
  void *v6; // rdi
  DWORD LastError; // eax
  HRESULT IsStorageFileHandle; // ebx

  if ( !(unsigned int)IsValidReadPtrIn(pwcsName, 0x104u) || !v2 )
    return -2147286788;
  v3 = v2;
  do
  {
    if ( !*v3 )
      break;
    ++v3;
    --v1;
  }
  while ( v1 );
  if ( !v1 )
    return -2147286788;
  FileW = CreateFileW(v2, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  v6 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    return Win32ErrorToScode(LastError);
  }
  else
  {
    IsStorageFileHandle = StgIsStorageFileHandle(FileW, 0);
    CloseHandle(v6);
    return IsStorageFileHandle;
  }
}

```

## disassembly

```asm
0x180027350  mov     [rsp+arg_0], rbx
0x180027355  push    rdi
0x180027356  sub     rsp, 40h
0x18002735a  mov     edx, 104h; unsigned __int64
0x18002735f  call    ?IsValidReadPtrIn@@YAHPEBX_K@Z; IsValidReadPtrIn(void const *,unsigned __int64)
0x180027364  xor     r8d, r8d
0x180027367  test    eax, eax
0x180027369  jz      short loc_180027388
0x18002736b  test    rcx, rcx
0x18002736e  jz      short loc_180027388
0x180027370  mov     rax, rcx
0x180027373  cmp     [rax], r8w
0x180027377  jz      short loc_180027383
0x180027379  add     rax, 2
0x18002737d  sub     rdx, 1
0x180027381  jnz     short loc_180027373
0x180027383  test    rdx, rdx
0x180027386  jnz     short loc_18002738F
0x180027388  mov     eax, 800300FCh
0x18002738d  jmp     short loc_1800273CC
0x18002738f  mov     [rsp+48h+hTemplateFile], r8; hTemplateFile
0x180027394  xor     r9d, r9d; lpSecurityAttributes
0x180027397  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002739f  mov     edx, 80000000h; dwDesiredAccess
0x1800273a4  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1800273ac  lea     r8d, [r9+7]; dwShareMode
0x1800273b0  call    cs:__imp_CreateFileW
0x1800273b6  mov     rdi, rax
0x1800273b9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800273bd  jnz     short loc_1800273D7
0x1800273bf  call    cs:__imp_GetLastError
0x1800273c5  mov     ecx, eax; unsigned int
0x1800273c7  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x1800273cc  mov     rbx, [rsp+48h+arg_0]
0x1800273d1  add     rsp, 40h
0x1800273d5  pop     rdi
0x1800273d6  retn
0x1800273d7  xor     edx, edx; lpOverlapped
0x1800273d9  mov     rcx, rdi; hFile
0x1800273dc  call    StgIsStorageFileHandle
0x1800273e1  mov     rcx, rdi; hObject
0x1800273e4  mov     ebx, eax
0x1800273e6  call    cs:__imp_CloseHandle
0x1800273ec  mov     eax, ebx
0x1800273ee  jmp     short loc_1800273CC
```
