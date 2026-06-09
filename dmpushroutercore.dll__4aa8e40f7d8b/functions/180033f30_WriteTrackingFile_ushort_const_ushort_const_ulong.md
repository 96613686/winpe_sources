# WriteTrackingFile(ushort const *,ushort const *,ulong)

- ea: `0x180033f30`
- end: `0x180034156`
- name: `?WriteTrackingFile@@YAJPEBG0K@Z`
- size: `550`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800336dc`

## callees

- `0x18000ba94`
- `0x18000bab4`
- `0x180025ae0`
- `0x180031a14`
- `0x180032d0c`
- `0x180033f30`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800340c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034127`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800340c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034127`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033fa9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034020`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800340d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800340e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034136`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034146`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033fa9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034020`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800340d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800340e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034136`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034146`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003409c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003409c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180034053`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180034053`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180033fb5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180033fb5`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180033ff3`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180033ff3`

## string_xrefs

- `0x1800340f8`: `failed to write data to the file`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WriteTrackingFile(const unsigned __int16 *a1, const unsigned __int16 *a2, int a3)
{
  int StoragePath; // ebx
  __int64 v6; // rdx
  DWORD FileAttributesW; // eax
  HRESULT v8; // eax
  HANDLE FileW; // rax
  const char *v10; // r9
  void *v11; // rbx
  const char *v12; // r9
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
  FileAttributesW = GetFileAttributesW((LPCWSTR)hMem);
  if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
  {
    StoragePath = CreateStoragePath(a1);
    if ( StoragePath < 0 )
    {
      v6 = 599;
      goto LABEL_6;
    }
  }
  ppszPathOut = 0;
  v8 = PathAllocCombine((PCWSTR)hMem, L"3d01ca82-df5d-4b64-b28d-ad19658c08e0.txt", 0, &ppszPathOut);
  StoragePath = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25B,
      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)(unsigned int)v8,
      dwCreationDisposition);
    goto LABEL_15;
  }
  FileW = CreateFileW(ppszPathOut, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  v11 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    StoragePath = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x265,
                    (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
                    v10);
LABEL_15:
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
                  v12);
LABEL_21:
    if ( v11 )
      CloseHandle(v11);
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
    goto LABEL_21;
  }
  if ( v11 )
    CloseHandle(v11);
  if ( ppszPathOut )
    LocalFree(ppszPathOut);
  if ( hMem )
    LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x180033f30  mov     [rsp-18h+Buffer], r8d
0x180033f35  mov     [rsp-18h+NumberOfBytesWritten], rdx
0x180033f3a  push    rbp
0x180033f3b  push    rbx
0x180033f3c  push    rdi
0x180033f3d  mov     rbp, rsp
0x180033f40  sub     rsp, 40h
0x180033f44  mov     rdi, rcx
0x180033f47  test    rcx, rcx
0x180033f4a  jnz     short loc_180033F70
0x180033f4c  mov     rcx, [rbp+18h]; this
0x180033f50  mov     ebx, 80070057h
0x180033f55  mov     r9d, ebx; char *
0x180033f58  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180033f5f  mov     edx, 250h; void *
0x180033f64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033f69  mov     eax, ebx
0x180033f6b  jmp     loc_18003414E
0x180033f70  mov     [rbp+hMem], 0
0x180033f78  lea     rdx, [rbp+hMem]; ppszPathOut
0x180033f7c  call    ?GetStoragePath@@YAJPEBGPEAPEAG@Z; GetStoragePath(ushort const *,ushort * *)
0x180033f81  mov     ebx, eax
0x180033f83  test    eax, eax
0x180033f85  jns     short loc_180033FB1
0x180033f87  mov     edx, 254h; void *
0x180033f8c  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180033f93  mov     r9d, ebx; char *
0x180033f96  mov     rcx, [rbp+18h]; this
0x180033f9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033f9f  nop
0x180033fa0  mov     rcx, [rbp+hMem]; hMem
0x180033fa4  test    rcx, rcx
0x180033fa7  jz      short loc_180033F69
0x180033fa9  call    cs:__imp_LocalFree
0x180033faf  jmp     short loc_180033F69
0x180033fb1  mov     rcx, [rbp+hMem]; lpFileName
0x180033fb5  call    cs:__imp_GetFileAttributesW
0x180033fbb  cmp     eax, 0FFFFFFFFh
0x180033fbe  jz      short loc_180033FC4
0x180033fc0  test    al, 10h
0x180033fc2  jnz     short loc_180033FD9
0x180033fc4  mov     rcx, rdi; unsigned __int16 *
0x180033fc7  call    ?CreateStoragePath@@YAJPEBG@Z; CreateStoragePath(ushort const *)
0x180033fcc  mov     ebx, eax
0x180033fce  test    eax, eax
0x180033fd0  jns     short loc_180033FD9
0x180033fd2  mov     edx, 257h
0x180033fd7  jmp     short loc_180033F8C
0x180033fd9  mov     [rbp+ppszPathOut], 0
0x180033fe1  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x180033fe5  xor     r8d, r8d; dwFlags
0x180033fe8  lea     rdx, a3d01ca82Df5d4b; "3d01ca82-df5d-4b64-b28d-ad19658c08e0.tx"...
0x180033fef  mov     rcx, [rbp+hMem]; pszPathIn
0x180033ff3  call    cs:__imp_PathAllocCombine
0x180033ff9  mov     ebx, eax
0x180033ffb  test    eax, eax
0x180033ffd  jns     short loc_18003402B
0x180033fff  mov     rcx, [rbp+18h]; this
0x180034003  mov     r9d, eax; char *
0x180034006  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x18003400d  mov     edx, 25Bh; void *
0x180034012  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034017  mov     rcx, [rbp+ppszPathOut]; hMem
0x18003401b  test    rcx, rcx
0x18003401e  jz      short loc_180033FA0
0x180034020  call    cs:__imp_LocalFree
0x180034026  jmp     loc_180033FA0
0x18003402b  mov     [rsp+40h+hTemplateFile], 0; hTemplateFile
0x180034034  mov     dword ptr [rsp+40h+dwFlagsAndAttributes], 80h; char *
0x18003403c  mov     [rsp+40h+dwCreationDisposition], 2; dwCreationDisposition
0x180034044  xor     r9d, r9d; lpSecurityAttributes
0x180034047  xor     r8d, r8d; dwShareMode
0x18003404a  mov     edx, 40000000h; dwDesiredAccess
0x18003404f  mov     rcx, [rbp+ppszPathOut]; lpFileName
0x180034053  call    cs:__imp_CreateFileW
0x180034059  mov     rbx, rax
0x18003405c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180034060  jnz     short loc_18003407B
0x180034062  mov     rcx, [rbp+18h]; this
0x180034066  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x18003406d  mov     edx, 265h; void *
0x180034072  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180034077  mov     ebx, eax
0x180034079  jmp     short loc_180034017
0x18003407b  mov     dword ptr [rbp+NumberOfBytesWritten], 0
0x180034082  mov     qword ptr [rsp+40h+dwCreationDisposition], 0; lpOverlapped
0x18003408b  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003408f  mov     r8d, 4; nNumberOfBytesToWrite
0x180034095  lea     rdx, [rbp+Buffer]; lpBuffer
0x180034099  mov     rcx, rbx; hFile
0x18003409c  call    cs:__imp_WriteFile
0x1800340a2  test    eax, eax
0x1800340a4  jnz     short loc_1800340EE
0x1800340a6  mov     rcx, [rbp+18h]; this
0x1800340aa  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x1800340b1  mov     edx, 268h; void *
0x1800340b6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800340bb  mov     edi, eax
0x1800340bd  test    rbx, rbx
0x1800340c0  jz      short loc_1800340CB
0x1800340c2  mov     rcx, rbx; hObject
0x1800340c5  call    cs:__imp_CloseHandle
0x1800340cb  mov     rcx, [rbp+ppszPathOut]; hMem
0x1800340cf  test    rcx, rcx
0x1800340d2  jz      short loc_1800340DB
0x1800340d4  call    cs:__imp_LocalFree
0x1800340da  nop
0x1800340db  mov     rcx, [rbp+hMem]; hMem
0x1800340df  test    rcx, rcx
0x1800340e2  jz      short loc_1800340EA
0x1800340e4  call    cs:__imp_LocalFree
0x1800340ea  mov     eax, edi
0x1800340ec  jmp     short loc_18003414E
0x1800340ee  cmp     dword ptr [rbp+NumberOfBytesWritten], 4
0x1800340f2  jz      short loc_18003411F
0x1800340f4  mov     rcx, [rbp+18h]; this
0x1800340f8  lea     rax, aFailedToWriteD; "failed to write data to the file"
0x1800340ff  mov     qword ptr [rsp+40h+dwCreationDisposition], rax; int
0x180034104  mov     edi, 80004005h
0x180034109  mov     r9d, edi; char *
0x18003410c  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180034113  mov     edx, 26Ch; void *
0x180034118  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003411d  jmp     short loc_1800340BD
0x18003411f  test    rbx, rbx
0x180034122  jz      short loc_18003412D
0x180034124  mov     rcx, rbx; hObject
0x180034127  call    cs:__imp_CloseHandle
0x18003412d  mov     rcx, [rbp+ppszPathOut]; hMem
0x180034131  test    rcx, rcx
0x180034134  jz      short loc_18003413D
0x180034136  call    cs:__imp_LocalFree
0x18003413c  nop
0x18003413d  mov     rcx, [rbp+hMem]; hMem
0x180034141  test    rcx, rcx
0x180034144  jz      short loc_18003414C
0x180034146  call    cs:__imp_LocalFree
0x18003414c  xor     eax, eax
0x18003414e  add     rsp, 40h
0x180034152  pop     rdi
0x180034153  pop     rbx
0x180034154  pop     rbp
0x180034155  retn
```
