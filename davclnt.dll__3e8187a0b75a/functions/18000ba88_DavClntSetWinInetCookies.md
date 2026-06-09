# DavClntSetWinInetCookies

- ea: `0x18000ba88`
- end: `0x18000bcb9`
- name: `DavClntSetWinInetCookies`
- size: `561`
- prototype: `__int64 __fastcall(LPCWSTR UncPath, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b8dc`

## callees

- `0x18000ba88`
- `0x180010a14`
- `0x180010be8`
- `0x180010c28`
- `0x180010c88`
- `0x180011e82`
- `0x180011eb0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bbfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bbfc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bb41`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bb41`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000bc89`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000bc89`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000bb18`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000bb18`
- `DAVHLPR!DavGetHTTPFromUNCPath` at `0x18000bb98`
- `DAVHLPR!DavGetHTTPFromUNCPath` at `0x18000bb98`

## string_xrefs

- `0x18000bb11`: `WinInet.dll`

## pseudocode

```c
__int64 __fastcall DavClntSetWinInetCookies(LPCWSTR UncPath, __int64 a2)
{
  HMODULE LibraryW; // rax
  HMODULE v5; // rbp
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  FARPROC ProcAddress; // r12
  DWORD LastError; // eax
  DWORD HTTPFromUNCPath; // eax
  int v11; // edx
  WCHAR *v12; // r9
  DWORD Size[4]; // [rsp+30h] [rbp-258h] BYREF
  WCHAR Url[264]; // [rsp+40h] [rbp-248h] BYREF

  memset_0(Url, 0, 0x208u);
  Size[0] = 260;
  if ( UncPath && a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 333, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, UncPath);
    LibraryW = LoadLibraryW(L"WinInet.dll");
    v5 = LibraryW;
    if ( !LibraryW )
    {
      v6 = 1157;
LABEL_8:
      v7 = WPP_GLOBAL_Control;
      goto LABEL_26;
    }
    ProcAddress = GetProcAddress(LibraryW, "InternetSetCookieW");
    if ( !ProcAddress )
    {
      LastError = GetLastError();
      v6 = LastError;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_26;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 334, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, LastError);
        goto LABEL_8;
      }
      goto LABEL_30;
    }
    HTTPFromUNCPath = DavGetHTTPFromUNCPath(UncPath, Url, Size);
    v6 = HTTPFromUNCPath;
    if ( HTTPFromUNCPath )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_30;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_26;
      v11 = 335;
      LODWORD(v12) = (_DWORD)UncPath;
    }
    else
    {
      v6 = 0;
      if ( ((unsigned int (__fastcall *)(WCHAR *, _QWORD, __int64))ProcAddress)(Url, 0, a2 + 16) )
        goto LABEL_8;
      HTTPFromUNCPath = GetLastError();
      v6 = HTTPFromUNCPath;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
LABEL_30:
        FreeLibrary(v5);
        return v6;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_26;
      v11 = 336;
      v12 = Url;
    }
    WPP_SF_Sd(v7[2], v11, (unsigned int)WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, (_DWORD)v12, HTTPFromUNCPath);
    goto LABEL_8;
  }
  v7 = WPP_GLOBAL_Control;
  v5 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 332, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  v6 = 87;
LABEL_26:
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x20) != 0 )
    WPP_SF_d(v7[2], 337, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v6);
  if ( v5 )
    goto LABEL_30;
  return v6;
}

```

## disassembly

```asm
0x18000ba88  mov     [rsp+arg_10], rbx
0x18000ba8d  push    rbp
0x18000ba8e  push    rdi
0x18000ba8f  push    r12
0x18000ba91  push    r14
0x18000ba93  push    r15
0x18000ba95  sub     rsp, 260h
0x18000ba9c  mov     rax, cs:__security_cookie
0x18000baa3  xor     rax, rsp
0x18000baa6  mov     [rsp+288h+var_38], rax
0x18000baae  mov     r15, rdx
0x18000bab1  mov     r14, rcx
0x18000bab4  xor     edx, edx; Val
0x18000bab6  lea     rcx, [rsp+288h+Url]; void *
0x18000babb  mov     r8d, 208h; Size
0x18000bac1  call    memset_0
0x18000bac6  mov     [rsp+288h+Size], 104h
0x18000bace  test    r14, r14
0x18000bad1  jz      loc_18000BC22
0x18000bad7  test    r15, r15
0x18000bada  jz      loc_18000BC22
0x18000bae0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bae7  lea     rdi, WPP_GLOBAL_Control
0x18000baee  cmp     rcx, rdi
0x18000baf1  jz      short loc_18000BB11
0x18000baf3  test    byte ptr [rcx+1Ch], 20h
0x18000baf7  jz      short loc_18000BB11
0x18000baf9  mov     rcx, [rcx+10h]
0x18000bafd  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000bb04  mov     edx, 14Dh
0x18000bb09  mov     r9, r14
0x18000bb0c  call    WPP_SF_S
0x18000bb11  lea     rcx, LibFileName; "WinInet.dll"
0x18000bb18  call    cs:__imp_LoadLibraryW
0x18000bb1e  mov     rbp, rax
0x18000bb21  test    rax, rax
0x18000bb24  jnz     short loc_18000BB37
0x18000bb26  mov     ebx, 485h
0x18000bb2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb32  jmp     loc_18000BC5E
0x18000bb37  lea     rdx, aInternetsetcoo; "InternetSetCookieW"
0x18000bb3e  mov     rcx, rax; hModule
0x18000bb41  call    cs:__imp_GetProcAddress
0x18000bb47  mov     r12, rax
0x18000bb4a  test    rax, rax
0x18000bb4d  jnz     short loc_18000BB8B
0x18000bb4f  call    cs:__imp_GetLastError
0x18000bb55  mov     ebx, eax
0x18000bb57  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb5e  cmp     rcx, rdi
0x18000bb61  jz      loc_18000BC86
0x18000bb67  test    byte ptr [rcx+1Ch], 1
0x18000bb6b  jz      loc_18000BC5E
0x18000bb71  mov     rcx, [rcx+10h]
0x18000bb75  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000bb7c  mov     edx, 14Eh
0x18000bb81  mov     r9d, eax
0x18000bb84  call    WPP_SF_d
0x18000bb89  jmp     short loc_18000BB2B
0x18000bb8b  lea     r8, [rsp+288h+Size]; lpSize
0x18000bb90  mov     rcx, r14; UncPath
0x18000bb93  lea     rdx, [rsp+288h+Url]; Url
0x18000bb98  call    cs:__imp_DavGetHTTPFromUNCPath
0x18000bb9e  mov     ebx, eax
0x18000bba0  test    eax, eax
0x18000bba2  jz      short loc_18000BBDF
0x18000bba4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bbab  cmp     rcx, rdi
0x18000bbae  jz      loc_18000BC86
0x18000bbb4  test    byte ptr [rcx+1Ch], 1
0x18000bbb8  jz      loc_18000BC5E
0x18000bbbe  mov     edx, 14Fh
0x18000bbc3  mov     r9, r14
0x18000bbc6  mov     rcx, [rcx+10h]
0x18000bbca  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000bbd1  mov     [rsp+288h+var_268], eax
0x18000bbd5  call    WPP_SF_Sd
0x18000bbda  jmp     loc_18000BB2B
0x18000bbdf  lea     r8, [r15+10h]
0x18000bbe3  xor     edx, edx
0x18000bbe5  lea     rcx, [rsp+288h+Url]
0x18000bbea  mov     rax, r12
0x18000bbed  xor     ebx, ebx
0x18000bbef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbf4  test    eax, eax
0x18000bbf6  jnz     loc_18000BB2B
0x18000bbfc  call    cs:__imp_GetLastError
0x18000bc02  mov     ebx, eax
0x18000bc04  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc0b  cmp     rcx, rdi
0x18000bc0e  jz      short loc_18000BC86
0x18000bc10  test    byte ptr [rcx+1Ch], 1
0x18000bc14  jz      short loc_18000BC5E
0x18000bc16  mov     edx, 150h
0x18000bc1b  lea     r9, [rsp+288h+Url]
0x18000bc20  jmp     short loc_18000BBC6
0x18000bc22  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc29  lea     rdi, WPP_GLOBAL_Control
0x18000bc30  xor     ebp, ebp
0x18000bc32  cmp     rcx, rdi
0x18000bc35  jz      short loc_18000BC59
0x18000bc37  test    byte ptr [rcx+1Ch], 1
0x18000bc3b  jz      short loc_18000BC59
0x18000bc3d  mov     rcx, [rcx+10h]
0x18000bc41  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000bc48  mov     edx, 14Ch
0x18000bc4d  call    WPP_SF_
0x18000bc52  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc59  mov     ebx, 57h ; 'W'
0x18000bc5e  cmp     rcx, rdi
0x18000bc61  jz      short loc_18000BC81
0x18000bc63  test    byte ptr [rcx+1Ch], 20h
0x18000bc67  jz      short loc_18000BC81
0x18000bc69  mov     rcx, [rcx+10h]
0x18000bc6d  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000bc74  mov     edx, 151h
0x18000bc79  mov     r9d, ebx
0x18000bc7c  call    WPP_SF_d
0x18000bc81  test    rbp, rbp
0x18000bc84  jz      short loc_18000BC8F
0x18000bc86  mov     rcx, rbp; hLibModule
0x18000bc89  call    cs:__imp_FreeLibrary
0x18000bc8f  mov     eax, ebx
0x18000bc91  mov     rcx, [rsp+288h+var_38]
0x18000bc99  xor     rcx, rsp; StackCookie
0x18000bc9c  call    __security_check_cookie
0x18000bca1  mov     rbx, [rsp+288h+arg_10]
0x18000bca9  add     rsp, 260h
0x18000bcb0  pop     r15
0x18000bcb2  pop     r14
0x18000bcb4  pop     r12
0x18000bcb6  pop     rdi
0x18000bcb7  pop     rbp
0x18000bcb8  retn
```
