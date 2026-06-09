# ColorFiltering::ColorFilterHelper::UpdateTransferSettingsIntensity(ulong)

- ea: `0x1401be79c`
- end: `0x1401be89b`
- name: `?UpdateTransferSettingsIntensity@ColorFilterHelper@ColorFiltering@@SAXK@Z`
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
- `0x1401be79c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1401be7ff`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1401be7ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401be86e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401be86e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1401be884`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1401be884`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1401be82b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1401be82b`

## string_xrefs

- `0x1401be860`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\`
- `0x1401be7f1`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

## pseudocode

```c
void __fastcall ColorFiltering::ColorFilterHelper::UpdateTransferSettingsIntensity(int a1)
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
      RegSetValueExW(hKey, L"Intensity", 0, 4u, (const BYTE *)&Data, 4u);
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
0x1401be79c  sub     rsp, 58h
0x1401be7a0  mov     [rsp+58h+Data], ecx
0x1401be7a4  call    ?IsActive@ColorFilterHelper@ColorFiltering@@SA_NXZ; ColorFiltering::ColorFilterHelper::IsActive(void)
0x1401be7a9  test    al, al
0x1401be7ab  jz      loc_1401BE83F
0x1401be7b1  mov     [rsp+58h+hKey], 0
0x1401be7ba  lea     rcx, [rsp+58h+hKey]
0x1401be7bf  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1401be7c4  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1401be7cd  mov     [rsp+58h+phkResult], rax; phkResult
0x1401be7d2  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1401be7db  mov     [rsp+58h+samDesired], 3; samDesired
0x1401be7e3  mov     [rsp+58h+dwOptions], 1; dwOptions
0x1401be7eb  xor     r9d, r9d; lpClass
0x1401be7ee  xor     r8d, r8d; Reserved
0x1401be7f1  lea     rdx, aSoftwareMicros_146; "Software\\Microsoft\\Windows NT\\Curren"...
0x1401be7f8  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1401be7ff  call    cs:__imp_RegCreateKeyExW
0x1401be805  test    eax, eax
0x1401be807  jnz     short loc_1401BE832
0x1401be809  lea     r9d, [rax+4]; dwType
0x1401be80d  mov     [rsp+58h+samDesired], r9d; cbData
0x1401be812  lea     rax, [rsp+58h+Data]
0x1401be817  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1401be81c  xor     r8d, r8d; Reserved
0x1401be81f  lea     rdx, aIntensity; "Intensity"
0x1401be826  mov     rcx, [rsp+58h+hKey]; hKey
0x1401be82b  call    cs:__imp_RegSetValueExW
0x1401be831  nop
0x1401be832  lea     rcx, [rsp+58h+hKey]
0x1401be837  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401be83c  nop
0x1401be83d  jmp     short loc_1401BE896
0x1401be83f  mov     [rsp+58h+hKey], 0
0x1401be848  lea     rcx, [rsp+58h+hKey]
0x1401be84d  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1401be852  mov     qword ptr [rsp+58h+dwOptions], rax; phkResult
0x1401be857  mov     r9d, 0F003Fh; samDesired
0x1401be85d  xor     r8d, r8d; ulOptions
0x1401be860  lea     rdx, aSoftwareMicros_148; "Software\\Microsoft\\Windows NT\\Curren"...
0x1401be867  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1401be86e  call    cs:__imp_RegOpenKeyExW
0x1401be874  test    eax, eax
0x1401be876  jnz     short loc_1401BE88B
0x1401be878  lea     rdx, aColorfiltering_0; "colorfiltering"
0x1401be87f  mov     rcx, [rsp+58h+hKey]; hKey
0x1401be884  call    cs:__imp_RegDeleteTreeW
0x1401be88a  nop
0x1401be88b  lea     rcx, [rsp+58h+hKey]
0x1401be890  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401be895  nop
0x1401be896  add     rsp, 58h
0x1401be89a  retn
```
