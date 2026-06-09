# FileDeleteHelper

- ea: `0x180010358`
- end: `0x1800104cc`
- name: `FileDeleteHelper`
- size: `372`
- prototype: `__int64 __fastcall(LPCWSTR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180010c74`

## callees

- `0x180001540`
- `0x180010358`
- `0x1800109d4`
- `0x180010a30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103bd`
- `ntdll!NtClose` at `0x1800103eb`
- `ntdll!NtClose` at `0x1800104b6`
- `ntdll!NtClose` at `0x1800103eb`
- `ntdll!NtClose` at `0x1800104b6`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800104a5`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800104a5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800103a7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800103a7`

## pseudocode

```c
__int64 __fastcall FileDeleteHelper(LPCWSTR *a1)
{
  unsigned __int16 v2; // dx
  char *FileW; // rbx
  unsigned __int16 v4; // r8
  unsigned __int16 v6; // dx
  unsigned __int16 v7; // cx
  unsigned __int16 v8; // r8
  FILE_INFO_BY_HANDLE_CLASS v9; // esi
  char *p_FileInformation; // rbp
  DWORD v11; // edi
  char v12; // [rsp+40h] [rbp-28h] BYREF
  char v13; // [rsp+41h] [rbp-27h] BYREF
  int FileInformation; // [rsp+44h] [rbp-24h] BYREF

  FileW = (char *)CreateFileW(*a1, 0x10180u, 7u, 0, 3u, 0x2200000u, 0);
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v13 = 0;
    FileInformation = 0;
    v12 = 0;
    if ( !IsWindowsVersionOrGreaterEx((_WORD)FileW + 1, v2, v4, 0x383Au) || (int)IsPathFAT(FileW, a1, &v12) < 0 || v12 )
    {
      v9 = FileDispositionInfo;
      v13 = 1;
      p_FileInformation = &v13;
      v11 = 1;
    }
    else
    {
      v9 = FileRenameInfoEx|FileDispositionInfo;
      FileInformation = 3;
      p_FileInformation = (char *)&FileInformation;
      v11 = 4;
      if ( IsWindowsVersionOrGreaterEx(v7, v6, v8, 0x4563u) )
        FileInformation |= 0x10u;
    }
    if ( !SetFileInformationByHandle(FileW, v9, p_FileInformation, v11) )
      goto LABEL_16;
    goto LABEL_6;
  }
  if ( GetLastError() - 2 <= 1 )
  {
    if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      return 1;
LABEL_6:
    if ( NtClose(FileW) < 0 )
      __fastfail(7u);
    return 1;
  }
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
LABEL_16:
    if ( NtClose(FileW) < 0 )
      __fastfail(7u);
  }
  return 0;
}

```

## disassembly

```asm
0x180010358  mov     [rsp+arg_8], rbx
0x18001035d  mov     [rsp+arg_10], rbp
0x180010362  push    rsi
0x180010363  push    rdi
0x180010364  push    r15
0x180010366  sub     rsp, 50h
0x18001036a  mov     rax, cs:__security_cookie
0x180010371  xor     rax, rsp
0x180010374  mov     [rsp+68h+var_20], rax
0x180010379  xor     r9d, r9d; lpSecurityAttributes
0x18001037c  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180010385  mov     rdi, rcx
0x180010388  mov     [rsp+68h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180010390  mov     rcx, [rcx]; lpFileName
0x180010393  mov     edx, 10180h; dwDesiredAccess
0x180010398  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1800103a0  lea     r15d, [r9+7]
0x1800103a4  mov     r8d, r15d; dwShareMode
0x1800103a7  call    cs:__imp_CreateFileW
0x1800103ad  mov     rbx, rax
0x1800103b0  lea     rcx, [rax+1]; unsigned __int16
0x1800103b4  test    rcx, 0FFFFFFFFFFFFFFFEh
0x1800103bb  jnz     short loc_180010421
0x1800103bd  call    cs:__imp_GetLastError
0x1800103c3  add     eax, 0FFFFFFFEh
0x1800103c6  cmp     eax, 1
0x1800103c9  jbe     short loc_1800103DE
0x1800103cb  lea     rdx, [rbx-1]
0x1800103cf  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800103d3  ja      loc_1800104C5
0x1800103d9  jmp     loc_1800104B3
0x1800103de  lea     rax, [rbx-1]
0x1800103e2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800103e6  ja      short loc_1800103FA
0x1800103e8  mov     rcx, rbx; Handle
0x1800103eb  call    cs:__imp_NtClose
0x1800103f1  test    eax, eax
0x1800103f3  jns     short loc_1800103FA
0x1800103f5  mov     rcx, r15
0x1800103f8  int     29h; Win8: RtlFailFast(ecx)
0x1800103fa  mov     eax, 1
0x1800103ff  mov     rcx, [rsp+68h+var_20]
0x180010404  xor     rcx, rsp; StackCookie
0x180010407  call    __security_check_cookie
0x18001040c  lea     r11, [rsp+68h+var_18]
0x180010411  mov     rbx, [r11+28h]
0x180010415  mov     rbp, [r11+30h]
0x180010419  mov     rsp, r11
0x18001041c  pop     r15
0x18001041e  pop     rdi
0x18001041f  pop     rsi
0x180010420  retn
0x180010421  mov     r9d, 383Ah; unsigned __int16
0x180010427  mov     [rsp+68h+var_27], 0
0x18001042c  mov     [rsp+68h+FileInformation], 0
0x180010434  mov     [rsp+68h+var_28], 0
0x180010439  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x18001043e  test    al, al
0x180010440  jz      short loc_180010488
0x180010442  lea     r8, [rsp+68h+var_28]
0x180010447  mov     rdx, rdi
0x18001044a  mov     rcx, rbx
0x18001044d  call    ?IsPathFAT@@YAJPEAXAEBV?$basic_zstring_view@_W@wil@@PEA_N@Z; IsPathFAT(void *,wil::basic_zstring_view<wchar_t> const &,bool *)
0x180010452  test    eax, eax
0x180010454  js      short loc_180010488
0x180010456  cmp     [rsp+68h+var_28], 0
0x18001045b  jnz     short loc_180010488
0x18001045d  mov     esi, 15h
0x180010462  mov     [rsp+68h+FileInformation], 3
0x18001046a  mov     r9d, 4563h; unsigned __int16
0x180010470  lea     rbp, [rsp+68h+FileInformation]
0x180010475  lea     edi, [rsi-11h]
0x180010478  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x18001047d  test    al, al
0x18001047f  jz      short loc_18001049A
0x180010481  or      [rsp+68h+FileInformation], 10h
0x180010486  jmp     short loc_18001049A
0x180010488  mov     esi, 4
0x18001048d  mov     [rsp+68h+var_27], 1
0x180010492  lea     rbp, [rsp+68h+var_27]
0x180010497  lea     edi, [rsi-3]
0x18001049a  mov     r9d, edi; dwBufferSize
0x18001049d  mov     r8, rbp; lpFileInformation
0x1800104a0  mov     edx, esi; FileInformationClass
0x1800104a2  mov     rcx, rbx; hFile
0x1800104a5  call    cs:__imp_SetFileInformationByHandle
0x1800104ab  test    eax, eax
0x1800104ad  jnz     loc_1800103E8
0x1800104b3  mov     rcx, rbx; Handle
0x1800104b6  call    cs:__imp_NtClose
0x1800104bc  test    eax, eax
0x1800104be  jns     short loc_1800104C5
0x1800104c0  mov     rcx, r15
0x1800104c3  int     29h; Win8: RtlFailFast(ecx)
0x1800104c5  xor     eax, eax
0x1800104c7  jmp     loc_1800103FF
```
