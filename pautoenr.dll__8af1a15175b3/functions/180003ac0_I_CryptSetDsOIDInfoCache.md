# I_CryptSetDsOIDInfoCache

- ea: `0x180003ac0`
- end: `0x180003b8c`
- name: `I_CryptSetDsOIDInfoCache`
- size: `204`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180006ecc`

## callees

- `0x180001010`
- `0x180003ac0`
- `0x180003ba0`
- `0x180005200`
- `0x180005240`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b3d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b61`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b61`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180003b50`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180003b50`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180003b22`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180003b22`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180003b59`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180003b59`

## pseudocode

```c
__int64 __fastcall I_CryptSetDsOIDInfoCache(__int64 a1)
{
  void *v1; // rdi
  unsigned int v2; // ebx
  HANDLE DsOIDInfoCacheFile; // rax
  DWORD v4; // ebp
  DWORD LastError; // ebx
  DWORD nNumberOfBytesToWrite; // [rsp+58h] [rbp+10h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+18h] BYREF
  LPCVOID lpBuffer; // [rsp+68h] [rbp+20h] BYREF

  lpBuffer = 0;
  v1 = 0;
  nNumberOfBytesToWrite = 0;
  NumberOfBytesWritten = 0;
  if ( !(unsigned int)SerializeBlobArray(a1, &lpBuffer, &nNumberOfBytesToWrite) )
    goto LABEL_7;
  v2 = 1;
  DsOIDInfoCacheFile = CreateDsOIDInfoCacheFile(1);
  v1 = DsOIDInfoCacheFile;
  if ( !DsOIDInfoCacheFile )
    goto LABEL_7;
  v4 = nNumberOfBytesToWrite;
  if ( !WriteFile(DsOIDInfoCacheFile, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
  {
LABEL_6:
    LastError = GetLastError();
    SetFilePointer(v1, 0, 0, 0);
    SetEndOfFile(v1);
    SetLastError(LastError);
LABEL_7:
    v2 = 0;
    goto LABEL_8;
  }
  if ( NumberOfBytesWritten != v4 )
  {
    SetLastError(0x8000FFFF);
    goto LABEL_6;
  }
LABEL_8:
  CloseHandle(v1);
  PkiFree((HLOCAL)lpBuffer);
  return v2;
}

```

## disassembly

```asm
0x180003ac0  mov     [rsp+arg_0], rbx
0x180003ac5  push    rbp
0x180003ac6  push    rdi
0x180003ac7  push    r14
0x180003ac9  sub     rsp, 30h
0x180003acd  xor     r14d, r14d
0x180003ad0  lea     r8, [rsp+48h+nNumberOfBytesToWrite]
0x180003ad5  lea     rdx, [rsp+48h+lpBuffer]
0x180003ada  mov     [rsp+48h+lpBuffer], r14
0x180003adf  mov     edi, r14d
0x180003ae2  mov     [rsp+48h+nNumberOfBytesToWrite], r14d
0x180003ae7  mov     [rsp+48h+NumberOfBytesWritten], r14d
0x180003aec  call    _SerializeBlobArray
0x180003af1  test    eax, eax
0x180003af3  jz      short loc_180003B67
0x180003af5  mov     ebx, 1
0x180003afa  mov     ecx, ebx
0x180003afc  call    _CreateDsOIDInfoCacheFile
0x180003b01  mov     rdi, rax
0x180003b04  test    rax, rax
0x180003b07  jz      short loc_180003B67
0x180003b09  mov     ebp, [rsp+48h+nNumberOfBytesToWrite]
0x180003b0d  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180003b12  mov     rdx, [rsp+48h+lpBuffer]; lpBuffer
0x180003b17  mov     r8d, ebp; nNumberOfBytesToWrite
0x180003b1a  mov     rcx, rax; hFile
0x180003b1d  mov     [rsp+48h+lpOverlapped], r14; lpOverlapped
0x180003b22  call    cs:__imp_WriteFile
0x180003b28  test    eax, eax
0x180003b2a  jz      short loc_180003B3D
0x180003b2c  cmp     [rsp+48h+NumberOfBytesWritten], ebp
0x180003b30  jz      short loc_180003B6A
0x180003b32  mov     ecx, 8000FFFFh; dwErrCode
0x180003b37  call    cs:__imp_SetLastError
0x180003b3d  call    cs:__imp_GetLastError
0x180003b43  xor     r9d, r9d; dwMoveMethod
0x180003b46  xor     r8d, r8d; lpDistanceToMoveHigh
0x180003b49  xor     edx, edx; lDistanceToMove
0x180003b4b  mov     rcx, rdi; hFile
0x180003b4e  mov     ebx, eax
0x180003b50  call    cs:__imp_SetFilePointer
0x180003b56  mov     rcx, rdi; hFile
0x180003b59  call    cs:__imp_SetEndOfFile
0x180003b5f  mov     ecx, ebx; dwErrCode
0x180003b61  call    cs:__imp_SetLastError
0x180003b67  mov     ebx, r14d
0x180003b6a  mov     rcx, rdi; hObject
0x180003b6d  call    _CloseHandle
0x180003b72  mov     rcx, [rsp+48h+lpBuffer]; hMem
0x180003b77  call    PkiFree
0x180003b7c  mov     eax, ebx
0x180003b7e  mov     rbx, [rsp+48h+arg_0]
0x180003b83  add     rsp, 30h
0x180003b87  pop     r14
0x180003b89  pop     rdi
0x180003b8a  pop     rbp
0x180003b8b  retn
```
