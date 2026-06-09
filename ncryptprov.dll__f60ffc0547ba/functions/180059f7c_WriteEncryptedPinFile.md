# WriteEncryptedPinFile

- ea: `0x180059f7c`
- end: `0x18005a07c`
- name: `WriteEncryptedPinFile`
- size: `256`
- prototype: `__int64 __usercall@<rax>(LPCVOID lpBuffer@<rcx>, DWORD nNumberOfBytesToWrite@<edx>, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180059ed0`

## callees

- `0x18000af80`
- `0x180036940`
- `0x180059588`
- `0x180059f7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a008`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a061`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a061`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180059ff8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180059ff8`

## string_xrefs

- `0x180059fc8`: `onecore\ds\security\cryptoapi\ncrypt\storage\encryptedpinfile.c`
- `0x18005a01a`: `onecore\ds\security\cryptoapi\ncrypt\storage\encryptedpinfile.c`

## pseudocode

```c
__int64 __fastcall WriteEncryptedPinFile(
        LPCVOID lpBuffer,
        DWORD nNumberOfBytesToWrite,
        __int64 a3,
        unsigned int a4,
        _WORD *a5)
{
  int FileHandle; // eax
  signed int LastError; // ebx
  bool v11; // sf
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-38h] BYREF
  HANDLE hFile[6]; // [rsp+38h] [rbp-30h] BYREF

  hFile[0] = (HANDLE)-1LL;
  NumberOfBytesWritten = 0;
  FileHandle = CreateFileHandle(a3, a4, a5, (__int64 *)hFile);
  LastError = FileHandle;
  if ( FileHandle >= 0 )
  {
    if ( !WriteFile(hFile[0], lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
    {
      LastError = GetLastError();
      DebugTraceError(
        (unsigned int)LastError,
        "dwReturn",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\encryptedpinfile.c",
        386);
      v11 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v11 = LastError < 0;
      }
      if ( v11 )
        DeleteEncryptedPinFile(a3, a4, (__int64)a5);
    }
  }
  else
  {
    DebugTraceError(
      (unsigned int)FileHandle,
      "hr",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\encryptedpinfile.c",
      373);
  }
  if ( hFile[0] != (HANDLE)-1LL )
    CloseHandle(hFile[0]);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180059f7c  push    rbx
0x180059f7e  push    rbp
0x180059f7f  push    rsi
0x180059f80  push    r14
0x180059f82  push    r15
0x180059f84  sub     rsp, 40h
0x180059f88  mov     esi, r9d
0x180059f8b  mov     [rsp+68h+hFile], 0FFFFFFFFFFFFFFFFh
0x180059f94  mov     rbp, r8
0x180059f97  mov     [rsp+68h+NumberOfBytesWritten], 0
0x180059f9f  mov     r8, [rsp+68h+arg_20]
0x180059fa7  lea     r9, [rsp+68h+hFile]
0x180059fac  mov     r14d, edx
0x180059faf  mov     r15, rcx
0x180059fb2  mov     edx, esi
0x180059fb4  mov     rcx, rbp
0x180059fb7  call    CreateFileHandle
0x180059fbc  mov     ebx, eax
0x180059fbe  test    eax, eax
0x180059fc0  jns     short loc_180059FDF
0x180059fc2  mov     r9d, 175h
0x180059fc8  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180059fcf  lea     rdx, aHr; "hr"
0x180059fd6  mov     ecx, eax
0x180059fd8  call    DebugTraceError
0x180059fdd  jmp     short loc_18005A054
0x180059fdf  mov     rcx, [rsp+68h+hFile]; hFile
0x180059fe4  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180059fe9  mov     r8d, r14d; nNumberOfBytesToWrite
0x180059fec  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x180059ff5  mov     rdx, r15; lpBuffer
0x180059ff8  call    cs:__imp_WriteFile
0x180059fff  nop     dword ptr [rax+rax+00h]
0x18005a004  test    eax, eax
0x18005a006  jnz     short loc_18005A054
0x18005a008  call    cs:__imp_GetLastError
0x18005a00f  nop     dword ptr [rax+rax+00h]
0x18005a014  mov     r9d, 182h
0x18005a01a  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005a021  mov     ecx, eax
0x18005a023  lea     rdx, aDwreturn; "dwReturn"
0x18005a02a  mov     ebx, eax
0x18005a02c  call    DebugTraceError
0x18005a031  test    ebx, ebx
0x18005a033  jle     short loc_18005A040
0x18005a035  movzx   ebx, bx
0x18005a038  or      ebx, 80070000h
0x18005a03e  test    ebx, ebx
0x18005a040  jns     short loc_18005A054
0x18005a042  mov     r8, [rsp+68h+arg_20]
0x18005a04a  mov     edx, esi
0x18005a04c  mov     rcx, rbp
0x18005a04f  call    DeleteEncryptedPinFile
0x18005a054  cmp     [rsp+68h+hFile], 0FFFFFFFFFFFFFFFFh
0x18005a05a  jz      short loc_18005A06D
0x18005a05c  mov     rcx, [rsp+68h+hFile]; hObject
0x18005a061  call    cs:__imp_CloseHandle
0x18005a068  nop     dword ptr [rax+rax+00h]
0x18005a06d  mov     eax, ebx
0x18005a06f  add     rsp, 40h
0x18005a073  pop     r15
0x18005a075  pop     r14
0x18005a077  pop     rsi
0x18005a078  pop     rbp
0x18005a079  pop     rbx
0x18005a07a  retn
```
