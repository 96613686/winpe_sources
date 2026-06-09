# UserInsights::GetRegistryValue(HKEY__ *,ushort const *,ushort const *,ulong,uchar *,ulong)

- ea: `0x18027cd88`
- end: `0x18027ce83`
- name: `?GetRegistryValue@UserInsights@@AEAA_NPEAUHKEY__@@PEBG1KPEAEK@Z`
- size: `251`
- prototype: `bool(UserInsights *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18027cbf8`
- `0x18027cfac`
- `0x18027d0a4`

## callees

- `0x18009aa7c`
- `0x1800caaa4`
- `0x1800cabe8`
- `0x18013ce80`
- `0x18027cd88`
- `0x18027ce8c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18027ce0e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18027ce0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18027ce4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18027ce4f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18027ce3a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18027ce3a`

## pseudocode

```c
bool __fastcall UserInsights::GetRegistryValue(
        UserInsights *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        DWORD Type,
        LPBYTE lpData,
        DWORD cbData)
{
  BYTE *v8; // rsi
  bool v9; // bl
  __int64 v10; // r8
  int v11; // r10d
  int v12; // r11d
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  const WCHAR *v16; // rax
  HKEY phkResult; // [rsp+30h] [rbp-40h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v20[32]; // [rsp+40h] [rbp-30h] BYREF

  v8 = lpData;
  v9 = 0;
  phkResult = 0;
  hKey = 0;
  std::wstring::wstring(v20);
  InsightsRegistryPath(v11, v12, *(_QWORD *)(v10 + 48), (unsigned int)&hKey, (__int64)v20);
  v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20, v13, v14, v15);
  if ( !RegOpenKeyExW(hKey, v16, 0, 0x20019u, &phkResult) )
  {
    v9 = RegQueryValueExW(phkResult, a4, 0, &Type, v8, &cbData) == 0;
    RegCloseKey(phkResult);
  }
  std::wstring::_Tidy_deallocate(v20);
  return v9;
}

```

## disassembly

```asm
0x18027cd88  mov     [rsp-18h+arg_8], rbx
0x18027cd8d  push    rbp
0x18027cd8e  push    rsi
0x18027cd8f  push    rdi
0x18027cd90  mov     rbp, rsp
0x18027cd93  sub     rsp, 70h
0x18027cd97  mov     rax, cs:__security_cookie
0x18027cd9e  xor     rax, rsp
0x18027cda1  mov     [rbp+var_10], rax
0x18027cda5  mov     rdi, r9
0x18027cda8  mov     r11, r8
0x18027cdab  mov     r10, rdx
0x18027cdae  mov     r8, rcx
0x18027cdb1  mov     rsi, [rbp+lpData]
0x18027cdb5  xor     bl, bl
0x18027cdb7  mov     [rbp+var_40], 0
0x18027cdbf  mov     [rbp+hKey], 0
0x18027cdc7  lea     rcx, [rbp+var_30]
0x18027cdcb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18027cdd0  lea     rcx, [rbp+var_30]
0x18027cdd4  mov     [rsp+70h+phkResult], rcx
0x18027cdd9  lea     r9, [rbp+hKey]
0x18027cddd  mov     r8, [r8+30h]
0x18027cde1  mov     rdx, r11
0x18027cde4  mov     rcx, r10
0x18027cde7  call    InsightsRegistryPath
0x18027cdec  lea     rcx, [rbp+var_30]
0x18027cdf0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18027cdf5  mov     rdx, rax; lpSubKey
0x18027cdf8  lea     rax, [rbp+var_40]
0x18027cdfc  mov     [rsp+70h+phkResult], rax; phkResult
0x18027ce01  mov     r9d, 20019h; samDesired
0x18027ce07  xor     r8d, r8d; ulOptions
0x18027ce0a  mov     rcx, [rbp+hKey]; hKey
0x18027ce0e  call    cs:__imp_RegOpenKeyExW
0x18027ce15  nop     dword ptr [rax+rax+00h]
0x18027ce1a  test    eax, eax
0x18027ce1c  jnz     short loc_18027CE5B
0x18027ce1e  lea     rax, [rbp+cbData]
0x18027ce22  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18027ce27  mov     [rsp+70h+phkResult], rsi; lpData
0x18027ce2c  lea     r9, [rbp+Type]; lpType
0x18027ce30  xor     r8d, r8d; lpReserved
0x18027ce33  mov     rdx, rdi; lpValueName
0x18027ce36  mov     rcx, [rbp+var_40]; hKey
0x18027ce3a  call    cs:__imp_RegQueryValueExW
0x18027ce41  nop     dword ptr [rax+rax+00h]
0x18027ce46  test    eax, eax
0x18027ce48  setz    bl
0x18027ce4b  mov     rcx, [rbp+var_40]; hKey
0x18027ce4f  call    cs:__imp_RegCloseKey
0x18027ce56  nop     dword ptr [rax+rax+00h]
0x18027ce5b  lea     rcx, [rbp+var_30]
0x18027ce5f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18027ce64  mov     al, bl
0x18027ce66  mov     rcx, [rbp+var_10]
0x18027ce6a  xor     rcx, rsp; StackCookie
0x18027ce6d  call    __security_check_cookie
0x18027ce72  mov     rbx, [rsp+70h+arg_8]
0x18027ce7a  add     rsp, 70h
0x18027ce7e  pop     rdi
0x18027ce7f  pop     rsi
0x18027ce80  pop     rbp
0x18027ce81  retn
```
