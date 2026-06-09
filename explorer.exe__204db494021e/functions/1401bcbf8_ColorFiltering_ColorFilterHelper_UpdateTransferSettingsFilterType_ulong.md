# ColorFiltering::ColorFilterHelper::UpdateTransferSettingsFilterType(ulong)

- ea: `0x1401bcbf8`
- end: `0x1401bcd10`
- name: `?UpdateTransferSettingsFilterType@ColorFilterHelper@ColorFiltering@@SAXK@Z`
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
- `0x1401bcbf8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1401bcc8d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1401bcc8d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1401bcc5b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1401bcc5b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401bccd6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401bccd6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1401bccf2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1401bccf2`

## string_xrefs

- `0x1401bcc4d`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`
- `0x1401bccc8`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ColorFiltering::ColorFilterHelper::UpdateTransferSettingsFilterType(int a1)
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
      RegSetValueExW(hKey, L"FilterType", 0, 4u, (const BYTE *)&Data, 4u);
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
0x1401bcbf8  sub     rsp, 58h
0x1401bcbfc  mov     [rsp+58h+Data], ecx
0x1401bcc00  call    ?IsActive@ColorFilterHelper@ColorFiltering@@SA_NXZ; ColorFiltering::ColorFilterHelper::IsActive(void)
0x1401bcc05  test    al, al
0x1401bcc07  jz      loc_1401BCCA7
0x1401bcc0d  mov     [rsp+58h+hKey], 0
0x1401bcc16  lea     rcx, [rsp+58h+hKey]
0x1401bcc1b  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1401bcc20  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1401bcc29  mov     [rsp+58h+phkResult], rax; phkResult
0x1401bcc2e  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1401bcc37  mov     [rsp+58h+samDesired], 3; samDesired
0x1401bcc3f  mov     [rsp+58h+dwOptions], 1; dwOptions
0x1401bcc47  xor     r9d, r9d; lpClass
0x1401bcc4a  xor     r8d, r8d; Reserved
0x1401bcc4d  lea     rdx, aSoftwareMicros_147; "Software\\Microsoft\\Windows NT\\Curren"...
0x1401bcc54  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1401bcc5b  call    cs:__imp_RegCreateKeyExW
0x1401bcc62  nop     dword ptr [rax+rax+00h]
0x1401bcc67  test    eax, eax
0x1401bcc69  jnz     short loc_1401BCC9A
0x1401bcc6b  lea     r9d, [rax+4]; dwType
0x1401bcc6f  mov     [rsp+58h+samDesired], r9d; cbData
0x1401bcc74  lea     rax, [rsp+58h+Data]
0x1401bcc79  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1401bcc7e  xor     r8d, r8d; Reserved
0x1401bcc81  lea     rdx, aFiltertype; "FilterType"
0x1401bcc88  mov     rcx, [rsp+58h+hKey]; hKey
0x1401bcc8d  call    cs:__imp_RegSetValueExW
0x1401bcc94  nop     dword ptr [rax+rax+00h]
0x1401bcc99  nop
0x1401bcc9a  lea     rcx, [rsp+58h+hKey]
0x1401bcc9f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401bcca4  nop
0x1401bcca5  jmp     short loc_1401BCD0A
0x1401bcca7  mov     [rsp+58h+hKey], 0
0x1401bccb0  lea     rcx, [rsp+58h+hKey]
0x1401bccb5  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1401bccba  mov     qword ptr [rsp+58h+dwOptions], rax; phkResult
0x1401bccbf  mov     r9d, 0F003Fh; samDesired
0x1401bccc5  xor     r8d, r8d; ulOptions
0x1401bccc8  lea     rdx, aSoftwareMicros_149; "Software\\Microsoft\\Windows NT\\Curren"...
0x1401bcccf  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1401bccd6  call    cs:__imp_RegOpenKeyExW
0x1401bccdd  nop     dword ptr [rax+rax+00h]
0x1401bcce2  test    eax, eax
0x1401bcce4  jnz     short loc_1401BCCFF
0x1401bcce6  lea     rdx, aColorfiltering_0; "colorfiltering"
0x1401bcced  mov     rcx, [rsp+58h+hKey]; hKey
0x1401bccf2  call    cs:__imp_RegDeleteTreeW
0x1401bccf9  nop     dword ptr [rax+rax+00h]
0x1401bccfe  nop
0x1401bccff  lea     rcx, [rsp+58h+hKey]
0x1401bcd04  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401bcd09  nop
0x1401bcd0a  add     rsp, 58h
0x1401bcd0e  retn
```
