# SKCacheLoadSettings

- ea: `0x180021df4`
- end: `0x180021fbe`
- name: `SKCacheLoadSettings`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021d90`

## callees

- `0x180021df4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021f87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021f87`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180021e5e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180021e5e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180021e9f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180021ee6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180021f2e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180021e9f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180021ee6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180021f2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021f6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021f6b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021e13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021e13`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180021e2c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180021e2c`

## string_xrefs

- `0x180021ec6`: `PrivKeyCachePurgeIntervalSeconds`
- `0x180021e7f`: `PrivKeyCacheMaxItems`

## pseudocode

```c
void SKCacheLoadSettings()
{
  int v0; // eax
  DWORD cbData; // [rsp+40h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+18h] BYREF

  hKey = 0;
  cbData = 0;
  EnterCriticalSection(&CriticalSection);
  if ( dword_18007A64C == 1 )
    goto LABEL_11;
  dword_18007A638 = GetTickCount();
  if ( RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Policies\\Microsoft\\Cryptography", 0, 0x20119u, &hKey) )
  {
    *(_DWORD *)&Data = 20;
    v0 = 86400;
  }
  else
  {
    cbData = 4;
    if ( RegQueryValueExA(hKey, "PrivKeyCacheMaxItems", 0, 0, &Data, &cbData) )
      *(_DWORD *)&Data = 20;
    cbData = 4;
    if ( RegQueryValueExA(hKey, "PrivKeyCachePurgeIntervalSeconds", 0, 0, &dword_18007A644, &cbData) )
      *(_DWORD *)&dword_18007A644 = 86400;
    cbData = 4;
    if ( !RegQueryValueExA(hKey, "PrivateKeyLifetimeSeconds", 0, 0, &dword_18007A648, &cbData) )
    {
      *(_DWORD *)&dword_18007A648 *= 1000;
      v0 = *(_DWORD *)&dword_18007A644;
      goto LABEL_10;
    }
    v0 = *(_DWORD *)&dword_18007A644;
  }
  *(_DWORD *)&dword_18007A648 = -1;
LABEL_10:
  dword_18007A64C = 1;
  *(_DWORD *)&dword_18007A644 = 1000 * v0;
LABEL_11:
  LeaveCriticalSection(&CriticalSection);
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180021df4  push    rbp
0x180021df6  mov     rbp, rsp
0x180021df9  sub     rsp, 30h
0x180021dfd  lea     rcx, CriticalSection; lpCriticalSection
0x180021e04  mov     [rbp+hKey], 0
0x180021e0c  mov     [rbp+cbData], 0
0x180021e13  call    cs:__imp_EnterCriticalSection
0x180021e1a  nop     dword ptr [rax+rax+00h]
0x180021e1f  cmp     cs:dword_18007A64C, 1
0x180021e26  jz      loc_180021F64
0x180021e2c  call    cs:__imp_GetTickCount
0x180021e33  nop     dword ptr [rax+rax+00h]
0x180021e38  mov     cs:dword_18007A638, eax
0x180021e3e  mov     r9d, 20119h; samDesired
0x180021e44  xor     r8d, r8d; ulOptions
0x180021e47  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Cryptogr"...
0x180021e4e  lea     rax, [rbp+hKey]
0x180021e52  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180021e59  mov     [rsp+30h+phkResult], rax; phkResult
0x180021e5e  call    cs:__imp_RegOpenKeyExA
0x180021e65  nop     dword ptr [rax+rax+00h]
0x180021e6a  test    eax, eax
0x180021e6c  jnz     loc_180021F95
0x180021e72  mov     rcx, [rbp+hKey]; hKey
0x180021e76  lea     rax, [rbp+cbData]
0x180021e7a  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180021e7f  lea     rdx, aPrivkeycachema; "PrivKeyCacheMaxItems"
0x180021e86  lea     rax, Data
0x180021e8d  mov     [rbp+cbData], 4
0x180021e94  xor     r9d, r9d; lpType
0x180021e97  mov     [rsp+30h+phkResult], rax; lpData
0x180021e9c  xor     r8d, r8d; lpReserved
0x180021e9f  call    cs:__imp_RegQueryValueExA
0x180021ea6  nop     dword ptr [rax+rax+00h]
0x180021eab  test    eax, eax
0x180021ead  jz      short loc_180021EB9
0x180021eaf  mov     cs:Data, 14h
0x180021eb9  mov     rcx, [rbp+hKey]; hKey
0x180021ebd  lea     rax, [rbp+cbData]
0x180021ec1  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180021ec6  lea     rdx, aPrivkeycachepu; "PrivKeyCachePurgeIntervalSeconds"
0x180021ecd  lea     rax, dword_18007A644
0x180021ed4  mov     [rbp+cbData], 4
0x180021edb  xor     r9d, r9d; lpType
0x180021ede  mov     [rsp+30h+phkResult], rax; lpData
0x180021ee3  xor     r8d, r8d; lpReserved
0x180021ee6  call    cs:__imp_RegQueryValueExA
0x180021eed  nop     dword ptr [rax+rax+00h]
0x180021ef2  test    eax, eax
0x180021ef4  jz      short loc_180021F01
0x180021ef6  mov     eax, 15180h
0x180021efb  mov     cs:dword_18007A644, eax
0x180021f01  mov     rcx, [rbp+hKey]; hKey
0x180021f05  lea     rax, [rbp+cbData]
0x180021f09  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180021f0e  lea     rdx, aPrivatekeylife; "PrivateKeyLifetimeSeconds"
0x180021f15  lea     rax, dword_18007A648
0x180021f1c  mov     [rbp+cbData], 4
0x180021f23  xor     r9d, r9d; lpType
0x180021f26  mov     [rsp+30h+phkResult], rax; lpData
0x180021f2b  xor     r8d, r8d; lpReserved
0x180021f2e  call    cs:__imp_RegQueryValueExA
0x180021f35  nop     dword ptr [rax+rax+00h]
0x180021f3a  test    eax, eax
0x180021f3c  jz      short loc_180021FA6
0x180021f3e  mov     eax, cs:dword_18007A644
0x180021f44  mov     cs:dword_18007A648, 0FFFFFFFFh
0x180021f4e  imul    eax, 3E8h
0x180021f54  mov     cs:dword_18007A64C, 1
0x180021f5e  mov     cs:dword_18007A644, eax
0x180021f64  lea     rcx, CriticalSection; lpCriticalSection
0x180021f6b  call    cs:__imp_LeaveCriticalSection
0x180021f72  nop     dword ptr [rax+rax+00h]
0x180021f77  mov     rcx, [rbp+hKey]; hKey
0x180021f7b  test    rcx, rcx
0x180021f7e  jnz     short loc_180021F87
0x180021f80  add     rsp, 30h
0x180021f84  pop     rbp
0x180021f85  retn
0x180021f87  call    cs:__imp_RegCloseKey
0x180021f8e  nop     dword ptr [rax+rax+00h]
0x180021f93  jmp     short loc_180021F80
0x180021f95  mov     cs:Data, 14h
0x180021f9f  mov     eax, 15180h
0x180021fa4  jmp     short loc_180021F44
0x180021fa6  imul    eax, cs:dword_18007A648, 3E8h
0x180021fb0  mov     cs:dword_18007A648, eax
0x180021fb6  mov     eax, cs:dword_18007A644
0x180021fbc  jmp     short loc_180021F4E
```
