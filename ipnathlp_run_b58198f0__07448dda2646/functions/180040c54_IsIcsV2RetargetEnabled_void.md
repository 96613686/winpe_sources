# IsIcsV2RetargetEnabled(void)

- ea: `0x180040c54`
- end: `0x180040dfa`
- name: `?IsIcsV2RetargetEnabled@@YAHXZ`
- size: `422`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18006e900`
- `0x18006eab0`

## callees

- `0x18000ca20`
- `0x180040c54`
- `0x180051f30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180040d83`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180040d83`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040d50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040d50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040da5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040da5`

## string_xrefs

- `0x180040ca8`: `System\CurrentControlSet\Services\SharedAccess\Parameters`

## pseudocode

```c
_BOOL8 IsIcsV2RetargetEnabled(void)
{
  BOOL v0; // ebx
  BYTE Data[4]; // [rsp+30h] [rbp-89h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-85h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-81h] BYREF
  wchar_t ValueName[16]; // [rsp+40h] [rbp-79h] BYREF
  WCHAR SubKey[64]; // [rsp+60h] [rbp-59h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids);
  }
  v0 = 0;
  wcscpy(SubKey, L"System\\CurrentControlSet\\Services\\SharedAccess\\Parameters");
  wcscpy(ValueName, L"V2Retaget");
  hKey = 0;
  cbData = 4;
  *(_DWORD *)Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey)
    && !RegQueryValueExW(hKey, ValueName, 0, 0, Data, &cbData) )
  {
    v0 = *(_DWORD *)Data != 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids);
  }
  return v0;
}

```

## disassembly

```asm
0x180040c54  push    rbp
0x180040c56  push    rbx
0x180040c57  push    rsi
0x180040c58  push    r14
0x180040c5a  lea     rbp, [rsp-3Fh]
0x180040c5f  sub     rsp, 0F8h
0x180040c66  mov     rax, cs:__security_cookie
0x180040c6d  xor     rax, rsp
0x180040c70  mov     [rbp+57h+var_30], rax
0x180040c74  mov     rcx, cs:WPP_GLOBAL_Control
0x180040c7b  lea     rsi, WPP_GLOBAL_Control
0x180040c82  cmp     rcx, rsi
0x180040c85  jz      short loc_180040CA8
0x180040c87  test    byte ptr [rcx+1Ch], 40h
0x180040c8b  jz      short loc_180040CA8
0x180040c8d  cmp     byte ptr [rcx+19h], 6
0x180040c91  jb      short loc_180040CA8
0x180040c93  mov     rcx, [rcx+10h]
0x180040c97  lea     r8, WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids
0x180040c9e  mov     edx, 1Bh
0x180040ca3  call    WPP_SF_
0x180040ca8  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Sh"...
0x180040caf  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180040cb3  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+10h; "urrentControlSet\\Services\\SharedAcces"...
0x180040cba  xor     ebx, ebx
0x180040cbc  mov     eax, dword ptr cs:aSystemCurrentc_2+70h; "s"
0x180040cc2  xor     r8d, r8d; ulOptions
0x180040cc5  movaps  xmmword ptr [rbp+57h+SubKey], xmm0
0x180040cc9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180040cd0  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+20h; "ntrolSet\\Services\\SharedAccess\\Param"...
0x180040cd7  movaps  [rbp+57h+var_90], xmm0
0x180040cdb  lea     r14d, [rbx+1]
0x180040cdf  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+40h; "s\\SharedAccess\\Parameters"
0x180040ce6  mov     r9d, r14d; samDesired
0x180040ce9  movaps  [rbp+57h+var_A0], xmm1
0x180040ced  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+30h; "\\Services\\SharedAccess\\Parameters"
0x180040cf4  movaps  [rbp+57h+var_70], xmm0
0x180040cf8  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+60h; "arameters"
0x180040cff  movaps  [rbp+57h+var_80], xmm1
0x180040d03  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+50h; "Access\\Parameters"
0x180040d0a  movaps  [rbp+57h+var_50], xmm0
0x180040d0e  movups  xmm0, xmmword ptr cs:aV2retarget; "V2Retarget"
0x180040d15  mov     [rbp+57h+var_40], eax
0x180040d18  lea     rax, [rsp+110h+hKey]
0x180040d1d  movaps  [rbp+57h+var_60], xmm1
0x180040d21  movsd   xmm1, qword ptr cs:aV2retarget+0Eh; "get"
0x180040d29  movups  xmmword ptr [rbp+57h+ValueName], xmm0
0x180040d2d  mov     [rsp+110h+hKey], 0
0x180040d36  movsd   qword ptr [rbp+57h+ValueName+0Eh], xmm1
0x180040d3b  mov     [rsp+110h+cbData], 4
0x180040d43  mov     dword ptr [rsp+110h+Data], 0
0x180040d4b  mov     [rsp+110h+phkResult], rax; phkResult
0x180040d50  call    cs:__imp_RegOpenKeyExW
0x180040d57  nop     dword ptr [rax+rax+00h]
0x180040d5c  test    eax, eax
0x180040d5e  jnz     short loc_180040D9B
0x180040d60  mov     rcx, [rsp+110h+hKey]; hKey
0x180040d65  lea     rax, [rsp+110h+cbData]
0x180040d6a  mov     [rsp+110h+lpcbData], rax; lpcbData
0x180040d6f  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x180040d73  lea     rax, [rsp+110h+Data]
0x180040d78  xor     r9d, r9d; lpType
0x180040d7b  xor     r8d, r8d; lpReserved
0x180040d7e  mov     [rsp+110h+phkResult], rax; lpData
0x180040d83  call    cs:__imp_RegQueryValueExW
0x180040d8a  nop     dword ptr [rax+rax+00h]
0x180040d8f  test    eax, eax
0x180040d91  jnz     short loc_180040D9B
0x180040d93  cmp     dword ptr [rsp+110h+Data], ebx
0x180040d97  cmovnz  ebx, r14d
0x180040d9b  mov     rcx, [rsp+110h+hKey]; hKey
0x180040da0  test    rcx, rcx
0x180040da3  jz      short loc_180040DB1
0x180040da5  call    cs:__imp_RegCloseKey
0x180040dac  nop     dword ptr [rax+rax+00h]
0x180040db1  mov     rcx, cs:WPP_GLOBAL_Control
0x180040db8  cmp     rcx, rsi
0x180040dbb  jz      short loc_180040DDE
0x180040dbd  test    byte ptr [rcx+1Ch], 40h
0x180040dc1  jz      short loc_180040DDE
0x180040dc3  cmp     byte ptr [rcx+19h], 6
0x180040dc7  jb      short loc_180040DDE
0x180040dc9  mov     rcx, [rcx+10h]
0x180040dcd  lea     r8, WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids
0x180040dd4  mov     edx, 1Ch
0x180040dd9  call    WPP_SF_
0x180040dde  mov     eax, ebx
0x180040de0  mov     rcx, [rbp+57h+var_30]
0x180040de4  xor     rcx, rsp; StackCookie
0x180040de7  call    __security_check_cookie
0x180040dec  add     rsp, 0F8h
0x180040df3  pop     r14
0x180040df5  pop     rsi
0x180040df6  pop     rbx
0x180040df7  pop     rbp
0x180040df8  retn
```
