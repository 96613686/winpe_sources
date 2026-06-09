# RegScanUtil::BeginRegistryIsRedirected(void)

- ea: `0x180052750`
- end: `0x180052837`
- name: `?BeginRegistryIsRedirected@RegScanUtil@@SAXXZ`
- size: `231`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000eaf8`

## callees

- `0x180052750`
- `0x180055880`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180052788`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180052788`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800527e1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800527e1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180052814`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180052814`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005281f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005281f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void RegScanUtil::BeginRegistryIsRedirected(void)
{
  HKEY hKey; // [rsp+50h] [rbp-28h] BYREF
  GUID pguid; // [rsp+58h] [rbp-20h] BYREF

  *(_QWORD *)&pguid.Data2 = *(_QWORD *)&GUID_NULL.Data2;
  pguid.Data1 = 0;
  *(_DWORD *)&pguid.Data4[4] = *(_DWORD *)&GUID_NULL.Data4[4];
  CoCreateGuid(&pguid);
  *(_DWORD *)&RegScanUtil::sm_dwCookie = pguid.Data1;
  hKey = 0;
  if ( !RegCreateKeyExW(HKEY_CLASSES_ROOT, L"REDIRECTED", 0, 0, 1u, 0x2001Bu, 0, &hKey, 0) )
  {
    if ( hKey )
    {
      RegSetValueExW(hKey, L"Cookie", 0, 4u, &RegScanUtil::sm_dwCookie, 4u);
      RegCloseKey(hKey);
    }
  }
}

```

## disassembly

```asm
0x180052750  sub     rsp, 78h
0x180052754  mov     rax, cs:__security_cookie
0x18005275b  xor     rax, rsp
0x18005275e  mov     [rsp+78h+var_10], rax
0x180052763  movsd   xmm0, qword ptr cs:GUID_NULL.Data2
0x18005276b  lea     rcx, [rsp+78h+pguid]; pguid
0x180052770  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x180052776  movsd   qword ptr [rsp+78h+pguid.Data2], xmm0
0x18005277c  mov     [rsp+78h+pguid.Data1], 0
0x180052784  mov     dword ptr [rsp+78h+pguid.Data4+4], eax
0x180052788  call    cs:__imp_CoCreateGuid
0x18005278e  mov     eax, [rsp+78h+pguid.Data1]
0x180052792  lea     rdx, aRedirected; "REDIRECTED"
0x180052799  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x1800527a2  xor     r9d, r9d; lpClass
0x1800527a5  mov     cs:?sm_dwCookie@RegScanUtil@@0KA, eax; ulong RegScanUtil::sm_dwCookie
0x1800527ab  xor     r8d, r8d; Reserved
0x1800527ae  lea     rax, [rsp+78h+hKey]
0x1800527b3  mov     [rsp+78h+hKey], 0
0x1800527bc  mov     [rsp+78h+phkResult], rax; phkResult
0x1800527c1  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800527c8  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800527d1  mov     [rsp+78h+samDesired], 2001Bh; samDesired
0x1800527d9  mov     [rsp+78h+dwOptions], 1; dwOptions
0x1800527e1  call    cs:__imp_RegCreateKeyExW
0x1800527e7  test    eax, eax
0x1800527e9  jnz     short loc_180052825
0x1800527eb  mov     rcx, [rsp+78h+hKey]; hKey
0x1800527f0  test    rcx, rcx
0x1800527f3  jz      short loc_180052825
0x1800527f5  lea     r9d, [rax+4]; dwType
0x1800527f9  xor     r8d, r8d; Reserved
0x1800527fc  lea     rax, ?sm_dwCookie@RegScanUtil@@0KA; ulong RegScanUtil::sm_dwCookie
0x180052803  mov     [rsp+78h+samDesired], r9d; cbData
0x180052808  lea     rdx, ValueName; "Cookie"
0x18005280f  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x180052814  call    cs:__imp_RegSetValueExW
0x18005281a  mov     rcx, [rsp+78h+hKey]; hKey
0x18005281f  call    cs:__imp_RegCloseKey
0x180052825  mov     rcx, [rsp+78h+var_10]
0x18005282a  xor     rcx, rsp; StackCookie
0x18005282d  call    __security_check_cookie
0x180052832  add     rsp, 78h
0x180052836  retn
```
