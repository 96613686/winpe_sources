# CreateFileHandle

- ea: `0x180036940`
- end: `0x180036b89`
- name: `CreateFileHandle`
- size: `585`
- prototype: `__int64 __fastcall(__int64, __int64, _WORD *, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180059f7c`

## callees

- `0x180006744`
- `0x18000af80`
- `0x18000d3d0`
- `0x18000dab0`
- `0x180036940`
- `0x1800599f8`
- `0x180059acc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036a73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036af0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036a73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036af0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036b69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036b69`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180036a5a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180036adb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180036a5a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180036adb`

## string_xrefs

- `0x180036999`: `onecore\ds\security\cryptoapi\ncrypt\storage\encryptedpinfile.c`
- `0x1800369da`: `onecore\ds\security\cryptoapi\ncrypt\storage\encryptedpinfile.c`
- `0x180036a10`: `onecore\ds\security\cryptoapi\ncrypt\storage\encryptedpinfile.c`
- `0x180036b0d`: `onecore\ds\security\cryptoapi\ncrypt\storage\encryptedpinfile.c`

## pseudocode

```c
__int64 __fastcall CreateFileHandle(__int64 a1, __int64 a2, _WORD *a3, __int64 *a4)
{
  const WCHAR *v7; // rsi
  __int64 FileW; // rdi
  int UserStorageArea; // eax
  _WORD *v10; // rbp
  unsigned int v11; // ebx
  int EncryptedPinFileStoragePath; // eax
  __int64 v13; // r14
  __int64 v14; // r9
  int EncryptedPinFilePath; // eax
  DWORD LastError; // eax
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // r9
  LPCWSTR lpFileName; // [rsp+40h] [rbp-68h] BYREF
  void *Src; // [rsp+48h] [rbp-60h] BYREF
  _QWORD v23[11]; // [rsp+50h] [rbp-58h] BYREF

  Src = 0;
  v23[0] = 0;
  lpFileName = 0;
  v7 = 0;
  FileW = -1;
  UserStorageArea = GetUserStorageArea(0, a2, a2, a3, (char **)&Src);
  v10 = Src;
  v11 = UserStorageArea;
  if ( UserStorageArea < 0 )
  {
    DebugTraceError(
      (unsigned int)UserStorageArea,
      "hr",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\encryptedpinfile.c",
      228);
    goto LABEL_24;
  }
  EncryptedPinFileStoragePath = GetEncryptedPinFileStoragePath(a3 != 0, Src, v23);
  v13 = v23[0];
  v11 = EncryptedPinFileStoragePath;
  if ( EncryptedPinFileStoragePath >= 0 )
  {
    EncryptedPinFilePath = GetEncryptedPinFilePath(v23[0], a1, &lpFileName);
    v11 = EncryptedPinFilePath;
    if ( EncryptedPinFilePath < 0 )
    {
      DebugTraceError(
        (unsigned int)EncryptedPinFilePath,
        "hr",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\encryptedpinfile.c",
        242);
      v7 = lpFileName;
      goto LABEL_20;
    }
    v7 = lpFileName;
    FileW = (__int64)CreateFileW(lpFileName, 0x40000000u, 0, 0, 1u, 0x8000002u, 0);
    if ( FileW == -1 )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError != 3 )
      {
        v19 = 288;
        v18 = LastError;
LABEL_16:
        DebugTraceError(v18, "dwReturn", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\encryptedpinfile.c", v19);
        if ( (int)v11 > 0 )
          v11 = (unsigned __int16)v11 | 0x80070000;
        goto LABEL_20;
      }
      v17 = -1;
      do
        ++v17;
      while ( v10[v17] );
      EncryptedPinFileStoragePath = CreateNestedDirectories(v10, (_WORD *)(v13 + 2 * (v17 + 1)), 0);
      v11 = EncryptedPinFileStoragePath;
      if ( EncryptedPinFileStoragePath < 0 )
      {
        v14 = 266;
        goto LABEL_5;
      }
      FileW = (__int64)CreateFileW(v7, 0x40000000u, 0, 0, 1u, 0x8000002u, 0);
      if ( FileW == -1 )
      {
        v11 = GetLastError();
        v18 = v11;
        v19 = 281;
        goto LABEL_16;
      }
    }
    *a4 = FileW;
    FileW = 0;
    goto LABEL_20;
  }
  v14 = 235;
LABEL_5:
  DebugTraceError(
    (unsigned int)EncryptedPinFileStoragePath,
    "hr",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\encryptedpinfile.c",
    v14);
LABEL_20:
  if ( v13 )
    MSCryptFree(v13);
  if ( v7 )
    MSCryptFree(v7);
LABEL_24:
  if ( v10 )
    MSCryptFree(v10);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  return v11;
}

```

## disassembly

```asm
0x180036940  mov     rax, rsp
0x180036943  push    rbx
0x180036944  push    rbp
0x180036945  push    rsi
0x180036946  push    rdi
0x180036947  push    r12
0x180036949  push    r13
0x18003694b  push    r14
0x18003694d  push    r15
0x18003694f  sub     rsp, 68h
0x180036953  xor     r13d, r13d
0x180036956  mov     r12, r9
0x180036959  mov     [rax-60h], r13
0x18003695d  mov     r14, r8
0x180036960  mov     [rax-58h], r13
0x180036964  mov     r15, rcx
0x180036967  mov     [rax-68h], r13
0x18003696b  lea     rax, [rax-60h]
0x18003696f  mov     r9, r8
0x180036972  mov     qword ptr [rsp+0A8h+dwCreationDisposition], rax
0x180036977  mov     r8d, edx
0x18003697a  xor     ecx, ecx
0x18003697c  mov     esi, r13d
0x18003697f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180036983  call    GetUserStorageArea
0x180036988  mov     rbp, [rsp+0A8h+Src]
0x18003698d  mov     ebx, eax
0x18003698f  test    eax, eax
0x180036991  jns     short loc_1800369B3
0x180036993  mov     r9d, 0E4h
0x180036999  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800369a0  lea     rdx, aHr; "hr"
0x1800369a7  mov     ecx, eax
0x1800369a9  call    DebugTraceError
0x1800369ae  jmp     loc_180036B53
0x1800369b3  mov     ecx, r13d
0x1800369b6  lea     r8, [rsp+0A8h+var_58]
0x1800369bb  test    r14, r14
0x1800369be  mov     rdx, rbp
0x1800369c1  setnz   cl
0x1800369c4  call    GetEncryptedPinFileStoragePath
0x1800369c9  mov     r14, [rsp+0A8h+var_58]
0x1800369ce  mov     ebx, eax
0x1800369d0  test    eax, eax
0x1800369d2  jns     short loc_1800369F4
0x1800369d4  mov     r9d, 0EBh
0x1800369da  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800369e1  mov     ecx, eax
0x1800369e3  lea     rdx, aHr; "hr"
0x1800369ea  call    DebugTraceError
0x1800369ef  jmp     loc_180036B39
0x1800369f4  lea     r8, [rsp+0A8h+lpFileName]
0x1800369f9  mov     rdx, r15
0x1800369fc  mov     rcx, r14
0x1800369ff  call    GetEncryptedPinFilePath
0x180036a04  mov     ebx, eax
0x180036a06  test    eax, eax
0x180036a08  jns     short loc_180036A2F
0x180036a0a  mov     r9d, 0F2h
0x180036a10  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180036a17  lea     rdx, aHr; "hr"
0x180036a1e  mov     ecx, eax
0x180036a20  call    DebugTraceError
0x180036a25  mov     rsi, [rsp+0A8h+lpFileName]
0x180036a2a  jmp     loc_180036B39
0x180036a2f  mov     rsi, [rsp+0A8h+lpFileName]
0x180036a34  mov     r15d, 8000002h
0x180036a3a  mov     [rsp+0A8h+hTemplateFile], r13; hTemplateFile
0x180036a3f  mov     rcx, rsi; lpFileName
0x180036a42  mov     [rsp+0A8h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x180036a47  xor     r9d, r9d; lpSecurityAttributes
0x180036a4a  xor     r8d, r8d; dwShareMode
0x180036a4d  mov     [rsp+0A8h+dwCreationDisposition], 1; dwCreationDisposition
0x180036a55  mov     edx, 40000000h; dwDesiredAccess
0x180036a5a  call    cs:__imp_CreateFileW
0x180036a61  nop     dword ptr [rax+rax+00h]
0x180036a66  mov     rdi, rax
0x180036a69  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180036a6d  jnz     loc_180036B32
0x180036a73  call    cs:__imp_GetLastError
0x180036a7a  nop     dword ptr [rax+rax+00h]
0x180036a7f  mov     ebx, eax
0x180036a81  cmp     eax, 3
0x180036a84  jnz     loc_180036B28
0x180036a8a  or      rax, rdi
0x180036a8d  inc     rax
0x180036a90  cmp     [rbp+rax*2+0], r13w
0x180036a96  jnz     short loc_180036A8D
0x180036a98  inc     rax
0x180036a9b  xor     r8d, r8d
0x180036a9e  mov     rcx, rbp; Src
0x180036aa1  lea     rdx, [r14+rax*2]; void *
0x180036aa5  call    CreateNestedDirectories
0x180036aaa  mov     ebx, eax
0x180036aac  test    eax, eax
0x180036aae  jns     short loc_180036ABB
0x180036ab0  mov     r9d, 10Ah
0x180036ab6  jmp     loc_1800369DA
0x180036abb  mov     [rsp+0A8h+hTemplateFile], r13; hTemplateFile
0x180036ac0  xor     r9d, r9d; lpSecurityAttributes
0x180036ac3  mov     [rsp+0A8h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x180036ac8  xor     r8d, r8d; dwShareMode
0x180036acb  mov     edx, 40000000h; dwDesiredAccess
0x180036ad0  mov     [rsp+0A8h+dwCreationDisposition], 1; dwCreationDisposition
0x180036ad8  mov     rcx, rsi; lpFileName
0x180036adb  call    cs:__imp_CreateFileW
0x180036ae2  nop     dword ptr [rax+rax+00h]
0x180036ae7  mov     rdi, rax
0x180036aea  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180036aee  jnz     short loc_180036B32
0x180036af0  call    cs:__imp_GetLastError
0x180036af7  nop     dword ptr [rax+rax+00h]
0x180036afc  mov     ebx, eax
0x180036afe  mov     ecx, eax
0x180036b00  mov     r9d, 119h
0x180036b06  lea     rdx, aDwreturn; "dwReturn"
0x180036b0d  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180036b14  call    DebugTraceError
0x180036b19  test    ebx, ebx
0x180036b1b  jle     short loc_180036B39
0x180036b1d  movzx   ebx, bx
0x180036b20  or      ebx, 80070000h
0x180036b26  jmp     short loc_180036B39
0x180036b28  mov     r9d, 120h
0x180036b2e  mov     ecx, ebx
0x180036b30  jmp     short loc_180036B06
0x180036b32  mov     [r12], rdi
0x180036b36  mov     rdi, r13
0x180036b39  test    r14, r14
0x180036b3c  jz      short loc_180036B46
0x180036b3e  mov     rcx, r14
0x180036b41  call    MSCryptFree
0x180036b46  test    rsi, rsi
0x180036b49  jz      short loc_180036B53
0x180036b4b  mov     rcx, rsi
0x180036b4e  call    MSCryptFree
0x180036b53  test    rbp, rbp
0x180036b56  jz      short loc_180036B60
0x180036b58  mov     rcx, rbp
0x180036b5b  call    MSCryptFree
0x180036b60  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180036b64  jz      short loc_180036B75
0x180036b66  mov     rcx, rdi; hObject
0x180036b69  call    cs:__imp_CloseHandle
0x180036b70  nop     dword ptr [rax+rax+00h]
0x180036b75  mov     eax, ebx
0x180036b77  add     rsp, 68h
0x180036b7b  pop     r15
0x180036b7d  pop     r14
0x180036b7f  pop     r13
0x180036b81  pop     r12
0x180036b83  pop     rdi
0x180036b84  pop     rsi
0x180036b85  pop     rbp
0x180036b86  pop     rbx
0x180036b87  retn
```
