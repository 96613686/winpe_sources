# OpenMemoryFile(ushort const *,void * *,void * *)

- ea: `0x180002a64`
- end: `0x180002b0d`
- name: `?OpenMemoryFile@@YAKPEBGPEAPEAX1@Z`
- size: `169`
- prototype: `unsigned int __fastcall(LPCWSTR lpName, void **, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800023d8`
- `0x1800027f8`

## callees

- `0x180002a64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ade`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ade`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180002ad0`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180002ad0`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180002aac`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180002aac`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180002a80`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180002a80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002a95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002af2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002a95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002af2`

## pseudocode

```c
__int64 __fastcall OpenMemoryFile(LPCWSTR lpName, void **a2, LPCVOID *a3)
{
  HANDLE v6; // rax
  void *v7; // rbx
  void *v8; // rbp
  DWORD LastError; // edi

  if ( *a3 )
  {
    UnmapViewOfFile(*a3);
    *a3 = 0;
  }
  if ( *a2 )
  {
    CloseHandle(*a2);
    *a2 = 0;
  }
  v6 = OpenFileMappingW(4u, 0, lpName);
  v7 = v6;
  if ( v6 )
  {
    LastError = 0;
    v8 = MapViewOfFile(v6, 4u, 0, 0, 0);
    if ( v8 )
    {
LABEL_11:
      *a3 = v8;
      *a2 = v7;
      return LastError;
    }
  }
  else
  {
    v8 = 0;
  }
  LastError = GetLastError();
  if ( !LastError )
    goto LABEL_11;
  if ( v7 )
    CloseHandle(v7);
  return LastError;
}

```

## disassembly

```asm
0x180002a64  push    rbx
0x180002a66  push    rbp
0x180002a67  push    rsi
0x180002a68  push    rdi
0x180002a69  push    r14
0x180002a6b  sub     rsp, 30h
0x180002a6f  mov     rbx, rcx
0x180002a72  mov     r14, r8
0x180002a75  mov     rcx, [r8]; lpBaseAddress
0x180002a78  mov     rsi, rdx
0x180002a7b  test    rcx, rcx
0x180002a7e  jz      short loc_180002A8D
0x180002a80  call    cs:__imp_UnmapViewOfFile
0x180002a86  mov     qword ptr [r14], 0
0x180002a8d  mov     rcx, [rsi]; hObject
0x180002a90  test    rcx, rcx
0x180002a93  jz      short loc_180002AA2
0x180002a95  call    cs:__imp_CloseHandle
0x180002a9b  mov     qword ptr [rsi], 0
0x180002aa2  xor     edx, edx; bInheritHandle
0x180002aa4  mov     r8, rbx; lpName
0x180002aa7  lea     ebp, [rdx+4]
0x180002aaa  mov     ecx, ebp; dwDesiredAccess
0x180002aac  call    cs:__imp_OpenFileMappingW
0x180002ab2  mov     rbx, rax
0x180002ab5  test    rax, rax
0x180002ab8  jnz     short loc_180002ABE
0x180002aba  xor     ebp, ebp
0x180002abc  jmp     short loc_180002ADE
0x180002abe  xor     edi, edi
0x180002ac0  xor     r9d, r9d; dwFileOffsetLow
0x180002ac3  xor     r8d, r8d; dwFileOffsetHigh
0x180002ac6  mov     [rsp+58h+dwNumberOfBytesToMap], rdi; dwNumberOfBytesToMap
0x180002acb  mov     edx, ebp; dwDesiredAccess
0x180002acd  mov     rcx, rbx; hFileMappingObject
0x180002ad0  call    cs:__imp_MapViewOfFile
0x180002ad6  mov     rbp, rax
0x180002ad9  test    rax, rax
0x180002adc  jnz     short loc_180002AFA
0x180002ade  call    cs:__imp_GetLastError
0x180002ae4  mov     edi, eax
0x180002ae6  test    eax, eax
0x180002ae8  jz      short loc_180002AFA
0x180002aea  test    rbx, rbx
0x180002aed  jz      short loc_180002B00
0x180002aef  mov     rcx, rbx; hObject
0x180002af2  call    cs:__imp_CloseHandle
0x180002af8  jmp     short loc_180002B00
0x180002afa  mov     [r14], rbp
0x180002afd  mov     [rsi], rbx
0x180002b00  mov     eax, edi
0x180002b02  add     rsp, 30h
0x180002b06  pop     r14
0x180002b08  pop     rdi
0x180002b09  pop     rsi
0x180002b0a  pop     rbp
0x180002b0b  pop     rbx
0x180002b0c  retn
```
