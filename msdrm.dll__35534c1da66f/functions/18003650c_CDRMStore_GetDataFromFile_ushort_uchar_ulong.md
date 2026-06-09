# CDRMStore::GetDataFromFile(ushort *,uchar *,ulong *)

- ea: `0x18003650c`
- end: `0x18003667e`
- name: `?GetDataFromFile@CDRMStore@@AEAAJPEAGPEAEPEAK@Z`
- size: `370`
- prototype: `__int64 __fastcall(CDRMStore *__hidden this, LPCWSTR lpFileName, unsigned __int8 *lpBuffer, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180036684`

## callees

- `0x180034e44`
- `0x18003650c`
- `0x180037e18`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800365ff`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003662e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003665d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800365ff`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003662e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003665d`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180036589`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180036589`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003656d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036596`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003656d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036596`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800365c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800365c8`

## pseudocode

```c
__int64 __fastcall CDRMStore::GetDataFromFile(
        CDRMStore *this,
        WCHAR *lpFileName,
        unsigned __int8 *lpBuffer,
        unsigned int *a4)
{
  unsigned int v8; // ebx
  int v9; // eax
  HANDLE v10; // rbp
  signed int LastError; // eax
  unsigned int FileSize; // edi
  signed int v13; // eax
  unsigned int v15; // r14d
  HANDLE hFile; // [rsp+30h] [rbp-48h] BYREF

  hFile = (HANDLE)-1LL;
  if ( DRMOS::GetFileAttributesA(lpFileName, lpFileName) == -1 )
    return (unsigned int)-2147168461;
  v9 = CDRMStore::CreateFileForReadWrite(this, lpFileName, 0, &hFile);
  v10 = hFile;
  v8 = v9;
  if ( v9 < 0 )
    goto LABEL_14;
  if ( hFile == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return v8;
  }
  FileSize = GetFileSize(hFile, 0);
  if ( FileSize == -1 )
    goto LABEL_8;
  if ( !lpBuffer )
    goto LABEL_13;
  if ( *a4 < FileSize )
  {
    v8 = -2147024774;
LABEL_13:
    *a4 = FileSize;
    goto LABEL_14;
  }
  LODWORD(hFile) = 0;
  if ( !ReadFile(v10, lpBuffer, 2u, (LPDWORD)&hFile, 0) )
    goto LABEL_8;
  if ( *lpBuffer == 0xFF && lpBuffer[1] == 0xFE )
  {
    FileSize -= 2;
    if ( !ReadFile(v10, lpBuffer, FileSize, (LPDWORD)&hFile, 0) )
      goto LABEL_8;
    v15 = FileSize;
  }
  else
  {
    v15 = FileSize - 2;
    if ( !ReadFile(v10, lpBuffer + 2, FileSize - 2, (LPDWORD)&hFile, 0) )
      goto LABEL_8;
  }
  *a4 = FileSize;
  if ( (unsigned int)hFile < v15 )
  {
LABEL_8:
    v13 = GetLastError();
    v8 = v13;
    if ( v13 > 0 )
      v8 = (unsigned __int16)v13 | 0x80070000;
  }
LABEL_14:
  if ( v10 != (HANDLE)-1LL )
    CloseHandle(v10);
  return v8;
}

```

## disassembly

```asm
0x18003650c  push    rbx
0x18003650e  push    rbp
0x18003650f  push    rsi
0x180036510  push    rdi
0x180036511  push    r14
0x180036513  push    r15
0x180036515  sub     rsp, 48h
0x180036519  mov     rdi, rcx
0x18003651c  mov     [rsp+78h+hFile], 0FFFFFFFFFFFFFFFFh
0x180036525  mov     rcx, rdx; lpFileName
0x180036528  mov     r15, r9
0x18003652b  mov     rsi, r8
0x18003652e  mov     rbx, rdx
0x180036531  call    ?GetFileAttributesA@DRMOS@@YAKPEBG@Z; DRMOS::GetFileAttributesA(ushort const *)
0x180036536  or      r14d, 0FFFFFFFFh
0x18003653a  cmp     eax, r14d
0x18003653d  jnz     short loc_180036549
0x18003653f  mov     ebx, 8004CF33h
0x180036544  jmp     loc_1800365CE
0x180036549  lea     r9, [rsp+78h+hFile]; void **
0x18003654e  xor     r8d, r8d; int
0x180036551  mov     rdx, rbx; unsigned __int16 *
0x180036554  mov     rcx, rdi; this
0x180036557  call    ?CreateFileForReadWrite@CDRMStore@@AEAAJPEAGHPEAPEAX@Z; CDRMStore::CreateFileForReadWrite(ushort *,int,void * *)
0x18003655c  mov     rbp, [rsp+78h+hFile]
0x180036561  mov     ebx, eax
0x180036563  test    eax, eax
0x180036565  js      short loc_1800365BF
0x180036567  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18003656b  jnz     short loc_180036584
0x18003656d  call    cs:__imp_GetLastError
0x180036573  mov     ebx, eax
0x180036575  test    eax, eax
0x180036577  jle     short loc_1800365CE
0x180036579  movzx   ebx, ax
0x18003657c  or      ebx, 80070000h
0x180036582  jmp     short loc_1800365CE
0x180036584  xor     edx, edx; lpFileSizeHigh
0x180036586  mov     rcx, rbp; hFile
0x180036589  call    cs:__imp_GetFileSize
0x18003658f  mov     edi, eax
0x180036591  cmp     eax, r14d
0x180036594  jnz     short loc_1800365AD
0x180036596  call    cs:__imp_GetLastError
0x18003659c  mov     ebx, eax
0x18003659e  test    eax, eax
0x1800365a0  jle     short loc_1800365BF
0x1800365a2  movzx   ebx, ax
0x1800365a5  or      ebx, 80070000h
0x1800365ab  jmp     short loc_1800365BF
0x1800365ad  test    rsi, rsi
0x1800365b0  jz      short loc_1800365BC
0x1800365b2  cmp     [r15], edi
0x1800365b5  jnb     short loc_1800365DD
0x1800365b7  mov     ebx, 8007007Ah
0x1800365bc  mov     [r15], edi
0x1800365bf  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x1800365c3  jz      short loc_1800365CE
0x1800365c5  mov     rcx, rbp; hObject
0x1800365c8  call    cs:__imp_CloseHandle
0x1800365ce  mov     eax, ebx
0x1800365d0  add     rsp, 48h
0x1800365d4  pop     r15
0x1800365d6  pop     r14
0x1800365d8  pop     rdi
0x1800365d9  pop     rsi
0x1800365da  pop     rbp
0x1800365db  pop     rbx
0x1800365dc  retn
0x1800365dd  lea     r9, [rsp+78h+hFile]; lpNumberOfBytesRead
0x1800365e2  mov     dword ptr [rsp+78h+hFile], 0
0x1800365ea  mov     r8d, 2; nNumberOfBytesToRead
0x1800365f0  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x1800365f9  mov     rdx, rsi; lpBuffer
0x1800365fc  mov     rcx, rbp; hFile
0x1800365ff  call    cs:__imp_ReadFile
0x180036605  test    eax, eax
0x180036607  jz      short loc_180036596
0x180036609  cmp     byte ptr [rsi], 0FFh
0x18003660c  jnz     short loc_180036641
0x18003660e  cmp     byte ptr [rsi+1], 0FEh
0x180036612  jnz     short loc_180036641
0x180036614  add     edi, 0FFFFFFFEh
0x180036617  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x180036620  mov     r8d, edi; nNumberOfBytesToRead
0x180036623  lea     r9, [rsp+78h+hFile]; lpNumberOfBytesRead
0x180036628  mov     rdx, rsi; lpBuffer
0x18003662b  mov     rcx, rbp; hFile
0x18003662e  call    cs:__imp_ReadFile
0x180036634  test    eax, eax
0x180036636  jz      loc_180036596
0x18003663c  mov     r14d, edi
0x18003663f  jmp     short loc_18003666B
0x180036641  lea     r14d, [rdi-2]
0x180036645  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18003664e  mov     r8d, r14d; nNumberOfBytesToRead
0x180036651  lea     rdx, [rsi+2]; lpBuffer
0x180036655  lea     r9, [rsp+78h+hFile]; lpNumberOfBytesRead
0x18003665a  mov     rcx, rbp; hFile
0x18003665d  call    cs:__imp_ReadFile
0x180036663  test    eax, eax
0x180036665  jz      loc_180036596
0x18003666b  mov     [r15], edi
0x18003666e  cmp     dword ptr [rsp+78h+hFile], r14d
0x180036673  jnb     loc_1800365BF
0x180036679  jmp     loc_180036596
```
