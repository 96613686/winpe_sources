# KspFindFirstKeyFile

- ea: `0x180052b74`
- end: `0x180052f7c`
- name: `KspFindFirstKeyFile`
- size: `1032`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180053500`

## callees

- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x180038970`
- `0x1800398b0`
- `0x180046dc0`
- `0x18005283c`
- `0x180052b74`
- `0x180053190`
- `0x1800532a4`
- `0x180062310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052ca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052ca9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180052c90`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180052c90`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180052f3d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180052f3d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180052d62`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180052d62`

## string_xrefs

- `0x180052c19`: `onecore\ds\security\cryptoapi\ncrypt\storage\enum.c`
- `0x180052c4c`: `onecore\ds\security\cryptoapi\ncrypt\storage\enum.c`
- `0x180052cbb`: `onecore\ds\security\cryptoapi\ncrypt\storage\enum.c`
- `0x180052ce7`: `onecore\ds\security\cryptoapi\ncrypt\storage\enum.c`
- `0x180052d46`: `onecore\ds\security\cryptoapi\ncrypt\storage\enum.c`
- `0x180052d82`: `onecore\ds\security\cryptoapi\ncrypt\storage\enum.c`
- `0x180052df0`: `onecore\ds\security\cryptoapi\ncrypt\storage\enum.c`
- `0x180052e5f`: `onecore\ds\security\cryptoapi\ncrypt\storage\enum.c`

## pseudocode

```c
__int64 __fastcall KspFindFirstKeyFile(__int64 a1, unsigned int a2, __int64 *a3, _QWORD *a4)
{
  const void *v6; // r15
  __int64 v7; // rsi
  STRSAFE_LPCWSTR v8; // r12
  __int64 FirstFile; // r13
  unsigned int ProfilePath; // eax
  _WORD *v11; // r14
  unsigned int v12; // ebx
  unsigned int KeySearchPath; // eax
  DWORD LastError; // ebx
  unsigned int v15; // esi
  int v16; // edx
  unsigned int v17; // eax
  __int64 v18; // rax
  unsigned int v19; // eax
  int v20; // edi
  unsigned int v21; // eax
  __int64 v22; // rax
  size_t v23; // r12
  __int64 v24; // rax
  __int64 v25; // rdi
  void *v26; // rdx
  __int64 v27; // rbx
  void *v28; // rbx
  __int64 *v29; // rax
  int v31; // [rsp+38h] [rbp-C8h]
  unsigned int lpFileName; // [rsp+40h] [rbp-C0h]
  STRSAFE_LPCWSTR pszSrc; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v34; // [rsp+50h] [rbp-B0h]
  void *Src; // [rsp+58h] [rbp-A8h]
  __int64 v36; // [rsp+60h] [rbp-A0h] BYREF
  const void *v37; // [rsp+68h] [rbp-98h] BYREF
  __int64 *v38; // [rsp+70h] [rbp-90h]
  _QWORD *v39; // [rsp+78h] [rbp-88h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF

  v38 = a3;
  v34 = a2;
  pszSrc = 0;
  v37 = 0;
  v36 = 0;
  v6 = 0;
  v39 = a4;
  v7 = 0;
  v8 = 0;
  FirstFile = -1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  ProfilePath = KspGetProfilePath(&pszSrc, *(_WORD **)(a1 + 40), a2, *(_DWORD *)(a1 + 48), 0);
  v11 = pszSrc;
  v12 = ProfilePath;
  Src = (void *)pszSrc;
  if ( ProfilePath )
  {
    DebugTraceError(ProfilePath, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\enum.c", 1344);
  }
  else
  {
    KeySearchPath = GetKeySearchPath(pszSrc);
    v12 = KeySearchPath;
    if ( KeySearchPath )
    {
      DebugTraceError(KeySearchPath, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\enum.c", 1357);
      v8 = 0;
    }
    else
    {
      v8 = 0;
      pszSrc = 0;
      v31 = 0;
      FirstFile = (__int64)FindFirstFileExW(0, FindExInfoStandard, &FindFileData, FindExSearchNameMatch, 0, 0);
      if ( FirstFile == -1 )
      {
        lpFileName = 0;
        LastError = GetLastError();
        DebugTraceError(LastError, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\enum.c", 1376);
        if ( LastError - 2 <= 1 )
          DebugTraceError(2148073514LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\enum.c", 1382);
      }
      else
      {
        v15 = v34;
        do
        {
          v16 = 0;
          if ( !v15 )
            v16 = *(_DWORD *)(a1 + 48);
          if ( IsValidKeyFileName((__int64)&FindFileData, v16, 0) )
          {
            v17 = ReadKeyNameFromFile(v11, FindFileData.cFileName, v15, &v36);
            if ( !v17 )
            {
              v31 = 1;
              goto LABEL_18;
            }
            DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\enum.c", 1408);
          }
        }
        while ( FindNextFileW((HANDLE)FirstFile, &FindFileData) );
        DebugTraceError(2148073514LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\enum.c", 1424);
LABEL_18:
        v18 = -1;
        do
          ++v18;
        while ( v11[v18] );
        v7 = v36;
        lpFileName = 2 * v18 + 2;
      }
      v19 = 0;
      if ( *(_DWORD *)(a1 + 48) && *(_DWORD *)(a1 + 52) && !*(_QWORD *)(a1 + 40) )
      {
        v20 = 1;
        v21 = KspGetProfilePath(&v37, 0, 0, 1, 1);
        if ( v21 )
        {
          DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\enum.c", 1452);
          v19 = 0;
        }
        else
        {
          v6 = v37;
          v22 = -1;
          do
            ++v22;
          while ( *((_WORD *)v37 + v22) );
          v19 = 2 * v22 + 2;
        }
      }
      else
      {
        v20 = 0;
      }
      if ( v31 || v20 )
      {
        v23 = v19;
        v24 = SafeAllocaAllocateFromHeap(v19 + lpFileName + 64LL);
        v25 = v24;
        if ( v24 )
        {
          v26 = Src;
          *(_DWORD *)v24 = 0;
          *(_DWORD *)(v24 + 24) = 0;
          v27 = v24 + 64;
          *(_QWORD *)(v24 + 8) = FirstFile;
          *(_QWORD *)(v24 + 52) = 0;
          FirstFile = -1;
          *(_QWORD *)(v24 + 32) = -1;
          *(_DWORD *)(v24 + 48) = v34;
          memcpy_0((void *)(v24 + 64), v26, lpFileName);
          *(_QWORD *)(v25 + 16) = v27;
          if ( v6 )
          {
            v28 = (void *)(v25 + lpFileName + 64LL);
            memcpy_0(v28, v6, v23);
          }
          else
          {
            v28 = 0;
          }
          v29 = v38;
          *(_QWORD *)(v25 + 40) = v28;
          v12 = 0;
          *v29 = v25;
          if ( v31 )
          {
            *v39 = v7;
            v7 = 0;
          }
          else
          {
            v12 = -2146893782;
          }
        }
        else
        {
          v12 = -2146893810;
          DebugTraceError(2148073486LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\enum.c", 1477);
        }
        v11 = Src;
        v8 = pszSrc;
      }
      else
      {
        v12 = -2146893782;
      }
    }
  }
  if ( v11 )
    MSCryptFree(v11);
  if ( v6 )
    MSCryptFree(v6);
  if ( v7 )
    MSCryptFree(v7);
  if ( FirstFile != -1 )
    FindClose((HANDLE)FirstFile);
  if ( v8 )
    MSCryptFree(v8);
  return v12;
}

```

## disassembly

```asm
0x180052b74  push    rbp
0x180052b76  push    rbx
0x180052b77  push    rsi
0x180052b78  push    rdi
0x180052b79  push    r12
0x180052b7b  push    r13
0x180052b7d  push    r14
0x180052b7f  push    r15
0x180052b81  lea     rbp, [rsp-1E8h]
0x180052b89  sub     rsp, 2E8h
0x180052b90  mov     rax, cs:__security_cookie
0x180052b97  xor     rax, rsp
0x180052b9a  mov     [rbp+220h+var_50], rax
0x180052ba1  xor     r14d, r14d
0x180052ba4  mov     [rsp+320h+var_2B0], r8
0x180052ba9  mov     ebx, edx
0x180052bab  mov     [rsp+320h+var_2D0], edx
0x180052baf  mov     rdi, rcx
0x180052bb2  mov     [rsp+320h+pszSrc], r14
0x180052bb7  xor     edx, edx; Val
0x180052bb9  mov     [rsp+320h+var_2B8], r14
0x180052bbe  mov     r8d, 250h; Size
0x180052bc4  mov     [rsp+320h+var_2C0], r14
0x180052bc9  lea     rcx, [rbp+220h+FindFileData]; void *
0x180052bcd  mov     [rsp+320h+lpFileName], r14
0x180052bd2  mov     r15d, r14d
0x180052bd5  mov     [rsp+320h+var_2A8], r9
0x180052bda  mov     esi, r14d
0x180052bdd  mov     r12d, r14d
0x180052be0  or      r13, 0FFFFFFFFFFFFFFFFh
0x180052be4  call    memset_0
0x180052be9  mov     r9d, [rdi+30h]
0x180052bed  lea     rcx, [rsp+320h+pszSrc]
0x180052bf2  mov     rdx, [rdi+28h]
0x180052bf6  mov     r8d, ebx
0x180052bf9  mov     dword ptr [rsp+320h+lpSearchFilter], r14d
0x180052bfe  call    KspGetProfilePath
0x180052c03  mov     r14, [rsp+320h+pszSrc]
0x180052c08  mov     ebx, eax
0x180052c0a  mov     [rsp+320h+Src], r14
0x180052c0f  test    eax, eax
0x180052c11  jz      short loc_180052C33
0x180052c13  mov     r9d, 540h
0x180052c19  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180052c20  lea     rdx, aStatus; "Status"
0x180052c27  mov     ecx, eax
0x180052c29  call    DebugTraceError
0x180052c2e  jmp     loc_180052F0D
0x180052c33  lea     rdx, [rsp+320h+lpFileName]
0x180052c38  mov     rcx, r14; pszSrc
0x180052c3b  call    GetKeySearchPath
0x180052c40  mov     ebx, eax
0x180052c42  test    eax, eax
0x180052c44  jz      short loc_180052C6B
0x180052c46  mov     r9d, 54Dh
0x180052c4c  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180052c53  lea     rdx, aStatus; "Status"
0x180052c5a  mov     ecx, eax
0x180052c5c  call    DebugTraceError
0x180052c61  mov     r12, [rsp+320h+lpFileName]
0x180052c66  jmp     loc_180052F0D
0x180052c6b  mov     r12, [rsp+320h+lpFileName]
0x180052c70  lea     r8, [rbp+220h+FindFileData]; lpFindFileData
0x180052c74  xor     ebx, ebx
0x180052c76  mov     [rsp+320h+pszSrc], r12
0x180052c7b  mov     [rsp+320h+dwAdditionalFlags], ebx; dwAdditionalFlags
0x180052c7f  mov     rcx, r12; lpFileName
0x180052c82  xor     r9d, r9d; fSearchOp
0x180052c85  mov     [rsp+320h+lpSearchFilter], rbx; lpSearchFilter
0x180052c8a  xor     edx, edx; fInfoLevelId
0x180052c8c  mov     [rsp+320h+var_2E8], ebx
0x180052c90  call    cs:__imp_FindFirstFileExW
0x180052c97  nop     dword ptr [rax+rax+00h]
0x180052c9c  mov     r13, rax
0x180052c9f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180052ca3  jnz     short loc_180052D04
0x180052ca5  mov     dword ptr [rsp+320h+lpFileName], ebx
0x180052ca9  call    cs:__imp_GetLastError
0x180052cb0  nop     dword ptr [rax+rax+00h]
0x180052cb5  mov     r9d, 560h
0x180052cbb  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180052cc2  mov     ecx, eax
0x180052cc4  lea     rdx, aStatus; "Status"
0x180052ccb  mov     ebx, eax
0x180052ccd  call    DebugTraceError
0x180052cd2  lea     ecx, [rbx-2]
0x180052cd5  lea     ebx, [r13+2]
0x180052cd9  cmp     ecx, ebx
0x180052cdb  ja      loc_180052DBA
0x180052ce1  mov     r9d, 566h
0x180052ce7  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180052cee  lea     rdx, aStatus; "Status"
0x180052cf5  mov     ecx, 8009002Ah
0x180052cfa  call    DebugTraceError
0x180052cff  jmp     loc_180052DBA
0x180052d04  mov     esi, [rsp+320h+var_2D0]
0x180052d08  mov     edx, ebx
0x180052d0a  test    esi, esi
0x180052d0c  jnz     short loc_180052D11
0x180052d0e  mov     edx, [rdi+30h]
0x180052d11  xor     r8d, r8d
0x180052d14  lea     rcx, [rbp+220h+FindFileData]
0x180052d18  call    IsValidKeyFileName
0x180052d1d  mov     ebx, 1
0x180052d22  test    eax, eax
0x180052d24  jz      short loc_180052D5B
0x180052d26  lea     r9, [rsp+320h+var_2C0]
0x180052d2b  mov     r8d, esi
0x180052d2e  lea     rdx, [rbp+220h+var_274]
0x180052d32  mov     rcx, r14
0x180052d35  call    ReadKeyNameFromFile
0x180052d3a  xor     ecx, ecx
0x180052d3c  test    eax, eax
0x180052d3e  jz      short loc_180052D76
0x180052d40  mov     r9d, 580h
0x180052d46  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180052d4d  lea     rdx, aStatus; "Status"
0x180052d54  mov     ecx, eax
0x180052d56  call    DebugTraceError
0x180052d5b  lea     rdx, [rbp+220h+FindFileData]; lpFindFileData
0x180052d5f  mov     rcx, r13; hFindFile
0x180052d62  call    cs:__imp_FindNextFileW
0x180052d69  nop     dword ptr [rax+rax+00h]
0x180052d6e  test    eax, eax
0x180052d70  jz      short loc_180052D7C
0x180052d72  xor     ebx, ebx
0x180052d74  jmp     short loc_180052D08
0x180052d76  mov     [rsp+320h+var_2E8], ebx
0x180052d7a  jmp     short loc_180052D9C
0x180052d7c  mov     r9d, 590h
0x180052d82  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180052d89  lea     rdx, aStatus; "Status"
0x180052d90  mov     ecx, 8009002Ah
0x180052d95  call    DebugTraceError
0x180052d9a  xor     ecx, ecx
0x180052d9c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180052da0  inc     rax
0x180052da3  cmp     [r14+rax*2], cx
0x180052da8  jnz     short loc_180052DA0
0x180052daa  mov     rsi, [rsp+320h+var_2C0]
0x180052daf  lea     eax, ds:2[rax*2]
0x180052db6  mov     dword ptr [rsp+320h+lpFileName], eax
0x180052dba  xor     eax, eax
0x180052dbc  cmp     [rdi+30h], eax
0x180052dbf  jz      short loc_180052E25
0x180052dc1  cmp     [rdi+34h], eax
0x180052dc4  jz      short loc_180052E25
0x180052dc6  cmp     [rdi+28h], rax
0x180052dca  jnz     short loc_180052E25
0x180052dcc  mov     r9d, ebx
0x180052dcf  mov     dword ptr [rsp+320h+lpSearchFilter], ebx
0x180052dd3  xor     r8d, r8d
0x180052dd6  lea     rcx, [rsp+320h+var_2B8]
0x180052ddb  xor     edx, edx
0x180052ddd  mov     edi, ebx
0x180052ddf  call    KspGetProfilePath
0x180052de4  xor     ebx, ebx
0x180052de6  test    eax, eax
0x180052de8  jz      short loc_180052E09
0x180052dea  mov     r9d, 5ACh
0x180052df0  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180052df7  lea     rdx, aStatus; "Status"
0x180052dfe  mov     ecx, eax
0x180052e00  call    DebugTraceError
0x180052e05  mov     eax, ebx
0x180052e07  jmp     short loc_180052E29
0x180052e09  mov     r15, [rsp+320h+var_2B8]
0x180052e0e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180052e12  inc     rax
0x180052e15  cmp     [r15+rax*2], bx
0x180052e1a  jnz     short loc_180052E12
0x180052e1c  lea     eax, ds:2[rax*2]
0x180052e23  jmp     short loc_180052E29
0x180052e25  mov     edi, eax
0x180052e27  xor     ebx, ebx
0x180052e29  cmp     [rsp+320h+var_2E8], ebx
0x180052e2d  jnz     short loc_180052E3D
0x180052e2f  test    edi, edi
0x180052e31  jnz     short loc_180052E3D
0x180052e33  mov     ebx, 8009002Ah
0x180052e38  jmp     loc_180052F0D
0x180052e3d  mov     r14d, dword ptr [rsp+320h+lpFileName]
0x180052e42  mov     r12d, eax
0x180052e45  lea     rcx, [r14+40h]
0x180052e49  add     rcx, r12
0x180052e4c  call    SafeAllocaAllocateFromHeap
0x180052e51  mov     rdi, rax
0x180052e54  test    rax, rax
0x180052e57  jnz     short loc_180052E81
0x180052e59  mov     r9d, 5C5h
0x180052e5f  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180052e66  lea     rdx, aStatus; "Status"
0x180052e6d  mov     ecx, 8009000Eh
0x180052e72  mov     ebx, 8009000Eh
0x180052e77  call    DebugTraceError
0x180052e7c  jmp     loc_180052F03
0x180052e81  mov     rdx, [rsp+320h+Src]; Src
0x180052e86  mov     r8, r14; Size
0x180052e89  mov     [rax], ebx
0x180052e8b  mov     [rax+18h], ebx
0x180052e8e  lea     rbx, [rdi+40h]
0x180052e92  mov     [rax+8], r13
0x180052e96  mov     rcx, rbx; void *
0x180052e99  or      rax, 0FFFFFFFFFFFFFFFFh
0x180052e9d  mov     qword ptr [rdi+34h], 0
0x180052ea5  mov     r13, rax
0x180052ea8  mov     [rdi+20h], rax
0x180052eac  mov     eax, [rsp+320h+var_2D0]
0x180052eb0  mov     [rdi+30h], eax
0x180052eb3  call    memcpy_0
0x180052eb8  xor     eax, eax
0x180052eba  mov     [rdi+10h], rbx
0x180052ebe  test    r15, r15
0x180052ec1  jz      short loc_180052EDA
0x180052ec3  lea     rbx, [r14+40h]
0x180052ec7  mov     r8, r12; Size
0x180052eca  add     rbx, rdi
0x180052ecd  mov     rdx, r15; Src
0x180052ed0  mov     rcx, rbx; void *
0x180052ed3  call    memcpy_0
0x180052ed8  jmp     short loc_180052EDD
0x180052eda  mov     rbx, rax
0x180052edd  mov     rax, [rsp+320h+var_2B0]
0x180052ee2  mov     [rdi+28h], rbx
0x180052ee6  xor     ebx, ebx
0x180052ee8  mov     [rax], rdi
0x180052eeb  cmp     [rsp+320h+var_2E8], ebx
0x180052eef  jnz     short loc_180052EF8
0x180052ef1  mov     ebx, 8009002Ah
0x180052ef6  jmp     short loc_180052F03
0x180052ef8  mov     rax, [rsp+320h+var_2A8]
0x180052efd  mov     [rax], rsi
0x180052f00  mov     rsi, rbx
0x180052f03  mov     r14, [rsp+320h+Src]
0x180052f08  mov     r12, [rsp+320h+pszSrc]
0x180052f0d  test    r14, r14
0x180052f10  jz      short loc_180052F1A
0x180052f12  mov     rcx, r14
0x180052f15  call    MSCryptFree
0x180052f1a  test    r15, r15
0x180052f1d  jz      short loc_180052F27
0x180052f1f  mov     rcx, r15
0x180052f22  call    MSCryptFree
0x180052f27  test    rsi, rsi
0x180052f2a  jz      short loc_180052F34
0x180052f2c  mov     rcx, rsi
0x180052f2f  call    MSCryptFree
0x180052f34  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x180052f38  jz      short loc_180052F49
0x180052f3a  mov     rcx, r13; hFindFile
0x180052f3d  call    cs:__imp_FindClose
0x180052f44  nop     dword ptr [rax+rax+00h]
0x180052f49  test    r12, r12
0x180052f4c  jz      short loc_180052F56
0x180052f4e  mov     rcx, r12
0x180052f51  call    MSCryptFree
0x180052f56  mov     eax, ebx
0x180052f58  mov     rcx, [rbp+220h+var_50]
0x180052f5f  xor     rcx, rsp; StackCookie
0x180052f62  call    __security_check_cookie
0x180052f67  add     rsp, 2E8h
0x180052f6e  pop     r15
0x180052f70  pop     r14
0x180052f72  pop     r13
0x180052f74  pop     r12
0x180052f76  pop     rdi
0x180052f77  pop     rsi
0x180052f78  pop     rbx
0x180052f79  pop     rbp
0x180052f7a  retn
```
