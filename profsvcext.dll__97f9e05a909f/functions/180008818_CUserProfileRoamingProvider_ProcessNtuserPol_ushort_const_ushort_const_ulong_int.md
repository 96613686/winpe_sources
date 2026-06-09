# CUserProfileRoamingProvider::_ProcessNtuserPol(ushort const *,ushort const *,ulong,int)

- ea: `0x180008818`
- end: `0x180008b16`
- name: `?_ProcessNtuserPol@CUserProfileRoamingProvider@@AEAAJPEBG0KH@Z`
- size: `766`
- prototype: `__int64 __fastcall(CUserProfileRoamingProvider *this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180008258`
- `0x180012314`

## callees

- `0x180008818`
- `0x180008b1c`
- `0x18000a074`
- `0x18000a520`
- `0x18000aef8`
- `0x18001da3c`
- `0x18001e520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a66`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180008a38`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180008a47`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180008a9f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180008aae`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180008a38`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180008a47`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180008a9f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180008aae`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180008959`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180008959`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180008a5c`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180008a5c`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800088f4`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800088f4`
- `SHELL32!SHCreateDirectoryExW` at `0x180008974`
- `SHELL32!SHCreateDirectoryExW` at `0x180008974`

## string_xrefs

- `0x18000899d`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180008a7f`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180008ac9`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180008ae7`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`

## pseudocode

```c
__int64 __fastcall CUserProfileRoamingProvider::_ProcessNtuserPol(
        CUserProfileRoamingProvider *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 a4,
        int a5)
{
  signed int BasicProfileFolderPath; // ebx
  __int64 v8; // rdx
  DWORD FileAttributesW; // eax
  int v10; // eax
  int v11; // r9d
  int v12; // eax
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  signed int LastError; // eax
  const int *v17; // [rsp+20h] [rbp-E0h]
  WCHAR ExistingFileName[264]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[528]; // [rsp+240h] [rbp+140h] BYREF
  WCHAR NewFileName[1032]; // [rsp+450h] [rbp+350h] BYREF
  WCHAR FileName[1032]; // [rsp+C60h] [rbp+B60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+14B8h] [rbp+13B8h]

  memset_0(ExistingFileName, 0, 0x20Au);
  memset_0(NewFileName, 0, 0x802u);
  memset_0(v19, 0, 0x20Au);
  memset_0(FileName, 0, 0x802u);
  v17 = &qword_180023CF8;
  BasicProfileFolderPath = StringCchPrintfW(ExistingFileName, 0x105u, L"%s%s%s", a2);
  if ( BasicProfileFolderPath < 0 )
  {
    v8 = 2172;
LABEL_26:
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
      (const char *)(unsigned int)BasicProfileFolderPath,
      (int)v17);
LABEL_27:
    v13 = (unsigned int)BasicProfileFolderPath;
    v14 = 2252;
    goto LABEL_28;
  }
  BasicProfileFolderPath = GetBasicProfileFolderPath(4, 0, v19, 261);
  if ( BasicProfileFolderPath < 0 )
  {
    v8 = 2217;
    goto LABEL_26;
  }
  v17 = (const int *)L"\\Microsoft\\GroupPolicy\\Users\\";
  BasicProfileFolderPath = StringCchPrintfW(FileName, 0x401u, L"%s%s%s", v19);
  if ( BasicProfileFolderPath < 0 )
  {
    v8 = 2212;
    goto LABEL_26;
  }
  if ( !a5 )
  {
    FileAttributesW = GetFileAttributesW(FileName);
    if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
    {
      v10 = SHCreateDirectoryExW(0, FileName, 0);
      BasicProfileFolderPath = v10;
      if ( v10 )
      {
        if ( v10 != 80 && v10 != 183 )
        {
          if ( v10 > 0 )
            BasicProfileFolderPath = (unsigned __int16)v10 | 0x80070000;
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x894,
            (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
            (const char *)(unsigned int)BasicProfileFolderPath,
            (int)L"\\Microsoft\\GroupPolicy\\Users\\");
          if ( BasicProfileFolderPath < 0 )
            goto LABEL_27;
        }
      }
    }
  }
  BasicProfileFolderPath = StringCchPrintfW(NewFileName, 0x401u, L"%s%s%s", FileName, &qword_180023CF8, L"ntuser.pol");
  if ( BasicProfileFolderPath < 0 )
  {
    v8 = 2206;
    goto LABEL_26;
  }
  if ( a5 )
  {
    v12 = CopyRupFile((const char *)NewFileName, ExistingFileName, a4 & 0x8000, v11);
    BasicProfileFolderPath = v12;
    if ( v12 < 0 )
    {
      v13 = (unsigned int)v12;
      v14 = 2229;
LABEL_28:
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)v13,
        (int)v17);
    }
  }
  else
  {
    SetFileAttributesW(ExistingFileName, 0x80u);
    SetFileAttributesW(NewFileName, 0x80u);
    if ( !CopyFileW(ExistingFileName, NewFileName, 0) )
    {
      LastError = GetLastError();
      BasicProfileFolderPath = LastError;
      if ( LastError > 0 )
        BasicProfileFolderPath = (unsigned __int16)LastError | 0x80070000;
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x8C0,
        (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)(unsigned int)BasicProfileFolderPath,
        (int)v17);
    }
    SetFileAttributesW(ExistingFileName, 7u);
    SetFileAttributesW(NewFileName, 7u);
  }
  return (unsigned int)BasicProfileFolderPath;
}

```

## disassembly

```asm
0x180008818  push    rbp
0x18000881a  push    rbx
0x18000881b  push    rsi
0x18000881c  push    rdi
0x18000881d  push    r13
0x18000881f  push    r14
0x180008821  push    r15
0x180008823  lea     rbp, [rsp-1380h]
0x18000882b  mov     eax, 1480h
0x180008830  call    _alloca_probe
0x180008835  sub     rsp, rax
0x180008838  mov     rax, cs:__security_cookie
0x18000883f  xor     rax, rsp
0x180008842  mov     [rbp+13B0h+var_40], rax
0x180008849  mov     rdi, r8
0x18000884c  lea     rcx, [rsp+14B0h+ExistingFileName]; void *
0x180008851  mov     rbx, rdx
0x180008854  mov     r15d, 20Ah
0x18000885a  mov     r8d, r15d; Size
0x18000885d  xor     edx, edx; Val
0x18000885f  mov     esi, r9d
0x180008862  call    memset_0
0x180008867  mov     r14d, 802h
0x18000886d  lea     rcx, [rbp+13B0h+NewFileName]; void *
0x180008874  mov     r8d, r14d; Size
0x180008877  xor     edx, edx; Val
0x180008879  call    memset_0
0x18000887e  mov     r8d, r15d; Size
0x180008881  lea     rcx, [rbp+13B0h+var_1270]; void *
0x180008888  xor     edx, edx; Val
0x18000888a  call    memset_0
0x18000888f  mov     r8d, r14d; Size
0x180008892  lea     rcx, [rbp+13B0h+FileName]; void *
0x180008899  xor     edx, edx; Val
0x18000889b  call    memset_0
0x1800088a0  lea     rax, qword_180023CF8
0x1800088a7  mov     r14d, 105h
0x1800088ad  lea     r13, ?c_szNTUserPol@@3QBGB; "ntuser.pol"
0x1800088b4  mov     edx, r14d; unsigned __int64
0x1800088b7  mov     [rsp+14B0h+var_1488], r13
0x1800088bc  lea     r8, aSSS; "%s%s%s"
0x1800088c3  mov     r9, rbx
0x1800088c6  mov     qword ptr [rsp+14B0h+var_1490], rax; int
0x1800088cb  lea     rcx, [rsp+14B0h+ExistingFileName]; unsigned __int16 *
0x1800088d0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800088d5  mov     ebx, eax
0x1800088d7  test    eax, eax
0x1800088d9  jns     short loc_1800088E5
0x1800088db  mov     edx, 87Ch
0x1800088e0  jmp     loc_180008AC2
0x1800088e5  xor     edx, edx
0x1800088e7  lea     r8, [rbp+13B0h+var_1270]
0x1800088ee  mov     r9, r14
0x1800088f1  lea     ecx, [rdx+4]
0x1800088f4  call    cs:__imp_GetBasicProfileFolderPath
0x1800088fa  mov     ebx, eax
0x1800088fc  test    eax, eax
0x1800088fe  js      loc_180008ABD
0x180008904  lea     rax, aMicrosoftGroup; "\\Microsoft\\GroupPolicy\\Users\\"
0x18000890b  mov     [rsp+14B0h+var_1488], rdi
0x180008910  mov     r15d, 401h
0x180008916  mov     qword ptr [rsp+14B0h+var_1490], rax; int
0x18000891b  mov     edx, r15d; unsigned __int64
0x18000891e  lea     r9, [rbp+13B0h+var_1270]
0x180008925  lea     r8, aSSS; "%s%s%s"
0x18000892c  lea     rcx, [rbp+13B0h+FileName]; unsigned __int16 *
0x180008933  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008938  mov     ebx, eax
0x18000893a  test    eax, eax
0x18000893c  js      loc_180008AB6
0x180008942  mov     edi, [rbp+13B0h+arg_20]
0x180008948  mov     r14d, 80070000h
0x18000894e  test    edi, edi
0x180008950  jnz     short loc_1800089B9
0x180008952  lea     rcx, [rbp+13B0h+FileName]; lpFileName
0x180008959  call    cs:__imp_GetFileAttributesW
0x18000895f  cmp     eax, 0FFFFFFFFh
0x180008962  jz      short loc_180008968
0x180008964  test    al, 10h
0x180008966  jnz     short loc_1800089B9
0x180008968  xor     r8d, r8d; psa
0x18000896b  lea     rdx, [rbp+13B0h+FileName]; pszPath
0x180008972  xor     ecx, ecx; hwnd
0x180008974  call    cs:__imp_SHCreateDirectoryExW
0x18000897a  mov     ebx, eax
0x18000897c  test    eax, eax
0x18000897e  jz      short loc_1800089B9
0x180008980  cmp     eax, 50h ; 'P'
0x180008983  jz      short loc_1800089B9
0x180008985  cmp     eax, 0B7h
0x18000898a  jz      short loc_1800089B9
0x18000898c  test    eax, eax
0x18000898e  jle     short loc_180008996
0x180008990  movzx   ebx, ax
0x180008993  or      ebx, r14d
0x180008996  mov     rcx, [rbp+13B8h]; this
0x18000899d  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x1800089a4  mov     r9d, ebx; char *
0x1800089a7  mov     edx, 894h; void *
0x1800089ac  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800089b1  test    ebx, ebx
0x1800089b3  js      loc_180008AD8
0x1800089b9  lea     rax, qword_180023CF8
0x1800089c0  mov     [rsp+14B0h+var_1488], r13
0x1800089c5  lea     r9, [rbp+13B0h+FileName]
0x1800089cc  mov     qword ptr [rsp+14B0h+var_1490], rax; int
0x1800089d1  lea     r8, aSSS; "%s%s%s"
0x1800089d8  mov     rdx, r15; unsigned __int64
0x1800089db  lea     rcx, [rbp+13B0h+NewFileName]; unsigned __int16 *
0x1800089e2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800089e7  mov     ebx, eax
0x1800089e9  test    eax, eax
0x1800089eb  jns     short loc_1800089F7
0x1800089ed  mov     edx, 89Eh
0x1800089f2  jmp     loc_180008AC2
0x1800089f7  test    edi, edi
0x1800089f9  jz      short loc_180008A2C
0x1800089fb  and     esi, 8000h
0x180008a01  lea     rdx, [rsp+14B0h+ExistingFileName]; unsigned __int16 *
0x180008a06  mov     r8d, esi; int
0x180008a09  lea     rcx, [rbp+13B0h+NewFileName]; unsigned __int16 *
0x180008a10  call    ?CopyRupFile@@YAJPEBG0HH@Z; CopyRupFile(ushort const *,ushort const *,int,int)
0x180008a15  mov     ebx, eax
0x180008a17  test    eax, eax
0x180008a19  jns     loc_180008AF3
0x180008a1f  mov     r9d, eax
0x180008a22  mov     edx, 8B5h
0x180008a27  jmp     loc_180008AE0
0x180008a2c  mov     edi, 80h
0x180008a31  lea     rcx, [rsp+14B0h+ExistingFileName]; lpFileName
0x180008a36  mov     edx, edi; dwFileAttributes
0x180008a38  call    cs:__imp_SetFileAttributesW
0x180008a3e  mov     edx, edi; dwFileAttributes
0x180008a40  lea     rcx, [rbp+13B0h+NewFileName]; lpFileName
0x180008a47  call    cs:__imp_SetFileAttributesW
0x180008a4d  xor     r8d, r8d; bFailIfExists
0x180008a50  lea     rdx, [rbp+13B0h+NewFileName]; lpNewFileName
0x180008a57  lea     rcx, [rsp+14B0h+ExistingFileName]; lpExistingFileName
0x180008a5c  call    cs:__imp_CopyFileW
0x180008a62  test    eax, eax
0x180008a64  jnz     short loc_180008A93
0x180008a66  call    cs:__imp_GetLastError
0x180008a6c  mov     ebx, eax
0x180008a6e  test    eax, eax
0x180008a70  jle     short loc_180008A78
0x180008a72  movzx   ebx, ax
0x180008a75  or      ebx, r14d
0x180008a78  mov     rcx, [rbp+13B8h]; this
0x180008a7f  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180008a86  mov     r9d, ebx; char *
0x180008a89  mov     edx, 8C0h; void *
0x180008a8e  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180008a93  mov     edi, 7
0x180008a98  lea     rcx, [rsp+14B0h+ExistingFileName]; lpFileName
0x180008a9d  mov     edx, edi; dwFileAttributes
0x180008a9f  call    cs:__imp_SetFileAttributesW
0x180008aa5  mov     edx, edi; dwFileAttributes
0x180008aa7  lea     rcx, [rbp+13B0h+NewFileName]; lpFileName
0x180008aae  call    cs:__imp_SetFileAttributesW
0x180008ab4  jmp     short loc_180008AF3
0x180008ab6  mov     edx, 8A4h
0x180008abb  jmp     short loc_180008AC2
0x180008abd  mov     edx, 8A9h; void *
0x180008ac2  mov     rcx, [rbp+13B8h]; this
0x180008ac9  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180008ad0  mov     r9d, ebx; char *
0x180008ad3  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180008ad8  mov     r9d, ebx; char *
0x180008adb  mov     edx, 8CCh; void *
0x180008ae0  mov     rcx, [rbp+13B8h]; this
0x180008ae7  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180008aee  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180008af3  mov     eax, ebx
0x180008af5  mov     rcx, [rbp+13B0h+var_40]
0x180008afc  xor     rcx, rsp; StackCookie
0x180008aff  call    __security_check_cookie
0x180008b04  add     rsp, 1480h
0x180008b0b  pop     r15
0x180008b0d  pop     r14
0x180008b0f  pop     r13
0x180008b11  pop     rdi
0x180008b12  pop     rsi
0x180008b13  pop     rbx
0x180008b14  pop     rbp
0x180008b15  retn
```
