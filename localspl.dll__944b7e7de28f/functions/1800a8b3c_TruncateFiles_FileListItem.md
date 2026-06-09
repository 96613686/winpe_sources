# TruncateFiles(FileListItem *)

- ea: `0x1800a8b3c`
- end: `0x1800a8cf2`
- name: `?TruncateFiles@@YAXPEAUFileListItem@@@Z`
- size: `438`
- prototype: `void __fastcall(struct FileListItem *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800a899c`

## callees

- `0x18003ea2c`
- `0x1800a8b3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a8b56`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a8b56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a8ce3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a8ce3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8b92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8bb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8bf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8c46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8c95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8b92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8bb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8bf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8c46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8c95`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a8c15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a8c15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8bef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8bef`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a8bdc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a8bdc`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800a8b84`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800a8c3c`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800a8c8b`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800a8b84`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800a8c3c`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800a8c8b`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800a8b71`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800a8c2d`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800a8c7d`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800a8cd9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800a8b71`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800a8c2d`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800a8c7d`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800a8cd9`

## string_xrefs

- `0x1800a8c00`: `CreateFile in TruncateFiles() failed with error code %d`

## pseudocode

```c
void __fastcall TruncateFiles(struct FileListItem *a1)
{
  int v2; // esi
  void *v3; // rcx
  DWORD v4; // eax
  DWORD LastError; // ebx
  char *FileW; // rax
  DWORD v7; // eax
  void *v8; // rcx
  DWORD v9; // eax
  HANDLE *v10; // rbx
  DWORD v11; // eax

  if ( a1 )
  {
    v2 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 24));
    v3 = (void *)*((_QWORD *)a1 + 13);
    *((_DWORD *)a1 + 28) = 0;
    if ( v3 == (void *)-1LL )
    {
      LastError = GetLastError();
      FileW = (char *)CreateFileW(*((LPCWSTR *)a1 + 10), 0x40000000u, 0, 0, 5u, 0x80u, 0);
      if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        v7 = GetLastError();
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "TruncateFiles",
          L"CreateFile in TruncateFiles() failed with error code %d",
          v7);
      }
      else
      {
        CloseHandle(FileW);
      }
      SetLastError(LastError);
    }
    else if ( SetFilePointer(v3, 0, 0, 0) != -1 && !SetEndOfFile(*((HANDLE *)a1 + 13)) )
    {
      v4 = GetLastError();
      LocalSpoolerTelemetry::WriteDbgTraceError("TruncateFiles", L"SetEndOfFile failed with error code %d", v4);
    }
    v8 = (void *)*((_QWORD *)a1 + 11);
    if ( v8 == (void *)-1LL )
    {
      v10 = (HANDLE *)((char *)a1 + 96);
      if ( *((_QWORD *)a1 + 12) == -1 )
      {
LABEL_23:
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 24));
        return;
      }
      if ( SetFilePointer(*v10, 0, 0, 0) != -1 && !SetEndOfFile(*v10) )
      {
        v11 = GetLastError();
        LocalSpoolerTelemetry::WriteDbgTraceError("TruncateFiles", L"SetEndOfFile failed with error code %d", v11);
      }
      v2 = 1;
      *((_QWORD *)a1 + 11) = *v10;
      *v10 = (HANDLE)-1LL;
    }
    else
    {
      if ( SetFilePointer(v8, 0, 0, 0) != -1 && !SetEndOfFile(*((HANDLE *)a1 + 11)) )
      {
        v9 = GetLastError();
        LocalSpoolerTelemetry::WriteDbgTraceError("TruncateFiles", L"SetEndOfFile failed with error code %d", v9);
      }
      v10 = (HANDLE *)((char *)a1 + 96);
    }
    if ( *v10 != (HANDLE)-1LL && !v2 )
      SetFilePointer(*v10, 0, 0, 0);
    goto LABEL_23;
  }
}

```

## disassembly

```asm
0x1800a8b3c  test    rcx, rcx
0x1800a8b3f  jz      locret_1800A8CF1
0x1800a8b45  push    rbx
0x1800a8b46  push    rbp
0x1800a8b47  push    rsi
0x1800a8b48  push    rdi
0x1800a8b49  sub     rsp, 48h
0x1800a8b4d  mov     rdi, rcx
0x1800a8b50  xor     esi, esi
0x1800a8b52  add     rcx, 18h; lpCriticalSection
0x1800a8b56  call    cs:__imp_EnterCriticalSection
0x1800a8b5c  mov     rcx, [rdi+68h]; hFile
0x1800a8b60  mov     [rdi+70h], esi
0x1800a8b63  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800a8b67  jz      short loc_1800A8BB0
0x1800a8b69  xor     r9d, r9d; dwMoveMethod
0x1800a8b6c  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800a8b6f  xor     edx, edx; lDistanceToMove
0x1800a8b71  call    cs:__imp_SetFilePointer
0x1800a8b77  cmp     eax, 0FFFFFFFFh
0x1800a8b7a  jz      loc_1800A8C1B
0x1800a8b80  mov     rcx, [rdi+68h]; hFile
0x1800a8b84  call    cs:__imp_SetEndOfFile
0x1800a8b8a  test    eax, eax
0x1800a8b8c  jnz     loc_1800A8C1B
0x1800a8b92  call    cs:__imp_GetLastError
0x1800a8b98  mov     r8d, eax
0x1800a8b9b  lea     rdx, aSetendoffileFa; "SetEndOfFile failed with error code %d"
0x1800a8ba2  lea     rcx, aTruncatefiles; "TruncateFiles"
0x1800a8ba9  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800a8bae  jmp     short loc_1800A8C1B
0x1800a8bb0  call    cs:__imp_GetLastError
0x1800a8bb6  mov     rcx, [rdi+50h]; lpFileName
0x1800a8bba  xor     r9d, r9d; lpSecurityAttributes
0x1800a8bbd  mov     [rsp+68h+hTemplateFile], rsi; hTemplateFile
0x1800a8bc2  xor     r8d, r8d; dwShareMode
0x1800a8bc5  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800a8bcd  mov     edx, 40000000h; dwDesiredAccess
0x1800a8bd2  mov     ebx, eax
0x1800a8bd4  mov     [rsp+68h+dwCreationDisposition], 5; dwCreationDisposition
0x1800a8bdc  call    cs:__imp_CreateFileW
0x1800a8be2  lea     rcx, [rax-1]
0x1800a8be6  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800a8bea  ja      short loc_1800A8BF7
0x1800a8bec  mov     rcx, rax; hObject
0x1800a8bef  call    cs:__imp_CloseHandle
0x1800a8bf5  jmp     short loc_1800A8C13
0x1800a8bf7  call    cs:__imp_GetLastError
0x1800a8bfd  mov     r8d, eax
0x1800a8c00  lea     rdx, aCreatefileInTr; "CreateFile in TruncateFiles() failed wi"...
0x1800a8c07  lea     rcx, aTruncatefiles; "TruncateFiles"
0x1800a8c0e  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800a8c13  mov     ecx, ebx; dwErrCode
0x1800a8c15  call    cs:__imp_SetLastError
0x1800a8c1b  mov     rcx, [rdi+58h]; hFile
0x1800a8c1f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800a8c23  jz      short loc_1800A8C68
0x1800a8c25  xor     r9d, r9d; dwMoveMethod
0x1800a8c28  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800a8c2b  xor     edx, edx; lDistanceToMove
0x1800a8c2d  call    cs:__imp_SetFilePointer
0x1800a8c33  cmp     eax, 0FFFFFFFFh
0x1800a8c36  jz      short loc_1800A8C62
0x1800a8c38  mov     rcx, [rdi+58h]; hFile
0x1800a8c3c  call    cs:__imp_SetEndOfFile
0x1800a8c42  test    eax, eax
0x1800a8c44  jnz     short loc_1800A8C62
0x1800a8c46  call    cs:__imp_GetLastError
0x1800a8c4c  mov     r8d, eax
0x1800a8c4f  lea     rdx, aSetendoffileFa; "SetEndOfFile failed with error code %d"
0x1800a8c56  lea     rcx, aTruncatefiles; "TruncateFiles"
0x1800a8c5d  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800a8c62  lea     rbx, [rdi+60h]
0x1800a8c66  jmp     short loc_1800A8CC4
0x1800a8c68  lea     rbx, [rdi+60h]
0x1800a8c6c  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1800a8c70  jz      short loc_1800A8CDF
0x1800a8c72  mov     rcx, [rbx]; hFile
0x1800a8c75  xor     r9d, r9d; dwMoveMethod
0x1800a8c78  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800a8c7b  xor     edx, edx; lDistanceToMove
0x1800a8c7d  call    cs:__imp_SetFilePointer
0x1800a8c83  cmp     eax, 0FFFFFFFFh
0x1800a8c86  jz      short loc_1800A8CB1
0x1800a8c88  mov     rcx, [rbx]; hFile
0x1800a8c8b  call    cs:__imp_SetEndOfFile
0x1800a8c91  test    eax, eax
0x1800a8c93  jnz     short loc_1800A8CB1
0x1800a8c95  call    cs:__imp_GetLastError
0x1800a8c9b  mov     r8d, eax
0x1800a8c9e  lea     rdx, aSetendoffileFa; "SetEndOfFile failed with error code %d"
0x1800a8ca5  lea     rcx, aTruncatefiles; "TruncateFiles"
0x1800a8cac  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800a8cb1  mov     rax, [rbx]
0x1800a8cb4  mov     esi, 1
0x1800a8cb9  mov     [rdi+58h], rax
0x1800a8cbd  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1800a8cc4  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1800a8cc8  jz      short loc_1800A8CDF
0x1800a8cca  test    esi, esi
0x1800a8ccc  jnz     short loc_1800A8CDF
0x1800a8cce  mov     rcx, [rbx]; hFile
0x1800a8cd1  xor     r9d, r9d; dwMoveMethod
0x1800a8cd4  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800a8cd7  xor     edx, edx; lDistanceToMove
0x1800a8cd9  call    cs:__imp_SetFilePointer
0x1800a8cdf  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800a8ce3  call    cs:__imp_LeaveCriticalSection
0x1800a8ce9  add     rsp, 48h
0x1800a8ced  pop     rdi
0x1800a8cee  pop     rsi
0x1800a8cef  pop     rbp
0x1800a8cf0  pop     rbx
0x1800a8cf1  retn
```
