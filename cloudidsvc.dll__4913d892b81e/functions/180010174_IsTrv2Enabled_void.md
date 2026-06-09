# IsTrv2Enabled(void)

- ea: `0x180010174`
- end: `0x180010262`
- name: `?IsTrv2Enabled@@YA_NXZ`
- size: `238`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b1d0`

## callees

- `0x18000a864`
- `0x18000ca74`
- `0x180010174`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800101b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800101b2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001022a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001022a`

## pseudocode

```c
bool IsTrv2Enabled(void)
{
  bool v0; // bl
  LSTATUS v1; // eax
  bool v2; // zf
  LSTATUS v3; // eax
  bool v4; // zf
  DWORD cValues; // [rsp+70h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  hKey = 0;
  v0 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\Windows\\TenantRestrictions\\Payload",
         0,
         0x20119u,
         &hKey);
  v2 = v1 == 0;
  if ( v1 > 0 )
    v2 = 0;
  if ( v2 )
  {
    cValues = 0;
    v3 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
    v4 = v3 == 0;
    if ( v3 > 0 )
      v4 = 0;
    if ( v4 )
      v0 = cValues != 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v0;
}

```

## disassembly

```asm
0x180010174  push    rbx
0x180010176  sub     rsp, 60h
0x18001017a  xor     edx, edx
0x18001017c  mov     [rsp+68h+hKey], 0
0x180010185  lea     rcx, [rsp+68h+hKey]
0x18001018a  xor     bl, bl
0x18001018c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180010191  lea     rax, [rsp+68h+hKey]
0x180010196  mov     r9d, 20119h; samDesired
0x18001019c  xor     r8d, r8d; ulOptions
0x18001019f  mov     [rsp+68h+phkResult], rax; phkResult
0x1800101a4  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1800101ab  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800101b2  call    cs:__imp_RegOpenKeyExW
0x1800101b8  test    eax, eax
0x1800101ba  jle     short loc_1800101C6
0x1800101bc  movzx   eax, ax
0x1800101bf  or      eax, 80070000h
0x1800101c4  test    eax, eax
0x1800101c6  jnz     loc_180010250
0x1800101cc  mov     rcx, [rsp+68h+hKey]; hKey
0x1800101d1  lea     rax, [rsp+68h+cValues]
0x1800101d6  mov     [rsp+68h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800101df  xor     r9d, r9d; lpReserved
0x1800101e2  mov     [rsp+68h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x1800101eb  xor     r8d, r8d; lpcchClass
0x1800101ee  mov     [rsp+68h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x1800101f7  xor     edx, edx; lpClass
0x1800101f9  mov     [rsp+68h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x180010202  mov     [rsp+68h+lpcValues], rax; lpcValues
0x180010207  mov     [rsp+68h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x180010210  mov     [rsp+68h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x180010219  mov     [rsp+68h+phkResult], 0; lpcSubKeys
0x180010222  mov     [rsp+68h+cValues], 0
0x18001022a  call    cs:__imp_RegQueryInfoKeyW
0x180010230  test    eax, eax
0x180010232  jle     short loc_18001023E
0x180010234  movzx   eax, ax
0x180010237  or      eax, 80070000h
0x18001023c  test    eax, eax
0x18001023e  jnz     short loc_180010250
0x180010240  cmp     [rsp+68h+cValues], 0
0x180010245  mov     eax, 1
0x18001024a  movzx   ebx, bl
0x18001024d  cmova   ebx, eax
0x180010250  lea     rcx, [rsp+68h+hKey]
0x180010255  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001025a  mov     al, bl
0x18001025c  add     rsp, 60h
0x180010260  pop     rbx
0x180010261  retn
```
