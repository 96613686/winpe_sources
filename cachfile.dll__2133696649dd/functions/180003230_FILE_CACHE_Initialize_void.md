# FILE_CACHE::Initialize(void)

- ea: `0x180003230`
- end: `0x18000352d`
- name: `?Initialize@FILE_CACHE@@QEAAJXZ`
- size: `765`
- prototype: `__int64 __fastcall(FILE_CACHE *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003720`

## callees

- `0x180003230`
- `0x180003534`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000348f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003502`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000348f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003502`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003289`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800034b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003289`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800034b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800032c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003300`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000333d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000337e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800033bf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800033fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003433`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003472`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800034e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800032c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003300`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000333d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000337e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800033bf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800033fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003433`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003472`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800034e6`
- `iisutil!?Initialize@TREE_HASH_TABLE@@QEAAJK@Z` at `0x180003510`
- `iisutil!?Initialize@TREE_HASH_TABLE@@QEAAJK@Z` at `0x180003510`

## string_xrefs

- `0x180003260`: `System\CurrentControlSet\Services\inetinfo\Parameters`
- `0x1800032ba`: `DisableMemoryCache`
- `0x1800032f9`: `MaxCachedFileSize`
- `0x180003336`: `MaxCachedFileSizeInMB`
- `0x180003377`: `MemCacheSize`
- `0x1800033b8`: `MaxOpenFiles`
- `0x1800033f4`: `ObjectCacheTTL`
- `0x1800034a7`: `System\CurrentControlSet\Services\http\Parameters`
- `0x1800034df`: `UriEnableCache`

## pseudocode

```c
signed int __fastcall FILE_CACHE::Initialize(FILE_CACHE *this)
{
  _BYTE *v1; // rbx
  int v2; // edi
  signed int result; // eax
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  int v5; // [rsp+64h] [rbp+2Ch]
  DWORD Type; // [rsp+68h] [rbp+30h] BYREF
  unsigned int Data; // [rsp+70h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+40h] BYREF

  v5 = HIDWORD(this);
  v1 = g_pFileCache;
  Type = 0;
  Data = 0;
  cbData = 0;
  v2 = 30;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\inetinfo\\Parameters",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"DisableMemoryCache", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      v1[64] = Data == 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"MaxCachedFileSize", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      *((_QWORD *)v1 + 5) = Data;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"MaxCachedFileSizeInMB", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      *((_QWORD *)v1 + 5) += (unsigned __int64)Data << 20;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"MemCacheSize", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      *((_QWORD *)v1 + 6) = (unsigned __int64)Data << 20;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"MaxOpenFiles", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      *((_DWORD *)v1 + 14) = Data;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"ObjectCacheTTL", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      v2 = Data;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"DoDirMonitoringForUnc", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      v1[66] = Data != 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"FileAttributeCheckThreshold", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      *((_DWORD *)v1 + 17) = 1000 * Data;
    RegCloseKey(hKey);
  }
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\http\\Parameters", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"UriEnableCache", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      v1[65] = Data != 0;
    RegCloseKey(hKey);
  }
  result = TREE_HASH_TABLE::Initialize((TREE_HASH_TABLE *)v1, 0x7E1u);
  if ( result >= 0 )
    return FILE_CACHE::InitializeMemoryCache(v1, v2);
  return result;
}

```

## disassembly

```asm
0x180003230  mov     qword ptr [rsp-20h+cbData], rcx
0x180003235  push    rbp
0x180003236  push    rbx
0x180003237  push    rsi
0x180003238  push    rdi
0x180003239  mov     rbp, rsp
0x18000323c  sub     rsp, 38h
0x180003240  mov     rbx, cs:?g_pFileCache@@3PEAVFILE_CACHE@@EA; FILE_CACHE * g_pFileCache
0x180003247  lea     rax, [rbp+hKey]
0x18000324b  mov     r9d, 20019h; samDesired
0x180003251  mov     [rsp+38h+phkResult], rax; phkResult
0x180003256  xor     r8d, r8d; ulOptions
0x180003259  mov     [rbp+Type], 0
0x180003260  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\in"...
0x180003267  mov     [rbp+Data], 0
0x18000326e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003275  mov     [rbp+cbData], 0
0x18000327c  mov     edi, 1Eh
0x180003281  mov     [rbp+hKey], 0
0x180003289  call    cs:__imp_RegOpenKeyExW
0x18000328f  lea     esi, [rdi-1Ah]
0x180003292  test    eax, eax
0x180003294  jnz     loc_180003495
0x18000329a  mov     rcx, [rbp+hKey]; hKey
0x18000329e  lea     rax, [rbp+cbData]
0x1800032a2  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800032a7  lea     r9, [rbp+Type]; lpType
0x1800032ab  lea     rax, [rbp+Data]
0x1800032af  mov     [rbp+cbData], esi
0x1800032b2  xor     r8d, r8d; lpReserved
0x1800032b5  mov     [rsp+38h+phkResult], rax; lpData
0x1800032ba  lea     rdx, ValueName; "DisableMemoryCache"
0x1800032c1  call    cs:__imp_RegQueryValueExW
0x1800032c7  test    eax, eax
0x1800032c9  jnz     short loc_1800032D9
0x1800032cb  cmp     [rbp+Type], esi
0x1800032ce  jnz     short loc_1800032D9
0x1800032d0  cmp     [rbp+Data], eax
0x1800032d3  setz    al
0x1800032d6  mov     [rbx+40h], al
0x1800032d9  mov     rcx, [rbp+hKey]; hKey
0x1800032dd  lea     rax, [rbp+cbData]
0x1800032e1  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800032e6  lea     r9, [rbp+Type]; lpType
0x1800032ea  lea     rax, [rbp+Data]
0x1800032ee  mov     [rbp+cbData], esi
0x1800032f1  xor     r8d, r8d; lpReserved
0x1800032f4  mov     [rsp+38h+phkResult], rax; lpData
0x1800032f9  lea     rdx, aMaxcachedfiles; "MaxCachedFileSize"
0x180003300  call    cs:__imp_RegQueryValueExW
0x180003306  test    eax, eax
0x180003308  jnz     short loc_180003316
0x18000330a  cmp     [rbp+Type], esi
0x18000330d  jnz     short loc_180003316
0x18000330f  mov     eax, [rbp+Data]
0x180003312  mov     [rbx+28h], rax
0x180003316  mov     rcx, [rbp+hKey]; hKey
0x18000331a  lea     rax, [rbp+cbData]
0x18000331e  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180003323  lea     r9, [rbp+Type]; lpType
0x180003327  lea     rax, [rbp+Data]
0x18000332b  mov     [rbp+cbData], esi
0x18000332e  xor     r8d, r8d; lpReserved
0x180003331  mov     [rsp+38h+phkResult], rax; lpData
0x180003336  lea     rdx, aMaxcachedfiles_0; "MaxCachedFileSizeInMB"
0x18000333d  call    cs:__imp_RegQueryValueExW
0x180003343  test    eax, eax
0x180003345  jnz     short loc_180003357
0x180003347  cmp     [rbp+Type], esi
0x18000334a  jnz     short loc_180003357
0x18000334c  mov     eax, [rbp+Data]
0x18000334f  shl     rax, 14h
0x180003353  add     [rbx+28h], rax
0x180003357  mov     rcx, [rbp+hKey]; hKey
0x18000335b  lea     rax, [rbp+cbData]
0x18000335f  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180003364  lea     r9, [rbp+Type]; lpType
0x180003368  lea     rax, [rbp+Data]
0x18000336c  mov     [rbp+cbData], esi
0x18000336f  xor     r8d, r8d; lpReserved
0x180003372  mov     [rsp+38h+phkResult], rax; lpData
0x180003377  lea     rdx, aMemcachesize; "MemCacheSize"
0x18000337e  call    cs:__imp_RegQueryValueExW
0x180003384  test    eax, eax
0x180003386  jnz     short loc_180003398
0x180003388  cmp     [rbp+Type], esi
0x18000338b  jnz     short loc_180003398
0x18000338d  mov     eax, [rbp+Data]
0x180003390  shl     rax, 14h
0x180003394  mov     [rbx+30h], rax
0x180003398  mov     rcx, [rbp+hKey]; hKey
0x18000339c  lea     rax, [rbp+cbData]
0x1800033a0  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800033a5  lea     r9, [rbp+Type]; lpType
0x1800033a9  lea     rax, [rbp+Data]
0x1800033ad  mov     [rbp+cbData], esi
0x1800033b0  xor     r8d, r8d; lpReserved
0x1800033b3  mov     [rsp+38h+phkResult], rax; lpData
0x1800033b8  lea     rdx, aMaxopenfiles; "MaxOpenFiles"
0x1800033bf  call    cs:__imp_RegQueryValueExW
0x1800033c5  test    eax, eax
0x1800033c7  jnz     short loc_1800033D4
0x1800033c9  cmp     [rbp+Type], esi
0x1800033cc  jnz     short loc_1800033D4
0x1800033ce  mov     eax, [rbp+Data]
0x1800033d1  mov     [rbx+38h], eax
0x1800033d4  mov     rcx, [rbp+hKey]; hKey
0x1800033d8  lea     rax, [rbp+cbData]
0x1800033dc  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800033e1  lea     r9, [rbp+Type]; lpType
0x1800033e5  lea     rax, [rbp+Data]
0x1800033e9  mov     [rbp+cbData], esi
0x1800033ec  xor     r8d, r8d; lpReserved
0x1800033ef  mov     [rsp+38h+phkResult], rax; lpData
0x1800033f4  lea     rdx, aObjectcachettl; "ObjectCacheTTL"
0x1800033fb  call    cs:__imp_RegQueryValueExW
0x180003401  test    eax, eax
0x180003403  jnz     short loc_18000340C
0x180003405  cmp     [rbp+Type], esi
0x180003408  cmovz   edi, [rbp+Data]
0x18000340c  mov     rcx, [rbp+hKey]; hKey
0x180003410  lea     rax, [rbp+cbData]
0x180003414  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180003419  lea     r9, [rbp+Type]; lpType
0x18000341d  lea     rax, [rbp+Data]
0x180003421  mov     [rbp+cbData], esi
0x180003424  xor     r8d, r8d; lpReserved
0x180003427  mov     [rsp+38h+phkResult], rax; lpData
0x18000342c  lea     rdx, aDodirmonitorin; "DoDirMonitoringForUnc"
0x180003433  call    cs:__imp_RegQueryValueExW
0x180003439  test    eax, eax
0x18000343b  jnz     short loc_18000344B
0x18000343d  cmp     [rbp+Type], esi
0x180003440  jnz     short loc_18000344B
0x180003442  cmp     [rbp+Data], eax
0x180003445  setnz   al
0x180003448  mov     [rbx+42h], al
0x18000344b  mov     rcx, [rbp+hKey]; hKey
0x18000344f  lea     rax, [rbp+cbData]
0x180003453  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180003458  lea     r9, [rbp+Type]; lpType
0x18000345c  lea     rax, [rbp+Data]
0x180003460  mov     [rbp+cbData], esi
0x180003463  xor     r8d, r8d; lpReserved
0x180003466  mov     [rsp+38h+phkResult], rax; lpData
0x18000346b  lea     rdx, aFileattributec; "FileAttributeCheckThreshold"
0x180003472  call    cs:__imp_RegQueryValueExW
0x180003478  test    eax, eax
0x18000347a  jnz     short loc_18000348B
0x18000347c  cmp     [rbp+Type], esi
0x18000347f  jnz     short loc_18000348B
0x180003481  imul    eax, [rbp+Data], 3E8h
0x180003488  mov     [rbx+44h], eax
0x18000348b  mov     rcx, [rbp+hKey]; hKey
0x18000348f  call    cs:__imp_RegCloseKey
0x180003495  lea     rax, [rbp+hKey]
0x180003499  mov     r9d, 20019h; samDesired
0x18000349f  xor     r8d, r8d; ulOptions
0x1800034a2  mov     [rsp+38h+phkResult], rax; phkResult
0x1800034a7  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\ht"...
0x1800034ae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800034b5  call    cs:__imp_RegOpenKeyExW
0x1800034bb  test    eax, eax
0x1800034bd  jnz     short loc_180003508
0x1800034bf  mov     rcx, [rbp+hKey]; hKey
0x1800034c3  lea     rax, [rbp+cbData]
0x1800034c7  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800034cc  lea     r9, [rbp+Type]; lpType
0x1800034d0  lea     rax, [rbp+Data]
0x1800034d4  mov     [rbp+cbData], esi
0x1800034d7  xor     r8d, r8d; lpReserved
0x1800034da  mov     [rsp+38h+phkResult], rax; lpData
0x1800034df  lea     rdx, aUrienablecache; "UriEnableCache"
0x1800034e6  call    cs:__imp_RegQueryValueExW
0x1800034ec  test    eax, eax
0x1800034ee  jnz     short loc_1800034FE
0x1800034f0  cmp     [rbp+Type], esi
0x1800034f3  jnz     short loc_1800034FE
0x1800034f5  cmp     [rbp+Data], eax
0x1800034f8  setnz   al
0x1800034fb  mov     [rbx+41h], al
0x1800034fe  mov     rcx, [rbp+hKey]; hKey
0x180003502  call    cs:__imp_RegCloseKey
0x180003508  mov     edx, 7E1h
0x18000350d  mov     rcx, rbx
0x180003510  call    cs:__imp_?Initialize@TREE_HASH_TABLE@@QEAAJK@Z; TREE_HASH_TABLE::Initialize(ulong)
0x180003516  test    eax, eax
0x180003518  js      short loc_180003524
0x18000351a  mov     edx, edi; unsigned int
0x18000351c  mov     rcx, rbx; Parameter
0x18000351f  call    ?InitializeMemoryCache@FILE_CACHE@@AEAAJK@Z; FILE_CACHE::InitializeMemoryCache(ulong)
0x180003524  add     rsp, 38h
0x180003528  pop     rdi
0x180003529  pop     rsi
0x18000352a  pop     rbx
0x18000352b  pop     rbp
0x18000352c  retn
```
