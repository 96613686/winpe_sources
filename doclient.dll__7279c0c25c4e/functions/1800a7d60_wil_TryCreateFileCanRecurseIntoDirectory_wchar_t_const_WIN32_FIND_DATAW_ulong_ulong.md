# wil::TryCreateFileCanRecurseIntoDirectory(wchar_t const *,_WIN32_FIND_DATAW *,ulong,ulong)

- ea: `0x1800a7d60`
- end: `0x1800a7e53`
- name: `?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEB_WPEAU_WIN32_FIND_DATAW@@KK@Z`
- size: `243`
- prototype: `void **__fastcall(void **, const WCHAR *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800a7e5c`

## callees

- `0x1800a7d60`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a7e26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a7e26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7e1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7e1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a7e2e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a7e2e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a7da9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a7da9`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800a7dd6`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800a7dd6`

## pseudocode

```c
void **__fastcall wil::TryCreateFileCanRecurseIntoDirectory(void **a1, const WCHAR *a2, _DWORD *a3)
{
  char *FileW; // rcx
  int v6; // ecx
  void *v7; // rdi
  DWORD LastError; // ebx
  __int64 FileInformation; // [rsp+40h] [rbp-28h] BYREF

  *a1 = 0;
  FileW = (char *)CreateFileW(a2, 0x80010000, 1u, 0, 3u, 0x2200000u, 0);
  *a1 = FileW;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    FileInformation = 0;
    if ( GetFileInformationByHandleEx(FileW, FileAttributeTagInfo, &FileInformation, 8u)
      && (FileInformation & 0x10) != 0
      && ((v6 = HIDWORD(FileInformation), (FileInformation & 0x400) == 0)
       || (FileInformation & 0x1000000000000000LL) != 0
       || HIDWORD(FileInformation) == -2147483624) )
    {
      if ( a3 )
      {
        *a3 = FileInformation;
        a3[9] = v6;
      }
    }
    else
    {
      v7 = *a1;
      if ( *a1 != (void *)-1LL && v7 )
      {
        LastError = GetLastError();
        CloseHandle(v7);
        SetLastError(LastError);
      }
      *a1 = (void *)-1LL;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800a7d60  push    rbx
0x1800a7d62  push    rsi
0x1800a7d63  push    rdi
0x1800a7d64  sub     rsp, 50h
0x1800a7d68  mov     rax, cs:__security_cookie
0x1800a7d6f  xor     rax, rsp
0x1800a7d72  mov     [rsp+68h+var_20], rax
0x1800a7d77  mov     rsi, rcx
0x1800a7d7a  mov     rax, rdx
0x1800a7d7d  xor     ecx, ecx
0x1800a7d7f  mov     rbx, r8
0x1800a7d82  mov     [rsp+68h+hTemplateFile], rcx; hTemplateFile
0x1800a7d87  xor     r9d, r9d; lpSecurityAttributes
0x1800a7d8a  mov     [rsp+68h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1800a7d92  mov     edx, 80010000h; dwDesiredAccess
0x1800a7d97  mov     [rsi], rcx
0x1800a7d9a  lea     r8d, [rcx+1]; dwShareMode
0x1800a7d9e  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1800a7da6  mov     rcx, rax; lpFileName
0x1800a7da9  call    cs:__imp_CreateFileW
0x1800a7daf  mov     rcx, rax; hFile
0x1800a7db2  mov     [rsi], rax
0x1800a7db5  dec     rax
0x1800a7db8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a7dbc  ja      short loc_1800A7E3B
0x1800a7dbe  mov     r9d, 8; dwBufferSize
0x1800a7dc4  mov     [rsp+68h+FileInformation], 0
0x1800a7dcd  lea     r8, [rsp+68h+FileInformation]; lpFileInformation
0x1800a7dd2  lea     edx, [r9+1]; FileInformationClass
0x1800a7dd6  call    cs:__imp_GetFileInformationByHandleEx
0x1800a7ddc  test    eax, eax
0x1800a7dde  jz      short loc_1800A7E0D
0x1800a7de0  mov     rax, [rsp+68h+FileInformation]
0x1800a7de5  test    al, 10h
0x1800a7de7  jz      short loc_1800A7E0D
0x1800a7de9  mov     ecx, dword ptr [rsp+68h+FileInformation+4]
0x1800a7ded  bt      eax, 0Ah
0x1800a7df1  jnb     short loc_1800A7E01
0x1800a7df3  bt      ecx, 1Ch
0x1800a7df7  jb      short loc_1800A7E01
0x1800a7df9  cmp     ecx, 80000018h
0x1800a7dff  jnz     short loc_1800A7E0D
0x1800a7e01  test    rbx, rbx
0x1800a7e04  jz      short loc_1800A7E3B
0x1800a7e06  mov     [rbx], eax
0x1800a7e08  mov     [rbx+24h], ecx
0x1800a7e0b  jmp     short loc_1800A7E3B
0x1800a7e0d  mov     rdi, [rsi]
0x1800a7e10  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800a7e14  jz      short loc_1800A7E34
0x1800a7e16  test    rdi, rdi
0x1800a7e19  jz      short loc_1800A7E34
0x1800a7e1b  call    cs:__imp_GetLastError
0x1800a7e21  mov     rcx, rdi; hObject
0x1800a7e24  mov     ebx, eax
0x1800a7e26  call    cs:__imp_CloseHandle
0x1800a7e2c  mov     ecx, ebx; dwErrCode
0x1800a7e2e  call    cs:__imp_SetLastError
0x1800a7e34  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x1800a7e3b  mov     rax, rsi
0x1800a7e3e  mov     rcx, [rsp+68h+var_20]
0x1800a7e43  xor     rcx, rsp; StackCookie
0x1800a7e46  call    __security_check_cookie
0x1800a7e4b  add     rsp, 50h
0x1800a7e4f  pop     rdi
0x1800a7e50  pop     rsi
0x1800a7e51  pop     rbx
0x1800a7e52  retn
```
