# W3_SERVER::W3_SERVER(int)

- ea: `0x18001a414`
- end: `0x18001a79f`
- name: `??0W3_SERVER@@QEAA@H@Z`
- size: `907`
- prototype: `W3_SERVER *__fastcall(W3_SERVER *__hidden this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180030bac`

## callees

- `0x180019224`
- `0x18001a200`
- `0x18001a414`
- `0x18003439a`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a760`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a760`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a6c5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a6c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a705`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a744`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a705`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a744`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18001a77d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18001a77d`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x18001a466`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x18001a466`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18001a478`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18001a676`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18001a478`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18001a676`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001a4cb`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001a4d8`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001a4e5`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001a4cb`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001a4d8`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001a4e5`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18001a557`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18001a557`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18001a537`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18001a537`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x18001a5bd`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x18001a5bd`
- `iisutil!??0TREE_HASH_TABLE@@QEAA@H@Z` at `0x18001a5cf`
- `iisutil!??0TREE_HASH_TABLE@@QEAA@H@Z` at `0x18001a5eb`
- `iisutil!??0TREE_HASH_TABLE@@QEAA@H@Z` at `0x18001a5cf`
- `iisutil!??0TREE_HASH_TABLE@@QEAA@H@Z` at `0x18001a5eb`

## string_xrefs

- `0x18001a683`: `System\CurrentControlSet\Services\W3SVC\Parameters`
- `0x18001a73d`: `ConfigPollMilliSeconds`

## pseudocode

```c
W3_SERVER *__fastcall W3_SERVER::W3_SERVER(W3_SERVER *this, int a2)
{
  const unsigned __int16 *v3; // rdx
  _SYSTEM_INFO SystemInfo; // [rsp+50h] [rbp-30h] BYREF
  int Data; // [rsp+B0h] [rbp+30h] BYREF
  DWORD Type; // [rsp+B8h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+C0h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+C8h] [rbp+48h] BYREF

  *((_QWORD *)this + 2) = 1448235863;
  *(_QWORD *)this = &W3_SERVER::`vftable'{for `IHttpServer3'};
  v3 = L"HostableWebCore";
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 1) = &W3_SERVER::`vftable'{for `IHttpTraceContext'};
  if ( !a2 )
    v3 = L"W3SVC-WP";
  EVENT_LOG::EVENT_LOG((W3_SERVER *)((char *)this + 28), v3);
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 10) = 0;
  CReaderWriterLock3::CReaderWriterLock3((W3_SERVER *)((char *)this + 44));
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = 0;
  *((_QWORD *)this + 9) = &W3_PERF_COUNTERS::`vftable';
  memset_0((char *)this + 80, 0, 0x88u);
  memset_0((char *)this + 216, 0, 0x88u);
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 45) = 0;
  STRU::STRU((W3_SERVER *)((char *)this + 368));
  STRU::STRU((W3_SERVER *)((char *)this + 424));
  STRU::STRU((W3_SERVER *)((char *)this + 480));
  *((_DWORD *)this + 134) = 0;
  *((_DWORD *)this + 135) = 64;
  *((_WORD *)this + 272) = 0;
  *((_DWORD *)this + 137) = a2;
  *((_QWORD *)this + 69) = 0;
  memset_0((char *)this + 560, 0, 0x1B8u);
  CACHED_MODULE_LIST::CACHED_MODULE_LIST((W3_SERVER *)((char *)this + 560));
  MULTISZ::MULTISZ((W3_SERVER *)((char *)this + 1000));
  memset_0((char *)this + 1056, 0, 0xB8u);
  BUFFER::BUFFER((W3_SERVER *)((char *)this + 1056));
  W3_SITE_TABLE_BY_ID::W3_SITE_TABLE_BY_ID((W3_SERVER *)((char *)this + 1240));
  CLKRHashTable::CLKRHashTable(
    (W3_SERVER *)((char *)this + 1312),
    "W3_SITE_TABLE_BY_NAME",
    (unsigned __int64 (*)(const void *))CTypedHashTable<W3_SITE_TABLE_BY_NAME,W3_SITE,unsigned short const *,CLKRHashTable>::_ExtractKey,
    (unsigned int (*)(unsigned __int64))CTypedHashTable<W3_SITE_TABLE_BY_NAME,W3_SITE,unsigned short const *,CLKRHashTable>::_CalcKeyHash,
    (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<W3_SITE_TABLE_BY_NAME,W3_SITE,unsigned short const *,CLKRHashTable>::_EqualKeys,
    (void (*)(const void *, int))CTypedHashTable<W3_SITE_TABLE_BY_NAME,W3_SITE,unsigned short const *,CLKRHashTable>::_AddRefRecord,
    4.0,
    1u,
    0,
    0);
  TREE_HASH_TABLE::TREE_HASH_TABLE((W3_SERVER *)((char *)this + 1384), 1);
  *((_QWORD *)this + 173) = &W3_APPLICATION_TABLE::`vftable';
  TREE_HASH_TABLE::TREE_HASH_TABLE((W3_SERVER *)((char *)this + 1424), 1);
  *((_QWORD *)this + 178) = &W3_METADATA_TABLE::`vftable';
  *((_QWORD *)this + 183) = 0;
  *((_QWORD *)this + 184) = 4096;
  *((_QWORD *)this + 185) = 0;
  *((_QWORD *)this + 186) = 0;
  *((_QWORD *)this + 187) = 0;
  *((_QWORD *)this + 188) = 0;
  *((_QWORD *)this + 189) = 0;
  *((_QWORD *)this + 190) = 0;
  *((_QWORD *)this + 191) = 0;
  *((_QWORD *)this + 192) = 0;
  *((_QWORD *)this + 193) = 0;
  *((_QWORD *)this + 194) = 0;
  *((_QWORD *)this + 195) = 0;
  *((_DWORD *)this + 392) = 0;
  *((_QWORD *)this + 197) = 0;
  *((_DWORD *)this + 396) = 0;
  CReaderWriterLock3::CReaderWriterLock3((W3_SERVER *)((char *)this + 1588));
  *((_QWORD *)this + 200) = 0;
  *((_DWORD *)this + 402) = 0;
  *(_QWORD *)((char *)this + 1612) = 0;
  *((_QWORD *)this + 211) = 0;
  *((_BYTE *)this + 1620) = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\W3SVC\\Parameters", 0, 0x20019u, &hKey) )
  {
    Type = 0;
    Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"DirMonBufferSize", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      *((_DWORD *)this + 368) = Data;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"ConfigPollMilliSeconds", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      *((_DWORD *)this + 369) = Data;
    RegCloseKey(hKey);
    hKey = 0;
  }
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  *((_WORD *)this + 272) = SystemInfo.wProcessorArchitecture;
  return this;
}

```

## disassembly

```asm
0x18001a414  push    rbp
0x18001a416  push    rbx
0x18001a417  push    rsi
0x18001a418  push    rdi
0x18001a419  push    r15
0x18001a41b  mov     rbp, rsp
0x18001a41e  sub     rsp, 80h
0x18001a425  mov     edi, edx
0x18001a427  mov     qword ptr [rcx+10h], 56525357h
0x18001a42f  lea     rax, ??_7W3_SERVER@@6BIHttpServer3@@@; const W3_SERVER::`vftable'{for `IHttpServer3'}
0x18001a436  xor     r15d, r15d
0x18001a439  mov     [rcx], rax
0x18001a43c  lea     rdx, aHostablewebcor; "HostableWebCore"
0x18001a443  lea     rax, ??_7W3_SERVER@@6BIHttpTraceContext@@@; const W3_SERVER::`vftable'{for `IHttpTraceContext'}
0x18001a44a  mov     [rcx+18h], r15d
0x18001a44e  mov     [rcx+8], rax
0x18001a452  mov     rsi, rcx
0x18001a455  lea     rax, aW3svcWp; "W3SVC-WP"
0x18001a45c  test    edi, edi
0x18001a45e  cmovz   rdx, rax
0x18001a462  add     rcx, 1Ch
0x18001a466  call    cs:__imp_??0EVENT_LOG@@QEAA@PEBG@Z; EVENT_LOG::EVENT_LOG(ushort const *)
0x18001a46c  lea     rcx, [rsi+2Ch]
0x18001a470  mov     [rsi+20h], r15
0x18001a474  mov     [rsi+28h], r15d
0x18001a478  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x18001a47e  lea     rax, ??_7W3_PERF_COUNTERS@@6B@; const W3_PERF_COUNTERS::`vftable'
0x18001a485  mov     [rsi+38h], r15
0x18001a489  mov     [rsi+40h], r15d
0x18001a48d  lea     rcx, [rsi+50h]; void *
0x18001a491  xor     edx, edx; Val
0x18001a493  mov     [rsi+48h], rax
0x18001a497  mov     r8d, 88h; Size
0x18001a49d  call    memset_0
0x18001a4a2  lea     rcx, [rsi+0D8h]; void *
0x18001a4a9  xor     edx, edx; Val
0x18001a4ab  mov     r8d, 88h; Size
0x18001a4b1  call    memset_0
0x18001a4b6  lea     rcx, [rsi+170h]
0x18001a4bd  mov     [rsi+160h], r15
0x18001a4c4  mov     [rsi+168h], r15
0x18001a4cb  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001a4d1  lea     rcx, [rsi+1A8h]
0x18001a4d8  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001a4de  lea     rcx, [rsi+1E0h]
0x18001a4e5  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001a4eb  lea     rbx, [rsi+230h]
0x18001a4f2  mov     [rsi+218h], r15d
0x18001a4f9  mov     rcx, rbx; void *
0x18001a4fc  mov     dword ptr [rsi+21Ch], 40h ; '@'
0x18001a506  xor     edx, edx; Val
0x18001a508  mov     [rsi+220h], r15w
0x18001a510  mov     r8d, 1B8h; Size
0x18001a516  mov     [rsi+224h], edi
0x18001a51c  mov     [rsi+228h], r15
0x18001a523  call    memset_0
0x18001a528  mov     rcx, rbx; this
0x18001a52b  call    ??0CACHED_MODULE_LIST@@QEAA@XZ; CACHED_MODULE_LIST::CACHED_MODULE_LIST(void)
0x18001a530  lea     rcx, [rsi+3E8h]
0x18001a537  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18001a53d  lea     rbx, [rsi+420h]
0x18001a544  xor     edx, edx; Val
0x18001a546  mov     rcx, rbx; void *
0x18001a549  mov     r8d, 0B8h; Size
0x18001a54f  call    memset_0
0x18001a554  mov     rcx, rbx
0x18001a557  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18001a55d  lea     rcx, [rsi+4D8h]; this
0x18001a564  call    ??0W3_SITE_TABLE_BY_ID@@QEAA@XZ; W3_SITE_TABLE_BY_ID::W3_SITE_TABLE_BY_ID(void)
0x18001a569  movsd   xmm0, cs:__real@4010000000000000
0x18001a571  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VW3_SITE_TABLE_BY_NAME@@VW3_SITE@@PEBGVCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<W3_SITE_TABLE_BY_NAME,W3_SITE,ushort const *,CLKRHashTable>::_AddRefRecord(void const *,int)
0x18001a578  mov     [rsp+80h+var_38], r15b
0x18001a57d  lea     edi, [r15+1]
0x18001a581  mov     [rsp+80h+var_40], r15d
0x18001a586  lea     rcx, [rsi+520h]
0x18001a58d  mov     [rsp+80h+var_48], edi
0x18001a591  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VW3_SITE_TABLE_BY_NAME@@VW3_SITE@@PEBGVCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<W3_SITE_TABLE_BY_NAME,W3_SITE,ushort const *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x18001a598  movsd   [rsp+80h+var_50], xmm0
0x18001a59e  lea     r8, ?_ExtractKey@?$CTypedHashTable@VW3_SITE_TABLE_BY_NAME@@VW3_SITE@@PEBGVCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<W3_SITE_TABLE_BY_NAME,W3_SITE,ushort const *,CLKRHashTable>::_ExtractKey(void const *)
0x18001a5a5  mov     [rsp+80h+lpcbData], rax
0x18001a5aa  lea     rdx, aW3SiteTableByN; "W3_SITE_TABLE_BY_NAME"
0x18001a5b1  lea     rax, ?_EqualKeys@?$CTypedHashTable@VW3_SITE_TABLE_BY_NAME@@VW3_SITE@@PEBGVCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<W3_SITE_TABLE_BY_NAME,W3_SITE,ushort const *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x18001a5b8  mov     [rsp+80h+phkResult], rax
0x18001a5bd  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x18001a5c3  lea     rbx, [rsi+568h]
0x18001a5ca  mov     edx, edi
0x18001a5cc  mov     rcx, rbx
0x18001a5cf  call    cs:__imp_??0TREE_HASH_TABLE@@QEAA@H@Z; TREE_HASH_TABLE::TREE_HASH_TABLE(int)
0x18001a5d5  lea     rax, ??_7W3_APPLICATION_TABLE@@6B@; const W3_APPLICATION_TABLE::`vftable'
0x18001a5dc  mov     edx, edi
0x18001a5de  mov     [rbx], rax
0x18001a5e1  lea     rbx, [rsi+590h]
0x18001a5e8  mov     rcx, rbx
0x18001a5eb  call    cs:__imp_??0TREE_HASH_TABLE@@QEAA@H@Z; TREE_HASH_TABLE::TREE_HASH_TABLE(int)
0x18001a5f1  lea     rax, ??_7W3_METADATA_TABLE@@6B@; const W3_METADATA_TABLE::`vftable'
0x18001a5f8  mov     [rbx], rax
0x18001a5fb  lea     rcx, [rsi+634h]
0x18001a602  mov     [rsi+5B8h], r15
0x18001a609  mov     qword ptr [rsi+5C0h], 1000h
0x18001a614  mov     [rsi+5C8h], r15
0x18001a61b  mov     [rsi+5D0h], r15
0x18001a622  mov     [rsi+5D8h], r15
0x18001a629  mov     [rsi+5E0h], r15
0x18001a630  mov     [rsi+5E8h], r15
0x18001a637  mov     [rsi+5F0h], r15
0x18001a63e  mov     [rsi+5F8h], r15
0x18001a645  mov     [rsi+600h], r15
0x18001a64c  mov     [rsi+608h], r15
0x18001a653  mov     [rsi+610h], r15
0x18001a65a  mov     [rsi+618h], r15
0x18001a661  mov     [rsi+620h], r15d
0x18001a668  mov     [rsi+628h], r15
0x18001a66f  mov     [rsi+630h], r15d
0x18001a676  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x18001a67c  mov     [rsi+640h], r15
0x18001a683  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\W3"...
0x18001a68a  xor     eax, eax
0x18001a68c  mov     [rsi+648h], r15d
0x18001a693  mov     [rsi+64Ch], rax
0x18001a69a  mov     r9d, 20019h; samDesired
0x18001a6a0  lea     rax, [rbp+hKey]
0x18001a6a4  mov     [rsi+698h], r15
0x18001a6ab  xor     r8d, r8d; ulOptions
0x18001a6ae  mov     [rsp+80h+phkResult], rax; phkResult
0x18001a6b3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a6ba  mov     [rsi+654h], r15b
0x18001a6c1  mov     [rbp+hKey], r15
0x18001a6c5  call    cs:__imp_RegOpenKeyExW
0x18001a6cb  test    eax, eax
0x18001a6cd  jnz     loc_18001A76A
0x18001a6d3  mov     rcx, [rbp+hKey]; hKey
0x18001a6d7  lea     rax, [rbp+cbData]
0x18001a6db  mov     [rsp+80h+lpcbData], rax; lpcbData
0x18001a6e0  lea     ebx, [rdi+3]
0x18001a6e3  lea     rax, [rbp+Data]
0x18001a6e7  mov     [rbp+Type], r15d
0x18001a6eb  lea     r9, [rbp+Type]; lpType
0x18001a6ef  mov     [rsp+80h+phkResult], rax; lpData
0x18001a6f4  xor     r8d, r8d; lpReserved
0x18001a6f7  mov     [rbp+Data], r15d
0x18001a6fb  lea     rdx, ValueName; "DirMonBufferSize"
0x18001a702  mov     [rbp+cbData], ebx
0x18001a705  call    cs:__imp_RegQueryValueExW
0x18001a70b  test    eax, eax
0x18001a70d  jnz     short loc_18001A71D
0x18001a70f  cmp     [rbp+Type], ebx
0x18001a712  jnz     short loc_18001A71D
0x18001a714  mov     eax, [rbp+Data]
0x18001a717  mov     [rsi+5C0h], eax
0x18001a71d  mov     rcx, [rbp+hKey]; hKey
0x18001a721  lea     rax, [rbp+cbData]
0x18001a725  mov     [rsp+80h+lpcbData], rax; lpcbData
0x18001a72a  lea     r9, [rbp+Type]; lpType
0x18001a72e  lea     rax, [rbp+Data]
0x18001a732  mov     [rbp+cbData], ebx
0x18001a735  xor     r8d, r8d; lpReserved
0x18001a738  mov     [rsp+80h+phkResult], rax; lpData
0x18001a73d  lea     rdx, aConfigpollmill; "ConfigPollMilliSeconds"
0x18001a744  call    cs:__imp_RegQueryValueExW
0x18001a74a  test    eax, eax
0x18001a74c  jnz     short loc_18001A75C
0x18001a74e  cmp     [rbp+Type], ebx
0x18001a751  jnz     short loc_18001A75C
0x18001a753  mov     eax, [rbp+Data]
0x18001a756  mov     [rsi+5C4h], eax
0x18001a75c  mov     rcx, [rbp+hKey]; hKey
0x18001a760  call    cs:__imp_RegCloseKey
0x18001a766  mov     [rbp+hKey], r15
0x18001a76a  xorps   xmm0, xmm0
0x18001a76d  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x18001a771  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x18001a775  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18001a779  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x18001a77d  call    cs:__imp_GetSystemInfo
0x18001a783  movzx   eax, word ptr [rbp+SystemInfo]
0x18001a787  mov     [rsi+220h], ax
0x18001a78e  mov     rax, rsi
0x18001a791  add     rsp, 80h
0x18001a798  pop     r15
0x18001a79a  pop     rdi
0x18001a79b  pop     rsi
0x18001a79c  pop     rbx
0x18001a79d  pop     rbp
0x18001a79e  retn
```
