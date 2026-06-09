# MprConfigInterfaceTransportSetInfo

- ea: `0x180025d60`
- end: `0x180025e10`
- name: `MprConfigInterfaceTransportSetInfo`
- size: `176`
- prototype: `DWORD __stdcall(HANDLE hMprConfig, HANDLE hRouterInterface, HANDLE hRouterIfTransport, LPBYTE pInterfaceInfo, DWORD dwInterfaceInfoSize)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800255a0`

## callees

- `0x180025d60`
- `0x180027d5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025ddd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025dee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025ddd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025dee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025d9b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025d9b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025dce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025dce`

## pseudocode

```c
DWORD __stdcall MprConfigInterfaceTransportSetInfo(
        HANDLE hMprConfig,
        HANDLE hRouterInterface,
        HANDLE hRouterIfTransport,
        LPBYTE pInterfaceInfo,
        DWORD dwInterfaceInfoSize)
{
  DWORD result; // eax
  LSTATUS v9; // ebx

  if ( !hRouterInterface || !hRouterIfTransport )
    return 87;
  if ( !pInterfaceInfo )
    return 0;
  result = MprConfigServerValidateCb(hMprConfig);
  if ( !result )
  {
    EnterCriticalSection(&CfgLock);
    if ( *((_DWORD *)hRouterInterface + 14) || *((_DWORD *)hRouterIfTransport + 6) )
    {
      LeaveCriticalSection(&CfgLock);
      return 905;
    }
    else
    {
      v9 = RegSetValueExW(
             *((HKEY *)hRouterIfTransport + 2),
             L"InterfaceInfo",
             0,
             3u,
             pInterfaceInfo,
             dwInterfaceInfoSize);
      LeaveCriticalSection(&CfgLock);
      return v9;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180025d60  mov     [rsp+arg_0], rbx
0x180025d65  mov     [rsp+arg_8], rsi
0x180025d6a  push    rdi
0x180025d6b  sub     rsp, 30h
0x180025d6f  mov     rsi, r9
0x180025d72  mov     rbx, r8
0x180025d75  mov     rdi, rdx
0x180025d78  test    rdx, rdx
0x180025d7b  jz      short loc_180025DFB
0x180025d7d  test    rbx, rbx
0x180025d80  jz      short loc_180025DFB
0x180025d82  test    r9, r9
0x180025d85  jnz     short loc_180025D8B
0x180025d87  xor     eax, eax
0x180025d89  jmp     short loc_180025E00
0x180025d8b  call    MprConfigServerValidateCb
0x180025d90  test    eax, eax
0x180025d92  jnz     short loc_180025E00
0x180025d94  lea     rcx, CfgLock; lpCriticalSection
0x180025d9b  call    cs:__imp_EnterCriticalSection
0x180025da1  cmp     dword ptr [rdi+38h], 0
0x180025da5  jnz     short loc_180025DE7
0x180025da7  cmp     dword ptr [rbx+18h], 0
0x180025dab  jnz     short loc_180025DE7
0x180025dad  mov     eax, [rsp+38h+dwInterfaceInfoSize]
0x180025db1  lea     rdx, c_szInterfaceInfo; "InterfaceInfo"
0x180025db8  mov     rcx, [rbx+10h]; hKey
0x180025dbc  mov     r9d, 3; dwType
0x180025dc2  mov     [rsp+38h+cbData], eax; cbData
0x180025dc6  xor     r8d, r8d; Reserved
0x180025dc9  mov     [rsp+38h+lpData], rsi; lpData
0x180025dce  call    cs:__imp_RegSetValueExW
0x180025dd4  lea     rcx, CfgLock; lpCriticalSection
0x180025ddb  mov     ebx, eax
0x180025ddd  call    cs:__imp_LeaveCriticalSection
0x180025de3  mov     eax, ebx
0x180025de5  jmp     short loc_180025E00
0x180025de7  lea     rcx, CfgLock; lpCriticalSection
0x180025dee  call    cs:__imp_LeaveCriticalSection
0x180025df4  mov     eax, 389h
0x180025df9  jmp     short loc_180025E00
0x180025dfb  mov     eax, 57h ; 'W'
0x180025e00  mov     rbx, [rsp+38h+arg_0]
0x180025e05  mov     rsi, [rsp+38h+arg_8]
0x180025e0a  add     rsp, 30h
0x180025e0e  pop     rdi
0x180025e0f  retn
```
