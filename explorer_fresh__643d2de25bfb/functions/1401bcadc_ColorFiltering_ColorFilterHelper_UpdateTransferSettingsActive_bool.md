# ColorFiltering::ColorFilterHelper::UpdateTransferSettingsActive(bool)

- ea: `0x1401bcadc`
- end: `0x1401bcbf2`
- name: `?UpdateTransferSettingsActive@ColorFilterHelper@ColorFiltering@@SAX_N@Z`
- size: `278`
- prototype: `void __fastcall(bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1401bb3e4`

## callees

- `0x140047f0c`
- `0x14007bf4c`
- `0x1401bcadc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1401bcb6f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1401bcb6f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1401bcb3d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1401bcb3d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401bcbb8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401bcbb8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1401bcbd4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1401bcbd4`

## string_xrefs

- `0x1401bcb2f`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`
- `0x1401bcbaa`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\`

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
0x1401bcadc  sub     rsp, 58h
0x1401bcae0  movzx   eax, cl
0x1401bcae3  mov     [rsp+58h+Data], eax
0x1401bcae7  test    cl, cl
0x1401bcae9  jz      loc_1401BCB89
0x1401bcaef  mov     [rsp+58h+hKey], 0
0x1401bcaf8  lea     rcx, [rsp+58h+hKey]
0x1401bcafd  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1401bcb02  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1401bcb0b  mov     [rsp+58h+phkResult], rax; phkResult
0x1401bcb10  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1401bcb19  mov     [rsp+58h+samDesired], 3; samDesired
0x1401bcb21  mov     [rsp+58h+dwOptions], 1; dwOptions
0x1401bcb29  xor     r9d, r9d; lpClass
0x1401bcb2c  xor     r8d, r8d; Reserved
0x1401bcb2f  lea     rdx, aSoftwareMicros_147; "Software\\Microsoft\\Windows NT\\Curren"...
0x1401bcb36  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1401bcb3d  call    cs:__imp_RegCreateKeyExW
0x1401bcb44  nop     dword ptr [rax+rax+00h]
0x1401bcb49  test    eax, eax
0x1401bcb4b  jnz     short loc_1401BCB7C
0x1401bcb4d  lea     r9d, [rax+4]; dwType
0x1401bcb51  mov     [rsp+58h+samDesired], r9d; cbData
0x1401bcb56  lea     rax, [rsp+58h+Data]
0x1401bcb5b  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1401bcb60  xor     r8d, r8d; Reserved
0x1401bcb63  lea     rdx, aActive; "Active"
0x1401bcb6a  mov     rcx, [rsp+58h+hKey]; hKey
0x1401bcb6f  call    cs:__imp_RegSetValueExW
0x1401bcb76  nop     dword ptr [rax+rax+00h]
0x1401bcb7b  nop
0x1401bcb7c  lea     rcx, [rsp+58h+hKey]
0x1401bcb81  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401bcb86  nop
0x1401bcb87  jmp     short loc_1401BCBEC
0x1401bcb89  mov     [rsp+58h+hKey], 0
0x1401bcb92  lea     rcx, [rsp+58h+hKey]
0x1401bcb97  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1401bcb9c  mov     qword ptr [rsp+58h+dwOptions], rax; phkResult
0x1401bcba1  mov     r9d, 0F003Fh; samDesired
0x1401bcba7  xor     r8d, r8d; ulOptions
0x1401bcbaa  lea     rdx, aSoftwareMicros_149; "Software\\Microsoft\\Windows NT\\Curren"...
0x1401bcbb1  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1401bcbb8  call    cs:__imp_RegOpenKeyExW
0x1401bcbbf  nop     dword ptr [rax+rax+00h]
0x1401bcbc4  test    eax, eax
0x1401bcbc6  jnz     short loc_1401BCBE1
0x1401bcbc8  lea     rdx, aColorfiltering_0; "colorfiltering"
0x1401bcbcf  mov     rcx, [rsp+58h+hKey]; hKey
0x1401bcbd4  call    cs:__imp_RegDeleteTreeW
0x1401bcbdb  nop     dword ptr [rax+rax+00h]
0x1401bcbe0  nop
0x1401bcbe1  lea     rcx, [rsp+58h+hKey]
0x1401bcbe6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401bcbeb  nop
0x1401bcbec  add     rsp, 58h
0x1401bcbf0  retn
```
