# ColorFiltering::ColorFilterHelper::UpdateTransferSettingsGain(ulong)

- ea: `0x1401bcd18`
- end: `0x1401bce30`
- name: `?UpdateTransferSettingsGain@ColorFilterHelper@ColorFiltering@@SAXK@Z`
- size: `280`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1401bc3e8`

## callees

- `0x140047f0c`
- `0x14007bf4c`
- `0x1401bb3e4`
- `0x1401bcd18`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1401bcdad`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1401bcdad`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1401bcd7b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1401bcd7b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401bcdf6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401bcdf6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1401bce12`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1401bce12`

## string_xrefs

- `0x1401bcd6d`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`
- `0x1401bcde8`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\`

## pseudocode

```c
void __fastcall ColorFiltering::ColorFilterHelper::UpdateTransferSettingsGain(int a1)
{
  HKEY *phkResult; // rax
  HKEY *v2; // rax
  int Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  Data = a1;
  if ( ColorFiltering::ColorFilterHelper::IsActive() )
  {
    hKey = 0;
    phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    if ( !RegCreateKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATConfig\\colorfiltering",
            0,
            0,
            1u,
            3u,
            0,
            phkResult,
            0) )
      RegSetValueExW(hKey, L"Gain", 0, 4u, (const BYTE *)&Data, 4u);
  }
  else
  {
    hKey = 0;
    v2 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    if ( !RegOpenKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATConfig\\",
            0,
            0xF003Fu,
            v2) )
      RegDeleteTreeW(hKey, L"colorfiltering");
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x1401bcd18  sub     rsp, 58h
0x1401bcd1c  mov     [rsp+58h+Data], ecx
0x1401bcd20  call    ?IsActive@ColorFilterHelper@ColorFiltering@@SA_NXZ; ColorFiltering::ColorFilterHelper::IsActive(void)
0x1401bcd25  test    al, al
0x1401bcd27  jz      loc_1401BCDC7
0x1401bcd2d  mov     [rsp+58h+hKey], 0
0x1401bcd36  lea     rcx, [rsp+58h+hKey]
0x1401bcd3b  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1401bcd40  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1401bcd49  mov     [rsp+58h+phkResult], rax; phkResult
0x1401bcd4e  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1401bcd57  mov     [rsp+58h+samDesired], 3; samDesired
0x1401bcd5f  mov     [rsp+58h+dwOptions], 1; dwOptions
0x1401bcd67  xor     r9d, r9d; lpClass
0x1401bcd6a  xor     r8d, r8d; Reserved
0x1401bcd6d  lea     rdx, aSoftwareMicros_147; "Software\\Microsoft\\Windows NT\\Curren"...
0x1401bcd74  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1401bcd7b  call    cs:__imp_RegCreateKeyExW
0x1401bcd82  nop     dword ptr [rax+rax+00h]
0x1401bcd87  test    eax, eax
0x1401bcd89  jnz     short loc_1401BCDBA
0x1401bcd8b  lea     r9d, [rax+4]; dwType
0x1401bcd8f  mov     [rsp+58h+samDesired], r9d; cbData
0x1401bcd94  lea     rax, [rsp+58h+Data]
0x1401bcd99  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1401bcd9e  xor     r8d, r8d; Reserved
0x1401bcda1  lea     rdx, aGain; "Gain"
0x1401bcda8  mov     rcx, [rsp+58h+hKey]; hKey
0x1401bcdad  call    cs:__imp_RegSetValueExW
0x1401bcdb4  nop     dword ptr [rax+rax+00h]
0x1401bcdb9  nop
0x1401bcdba  lea     rcx, [rsp+58h+hKey]
0x1401bcdbf  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401bcdc4  nop
0x1401bcdc5  jmp     short loc_1401BCE2A
0x1401bcdc7  mov     [rsp+58h+hKey], 0
0x1401bcdd0  lea     rcx, [rsp+58h+hKey]
0x1401bcdd5  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1401bcdda  mov     qword ptr [rsp+58h+dwOptions], rax; phkResult
0x1401bcddf  mov     r9d, 0F003Fh; samDesired
0x1401bcde5  xor     r8d, r8d; ulOptions
0x1401bcde8  lea     rdx, aSoftwareMicros_149; "Software\\Microsoft\\Windows NT\\Curren"...
0x1401bcdef  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1401bcdf6  call    cs:__imp_RegOpenKeyExW
0x1401bcdfd  nop     dword ptr [rax+rax+00h]
0x1401bce02  test    eax, eax
0x1401bce04  jnz     short loc_1401BCE1F
0x1401bce06  lea     rdx, aColorfiltering_0; "colorfiltering"
0x1401bce0d  mov     rcx, [rsp+58h+hKey]; hKey
0x1401bce12  call    cs:__imp_RegDeleteTreeW
0x1401bce19  nop     dword ptr [rax+rax+00h]
0x1401bce1e  nop
0x1401bce1f  lea     rcx, [rsp+58h+hKey]
0x1401bce24  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401bce29  nop
0x1401bce2a  add     rsp, 58h
0x1401bce2e  retn
```
