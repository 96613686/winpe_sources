# CiSetHintsForPackageCatalog2

- ea: `0x18002b69c`
- end: `0x18002b8c9`
- name: `CiSetHintsForPackageCatalog2`
- size: `557`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180024f88`

## callees

- `0x18002b69c`
- `0x18002b8d0`
- `0x18002bd24`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002b799`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002b799`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b6e7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b6e7`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18002b70b`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18002b70b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b83c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b83c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b894`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b8a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b894`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b8a9`
- `ntdll!RtlFreeHeap` at `0x18002b82e`
- `ntdll!RtlFreeHeap` at `0x18002b82e`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002b880`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002b880`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002b77b`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002b77b`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002b751`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002b751`
- `CRYPT32!CertFreeCTLContext` at `0x18002b86c`
- `CRYPT32!CertFreeCTLContext` at `0x18002b86c`
- `CRYPT32!CertCreateContext` at `0x18002b7d3`
- `CRYPT32!CertCreateContext` at `0x18002b7d3`

## pseudocode

```c
__int64 __fastcall CiSetHintsForPackageCatalog2(PCWSTR SourceString, __int64 a2)
{
  const CTL_CONTEXT *Context; // rsi
  const BYTE *v5; // r14
  void *v6; // r15
  HANDLE FileW; // rax
  void *v8; // rbp
  DWORD LowPart; // ebx
  HANDLE FileMappingW; // rax
  wchar_t *v11; // rax
  const WCHAR *v12; // rdi
  signed int CatalogHint; // ebx
  signed int LastError; // eax
  unsigned int v15; // ebx
  union _LARGE_INTEGER FileSize; // [rsp+B8h] [rbp+20h] BYREF

  FileSize.QuadPart = 0;
  Context = 0;
  v5 = 0;
  v6 = 0;
  FileW = CreateFileW(SourceString, 0x80000000, 5u, 0, 3u, 0x8000080u, 0);
  v8 = FileW;
  if ( FileW == (HANDLE)-1LL || !GetFileSizeEx(FileW, &FileSize) )
    goto LABEL_15;
  if ( FileSize.HighPart || (LowPart = FileSize.LowPart) == 0 )
  {
    CatalogHint = -1073741538;
    goto LABEL_19;
  }
  if ( (FileMappingW = CreateFileMappingW(v8, 0, 2u, 0, 0, 0), (v6 = FileMappingW) != 0)
    && (v5 = (const BYTE *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0)) != 0
    && ((v11 = wcsrchr(SourceString, 0x5Cu)) != 0 ? (v12 = v11 + 1) : (v12 = SourceString),
        (Context = (const CTL_CONTEXT *)CertCreateContext(3u, 0x10001u, v5, LowPart, 5u, 0)) != 0) )
  {
    CatalogHint = CiCreateCatalogHint(v12);
    if ( CatalogHint >= 0 )
      CatalogHint = CipSetEasForEachHint(Context->pCtlInfo, a2, 0);
  }
  else
  {
LABEL_15:
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
    CatalogHint = v15 & 0xEFFFFFFF;
    if ( CatalogHint >= 0 )
      CatalogHint = -1073741823;
  }
LABEL_19:
  if ( Context )
    CertFreeCTLContext(Context);
  if ( v5 )
    UnmapViewOfFile(v5);
  if ( v6 )
    CloseHandle(v6);
  if ( v8 != (void *)-1LL )
    CloseHandle(v8);
  return (unsigned int)CatalogHint;
}

```

## disassembly

```asm
0x18002b69c  mov     rax, rsp
0x18002b69f  push    rbx
0x18002b6a0  push    rbp
0x18002b6a1  push    rsi
0x18002b6a2  push    rdi
0x18002b6a3  push    r12
0x18002b6a5  push    r13
0x18002b6a7  push    r14
0x18002b6a9  push    r15
0x18002b6ab  sub     rsp, 58h
0x18002b6af  xor     ebx, ebx
0x18002b6b1  mov     r13, rdx
0x18002b6b4  mov     [rax-68h], rbx
0x18002b6b8  xor     r9d, r9d; lpSecurityAttributes
0x18002b6bb  mov     dword ptr [rax-70h], 8000080h
0x18002b6c2  mov     edx, 80000000h; dwDesiredAccess
0x18002b6c7  mov     r12, rcx
0x18002b6ca  mov     [rax+20h], rbx
0x18002b6ce  lea     r8d, [rbx+5]; dwShareMode
0x18002b6d2  mov     [rax-58h], rbx
0x18002b6d6  mov     esi, ebx
0x18002b6d8  mov     dword ptr [rax-78h], 3
0x18002b6df  mov     edi, ebx
0x18002b6e1  mov     r14d, ebx
0x18002b6e4  mov     r15d, ebx
0x18002b6e7  call    cs:__imp_CreateFileW
0x18002b6ee  nop     dword ptr [rax+rax+00h]
0x18002b6f3  mov     rbp, rax
0x18002b6f6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002b6fa  jz      loc_18002B83C
0x18002b700  lea     rdx, [rsp+98h+FileSize]; lpFileSize
0x18002b708  mov     rcx, rax; hFile
0x18002b70b  call    cs:__imp_GetFileSizeEx
0x18002b712  nop     dword ptr [rax+rax+00h]
0x18002b717  test    eax, eax
0x18002b719  jz      loc_18002B83C
0x18002b71f  cmp     dword ptr [rsp+98h+FileSize+4], ebx
0x18002b726  jnz     loc_18002B812
0x18002b72c  mov     rbx, qword ptr [rsp+98h+FileSize]
0x18002b734  test    ebx, ebx
0x18002b736  jz      loc_18002B812
0x18002b73c  mov     [rsp+98h+lpName], r15; lpName
0x18002b741  lea     r8d, [r15+2]; flProtect
0x18002b745  xor     r9d, r9d; dwMaximumSizeHigh
0x18002b748  mov     [rsp+98h+dwMaximumSizeLow], esi; dwMaximumSizeLow
0x18002b74c  xor     edx, edx; lpFileMappingAttributes
0x18002b74e  mov     rcx, rbp; hFile
0x18002b751  call    cs:__imp_CreateFileMappingW
0x18002b758  nop     dword ptr [rax+rax+00h]
0x18002b75d  mov     r15, rax
0x18002b760  test    rax, rax
0x18002b763  jz      loc_18002B83C
0x18002b769  xor     r9d, r9d; dwFileOffsetLow
0x18002b76c  mov     qword ptr [rsp+98h+dwMaximumSizeLow], r14; dwNumberOfBytesToMap
0x18002b771  xor     r8d, r8d; dwFileOffsetHigh
0x18002b774  lea     edx, [r14+4]; dwDesiredAccess
0x18002b778  mov     rcx, rax; hFileMappingObject
0x18002b77b  call    cs:__imp_MapViewOfFile
0x18002b782  nop     dword ptr [rax+rax+00h]
0x18002b787  mov     r14, rax
0x18002b78a  test    rax, rax
0x18002b78d  jz      loc_18002B83C
0x18002b793  lea     edx, [rdi+5Ch]; Ch
0x18002b796  mov     rcx, r12; Str
0x18002b799  call    cs:__imp_wcsrchr
0x18002b7a0  nop     dword ptr [rax+rax+00h]
0x18002b7a5  mov     rdi, rax
0x18002b7a8  test    rax, rax
0x18002b7ab  jnz     short loc_18002B7B2
0x18002b7ad  mov     rdi, r12
0x18002b7b0  jmp     short loc_18002B7B6
0x18002b7b2  add     rdi, 2
0x18002b7b6  mov     [rsp+98h+lpName], rsi; pCreatePara
0x18002b7bb  mov     r9d, ebx; cbEncoded
0x18002b7be  mov     r8, r14; pbEncoded
0x18002b7c1  mov     [rsp+98h+dwMaximumSizeLow], 5; dwFlags
0x18002b7c9  mov     edx, 10001h; dwEncodingType
0x18002b7ce  mov     ecx, 3; dwContextType
0x18002b7d3  call    cs:__imp_CertCreateContext
0x18002b7da  nop     dword ptr [rax+rax+00h]
0x18002b7df  mov     rsi, rax
0x18002b7e2  test    rax, rax
0x18002b7e5  jz      short loc_18002B83C
0x18002b7e7  lea     rdx, [rsp+98h+P]
0x18002b7ec  mov     rcx, rdi; SourceString
0x18002b7ef  call    CiCreateCatalogHint
0x18002b7f4  mov     rdi, [rsp+98h+P]
0x18002b7f9  mov     ebx, eax
0x18002b7fb  test    eax, eax
0x18002b7fd  js      short loc_18002B817
0x18002b7ff  mov     rcx, [rsi+18h]
0x18002b803  mov     r8, rdi
0x18002b806  mov     rdx, r13
0x18002b809  call    CipSetEasForEachHint
0x18002b80e  mov     ebx, eax
0x18002b810  jmp     short loc_18002B817
0x18002b812  mov     ebx, 0C000011Eh
0x18002b817  test    rdi, rdi
0x18002b81a  jz      short loc_18002B864
0x18002b81c  mov     rcx, gs:60h
0x18002b825  mov     r8, rdi; P
0x18002b828  xor     edx, edx; Flags
0x18002b82a  mov     rcx, [rcx+30h]; HeapHandle
0x18002b82e  call    cs:__imp_RtlFreeHeap
0x18002b835  nop     dword ptr [rax+rax+00h]
0x18002b83a  jmp     short loc_18002B864
0x18002b83c  call    cs:__imp_GetLastError
0x18002b843  nop     dword ptr [rax+rax+00h]
0x18002b848  mov     ebx, eax
0x18002b84a  test    eax, eax
0x18002b84c  jle     short loc_18002B857
0x18002b84e  movzx   ebx, ax
0x18002b851  or      ebx, 80070000h
0x18002b857  and     ebx, 0EFFFFFFFh
0x18002b85d  jl      short loc_18002B864
0x18002b85f  mov     ebx, 0C0000001h
0x18002b864  test    rsi, rsi
0x18002b867  jz      short loc_18002B878
0x18002b869  mov     rcx, rsi; pCtlContext
0x18002b86c  call    cs:__imp_CertFreeCTLContext
0x18002b873  nop     dword ptr [rax+rax+00h]
0x18002b878  test    r14, r14
0x18002b87b  jz      short loc_18002B88C
0x18002b87d  mov     rcx, r14; lpBaseAddress
0x18002b880  call    cs:__imp_UnmapViewOfFile
0x18002b887  nop     dword ptr [rax+rax+00h]
0x18002b88c  test    r15, r15
0x18002b88f  jz      short loc_18002B8A0
0x18002b891  mov     rcx, r15; hObject
0x18002b894  call    cs:__imp_CloseHandle
0x18002b89b  nop     dword ptr [rax+rax+00h]
0x18002b8a0  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18002b8a4  jz      short loc_18002B8B5
0x18002b8a6  mov     rcx, rbp; hObject
0x18002b8a9  call    cs:__imp_CloseHandle
0x18002b8b0  nop     dword ptr [rax+rax+00h]
0x18002b8b5  mov     eax, ebx
0x18002b8b7  add     rsp, 58h
0x18002b8bb  pop     r15
0x18002b8bd  pop     r14
0x18002b8bf  pop     r13
0x18002b8c1  pop     r12
0x18002b8c3  pop     rdi
0x18002b8c4  pop     rsi
0x18002b8c5  pop     rbp
0x18002b8c6  pop     rbx
0x18002b8c7  retn
```
