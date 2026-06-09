# ColorFiltering::ColorFilterHelper::UpdateTransferSettingsActive(bool)

- ea: `0x140023ea0`
- end: `0x140023ff2`
- name: `?UpdateTransferSettingsActive@ColorFilterHelper@ColorFiltering@@SAX_N@Z`
- size: `338`
- prototype: `void __fastcall(bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400227c0`

## callees

- `0x140004b80`
- `0x140005460`
- `0x14001d7b4`
- `0x140023ea0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140023fc1`
- `ADVAPI32!RegOpenKeyExW` at `0x140023fc1`
- `ADVAPI32!RegSetValueExW` at `0x140023f59`
- `ADVAPI32!RegSetValueExW` at `0x140023f59`
- `ADVAPI32!RegCloseKey` at `0x140023ed8`
- `ADVAPI32!RegCloseKey` at `0x140023f89`
- `ADVAPI32!RegCloseKey` at `0x140023ed8`
- `ADVAPI32!RegCloseKey` at `0x140023f89`
- `ADVAPI32!RegCreateKeyExW` at `0x140023f2f`
- `ADVAPI32!RegCreateKeyExW` at `0x140023f2f`
- `ADVAPI32!RegDeleteTreeW` at `0x140023fd6`
- `ADVAPI32!RegDeleteTreeW` at `0x140023fd6`

## string_xrefs

- `0x140023fb3`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\`
- `0x140023f21`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ColorFiltering::ColorFilterHelper::UpdateTransferSettingsActive(unsigned __int8 a1)
{
  int Data; // [rsp+60h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+18h] BYREF

  Data = a1;
  if ( a1 )
  {
    hKey = 0;
    if ( !RegCreateKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATConfig\\colorfiltering",
            0,
            0,
            1u,
            3u,
            0,
            &hKey,
            0) )
      RegSetValueExW(hKey, L"Active", 0, 4u, (const BYTE *)&Data, 4u);
  }
  else
  {
    hKey = 0;
    if ( !RegOpenKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATConfig\\",
            0,
            0xF003Fu,
            &hKey) )
      RegDeleteTreeW(hKey, L"colorfiltering");
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x140023ea0  mov     [rsp-8+arg_18], rbx
0x140023ea5  push    rbp
0x140023ea6  mov     rbp, rsp
0x140023ea9  sub     rsp, 50h
0x140023ead  movzx   eax, cl
0x140023eb0  mov     [rbp+Data], eax
0x140023eb3  test    cl, cl
0x140023eb5  jz      loc_140023F6C
0x140023ebb  mov     [rbp+hKey], 0
0x140023ec3  mov     rbx, [rbp+hKey]
0x140023ec7  test    rbx, rbx
0x140023eca  jz      short loc_140023EE8
0x140023ecc  lea     rcx, [rbp+arg_10]; this
0x140023ed0  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140023ed5  mov     rcx, rbx; hKey
0x140023ed8  call    cs:__imp_RegCloseKey
0x140023ede  lea     rcx, [rbp+arg_10]; this
0x140023ee2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140023ee7  nop
0x140023ee8  mov     [rbp+hKey], 0
0x140023ef0  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x140023ef9  lea     rax, [rbp+hKey]
0x140023efd  mov     [rsp+50h+phkResult], rax; phkResult
0x140023f02  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140023f0b  mov     [rsp+50h+samDesired], 3; samDesired
0x140023f13  mov     [rsp+50h+dwOptions], 1; dwOptions
0x140023f1b  xor     r9d, r9d; lpClass
0x140023f1e  xor     r8d, r8d; Reserved
0x140023f21  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Windows NT\\Curren"...
0x140023f28  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140023f2f  call    cs:__imp_RegCreateKeyExW
0x140023f35  test    eax, eax
0x140023f37  jnz     short loc_140023F60
0x140023f39  lea     r9d, [rax+4]; dwType
0x140023f3d  mov     [rsp+50h+samDesired], r9d; cbData
0x140023f42  lea     rax, [rbp+Data]
0x140023f46  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x140023f4b  xor     r8d, r8d; Reserved
0x140023f4e  lea     rdx, aActive; "Active"
0x140023f55  mov     rcx, [rbp+hKey]; hKey
0x140023f59  call    cs:__imp_RegSetValueExW
0x140023f5f  nop
0x140023f60  lea     rcx, [rbp+hKey]
0x140023f64  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140023f69  nop
0x140023f6a  jmp     short loc_140023FE7
0x140023f6c  mov     [rbp+hKey], 0
0x140023f74  mov     rbx, [rbp+hKey]
0x140023f78  test    rbx, rbx
0x140023f7b  jz      short loc_140023F99
0x140023f7d  lea     rcx, [rbp+arg_10]; this
0x140023f81  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140023f86  mov     rcx, rbx; hKey
0x140023f89  call    cs:__imp_RegCloseKey
0x140023f8f  lea     rcx, [rbp+arg_10]; this
0x140023f93  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140023f98  nop
0x140023f99  mov     [rbp+hKey], 0
0x140023fa1  lea     rax, [rbp+hKey]
0x140023fa5  mov     qword ptr [rsp+50h+dwOptions], rax; phkResult
0x140023faa  mov     r9d, 0F003Fh; samDesired
0x140023fb0  xor     r8d, r8d; ulOptions
0x140023fb3  lea     rdx, aSoftwareMicros_18; "Software\\Microsoft\\Windows NT\\Curren"...
0x140023fba  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140023fc1  call    cs:__imp_RegOpenKeyExW
0x140023fc7  test    eax, eax
0x140023fc9  jnz     short loc_140023FDD
0x140023fcb  lea     rdx, aColorfiltering_0; "colorfiltering"
0x140023fd2  mov     rcx, [rbp+hKey]; hKey
0x140023fd6  call    cs:__imp_RegDeleteTreeW
0x140023fdc  nop
0x140023fdd  lea     rcx, [rbp+hKey]
0x140023fe1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140023fe6  nop
0x140023fe7  mov     rbx, [rsp+50h+arg_18]
0x140023fec  add     rsp, 50h
0x140023ff0  pop     rbp
0x140023ff1  retn
```
