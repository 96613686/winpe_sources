# IsIcsDnsFallbackDisabled(void)

- ea: `0x180021640`
- end: `0x1800217f3`
- name: `?IsIcsDnsFallbackDisabled@@YAHXZ`
- size: `435`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18002043c`

## callees

- `0x18000ca20`
- `0x180021640`
- `0x180051f30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002175c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002175c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021729`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021729`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800217c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800217c2`

## string_xrefs

- `0x180021683`: `System\CurrentControlSet\Services\SharedAccess\Parameters`

## pseudocode

```c
_BOOL8 IsIcsDnsFallbackDisabled(void)
{
  BOOL v0; // ebx
  BYTE Data[4]; // [rsp+30h] [rbp-89h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-85h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-81h] BYREF
  WCHAR ValueName[16]; // [rsp+40h] [rbp-79h] BYREF
  WCHAR SubKey[64]; // [rsp+60h] [rbp-59h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_9be8243bb99535625437fc4fc0071459_Traceguids);
  }
  v0 = 0;
  wcscpy(SubKey, L"System\\CurrentControlSet\\Services\\SharedAccess\\Parameters");
  hKey = 0;
  wcscpy(ValueName, L"DisableFallback");
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
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_9be8243bb99535625437fc4fc0071459_Traceguids);
  }
  return v0;
}

```

## disassembly

```asm
0x180021640  push    rbp
0x180021642  push    rbx
0x180021643  push    rsi
0x180021644  push    r14
0x180021646  lea     rbp, [rsp-3Fh]
0x18002164b  sub     rsp, 0F8h
0x180021652  mov     rax, cs:__security_cookie
0x180021659  xor     rax, rsp
0x18002165c  mov     [rbp+57h+var_30], rax
0x180021660  mov     rcx, cs:WPP_GLOBAL_Control
0x180021667  lea     rsi, WPP_GLOBAL_Control
0x18002166e  cmp     rcx, rsi
0x180021671  jz      short loc_180021683
0x180021673  test    byte ptr [rcx+1Ch], 10h
0x180021677  jz      short loc_180021683
0x180021679  cmp     byte ptr [rcx+19h], 6
0x18002167d  jnb     loc_18002179E
0x180021683  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Sh"...
0x18002168a  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x18002168e  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+10h; "urrentControlSet\\Services\\SharedAcces"...
0x180021695  xor     ebx, ebx
0x180021697  mov     eax, dword ptr cs:aSystemCurrentc_2+70h; "s"
0x18002169d  xor     r8d, r8d; ulOptions
0x1800216a0  movaps  xmmword ptr [rbp+57h+SubKey], xmm0
0x1800216a4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800216ab  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+20h; "ntrolSet\\Services\\SharedAccess\\Param"...
0x1800216b2  movaps  [rbp+57h+var_90], xmm0
0x1800216b6  lea     r14d, [rbx+1]
0x1800216ba  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+40h; "s\\SharedAccess\\Parameters"
0x1800216c1  mov     r9d, r14d; samDesired
0x1800216c4  movaps  [rbp+57h+var_A0], xmm1
0x1800216c8  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+30h; "\\Services\\SharedAccess\\Parameters"
0x1800216cf  movaps  [rbp+57h+var_70], xmm0
0x1800216d3  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+60h; "arameters"
0x1800216da  movaps  [rbp+57h+var_80], xmm1
0x1800216de  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+50h; "Access\\Parameters"
0x1800216e5  movaps  [rbp+57h+var_50], xmm0
0x1800216e9  movups  xmm0, xmmword ptr cs:aDisablefallbac; "DisableFallback"
0x1800216f0  mov     [rbp+57h+var_40], eax
0x1800216f3  lea     rax, [rsp+110h+hKey]
0x1800216f8  movaps  [rbp+57h+var_60], xmm1
0x1800216fc  movups  xmm1, xmmword ptr cs:aDisablefallbac+10h; "allback"
0x180021703  mov     [rsp+110h+hKey], 0
0x18002170c  movups  xmmword ptr [rbp+57h+ValueName], xmm0
0x180021710  mov     [rsp+110h+cbData], 4
0x180021718  mov     dword ptr [rsp+110h+Data], 0
0x180021720  movups  [rbp+57h+var_C0], xmm1
0x180021724  mov     [rsp+110h+phkResult], rax; phkResult
0x180021729  call    cs:__imp_RegOpenKeyExW
0x180021730  nop     dword ptr [rax+rax+00h]
0x180021735  test    eax, eax
0x180021737  jnz     short loc_18002176C
0x180021739  mov     rcx, [rsp+110h+hKey]; hKey
0x18002173e  lea     rax, [rsp+110h+cbData]
0x180021743  mov     [rsp+110h+lpcbData], rax; lpcbData
0x180021748  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x18002174c  lea     rax, [rsp+110h+Data]
0x180021751  xor     r9d, r9d; lpType
0x180021754  xor     r8d, r8d; lpReserved
0x180021757  mov     [rsp+110h+phkResult], rax; lpData
0x18002175c  call    cs:__imp_RegQueryValueExW
0x180021763  nop     dword ptr [rax+rax+00h]
0x180021768  test    eax, eax
0x18002176a  jz      short loc_1800217B8
0x18002176c  mov     rcx, [rsp+110h+hKey]; hKey
0x180021771  test    rcx, rcx
0x180021774  jnz     short loc_1800217C2
0x180021776  mov     rcx, cs:WPP_GLOBAL_Control
0x18002177d  cmp     rcx, rsi
0x180021780  jnz     short loc_1800217D0
0x180021782  mov     eax, ebx
0x180021784  mov     rcx, [rbp+57h+var_30]
0x180021788  xor     rcx, rsp; StackCookie
0x18002178b  call    __security_check_cookie
0x180021790  add     rsp, 0F8h
0x180021797  pop     r14
0x180021799  pop     rsi
0x18002179a  pop     rbx
0x18002179b  pop     rbp
0x18002179c  retn
0x18002179e  mov     rcx, [rcx+10h]
0x1800217a2  lea     r8, WPP_9be8243bb99535625437fc4fc0071459_Traceguids
0x1800217a9  mov     edx, 0Ah
0x1800217ae  call    WPP_SF_
0x1800217b3  jmp     loc_180021683
0x1800217b8  cmp     dword ptr [rsp+110h+Data], ebx
0x1800217bc  cmovnz  ebx, r14d
0x1800217c0  jmp     short loc_18002176C
0x1800217c2  call    cs:__imp_RegCloseKey
0x1800217c9  nop     dword ptr [rax+rax+00h]
0x1800217ce  jmp     short loc_180021776
0x1800217d0  test    byte ptr [rcx+1Ch], 10h
0x1800217d4  jz      short loc_180021782
0x1800217d6  cmp     byte ptr [rcx+19h], 6
0x1800217da  jb      short loc_180021782
0x1800217dc  mov     rcx, [rcx+10h]
0x1800217e0  lea     r8, WPP_9be8243bb99535625437fc4fc0071459_Traceguids
0x1800217e7  mov     edx, 0Bh
0x1800217ec  call    WPP_SF_
0x1800217f1  jmp     short loc_180021782
```
