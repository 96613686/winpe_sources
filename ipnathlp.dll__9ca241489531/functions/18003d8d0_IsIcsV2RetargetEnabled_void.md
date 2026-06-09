# IsIcsV2RetargetEnabled(void)

- ea: `0x18003d8d0`
- end: `0x18003da63`
- name: `?IsIcsV2RetargetEnabled@@YAHXZ`
- size: `403`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180069660`
- `0x1800697e0`

## callees

- `0x18000c110`
- `0x18003d8d0`
- `0x18004e0c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003d9f9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003d9f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d9cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d9cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003da15`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003da15`

## string_xrefs

- `0x18003d924`: `System\CurrentControlSet\Services\SharedAccess\Parameters`

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
0x18003d8d0  push    rbp
0x18003d8d2  push    rbx
0x18003d8d3  push    rsi
0x18003d8d4  push    r14
0x18003d8d6  lea     rbp, [rsp-3Fh]
0x18003d8db  sub     rsp, 0F8h
0x18003d8e2  mov     rax, cs:__security_cookie
0x18003d8e9  xor     rax, rsp
0x18003d8ec  mov     [rbp+57h+var_30], rax
0x18003d8f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d8f7  lea     rsi, WPP_GLOBAL_Control
0x18003d8fe  cmp     rcx, rsi
0x18003d901  jz      short loc_18003D924
0x18003d903  test    byte ptr [rcx+1Ch], 40h
0x18003d907  jz      short loc_18003D924
0x18003d909  cmp     byte ptr [rcx+19h], 6
0x18003d90d  jb      short loc_18003D924
0x18003d90f  mov     rcx, [rcx+10h]
0x18003d913  lea     r8, WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids
0x18003d91a  mov     edx, 1Bh
0x18003d91f  call    WPP_SF_
0x18003d924  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Sh"...
0x18003d92b  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x18003d92f  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+10h; "urrentControlSet\\Services\\SharedAcces"...
0x18003d936  xor     ebx, ebx
0x18003d938  mov     eax, dword ptr cs:aSystemCurrentc_2+70h; "s"
0x18003d93e  xor     r8d, r8d; ulOptions
0x18003d941  movaps  xmmword ptr [rbp+57h+SubKey], xmm0
0x18003d945  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003d94c  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+20h; "ntrolSet\\Services\\SharedAccess\\Param"...
0x18003d953  movaps  [rbp+57h+var_90], xmm0
0x18003d957  lea     r14d, [rbx+1]
0x18003d95b  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+40h; "s\\SharedAccess\\Parameters"
0x18003d962  mov     r9d, r14d; samDesired
0x18003d965  movaps  [rbp+57h+var_A0], xmm1
0x18003d969  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+30h; "\\Services\\SharedAccess\\Parameters"
0x18003d970  movaps  [rbp+57h+var_70], xmm0
0x18003d974  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+60h; "arameters"
0x18003d97b  movaps  [rbp+57h+var_80], xmm1
0x18003d97f  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+50h; "Access\\Parameters"
0x18003d986  movaps  [rbp+57h+var_50], xmm0
0x18003d98a  movups  xmm0, xmmword ptr cs:aV2retarget; "V2Retarget"
0x18003d991  mov     [rbp+57h+var_40], eax
0x18003d994  lea     rax, [rsp+110h+hKey]
0x18003d999  movaps  [rbp+57h+var_60], xmm1
0x18003d99d  movsd   xmm1, qword ptr cs:aV2retarget+0Eh; "get"
0x18003d9a5  movups  xmmword ptr [rbp+57h+ValueName], xmm0
0x18003d9a9  mov     [rsp+110h+hKey], 0
0x18003d9b2  movsd   qword ptr [rbp+57h+ValueName+0Eh], xmm1
0x18003d9b7  mov     [rsp+110h+cbData], 4
0x18003d9bf  mov     dword ptr [rsp+110h+Data], 0
0x18003d9c7  mov     [rsp+110h+phkResult], rax; phkResult
0x18003d9cc  call    cs:__imp_RegOpenKeyExW
0x18003d9d2  test    eax, eax
0x18003d9d4  jnz     short loc_18003DA0B
0x18003d9d6  mov     rcx, [rsp+110h+hKey]; hKey
0x18003d9db  lea     rax, [rsp+110h+cbData]
0x18003d9e0  mov     [rsp+110h+lpcbData], rax; lpcbData
0x18003d9e5  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x18003d9e9  lea     rax, [rsp+110h+Data]
0x18003d9ee  xor     r9d, r9d; lpType
0x18003d9f1  xor     r8d, r8d; lpReserved
0x18003d9f4  mov     [rsp+110h+phkResult], rax; lpData
0x18003d9f9  call    cs:__imp_RegQueryValueExW
0x18003d9ff  test    eax, eax
0x18003da01  jnz     short loc_18003DA0B
0x18003da03  cmp     dword ptr [rsp+110h+Data], ebx
0x18003da07  cmovnz  ebx, r14d
0x18003da0b  mov     rcx, [rsp+110h+hKey]; hKey
0x18003da10  test    rcx, rcx
0x18003da13  jz      short loc_18003DA1B
0x18003da15  call    cs:__imp_RegCloseKey
0x18003da1b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003da22  cmp     rcx, rsi
0x18003da25  jz      short loc_18003DA48
0x18003da27  test    byte ptr [rcx+1Ch], 40h
0x18003da2b  jz      short loc_18003DA48
0x18003da2d  cmp     byte ptr [rcx+19h], 6
0x18003da31  jb      short loc_18003DA48
0x18003da33  mov     rcx, [rcx+10h]
0x18003da37  lea     r8, WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids
0x18003da3e  mov     edx, 1Ch
0x18003da43  call    WPP_SF_
0x18003da48  mov     eax, ebx
0x18003da4a  mov     rcx, [rbp+57h+var_30]
0x18003da4e  xor     rcx, rsp; StackCookie
0x18003da51  call    __security_check_cookie
0x18003da56  add     rsp, 0F8h
0x18003da5d  pop     r14
0x18003da5f  pop     rsi
0x18003da60  pop     rbx
0x18003da61  pop     rbp
0x18003da62  retn
```
