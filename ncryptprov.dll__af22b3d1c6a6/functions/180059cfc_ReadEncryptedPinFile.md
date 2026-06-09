# ReadEncryptedPinFile

- ea: `0x180059cfc`
- end: `0x180059eca`
- name: `ReadEncryptedPinFile`
- size: `462`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *, DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800597f0`

## callees

- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x180059bd4`
- `0x180059cfc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059d8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059dd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059e5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059d8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059dd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059e5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059eb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059eb1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180059e4f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180059e4f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180059d76`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180059d76`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180059dc1`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180059dc1`

## string_xrefs

- `0x180059d3f`: `onecore\ds\security\cryptoapi\ncrypt\storage\encryptedpinfile.c`
- `0x180059d9d`: `onecore\ds\security\cryptoapi\ncrypt\storage\encryptedpinfile.c`
- `0x180059de8`: `onecore\ds\security\cryptoapi\ncrypt\storage\encryptedpinfile.c`

## pseudocode

```c
__int64 __fastcall ReadEncryptedPinFile(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4, DWORD *a5)
{
  void *v6; // rdi
  int PinFileFullPath; // eax
  signed int v8; // ebx
  __int64 v9; // rsi
  __int64 v10; // r9
  __int64 v11; // rcx
  HANDLE FileW; // rax
  DWORD LastError; // eax
  DWORD FileSize; // eax
  DWORD v15; // eax
  __int64 v16; // r9
  void *v17; // rax
  DWORD v18; // edx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-38h] BYREF
  LPCWSTR lpFileName[6]; // [rsp+48h] [rbp-30h] BYREF

  lpFileName[0] = 0;
  NumberOfBytesRead = 0;
  v6 = 0;
  PinFileFullPath = GetPinFileFullPath(a1, a2, a3, lpFileName);
  v8 = PinFileFullPath;
  if ( PinFileFullPath < 0 )
  {
    v9 = -1;
    v10 = 428;
    v11 = (unsigned int)PinFileFullPath;
LABEL_3:
    DebugTraceError(v11, "hr", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\encryptedpinfile.c", v10);
    goto LABEL_15;
  }
  FileW = CreateFileW(lpFileName[0], 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  v9 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    DebugTraceError(LastError, "dwReturn", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\encryptedpinfile.c", 444);
    v8 = -2146893811;
    goto LABEL_15;
  }
  FileSize = GetFileSize(FileW, 0);
  NumberOfBytesRead = FileSize;
  if ( FileSize == -1 )
  {
    v15 = GetLastError();
    v16 = 455;
  }
  else
  {
    v17 = (void *)SafeAllocaAllocateFromHeap(FileSize);
    v6 = v17;
    if ( !v17 )
    {
      v8 = -2146893810;
      v10 = 464;
      v11 = 2148073486LL;
      goto LABEL_3;
    }
    if ( ReadFile((HANDLE)v9, v17, NumberOfBytesRead, &NumberOfBytesRead, 0) )
    {
      v18 = NumberOfBytesRead;
      *a4 = v6;
      v6 = 0;
      *a5 = v18;
      goto LABEL_15;
    }
    v15 = GetLastError();
    v16 = 476;
  }
  v8 = v15;
  DebugTraceError(v15, "dwReturn", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\encryptedpinfile.c", v16);
  if ( v8 > 0 )
    v8 = (unsigned __int16)v8 | 0x80070000;
LABEL_15:
  if ( lpFileName[0] )
    MSCryptFree(lpFileName[0]);
  if ( v6 )
    MSCryptFree(v6);
  if ( v9 != -1 )
    CloseHandle((HANDLE)v9);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180059cfc  push    rbx
0x180059cfe  push    rsi
0x180059cff  push    rdi
0x180059d00  push    r14
0x180059d02  sub     rsp, 58h
0x180059d06  mov     r14, r9
0x180059d09  mov     [rsp+78h+lpFileName], 0
0x180059d12  lea     r9, [rsp+78h+lpFileName]
0x180059d17  mov     [rsp+78h+NumberOfBytesRead], 0
0x180059d1f  xor     edi, edi
0x180059d21  call    GetPinFileFullPath
0x180059d26  mov     ebx, eax
0x180059d28  test    eax, eax
0x180059d2a  jns     short loc_180059D50
0x180059d2c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180059d30  mov     r9d, 1ACh
0x180059d36  mov     ecx, eax
0x180059d38  lea     rdx, aHr; "hr"
0x180059d3f  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180059d46  call    DebugTraceError
0x180059d4b  jmp     loc_180059E89
0x180059d50  mov     rcx, [rsp+78h+lpFileName]; lpFileName
0x180059d55  xor     r9d, r9d; lpSecurityAttributes
0x180059d58  mov     [rsp+78h+hTemplateFile], rdi; hTemplateFile
0x180059d5d  mov     edx, 80000000h; dwDesiredAccess
0x180059d62  mov     [rsp+78h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x180059d6a  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180059d72  lea     r8d, [r9+1]; dwShareMode
0x180059d76  call    cs:__imp_CreateFileW
0x180059d7d  nop     dword ptr [rax+rax+00h]
0x180059d82  mov     rsi, rax
0x180059d85  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180059d89  jnz     short loc_180059DBC
0x180059d8b  call    cs:__imp_GetLastError
0x180059d92  nop     dword ptr [rax+rax+00h]
0x180059d97  mov     r9d, 1BCh
0x180059d9d  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180059da4  mov     ecx, eax
0x180059da6  lea     rdx, aDwreturn; "dwReturn"
0x180059dad  call    DebugTraceError
0x180059db2  mov     ebx, 8009000Dh
0x180059db7  jmp     loc_180059E89
0x180059dbc  xor     edx, edx; lpFileSizeHigh
0x180059dbe  mov     rcx, rsi; hFile
0x180059dc1  call    cs:__imp_GetFileSize
0x180059dc8  nop     dword ptr [rax+rax+00h]
0x180059dcd  mov     [rsp+78h+NumberOfBytesRead], eax
0x180059dd1  cmp     eax, 0FFFFFFFFh
0x180059dd4  jnz     short loc_180059E12
0x180059dd6  call    cs:__imp_GetLastError
0x180059ddd  nop     dword ptr [rax+rax+00h]
0x180059de2  mov     r9d, 1C7h
0x180059de8  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180059def  mov     ecx, eax
0x180059df1  lea     rdx, aDwreturn; "dwReturn"
0x180059df8  mov     ebx, eax
0x180059dfa  call    DebugTraceError
0x180059dff  test    ebx, ebx
0x180059e01  jle     loc_180059E89
0x180059e07  movzx   ebx, bx
0x180059e0a  or      ebx, 80070000h
0x180059e10  jmp     short loc_180059E89
0x180059e12  mov     ecx, eax
0x180059e14  call    SafeAllocaAllocateFromHeap
0x180059e19  mov     rdi, rax
0x180059e1c  test    rax, rax
0x180059e1f  jnz     short loc_180059E36
0x180059e21  mov     ebx, 8009000Eh
0x180059e26  mov     r9d, 1D0h
0x180059e2c  mov     ecx, 8009000Eh
0x180059e31  jmp     loc_180059D38
0x180059e36  mov     r8d, [rsp+78h+NumberOfBytesRead]; nNumberOfBytesToRead
0x180059e3b  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180059e40  mov     rdx, rdi; lpBuffer
0x180059e43  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; lpOverlapped
0x180059e4c  mov     rcx, rsi; hFile
0x180059e4f  call    cs:__imp_ReadFile
0x180059e56  nop     dword ptr [rax+rax+00h]
0x180059e5b  test    eax, eax
0x180059e5d  jnz     short loc_180059E76
0x180059e5f  call    cs:__imp_GetLastError
0x180059e66  nop     dword ptr [rax+rax+00h]
0x180059e6b  mov     r9d, 1DCh
0x180059e71  jmp     loc_180059DE8
0x180059e76  mov     rax, [rsp+78h+arg_20]
0x180059e7e  mov     edx, [rsp+78h+NumberOfBytesRead]
0x180059e82  mov     [r14], rdi
0x180059e85  xor     edi, edi
0x180059e87  mov     [rax], edx
0x180059e89  cmp     [rsp+78h+lpFileName], 0
0x180059e8f  jz      short loc_180059E9B
0x180059e91  mov     rcx, [rsp+78h+lpFileName]
0x180059e96  call    MSCryptFree
0x180059e9b  test    rdi, rdi
0x180059e9e  jz      short loc_180059EA8
0x180059ea0  mov     rcx, rdi
0x180059ea3  call    MSCryptFree
0x180059ea8  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180059eac  jz      short loc_180059EBD
0x180059eae  mov     rcx, rsi; hObject
0x180059eb1  call    cs:__imp_CloseHandle
0x180059eb8  nop     dword ptr [rax+rax+00h]
0x180059ebd  mov     eax, ebx
0x180059ebf  add     rsp, 58h
0x180059ec3  pop     r14
0x180059ec5  pop     rdi
0x180059ec6  pop     rsi
0x180059ec7  pop     rbx
0x180059ec8  retn
```
