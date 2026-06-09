# ColorFiltering::ColorFilterHelper::UpdateTransferSettingsFilterType(ulong)

- ea: `0x1401be58c`
- end: `0x1401be68b`
- name: `?UpdateTransferSettingsFilterType@ColorFilterHelper@ColorFiltering@@SAXK@Z`
- size: `255`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1401bdda0`

## callees

- `0x140076e00`
- `0x140078078`
- `0x1401bcda0`
- `0x1401be58c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1401be5ef`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1401be5ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401be65e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401be65e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1401be674`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1401be674`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1401be61b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1401be61b`

## string_xrefs

- `0x1401be650`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\`
- `0x1401be5e1`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

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
0x1401be58c  sub     rsp, 58h
0x1401be590  mov     [rsp+58h+Data], ecx
0x1401be594  call    ?IsActive@ColorFilterHelper@ColorFiltering@@SA_NXZ; ColorFiltering::ColorFilterHelper::IsActive(void)
0x1401be599  test    al, al
0x1401be59b  jz      loc_1401BE62F
0x1401be5a1  mov     [rsp+58h+hKey], 0
0x1401be5aa  lea     rcx, [rsp+58h+hKey]
0x1401be5af  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1401be5b4  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1401be5bd  mov     [rsp+58h+phkResult], rax; phkResult
0x1401be5c2  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1401be5cb  mov     [rsp+58h+samDesired], 3; samDesired
0x1401be5d3  mov     [rsp+58h+dwOptions], 1; dwOptions
0x1401be5db  xor     r9d, r9d; lpClass
0x1401be5de  xor     r8d, r8d; Reserved
0x1401be5e1  lea     rdx, aSoftwareMicros_146; "Software\\Microsoft\\Windows NT\\Curren"...
0x1401be5e8  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1401be5ef  call    cs:__imp_RegCreateKeyExW
0x1401be5f5  test    eax, eax
0x1401be5f7  jnz     short loc_1401BE622
0x1401be5f9  lea     r9d, [rax+4]; dwType
0x1401be5fd  mov     [rsp+58h+samDesired], r9d; cbData
0x1401be602  lea     rax, [rsp+58h+Data]
0x1401be607  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1401be60c  xor     r8d, r8d; Reserved
0x1401be60f  lea     rdx, aFiltertype; "FilterType"
0x1401be616  mov     rcx, [rsp+58h+hKey]; hKey
0x1401be61b  call    cs:__imp_RegSetValueExW
0x1401be621  nop
0x1401be622  lea     rcx, [rsp+58h+hKey]
0x1401be627  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401be62c  nop
0x1401be62d  jmp     short loc_1401BE686
0x1401be62f  mov     [rsp+58h+hKey], 0
0x1401be638  lea     rcx, [rsp+58h+hKey]
0x1401be63d  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1401be642  mov     qword ptr [rsp+58h+dwOptions], rax; phkResult
0x1401be647  mov     r9d, 0F003Fh; samDesired
0x1401be64d  xor     r8d, r8d; ulOptions
0x1401be650  lea     rdx, aSoftwareMicros_148; "Software\\Microsoft\\Windows NT\\Curren"...
0x1401be657  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1401be65e  call    cs:__imp_RegOpenKeyExW
0x1401be664  test    eax, eax
0x1401be666  jnz     short loc_1401BE67B
0x1401be668  lea     rdx, aColorfiltering_0; "colorfiltering"
0x1401be66f  mov     rcx, [rsp+58h+hKey]; hKey
0x1401be674  call    cs:__imp_RegDeleteTreeW
0x1401be67a  nop
0x1401be67b  lea     rcx, [rsp+58h+hKey]
0x1401be680  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401be685  nop
0x1401be686  add     rsp, 58h
0x1401be68a  retn
```
