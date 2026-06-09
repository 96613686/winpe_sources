# LoadInterceptorFunctionTable

- ea: `0x180059b9c`
- end: `0x180059d80`
- name: `LoadInterceptorFunctionTable`
- size: `484`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName, FARPROC *, unsigned int *, HMODULE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800598bc`

## callees

- `0x180059b9c`
- `0x180080784`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059c2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059c2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059c42`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059c56`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059c69`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059c7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059c91`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059ca5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059c42`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059c56`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059c69`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059c7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059c91`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059ca5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180059d6b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180059d6b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180059c1d`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180059c1d`

## pseudocode

```c
__int64 __fastcall LoadInterceptorFunctionTable(LPCWSTR lpLibFileName, FARPROC *a2, unsigned int *a3, HMODULE *a4)
{
  HMODULE v8; // rbx
  unsigned int v9; // esi
  __int64 v10; // rcx
  FARPROC *v11; // rax
  DWORD LastError; // edi
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax

  v8 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_Sqqq(
      (_DWORD)lpLibFileName,
      (_DWORD)a2,
      (_DWORD)a3,
      (_DWORD)lpLibFileName,
      (__int64)a2,
      (__int64)a3,
      (__int64)a4);
  v9 = 1;
  if ( a2 )
  {
    v10 = 48;
    v11 = a2;
    do
    {
      *(_BYTE *)v11 = 0;
      v11 = (FARPROC *)((char *)v11 + 1);
      --v10;
    }
    while ( v10 );
  }
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( !a2 || !a4 || !a3 )
  {
    LastError = 87;
    goto LABEL_32;
  }
  LibraryW = LoadLibraryW(lpLibFileName);
  v8 = LibraryW;
  if ( !LibraryW )
  {
    LastError = GetLastError();
    goto LABEL_32;
  }
  a2[2] = GetProcAddress(LibraryW, "DnsInterceptionOnQueryEvent");
  *a2 = GetProcAddress(v8, "DnsInterceptionInit");
  a2[1] = GetProcAddress(v8, "DnsInterceptionShutdown");
  a2[3] = GetProcAddress(v8, "DnsInterceptionFree");
  a2[5] = GetProcAddress(v8, "DnsInterceptionOnStartEvent");
  ProcAddress = GetProcAddress(v8, "DnsInterceptionInitEx");
  a2[4] = ProcAddress;
  if ( ProcAddress )
  {
    if ( !a2[3] || !a2[1] || !a2[2] || !a2[5] )
      goto LABEL_30;
    v9 = 0;
LABEL_27:
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 12, WPP_148b470cd89931158ac1095a15ebe1c1_Traceguids, v9);
    *a3 = v9;
    *a4 = v8;
    v8 = 0;
    LastError = 0;
    goto LABEL_32;
  }
  if ( a2[3] && a2[1] && a2[2] && *a2 )
    goto LABEL_27;
LABEL_30:
  LastError = 87;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
    goto LABEL_34;
  WPP_SF_d(1035, 11, WPP_148b470cd89931158ac1095a15ebe1c1_Traceguids, 87);
LABEL_32:
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 13, WPP_148b470cd89931158ac1095a15ebe1c1_Traceguids, LastError);
LABEL_34:
  if ( v8 )
    FreeLibrary(v8);
  return LastError;
}

```

## disassembly

```asm
0x180059b9c  push    rbx
0x180059b9e  push    rbp
0x180059b9f  push    rsi
0x180059ba0  push    rdi
0x180059ba1  push    r14
0x180059ba3  push    r15
0x180059ba5  sub     rsp, 48h
0x180059ba9  mov     r15, r9
0x180059bac  mov     r14, r8
0x180059baf  mov     rdi, rdx
0x180059bb2  mov     rbp, rcx
0x180059bb5  xor     ebx, ebx
0x180059bb7  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180059bbe  jz      short loc_180059BD7
0x180059bc0  mov     [rsp+78h+var_48], r9
0x180059bc5  mov     r9, rcx
0x180059bc8  mov     [rsp+78h+var_50], r8
0x180059bcd  mov     [rsp+78h+var_58], rdx
0x180059bd2  call    WPP_SF_Sqqq
0x180059bd7  mov     esi, 1
0x180059bdc  test    rdi, rdi
0x180059bdf  jz      short loc_180059BF1
0x180059be1  lea     ecx, [rsi+2Fh]
0x180059be4  mov     rax, rdi
0x180059be7  mov     [rax], bl
0x180059be9  add     rax, rsi
0x180059bec  sub     rcx, rsi
0x180059bef  jnz     short loc_180059BE7
0x180059bf1  test    r14, r14
0x180059bf4  jz      short loc_180059BF9
0x180059bf6  mov     [r14], ebx
0x180059bf9  test    r15, r15
0x180059bfc  jz      short loc_180059C01
0x180059bfe  mov     [r15], rbx
0x180059c01  test    rdi, rdi
0x180059c04  jnz     short loc_180059C10
0x180059c06  mov     edi, 57h ; 'W'
0x180059c0b  jmp     loc_180059D41
0x180059c10  test    r15, r15
0x180059c13  jz      short loc_180059C06
0x180059c15  test    r14, r14
0x180059c18  jz      short loc_180059C06
0x180059c1a  mov     rcx, rbp; lpLibFileName
0x180059c1d  call    cs:__imp_LoadLibraryW
0x180059c23  mov     rbx, rax
0x180059c26  test    rax, rax
0x180059c29  jnz     short loc_180059C38
0x180059c2b  call    cs:__imp_GetLastError
0x180059c31  mov     edi, eax
0x180059c33  jmp     loc_180059D41
0x180059c38  lea     rdx, aDnsinterceptio_0; "DnsInterceptionOnQueryEvent"
0x180059c3f  mov     rcx, rbx; hModule
0x180059c42  call    cs:__imp_GetProcAddress
0x180059c48  lea     rdx, aDnsinterceptio_1; "DnsInterceptionInit"
0x180059c4f  mov     rcx, rbx; hModule
0x180059c52  mov     [rdi+10h], rax
0x180059c56  call    cs:__imp_GetProcAddress
0x180059c5c  lea     rdx, aDnsinterceptio; "DnsInterceptionShutdown"
0x180059c63  mov     rcx, rbx; hModule
0x180059c66  mov     [rdi], rax
0x180059c69  call    cs:__imp_GetProcAddress
0x180059c6f  lea     rdx, aDnsinterceptio_3; "DnsInterceptionFree"
0x180059c76  mov     rcx, rbx; hModule
0x180059c79  mov     [rdi+8], rax
0x180059c7d  call    cs:__imp_GetProcAddress
0x180059c83  lea     rdx, aDnsinterceptio_2; "DnsInterceptionOnStartEvent"
0x180059c8a  mov     rcx, rbx; hModule
0x180059c8d  mov     [rdi+18h], rax
0x180059c91  call    cs:__imp_GetProcAddress
0x180059c97  lea     rdx, aDnsinterceptio_4; "DnsInterceptionInitEx"
0x180059c9e  mov     rcx, rbx; hModule
0x180059ca1  mov     [rdi+28h], rax
0x180059ca5  call    cs:__imp_GetProcAddress
0x180059cab  mov     [rdi+20h], rax
0x180059caf  test    rax, rax
0x180059cb2  jnz     short loc_180059CD0
0x180059cb4  cmp     [rdi+18h], rax
0x180059cb8  jz      short loc_180059CCB
0x180059cba  cmp     [rdi+8], rax
0x180059cbe  jz      short loc_180059CCB
0x180059cc0  cmp     [rdi+10h], rax
0x180059cc4  jz      short loc_180059CCB
0x180059cc6  cmp     [rdi], rax
0x180059cc9  jnz     short loc_180059CEE
0x180059ccb  test    rax, rax
0x180059cce  jz      short loc_180059D1C
0x180059cd0  cmp     qword ptr [rdi+18h], 0
0x180059cd5  jz      short loc_180059D1C
0x180059cd7  cmp     qword ptr [rdi+8], 0
0x180059cdc  jz      short loc_180059D1C
0x180059cde  cmp     qword ptr [rdi+10h], 0
0x180059ce3  jz      short loc_180059D1C
0x180059ce5  cmp     qword ptr [rdi+28h], 0
0x180059cea  jz      short loc_180059D1C
0x180059cec  xor     esi, esi
0x180059cee  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180059cf5  jz      short loc_180059D10
0x180059cf7  mov     edx, 0Ch
0x180059cfc  lea     r8, WPP_148b470cd89931158ac1095a15ebe1c1_Traceguids
0x180059d03  mov     ecx, 40Bh
0x180059d08  mov     r9d, esi
0x180059d0b  call    WPP_SF_d
0x180059d10  mov     [r14], esi
0x180059d13  mov     [r15], rbx
0x180059d16  xor     ebx, ebx
0x180059d18  xor     edi, edi
0x180059d1a  jmp     short loc_180059D41
0x180059d1c  mov     edi, 57h ; 'W'
0x180059d21  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180059d28  jz      short loc_180059D63
0x180059d2a  lea     edx, [rdi-4Ch]
0x180059d2d  mov     ecx, 40Bh
0x180059d32  mov     r9d, edi
0x180059d35  lea     r8, WPP_148b470cd89931158ac1095a15ebe1c1_Traceguids
0x180059d3c  call    WPP_SF_d
0x180059d41  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180059d48  jz      short loc_180059D63
0x180059d4a  mov     edx, 0Dh
0x180059d4f  lea     r8, WPP_148b470cd89931158ac1095a15ebe1c1_Traceguids
0x180059d56  mov     ecx, 40Bh
0x180059d5b  mov     r9d, edi
0x180059d5e  call    WPP_SF_d
0x180059d63  test    rbx, rbx
0x180059d66  jz      short loc_180059D71
0x180059d68  mov     rcx, rbx; hLibModule
0x180059d6b  call    cs:__imp_FreeLibrary
0x180059d71  mov     eax, edi
0x180059d73  add     rsp, 48h
0x180059d77  pop     r15
0x180059d79  pop     r14
0x180059d7b  pop     rdi
0x180059d7c  pop     rsi
0x180059d7d  pop     rbp
0x180059d7e  pop     rbx
0x180059d7f  retn
```
