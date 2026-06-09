# ColorFiltering::ColorFilterHelper::UpdateTransferSettingsActive(bool)

- ea: `0x1401be488`
- end: `0x1401be585`
- name: `?UpdateTransferSettingsActive@ColorFilterHelper@ColorFiltering@@SAX_N@Z`
- size: `253`
- prototype: `void __fastcall(bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1401bcda0`

## callees

- `0x140076e00`
- `0x140078078`
- `0x1401be488`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1401be4e9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1401be4e9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401be558`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401be558`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1401be56e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1401be56e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1401be515`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1401be515`

## string_xrefs

- `0x1401be54a`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\`
- `0x1401be4db`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ColorFiltering::ColorFilterHelper::UpdateTransferSettingsActive(unsigned __int8 a1)
{
  HKEY *phkResult; // rax
  HKEY *v2; // rax
  int Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  Data = a1;
  if ( a1 )
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
      RegSetValueExW(hKey, L"Active", 0, 4u, (const BYTE *)&Data, 4u);
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
0x1401be488  sub     rsp, 58h
0x1401be48c  movzx   eax, cl
0x1401be48f  mov     [rsp+58h+Data], eax
0x1401be493  test    cl, cl
0x1401be495  jz      loc_1401BE529
0x1401be49b  mov     [rsp+58h+hKey], 0
0x1401be4a4  lea     rcx, [rsp+58h+hKey]
0x1401be4a9  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1401be4ae  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1401be4b7  mov     [rsp+58h+phkResult], rax; phkResult
0x1401be4bc  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1401be4c5  mov     [rsp+58h+samDesired], 3; samDesired
0x1401be4cd  mov     [rsp+58h+dwOptions], 1; dwOptions
0x1401be4d5  xor     r9d, r9d; lpClass
0x1401be4d8  xor     r8d, r8d; Reserved
0x1401be4db  lea     rdx, aSoftwareMicros_146; "Software\\Microsoft\\Windows NT\\Curren"...
0x1401be4e2  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1401be4e9  call    cs:__imp_RegCreateKeyExW
0x1401be4ef  test    eax, eax
0x1401be4f1  jnz     short loc_1401BE51C
0x1401be4f3  lea     r9d, [rax+4]; dwType
0x1401be4f7  mov     [rsp+58h+samDesired], r9d; cbData
0x1401be4fc  lea     rax, [rsp+58h+Data]
0x1401be501  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1401be506  xor     r8d, r8d; Reserved
0x1401be509  lea     rdx, aActive; "Active"
0x1401be510  mov     rcx, [rsp+58h+hKey]; hKey
0x1401be515  call    cs:__imp_RegSetValueExW
0x1401be51b  nop
0x1401be51c  lea     rcx, [rsp+58h+hKey]
0x1401be521  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401be526  nop
0x1401be527  jmp     short loc_1401BE580
0x1401be529  mov     [rsp+58h+hKey], 0
0x1401be532  lea     rcx, [rsp+58h+hKey]
0x1401be537  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1401be53c  mov     qword ptr [rsp+58h+dwOptions], rax; phkResult
0x1401be541  mov     r9d, 0F003Fh; samDesired
0x1401be547  xor     r8d, r8d; ulOptions
0x1401be54a  lea     rdx, aSoftwareMicros_148; "Software\\Microsoft\\Windows NT\\Curren"...
0x1401be551  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1401be558  call    cs:__imp_RegOpenKeyExW
0x1401be55e  test    eax, eax
0x1401be560  jnz     short loc_1401BE575
0x1401be562  lea     rdx, aColorfiltering_0; "colorfiltering"
0x1401be569  mov     rcx, [rsp+58h+hKey]; hKey
0x1401be56e  call    cs:__imp_RegDeleteTreeW
0x1401be574  nop
0x1401be575  lea     rcx, [rsp+58h+hKey]
0x1401be57a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401be57f  nop
0x1401be580  add     rsp, 58h
0x1401be584  retn
```
