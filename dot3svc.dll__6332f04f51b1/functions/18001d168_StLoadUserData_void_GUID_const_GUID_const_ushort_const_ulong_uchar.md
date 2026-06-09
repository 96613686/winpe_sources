# StLoadUserData(void *,_GUID const *,_GUID const *,ushort const *,ulong *,uchar * *)

- ea: `0x18001d168`
- end: `0x18001d475`
- name: `?StLoadUserData@@YAKPEAXPEBU_GUID@@1PEBGPEAKPEAPEAE@Z`
- size: `781`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, GUID *rguid, GUID *, LPCWSTR lpValueName, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000cd2c`

## callees

- `0x1800025f0`
- `0x1800030fc`
- `0x18000a7ec`
- `0x18000a87c`
- `0x18000a9c0`
- `0x18000c230`
- `0x18001d168`
- `0x18001e34c`
- `0x18001e620`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d294`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d294`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d2c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d31a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d2c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d31a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d405`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d413`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d405`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d413`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d2e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d360`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d2e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d360`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d381`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d3d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d3d4`
- `CRYPT32!CryptUnprotectData` at `0x18001d356`
- `CRYPT32!CryptUnprotectData` at `0x18001d356`

## pseudocode

```c
__int64 __fastcall StLoadUserData(
        HANDLE TokenHandle,
        GUID *rguid,
        GUID *a3,
        LPCWSTR lpValueName,
        unsigned int *a5,
        unsigned __int8 **a6)
{
  unsigned __int8 **v6; // rax
  HKEY v7; // rdi
  unsigned int HKeyFromToken; // eax
  unsigned int RegKeyPath; // ebx
  __int64 v14; // rcx
  BYTE *pbData; // rax
  size_t v16; // r14
  void *v17; // rsi
  unsigned __int8 **v18; // rax
  BYTE *v19; // rax
  __int64 v20; // rcx
  DATA_BLOB cbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DATA_BLOB pDataOut; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v25; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int8 **v26; // [rsp+70h] [rbp-90h]
  WCHAR SubKey[264]; // [rsp+80h] [rbp-80h] BYREF

  v6 = a6;
  v7 = 0;
  v26 = a6;
  v25 = 0;
  hKey = 0;
  *(_QWORD *)&cbData.cbData = 0;
  cbData.pbData = 0;
  *(_QWORD *)&pDataOut.cbData = 0;
  pDataOut.pbData = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 33, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids);
    v6 = v26;
  }
  if ( lpValueName && a5 && v6 )
  {
    if ( !TokenHandle
      || (HKeyFromToken = StpGetHKeyFromToken(TokenHandle, &v25), v7 = v25, (RegKeyPath = HKeyFromToken) == 0) )
    {
      RegKeyPath = StpGetRegKeyPath(rguid, a3, 1, SubKey, 0x104u);
      if ( !RegKeyPath )
      {
        v14 = -2147483646;
        if ( TokenHandle )
          v14 = (__int64)v7;
        RegKeyPath = RegOpenKeyExW((HKEY)v14, SubKey, 0, 1u, &hKey);
        if ( !RegKeyPath )
        {
          RegKeyPath = RegQueryValueExW(hKey, lpValueName, 0, 0, 0, &cbData.cbData);
          if ( !RegKeyPath )
          {
            pbData = (BYTE *)Dot3Alloc(cbData.cbData);
            cbData.pbData = pbData;
            if ( !pbData )
            {
              RegKeyPath = GetLastError();
              if ( RegKeyPath )
                goto LABEL_25;
              pbData = cbData.pbData;
            }
            RegKeyPath = RegQueryValueExW(hKey, lpValueName, 0, 0, pbData, &cbData.cbData);
            if ( !RegKeyPath
              && (CryptUnprotectData(&cbData, 0, &blobSalt, 0, 0, 1u, &pDataOut) || (RegKeyPath = GetLastError()) == 0) )
            {
              v16 = pDataOut.cbData;
              v17 = Dot3Alloc(pDataOut.cbData);
              if ( v17 || (RegKeyPath = GetLastError()) == 0 )
              {
                memcpy_0(v17, pDataOut.pbData, v16);
                v18 = v26;
                *a5 = v16;
                *v18 = (unsigned __int8 *)v17;
              }
            }
          }
        }
      }
    }
  }
  else
  {
    RegKeyPath = 87;
  }
LABEL_25:
  v19 = pDataOut.pbData;
  if ( pDataOut.pbData )
  {
    v20 = pDataOut.cbData;
    if ( pDataOut.cbData )
    {
      do
      {
        *v19++ = 0;
        --v20;
      }
      while ( v20 );
    }
    LocalFree(pDataOut.pbData);
    pDataOut.pbData = 0;
  }
  if ( cbData.pbData )
  {
    Dot3Free(cbData.pbData);
    cbData.pbData = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v7 )
    RegCloseKey(v7);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 34, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids, RegKeyPath);
  }
  return RegKeyPath;
}

```

## disassembly

```asm
0x18001d168  push    rbp
0x18001d16a  push    rbx
0x18001d16b  push    rsi
0x18001d16c  push    rdi
0x18001d16d  push    r12
0x18001d16f  push    r13
0x18001d171  push    r14
0x18001d173  push    r15
0x18001d175  lea     rbp, [rsp-1A8h]
0x18001d17d  sub     rsp, 2A8h
0x18001d184  mov     rax, cs:__security_cookie
0x18001d18b  xor     rax, rsp
0x18001d18e  mov     [rbp+1E0h+var_50], rax
0x18001d195  mov     rax, [rbp+1E0h+arg_28]
0x18001d19c  xor     ebx, ebx
0x18001d19e  mov     r13, [rbp+1E0h+arg_20]
0x18001d1a5  mov     edi, ebx
0x18001d1a7  mov     [rsp+2E0h+var_270], rax
0x18001d1ac  mov     r14, r9
0x18001d1af  mov     [rsp+2E0h+var_278], rbx
0x18001d1b4  mov     r12, r8
0x18001d1b7  mov     [rsp+2E0h+hKey], rbx
0x18001d1bc  mov     r15, rdx
0x18001d1bf  mov     qword ptr [rsp+2E0h+cbData], rbx
0x18001d1c4  mov     rsi, rcx
0x18001d1c7  mov     [rsp+2E0h+lpMem], rbx
0x18001d1cc  mov     qword ptr [rsp+2E0h+var_288.cbData], rbx
0x18001d1d1  mov     [rsp+2E0h+var_288.pbData], rbx
0x18001d1d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d1dd  lea     rdx, WPP_GLOBAL_Control
0x18001d1e4  cmp     rcx, rdx
0x18001d1e7  jz      short loc_18001D20D
0x18001d1e9  cmp     byte ptr [rcx+19h], 4
0x18001d1ed  jb      short loc_18001D20D
0x18001d1ef  test    byte ptr [rcx+1Ch], 1
0x18001d1f3  jz      short loc_18001D20D
0x18001d1f5  mov     rcx, [rcx+10h]
0x18001d1f9  lea     edx, [rbx+21h]
0x18001d1fc  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001d203  call    WPP_SF_
0x18001d208  mov     rax, [rsp+2E0h+var_270]
0x18001d20d  test    r14, r14
0x18001d210  jz      loc_18001D3AB
0x18001d216  test    r13, r13
0x18001d219  jz      loc_18001D3AB
0x18001d21f  test    rax, rax
0x18001d222  jz      loc_18001D3AB
0x18001d228  test    rsi, rsi
0x18001d22b  jz      short loc_18001D249
0x18001d22d  lea     rdx, [rsp+2E0h+var_278]; HKEY *
0x18001d232  mov     rcx, rsi; TokenHandle
0x18001d235  call    ?StpGetHKeyFromToken@@YAKPEAXPEAPEAUHKEY__@@@Z; StpGetHKeyFromToken(void *,HKEY__ * *)
0x18001d23a  mov     rdi, [rsp+2E0h+var_278]
0x18001d23f  mov     ebx, eax
0x18001d241  test    eax, eax
0x18001d243  jnz     loc_18001D3B0
0x18001d249  lea     r9, [rbp+1E0h+SubKey]; unsigned __int16 *
0x18001d24d  mov     [rsp+2E0h+phkResult], 104h; unsigned __int64
0x18001d256  mov     r8d, 1; int
0x18001d25c  mov     rdx, r12; GUID *
0x18001d25f  mov     rcx, r15; rguid
0x18001d262  call    ?StpGetRegKeyPath@@YAKPEBU_GUID@@0HPEAG_K@Z; StpGetRegKeyPath(_GUID const *,_GUID const *,int,ushort *,unsigned __int64)
0x18001d267  mov     ebx, eax
0x18001d269  test    eax, eax
0x18001d26b  jnz     loc_18001D3B0
0x18001d271  lea     rax, [rsp+2E0h+hKey]
0x18001d276  test    rsi, rsi
0x18001d279  mov     rcx, 0FFFFFFFF80000002h
0x18001d280  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18001d285  cmovnz  rcx, rdi; hKey
0x18001d289  lea     r9d, [rbx+1]; samDesired
0x18001d28d  xor     r8d, r8d; ulOptions
0x18001d290  lea     rdx, [rbp+1E0h+SubKey]; lpSubKey
0x18001d294  call    cs:__imp_RegOpenKeyExW
0x18001d29a  mov     ebx, eax
0x18001d29c  test    eax, eax
0x18001d29e  jnz     loc_18001D3B0
0x18001d2a4  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18001d2a9  lea     rax, [rsp+2E0h+cbData]
0x18001d2ae  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x18001d2b3  xor     r9d, r9d; lpType
0x18001d2b6  xor     r8d, r8d; lpReserved
0x18001d2b9  mov     [rsp+2E0h+phkResult], 0; lpData
0x18001d2c2  mov     rdx, r14; lpValueName
0x18001d2c5  call    cs:__imp_RegQueryValueExW
0x18001d2cb  mov     ebx, eax
0x18001d2cd  test    eax, eax
0x18001d2cf  jnz     loc_18001D3B0
0x18001d2d5  mov     ecx, [rsp+2E0h+cbData]; dwBytes
0x18001d2d9  call    ?Dot3Alloc@@YAPEAX_K@Z; Dot3Alloc(unsigned __int64)
0x18001d2de  mov     [rsp+2E0h+lpMem], rax
0x18001d2e3  test    rax, rax
0x18001d2e6  jnz     short loc_18001D2FD
0x18001d2e8  call    cs:__imp_GetLastError
0x18001d2ee  mov     ebx, eax
0x18001d2f0  test    eax, eax
0x18001d2f2  jnz     loc_18001D3B0
0x18001d2f8  mov     rax, [rsp+2E0h+lpMem]
0x18001d2fd  lea     rcx, [rsp+2E0h+cbData]
0x18001d302  xor     r9d, r9d; lpType
0x18001d305  mov     [rsp+2E0h+lpcbData], rcx; lpcbData
0x18001d30a  xor     r8d, r8d; lpReserved
0x18001d30d  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18001d312  mov     rdx, r14; lpValueName
0x18001d315  mov     [rsp+2E0h+phkResult], rax; lpData
0x18001d31a  call    cs:__imp_RegQueryValueExW
0x18001d320  mov     ebx, eax
0x18001d322  test    eax, eax
0x18001d324  jnz     loc_18001D3B0
0x18001d32a  lea     rax, [rsp+2E0h+var_288]
0x18001d32f  xor     r9d, r9d; pvReserved
0x18001d332  mov     [rsp+2E0h+pDataOut], rax; pDataOut
0x18001d337  lea     r8, ?blobSalt@@3U_CRYPTOAPI_BLOB@@A; pOptionalEntropy
0x18001d33e  mov     dword ptr [rsp+2E0h+lpcbData], 1; dwFlags
0x18001d346  lea     rcx, [rsp+2E0h+cbData]; pDataIn
0x18001d34b  xor     edx, edx; ppszDataDescr
0x18001d34d  mov     [rsp+2E0h+phkResult], 0; pPromptStruct
0x18001d356  call    cs:__imp_CryptUnprotectData
0x18001d35c  test    eax, eax
0x18001d35e  jnz     short loc_18001D36C
0x18001d360  call    cs:__imp_GetLastError
0x18001d366  mov     ebx, eax
0x18001d368  test    eax, eax
0x18001d36a  jnz     short loc_18001D3B0
0x18001d36c  mov     r14d, [rsp+2E0h+var_288.cbData]
0x18001d371  mov     ecx, r14d; dwBytes
0x18001d374  call    ?Dot3Alloc@@YAPEAX_K@Z; Dot3Alloc(unsigned __int64)
0x18001d379  mov     rsi, rax
0x18001d37c  test    rax, rax
0x18001d37f  jnz     short loc_18001D38D
0x18001d381  call    cs:__imp_GetLastError
0x18001d387  mov     ebx, eax
0x18001d389  test    eax, eax
0x18001d38b  jnz     short loc_18001D3B0
0x18001d38d  mov     rdx, [rsp+2E0h+var_288.pbData]; Src
0x18001d392  mov     r8, r14; Size
0x18001d395  mov     rcx, rsi; void *
0x18001d398  call    memcpy_0
0x18001d39d  mov     rax, [rsp+2E0h+var_270]
0x18001d3a2  mov     [r13+0], r14d
0x18001d3a6  mov     [rax], rsi
0x18001d3a9  jmp     short loc_18001D3B0
0x18001d3ab  mov     ebx, 57h ; 'W'
0x18001d3b0  mov     rax, [rsp+2E0h+var_288.pbData]
0x18001d3b5  test    rax, rax
0x18001d3b8  jz      short loc_18001D3E3
0x18001d3ba  mov     ecx, [rsp+2E0h+var_288.cbData]
0x18001d3be  test    rcx, rcx
0x18001d3c1  jz      short loc_18001D3CF
0x18001d3c3  mov     byte ptr [rax], 0
0x18001d3c6  inc     rax
0x18001d3c9  sub     rcx, 1
0x18001d3cd  jnz     short loc_18001D3C3
0x18001d3cf  mov     rcx, [rsp+2E0h+var_288.pbData]; hMem
0x18001d3d4  call    cs:__imp_LocalFree
0x18001d3da  mov     [rsp+2E0h+var_288.pbData], 0
0x18001d3e3  mov     rcx, [rsp+2E0h+lpMem]; lpMem
0x18001d3e8  test    rcx, rcx
0x18001d3eb  jz      short loc_18001D3FB
0x18001d3ed  call    ?Dot3Free@@YAXPEAX@Z; Dot3Free(void *)
0x18001d3f2  mov     [rsp+2E0h+lpMem], 0
0x18001d3fb  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18001d400  test    rcx, rcx
0x18001d403  jz      short loc_18001D40B
0x18001d405  call    cs:__imp_RegCloseKey
0x18001d40b  test    rdi, rdi
0x18001d40e  jz      short loc_18001D419
0x18001d410  mov     rcx, rdi; hKey
0x18001d413  call    cs:__imp_RegCloseKey
0x18001d419  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d420  lea     rax, WPP_GLOBAL_Control
0x18001d427  cmp     rcx, rax
0x18001d42a  jz      short loc_18001D450
0x18001d42c  cmp     byte ptr [rcx+19h], 4
0x18001d430  jb      short loc_18001D450
0x18001d432  test    byte ptr [rcx+1Ch], 1
0x18001d436  jz      short loc_18001D450
0x18001d438  mov     rcx, [rcx+10h]
0x18001d43c  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001d443  mov     edx, 22h ; '"'
0x18001d448  mov     r9d, ebx
0x18001d44b  call    WPP_SF_d
0x18001d450  mov     eax, ebx
0x18001d452  mov     rcx, [rbp+1E0h+var_50]
0x18001d459  xor     rcx, rsp; StackCookie
0x18001d45c  call    __security_check_cookie
0x18001d461  add     rsp, 2A8h
0x18001d468  pop     r15
0x18001d46a  pop     r14
0x18001d46c  pop     r13
0x18001d46e  pop     r12
0x18001d470  pop     rdi
0x18001d471  pop     rsi
0x18001d472  pop     rbx
0x18001d473  pop     rbp
0x18001d474  retn
```
