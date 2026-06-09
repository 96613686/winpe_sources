# ColorFiltering::ColorFilterHelper::UpdateTransferSettingsGain(ulong)

- ea: `0x1401be694`
- end: `0x1401be793`
- name: `?UpdateTransferSettingsGain@ColorFilterHelper@ColorFiltering@@SAXK@Z`
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
- `0x1401be694`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1401be6f7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1401be6f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401be766`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401be766`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1401be77c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1401be77c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1401be723`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1401be723`

## string_xrefs

- `0x1401be758`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\`
- `0x1401be6e9`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

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
0x1401be694  sub     rsp, 58h
0x1401be698  mov     [rsp+58h+Data], ecx
0x1401be69c  call    ?IsActive@ColorFilterHelper@ColorFiltering@@SA_NXZ; ColorFiltering::ColorFilterHelper::IsActive(void)
0x1401be6a1  test    al, al
0x1401be6a3  jz      loc_1401BE737
0x1401be6a9  mov     [rsp+58h+hKey], 0
0x1401be6b2  lea     rcx, [rsp+58h+hKey]
0x1401be6b7  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1401be6bc  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1401be6c5  mov     [rsp+58h+phkResult], rax; phkResult
0x1401be6ca  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1401be6d3  mov     [rsp+58h+samDesired], 3; samDesired
0x1401be6db  mov     [rsp+58h+dwOptions], 1; dwOptions
0x1401be6e3  xor     r9d, r9d; lpClass
0x1401be6e6  xor     r8d, r8d; Reserved
0x1401be6e9  lea     rdx, aSoftwareMicros_146; "Software\\Microsoft\\Windows NT\\Curren"...
0x1401be6f0  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1401be6f7  call    cs:__imp_RegCreateKeyExW
0x1401be6fd  test    eax, eax
0x1401be6ff  jnz     short loc_1401BE72A
0x1401be701  lea     r9d, [rax+4]; dwType
0x1401be705  mov     [rsp+58h+samDesired], r9d; cbData
0x1401be70a  lea     rax, [rsp+58h+Data]
0x1401be70f  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1401be714  xor     r8d, r8d; Reserved
0x1401be717  lea     rdx, aGain; "Gain"
0x1401be71e  mov     rcx, [rsp+58h+hKey]; hKey
0x1401be723  call    cs:__imp_RegSetValueExW
0x1401be729  nop
0x1401be72a  lea     rcx, [rsp+58h+hKey]
0x1401be72f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401be734  nop
0x1401be735  jmp     short loc_1401BE78E
0x1401be737  mov     [rsp+58h+hKey], 0
0x1401be740  lea     rcx, [rsp+58h+hKey]
0x1401be745  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1401be74a  mov     qword ptr [rsp+58h+dwOptions], rax; phkResult
0x1401be74f  mov     r9d, 0F003Fh; samDesired
0x1401be755  xor     r8d, r8d; ulOptions
0x1401be758  lea     rdx, aSoftwareMicros_148; "Software\\Microsoft\\Windows NT\\Curren"...
0x1401be75f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1401be766  call    cs:__imp_RegOpenKeyExW
0x1401be76c  test    eax, eax
0x1401be76e  jnz     short loc_1401BE783
0x1401be770  lea     rdx, aColorfiltering_0; "colorfiltering"
0x1401be777  mov     rcx, [rsp+58h+hKey]; hKey
0x1401be77c  call    cs:__imp_RegDeleteTreeW
0x1401be782  nop
0x1401be783  lea     rcx, [rsp+58h+hKey]
0x1401be788  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401be78d  nop
0x1401be78e  add     rsp, 58h
0x1401be792  retn
```
