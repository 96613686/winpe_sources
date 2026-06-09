# DnsGetQueryRetryTimeoutsRegistryHandle

- ea: `0x180079794`
- end: `0x180079932`
- name: `DnsGetQueryRetryTimeoutsRegistryHandle`
- size: `414`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x1800795d0`
- `0x1800968d0`
- `0x180096b20`

## callees

- `0x180001780`
- `0x18003de30`
- `0x18004ec60`
- `0x180071278`
- `0x180079794`
- `0x18008b5f0`
- `0x18008bf98`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800798e1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800798e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800798fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800798fa`

## string_xrefs

- `0x180079893`: `Dnscache`
- `0x18007988c`: `SYSTEM\CurrentControlSet\Services\Dnscache`

## pseudocode

```c
LSTATUS __fastcall DnsGetQueryRetryTimeoutsRegistryHandle(__int64 a1, int a2, HKEY *a3)
{
  int PersistedRegistryLocation; // eax
  _BYTE v8[176]; // [rsp+50h] [rbp-4F8h] BYREF
  WCHAR SubKey[264]; // [rsp+100h] [rbp-448h] BYREF
  wchar_t pszDest[264]; // [rsp+310h] [rbp-238h] BYREF

  memset_0(pszDest, 0, 0x208u);
  memset_0(v8, 0, 0xA2u);
  memset_0(SubKey, 0, 0x208u);
  if ( g_fVelocityDisableInternalExports )
    return 120;
  if ( !a3 || !a1 )
    return 87;
  *a3 = 0;
  if ( !(unsigned int)Dns_GuidToString(a1, v8) )
    return 14;
  if ( StringCbPrintfW(pszDest, 0x208u, L"%s\\%s", L"InterfaceSpecificParameters", v8) < 0 )
    return 1292;
  PersistedRegistryLocation = WxGetPersistedRegistryLocation(
                                (unsigned int)L"Dnscache",
                                (unsigned int)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
                                (unsigned int)pszDest,
                                (unsigned int)SubKey,
                                520);
  if ( PersistedRegistryLocation < 0 )
    return WX_WIN32_FROM_HR((unsigned int)PersistedRegistryLocation);
  if ( a2 )
    return RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, a3, 0);
  return RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, a3);
}

```

## disassembly

```asm
0x180079794  mov     [rsp+arg_8], rbx
0x180079799  push    rsi
0x18007979a  push    rdi
0x18007979b  push    r14
0x18007979d  sub     rsp, 530h
0x1800797a4  mov     rax, cs:__security_cookie
0x1800797ab  xor     rax, rsp
0x1800797ae  mov     [rsp+548h+var_28], rax
0x1800797b6  mov     rbx, r8
0x1800797b9  mov     esi, edx
0x1800797bb  mov     rdi, rcx
0x1800797be  mov     r14d, 208h
0x1800797c4  mov     r8d, r14d; Size
0x1800797c7  lea     rcx, [rsp+548h+pszDest]; void *
0x1800797cf  xor     edx, edx; Val
0x1800797d1  call    memset_0
0x1800797d6  xor     edx, edx; Val
0x1800797d8  lea     rcx, [rsp+548h+var_4F8]; void *
0x1800797dd  mov     r8d, 0A2h; Size
0x1800797e3  call    memset_0
0x1800797e8  mov     r8d, r14d; Size
0x1800797eb  lea     rcx, [rsp+548h+SubKey]; void *
0x1800797f3  xor     edx, edx; Val
0x1800797f5  call    memset_0
0x1800797fa  cmp     cs:g_fVelocityDisableInternalExports, 0
0x180079801  jz      short loc_18007980D
0x180079803  mov     eax, 78h ; 'x'
0x180079808  jmp     loc_18007990D
0x18007980d  test    rbx, rbx
0x180079810  jz      loc_180079908
0x180079816  test    rdi, rdi
0x180079819  jz      loc_180079908
0x18007981f  lea     rdx, [rsp+548h+var_4F8]
0x180079824  mov     qword ptr [rbx], 0
0x18007982b  mov     rcx, rdi
0x18007982e  call    Dns_GuidToString
0x180079833  test    eax, eax
0x180079835  jnz     short loc_180079841
0x180079837  mov     eax, 0Eh
0x18007983c  jmp     loc_18007990D
0x180079841  lea     rax, [rsp+548h+var_4F8]
0x180079846  mov     rdx, r14; cbDest
0x180079849  lea     r9, aInterfacespeci; "InterfaceSpecificParameters"
0x180079850  mov     qword ptr [rsp+548h+dwOptions], rax
0x180079855  lea     r8, aSS_0; "%s\\%s"
0x18007985c  lea     rcx, [rsp+548h+pszDest]; pszDest
0x180079864  call    StringCbPrintfW
0x180079869  test    eax, eax
0x18007986b  jns     short loc_180079877
0x18007986d  mov     eax, 50Ch
0x180079872  jmp     loc_18007990D
0x180079877  lea     r9, [rsp+548h+SubKey]
0x18007987f  mov     [rsp+548h+dwOptions], r14d
0x180079884  lea     r8, [rsp+548h+pszDest]
0x18007988c  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x180079893  lea     rcx, aDnscache_1; "Dnscache"
0x18007989a  call    WxGetPersistedRegistryLocation
0x18007989f  test    eax, eax
0x1800798a1  jns     short loc_1800798AC
0x1800798a3  mov     ecx, eax
0x1800798a5  call    WX_WIN32_FROM_HR
0x1800798aa  jmp     short loc_18007990D
0x1800798ac  xor     r8d, r8d; ulOptions
0x1800798af  lea     rdx, [rsp+548h+SubKey]; lpSubKey
0x1800798b7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800798be  test    esi, esi
0x1800798c0  jz      short loc_1800798EF
0x1800798c2  mov     [rsp+548h+lpdwDisposition], r8; lpdwDisposition
0x1800798c7  xor     r9d, r9d; lpClass
0x1800798ca  mov     [rsp+548h+phkResult], rbx; phkResult
0x1800798cf  mov     [rsp+548h+lpSecurityAttributes], r8; lpSecurityAttributes
0x1800798d4  mov     [rsp+548h+samDesired], 0F003Fh; samDesired
0x1800798dc  mov     [rsp+548h+dwOptions], r8d; dwOptions
0x1800798e1  call    cs:__imp_RegCreateKeyExW
0x1800798e8  nop     dword ptr [rax+rax+00h]
0x1800798ed  jmp     short loc_18007990D
0x1800798ef  mov     r9d, 20019h; samDesired
0x1800798f5  mov     qword ptr [rsp+548h+dwOptions], rbx; phkResult
0x1800798fa  call    cs:__imp_RegOpenKeyExW
0x180079901  nop     dword ptr [rax+rax+00h]
0x180079906  jmp     short loc_18007990D
0x180079908  mov     eax, 57h ; 'W'
0x18007990d  mov     rcx, [rsp+548h+var_28]
0x180079915  xor     rcx, rsp; StackCookie
0x180079918  call    __security_check_cookie
0x18007991d  mov     rbx, [rsp+548h+arg_8]
0x180079925  add     rsp, 530h
0x18007992c  pop     r14
0x18007992e  pop     rdi
0x18007992f  pop     rsi
0x180079930  retn
```
