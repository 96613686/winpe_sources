# NlWriteBinaryLogEx

- ea: `0x180085128`
- end: `0x1800852b5`
- name: `NlWriteBinaryLogEx`
- size: `397`
- prototype: `__int64 __fastcall(wchar_t *Source, wchar_t *, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800850b0`

## callees

- `0x18000ed04`
- `0x18000ed10`
- `0x180085128`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800851b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800851b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008529c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008529c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180085157`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180085157`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008528e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008528e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800851af`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800851af`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008524a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008524a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008526f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008526f`

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
0x180085128  push    rbx
0x18008512a  push    rbp
0x18008512b  push    rsi
0x18008512c  push    rdi
0x18008512d  push    r12
0x18008512f  push    r13
0x180085131  push    r14
0x180085133  push    r15
0x180085135  sub     rsp, 58h
0x180085139  xor     r12d, r12d
0x18008513c  mov     rbp, rdx
0x18008513f  mov     rbx, rcx
0x180085142  mov     [rsp+98h+NumberOfBytesWritten], r12d
0x180085147  mov     edx, 20Ch; uBytes
0x18008514c  mov     r14d, r9d
0x18008514f  mov     r15, r8
0x180085152  lea     ecx, [r12+40h]; uFlags
0x180085157  call    cs:__imp_LocalAlloc
0x18008515d  mov     rdi, rax
0x180085160  test    rax, rax
0x180085163  jnz     short loc_18008516D
0x180085165  lea     ebx, [rax+8]
0x180085168  jmp     loc_1800852A2
0x18008516d  or      r13, 0FFFFFFFFFFFFFFFFh
0x180085171  mov     rsi, r13
0x180085174  mov     rax, r13
0x180085177  inc     rax
0x18008517a  cmp     [rbp+rax*2+0], r12w
0x180085180  jnz     short loc_180085177
0x180085182  mov     rcx, r13
0x180085185  inc     rcx
0x180085188  cmp     [rbx+rcx*2], r12w
0x18008518d  jnz     short loc_180085185
0x18008518f  inc     rax
0x180085192  add     rax, rcx
0x180085195  cmp     rax, 104h
0x18008519b  jb      short loc_1800851A7
0x18008519d  mov     ebx, 7Bh ; '{'
0x1800851a2  jmp     loc_18008528B
0x1800851a7  mov     edx, 105h; uSize
0x1800851ac  mov     rcx, rdi; lpBuffer
0x1800851af  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800851b5  test    eax, eax
0x1800851b7  jnz     short loc_1800851C6
0x1800851b9  call    cs:__imp_GetLastError
0x1800851bf  mov     ebx, eax
0x1800851c1  jmp     loc_18008528B
0x1800851c6  mov     rax, r13
0x1800851c9  inc     rax
0x1800851cc  cmp     [rbx+rax*2], r12w
0x1800851d1  jnz     short loc_1800851C9
0x1800851d3  test    rax, rax
0x1800851d6  jz      short loc_18008519D
0x1800851d8  mov     r8, rbx; Source
0x1800851db  mov     rcx, rdi; Destination
0x1800851de  mov     ebx, 106h
0x1800851e3  mov     edx, ebx; SizeInWords
0x1800851e5  call    wcscpy_s
0x1800851ea  mov     rax, r13
0x1800851ed  inc     rax
0x1800851f0  cmp     [rdi+rax*2], r12w
0x1800851f5  jnz     short loc_1800851ED
0x1800851f7  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x1800851fd  jz      short loc_180085218
0x1800851ff  cmp     word ptr [rbp+0], 5Ch ; '\'
0x180085204  jz      short loc_180085218
0x180085206  lea     r8, SubStr; "\\"
0x18008520d  mov     rdx, rbx; SizeInWords
0x180085210  mov     rcx, rdi; Destination
0x180085213  call    wcscat_s
0x180085218  mov     r8, rbp; Source
0x18008521b  mov     rdx, rbx; SizeInWords
0x18008521e  mov     rcx, rdi; Destination
0x180085221  call    wcscat_s
0x180085226  xor     r9d, r9d; lpSecurityAttributes
0x180085229  mov     [rsp+98h+hTemplateFile], r12; hTemplateFile
0x18008522e  mov     [rsp+98h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180085236  mov     edx, 0C0000000h; dwDesiredAccess
0x18008523b  mov     rcx, rdi; lpFileName
0x18008523e  mov     [rsp+98h+dwCreationDisposition], 2; dwCreationDisposition
0x180085246  lea     r8d, [r9+1]; dwShareMode
0x18008524a  call    cs:__imp_CreateFileW
0x180085250  mov     rsi, rax
0x180085253  cmp     rax, r13
0x180085256  jz      loc_1800851B9
0x18008525c  lea     r9, [rsp+98h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180085261  mov     qword ptr [rsp+98h+dwCreationDisposition], r12; lpOverlapped
0x180085266  mov     r8d, r14d; nNumberOfBytesToWrite
0x180085269  mov     rdx, r15; lpBuffer
0x18008526c  mov     rcx, rax; hFile
0x18008526f  call    cs:__imp_WriteFile
0x180085275  test    eax, eax
0x180085277  jz      loc_1800851B9
0x18008527d  mov     eax, [rsp+98h+NumberOfBytesWritten]
0x180085281  sub     eax, r14d
0x180085284  neg     eax
0x180085286  sbb     ebx, ebx
0x180085288  and     ebx, 7Ah
0x18008528b  mov     rcx, rdi; hMem
0x18008528e  call    cs:__imp_LocalFree
0x180085294  cmp     rsi, r13
0x180085297  jz      short loc_1800852A2
0x180085299  mov     rcx, rsi; hObject
0x18008529c  call    cs:__imp_CloseHandle
0x1800852a2  mov     eax, ebx
0x1800852a4  add     rsp, 58h
0x1800852a8  pop     r15
0x1800852aa  pop     r14
0x1800852ac  pop     r13
0x1800852ae  pop     r12
0x1800852b0  pop     rdi
0x1800852b1  pop     rsi
0x1800852b2  pop     rbp
0x1800852b3  pop     rbx
0x1800852b4  retn
```
