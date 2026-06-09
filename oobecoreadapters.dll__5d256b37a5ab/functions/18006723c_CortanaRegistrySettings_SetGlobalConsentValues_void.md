# CortanaRegistrySettings::SetGlobalConsentValues(void)

- ea: `0x18006723c`
- end: `0x180067354`
- name: `?SetGlobalConsentValues@CortanaRegistrySettings@@YAJXZ`
- size: `280`
- prototype: `__int64 __fastcall(CortanaRegistrySettings *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180060418`

## callees

- `0x180009834`
- `0x18000ac54`
- `0x18000b254`
- `0x18006723c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800672c2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180067336`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800672c2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180067336`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180067279`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180067279`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180067303`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180067303`

## pseudocode

```c
__int64 __fastcall CortanaRegistrySettings::SetGlobalConsentValues(CortanaRegistrySettings *this)
{
  LSTATUS v1; // eax
  unsigned int v2; // ebx
  int v3; // eax
  bool v4; // cc
  int Data; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF
  __int64 v8; // [rsp+60h] [rbp+28h] BYREF
  __int64 v9; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v1 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\CurrentVersion\\Search", 0, 0x20006u, &hKey);
  v2 = v1;
  if ( v1 )
  {
    if ( v1 > 0 )
      v2 = (unsigned __int16)v1 | 0x80070000;
  }
  else
  {
    Data = 1;
    v3 = RegSetValueExW(hKey, L"CortanaGlobalConsent", 0, 4u, (const BYTE *)&Data, 4u);
    v4 = v3 <= 0;
    if ( v3
      || (v3 = SHRegSetString(hKey, 0, L"CortanaGlobalConsentVersion", L"1.0"), v4 = v3 <= 0, v3)
      || (v8 = 0,
          GetSystemTimePreciseAsFileTime(&v8),
          v9 = v8,
          v3 = RegSetValueExW(hKey, L"CortanaGlobalConsentDate", 0, 0xBu, (const BYTE *)&v9, 8u),
          v4 = v3 <= 0,
          v3) )
    {
      if ( !v4 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      v2 = v3;
    }
    else
    {
      v2 = 0;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v2;
}

```

## disassembly

```asm
0x18006723c  push    rbp
0x18006723e  push    rbx
0x18006723f  mov     rbp, rsp
0x180067242  sub     rsp, 38h
0x180067246  xor     edx, edx
0x180067248  mov     [rbp+hKey], 0
0x180067250  lea     rcx, [rbp+hKey]
0x180067254  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180067259  lea     rax, [rbp+hKey]
0x18006725d  mov     r9d, 20006h; samDesired
0x180067263  xor     r8d, r8d; ulOptions
0x180067266  mov     [rsp+38h+phkResult], rax; phkResult
0x18006726b  lea     rdx, aSoftwareMicros_15; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180067272  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180067279  call    cs:__imp_RegOpenKeyExW
0x18006727f  mov     ebx, eax
0x180067281  test    eax, eax
0x180067283  jz      short loc_180067299
0x180067285  jle     loc_180067342
0x18006728b  movzx   ebx, ax
0x18006728e  or      ebx, 80070000h
0x180067294  jmp     loc_180067342
0x180067299  mov     rcx, [rbp+hKey]; hKey
0x18006729d  lea     rax, [rbp+Data]
0x1800672a1  mov     r9d, 4; dwType
0x1800672a7  mov     [rbp+Data], 1
0x1800672ae  mov     [rsp+38h+cbData], r9d; cbData
0x1800672b3  lea     rdx, aCortanaglobalc; "CortanaGlobalConsent"
0x1800672ba  xor     r8d, r8d; Reserved
0x1800672bd  mov     [rsp+38h+phkResult], rax; lpData
0x1800672c2  call    cs:__imp_RegSetValueExW
0x1800672c8  test    eax, eax
0x1800672ca  jz      short loc_1800672DA
0x1800672cc  jle     short loc_1800672D6
0x1800672ce  movzx   eax, ax
0x1800672d1  or      eax, 80070000h
0x1800672d6  mov     ebx, eax
0x1800672d8  jmp     short loc_180067342
0x1800672da  mov     rcx, [rbp+hKey]; HKEY
0x1800672de  lea     r9, a10; "1.0"
0x1800672e5  lea     r8, aCortanaglobalc_0; "CortanaGlobalConsentVersion"
0x1800672ec  xor     edx, edx; unsigned __int16 *
0x1800672ee  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800672f3  test    eax, eax
0x1800672f5  jnz     short loc_1800672CC
0x1800672f7  lea     rcx, [rbp+arg_10]
0x1800672fb  mov     [rbp+arg_10], 0
0x180067303  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x180067309  mov     rax, [rbp+arg_10]
0x18006730d  lea     rdx, aCortanaglobalc_1; "CortanaGlobalConsentDate"
0x180067314  mov     rcx, [rbp+hKey]; hKey
0x180067318  mov     r9d, 0Bh; dwType
0x18006731e  mov     [rbp+arg_18], rax
0x180067322  xor     r8d, r8d; Reserved
0x180067325  lea     rax, [rbp+arg_18]
0x180067329  mov     [rsp+38h+cbData], 8; cbData
0x180067331  mov     [rsp+38h+phkResult], rax; lpData
0x180067336  call    cs:__imp_RegSetValueExW
0x18006733c  test    eax, eax
0x18006733e  jnz     short loc_1800672CC
0x180067340  xor     ebx, ebx
0x180067342  lea     rcx, [rbp+hKey]
0x180067346  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006734b  mov     eax, ebx
0x18006734d  add     rsp, 38h
0x180067351  pop     rbx
0x180067352  pop     rbp
0x180067353  retn
```
