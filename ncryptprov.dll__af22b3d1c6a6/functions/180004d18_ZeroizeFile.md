# ZeroizeFile

- ea: `0x180004d18`
- end: `0x180004f85`
- name: `ZeroizeFile`
- size: `621`
- prototype: `__int64 __fastcall(const WCHAR *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004850`

## callees

- `0x180004d18`
- `0x1800086d0`
- `0x18000af80`
- `0x18000b250`
- `0x180038970`
- `0x180062280`
- `0x180062310`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004dd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004dd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f5d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004d63`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004d63`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180004dbc`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180004dbc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180004f05`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180004f05`

## string_xrefs

- `0x180004d97`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x180004de2`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x180004ebc`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x180004f27`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`

## pseudocode

```c
__int64 __fastcall ZeroizeFile(const WCHAR *a1)
{
  HANDLE FileW; // rax
  void *v2; // r15
  __int64 LastError; // rbx
  DWORD FileSize; // eax
  __int64 v5; // rdx
  unsigned __int64 v6; // r14
  DWORD *p_NumberOfBytesWritten; // rdi
  size_t v8; // rsi
  unsigned __int64 v9; // rcx
  __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  void *v12; // rsp
  void *v13; // rsp
  DWORD *v14; // rax
  __int64 v16; // [rsp+0h] [rbp-40h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp+0h] BYREF
  __int64 v18; // [rsp+48h] [rbp+8h] BYREF

  NumberOfBytesWritten = 0;
  FileW = CreateFileW(a1, 0x40000000u, 0, 0, 3u, 4u, 0);
  v2 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LODWORD(LastError) = GetLastError();
    if ( (unsigned int)(LastError - 2) <= 1 )
    {
      LODWORD(LastError) = -2146893802;
      DebugTraceError(2148073494LL, "dwReturn", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c", 924);
    }
  }
  else
  {
    FileSize = GetFileSize(FileW, 0);
    v6 = FileSize;
    if ( FileSize == -1 )
    {
      LODWORD(LastError) = GetLastError();
      DebugTraceError(
        (unsigned int)LastError,
        "dwReturn",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
        937);
    }
    else
    {
      p_NumberOfBytesWritten = 0;
      LODWORD(LastError) = 8;
      if ( !FileSize )
        goto LABEL_14;
      v8 = FileSize;
      if ( FileSize > (unsigned __int64)g_ulMaxStackAllocSize )
        goto LABEL_14;
      v9 = FileSize + g_ulAdditionalProbeSize + 8;
      if ( v9 < FileSize || !(unsigned int)VerifyStackAvailable(v9, v5) )
        goto LABEL_14;
      v10 = v6 + 23;
      if ( v6 + 23 <= v6 + 8 )
        v10 = 0xFFFFFFFFFFFFFF0LL;
      v11 = v10 & 0xFFFFFFFFFFFFFFF0uLL;
      v12 = alloca(v11);
      v13 = alloca(v11);
      p_NumberOfBytesWritten = &NumberOfBytesWritten;
      if ( &v16 == (__int64 *)-64LL
        || (NumberOfBytesWritten = 1801679955, (p_NumberOfBytesWritten = (DWORD *)&v18) == 0) )
      {
LABEL_14:
        v8 = v6;
        if ( v6 + 8 >= v6 )
        {
          v14 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
          p_NumberOfBytesWritten = v14;
          if ( v14 )
          {
            *v14 = 1885431112;
            p_NumberOfBytesWritten = v14 + 2;
          }
        }
      }
      if ( p_NumberOfBytesWritten )
      {
        memset_0(p_NumberOfBytesWritten, 0, v8);
        if ( WriteFile(v2, p_NumberOfBytesWritten, v6, &NumberOfBytesWritten, 0) )
        {
          LODWORD(LastError) = 0;
        }
        else
        {
          LastError = GetLastError();
          DebugTraceError(LastError, "dwReturn", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c", 954);
        }
        if ( *(p_NumberOfBytesWritten - 2) == 1885431112 )
          ((void (*)(void))g_pfnFree)();
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v5,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
          (unsigned int)"dwReturn",
          8,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
          178);
      }
    }
    CloseHandle(v2);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180004d18  push    rbp
0x180004d1a  push    rbx
0x180004d1b  push    rsi
0x180004d1c  push    rdi
0x180004d1d  push    r14
0x180004d1f  push    r15
0x180004d21  sub     rsp, 68h
0x180004d25  lea     rbp, [rsp+40h]
0x180004d2a  mov     rax, cs:__security_cookie
0x180004d31  xor     rax, rbp
0x180004d34  mov     [rbp+50h+var_40], rax
0x180004d38  mov     [rsp+90h+hTemplateFile], 0; hTemplateFile
0x180004d41  xor     r9d, r9d; lpSecurityAttributes
0x180004d44  mov     [rsp+90h+dwFlagsAndAttributes], 4; dwFlagsAndAttributes
0x180004d4c  xor     r8d, r8d; dwShareMode
0x180004d4f  mov     edx, 40000000h; dwDesiredAccess
0x180004d54  mov     [rsp+90h+dwCreationDisposition], 3; dwCreationDisposition
0x180004d5c  mov     [rbp+50h+NumberOfBytesWritten], 0
0x180004d63  call    cs:__imp_CreateFileW
0x180004d6a  nop     dword ptr [rax+rax+00h]
0x180004d6f  mov     r15, rax
0x180004d72  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004d76  jnz     short loc_180004DB7
0x180004d78  call    cs:__imp_GetLastError
0x180004d7f  nop     dword ptr [rax+rax+00h]
0x180004d84  mov     ebx, eax
0x180004d86  add     eax, 0FFFFFFFEh
0x180004d89  cmp     eax, 1
0x180004d8c  ja      loc_180004F69
0x180004d92  mov     ebx, 80090016h
0x180004d97  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004d9e  mov     ecx, ebx
0x180004da0  lea     rdx, aDwreturn; "dwReturn"
0x180004da7  mov     r9d, 39Ch
0x180004dad  call    DebugTraceError
0x180004db2  jmp     loc_180004F69
0x180004db7  xor     edx, edx; lpFileSizeHigh
0x180004db9  mov     rcx, r15; hFile
0x180004dbc  call    cs:__imp_GetFileSize
0x180004dc3  nop     dword ptr [rax+rax+00h]
0x180004dc8  mov     r14d, eax
0x180004dcb  cmp     eax, 0FFFFFFFFh
0x180004dce  jnz     short loc_180004DFE
0x180004dd0  call    cs:__imp_GetLastError
0x180004dd7  nop     dword ptr [rax+rax+00h]
0x180004ddc  mov     r9d, 3A9h
0x180004de2  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004de9  mov     ecx, eax
0x180004deb  lea     rdx, aDwreturn; "dwReturn"
0x180004df2  mov     ebx, eax
0x180004df4  call    DebugTraceError
0x180004df9  jmp     loc_180004F5A
0x180004dfe  xor     edi, edi
0x180004e00  lea     ebx, [rdi+8]
0x180004e03  test    eax, eax
0x180004e05  jz      short loc_180004E69
0x180004e07  cmp     r14, cs:g_ulMaxStackAllocSize
0x180004e0e  mov     rsi, r14
0x180004e11  ja      short loc_180004E69
0x180004e13  mov     rcx, cs:g_ulAdditionalProbeSize
0x180004e1a  add     rcx, rbx
0x180004e1d  add     rcx, r14
0x180004e20  cmp     rcx, r14
0x180004e23  jb      short loc_180004E69
0x180004e25  call    VerifyStackAvailable
0x180004e2a  test    eax, eax
0x180004e2c  jz      short loc_180004E69
0x180004e2e  lea     rax, [r14+8]
0x180004e32  lea     rcx, [rax+0Fh]
0x180004e36  cmp     rcx, rax
0x180004e39  ja      short loc_180004E45
0x180004e3b  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180004e45  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180004e49  mov     rax, rcx
0x180004e4c  call    _alloca_probe
0x180004e51  sub     rsp, rcx
0x180004e54  lea     rdi, [rsp+90h+NumberOfBytesWritten]
0x180004e59  test    rdi, rdi
0x180004e5c  jz      short loc_180004E69
0x180004e5e  mov     dword ptr [rdi], 6B637453h
0x180004e64  add     rdi, rbx
0x180004e67  jnz     short loc_180004E92
0x180004e69  lea     rcx, [r14+8]
0x180004e6d  mov     rsi, r14
0x180004e70  cmp     rcx, r14
0x180004e73  jb      short loc_180004E92
0x180004e75  mov     rax, cs:g_pfnAllocate
0x180004e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e81  mov     rdi, rax
0x180004e84  test    rax, rax
0x180004e87  jz      short loc_180004E92
0x180004e89  mov     dword ptr [rax], 70616548h
0x180004e8f  add     rdi, rbx
0x180004e92  test    rdi, rdi
0x180004e95  jnz     short loc_180004EE2
0x180004e97  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e9e  lea     rax, WPP_GLOBAL_Control
0x180004ea5  cmp     rcx, rax
0x180004ea8  jz      loc_180004F5A
0x180004eae  test    byte ptr [rcx+1Ch], 1
0x180004eb2  jz      loc_180004F5A
0x180004eb8  mov     rcx, [rcx+10h]
0x180004ebc  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004ec3  mov     dword ptr [rsp+90h+hTemplateFile], 3B2h
0x180004ecb  lea     r9, aDwreturn; "dwReturn"
0x180004ed2  mov     qword ptr [rsp+90h+dwFlagsAndAttributes], r8
0x180004ed7  mov     [rsp+90h+dwCreationDisposition], ebx
0x180004edb  call    WPP_SF_sDsd
0x180004ee0  jmp     short loc_180004F5A
0x180004ee2  mov     r8, rsi; Size
0x180004ee5  xor     edx, edx; Val
0x180004ee7  mov     rcx, rdi; void *
0x180004eea  call    memset_0
0x180004eef  lea     r9, [rbp+50h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180004ef3  mov     qword ptr [rsp+90h+dwCreationDisposition], 0; lpOverlapped
0x180004efc  mov     r8d, r14d; nNumberOfBytesToWrite
0x180004eff  mov     rdx, rdi; lpBuffer
0x180004f02  mov     rcx, r15; hFile
0x180004f05  call    cs:__imp_WriteFile
0x180004f0c  nop     dword ptr [rax+rax+00h]
0x180004f11  test    eax, eax
0x180004f13  jnz     short loc_180004F40
0x180004f15  call    cs:__imp_GetLastError
0x180004f1c  nop     dword ptr [rax+rax+00h]
0x180004f21  mov     r9d, 3BAh
0x180004f27  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004f2e  mov     ecx, eax
0x180004f30  lea     rdx, aDwreturn; "dwReturn"
0x180004f37  mov     ebx, eax
0x180004f39  call    DebugTraceError
0x180004f3e  jmp     short loc_180004F42
0x180004f40  xor     ebx, ebx
0x180004f42  lea     rcx, [rdi-8]
0x180004f46  cmp     dword ptr [rcx], 70616548h
0x180004f4c  jnz     short loc_180004F5A
0x180004f4e  mov     rax, cs:g_pfnFree
0x180004f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f5a  mov     rcx, r15; hObject
0x180004f5d  call    cs:__imp_CloseHandle
0x180004f64  nop     dword ptr [rax+rax+00h]
0x180004f69  mov     eax, ebx
0x180004f6b  mov     rcx, [rbp+50h+var_40]
0x180004f6f  xor     rcx, rbp; StackCookie
0x180004f72  call    __security_check_cookie
0x180004f77  lea     rsp, [rbp+28h]
0x180004f7b  pop     r15
0x180004f7d  pop     r14
0x180004f7f  pop     rdi
0x180004f80  pop     rsi
0x180004f81  pop     rbx
0x180004f82  pop     rbp
0x180004f83  retn
```
