# DfsRegistryRootFolder::CheckNamespaceDelegation(void)

- ea: `0x140020be8`
- end: `0x140020cef`
- name: `?CheckNamespaceDelegation@DfsRegistryRootFolder@@QEAAXXZ`
- size: `263`
- prototype: `void __fastcall(DfsRegistryRootFolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140021460`

## callees

- `0x140005f20`
- `0x140020be8`
- `0x140057f64`
- `0x140059f0c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x140020c84`
- `msvcrt!_wcsicmp` at `0x140020c84`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140020c5f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140020c5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140020ca4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140020ca4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140020cb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140020cce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140020cb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140020cce`

## pseudocode

```c
void __fastcall DfsRegistryRootFolder::CheckNamespaceDelegation(DfsRegistryRootFolder *this)
{
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  int v3; // [rsp+38h] [rbp-8h]
  HKEY phkResult; // [rsp+58h] [rbp+18h] BYREF
  wchar_t *String2; // [rsp+60h] [rbp+20h] BYREF
  wchar_t *String1; // [rsp+68h] [rbp+28h] BYREF

  hKey = 0;
  v3 = 0;
  phkResult = 0;
  String2 = 0;
  String1 = 0;
  if ( (unsigned int)CRegistry::OpenKey(
                       (CRegistry *)&hKey,
                       HKEY_LOCAL_MACHINE,
                       L"SOFTWARE\\Microsoft\\Dfs\\Roots\\Standalone",
                       0x20019u)
    && !(unsigned int)DfsReadRegistryStringSD(hKey, &String2)
    && !RegOpenKeyExW(hKey, *((LPCWSTR *)this + 26), 0, 0x20019u, &phkResult) )
  {
    DfsReadRegistryStringSD(phkResult, &String1);
    *((_BYTE *)this + 451) = _wcsicmp(String1, String2) != 0;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( String2 )
    LocalFree(String2);
  if ( String1 )
    LocalFree(String1);
  CRegistry::~CRegistry((CRegistry *)&hKey);
}

```

## disassembly

```asm
0x140020be8  mov     [rsp-8+arg_0], rbx
0x140020bed  push    rbp
0x140020bee  mov     rbp, rsp
0x140020bf1  sub     rsp, 40h
0x140020bf5  and     [rbp+hKey], 0
0x140020bfa  lea     r8, aSoftwareMicros; "SOFTWARE\\Microsoft\\Dfs\\Roots\\Standa"...
0x140020c01  and     [rbp+var_8], 0
0x140020c05  mov     rbx, rcx
0x140020c08  and     [rbp+arg_8], 0
0x140020c0d  lea     rcx, [rbp+hKey]; this
0x140020c11  and     [rbp+String2], 0
0x140020c16  mov     r9d, 20019h; unsigned int
0x140020c1c  and     [rbp+String1], 0
0x140020c21  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x140020c28  call    ?OpenKey@CRegistry@@QEAAHPEAUHKEY__@@PEBGK@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong)
0x140020c2d  test    eax, eax
0x140020c2f  jz      short loc_140020C9B
0x140020c31  mov     rcx, [rbp+hKey]
0x140020c35  lea     rdx, [rbp+String2]
0x140020c39  call    DfsReadRegistryStringSD
0x140020c3e  test    eax, eax
0x140020c40  jnz     short loc_140020C9B
0x140020c42  mov     rdx, [rbx+0D0h]; lpSubKey
0x140020c49  lea     rax, [rbp+arg_8]
0x140020c4d  mov     rcx, [rbp+hKey]; hKey
0x140020c51  mov     r9d, 20019h; samDesired
0x140020c57  xor     r8d, r8d; ulOptions
0x140020c5a  mov     [rsp+40h+phkResult], rax; phkResult
0x140020c5f  call    cs:__imp_RegOpenKeyExW
0x140020c66  nop     dword ptr [rax+rax+00h]
0x140020c6b  test    eax, eax
0x140020c6d  jnz     short loc_140020C9B
0x140020c6f  mov     rcx, [rbp+arg_8]
0x140020c73  lea     rdx, [rbp+String1]
0x140020c77  call    DfsReadRegistryStringSD
0x140020c7c  mov     rdx, [rbp+String2]; String2
0x140020c80  mov     rcx, [rbp+String1]; String1
0x140020c84  call    cs:__imp__wcsicmp
0x140020c8b  nop     dword ptr [rax+rax+00h]
0x140020c90  test    eax, eax
0x140020c92  setnz   al
0x140020c95  mov     [rbx+1C3h], al
0x140020c9b  mov     rcx, [rbp+arg_8]; hKey
0x140020c9f  test    rcx, rcx
0x140020ca2  jz      short loc_140020CB0
0x140020ca4  call    cs:__imp_RegCloseKey
0x140020cab  nop     dword ptr [rax+rax+00h]
0x140020cb0  mov     rcx, [rbp+String2]; hMem
0x140020cb4  test    rcx, rcx
0x140020cb7  jz      short loc_140020CC5
0x140020cb9  call    cs:__imp_LocalFree
0x140020cc0  nop     dword ptr [rax+rax+00h]
0x140020cc5  mov     rcx, [rbp+String1]; hMem
0x140020cc9  test    rcx, rcx
0x140020ccc  jz      short loc_140020CDA
0x140020cce  call    cs:__imp_LocalFree
0x140020cd5  nop     dword ptr [rax+rax+00h]
0x140020cda  lea     rcx, [rbp+hKey]; this
0x140020cde  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x140020ce3  mov     rbx, [rsp+40h+arg_0]
0x140020ce8  add     rsp, 40h
0x140020cec  pop     rbp
0x140020ced  retn
```
