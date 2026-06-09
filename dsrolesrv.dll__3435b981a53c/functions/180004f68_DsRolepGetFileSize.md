# DsRolepGetFileSize

- ea: `0x180004f68`
- end: `0x180005021`
- name: `DsRolepGetFileSize`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x1800072ec`

## callees

- `0x180004f68`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004fa3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004fa3`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180004fd6`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180004fd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fe1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000500f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000500f`

## string_xrefs

- `0x180004fbb`: `vDC Cloning: Failed to open clone config file %ws to read: 0x%x\n`
- `0x180004fea`: `vDC Cloning: Failed to get clone config file %ws size: 0x%x\n`

## pseudocode

```c
__int64 __fastcall DsRolepGetFileSize(const WCHAR *a1, DWORD *a2)
{
  HANDLE FileW; // rax
  void *v5; // rdi
  __int64 LastError; // rbx
  DWORD FileSize; // eax

  *a2 = 0;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v5 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    DsRolepLogPrintRoutine(1, "vDC Cloning: Failed to open clone config file %ws to read: 0x%x\n", a1, LastError);
  }
  else
  {
    FileSize = GetFileSize(FileW, 0);
    if ( FileSize == -1 )
    {
      LastError = GetLastError();
      DsRolepLogPrintRoutine(1, "vDC Cloning: Failed to get clone config file %ws size: 0x%x\n", a1, LastError);
    }
    else
    {
      LODWORD(LastError) = 0;
      *a2 = FileSize;
    }
    if ( v5 )
      CloseHandle(v5);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180004f68  push    rbx
0x180004f6a  push    rsi
0x180004f6b  push    rdi
0x180004f6c  push    r14
0x180004f6e  sub     rsp, 48h
0x180004f72  xor     r9d, r9d; lpSecurityAttributes
0x180004f75  mov     dword ptr [rdx], 0
0x180004f7b  mov     r14, rdx
0x180004f7e  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180004f87  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180004f8f  mov     edx, 80000000h; dwDesiredAccess
0x180004f94  mov     rsi, rcx
0x180004f97  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180004f9f  lea     r8d, [r9+1]; dwShareMode
0x180004fa3  call    cs:__imp_CreateFileW
0x180004fa9  mov     rdi, rax
0x180004fac  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004fb0  jnz     short loc_180004FD1
0x180004fb2  call    cs:__imp_GetLastError
0x180004fb8  mov     r8, rsi
0x180004fbb  lea     rdx, aVdcCloningFail; "vDC Cloning: Failed to open clone confi"...
0x180004fc2  mov     r9d, eax
0x180004fc5  lea     ecx, [rdi+2]
0x180004fc8  mov     ebx, eax
0x180004fca  call    DsRolepLogPrintRoutine
0x180004fcf  jmp     short loc_180005015
0x180004fd1  xor     edx, edx; lpFileSizeHigh
0x180004fd3  mov     rcx, rdi; hFile
0x180004fd6  call    cs:__imp_GetFileSize
0x180004fdc  cmp     eax, 0FFFFFFFFh
0x180004fdf  jnz     short loc_180005002
0x180004fe1  call    cs:__imp_GetLastError
0x180004fe7  mov     r8, rsi
0x180004fea  lea     rdx, aVdcCloningFail_0; "vDC Cloning: Failed to get clone config"...
0x180004ff1  mov     r9d, eax
0x180004ff4  mov     ecx, 1
0x180004ff9  mov     ebx, eax
0x180004ffb  call    DsRolepLogPrintRoutine
0x180005000  jmp     short loc_180005007
0x180005002  xor     ebx, ebx
0x180005004  mov     [r14], eax
0x180005007  test    rdi, rdi
0x18000500a  jz      short loc_180005015
0x18000500c  mov     rcx, rdi; hObject
0x18000500f  call    cs:__imp_CloseHandle
0x180005015  mov     eax, ebx
0x180005017  add     rsp, 48h
0x18000501b  pop     r14
0x18000501d  pop     rdi
0x18000501e  pop     rsi
0x18000501f  pop     rbx
0x180005020  retn
```
