# ConfigParser::ParseRegistry(void)

- ea: `0x1801b156c`
- end: `0x1801b1683`
- name: `?ParseRegistry@ConfigParser@@SAXXZ`
- size: `279`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18018fff0`

## callees

- `0x1801b156c`
- `0x180221d84`

## import_xrefs

- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1801b161e`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1801b166b`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1801b161e`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1801b166b`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1801b15b0`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1801b164e`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1801b15b0`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1801b164e`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x1801b1601`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x1801b1601`

## string_xrefs

- `0x1801b15e0`: `AllowUserConfig`

## pseudocode

```c
void ConfigParser::ParseRegistry(void)
{
  bool v0; // bl
  int pvData; // [rsp+40h] [rbp-10h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-Ch] BYREF
  HKEY hkey; // [rsp+48h] [rbp-8h] BYREF

  hkey = 0;
  v0 = 1;
  LOBYTE(word_180442D5C) = 1;
  LOBYTE(dword_180442D48) = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Internet Explorer\\JScriptLegacy", 0, 0x20019u, &hkey) )
    goto LABEL_9;
  pvData = 0;
  pcbData = 4;
  ConfigParser::ParseRegistryKey(hkey);
  if ( !RegGetValueW(hkey, 0, L"AllowUserConfig", 0x18u, 0, &pvData, &pcbData) )
    v0 = pvData != 0;
  RegCloseKey(hkey);
  if ( v0 )
  {
LABEL_9:
    if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Internet Explorer\\JScriptLegacy", 0, 0x20019u, &hkey) )
    {
      ConfigParser::ParseRegistryKey(hkey);
      RegCloseKey(hkey);
    }
  }
}

```

## disassembly

```asm
0x1801b156c  mov     [rsp-8+arg_0], rbx
0x1801b1571  push    rbp
0x1801b1572  mov     rbp, rsp
0x1801b1575  sub     rsp, 50h
0x1801b1579  lea     rax, [rbp+hkey]
0x1801b157d  mov     [rbp+hkey], 0
0x1801b1585  mov     bl, 1
0x1801b1587  mov     [rsp+50h+phkResult], rax; phkResult
0x1801b158c  mov     r9d, 20019h; samDesired
0x1801b1592  mov     byte ptr cs:word_180442D5C, bl
0x1801b1598  xor     r8d, r8d; ulOptions
0x1801b159b  mov     byte ptr cs:dword_180442D48, 0
0x1801b15a2  lea     rdx, SubKey; "Software\\Microsoft\\Internet Explorer"...
0x1801b15a9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801b15b0  call    cs:__imp_RegOpenKeyExW
0x1801b15b7  nop     dword ptr [rax+rax+00h]
0x1801b15bc  test    eax, eax
0x1801b15be  jnz     short loc_1801B162E
0x1801b15c0  mov     rcx, [rbp+hkey]; HKEY
0x1801b15c4  mov     [rbp+var_10], eax
0x1801b15c7  mov     [rbp+var_C], 4
0x1801b15ce  call    ?ParseRegistryKey@ConfigParser@@CAXPEAUHKEY__@@@Z; ConfigParser::ParseRegistryKey(HKEY__ *)
0x1801b15d3  mov     rcx, [rbp+hkey]; hkey
0x1801b15d7  lea     rax, [rbp+var_C]
0x1801b15db  mov     [rsp+50h+pcbData], rax; pcbData
0x1801b15e0  lea     r8, Value; "AllowUserConfig"
0x1801b15e7  lea     rax, [rbp+var_10]
0x1801b15eb  mov     r9d, 18h; dwFlags
0x1801b15f1  mov     [rsp+50h+pvData], rax; pvData
0x1801b15f6  xor     edx, edx; lpSubKey
0x1801b15f8  mov     [rsp+50h+phkResult], 0; pdwType
0x1801b1601  call    cs:__imp_RegGetValueW
0x1801b1608  nop     dword ptr [rax+rax+00h]
0x1801b160d  test    eax, eax
0x1801b160f  jnz     short loc_1801B161A
0x1801b1611  mov     eax, [rbp+var_10]
0x1801b1614  neg     eax
0x1801b1616  sbb     cl, cl
0x1801b1618  and     bl, cl
0x1801b161a  mov     rcx, [rbp+hkey]; hKey
0x1801b161e  call    cs:__imp_RegCloseKey
0x1801b1625  nop     dword ptr [rax+rax+00h]
0x1801b162a  test    bl, bl
0x1801b162c  jz      short loc_1801B1677
0x1801b162e  lea     rax, [rbp+hkey]
0x1801b1632  mov     r9d, 20019h; samDesired
0x1801b1638  xor     r8d, r8d; ulOptions
0x1801b163b  mov     [rsp+50h+phkResult], rax; phkResult
0x1801b1640  lea     rdx, SubKey; "Software\\Microsoft\\Internet Explorer"...
0x1801b1647  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1801b164e  call    cs:__imp_RegOpenKeyExW
0x1801b1655  nop     dword ptr [rax+rax+00h]
0x1801b165a  test    eax, eax
0x1801b165c  jnz     short loc_1801B1677
0x1801b165e  mov     rcx, [rbp+hkey]; HKEY
0x1801b1662  call    ?ParseRegistryKey@ConfigParser@@CAXPEAUHKEY__@@@Z; ConfigParser::ParseRegistryKey(HKEY__ *)
0x1801b1667  mov     rcx, [rbp+hkey]; hKey
0x1801b166b  call    cs:__imp_RegCloseKey
0x1801b1672  nop     dword ptr [rax+rax+00h]
0x1801b1677  mov     rbx, [rsp+50h+arg_0]
0x1801b167c  add     rsp, 50h
0x1801b1680  pop     rbp
0x1801b1681  retn
```
