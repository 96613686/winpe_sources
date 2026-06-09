# ColorFiltering::ColorFilterHelper::UpdateTransferSettingsIntensity(ulong)

- ea: `0x1401bce38`
- end: `0x1401bcf50`
- name: `?UpdateTransferSettingsIntensity@ColorFilterHelper@ColorFiltering@@SAXK@Z`
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
- `0x1401bce38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1401bcecd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1401bcecd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1401bce9b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1401bce9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401bcf16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401bcf16`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1401bcf32`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1401bcf32`

## string_xrefs

- `0x1401bce8d`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`
- `0x1401bcf08`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\`

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
0x1401bce38  sub     rsp, 58h
0x1401bce3c  mov     [rsp+58h+Data], ecx
0x1401bce40  call    ?IsActive@ColorFilterHelper@ColorFiltering@@SA_NXZ; ColorFiltering::ColorFilterHelper::IsActive(void)
0x1401bce45  test    al, al
0x1401bce47  jz      loc_1401BCEE7
0x1401bce4d  mov     [rsp+58h+hKey], 0
0x1401bce56  lea     rcx, [rsp+58h+hKey]
0x1401bce5b  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1401bce60  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1401bce69  mov     [rsp+58h+phkResult], rax; phkResult
0x1401bce6e  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1401bce77  mov     [rsp+58h+samDesired], 3; samDesired
0x1401bce7f  mov     [rsp+58h+dwOptions], 1; dwOptions
0x1401bce87  xor     r9d, r9d; lpClass
0x1401bce8a  xor     r8d, r8d; Reserved
0x1401bce8d  lea     rdx, aSoftwareMicros_147; "Software\\Microsoft\\Windows NT\\Curren"...
0x1401bce94  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1401bce9b  call    cs:__imp_RegCreateKeyExW
0x1401bcea2  nop     dword ptr [rax+rax+00h]
0x1401bcea7  test    eax, eax
0x1401bcea9  jnz     short loc_1401BCEDA
0x1401bceab  lea     r9d, [rax+4]; dwType
0x1401bceaf  mov     [rsp+58h+samDesired], r9d; cbData
0x1401bceb4  lea     rax, [rsp+58h+Data]
0x1401bceb9  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1401bcebe  xor     r8d, r8d; Reserved
0x1401bcec1  lea     rdx, aIntensity; "Intensity"
0x1401bcec8  mov     rcx, [rsp+58h+hKey]; hKey
0x1401bcecd  call    cs:__imp_RegSetValueExW
0x1401bced4  nop     dword ptr [rax+rax+00h]
0x1401bced9  nop
0x1401bceda  lea     rcx, [rsp+58h+hKey]
0x1401bcedf  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401bcee4  nop
0x1401bcee5  jmp     short loc_1401BCF4A
0x1401bcee7  mov     [rsp+58h+hKey], 0
0x1401bcef0  lea     rcx, [rsp+58h+hKey]
0x1401bcef5  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1401bcefa  mov     qword ptr [rsp+58h+dwOptions], rax; phkResult
0x1401bceff  mov     r9d, 0F003Fh; samDesired
0x1401bcf05  xor     r8d, r8d; ulOptions
0x1401bcf08  lea     rdx, aSoftwareMicros_149; "Software\\Microsoft\\Windows NT\\Curren"...
0x1401bcf0f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1401bcf16  call    cs:__imp_RegOpenKeyExW
0x1401bcf1d  nop     dword ptr [rax+rax+00h]
0x1401bcf22  test    eax, eax
0x1401bcf24  jnz     short loc_1401BCF3F
0x1401bcf26  lea     rdx, aColorfiltering_0; "colorfiltering"
0x1401bcf2d  mov     rcx, [rsp+58h+hKey]; hKey
0x1401bcf32  call    cs:__imp_RegDeleteTreeW
0x1401bcf39  nop     dword ptr [rax+rax+00h]
0x1401bcf3e  nop
0x1401bcf3f  lea     rcx, [rsp+58h+hKey]
0x1401bcf44  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401bcf49  nop
0x1401bcf4a  add     rsp, 58h
0x1401bcf4e  retn
```
