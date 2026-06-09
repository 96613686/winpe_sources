# GetLUAPhonebookPath

- ea: `0x180080430`
- end: `0x1800806e8`
- name: `GetLUAPhonebookPath`
- size: `696`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, reparse_path`

## callers

- `0x180068bec`
- `0x1800714c0`
- `0x18007cf04`
- `0x18008e3fc`

## callees

- `0x18005e894`
- `0x18005eed8`
- `0x18005fbf4`
- `0x18005fe20`
- `0x18006d4c4`
- `0x1800803c0`
- `0x180080430`
- `0x1800806f0`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `msvcrt!wcsstr` at `0x1800804bf`
- `msvcrt!wcsstr` at `0x1800804bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080533`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080615`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080645`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080533`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080615`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080645`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008066c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008066c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180080689`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180080689`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008051e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800805e0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008051e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800805e0`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800805fc`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800805fc`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18008065c`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18008065c`

## string_xrefs

- `0x1800804b5`: `\system32\`

## pseudocode

```c
__int64 __fastcall GetLUAPhonebookPath(LPCWSTR lpFileName, __int64 *a2)
{
  wchar_t *v4; // r14
  DWORD DirectoriesOnPath; // ebx
  STRSAFE_LPWSTR *v6; // r9
  const wchar_t *v7; // r8
  HRESULT v8; // eax
  HANDLE FileW; // rax
  DWORD FileNameFromPath; // eax
  STRSAFE_LPWSTR *v11; // r9
  HRESULT v12; // eax
  HANDLE v13; // rax
  void *v14; // rdi
  __int64 v15; // rax
  size_t *dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  size_t *dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  STRSAFE_LPCWSTR pszSrc[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(pszDest, 0, 0x20Au);
  v4 = 0;
  pszSrc[0] = 0;
  if ( a2 && lpFileName )
  {
    *a2 = 0;
    if ( !(unsigned int)GetPhonebookDirectory(1u, pszDest) )
    {
LABEL_4:
      DirectoriesOnPath = 621;
      goto LABEL_28;
    }
    if ( wcsstr(lpFileName, L"\\system32\\") )
      v7 = L"_hiddenPBK\\System\\";
    else
      v7 = L"_hiddenPbk\\";
    v8 = StringCchCatExW(pszDest, 0x105u, v7, v6, dwCreationDisposition, 0x900u);
    DirectoriesOnPath = (unsigned __int16)v8;
    if ( v8 >= 0 )
      DirectoriesOnPath = 0;
    if ( !DirectoriesOnPath )
    {
      FileW = CreateFileW(pszDest, 0, 3u, 0, 3u, 0x2000080u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        DirectoriesOnPath = CreateDirectoriesOnPath(pszDest);
        if ( DirectoriesOnPath )
          goto LABEL_28;
      }
      else
      {
        CloseHandle(FileW);
      }
      FileNameFromPath = GetFileNameFromPath(lpFileName, pszSrc);
      v4 = (wchar_t *)pszSrc[0];
      DirectoriesOnPath = FileNameFromPath;
      if ( !FileNameFromPath )
      {
        v12 = StringCchCatExW(pszDest, 0x105u, pszSrc[0], v11, dwCreationDispositiona, 0x900u);
        DirectoriesOnPath = (unsigned __int16)v12;
        if ( v12 >= 0 )
          DirectoriesOnPath = 0;
        if ( !DirectoriesOnPath && !(unsigned int)FFileExists(pszDest) )
        {
          v13 = CreateFileW(pszDest, 0xC0000000, 1u, 0, 2u, 0x80u, 0);
          v14 = v13;
          if ( v13 == (HANDLE)-1LL )
            goto LABEL_4;
          if ( GetFileType(v13) != 1 )
          {
            DirectoriesOnPath = 621;
LABEL_22:
            CloseHandle(v14);
            goto LABEL_28;
          }
          if ( !(unsigned int)FFileExists(lpFileName) )
            goto LABEL_22;
          DirectoriesOnPath = IsFileNotASymlink(v14, pszDest);
          if ( DirectoriesOnPath )
            goto LABEL_22;
          CloseHandle(v14);
          if ( !CopyFileW(lpFileName, pszDest, 0) )
            DirectoriesOnPath = GetLastError();
        }
      }
    }
  }
  else
  {
    DirectoriesOnPath = 87;
  }
LABEL_28:
  if ( v4 )
    GlobalFree(v4);
  if ( a2 )
  {
    if ( DirectoriesOnPath )
    {
      *a2 = 0;
    }
    else
    {
      v15 = StrDup(pszDest);
      *a2 = v15;
      if ( !v15 )
        return 8;
    }
  }
  return DirectoriesOnPath;
}

```

## disassembly

```asm
0x180080430  mov     [rsp-8+arg_10], rbx
0x180080435  push    rbp
0x180080436  push    rsi
0x180080437  push    rdi
0x180080438  push    r14
0x18008043a  push    r15
0x18008043c  lea     rbp, [rsp-170h]
0x180080444  sub     rsp, 270h
0x18008044b  mov     rax, cs:__security_cookie
0x180080452  xor     rax, rsp
0x180080455  mov     [rbp+190h+var_30], rax
0x18008045c  mov     r15, rdx
0x18008045f  mov     rsi, rcx
0x180080462  xor     edx, edx; Val
0x180080464  lea     rcx, [rsp+290h+pszDest]; void *
0x180080469  mov     r8d, 20Ah; Size
0x18008046f  call    memset_0
0x180080474  xor     r14d, r14d
0x180080477  mov     [rsp+290h+pszSrc], r14
0x18008047c  test    r15, r15
0x18008047f  jz      loc_18008067C
0x180080485  test    rsi, rsi
0x180080488  jz      loc_18008067C
0x18008048e  mov     edi, 105h
0x180080493  mov     [r15], r14
0x180080496  mov     r8d, edi
0x180080499  lea     rdx, [rsp+290h+pszDest]
0x18008049e  lea     ecx, [r14+1]
0x1800804a2  call    GetPhonebookDirectory
0x1800804a7  test    eax, eax
0x1800804a9  jnz     short loc_1800804B5
0x1800804ab  mov     ebx, 26Dh
0x1800804b0  jmp     loc_180080681
0x1800804b5  lea     rdx, aSystem32; "\\system32\\"
0x1800804bc  mov     rcx, rsi; Str
0x1800804bf  call    cs:__imp_wcsstr
0x1800804c6  nop     dword ptr [rax+rax+00h]
0x1800804cb  mov     [rsp+290h+dwFlags], 900h; dwFlags
0x1800804d3  lea     rcx, [rsp+290h+pszDest]; pszDest
0x1800804d8  mov     rdx, rdi; cchDest
0x1800804db  test    rax, rax
0x1800804de  jz      short loc_180080541
0x1800804e0  lea     r8, aHiddenpbkSyste; "_hiddenPBK\\System\\"
0x1800804e7  call    StringCchCatExW
0x1800804ec  xor     ecx, ecx
0x1800804ee  movzx   ebx, ax
0x1800804f1  test    eax, eax
0x1800804f3  cmovns  ebx, ecx
0x1800804f6  test    ebx, ebx
0x1800804f8  jnz     loc_180080681
0x1800804fe  lea     r8d, [rcx+3]; dwShareMode
0x180080502  mov     [rsp+290h+hTemplateFile], r14; hTemplateFile
0x180080507  mov     [rsp+290h+dwFlags], 2000080h; dwFlagsAndAttributes
0x18008050f  lea     rcx, [rsp+290h+pszDest]; lpFileName
0x180080514  xor     r9d, r9d; lpSecurityAttributes
0x180080517  mov     dword ptr [rsp+290h+dwCreationDisposition], r8d; pcchRemaining
0x18008051c  xor     edx, edx; dwDesiredAccess
0x18008051e  call    cs:__imp_CreateFileW
0x180080525  nop     dword ptr [rax+rax+00h]
0x18008052a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008052e  jz      short loc_18008054A
0x180080530  mov     rcx, rax; hObject
0x180080533  call    cs:__imp_CloseHandle
0x18008053a  nop     dword ptr [rax+rax+00h]
0x18008053f  jmp     short loc_18008055E
0x180080541  lea     r8, aHiddenpbk; "_hiddenPbk\\"
0x180080548  jmp     short loc_1800804E7
0x18008054a  lea     rcx, [rsp+290h+pszDest]; lpPathName
0x18008054f  call    CreateDirectoriesOnPath
0x180080554  mov     ebx, eax
0x180080556  test    eax, eax
0x180080558  jnz     loc_180080681
0x18008055e  lea     rdx, [rsp+290h+pszSrc]
0x180080563  mov     rcx, rsi
0x180080566  call    GetFileNameFromPath
0x18008056b  mov     r14, [rsp+290h+pszSrc]
0x180080570  mov     ebx, eax
0x180080572  test    eax, eax
0x180080574  jnz     loc_180080681
0x18008057a  mov     r8, r14; pszSrc
0x18008057d  mov     [rsp+290h+dwFlags], 900h; dwFlags
0x180080585  mov     rdx, rdi; cchDest
0x180080588  lea     rcx, [rsp+290h+pszDest]; pszDest
0x18008058d  call    StringCchCatExW
0x180080592  xor     ecx, ecx
0x180080594  movzx   ebx, ax
0x180080597  test    eax, eax
0x180080599  cmovns  ebx, ecx
0x18008059c  test    ebx, ebx
0x18008059e  jnz     loc_180080681
0x1800805a4  lea     rcx, [rsp+290h+pszDest]; lpFileName
0x1800805a9  call    FFileExists
0x1800805ae  test    eax, eax
0x1800805b0  jnz     loc_180080681
0x1800805b6  mov     [rsp+290h+hTemplateFile], 0; hTemplateFile
0x1800805bf  lea     r8d, [rbx+1]; dwShareMode
0x1800805c3  mov     [rsp+290h+dwFlags], 80h; dwFlagsAndAttributes
0x1800805cb  lea     rcx, [rsp+290h+pszDest]; lpFileName
0x1800805d0  xor     r9d, r9d; lpSecurityAttributes
0x1800805d3  mov     dword ptr [rsp+290h+dwCreationDisposition], 2; dwCreationDisposition
0x1800805db  mov     edx, 0C0000000h; dwDesiredAccess
0x1800805e0  call    cs:__imp_CreateFileW
0x1800805e7  nop     dword ptr [rax+rax+00h]
0x1800805ec  mov     rdi, rax
0x1800805ef  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800805f3  jz      loc_1800804AB
0x1800805f9  mov     rcx, rax; hFile
0x1800805fc  call    cs:__imp_GetFileType
0x180080603  nop     dword ptr [rax+rax+00h]
0x180080608  cmp     eax, 1
0x18008060b  jz      short loc_180080623
0x18008060d  mov     ebx, 26Dh
0x180080612  mov     rcx, rdi; hObject
0x180080615  call    cs:__imp_CloseHandle
0x18008061c  nop     dword ptr [rax+rax+00h]
0x180080621  jmp     short loc_180080681
0x180080623  mov     rcx, rsi; lpFileName
0x180080626  call    FFileExists
0x18008062b  test    eax, eax
0x18008062d  jz      short loc_180080612
0x18008062f  lea     rdx, [rsp+290h+pszDest]; String1
0x180080634  mov     rcx, rdi; hFile
0x180080637  call    IsFileNotASymlink
0x18008063c  mov     ebx, eax
0x18008063e  test    eax, eax
0x180080640  jnz     short loc_180080612
0x180080642  mov     rcx, rdi; hObject
0x180080645  call    cs:__imp_CloseHandle
0x18008064c  nop     dword ptr [rax+rax+00h]
0x180080651  xor     r8d, r8d; bFailIfExists
0x180080654  lea     rdx, [rsp+290h+pszDest]; lpNewFileName
0x180080659  mov     rcx, rsi; lpExistingFileName
0x18008065c  call    cs:__imp_CopyFileW
0x180080663  nop     dword ptr [rax+rax+00h]
0x180080668  test    eax, eax
0x18008066a  jnz     short loc_180080681
0x18008066c  call    cs:__imp_GetLastError
0x180080673  nop     dword ptr [rax+rax+00h]
0x180080678  mov     ebx, eax
0x18008067a  jmp     short loc_180080681
0x18008067c  mov     ebx, 57h ; 'W'
0x180080681  test    r14, r14
0x180080684  jz      short loc_180080695
0x180080686  mov     rcx, r14; hMem
0x180080689  call    cs:__imp_GlobalFree
0x180080690  nop     dword ptr [rax+rax+00h]
0x180080695  test    r15, r15
0x180080698  jz      short loc_1800806BF
0x18008069a  test    ebx, ebx
0x18008069c  jz      short loc_1800806A7
0x18008069e  mov     qword ptr [r15], 0
0x1800806a5  jmp     short loc_1800806BF
0x1800806a7  lea     rcx, [rsp+290h+pszDest]; pszSrc
0x1800806ac  call    StrDup
0x1800806b1  test    rax, rax
0x1800806b4  mov     [r15], rax
0x1800806b7  mov     ecx, 8
0x1800806bc  cmovz   ebx, ecx
0x1800806bf  mov     eax, ebx
0x1800806c1  mov     rcx, [rbp+190h+var_30]
0x1800806c8  xor     rcx, rsp; StackCookie
0x1800806cb  call    __security_check_cookie
0x1800806d0  mov     rbx, [rsp+290h+arg_10]
0x1800806d8  add     rsp, 270h
0x1800806df  pop     r15
0x1800806e1  pop     r14
0x1800806e3  pop     rdi
0x1800806e4  pop     rsi
0x1800806e5  pop     rbp
0x1800806e6  retn
```
