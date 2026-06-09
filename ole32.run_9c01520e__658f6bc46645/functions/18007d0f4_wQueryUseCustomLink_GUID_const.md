# wQueryUseCustomLink(_GUID const &)

- ea: `0x18007d0f4`
- end: `0x18007d17f`
- name: `?wQueryUseCustomLink@@YAHAEBU_GUID@@@Z`
- size: `139`
- prototype: `int __fastcall(const _GUID *rclsid)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007becc`
- `0x18007e370`

## callees

- `0x18007d0f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007d13f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007d13f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d154`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d16a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d154`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d16a`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x18007d110`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x18007d110`

## string_xrefs

- `0x18007d138`: `UseCustomLink`

## pseudocode

```c
__int64 __fastcall wQueryUseCustomLink(const _GUID *rclsid)
{
  unsigned int v1; // ebx
  HKEY__ *hkeyClsid; // [rsp+48h] [rbp+10h] BYREF
  HKEY__ *hkeyTmp; // [rsp+50h] [rbp+18h] BYREF

  v1 = 0;
  hkeyClsid = 0;
  hkeyTmp = 0;
  if ( (int)InternalRegOpenClassKey(rclsid, 131097, &hkeyClsid) >= 0 )
  {
    if ( !RegOpenKeyExW(hkeyClsid, L"UseCustomLink", 0, 0x20019u, &hkeyTmp) )
    {
      RegCloseKey(hkeyTmp);
      v1 = 1;
    }
    RegCloseKey(hkeyClsid);
  }
  return v1;
}

```

## disassembly

```asm
0x18007d0f4  push    rbx
0x18007d0f6  sub     rsp, 30h
0x18007d0fa  xor     ebx, ebx
0x18007d0fc  lea     r8, [rsp+38h+hkeyClsid]
0x18007d101  mov     edx, 20019h
0x18007d106  mov     [rsp+38h+hkeyClsid], rbx
0x18007d10b  mov     [rsp+38h+hkeyTmp], rbx
0x18007d110  call    cs:__imp_InternalRegOpenClassKey
0x18007d117  nop     dword ptr [rax+rax+00h]
0x18007d11c  test    eax, eax
0x18007d11e  js      short loc_18007D176
0x18007d120  mov     rclsid, [rsp+38h+hkeyClsid]; hKey
0x18007d125  lea     rax, [rsp+38h+hkeyTmp]
0x18007d12a  mov     r9d, 20019h; samDesired
0x18007d130  mov     [rsp+38h+phkResult], rax; phkResult
0x18007d135  xor     r8d, r8d; ulOptions
0x18007d138  lea     rdx, aUsecustomlink; "UseCustomLink"
0x18007d13f  call    cs:__imp_RegOpenKeyExW
0x18007d146  nop     dword ptr [rax+rax+00h]
0x18007d14b  test    eax, eax
0x18007d14d  jnz     short loc_18007D165
0x18007d14f  mov     rclsid, [rsp+38h+hkeyTmp]; hKey
0x18007d154  call    cs:__imp_RegCloseKey
0x18007d15b  nop     dword ptr [rax+rax+00h]
0x18007d160  mov     ebx, 1
0x18007d165  mov     rclsid, [rsp+38h+hkeyClsid]; hKey
0x18007d16a  call    cs:__imp_RegCloseKey
0x18007d171  nop     dword ptr [rax+rax+00h]
0x18007d176  mov     eax, ebx
0x18007d178  add     rsp, 30h
0x18007d17c  pop     rbx
0x18007d17d  retn
```
