# GetAllowListAppByAliasFromRegistry(ushort const *,AllowListAppInfo *)

- ea: `0x1800765b8`
- end: `0x1800768de`
- name: `?GetAllowListAppByAliasFromRegistry@@YAJPEBGPEAUAllowListAppInfo@@@Z`
- size: `806`
- prototype: `int(const unsigned __int16 *, struct AllowListAppInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180075fb0`

## callees

- `0x18000e420`
- `0x180033da0`
- `0x180034970`
- `0x1800765b8`
- `0x18014c328`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180076767`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800767b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180076803`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180076767`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800767b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180076803`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800768a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800768b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800768a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800768b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800766b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007671c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800766b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007671c`
- `RDPBASE!TRC_TraceBufferW` at `0x180076682`
- `RDPBASE!TRC_TraceBufferW` at `0x1800766f7`
- `RDPBASE!TRC_TraceBufferW` at `0x18007688d`
- `RDPBASE!TRC_TraceBufferW` at `0x180076682`
- `RDPBASE!TRC_TraceBufferW` at `0x1800766f7`
- `RDPBASE!TRC_TraceBufferW` at `0x18007688d`

## string_xrefs

- `0x18007685c`: `Invalid argument to GetAllowListAppByAliasFromRegistry!`
- `0x180076658`: `StringCchCopy hr[0x%x]`
- `0x18007664c`: `GetAllowListAppByAliasFromRegistry`
- `0x1800766d1`: `GetAllowListAppByAliasFromRegistry`
- `0x180076868`: `GetAllowListAppByAliasFromRegistry`
- `0x1800766ba`: `RegOpenKeyEx ALLOW_LIST_APP_KEY`
- `0x180076845`: `RegQueryValueEx ALLOW_LIST_COMMON_PATH_VALUE`
- `0x180076726`: `RegOpenKeyEx Alias`
- `0x1800767fc`: `RequiredCommandLine`
- `0x1800767af`: `CommandLineSetting`

## pseudocode

```c
__int64 __fastcall GetAllowListAppByAliasFromRegistry(const unsigned __int16 *a1, struct AllowListAppInfo *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  const wchar_t *v6; // rax
  __int64 v7; // r8
  __int64 cbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[260]; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[520]; // [rsp+268h] [rbp+168h] BYREF
  BYTE v14[4]; // [rsp+470h] [rbp+370h] BYREF
  BYTE v15[520]; // [rsp+474h] [rbp+374h] BYREF
  int v16; // [rsp+67Ch] [rbp+57Ch]

  memset_0(SubKey, 0, 0x620u);
  hKey = 0;
  phkResult = 0;
  cbData = 0;
  if ( a1 && a2 )
  {
    v4 = StringCchCopyW(SubKey, 0x104u, a1 + 2);
    v5 = v4;
    if ( v4 < 0 )
    {
      TRC_TraceBufferW(
        3,
        4096,
        81,
        L"GetAllowListAppByAliasFromRegistry",
        L"clientcore\\termsrv\\rap\\allow\\lib\\tsallow.cpp",
        0,
        L"StringCchCopy hr[0x%x]",
        v4,
        cbData);
      goto LABEL_23;
    }
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Terminal Server\\TSAppAllowList\\Applications",
           0,
           0x20019u,
           &hKey) )
    {
      v6 = L"RegOpenKeyEx ALLOW_LIST_APP_KEY";
      v7 = 92;
LABEL_7:
      v5 = 1;
LABEL_8:
      TRC_TraceBufferW(
        3,
        4096,
        v7,
        L"GetAllowListAppByAliasFromRegistry",
        L"clientcore\\termsrv\\rap\\allow\\lib\\tsallow.cpp",
        0,
        v6);
      goto LABEL_23;
    }
    if ( RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &phkResult) )
    {
      v6 = L"RegOpenKeyEx Alias";
      v7 = 106;
      goto LABEL_7;
    }
    LODWORD(cbData) = 520;
    v5 = 1;
    if ( RegQueryValueExW(phkResult, L"Path", 0, (LPDWORD)&cbData + 1, Data, (LPDWORD)&cbData) || HIDWORD(cbData) != 1 )
    {
      v6 = L"RegQueryValueEx ALLOW_LIST_COMMON_PATH_VALUE";
      v7 = 122;
      goto LABEL_8;
    }
    LODWORD(cbData) = 4;
    if ( RegQueryValueExW(phkResult, L"CommandLineSetting", 0, (LPDWORD)&cbData + 1, v14, (LPDWORD)&cbData)
      || HIDWORD(cbData) != 4 )
    {
      *(_DWORD *)v14 = 0;
    }
    LODWORD(cbData) = 520;
    if ( RegQueryValueExW(phkResult, L"RequiredCommandLine", 0, (LPDWORD)&cbData + 1, v15, (LPDWORD)&cbData)
      || HIDWORD(cbData) != 1 )
    {
      v16 = 0;
      *(_WORD *)v15 = 0;
    }
    else
    {
      v16 = 1;
    }
    memcpy_0(a2, SubKey, 0x620u);
    v5 = 0;
  }
  else
  {
    TRC_TraceBufferW(
      3,
      4096,
      66,
      L"GetAllowListAppByAliasFromRegistry",
      L"clientcore\\termsrv\\rap\\allow\\lib\\tsallow.cpp",
      0,
      L"Invalid argument to GetAllowListAppByAliasFromRegistry!");
    v5 = -2147024809;
  }
LABEL_23:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x1800765b8  mov     [rsp-8+arg_10], rbx
0x1800765bd  mov     [rsp-8+arg_18], rdi
0x1800765c2  push    rbp
0x1800765c3  lea     rbp, [rsp-590h]
0x1800765cb  sub     rsp, 690h
0x1800765d2  mov     rax, cs:__security_cookie
0x1800765d9  xor     rax, rsp
0x1800765dc  mov     [rbp+590h+var_10], rax
0x1800765e3  mov     rdi, rdx
0x1800765e6  mov     rbx, rcx
0x1800765e9  xor     edx, edx; Val
0x1800765eb  lea     rcx, [rsp+690h+SubKey]; void *
0x1800765f0  mov     r8d, 620h; Size
0x1800765f6  call    memset_0
0x1800765fb  mov     [rsp+690h+hKey], 0
0x180076604  mov     [rsp+690h+var_648], 0
0x18007660d  mov     [rsp+690h+Type], 0
0x180076615  mov     [rsp+690h+cbData], 0
0x18007661d  test    rbx, rbx
0x180076620  jz      loc_180076857
0x180076626  test    rdi, rdi
0x180076629  jz      loc_180076857
0x18007662f  lea     r8, [rbx+4]; unsigned __int16 *
0x180076633  mov     edx, 104h; unsigned __int64
0x180076638  lea     rcx, [rsp+690h+SubKey]; unsigned __int16 *
0x18007663d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180076642  mov     ebx, eax
0x180076644  test    eax, eax
0x180076646  jns     short loc_18007668D
0x180076648  mov     [rsp+690h+var_658], eax
0x18007664c  lea     r9, aGetallowlistap_2; "GetAllowListAppByAliasFromRegistry"
0x180076653  mov     ecx, 3
0x180076658  lea     rax, aStringcchcopyH; "StringCchCopy hr[0x%x]"
0x18007665f  mov     [rsp+690h+var_660], rax
0x180076664  mov     edx, 1000h
0x180076669  lea     rax, aClientcoreTerm_1; "clientcore\\termsrv\\rap\\allow\\lib\\t"...
0x180076670  mov     [rsp+690h+lpcbData], 0
0x180076679  mov     [rsp+690h+phkResult], rax
0x18007667e  lea     r8d, [rcx+4Eh]
0x180076682  call    cs:__imp_TRC_TraceBufferW
0x180076688  jmp     loc_180076898
0x18007668d  lea     rax, [rsp+690h+hKey]
0x180076692  mov     ebx, 20019h
0x180076697  mov     r9d, ebx; samDesired
0x18007669a  mov     [rsp+690h+phkResult], rax; phkResult
0x18007669f  xor     r8d, r8d; ulOptions
0x1800766a2  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800766a9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800766b0  call    cs:__imp_RegOpenKeyExW
0x1800766b6  test    eax, eax
0x1800766b8  jz      short loc_180076702
0x1800766ba  lea     rax, aRegopenkeyexAl_0; "RegOpenKeyEx ALLOW_LIST_APP_KEY"
0x1800766c1  mov     r8d, 5Ch ; '\'
0x1800766c7  mov     ebx, 1
0x1800766cc  mov     [rsp+690h+var_660], rax
0x1800766d1  lea     r9, aGetallowlistap_2; "GetAllowListAppByAliasFromRegistry"
0x1800766d8  lea     rax, aClientcoreTerm_1; "clientcore\\termsrv\\rap\\allow\\lib\\t"...
0x1800766df  mov     [rsp+690h+lpcbData], 0
0x1800766e8  mov     edx, 1000h
0x1800766ed  mov     [rsp+690h+phkResult], rax
0x1800766f2  mov     ecx, 3
0x1800766f7  call    cs:__imp_TRC_TraceBufferW
0x1800766fd  jmp     loc_180076898
0x180076702  mov     rcx, [rsp+690h+hKey]; hKey
0x180076707  lea     rax, [rsp+690h+var_648]
0x18007670c  mov     r9d, ebx; samDesired
0x18007670f  mov     [rsp+690h+phkResult], rax; phkResult
0x180076714  xor     r8d, r8d; ulOptions
0x180076717  lea     rdx, [rsp+690h+SubKey]; lpSubKey
0x18007671c  call    cs:__imp_RegOpenKeyExW
0x180076722  test    eax, eax
0x180076724  jz      short loc_180076735
0x180076726  lea     rax, aRegopenkeyexAl; "RegOpenKeyEx Alias"
0x18007672d  mov     r8d, 6Ah ; 'j'
0x180076733  jmp     short loc_1800766C7
0x180076735  mov     rcx, [rsp+690h+var_648]; hKey
0x18007673a  lea     rax, [rsp+690h+cbData]
0x18007673f  mov     [rsp+690h+lpcbData], rax; lpcbData
0x180076744  lea     r9, [rsp+690h+Type]; lpType
0x180076749  lea     rax, [rbp+590h+Data]
0x180076750  mov     [rsp+690h+cbData], 208h
0x180076758  xor     r8d, r8d; lpReserved
0x18007675b  mov     [rsp+690h+phkResult], rax; lpData
0x180076760  lea     rdx, aPath; "Path"
0x180076767  call    cs:__imp_RegQueryValueExW
0x18007676d  mov     ebx, 1
0x180076772  test    eax, eax
0x180076774  jnz     loc_180076845
0x18007677a  cmp     [rsp+690h+Type], ebx
0x18007677e  jnz     loc_180076845
0x180076784  mov     rcx, [rsp+690h+var_648]; hKey
0x180076789  lea     rax, [rsp+690h+cbData]
0x18007678e  mov     [rsp+690h+lpcbData], rax; lpcbData
0x180076793  lea     r9, [rsp+690h+Type]; lpType
0x180076798  lea     rax, [rbp+590h+var_220]
0x18007679f  mov     [rsp+690h+cbData], 4
0x1800767a7  xor     r8d, r8d; lpReserved
0x1800767aa  mov     [rsp+690h+phkResult], rax; lpData
0x1800767af  lea     rdx, aCommandlineset; "CommandLineSetting"
0x1800767b6  call    cs:__imp_RegQueryValueExW
0x1800767bc  test    eax, eax
0x1800767be  jnz     short loc_1800767C7
0x1800767c0  cmp     [rsp+690h+Type], 4
0x1800767c5  jz      short loc_1800767D1
0x1800767c7  mov     dword ptr [rbp+590h+var_220], 0
0x1800767d1  mov     rcx, [rsp+690h+var_648]; hKey
0x1800767d6  lea     rax, [rsp+690h+cbData]
0x1800767db  mov     [rsp+690h+lpcbData], rax; lpcbData
0x1800767e0  lea     r9, [rsp+690h+Type]; lpType
0x1800767e5  lea     rax, [rbp+590h+var_21C]
0x1800767ec  mov     [rsp+690h+cbData], 208h
0x1800767f4  xor     r8d, r8d; lpReserved
0x1800767f7  mov     [rsp+690h+phkResult], rax; lpData
0x1800767fc  lea     rdx, aRequiredcomman; "RequiredCommandLine"
0x180076803  call    cs:__imp_RegQueryValueExW
0x180076809  test    eax, eax
0x18007680b  jnz     short loc_18007681B
0x18007680d  cmp     [rsp+690h+Type], ebx
0x180076811  jnz     short loc_18007681B
0x180076813  mov     [rbp+590h+var_14], ebx
0x180076819  jmp     short loc_18007682E
0x18007681b  xor     eax, eax
0x18007681d  mov     [rbp+590h+var_14], 0
0x180076827  mov     word ptr [rbp+590h+var_21C], ax
0x18007682e  mov     rcx, rdi; void *
0x180076831  lea     rdx, [rsp+690h+SubKey]; Src
0x180076836  mov     r8d, 620h; Size
0x18007683c  call    memcpy_0
0x180076841  xor     ebx, ebx
0x180076843  jmp     short loc_180076898
0x180076845  lea     rax, aRegqueryvaluee_0; "RegQueryValueEx ALLOW_LIST_COMMON_PATH_"...
0x18007684c  mov     r8d, 7Ah ; 'z'
0x180076852  jmp     loc_1800766CC
0x180076857  mov     ecx, 3
0x18007685c  lea     rax, aInvalidArgumen_0; "Invalid argument to GetAllowListAppByAl"...
0x180076863  mov     [rsp+690h+var_660], rax
0x180076868  lea     r9, aGetallowlistap_2; "GetAllowListAppByAliasFromRegistry"
0x18007686f  lea     rax, aClientcoreTerm_1; "clientcore\\termsrv\\rap\\allow\\lib\\t"...
0x180076876  mov     [rsp+690h+lpcbData], 0
0x18007687f  mov     edx, 1000h
0x180076884  mov     [rsp+690h+phkResult], rax
0x180076889  lea     r8d, [rcx+3Fh]
0x18007688d  call    cs:__imp_TRC_TraceBufferW
0x180076893  mov     ebx, 80070057h
0x180076898  mov     rcx, [rsp+690h+var_648]; hKey
0x18007689d  test    rcx, rcx
0x1800768a0  jz      short loc_1800768A8
0x1800768a2  call    cs:__imp_RegCloseKey
0x1800768a8  mov     rcx, [rsp+690h+hKey]; hKey
0x1800768ad  test    rcx, rcx
0x1800768b0  jz      short loc_1800768B8
0x1800768b2  call    cs:__imp_RegCloseKey
0x1800768b8  mov     eax, ebx
0x1800768ba  mov     rcx, [rbp+590h+var_10]
0x1800768c1  xor     rcx, rsp; StackCookie
0x1800768c4  call    __security_check_cookie
0x1800768c9  lea     r11, [rsp+690h+var_s0]
0x1800768d1  mov     rbx, [r11+20h]
0x1800768d5  mov     rdi, [r11+28h]
0x1800768d9  mov     rsp, r11
0x1800768dc  pop     rbp
0x1800768dd  retn
```
