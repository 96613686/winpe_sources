# ConfigParser::ParseRegistry(CmdLineArgsParser &)

- ea: `0x1802f2eb0`
- end: `0x1802f2fc3`
- name: `?ParseRegistry@ConfigParser@@QEAAXAEAVCmdLineArgsParser@@@Z`
- size: `275`
- prototype: `void __fastcall(ConfigParser *__hidden this, struct CmdLineArgsParser *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1802f257c`
- `0x1803c4aa8`

## callees

- `0x1802f2eb0`
- `0x1804888ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802f2f5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802f2fab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802f2f5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802f2fab`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1802f2f41`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1802f2f41`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802f2eee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802f2f8e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802f2eee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802f2f8e`

## string_xrefs

- `0x1802f2f20`: `AllowUserConfig`

## pseudocode

```c
void __fastcall ConfigParser::ParseRegistry(ConfigParser *this, struct CmdLineArgsParser *a2)
{
  ConfigParser *v2; // rcx
  struct CmdLineArgsParser *v3; // r8
  bool v4; // bl
  ConfigParser *v5; // rcx
  struct CmdLineArgsParser *v6; // r8
  int pvData; // [rsp+40h] [rbp-10h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-Ch] BYREF
  HKEY hkey; // [rsp+48h] [rbp-8h] BYREF

  hkey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Internet Explorer\\JScript9", 0, 0x20019u, &hkey) )
    goto LABEL_9;
  v4 = 1;
  pvData = 0;
  pcbData = 4;
  ConfigParser::ParseRegistryKey(v2, hkey, v3);
  if ( !RegGetValueW(hkey, 0, L"AllowUserConfig", 0x18u, 0, &pvData, &pcbData) )
    v4 = pvData != 0;
  RegCloseKey(hkey);
  if ( v4 )
  {
LABEL_9:
    if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Internet Explorer\\JScript9", 0, 0x20019u, &hkey) )
    {
      ConfigParser::ParseRegistryKey(v5, hkey, v6);
      RegCloseKey(hkey);
    }
  }
}

```

## disassembly

```asm
0x1802f2eb0  mov     r11, rsp
0x1802f2eb3  mov     [r11+18h], rbx
0x1802f2eb7  mov     [r11+10h], rdx
0x1802f2ebb  mov     [r11+8], rcx
0x1802f2ebf  push    rbp
0x1802f2ec0  mov     rbp, rsp
0x1802f2ec3  sub     rsp, 50h
0x1802f2ec7  lea     rax, [rbp+hkey]
0x1802f2ecb  mov     [rbp+hkey], 0
0x1802f2ed3  mov     r9d, 20019h; samDesired
0x1802f2ed9  mov     [r11-38h], rax
0x1802f2edd  xor     r8d, r8d; ulOptions
0x1802f2ee0  lea     rdx, SubKey; "Software\\Microsoft\\Internet Explorer"...
0x1802f2ee7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1802f2eee  call    cs:__imp_RegOpenKeyExW
0x1802f2ef5  nop     dword ptr [rax+rax+00h]
0x1802f2efa  test    eax, eax
0x1802f2efc  jnz     short loc_1802F2F6E
0x1802f2efe  mov     rdx, [rbp+hkey]; HKEY
0x1802f2f02  mov     bl, 1
0x1802f2f04  mov     [rbp+var_10], eax
0x1802f2f07  mov     [rbp+var_C], 4
0x1802f2f0e  call    ?ParseRegistryKey@ConfigParser@@AEAAXPEAUHKEY__@@AEAVCmdLineArgsParser@@@Z; ConfigParser::ParseRegistryKey(HKEY__ *,CmdLineArgsParser &)
0x1802f2f13  mov     rcx, [rbp+hkey]; hkey
0x1802f2f17  lea     rax, [rbp+var_C]
0x1802f2f1b  mov     [rsp+50h+pcbData], rax; pcbData
0x1802f2f20  lea     r8, Value; "AllowUserConfig"
0x1802f2f27  lea     rax, [rbp+var_10]
0x1802f2f2b  mov     r9d, 18h; dwFlags
0x1802f2f31  mov     [rsp+50h+pvData], rax; pvData
0x1802f2f36  xor     edx, edx; lpSubKey
0x1802f2f38  mov     [rsp+50h+pdwType], 0; pdwType
0x1802f2f41  call    cs:__imp_RegGetValueW
0x1802f2f48  nop     dword ptr [rax+rax+00h]
0x1802f2f4d  test    eax, eax
0x1802f2f4f  jnz     short loc_1802F2F5A
0x1802f2f51  mov     eax, [rbp+var_10]
0x1802f2f54  neg     eax
0x1802f2f56  sbb     cl, cl
0x1802f2f58  and     bl, cl
0x1802f2f5a  mov     rcx, [rbp+hkey]; hKey
0x1802f2f5e  call    cs:__imp_RegCloseKey
0x1802f2f65  nop     dword ptr [rax+rax+00h]
0x1802f2f6a  test    bl, bl
0x1802f2f6c  jz      short loc_1802F2FB7
0x1802f2f6e  lea     rax, [rbp+hkey]
0x1802f2f72  mov     r9d, 20019h; samDesired
0x1802f2f78  xor     r8d, r8d; ulOptions
0x1802f2f7b  mov     [rsp+50h+pdwType], rax; phkResult
0x1802f2f80  lea     rdx, SubKey; "Software\\Microsoft\\Internet Explorer"...
0x1802f2f87  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1802f2f8e  call    cs:__imp_RegOpenKeyExW
0x1802f2f95  nop     dword ptr [rax+rax+00h]
0x1802f2f9a  test    eax, eax
0x1802f2f9c  jnz     short loc_1802F2FB7
0x1802f2f9e  mov     rdx, [rbp+hkey]; HKEY
0x1802f2fa2  call    ?ParseRegistryKey@ConfigParser@@AEAAXPEAUHKEY__@@AEAVCmdLineArgsParser@@@Z; ConfigParser::ParseRegistryKey(HKEY__ *,CmdLineArgsParser &)
0x1802f2fa7  mov     rcx, [rbp+hkey]; hKey
0x1802f2fab  call    cs:__imp_RegCloseKey
0x1802f2fb2  nop     dword ptr [rax+rax+00h]
0x1802f2fb7  mov     rbx, [rsp+50h+arg_10]
0x1802f2fbc  add     rsp, 50h
0x1802f2fc0  pop     rbp
0x1802f2fc1  retn
```
