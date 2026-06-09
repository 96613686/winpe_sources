# ICS_AppendEventToLogFile(ushort const *,char const *)

- ea: `0x1800bdbb0`
- end: `0x1800bdc9a`
- name: `?ICS_AppendEventToLogFile@@YAXPEBGPEBD@Z`
- size: `234`
- prototype: `void __fastcall(LPCWSTR lpFileName, LPCVOID lpBuffer)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800bd820`
- `0x1800f35b8`
- `0x1800f38e0`

## callees

- `0x1800bdbb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdc21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdc21`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bdc2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bdc2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bdc84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bdc84`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800bdbea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800bdbea`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800bdc18`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800bdc18`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800bdc4c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800bdc4c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800bdc6e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800bdc6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bdc77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bdc77`

## pseudocode

```c
void __fastcall ICS_AppendEventToLogFile(LPCWSTR lpFileName, _BYTE *lpBuffer)
{
  __int64 v4; // rbx
  HANDLE FileW; // rdi
  DWORD LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp+10h] BYREF

  NumberOfBytesWritten = 0;
  if ( lpBuffer )
  {
    v4 = -1;
    do
      ++v4;
    while ( lpBuffer[v4] );
  }
  else
  {
    LODWORD(v4) = 0;
  }
  AcquireSRWLockExclusive(&stru_18015D730);
  FileW = CreateFileW(lpFileName, 0xC0000000, 3u, 0, 4u, 0, 0);
  LastError = GetLastError();
  if ( FileW == (HANDLE)-1LL )
  {
    SetLastError(LastError);
  }
  else
  {
    if ( LastError != 183 || SetFilePointer(FileW, 0, 0, 2u) != -1 )
      WriteFile(FileW, lpBuffer, v4, &NumberOfBytesWritten, 0);
    CloseHandle(FileW);
  }
  ReleaseSRWLockExclusive(&stru_18015D730);
}

```

## disassembly

```asm
0x1800bdbb0  mov     [rsp+arg_0], rbx
0x1800bdbb5  mov     [rsp+arg_10], rsi
0x1800bdbba  push    rdi
0x1800bdbbb  sub     rsp, 40h
0x1800bdbbf  mov     [rsp+48h+NumberOfBytesWritten], 0
0x1800bdbc7  mov     rsi, rdx
0x1800bdbca  mov     rdi, rcx
0x1800bdbcd  test    rdx, rdx
0x1800bdbd0  jz      short loc_1800BDBE1
0x1800bdbd2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800bdbd6  inc     rbx
0x1800bdbd9  cmp     byte ptr [rdx+rbx], 0
0x1800bdbdd  jnz     short loc_1800BDBD6
0x1800bdbdf  jmp     short loc_1800BDBE3
0x1800bdbe1  xor     ebx, ebx
0x1800bdbe3  lea     rcx, stru_18015D730; SRWLock
0x1800bdbea  call    cs:__imp_AcquireSRWLockExclusive
0x1800bdbf0  xor     r9d, r9d; lpSecurityAttributes
0x1800bdbf3  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800bdbfc  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800bdc04  mov     edx, 0C0000000h; dwDesiredAccess
0x1800bdc09  mov     rcx, rdi; lpFileName
0x1800bdc0c  mov     [rsp+48h+dwCreationDisposition], 4; dwCreationDisposition
0x1800bdc14  lea     r8d, [r9+3]; dwShareMode
0x1800bdc18  call    cs:__imp_CreateFileW
0x1800bdc1e  mov     rdi, rax
0x1800bdc21  call    cs:__imp_GetLastError
0x1800bdc27  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800bdc2b  jnz     short loc_1800BDC37
0x1800bdc2d  mov     ecx, eax; dwErrCode
0x1800bdc2f  call    cs:__imp_SetLastError
0x1800bdc35  jmp     short loc_1800BDC7D
0x1800bdc37  cmp     eax, 0B7h
0x1800bdc3c  jnz     short loc_1800BDC57
0x1800bdc3e  mov     r9d, 2; dwMoveMethod
0x1800bdc44  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800bdc47  xor     edx, edx; lDistanceToMove
0x1800bdc49  mov     rcx, rdi; hFile
0x1800bdc4c  call    cs:__imp_SetFilePointer
0x1800bdc52  cmp     eax, 0FFFFFFFFh
0x1800bdc55  jz      short loc_1800BDC74
0x1800bdc57  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800bdc5c  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; lpOverlapped
0x1800bdc65  mov     r8d, ebx; nNumberOfBytesToWrite
0x1800bdc68  mov     rdx, rsi; lpBuffer
0x1800bdc6b  mov     rcx, rdi; hFile
0x1800bdc6e  call    cs:__imp_WriteFile
0x1800bdc74  mov     rcx, rdi; hObject
0x1800bdc77  call    cs:__imp_CloseHandle
0x1800bdc7d  lea     rcx, stru_18015D730; SRWLock
0x1800bdc84  call    cs:__imp_ReleaseSRWLockExclusive
0x1800bdc8a  mov     rbx, [rsp+48h+arg_0]
0x1800bdc8f  mov     rsi, [rsp+48h+arg_10]
0x1800bdc94  add     rsp, 40h
0x1800bdc98  pop     rdi
0x1800bdc99  retn
```
