# WriteTrackingFile(ushort const *,ushort const *,ulong)

- ea: `0x14005f750`
- end: `0x14005f9b4`
- name: `?WriteTrackingFile@@YAJPEBG0K@Z`
- size: `612`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14005f5bc`

## callees

- `0x14000b0d4`
- `0x14000b0f4`
- `0x14005f3e4`
- `0x14005f474`
- `0x14005f6e0`
- `0x14005f710`
- `0x14005f750`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005f900`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005f973`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005f900`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005f973`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005f7c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005f849`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005f915`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005f92a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005f988`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005f99d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005f7c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005f849`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005f915`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005f92a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005f988`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005f99d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14005f8d1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14005f8d1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14005f882`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14005f882`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x14005f812`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x14005f812`

## string_xrefs

- `0x14005f944`: `failed to write data to the file`

## pseudocode

```c
__int64 __fastcall WriteTrackingFile(const unsigned __int16 *a1, const unsigned __int16 *a2, int a3)
{
  int StoragePath; // ebx
  __int64 v6; // rdx
  HRESULT v7; // eax
  HANDLE FileW; // rax
  const char *v9; // r9
  void *v10; // rbx
  const char *v11; // r9
  unsigned int LastError; // edi
  int dwCreationDisposition; // [rsp+20h] [rbp-20h]
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  HLOCAL hMem; // [rsp+60h] [rbp+20h] BYREF
  const unsigned __int16 *NumberOfBytesWritten; // [rsp+68h] [rbp+28h] BYREF
  int Buffer; // [rsp+70h] [rbp+30h] BYREF
  PWSTR ppszPathOut; // [rsp+78h] [rbp+38h] BYREF

  Buffer = a3;
  NumberOfBytesWritten = a2;
  if ( !a1 )
  {
    StoragePath = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x250,
      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)0x80070057LL,
      dwCreationDisposition);
    return (unsigned int)StoragePath;
  }
  hMem = 0;
  StoragePath = GetStoragePath(a1, (PWSTR *)&hMem);
  if ( StoragePath < 0 )
  {
    v6 = 596;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)(unsigned int)StoragePath,
      dwCreationDisposition);
LABEL_7:
    if ( hMem )
      LocalFree(hMem);
    return (unsigned int)StoragePath;
  }
  if ( !(unsigned int)PathExists((const unsigned __int16 *)hMem) )
  {
    StoragePath = CreateStoragePath(a1);
    if ( StoragePath < 0 )
    {
      v6 = 599;
      goto LABEL_6;
    }
  }
  ppszPathOut = 0;
  v7 = PathAllocCombine((PCWSTR)hMem, L"171be49a-d484-4251-9513-068d10acb6a1.txt", 0, &ppszPathOut);
  StoragePath = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25B,
      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)(unsigned int)v7,
      dwCreationDisposition);
    goto LABEL_14;
  }
  FileW = CreateFileW(ppszPathOut, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  v10 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    StoragePath = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x265,
                    (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
                    v9);
LABEL_14:
    if ( ppszPathOut )
      LocalFree(ppszPathOut);
    goto LABEL_7;
  }
  LODWORD(NumberOfBytesWritten) = 0;
  if ( !WriteFile(FileW, &Buffer, 4u, (LPDWORD)&NumberOfBytesWritten, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x268,
                  (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
                  v11);
LABEL_20:
    if ( v10 )
      CloseHandle(v10);
    if ( ppszPathOut )
      LocalFree(ppszPathOut);
    if ( hMem )
      LocalFree(hMem);
    return LastError;
  }
  if ( (_DWORD)NumberOfBytesWritten != 4 )
  {
    LastError = -2147467259;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x26C,
      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)0x80004005LL,
      (int)"failed to write data to the file",
      dwFlagsAndAttributes);
    goto LABEL_20;
  }
  if ( v10 )
    CloseHandle(v10);
  if ( ppszPathOut )
    LocalFree(ppszPathOut);
  if ( hMem )
    LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x14005f750  mov     [rsp-18h+Buffer], r8d
0x14005f755  mov     [rsp-18h+NumberOfBytesWritten], rdx
0x14005f75a  push    rbp
0x14005f75b  push    rbx
0x14005f75c  push    rdi
0x14005f75d  mov     rbp, rsp
0x14005f760  sub     rsp, 40h
0x14005f764  mov     rdi, rcx
0x14005f767  test    rcx, rcx
0x14005f76a  jnz     short loc_14005F790
0x14005f76c  mov     rcx, [rbp+18h]; this
0x14005f770  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x14005f777  mov     ebx, 80070057h
0x14005f77c  mov     edx, 250h; void *
0x14005f781  mov     r9d, ebx; char *
0x14005f784  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005f789  mov     eax, ebx
0x14005f78b  jmp     loc_14005F9AB
0x14005f790  lea     rdx, [rbp+hMem]; ppszPathOut
0x14005f794  mov     [rbp+hMem], 0
0x14005f79c  call    ?GetStoragePath@@YAJPEBGPEAPEAG@Z; GetStoragePath(ushort const *,ushort * *)
0x14005f7a1  mov     ebx, eax
0x14005f7a3  test    eax, eax
0x14005f7a5  jns     short loc_14005F7D6
0x14005f7a7  mov     edx, 254h; void *
0x14005f7ac  mov     rcx, [rbp+18h]; this
0x14005f7b0  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x14005f7b7  mov     r9d, ebx; char *
0x14005f7ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005f7bf  mov     rcx, [rbp+hMem]; hMem
0x14005f7c3  test    rcx, rcx
0x14005f7c6  jz      short loc_14005F789
0x14005f7c8  call    cs:__imp_LocalFree
0x14005f7cf  nop     dword ptr [rax+rax+00h]
0x14005f7d4  jmp     short loc_14005F789
0x14005f7d6  mov     rcx, [rbp+hMem]; unsigned __int16 *
0x14005f7da  call    ?PathExists@@YAHPEBG@Z; PathExists(ushort const *)
0x14005f7df  test    eax, eax
0x14005f7e1  jnz     short loc_14005F7F8
0x14005f7e3  mov     rcx, rdi; unsigned __int16 *
0x14005f7e6  call    ?CreateStoragePath@@YAJPEBG@Z; CreateStoragePath(ushort const *)
0x14005f7eb  mov     ebx, eax
0x14005f7ed  test    eax, eax
0x14005f7ef  jns     short loc_14005F7F8
0x14005f7f1  mov     edx, 257h
0x14005f7f6  jmp     short loc_14005F7AC
0x14005f7f8  mov     rcx, [rbp+hMem]; pszPathIn
0x14005f7fc  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x14005f800  xor     r8d, r8d; dwFlags
0x14005f803  mov     [rbp+ppszPathOut], 0
0x14005f80b  lea     rdx, a171be49aD48442; "171be49a-d484-4251-9513-068d10acb6a1.tx"...
0x14005f812  call    cs:__imp_PathAllocCombine
0x14005f819  nop     dword ptr [rax+rax+00h]
0x14005f81e  mov     ebx, eax
0x14005f820  test    eax, eax
0x14005f822  jns     short loc_14005F85A
0x14005f824  mov     rcx, [rbp+18h]; this
0x14005f828  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x14005f82f  mov     r9d, eax; char *
0x14005f832  mov     edx, 25Bh; void *
0x14005f837  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005f83c  mov     rcx, [rbp+ppszPathOut]; hMem
0x14005f840  test    rcx, rcx
0x14005f843  jz      loc_14005F7BF
0x14005f849  call    cs:__imp_LocalFree
0x14005f850  nop     dword ptr [rax+rax+00h]
0x14005f855  jmp     loc_14005F7BF
0x14005f85a  mov     rcx, [rbp+ppszPathOut]; lpFileName
0x14005f85e  xor     r9d, r9d; lpSecurityAttributes
0x14005f861  mov     [rsp+40h+hTemplateFile], 0; hTemplateFile
0x14005f86a  xor     r8d, r8d; dwShareMode
0x14005f86d  mov     dword ptr [rsp+40h+dwFlagsAndAttributes], 80h; char *
0x14005f875  mov     edx, 40000000h; dwDesiredAccess
0x14005f87a  mov     [rsp+40h+dwCreationDisposition], 2; dwCreationDisposition
0x14005f882  call    cs:__imp_CreateFileW
0x14005f889  nop     dword ptr [rax+rax+00h]
0x14005f88e  mov     rbx, rax
0x14005f891  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14005f895  jnz     short loc_14005F8B0
0x14005f897  mov     rcx, [rbp+18h]; this
0x14005f89b  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x14005f8a2  mov     edx, 265h; void *
0x14005f8a7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14005f8ac  mov     ebx, eax
0x14005f8ae  jmp     short loc_14005F83C
0x14005f8b0  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14005f8b4  mov     dword ptr [rbp+NumberOfBytesWritten], 0
0x14005f8bb  mov     r8d, 4; nNumberOfBytesToWrite
0x14005f8c1  mov     qword ptr [rsp+40h+dwCreationDisposition], 0; lpOverlapped
0x14005f8ca  lea     rdx, [rbp+Buffer]; lpBuffer
0x14005f8ce  mov     rcx, rbx; hFile
0x14005f8d1  call    cs:__imp_WriteFile
0x14005f8d8  nop     dword ptr [rax+rax+00h]
0x14005f8dd  test    eax, eax
0x14005f8df  jnz     short loc_14005F93A
0x14005f8e1  mov     rcx, [rbp+18h]; this
0x14005f8e5  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x14005f8ec  mov     edx, 268h; void *
0x14005f8f1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14005f8f6  mov     edi, eax
0x14005f8f8  test    rbx, rbx
0x14005f8fb  jz      short loc_14005F90C
0x14005f8fd  mov     rcx, rbx; hObject
0x14005f900  call    cs:__imp_CloseHandle
0x14005f907  nop     dword ptr [rax+rax+00h]
0x14005f90c  mov     rcx, [rbp+ppszPathOut]; hMem
0x14005f910  test    rcx, rcx
0x14005f913  jz      short loc_14005F921
0x14005f915  call    cs:__imp_LocalFree
0x14005f91c  nop     dword ptr [rax+rax+00h]
0x14005f921  mov     rcx, [rbp+hMem]; hMem
0x14005f925  test    rcx, rcx
0x14005f928  jz      short loc_14005F936
0x14005f92a  call    cs:__imp_LocalFree
0x14005f931  nop     dword ptr [rax+rax+00h]
0x14005f936  mov     eax, edi
0x14005f938  jmp     short loc_14005F9AB
0x14005f93a  cmp     dword ptr [rbp+NumberOfBytesWritten], 4
0x14005f93e  jz      short loc_14005F96B
0x14005f940  mov     rcx, [rbp+18h]; this
0x14005f944  lea     rax, aFailedToWriteD; "failed to write data to the file"
0x14005f94b  mov     edi, 80004005h
0x14005f950  mov     qword ptr [rsp+40h+dwCreationDisposition], rax; int
0x14005f955  mov     r9d, edi; char *
0x14005f958  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x14005f95f  mov     edx, 26Ch; void *
0x14005f964  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14005f969  jmp     short loc_14005F8F8
0x14005f96b  test    rbx, rbx
0x14005f96e  jz      short loc_14005F97F
0x14005f970  mov     rcx, rbx; hObject
0x14005f973  call    cs:__imp_CloseHandle
0x14005f97a  nop     dword ptr [rax+rax+00h]
0x14005f97f  mov     rcx, [rbp+ppszPathOut]; hMem
0x14005f983  test    rcx, rcx
0x14005f986  jz      short loc_14005F994
0x14005f988  call    cs:__imp_LocalFree
0x14005f98f  nop     dword ptr [rax+rax+00h]
0x14005f994  mov     rcx, [rbp+hMem]; hMem
0x14005f998  test    rcx, rcx
0x14005f99b  jz      short loc_14005F9A9
0x14005f99d  call    cs:__imp_LocalFree
0x14005f9a4  nop     dword ptr [rax+rax+00h]
0x14005f9a9  xor     eax, eax
0x14005f9ab  add     rsp, 40h
0x14005f9af  pop     rdi
0x14005f9b0  pop     rbx
0x14005f9b1  pop     rbp
0x14005f9b2  retn
```
