# APP_POOL_ISOLATION::GenerateErrorConfigFile(ushort const *,ushort const *)

- ea: `0x18000cc40`
- end: `0x18000cf22`
- name: `?GenerateErrorConfigFile@APP_POOL_ISOLATION@@QEAAJPEBG0@Z`
- size: `738`
- prototype: `int(APP_POOL_ISOLATION *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x180017f18`

## callees

- `0x18000c4e4`
- `0x18000cc40`
- `0x18000d6b8`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cced`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cced`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ce8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ced3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ce8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ced3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000ccdd`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000ccdd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000cd55`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000cd55`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000cd98`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000cd98`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000ceb3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000ceb3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000ce75`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000ce75`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000ce86`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000ce86`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000cea5`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000cea5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000cee8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000cef2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000cefc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000cee8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000cef2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000cefc`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000cc72`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000cc7c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000cc86`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000cc72`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000cc7c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000cc86`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000cede`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000cede`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000cca7`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000cca7`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000cec4`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000cec4`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000cc95`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000cc95`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000cdb6`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000cdd8`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000ce12`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000ce4a`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000cdb6`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000cdd8`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000ce12`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000ce4a`
- `iisutil!?AppendW@STRA@@QEAAJPEBG@Z` at `0x18000cdf0`
- `iisutil!?AppendW@STRA@@QEAAJPEBG@Z` at `0x18000ce2e`
- `iisutil!?AppendW@STRA@@QEAAJPEBG@Z` at `0x18000cdf0`
- `iisutil!?AppendW@STRA@@QEAAJPEBG@Z` at `0x18000ce2e`

## string_xrefs

- `0x18000cdaa`: `<!-- ERROR: There's been an error reading or processing the applicationhost.config file. `

## pseudocode

```c
__int64 __fastcall APP_POOL_ISOLATION::GenerateErrorConfigFile(
        const unsigned __int16 **this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 FileW; // rdi
  signed int AppPoolFilePath; // ebx
  int v8; // r14d
  signed int LastError; // eax
  signed int v10; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v13[32]; // [rsp+48h] [rbp-B8h] BYREF
  LPCVOID lpBuffer; // [rsp+68h] [rbp-98h]
  DWORD nNumberOfBytesToWrite; // [rsp+78h] [rbp-88h]
  _BYTE v16[32]; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR lpFileName; // [rsp+A0h] [rbp-60h]
  _BYTE v18[32]; // [rsp+B8h] [rbp-48h] BYREF
  LPCWSTR lpPathName; // [rsp+D8h] [rbp-28h]
  _BYTE v20[32]; // [rsp+F0h] [rbp-10h] BYREF
  LPCWSTR lpNewFileName; // [rsp+110h] [rbp+10h]

  STRU::STRU((STRU *)v18);
  STRU::STRU((STRU *)v20);
  STRU::STRU((STRU *)v16);
  FileW = -1;
  STRA::STRA((STRA *)v13);
  NumberOfBytesWritten = 0;
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(this + 2));
  AppPoolFilePath = APP_POOL_ISOLATION::MakeAppPoolFilePath(
                      this[16],
                      a2,
                      (struct STRU *)v18,
                      (struct STRU *)v20,
                      (struct STRU *)v16);
  if ( AppPoolFilePath < 0 )
    goto LABEL_29;
  if ( CreateDirectoryW(lpPathName, 0) )
  {
    v8 = 1;
  }
  else
  {
    if ( !GetLastError() )
    {
      AppPoolFilePath = -2147467259;
      goto LABEL_29;
    }
    v8 = 0;
    LastError = GetLastError();
    AppPoolFilePath = LastError;
    if ( LastError > 0 )
      AppPoolFilePath = (unsigned __int16)LastError | 0x80070000;
    if ( AppPoolFilePath != -2147024713 )
      goto LABEL_13;
  }
  AppPoolFilePath = APP_POOL_ISOLATION::CreateAndSetFileACL(lpFileName, a3);
  if ( AppPoolFilePath < 0 )
    goto LABEL_14;
  FileW = (__int64)CreateFileW(lpFileName, 0xC0000000, 0, 0, 3u, 0x80u, 0);
  if ( FileW == -1 )
    goto LABEL_10;
  if ( (AppPoolFilePath = STRA::Append(
                            (STRA *)v13,
                            "<!-- ERROR: There's been an error reading or processing the applicationhost.config file. "),
        AppPoolFilePath < 0)
    || this[33]
    && ((AppPoolFilePath = STRA::Append((STRA *)v13, " Line number: "), AppPoolFilePath < 0)
     || (AppPoolFilePath = STRA::AppendW((STRA *)v13, this[33]), AppPoolFilePath < 0))
    || this[34]
    && ((AppPoolFilePath = STRA::Append((STRA *)v13, "  Error message: "), AppPoolFilePath < 0)
     || (AppPoolFilePath = STRA::AppendW((STRA *)v13, this[34]), AppPoolFilePath < 0))
    || (AppPoolFilePath = STRA::Append((STRA *)v13, " -->\r\n"), AppPoolFilePath < 0) )
  {
LABEL_14:
    if ( v8 )
      RemoveDirectoryW(lpPathName);
    goto LABEL_29;
  }
  if ( !WriteFile((HANDLE)FileW, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
  {
LABEL_10:
    if ( GetLastError() )
    {
      v10 = GetLastError();
      AppPoolFilePath = v10;
      if ( v10 > 0 )
        AppPoolFilePath = (unsigned __int16)v10 | 0x80070000;
    }
    else
    {
      AppPoolFilePath = -2147467259;
    }
LABEL_13:
    if ( AppPoolFilePath >= 0 )
      goto LABEL_29;
    goto LABEL_14;
  }
  SetEndOfFile((HANDLE)FileW);
  CloseHandle((HANDLE)FileW);
  FileW = -1;
  if ( !MoveFileExW(lpFileName, lpNewFileName, 1u) )
    DeleteFileW(lpFileName);
LABEL_29:
  CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)(this + 2));
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  STRA::~STRA((STRA *)v13);
  STRU::~STRU((STRU *)v16);
  STRU::~STRU((STRU *)v20);
  STRU::~STRU((STRU *)v18);
  return (unsigned int)AppPoolFilePath;
}

```

## disassembly

```asm
0x18000cc40  push    rbp
0x18000cc42  push    rbx
0x18000cc43  push    rsi
0x18000cc44  push    rdi
0x18000cc45  push    r12
0x18000cc47  push    r14
0x18000cc49  push    r15
0x18000cc4b  lea     rbp, [rsp-30h]
0x18000cc50  sub     rsp, 130h
0x18000cc57  mov     rax, cs:__security_cookie
0x18000cc5e  xor     rax, rsp
0x18000cc61  mov     [rbp+60h+var_38], rax
0x18000cc65  mov     rsi, rcx
0x18000cc68  mov     r15, r8
0x18000cc6b  lea     rcx, [rbp+60h+var_A8]
0x18000cc6f  mov     rbx, rdx
0x18000cc72  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000cc78  lea     rcx, [rbp+60h+var_70]
0x18000cc7c  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000cc82  lea     rcx, [rbp+60h+var_E0]
0x18000cc86  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000cc8c  lea     rcx, [rsp+160h+var_118]
0x18000cc91  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000cc95  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x18000cc9b  lea     rcx, [rsi+10h]
0x18000cc9f  mov     [rsp+160h+NumberOfBytesWritten], 0
0x18000cca7  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000ccad  mov     rcx, [rsi+80h]; unsigned __int16 *
0x18000ccb4  lea     rax, [rbp+60h+var_E0]
0x18000ccb8  lea     r9, [rbp+60h+var_70]; struct STRU *
0x18000ccbc  mov     qword ptr [rsp+160h+dwCreationDisposition], rax; struct STRU *
0x18000ccc1  lea     r8, [rbp+60h+var_A8]; struct STRU *
0x18000ccc5  mov     rdx, rbx; unsigned __int16 *
0x18000ccc8  call    ?MakeAppPoolFilePath@APP_POOL_ISOLATION@@SAJPEBG0PEAVSTRU@@11@Z; APP_POOL_ISOLATION::MakeAppPoolFilePath(ushort const *,ushort const *,STRU *,STRU *,STRU *)
0x18000cccd  mov     ebx, eax
0x18000cccf  test    eax, eax
0x18000ccd1  js      loc_18000CEC0
0x18000ccd7  mov     rcx, [rbp+60h+lpPathName]; lpPathName
0x18000ccdb  xor     edx, edx; lpSecurityAttributes
0x18000ccdd  call    cs:__imp_CreateDirectoryW
0x18000cce3  test    eax, eax
0x18000cce5  jz      short loc_18000CCED
0x18000cce7  lea     r14d, [rdi+2]
0x18000cceb  jmp     short loc_18000CD1B
0x18000cced  call    cs:__imp_GetLastError
0x18000ccf3  test    eax, eax
0x18000ccf5  jz      loc_18000CEBB
0x18000ccfb  xor     r14d, r14d
0x18000ccfe  call    cs:__imp_GetLastError
0x18000cd04  mov     ebx, eax
0x18000cd06  test    eax, eax
0x18000cd08  jle     short loc_18000CD13
0x18000cd0a  movzx   ebx, ax
0x18000cd0d  or      ebx, 80070000h
0x18000cd13  cmp     ebx, 800700B7h
0x18000cd19  jnz     short loc_18000CD83
0x18000cd1b  mov     rcx, [rbp+60h+lpFileName]; lpFileName
0x18000cd1f  mov     rdx, r15; unsigned __int16 *
0x18000cd22  call    ?CreateAndSetFileACL@APP_POOL_ISOLATION@@SAJPEBG0@Z; APP_POOL_ISOLATION::CreateAndSetFileACL(ushort const *,ushort const *)
0x18000cd27  mov     ebx, eax
0x18000cd29  test    eax, eax
0x18000cd2b  js      short loc_18000CD8B
0x18000cd2d  mov     rcx, [rbp+60h+lpFileName]; lpFileName
0x18000cd31  xor     r9d, r9d; lpSecurityAttributes
0x18000cd34  mov     [rsp+160h+hTemplateFile], 0; hTemplateFile
0x18000cd3d  xor     r8d, r8d; dwShareMode
0x18000cd40  mov     [rsp+160h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000cd48  mov     edx, 0C0000000h; dwDesiredAccess
0x18000cd4d  mov     [rsp+160h+dwCreationDisposition], 3; dwCreationDisposition
0x18000cd55  call    cs:__imp_CreateFileW
0x18000cd5b  mov     rdi, rax
0x18000cd5e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000cd62  jnz     short loc_18000CDAA
0x18000cd64  call    cs:__imp_GetLastError
0x18000cd6a  test    eax, eax
0x18000cd6c  jz      short loc_18000CDA3
0x18000cd6e  call    cs:__imp_GetLastError
0x18000cd74  mov     ebx, eax
0x18000cd76  test    eax, eax
0x18000cd78  jle     short loc_18000CD83
0x18000cd7a  movzx   ebx, ax
0x18000cd7d  or      ebx, 80070000h
0x18000cd83  test    ebx, ebx
0x18000cd85  jns     loc_18000CEC0
0x18000cd8b  test    r14d, r14d
0x18000cd8e  jz      loc_18000CEC0
0x18000cd94  mov     rcx, [rbp+60h+lpPathName]; lpPathName
0x18000cd98  call    cs:__imp_RemoveDirectoryW
0x18000cd9e  jmp     loc_18000CEC0
0x18000cda3  mov     ebx, 80004005h
0x18000cda8  jmp     short loc_18000CD83
0x18000cdaa  lea     rdx, aErrorThereSBee; "<!-- ERROR: There's been an error readi"...
0x18000cdb1  lea     rcx, [rsp+160h+var_118]
0x18000cdb6  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x18000cdbc  mov     ebx, eax
0x18000cdbe  test    eax, eax
0x18000cdc0  js      short loc_18000CD8B
0x18000cdc2  cmp     qword ptr [rsi+108h], 0
0x18000cdca  jz      short loc_18000CDFC
0x18000cdcc  lea     rdx, aLineNumber; " Line number: "
0x18000cdd3  lea     rcx, [rsp+160h+var_118]
0x18000cdd8  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x18000cdde  mov     ebx, eax
0x18000cde0  test    eax, eax
0x18000cde2  js      short loc_18000CD8B
0x18000cde4  mov     rdx, [rsi+108h]
0x18000cdeb  lea     rcx, [rsp+160h+var_118]
0x18000cdf0  call    cs:__imp_?AppendW@STRA@@QEAAJPEBG@Z; STRA::AppendW(ushort const *)
0x18000cdf6  mov     ebx, eax
0x18000cdf8  test    eax, eax
0x18000cdfa  js      short loc_18000CD8B
0x18000cdfc  cmp     qword ptr [rsi+110h], 0
0x18000ce04  jz      short loc_18000CE3E
0x18000ce06  lea     rdx, aErrorMessage; "  Error message: "
0x18000ce0d  lea     rcx, [rsp+160h+var_118]
0x18000ce12  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x18000ce18  mov     ebx, eax
0x18000ce1a  test    eax, eax
0x18000ce1c  js      loc_18000CD8B
0x18000ce22  mov     rdx, [rsi+110h]
0x18000ce29  lea     rcx, [rsp+160h+var_118]
0x18000ce2e  call    cs:__imp_?AppendW@STRA@@QEAAJPEBG@Z; STRA::AppendW(ushort const *)
0x18000ce34  mov     ebx, eax
0x18000ce36  test    eax, eax
0x18000ce38  js      loc_18000CD8B
0x18000ce3e  lea     rdx, asc_180067F54; " -->\r\n"
0x18000ce45  lea     rcx, [rsp+160h+var_118]
0x18000ce4a  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x18000ce50  mov     ebx, eax
0x18000ce52  test    eax, eax
0x18000ce54  js      loc_18000CD8B
0x18000ce5a  mov     r8d, [rsp+160h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x18000ce5f  lea     r9, [rsp+160h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000ce64  mov     rdx, [rsp+160h+lpBuffer]; lpBuffer
0x18000ce69  mov     rcx, rdi; hFile
0x18000ce6c  mov     qword ptr [rsp+160h+dwCreationDisposition], 0; lpOverlapped
0x18000ce75  call    cs:__imp_WriteFile
0x18000ce7b  test    eax, eax
0x18000ce7d  jz      loc_18000CD64
0x18000ce83  mov     rcx, rdi; hFile
0x18000ce86  call    cs:__imp_SetEndOfFile
0x18000ce8c  mov     rcx, rdi; hObject
0x18000ce8f  call    cs:__imp_CloseHandle
0x18000ce95  mov     rdx, [rbp+60h+lpNewFileName]; lpNewFileName
0x18000ce99  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000ce9d  mov     rcx, [rbp+60h+lpFileName]; lpExistingFileName
0x18000cea1  lea     r8d, [rdi+2]; dwFlags
0x18000cea5  call    cs:__imp_MoveFileExW
0x18000ceab  test    eax, eax
0x18000cead  jnz     short loc_18000CEC0
0x18000ceaf  mov     rcx, [rbp+60h+lpFileName]; lpFileName
0x18000ceb3  call    cs:__imp_DeleteFileW
0x18000ceb9  jmp     short loc_18000CEC0
0x18000cebb  mov     ebx, 80004005h
0x18000cec0  lea     rcx, [rsi+10h]
0x18000cec4  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000ceca  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000cece  jz      short loc_18000CED9
0x18000ced0  mov     rcx, rdi; hObject
0x18000ced3  call    cs:__imp_CloseHandle
0x18000ced9  lea     rcx, [rsp+160h+var_118]
0x18000cede  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000cee4  lea     rcx, [rbp+60h+var_E0]
0x18000cee8  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000ceee  lea     rcx, [rbp+60h+var_70]
0x18000cef2  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000cef8  lea     rcx, [rbp+60h+var_A8]
0x18000cefc  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000cf02  mov     eax, ebx
0x18000cf04  mov     rcx, [rbp+60h+var_38]
0x18000cf08  xor     rcx, rsp; StackCookie
0x18000cf0b  call    __security_check_cookie
0x18000cf10  add     rsp, 130h
0x18000cf17  pop     r15
0x18000cf19  pop     r14
0x18000cf1b  pop     r12
0x18000cf1d  pop     rdi
0x18000cf1e  pop     rsi
0x18000cf1f  pop     rbx
0x18000cf20  pop     rbp
0x18000cf21  retn
```
