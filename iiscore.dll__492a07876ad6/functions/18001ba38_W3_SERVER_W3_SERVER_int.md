# W3_SERVER::W3_SERVER(int)

- ea: `0x18001ba38`
- end: `0x18001be24`
- name: `??0W3_SERVER@@QEAA@H@Z`
- size: `1004`
- prototype: `W3_SERVER *__fastcall(W3_SERVER *__hidden this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800338ac`

## callees

- `0x18001a7e4`
- `0x18001b7f0`
- `0x18001ba38`
- `0x18003773a`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bdd8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bdd8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bd2b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bd2b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001bd71`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001bdb6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001bd71`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001bdb6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18001bdfb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18001bdfb`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x18001ba8a`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x18001ba8a`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18001baa2`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18001bcd6`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18001baa2`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18001bcd6`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001bafb`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001bb0e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001bb21`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001bafb`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001bb0e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001bb21`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18001bb9f`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18001bb9f`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18001bb79`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18001bb79`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x18001bc0b`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x18001bc0b`
- `iisutil!??0TREE_HASH_TABLE@@QEAA@H@Z` at `0x18001bc23`
- `iisutil!??0TREE_HASH_TABLE@@QEAA@H@Z` at `0x18001bc45`
- `iisutil!??0TREE_HASH_TABLE@@QEAA@H@Z` at `0x18001bc23`
- `iisutil!??0TREE_HASH_TABLE@@QEAA@H@Z` at `0x18001bc45`

## string_xrefs

- `0x18001bce9`: `System\CurrentControlSet\Services\W3SVC\Parameters`
- `0x18001bdaf`: `ConfigPollMilliSeconds`

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
0x18001ba38  push    rbp
0x18001ba3a  push    rbx
0x18001ba3b  push    rsi
0x18001ba3c  push    rdi
0x18001ba3d  push    r15
0x18001ba3f  mov     rbp, rsp
0x18001ba42  sub     rsp, 80h
0x18001ba49  mov     edi, edx
0x18001ba4b  mov     qword ptr [rcx+10h], 56525357h
0x18001ba53  lea     rax, ??_7W3_SERVER@@6BIHttpServer3@@@; const W3_SERVER::`vftable'{for `IHttpServer3'}
0x18001ba5a  xor     r15d, r15d
0x18001ba5d  mov     [rcx], rax
0x18001ba60  lea     rdx, aHostablewebcor; "HostableWebCore"
0x18001ba67  lea     rax, ??_7W3_SERVER@@6BIHttpTraceContext@@@; const W3_SERVER::`vftable'{for `IHttpTraceContext'}
0x18001ba6e  mov     [rcx+18h], r15d
0x18001ba72  mov     [rcx+8], rax
0x18001ba76  mov     rsi, rcx
0x18001ba79  lea     rax, aW3svcWp; "W3SVC-WP"
0x18001ba80  test    edi, edi
0x18001ba82  cmovz   rdx, rax
0x18001ba86  add     rcx, 1Ch
0x18001ba8a  call    cs:__imp_??0EVENT_LOG@@QEAA@PEBG@Z; EVENT_LOG::EVENT_LOG(ushort const *)
0x18001ba91  nop     dword ptr [rax+rax+00h]
0x18001ba96  lea     rcx, [rsi+2Ch]
0x18001ba9a  mov     [rsi+20h], r15
0x18001ba9e  mov     [rsi+28h], r15d
0x18001baa2  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x18001baa9  nop     dword ptr [rax+rax+00h]
0x18001baae  lea     rax, ??_7W3_PERF_COUNTERS@@6B@; const W3_PERF_COUNTERS::`vftable'
0x18001bab5  mov     [rsi+38h], r15
0x18001bab9  mov     [rsi+40h], r15d
0x18001babd  lea     rcx, [rsi+50h]; void *
0x18001bac1  xor     edx, edx; Val
0x18001bac3  mov     [rsi+48h], rax
0x18001bac7  mov     r8d, 88h; Size
0x18001bacd  call    memset_0
0x18001bad2  lea     rcx, [rsi+0D8h]; void *
0x18001bad9  xor     edx, edx; Val
0x18001badb  mov     r8d, 88h; Size
0x18001bae1  call    memset_0
0x18001bae6  lea     rcx, [rsi+170h]
0x18001baed  mov     [rsi+160h], r15
0x18001baf4  mov     [rsi+168h], r15
0x18001bafb  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001bb02  nop     dword ptr [rax+rax+00h]
0x18001bb07  lea     rcx, [rsi+1A8h]
0x18001bb0e  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001bb15  nop     dword ptr [rax+rax+00h]
0x18001bb1a  lea     rcx, [rsi+1E0h]
0x18001bb21  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001bb28  nop     dword ptr [rax+rax+00h]
0x18001bb2d  lea     rbx, [rsi+230h]
0x18001bb34  mov     [rsi+218h], r15d
0x18001bb3b  mov     rcx, rbx; void *
0x18001bb3e  mov     dword ptr [rsi+21Ch], 40h ; '@'
0x18001bb48  xor     edx, edx; Val
0x18001bb4a  mov     [rsi+220h], r15w
0x18001bb52  mov     r8d, 1B8h; Size
0x18001bb58  mov     [rsi+224h], edi
0x18001bb5e  mov     [rsi+228h], r15
0x18001bb65  call    memset_0
0x18001bb6a  mov     rcx, rbx; this
0x18001bb6d  call    ??0CACHED_MODULE_LIST@@QEAA@XZ; CACHED_MODULE_LIST::CACHED_MODULE_LIST(void)
0x18001bb72  lea     rcx, [rsi+3E8h]
0x18001bb79  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18001bb80  nop     dword ptr [rax+rax+00h]
0x18001bb85  lea     rbx, [rsi+420h]
0x18001bb8c  xor     edx, edx; Val
0x18001bb8e  mov     rcx, rbx; void *
0x18001bb91  mov     r8d, 0B8h; Size
0x18001bb97  call    memset_0
0x18001bb9c  mov     rcx, rbx
0x18001bb9f  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18001bba6  nop     dword ptr [rax+rax+00h]
0x18001bbab  lea     rcx, [rsi+4D8h]; this
0x18001bbb2  call    ??0W3_SITE_TABLE_BY_ID@@QEAA@XZ; W3_SITE_TABLE_BY_ID::W3_SITE_TABLE_BY_ID(void)
0x18001bbb7  movsd   xmm0, cs:__real@4010000000000000
0x18001bbbf  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VW3_SITE_TABLE_BY_NAME@@VW3_SITE@@PEBGVCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<W3_SITE_TABLE_BY_NAME,W3_SITE,ushort const *,CLKRHashTable>::_AddRefRecord(void const *,int)
0x18001bbc6  mov     [rsp+80h+var_38], r15b
0x18001bbcb  lea     edi, [r15+1]
0x18001bbcf  mov     [rsp+80h+var_40], r15d
0x18001bbd4  lea     rcx, [rsi+520h]
0x18001bbdb  mov     [rsp+80h+var_48], edi
0x18001bbdf  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VW3_SITE_TABLE_BY_NAME@@VW3_SITE@@PEBGVCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<W3_SITE_TABLE_BY_NAME,W3_SITE,ushort const *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x18001bbe6  movsd   [rsp+80h+var_50], xmm0
0x18001bbec  lea     r8, ?_ExtractKey@?$CTypedHashTable@VW3_SITE_TABLE_BY_NAME@@VW3_SITE@@PEBGVCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<W3_SITE_TABLE_BY_NAME,W3_SITE,ushort const *,CLKRHashTable>::_ExtractKey(void const *)
0x18001bbf3  mov     [rsp+80h+lpcbData], rax
0x18001bbf8  lea     rdx, aW3SiteTableByN; "W3_SITE_TABLE_BY_NAME"
0x18001bbff  lea     rax, ?_EqualKeys@?$CTypedHashTable@VW3_SITE_TABLE_BY_NAME@@VW3_SITE@@PEBGVCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<W3_SITE_TABLE_BY_NAME,W3_SITE,ushort const *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x18001bc06  mov     [rsp+80h+phkResult], rax
0x18001bc0b  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x18001bc12  nop     dword ptr [rax+rax+00h]
0x18001bc17  lea     rbx, [rsi+568h]
0x18001bc1e  mov     edx, edi
0x18001bc20  mov     rcx, rbx
0x18001bc23  call    cs:__imp_??0TREE_HASH_TABLE@@QEAA@H@Z; TREE_HASH_TABLE::TREE_HASH_TABLE(int)
0x18001bc2a  nop     dword ptr [rax+rax+00h]
0x18001bc2f  lea     rax, ??_7W3_APPLICATION_TABLE@@6B@; const W3_APPLICATION_TABLE::`vftable'
0x18001bc36  mov     edx, edi
0x18001bc38  mov     [rbx], rax
0x18001bc3b  lea     rbx, [rsi+590h]
0x18001bc42  mov     rcx, rbx
0x18001bc45  call    cs:__imp_??0TREE_HASH_TABLE@@QEAA@H@Z; TREE_HASH_TABLE::TREE_HASH_TABLE(int)
0x18001bc4c  nop     dword ptr [rax+rax+00h]
0x18001bc51  lea     rax, ??_7W3_METADATA_TABLE@@6B@; const W3_METADATA_TABLE::`vftable'
0x18001bc58  mov     [rbx], rax
0x18001bc5b  lea     rcx, [rsi+634h]
0x18001bc62  mov     [rsi+5B8h], r15
0x18001bc69  mov     qword ptr [rsi+5C0h], 1000h
0x18001bc74  mov     [rsi+5C8h], r15
0x18001bc7b  mov     [rsi+5D0h], r15
0x18001bc82  mov     [rsi+5D8h], r15
0x18001bc89  mov     [rsi+5E0h], r15
0x18001bc90  mov     [rsi+5E8h], r15
0x18001bc97  mov     [rsi+5F0h], r15
0x18001bc9e  mov     [rsi+5F8h], r15
0x18001bca5  mov     [rsi+600h], r15
0x18001bcac  mov     [rsi+608h], r15
0x18001bcb3  mov     [rsi+610h], r15
0x18001bcba  mov     [rsi+618h], r15
0x18001bcc1  mov     [rsi+620h], r15d
0x18001bcc8  mov     [rsi+628h], r15
0x18001bccf  mov     [rsi+630h], r15d
0x18001bcd6  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x18001bcdd  nop     dword ptr [rax+rax+00h]
0x18001bce2  mov     [rsi+640h], r15
0x18001bce9  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\W3"...
0x18001bcf0  xor     eax, eax
0x18001bcf2  mov     [rsi+648h], r15d
0x18001bcf9  mov     [rsi+64Ch], rax
0x18001bd00  mov     r9d, 20019h; samDesired
0x18001bd06  lea     rax, [rbp+hKey]
0x18001bd0a  mov     [rsi+698h], r15
0x18001bd11  xor     r8d, r8d; ulOptions
0x18001bd14  mov     [rsp+80h+phkResult], rax; phkResult
0x18001bd19  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001bd20  mov     [rsi+654h], r15b
0x18001bd27  mov     [rbp+hKey], r15
0x18001bd2b  call    cs:__imp_RegOpenKeyExW
0x18001bd32  nop     dword ptr [rax+rax+00h]
0x18001bd37  test    eax, eax
0x18001bd39  jnz     loc_18001BDE8
0x18001bd3f  mov     rcx, [rbp+hKey]; hKey
0x18001bd43  lea     rax, [rbp+cbData]
0x18001bd47  mov     [rsp+80h+lpcbData], rax; lpcbData
0x18001bd4c  lea     ebx, [rdi+3]
0x18001bd4f  lea     rax, [rbp+Data]
0x18001bd53  mov     [rbp+Type], r15d
0x18001bd57  lea     r9, [rbp+Type]; lpType
0x18001bd5b  mov     [rsp+80h+phkResult], rax; lpData
0x18001bd60  xor     r8d, r8d; lpReserved
0x18001bd63  mov     [rbp+Data], r15d
0x18001bd67  lea     rdx, ValueName; "DirMonBufferSize"
0x18001bd6e  mov     [rbp+cbData], ebx
0x18001bd71  call    cs:__imp_RegQueryValueExW
0x18001bd78  nop     dword ptr [rax+rax+00h]
0x18001bd7d  test    eax, eax
0x18001bd7f  jnz     short loc_18001BD8F
0x18001bd81  cmp     [rbp+Type], ebx
0x18001bd84  jnz     short loc_18001BD8F
0x18001bd86  mov     eax, [rbp+Data]
0x18001bd89  mov     [rsi+5C0h], eax
0x18001bd8f  mov     rcx, [rbp+hKey]; hKey
0x18001bd93  lea     rax, [rbp+cbData]
0x18001bd97  mov     [rsp+80h+lpcbData], rax; lpcbData
0x18001bd9c  lea     r9, [rbp+Type]; lpType
0x18001bda0  lea     rax, [rbp+Data]
0x18001bda4  mov     [rbp+cbData], ebx
0x18001bda7  xor     r8d, r8d; lpReserved
0x18001bdaa  mov     [rsp+80h+phkResult], rax; lpData
0x18001bdaf  lea     rdx, aConfigpollmill; "ConfigPollMilliSeconds"
0x18001bdb6  call    cs:__imp_RegQueryValueExW
0x18001bdbd  nop     dword ptr [rax+rax+00h]
0x18001bdc2  test    eax, eax
0x18001bdc4  jnz     short loc_18001BDD4
0x18001bdc6  cmp     [rbp+Type], ebx
0x18001bdc9  jnz     short loc_18001BDD4
0x18001bdcb  mov     eax, [rbp+Data]
0x18001bdce  mov     [rsi+5C4h], eax
0x18001bdd4  mov     rcx, [rbp+hKey]; hKey
0x18001bdd8  call    cs:__imp_RegCloseKey
0x18001bddf  nop     dword ptr [rax+rax+00h]
0x18001bde4  mov     [rbp+hKey], r15
0x18001bde8  xorps   xmm0, xmm0
0x18001bdeb  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x18001bdef  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x18001bdf3  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18001bdf7  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x18001bdfb  call    cs:__imp_GetSystemInfo
0x18001be02  nop     dword ptr [rax+rax+00h]
0x18001be07  movzx   eax, word ptr [rbp+SystemInfo]
0x18001be0b  mov     [rsi+220h], ax
0x18001be12  mov     rax, rsi
0x18001be15  add     rsp, 80h
0x18001be1c  pop     r15
0x18001be1e  pop     rdi
0x18001be1f  pop     rsi
0x18001be20  pop     rbx
0x18001be21  pop     rbp
0x18001be22  retn
```
