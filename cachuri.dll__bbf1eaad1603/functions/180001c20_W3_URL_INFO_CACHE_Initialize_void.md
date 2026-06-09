# W3_URL_INFO_CACHE::Initialize(void)

- ea: `0x180001c20`
- end: `0x180001d6a`
- name: `?Initialize@W3_URL_INFO_CACHE@@QEAAJXZ`
- size: `330`
- prototype: `signed int __fastcall(W3_URL_INFO_CACHE *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180001de0`

## callees

- `0x180001c20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001caa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001ce7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001caa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001ce7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001d04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001d04`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001c78`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001c78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d4c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180001d42`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180001d42`
- `iisutil!?Initialize@TREE_HASH_TABLE@@QEAAJK@Z` at `0x180001d12`
- `iisutil!?Initialize@TREE_HASH_TABLE@@QEAAJK@Z` at `0x180001d12`

## string_xrefs

- `0x180001c4f`: `System\CurrentControlSet\Services\inetinfo\Parameters`
- `0x180001c9e`: `ObjectCacheTTL`
- `0x180001ce0`: `MaxUrlSegmentsCached`

## pseudocode

```c
signed int __fastcall W3_URL_INFO_CACHE::Initialize(W3_URL_INFO_CACHE *this)
{
  HANDLE *v1; // rdi
  int v2; // ebx
  signed int result; // eax
  DWORD Type; // [rsp+60h] [rbp+20h] BYREF
  int v5; // [rsp+64h] [rbp+24h]
  unsigned int Data; // [rsp+68h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+38h] BYREF

  v5 = HIDWORD(this);
  v1 = (HANDLE *)g_pUriCache;
  Data = 0;
  Type = 0;
  cbData = 4;
  v2 = 30;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\inetinfo\\Parameters",
          0,
          0x20019u,
          &hKey) )
  {
    if ( !RegQueryValueExW(hKey, L"ObjectCacheTTL", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      v2 = Data;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"MaxUrlSegmentsCached", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      g_dwMaxSegments = Data;
    RegCloseKey(hKey);
  }
  result = TREE_HASH_TABLE::Initialize((TREE_HASH_TABLE *)v1, 0x7E1u);
  if ( result >= 0 )
  {
    if ( CreateTimerQueueTimer(v1 + 5, 0, W3_URL_INFO_CACHE::ScavengerCallback, v1, 1000 * v2, 1000 * v2, 0x10u) )
    {
      return 0;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180001c20  mov     qword ptr [rsp-18h+Type], rcx
0x180001c25  push    rbp
0x180001c26  push    rbx
0x180001c27  push    rdi
0x180001c28  mov     rbp, rsp
0x180001c2b  sub     rsp, 40h
0x180001c2f  mov     rdi, cs:?g_pUriCache@@3PEAVW3_URL_INFO_CACHE@@EA; W3_URL_INFO_CACHE * g_pUriCache
0x180001c36  lea     rax, [rbp+hKey]
0x180001c3a  mov     r9d, 20019h; samDesired
0x180001c40  mov     [rsp+40h+phkResult], rax; phkResult
0x180001c45  xor     r8d, r8d; ulOptions
0x180001c48  mov     [rbp+Data], 0
0x180001c4f  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\in"...
0x180001c56  mov     [rbp+Type], 0
0x180001c5d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180001c64  mov     [rbp+cbData], 4
0x180001c6b  mov     ebx, 1Eh
0x180001c70  mov     [rbp+hKey], 0
0x180001c78  call    cs:__imp_RegOpenKeyExW
0x180001c7e  test    eax, eax
0x180001c80  jnz     loc_180001D0A
0x180001c86  mov     rcx, [rbp+hKey]; hKey
0x180001c8a  lea     rax, [rbp+cbData]
0x180001c8e  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180001c93  lea     r9, [rbp+Type]; lpType
0x180001c97  lea     rax, [rbp+Data]
0x180001c9b  xor     r8d, r8d; lpReserved
0x180001c9e  lea     rdx, ValueName; "ObjectCacheTTL"
0x180001ca5  mov     [rsp+40h+phkResult], rax; lpData
0x180001caa  call    cs:__imp_RegQueryValueExW
0x180001cb0  test    eax, eax
0x180001cb2  jnz     short loc_180001CBC
0x180001cb4  cmp     [rbp+Type], 4
0x180001cb8  cmovz   ebx, [rbp+Data]
0x180001cbc  mov     rcx, [rbp+hKey]; hKey
0x180001cc0  lea     rax, [rbp+cbData]
0x180001cc4  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180001cc9  lea     r9, [rbp+Type]; lpType
0x180001ccd  lea     rax, [rbp+Data]
0x180001cd1  mov     [rbp+cbData], 4
0x180001cd8  xor     r8d, r8d; lpReserved
0x180001cdb  mov     [rsp+40h+phkResult], rax; lpData
0x180001ce0  lea     rdx, aMaxurlsegments; "MaxUrlSegmentsCached"
0x180001ce7  call    cs:__imp_RegQueryValueExW
0x180001ced  test    eax, eax
0x180001cef  jnz     short loc_180001D00
0x180001cf1  cmp     [rbp+Type], 4
0x180001cf5  jnz     short loc_180001D00
0x180001cf7  mov     eax, [rbp+Data]
0x180001cfa  mov     cs:?g_dwMaxSegments@@3KA, eax; ulong g_dwMaxSegments
0x180001d00  mov     rcx, [rbp+hKey]; hKey
0x180001d04  call    cs:__imp_RegCloseKey
0x180001d0a  mov     edx, 7E1h
0x180001d0f  mov     rcx, rdi
0x180001d12  call    cs:__imp_?Initialize@TREE_HASH_TABLE@@QEAAJK@Z; TREE_HASH_TABLE::Initialize(ulong)
0x180001d18  test    eax, eax
0x180001d1a  js      short loc_180001D62
0x180001d1c  imul    eax, ebx, 3E8h
0x180001d22  lea     rcx, [rdi+28h]; phNewTimer
0x180001d26  mov     [rsp+40h+Flags], 10h; Flags
0x180001d2e  lea     r8, ?ScavengerCallback@W3_URL_INFO_CACHE@@CAXPEAXE@Z; Callback
0x180001d35  mov     r9, rdi; Parameter
0x180001d38  xor     edx, edx; TimerQueue
0x180001d3a  mov     dword ptr [rsp+40h+lpcbData], eax; Period
0x180001d3e  mov     dword ptr [rsp+40h+phkResult], eax; DueTime
0x180001d42  call    cs:__imp_CreateTimerQueueTimer
0x180001d48  test    eax, eax
0x180001d4a  jnz     short loc_180001D60
0x180001d4c  call    cs:__imp_GetLastError
0x180001d52  test    eax, eax
0x180001d54  jle     short loc_180001D62
0x180001d56  movzx   eax, ax
0x180001d59  or      eax, 80070000h
0x180001d5e  jmp     short loc_180001D62
0x180001d60  xor     eax, eax
0x180001d62  add     rsp, 40h
0x180001d66  pop     rdi
0x180001d67  pop     rbx
0x180001d68  pop     rbp
0x180001d69  retn
```
