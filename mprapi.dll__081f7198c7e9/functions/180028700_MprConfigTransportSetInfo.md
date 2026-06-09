# MprConfigTransportSetInfo

- ea: `0x180028700`
- end: `0x18002882f`
- name: `MprConfigTransportSetInfo`
- size: `303`
- prototype: `DWORD __stdcall(HANDLE hMprConfig, HANDLE hRouterTransport, LPBYTE pGlobalInfo, DWORD dwGlobalInfoSize, LPBYTE pClientInterfaceInfo, DWORD dwClientInterfaceInfoSize, LPWSTR lpwsDLLPath)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800181b8`
- `0x180027da0`

## callees

- `0x180027d5c`
- `0x180028700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002881c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002881c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002875b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002875b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028794`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800287c9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028807`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028794`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800287c9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028807`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800287dd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800287dd`

## string_xrefs

- `0x1800287e7`: `DLLPath`

## pseudocode

```c
DWORD __stdcall MprConfigTransportSetInfo(
        HANDLE hMprConfig,
        HANDLE hRouterTransport,
        LPBYTE pGlobalInfo,
        DWORD dwGlobalInfoSize,
        LPBYTE pClientInterfaceInfo,
        DWORD dwClientInterfaceInfoSize,
        LPWSTR lpwsDLLPath)
{
  DWORD result; // eax
  LSTATUS v11; // ebx
  int v12; // eax

  if ( !hRouterTransport )
    return 87;
  if ( !pGlobalInfo && !pClientInterfaceInfo && !lpwsDLLPath )
    return 0;
  result = MprConfigServerValidateCb(hMprConfig);
  if ( !result )
  {
    EnterCriticalSection(&CfgLock);
    if ( *((_DWORD *)hRouterTransport + 6) )
    {
      v11 = 902;
    }
    else if ( (!pGlobalInfo
            || (v11 = RegSetValueExW(
                        *((HKEY *)hRouterTransport + 2),
                        L"GlobalInfo",
                        0,
                        3u,
                        pGlobalInfo,
                        dwGlobalInfoSize)) == 0)
           && (!pClientInterfaceInfo
            || (v11 = RegSetValueExW(
                        *((HKEY *)hRouterTransport + 2),
                        L"GlobalInterfaceInfo",
                        0,
                        3u,
                        pClientInterfaceInfo,
                        dwClientInterfaceInfoSize)) == 0) )
    {
      if ( !lpwsDLLPath
        || (v12 = lstrlenW(lpwsDLLPath),
            (v11 = RegSetValueExW(
                     *((HKEY *)hRouterTransport + 2),
                     L"DLLPath",
                     0,
                     2u,
                     (const BYTE *)lpwsDLLPath,
                     2 * v12 + 2)) == 0) )
      {
        v11 = 0;
      }
    }
    LeaveCriticalSection(&CfgLock);
    return v11;
  }
  return result;
}

```

## disassembly

```asm
0x180028700  push    rbx
0x180028702  push    rbp
0x180028703  push    rsi
0x180028704  push    rdi
0x180028705  push    r14
0x180028707  sub     rsp, 30h
0x18002870b  mov     r14d, r9d
0x18002870e  mov     rbx, r8
0x180028711  mov     rsi, rdx
0x180028714  test    rdx, rdx
0x180028717  jnz     short loc_180028721
0x180028719  lea     eax, [rdx+57h]
0x18002871c  jmp     loc_180028824
0x180028721  mov     rdi, [rsp+58h+lpwsDLLPath]
0x180028729  mov     rbp, [rsp+58h+pClientInterfaceInfo]
0x180028731  test    rbx, rbx
0x180028734  jnz     short loc_180028747
0x180028736  test    rbp, rbp
0x180028739  jnz     short loc_180028747
0x18002873b  test    rdi, rdi
0x18002873e  jnz     short loc_180028747
0x180028740  xor     eax, eax
0x180028742  jmp     loc_180028824
0x180028747  call    MprConfigServerValidateCb
0x18002874c  test    eax, eax
0x18002874e  jnz     loc_180028824
0x180028754  lea     rcx, CfgLock; lpCriticalSection
0x18002875b  call    cs:__imp_EnterCriticalSection
0x180028761  cmp     dword ptr [rsi+18h], 0
0x180028765  jz      short loc_180028771
0x180028767  mov     ebx, 386h
0x18002876c  jmp     loc_180028815
0x180028771  test    rbx, rbx
0x180028774  jz      short loc_1800287A0
0x180028776  mov     rcx, [rsi+10h]; hKey
0x18002877a  lea     rdx, c_szGlobalInfo; "GlobalInfo"
0x180028781  mov     [rsp+58h+cbData], r14d; cbData
0x180028786  mov     r9d, 3; dwType
0x18002878c  xor     r8d, r8d; Reserved
0x18002878f  mov     [rsp+58h+lpData], rbx; lpData
0x180028794  call    cs:__imp_RegSetValueExW
0x18002879a  mov     ebx, eax
0x18002879c  test    eax, eax
0x18002879e  jnz     short loc_180028815
0x1800287a0  test    rbp, rbp
0x1800287a3  jz      short loc_1800287D5
0x1800287a5  mov     eax, [rsp+58h+dwClientInterfaceInfoSize]
0x1800287ac  lea     rdx, c_szGlobalInterfaceInfo; "GlobalInterfaceInfo"
0x1800287b3  mov     rcx, [rsi+10h]; hKey
0x1800287b7  mov     r9d, 3; dwType
0x1800287bd  mov     [rsp+58h+cbData], eax; cbData
0x1800287c1  xor     r8d, r8d; Reserved
0x1800287c4  mov     [rsp+58h+lpData], rbp; lpData
0x1800287c9  call    cs:__imp_RegSetValueExW
0x1800287cf  mov     ebx, eax
0x1800287d1  test    eax, eax
0x1800287d3  jnz     short loc_180028815
0x1800287d5  test    rdi, rdi
0x1800287d8  jz      short loc_180028813
0x1800287da  mov     rcx, rdi; lpString
0x1800287dd  call    cs:__imp_lstrlenW
0x1800287e3  mov     rcx, [rsi+10h]; hKey
0x1800287e7  lea     rdx, c_szDLLPath; "DLLPath"
0x1800287ee  mov     r9d, 2; dwType
0x1800287f4  xor     r8d, r8d; Reserved
0x1800287f7  lea     eax, ds:2[rax*2]
0x1800287fe  mov     [rsp+58h+cbData], eax; cbData
0x180028802  mov     [rsp+58h+lpData], rdi; lpData
0x180028807  call    cs:__imp_RegSetValueExW
0x18002880d  mov     ebx, eax
0x18002880f  test    eax, eax
0x180028811  jnz     short loc_180028815
0x180028813  xor     ebx, ebx
0x180028815  lea     rcx, CfgLock; lpCriticalSection
0x18002881c  call    cs:__imp_LeaveCriticalSection
0x180028822  mov     eax, ebx
0x180028824  add     rsp, 30h
0x180028828  pop     r14
0x18002882a  pop     rdi
0x18002882b  pop     rsi
0x18002882c  pop     rbp
0x18002882d  pop     rbx
0x18002882e  retn
```
