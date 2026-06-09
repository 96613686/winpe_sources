# NlWriteBinaryLogEx

- ea: `0x18008b350`
- end: `0x18008b508`
- name: `NlWriteBinaryLogEx`
- size: `440`
- prototype: `__int64 __fastcall(wchar_t *Source, wchar_t *, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18008b2c0`

## callees

- `0x18000f3b4`
- `0x18000f3c0`
- `0x18008b350`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b3ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b3ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b4e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b4e8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008b37f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008b37f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008b4d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008b4d4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18008b3dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18008b3dd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008b484`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008b484`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008b4af`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008b4af`

## pseudocode

```c
__int64 __fastcall NlWriteBinaryLogEx(wchar_t *Source, wchar_t *a2, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)
{
  WCHAR *v8; // rdi
  DWORD LastError; // ebx
  __int64 v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  HANDLE FileW; // rax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-58h] BYREF

  NumberOfBytesWritten = 0;
  v8 = (WCHAR *)LocalAlloc(0x40u, 0x20Cu);
  if ( !v8 )
    return 8;
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( a2[v11] );
  v12 = -1;
  do
    ++v12;
  while ( Source[v12] );
  if ( (unsigned __int64)(v12 + v11 + 1) >= 0x104 )
    goto LABEL_8;
  if ( !GetSystemWindowsDirectoryW(v8, 0x105u) )
    goto LABEL_10;
  v13 = -1;
  do
    ++v13;
  while ( Source[v13] );
  if ( !v13 )
  {
LABEL_8:
    LastError = 123;
    goto LABEL_22;
  }
  wcscpy_s(v8, 0x106u, Source);
  v14 = -1;
  do
    ++v14;
  while ( v8[v14] );
  if ( v8[v14 - 1] != 92 && *a2 != 92 )
    wcscat_s(v8, 0x106u, L"\\");
  wcscat_s(v8, 0x106u, a2);
  FileW = CreateFileW(v8, 0xC0000000, 1u, 0, 2u, 0x80u, 0);
  v10 = (__int64)FileW;
  if ( FileW != (HANDLE)-1LL && WriteFile(FileW, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
    LastError = nNumberOfBytesToWrite != NumberOfBytesWritten ? 0x7A : 0;
  else
LABEL_10:
    LastError = GetLastError();
LABEL_22:
  LocalFree(v8);
  if ( v10 != -1 )
    CloseHandle((HANDLE)v10);
  return LastError;
}

```

## disassembly

```asm
0x18008b350  push    rbx
0x18008b352  push    rbp
0x18008b353  push    rsi
0x18008b354  push    rdi
0x18008b355  push    r12
0x18008b357  push    r13
0x18008b359  push    r14
0x18008b35b  push    r15
0x18008b35d  sub     rsp, 58h
0x18008b361  xor     r12d, r12d
0x18008b364  mov     rbp, rdx
0x18008b367  mov     rbx, rcx
0x18008b36a  mov     [rsp+98h+NumberOfBytesWritten], r12d
0x18008b36f  mov     edx, 20Ch; uBytes
0x18008b374  mov     r14d, r9d
0x18008b377  mov     r15, r8
0x18008b37a  lea     ecx, [r12+40h]; uFlags
0x18008b37f  call    cs:__imp_LocalAlloc
0x18008b386  nop     dword ptr [rax+rax+00h]
0x18008b38b  mov     rdi, rax
0x18008b38e  test    rax, rax
0x18008b391  jnz     short loc_18008B39B
0x18008b393  lea     ebx, [rax+8]
0x18008b396  jmp     loc_18008B4F4
0x18008b39b  or      r13, 0FFFFFFFFFFFFFFFFh
0x18008b39f  mov     rsi, r13
0x18008b3a2  mov     rax, r13
0x18008b3a5  inc     rax
0x18008b3a8  cmp     [rbp+rax*2+0], r12w
0x18008b3ae  jnz     short loc_18008B3A5
0x18008b3b0  mov     rcx, r13
0x18008b3b3  inc     rcx
0x18008b3b6  cmp     [rbx+rcx*2], r12w
0x18008b3bb  jnz     short loc_18008B3B3
0x18008b3bd  inc     rax
0x18008b3c0  add     rax, rcx
0x18008b3c3  cmp     rax, 104h
0x18008b3c9  jb      short loc_18008B3D5
0x18008b3cb  mov     ebx, 7Bh ; '{'
0x18008b3d0  jmp     loc_18008B4D1
0x18008b3d5  mov     edx, 105h; uSize
0x18008b3da  mov     rcx, rdi; lpBuffer
0x18008b3dd  call    cs:__imp_GetSystemWindowsDirectoryW
0x18008b3e4  nop     dword ptr [rax+rax+00h]
0x18008b3e9  test    eax, eax
0x18008b3eb  jnz     short loc_18008B400
0x18008b3ed  call    cs:__imp_GetLastError
0x18008b3f4  nop     dword ptr [rax+rax+00h]
0x18008b3f9  mov     ebx, eax
0x18008b3fb  jmp     loc_18008B4D1
0x18008b400  mov     rax, r13
0x18008b403  inc     rax
0x18008b406  cmp     [rbx+rax*2], r12w
0x18008b40b  jnz     short loc_18008B403
0x18008b40d  test    rax, rax
0x18008b410  jz      short loc_18008B3CB
0x18008b412  mov     r8, rbx; Source
0x18008b415  mov     rcx, rdi; Destination
0x18008b418  mov     ebx, 106h
0x18008b41d  mov     edx, ebx; SizeInWords
0x18008b41f  call    wcscpy_s
0x18008b424  mov     rax, r13
0x18008b427  inc     rax
0x18008b42a  cmp     [rdi+rax*2], r12w
0x18008b42f  jnz     short loc_18008B427
0x18008b431  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x18008b437  jz      short loc_18008B452
0x18008b439  cmp     word ptr [rbp+0], 5Ch ; '\'
0x18008b43e  jz      short loc_18008B452
0x18008b440  lea     r8, SubStr; "\\"
0x18008b447  mov     rdx, rbx; SizeInWords
0x18008b44a  mov     rcx, rdi; Destination
0x18008b44d  call    wcscat_s
0x18008b452  mov     r8, rbp; Source
0x18008b455  mov     rdx, rbx; SizeInWords
0x18008b458  mov     rcx, rdi; Destination
0x18008b45b  call    wcscat_s
0x18008b460  xor     r9d, r9d; lpSecurityAttributes
0x18008b463  mov     [rsp+98h+hTemplateFile], r12; hTemplateFile
0x18008b468  mov     [rsp+98h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18008b470  mov     edx, 0C0000000h; dwDesiredAccess
0x18008b475  mov     rcx, rdi; lpFileName
0x18008b478  mov     [rsp+98h+dwCreationDisposition], 2; dwCreationDisposition
0x18008b480  lea     r8d, [r9+1]; dwShareMode
0x18008b484  call    cs:__imp_CreateFileW
0x18008b48b  nop     dword ptr [rax+rax+00h]
0x18008b490  mov     rsi, rax
0x18008b493  cmp     rax, r13
0x18008b496  jz      loc_18008B3ED
0x18008b49c  lea     r9, [rsp+98h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18008b4a1  mov     qword ptr [rsp+98h+dwCreationDisposition], r12; lpOverlapped
0x18008b4a6  mov     r8d, r14d; nNumberOfBytesToWrite
0x18008b4a9  mov     rdx, r15; lpBuffer
0x18008b4ac  mov     rcx, rax; hFile
0x18008b4af  call    cs:__imp_WriteFile
0x18008b4b6  nop     dword ptr [rax+rax+00h]
0x18008b4bb  test    eax, eax
0x18008b4bd  jz      loc_18008B3ED
0x18008b4c3  mov     eax, [rsp+98h+NumberOfBytesWritten]
0x18008b4c7  sub     eax, r14d
0x18008b4ca  neg     eax
0x18008b4cc  sbb     ebx, ebx
0x18008b4ce  and     ebx, 7Ah
0x18008b4d1  mov     rcx, rdi; hMem
0x18008b4d4  call    cs:__imp_LocalFree
0x18008b4db  nop     dword ptr [rax+rax+00h]
0x18008b4e0  cmp     rsi, r13
0x18008b4e3  jz      short loc_18008B4F4
0x18008b4e5  mov     rcx, rsi; hObject
0x18008b4e8  call    cs:__imp_CloseHandle
0x18008b4ef  nop     dword ptr [rax+rax+00h]
0x18008b4f4  mov     eax, ebx
0x18008b4f6  add     rsp, 58h
0x18008b4fa  pop     r15
0x18008b4fc  pop     r14
0x18008b4fe  pop     r13
0x18008b500  pop     r12
0x18008b502  pop     rdi
0x18008b503  pop     rsi
0x18008b504  pop     rbp
0x18008b505  pop     rbx
0x18008b506  retn
```
