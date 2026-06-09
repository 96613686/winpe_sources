# SymAddSourceStreamW

- ea: `0x1801a4d80`
- end: `0x1801a4eea`
- name: `SymAddSourceStreamW`
- size: `362`
- prototype: `BOOL __stdcall(HANDLE hProcess, ULONG64 Base, PCWSTR FileSpec, PBYTE Buffer, size_t Size)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x1801a4d20`

## callees

- `0x1800089f0`
- `0x180008ad0`
- `0x18000982c`
- `0x18000aeec`
- `0x180169420`
- `0x18019f648`
- `0x1801a4d80`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801a4e85`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801a4e85`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1801a4e29`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1801a4e29`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801a4e15`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801a4e15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a4e43`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a4e43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a4e38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a4ea5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a4e38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a4ea5`

## pseudocode

```c
BOOL __stdcall SymAddSourceStreamW(HANDLE hProcess, ULONG64 Base, PCWSTR FileSpec, PBYTE Buffer, size_t Size)
{
  SIZE_T v5; // rdi
  struct _PROCESS_ENTRY *ProcessEntry; // rax
  struct _PROCESS_ENTRY *v10; // r14
  DWORD v11; // ecx
  struct _MODULE_ENTRY *ModuleForDLLBase; // r15
  HANDLE FileW; // rax
  void *v14; // rsi
  DWORD FileSize; // eax
  DWORD v16; // ebp
  void *v18; // rax
  void *v19; // rbx
  void *v20; // rax
  DWORD NumberOfBytesRead; // [rsp+90h] [rbp+18h] BYREF

  v5 = Size;
  NumberOfBytesRead = 0;
  if ( !FileSpec && (!Buffer || !Size) )
    goto LABEL_12;
  ProcessEntry = FindProcessEntry(hProcess);
  v10 = ProcessEntry;
  if ( !ProcessEntry )
  {
    v11 = 6;
LABEL_13:
    SetLastError(v11);
    return 0;
  }
  ModuleForDLLBase = GetModuleForDLLBase(ProcessEntry, Base);
  if ( !ModuleForDLLBase )
  {
    v11 = 126;
    goto LABEL_13;
  }
  if ( Buffer )
  {
    v20 = (void *)pMemAlloc(v5);
    v19 = v20;
    if ( !v20 )
      goto LABEL_12;
    memcpy_0(v20, Buffer, v5);
  }
  else
  {
    FileW = CreateFileW(FileSpec, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    v14 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
LABEL_12:
      v11 = 87;
      goto LABEL_13;
    }
    FileSize = GetFileSize(FileW, 0);
    v16 = FileSize;
    if ( !FileSize )
    {
      CloseHandle(v14);
      goto LABEL_12;
    }
    v5 = FileSize;
    v18 = (void *)pMemAlloc(FileSize);
    v19 = v18;
    if ( v18 && ReadFile(v14, v18, v16, &NumberOfBytesRead, 0) && NumberOfBytesRead != v16 )
    {
      FreeIt(v19);
      v19 = 0;
    }
    CloseHandle(v14);
    if ( !v19 )
      goto LABEL_12;
  }
  return srcsrvLoadModule(v10, ModuleForDLLBase, (unsigned __int8 *)v19, v5);
}

```

## disassembly

```asm
0x1801a4d80  mov     rax, rsp
0x1801a4d83  push    rbx
0x1801a4d84  push    rbp
0x1801a4d85  push    rsi
0x1801a4d86  push    rdi
0x1801a4d87  push    r14
0x1801a4d89  push    r15
0x1801a4d8b  sub     rsp, 48h
0x1801a4d8f  mov     rdi, [rsp+78h+Size]
0x1801a4d97  mov     rsi, r9
0x1801a4d9a  mov     dword ptr [rax+18h], 0
0x1801a4da1  mov     rbx, r8
0x1801a4da4  mov     rbp, rdx
0x1801a4da7  test    r8, r8
0x1801a4daa  jnz     short loc_1801A4DBE
0x1801a4dac  test    r9, r9
0x1801a4daf  jz      loc_1801A4E3E
0x1801a4db5  test    rdi, rdi
0x1801a4db8  jz      loc_1801A4E3E
0x1801a4dbe  call    ?FindProcessEntry@@YAPEAU_PROCESS_ENTRY@@PEAX@Z; FindProcessEntry(void *)
0x1801a4dc3  mov     r14, rax
0x1801a4dc6  test    rax, rax
0x1801a4dc9  jnz     short loc_1801A4DD0
0x1801a4dcb  lea     ecx, [rax+6]
0x1801a4dce  jmp     short loc_1801A4E43
0x1801a4dd0  mov     rdx, rbp; unsigned __int64
0x1801a4dd3  mov     rcx, r14; struct _PROCESS_ENTRY *
0x1801a4dd6  call    ?GetModuleForDLLBase@@YAPEAU_MODULE_ENTRY@@PEAU_PROCESS_ENTRY@@_K@Z; GetModuleForDLLBase(_PROCESS_ENTRY *,unsigned __int64)
0x1801a4ddb  mov     r15, rax
0x1801a4dde  test    rax, rax
0x1801a4de1  jnz     short loc_1801A4DE8
0x1801a4de3  lea     ecx, [rax+7Eh]
0x1801a4de6  jmp     short loc_1801A4E43
0x1801a4de8  test    rsi, rsi
0x1801a4deb  jnz     loc_1801A4EB2
0x1801a4df1  mov     [rsp+78h+hTemplateFile], rsi; hTemplateFile
0x1801a4df6  lea     r8d, [rsi+1]; dwShareMode
0x1801a4dfa  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1801a4e02  xor     r9d, r9d; lpSecurityAttributes
0x1801a4e05  mov     edx, 80000000h; dwDesiredAccess
0x1801a4e0a  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x1801a4e12  mov     rcx, rbx; lpFileName
0x1801a4e15  call    cs:__imp_CreateFileW
0x1801a4e1b  mov     rsi, rax
0x1801a4e1e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801a4e22  jz      short loc_1801A4E3E
0x1801a4e24  xor     edx, edx; lpFileSizeHigh
0x1801a4e26  mov     rcx, rax; hFile
0x1801a4e29  call    cs:__imp_GetFileSize
0x1801a4e2f  mov     ebp, eax
0x1801a4e31  test    eax, eax
0x1801a4e33  jnz     short loc_1801A4E58
0x1801a4e35  mov     rcx, rsi; hObject
0x1801a4e38  call    cs:__imp_CloseHandle
0x1801a4e3e  mov     ecx, 57h ; 'W'; dwErrCode
0x1801a4e43  call    cs:__imp_SetLastError
0x1801a4e49  xor     eax, eax
0x1801a4e4b  add     rsp, 48h
0x1801a4e4f  pop     r15
0x1801a4e51  pop     r14
0x1801a4e53  pop     rdi
0x1801a4e54  pop     rsi
0x1801a4e55  pop     rbp
0x1801a4e56  pop     rbx
0x1801a4e57  retn
0x1801a4e58  mov     rcx, rbp; dwBytes
0x1801a4e5b  mov     rdi, rbp
0x1801a4e5e  call    pMemAlloc
0x1801a4e63  mov     rbx, rax
0x1801a4e66  test    rax, rax
0x1801a4e69  jz      short loc_1801A4EA2
0x1801a4e6b  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1801a4e73  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; lpOverlapped
0x1801a4e7c  mov     r8d, ebp; nNumberOfBytesToRead
0x1801a4e7f  mov     rdx, rax; lpBuffer
0x1801a4e82  mov     rcx, rsi; hFile
0x1801a4e85  call    cs:__imp_ReadFile
0x1801a4e8b  test    eax, eax
0x1801a4e8d  jz      short loc_1801A4EA2
0x1801a4e8f  cmp     [rsp+78h+NumberOfBytesRead], ebp
0x1801a4e96  jz      short loc_1801A4EA2
0x1801a4e98  mov     rcx, rbx; lpMem
0x1801a4e9b  call    ?FreeIt@@YAXPEAX@Z; FreeIt(void *)
0x1801a4ea0  xor     ebx, ebx
0x1801a4ea2  mov     rcx, rsi; hObject
0x1801a4ea5  call    cs:__imp_CloseHandle
0x1801a4eab  test    rbx, rbx
0x1801a4eae  jz      short loc_1801A4E3E
0x1801a4eb0  jmp     short loc_1801A4ED4
0x1801a4eb2  mov     rcx, rdi; dwBytes
0x1801a4eb5  call    pMemAlloc
0x1801a4eba  mov     rbx, rax
0x1801a4ebd  test    rax, rax
0x1801a4ec0  jz      loc_1801A4E3E
0x1801a4ec6  mov     r8, rdi; Size
0x1801a4ec9  mov     rdx, rsi; Src
0x1801a4ecc  mov     rcx, rax; void *
0x1801a4ecf  call    memcpy_0
0x1801a4ed4  mov     r9, rdi; unsigned __int64
0x1801a4ed7  mov     r8, rbx; unsigned __int8 *
0x1801a4eda  mov     rdx, r15; struct _MODULE_ENTRY *
0x1801a4edd  mov     rcx, r14; struct _PROCESS_ENTRY *
0x1801a4ee0  call    ?srcsrvLoadModule@@YAHPEAU_PROCESS_ENTRY@@PEAU_MODULE_ENTRY@@PEAE_K@Z; srcsrvLoadModule(_PROCESS_ENTRY *,_MODULE_ENTRY *,uchar *,unsigned __int64)
0x1801a4ee5  jmp     loc_1801A4E4B
```
