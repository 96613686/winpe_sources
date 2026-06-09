# _FormatCrlPreFetchEvent

- ea: `0x18001ec64`
- end: `0x18001eedf`
- name: `_FormatCrlPreFetchEvent`
- size: `635`
- prototype: `char *__fastcall(const char *, __int64, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18001f310`

## callees

- `0x180007c00`
- `0x18000a990`
- `0x180016d50`
- `0x18001ea48`
- `0x18001eac8`
- `0x18001ec64`
- `0x18002656a`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ee69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ee69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ed36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ed36`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18001ece3`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18001ece3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001ede3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001ee26`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001ede3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001ee26`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatA` at `0x18001ed2d`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatA` at `0x18001ed2d`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatA` at `0x18001ed0b`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatA` at `0x18001ed0b`

## pseudocode

```c
char *__fastcall FormatCrlPreFetchEvent(const char *a1, __int64 a2, int a3)
{
  CHAR *v6; // rbx
  __int64 v7; // r12
  DWORD CurrentProcessId; // eax
  __int64 v9; // rdi
  __int64 v10; // rsi
  const WCHAR *v11; // r14
  int v12; // eax
  int v13; // r15d
  CHAR *v14; // rax
  SIZE_T v15; // rsi
  char *v16; // rax
  char *v17; // rdi
  struct _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-B0h] BYREF
  CHAR TimeStr[64]; // [rsp+60h] [rbp-A0h] BYREF
  CHAR DateStr[64]; // [rsp+A0h] [rbp-60h] BYREF
  char v22[256]; // [rsp+E0h] [rbp-20h] BYREF

  SystemTime = 0;
  memset_0(DateStr, 0, sizeof(DateStr));
  memset_0(TimeStr, 0, sizeof(TimeStr));
  memset_0(v22, 0, sizeof(v22));
  v6 = 0;
  v7 = 0;
  GetLocalTime(&SystemTime);
  GetDateFormatA(0x400u, 1u, &SystemTime, 0, DateStr, 64);
  GetTimeFormatA(0x400u, 0, &SystemTime, 0, TimeStr, 64);
  CurrentProcessId = GetCurrentProcessId();
  if ( a3 )
    StringCchPrintfA(v22, 0x100u, "%s %s PID:%d %s:0x%x (%d)  ", DateStr, TimeStr, CurrentProcessId, a1, a3, a3);
  else
    StringCchPrintfA(v22, 0x100u, "%s %s PID:%d %s  ", DateStr, TimeStr, CurrentProcessId, a1);
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( v22[v10] );
  if ( a2 )
  {
    v11 = *(const WCHAR **)(a2 + 88);
    if ( v11 )
    {
      v12 = WideCharToMultiByte(0xFDE9u, 0x80u, v11, -1, 0, 0, 0, 0);
      v13 = v12;
      if ( v12 > 1 )
      {
        v14 = (CHAR *)operator new(v12);
        v6 = v14;
        if ( v14 )
        {
          if ( WideCharToMultiByte(0xFDE9u, 0x80u, v11, -1, v14, v13, 0, 0) > 1 )
          {
            do
              ++v9;
            while ( v6[v9] );
            v7 = (int)v9;
          }
          else
          {
            operator delete(v6);
            v6 = 0;
          }
        }
      }
    }
  }
  v15 = v7 + (int)v10 + 3LL;
  v16 = (char *)operator new(v15);
  v17 = v16;
  if ( v16 )
  {
    StringCchCopyA(v16, v15, v22);
    if ( v7 )
      StringCchCatA(v17, v15, v6);
    StringCchCatA(v17, v15, "\r\n");
  }
  else
  {
    SetLastError(0x8007000E);
  }
  if ( v6 )
    operator delete(v6);
  return v17;
}

```

## disassembly

```asm
0x18001ec64  mov     [rsp-8+arg_18], rbx
0x18001ec69  push    rbp
0x18001ec6a  push    rsi
0x18001ec6b  push    rdi
0x18001ec6c  push    r12
0x18001ec6e  push    r13
0x18001ec70  push    r14
0x18001ec72  push    r15
0x18001ec74  lea     rbp, [rsp-0F0h]
0x18001ec7c  sub     rsp, 1F0h
0x18001ec83  mov     rax, cs:__security_cookie
0x18001ec8a  xor     rax, rsp
0x18001ec8d  mov     [rbp+120h+var_40], rax
0x18001ec94  mov     edi, r8d
0x18001ec97  mov     r14, rdx
0x18001ec9a  mov     rsi, rcx
0x18001ec9d  xorps   xmm0, xmm0
0x18001eca0  mov     r13d, 40h ; '@'
0x18001eca6  lea     rcx, [rbp+120h+DateStr]; void *
0x18001ecaa  mov     r8d, r13d; Size
0x18001ecad  xor     edx, edx; Val
0x18001ecaf  movups  xmmword ptr [rsp+220h+SystemTime.wYear], xmm0
0x18001ecb4  call    memset_0
0x18001ecb9  mov     r8d, r13d; Size
0x18001ecbc  lea     rcx, [rsp+220h+TimeStr]; void *
0x18001ecc1  xor     edx, edx; Val
0x18001ecc3  call    memset_0
0x18001ecc8  xor     edx, edx; Val
0x18001ecca  lea     rcx, [rbp+120h+var_140]; void *
0x18001ecce  mov     r8d, 100h; Size
0x18001ecd4  call    memset_0
0x18001ecd9  lea     rcx, [rsp+220h+SystemTime]; lpSystemTime
0x18001ecde  xor     ebx, ebx
0x18001ece0  xor     r12d, r12d
0x18001ece3  call    cs:__imp_GetLocalTime
0x18001ece9  lea     rax, [rbp+120h+DateStr]
0x18001eced  mov     [rsp+220h+cchDate], r13d; cchDate
0x18001ecf2  mov     r15d, 400h
0x18001ecf8  mov     [rsp+220h+lpDateStr], rax; lpDateStr
0x18001ecfd  mov     ecx, r15d; Locale
0x18001ed00  lea     r8, [rsp+220h+SystemTime]; lpDate
0x18001ed05  xor     r9d, r9d; lpFormat
0x18001ed08  lea     edx, [rbx+1]; dwFlags
0x18001ed0b  call    cs:__imp_GetDateFormatA
0x18001ed11  lea     rax, [rsp+220h+TimeStr]
0x18001ed16  mov     [rsp+220h+cchDate], r13d; cchTime
0x18001ed1b  xor     r9d, r9d; lpFormat
0x18001ed1e  mov     [rsp+220h+lpDateStr], rax; lpTimeStr
0x18001ed23  lea     r8, [rsp+220h+SystemTime]; lpTime
0x18001ed28  xor     edx, edx; dwFlags
0x18001ed2a  mov     ecx, r15d; Locale
0x18001ed2d  call    cs:__imp_GetTimeFormatA
0x18001ed33  xor     r13d, r13d
0x18001ed36  call    cs:__imp_GetCurrentProcessId
0x18001ed3c  lea     r9, [rbp+120h+DateStr]
0x18001ed40  mov     edx, 100h; unsigned __int64
0x18001ed45  lea     rcx, [rbp+120h+var_140]; char *
0x18001ed49  test    edi, edi
0x18001ed4b  jnz     short loc_18001ED6E
0x18001ed4d  mov     [rsp+220h+lpDefaultChar], rsi
0x18001ed52  lea     r8, aSSPidDS; "%s %s PID:%d %s  "
0x18001ed59  mov     [rsp+220h+cchDate], eax
0x18001ed5d  lea     rax, [rsp+220h+TimeStr]
0x18001ed62  mov     [rsp+220h+lpDateStr], rax
0x18001ed67  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001ed6c  jmp     short loc_18001ED95
0x18001ed6e  mov     [rsp+220h+var_1E0], edi
0x18001ed72  lea     r8, aSSPidDS0xXD; "%s %s PID:%d %s:0x%x (%d)  "
0x18001ed79  mov     dword ptr [rsp+220h+lpUsedDefaultChar], edi
0x18001ed7d  mov     [rsp+220h+lpDefaultChar], rsi
0x18001ed82  mov     [rsp+220h+cchDate], eax
0x18001ed86  lea     rax, [rsp+220h+TimeStr]
0x18001ed8b  mov     [rsp+220h+lpDateStr], rax
0x18001ed90  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001ed95  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001ed99  lea     rax, [rbp+120h+var_140]
0x18001ed9d  mov     rsi, rdi
0x18001eda0  inc     rsi
0x18001eda3  cmp     [rax+rsi], r13b
0x18001eda7  jnz     short loc_18001EDA0
0x18001eda9  test    r14, r14
0x18001edac  jz      loc_18001EE4A
0x18001edb2  mov     r14, [r14+58h]
0x18001edb6  test    r14, r14
0x18001edb9  jz      loc_18001EE4A
0x18001edbf  mov     [rsp+220h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18001edc4  mov     r9d, edi; cchWideChar
0x18001edc7  mov     [rsp+220h+lpDefaultChar], r13; lpDefaultChar
0x18001edcc  mov     r8, r14; lpWideCharStr
0x18001edcf  mov     [rsp+220h+cchDate], r13d; cbMultiByte
0x18001edd4  mov     edx, 80h; dwFlags
0x18001edd9  mov     ecx, 0FDE9h; CodePage
0x18001edde  mov     [rsp+220h+lpDateStr], r13; lpMultiByteStr
0x18001ede3  call    cs:__imp_WideCharToMultiByte
0x18001ede9  movsxd  r15, eax
0x18001edec  cmp     r15d, 1
0x18001edf0  jle     short loc_18001EE4A
0x18001edf2  mov     rcx, r15; uBytes
0x18001edf5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001edfa  mov     rbx, rax
0x18001edfd  test    rax, rax
0x18001ee00  jz      short loc_18001EE4A
0x18001ee02  mov     [rsp+220h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18001ee07  mov     r9d, edi; cchWideChar
0x18001ee0a  mov     [rsp+220h+lpDefaultChar], r13; lpDefaultChar
0x18001ee0f  mov     r8, r14; lpWideCharStr
0x18001ee12  mov     [rsp+220h+cchDate], r15d; cbMultiByte
0x18001ee17  mov     edx, 80h; dwFlags
0x18001ee1c  mov     ecx, 0FDE9h; CodePage
0x18001ee21  mov     [rsp+220h+lpDateStr], rax; lpMultiByteStr
0x18001ee26  call    cs:__imp_WideCharToMultiByte
0x18001ee2c  cmp     eax, 1
0x18001ee2f  jg      short loc_18001EE3E
0x18001ee31  mov     rcx, rbx; hMem
0x18001ee34  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ee39  mov     rbx, r13
0x18001ee3c  jmp     short loc_18001EE4A
0x18001ee3e  inc     rdi
0x18001ee41  cmp     [rbx+rdi], r13b
0x18001ee45  jnz     short loc_18001EE3E
0x18001ee47  movsxd  r12, edi
0x18001ee4a  movsxd  rsi, esi
0x18001ee4d  add     rsi, 3
0x18001ee51  add     rsi, r12
0x18001ee54  mov     rcx, rsi; uBytes
0x18001ee57  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ee5c  mov     rdi, rax
0x18001ee5f  test    rax, rax
0x18001ee62  jnz     short loc_18001EE71
0x18001ee64  mov     ecx, 8007000Eh; dwErrCode
0x18001ee69  call    cs:__imp_SetLastError
0x18001ee6f  jmp     short loc_18001EEA5
0x18001ee71  lea     r8, [rbp+120h+var_140]; char *
0x18001ee75  mov     rdx, rsi; unsigned __int64
0x18001ee78  mov     rcx, rdi; char *
0x18001ee7b  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18001ee80  test    r12, r12
0x18001ee83  jz      short loc_18001EE93
0x18001ee85  mov     r8, rbx; char *
0x18001ee88  mov     rdx, rsi; unsigned __int64
0x18001ee8b  mov     rcx, rdi; char *
0x18001ee8e  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18001ee93  lea     r8, asc_18002A824; "\r\n"
0x18001ee9a  mov     rdx, rsi; unsigned __int64
0x18001ee9d  mov     rcx, rdi; char *
0x18001eea0  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18001eea5  test    rbx, rbx
0x18001eea8  jz      short loc_18001EEB2
0x18001eeaa  mov     rcx, rbx; hMem
0x18001eead  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001eeb2  mov     rax, rdi
0x18001eeb5  mov     rcx, [rbp+120h+var_40]
0x18001eebc  xor     rcx, rsp; StackCookie
0x18001eebf  call    __security_check_cookie
0x18001eec4  mov     rbx, [rsp+220h+arg_18]
0x18001eecc  add     rsp, 1F0h
0x18001eed3  pop     r15
0x18001eed5  pop     r14
0x18001eed7  pop     r13
0x18001eed9  pop     r12
0x18001eedb  pop     rdi
0x18001eedc  pop     rsi
0x18001eedd  pop     rbp
0x18001eede  retn
```
