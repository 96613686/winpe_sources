# FtpDoesFileExist(void *,char const *,_WIN32_FIND_DATAA *,ulong)

- ea: `0x18000c93c`
- end: `0x18000cadd`
- name: `?FtpDoesFileExist@@YAJPEAXPEBDPEAU_WIN32_FIND_DATAA@@K@Z`
- size: `417`
- prototype: `__int64 __fastcall(HINTERNET hConnect, LPCSTR lpString2, struct _WIN32_FIND_DATAA *lpvFindData, DWORD dwFlags)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800117c0`
- `0x180024638`

## callees

- `0x180002240`
- `0x180002b60`
- `0x18000c93c`
- `0x18000d098`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca97`
- `KERNEL32!lstrlenA` at `0x18000c9d3`
- `KERNEL32!lstrlenA` at `0x18000ca56`
- `KERNEL32!lstrlenA` at `0x18000ca64`
- `KERNEL32!lstrlenA` at `0x18000c9d3`
- `KERNEL32!lstrlenA` at `0x18000ca56`
- `KERNEL32!lstrlenA` at `0x18000ca64`
- `KERNEL32!lstrcmpiA` at `0x18000ca49`
- `KERNEL32!lstrcmpiA` at `0x18000ca49`
- `KERNEL32!lstrcmpA` at `0x18000ca7b`
- `KERNEL32!lstrcmpA` at `0x18000ca7b`
- `WININET!FtpFindFirstFileA` at `0x18000ca18`
- `WININET!FtpFindFirstFileA` at `0x18000ca18`
- `WININET!InternetCloseHandle` at `0x18000cab7`
- `WININET!InternetCloseHandle` at `0x18000cab7`
- `WININET!InternetFindNextFileA` at `0x18000ca8d`
- `WININET!InternetFindNextFileA` at `0x18000ca8d`

## string_xrefs

- `0x18000ca6d`: `: No such file or directory`

## pseudocode

```c
__int64 __fastcall FtpDoesFileExist(
        HINTERNET hConnect,
        LPCSTR lpString2,
        struct _WIN32_FIND_DATAA *lpvFindData,
        DWORD dwFlags)
{
  struct _WIN32_FIND_DATAA *v8; // rsi
  __int64 v9; // rax
  CHAR *v10; // rcx
  LPCSTR v11; // rdx
  __int64 v12; // r8
  CHAR *v13; // rax
  void *FirstFileA; // rbp
  signed int LastError; // eax
  unsigned int v16; // ebx
  int v17; // eax
  signed int v18; // eax
  CHAR v20[320]; // [rsp+30h] [rbp-288h] BYREF
  CHAR String[272]; // [rsp+170h] [rbp-148h] BYREF

  memset_0(v20, 0, sizeof(v20));
  v8 = (struct _WIN32_FIND_DATAA *)v20;
  v9 = 2147483646;
  v10 = String;
  if ( lpvFindData )
    v8 = lpvFindData;
  v11 = lpString2;
  v12 = 260;
  do
  {
    if ( !v9 )
      break;
    if ( !*v11 )
      break;
    *v10++ = *v11++;
    --v9;
    --v12;
  }
  while ( v12 );
  v13 = v10 - 1;
  if ( v12 )
    v13 = v10;
  *v13 = 0;
  if ( v20[lstrlenA(String) + 319] != 42 )
    StringCchCatA(String, 0x104u, "*");
  FirstFileA = FtpFindFirstFileA(hConnect, String, v8, dwFlags, 0);
  if ( FirstFileA )
    goto LABEL_28;
  LastError = GetLastError();
  v16 = LastError;
  if ( LastError > 0 )
    v16 = (unsigned __int16)LastError | 0x80070000;
  if ( !v16 )
  {
LABEL_28:
    while ( lstrcmpiA(v8->cFileName, lpString2) )
    {
      if ( (unsigned int)lstrlenA(v8->cFileName) > 0x1B )
      {
        v17 = lstrlenA(v8->cFileName);
        if ( !lstrcmpA((LPCSTR)&v8->ftLastAccessTime.dwHighDateTime + v17 + 1, ": No such file or directory") )
          break;
      }
      v16 = 0;
      if ( !InternetFindNextFileA(FirstFileA, v8) )
      {
        v18 = GetLastError();
        v16 = v18;
        if ( v18 > 0 )
          v16 = (unsigned __int16)v18 | 0x80070000;
      }
      if ( v16 )
        goto LABEL_24;
    }
    v16 = 0;
LABEL_24:
    InternetCloseHandle(FirstFileA);
  }
  return v16;
}

```

## disassembly

```asm
0x18000c93c  push    rbx
0x18000c93e  push    rbp
0x18000c93f  push    rsi
0x18000c940  push    rdi
0x18000c941  push    r14
0x18000c943  sub     rsp, 290h
0x18000c94a  mov     rax, cs:__security_cookie
0x18000c951  xor     rax, rsp
0x18000c954  mov     [rsp+2B8h+var_38], rax
0x18000c95c  mov     rbx, r8
0x18000c95f  mov     r14, rdx
0x18000c962  mov     rdi, rcx
0x18000c965  xor     edx, edx; Val
0x18000c967  mov     r8d, 140h; Size
0x18000c96d  lea     rcx, [rsp+2B8h+var_288]; void *
0x18000c972  mov     ebp, r9d
0x18000c975  call    memset_0
0x18000c97a  test    rbx, rbx
0x18000c97d  lea     rsi, [rsp+2B8h+var_288]
0x18000c982  mov     eax, 7FFFFFFEh
0x18000c987  lea     rcx, [rsp+2B8h+String]
0x18000c98f  cmovnz  rsi, rbx
0x18000c993  mov     rdx, r14
0x18000c996  mov     ebx, 104h
0x18000c99b  mov     r8d, ebx
0x18000c99e  test    rax, rax
0x18000c9a1  jz      short loc_18000C9BD
0x18000c9a3  mov     r9b, [rdx]
0x18000c9a6  test    r9b, r9b
0x18000c9a9  jz      short loc_18000C9BD
0x18000c9ab  mov     [rcx], r9b
0x18000c9ae  inc     rdx
0x18000c9b1  inc     rcx
0x18000c9b4  dec     rax
0x18000c9b7  sub     r8, 1
0x18000c9bb  jnz     short loc_18000C99E
0x18000c9bd  lea     rax, [rcx-1]
0x18000c9c1  test    r8, r8
0x18000c9c4  cmovnz  rax, rcx
0x18000c9c8  lea     rcx, [rsp+2B8h+String]; lpString
0x18000c9d0  mov     byte ptr [rax], 0
0x18000c9d3  call    cs:__imp_lstrlenA
0x18000c9d9  movsxd  r8, eax
0x18000c9dc  cmp     [rsp+r8+2B8h+var_149], 2Ah ; '*'
0x18000c9e5  jz      short loc_18000C9FE
0x18000c9e7  lea     r8, asc_18002B65C; "*"
0x18000c9ee  mov     rdx, rbx; unsigned __int64
0x18000c9f1  lea     rcx, [rsp+2B8h+String]; char *
0x18000c9f9  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18000c9fe  mov     r9d, ebp; dwFlags
0x18000ca01  mov     [rsp+2B8h+dwContext], 0; dwContext
0x18000ca0a  mov     r8, rsi; lpFindFileData
0x18000ca0d  lea     rdx, [rsp+2B8h+String]; lpszSearchFile
0x18000ca15  mov     rcx, rdi; hConnect
0x18000ca18  call    cs:__imp_FtpFindFirstFileA
0x18000ca1e  mov     rbp, rax
0x18000ca21  test    rax, rax
0x18000ca24  jnz     short loc_18000CA3F
0x18000ca26  call    cs:__imp_GetLastError
0x18000ca2c  mov     ebx, eax
0x18000ca2e  test    eax, eax
0x18000ca30  jle     short loc_18000CA3B
0x18000ca32  movzx   ebx, ax
0x18000ca35  or      ebx, 80070000h
0x18000ca3b  test    ebx, ebx
0x18000ca3d  jnz     short loc_18000CABD
0x18000ca3f  lea     rdi, [rsi+2Ch]
0x18000ca43  mov     rdx, r14; lpString2
0x18000ca46  mov     rcx, rdi; lpString1
0x18000ca49  call    cs:__imp_lstrcmpiA
0x18000ca4f  test    eax, eax
0x18000ca51  jz      short loc_18000CAB2
0x18000ca53  mov     rcx, rdi; lpString
0x18000ca56  call    cs:__imp_lstrlenA
0x18000ca5c  cmp     eax, 1Bh
0x18000ca5f  jbe     short loc_18000CA85
0x18000ca61  mov     rcx, rdi; lpString
0x18000ca64  call    cs:__imp_lstrlenA
0x18000ca6a  movsxd  rcx, eax
0x18000ca6d  lea     rdx, String2; ": No such file or directory"
0x18000ca74  add     rcx, 11h
0x18000ca78  add     rcx, rsi; lpString1
0x18000ca7b  call    cs:__imp_lstrcmpA
0x18000ca81  test    eax, eax
0x18000ca83  jz      short loc_18000CAB2
0x18000ca85  mov     rdx, rsi; lpvFindData
0x18000ca88  mov     rcx, rbp; hFind
0x18000ca8b  xor     ebx, ebx
0x18000ca8d  call    cs:__imp_InternetFindNextFileA
0x18000ca93  test    eax, eax
0x18000ca95  jnz     short loc_18000CAAC
0x18000ca97  call    cs:__imp_GetLastError
0x18000ca9d  mov     ebx, eax
0x18000ca9f  test    eax, eax
0x18000caa1  jle     short loc_18000CAAC
0x18000caa3  movzx   ebx, ax
0x18000caa6  or      ebx, 80070000h
0x18000caac  test    ebx, ebx
0x18000caae  jz      short loc_18000CA43
0x18000cab0  jmp     short loc_18000CAB4
0x18000cab2  xor     ebx, ebx
0x18000cab4  mov     rcx, rbp; hInternet
0x18000cab7  call    cs:__imp_InternetCloseHandle
0x18000cabd  mov     eax, ebx
0x18000cabf  mov     rcx, [rsp+2B8h+var_38]
0x18000cac7  xor     rcx, rsp; StackCookie
0x18000caca  call    __security_check_cookie
0x18000cacf  add     rsp, 290h
0x18000cad6  pop     r14
0x18000cad8  pop     rdi
0x18000cad9  pop     rsi
0x18000cada  pop     rbp
0x18000cadb  pop     rbx
0x18000cadc  retn
```
