# ColorFiltering::ColorFilterHelper::UpdateTransferSettingsFilterType(ulong)

- ea: `0x140023ff8`
- end: `0x14002414c`
- name: `?UpdateTransferSettingsFilterType@ColorFilterHelper@ColorFiltering@@SAXK@Z`
- size: `340`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400237b8`

## callees

- `0x140004b80`
- `0x140005460`
- `0x14001d7b4`
- `0x1400227c0`
- `0x140023ff8`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14002411b`
- `ADVAPI32!RegOpenKeyExW` at `0x14002411b`
- `ADVAPI32!RegSetValueExW` at `0x1400240b3`
- `ADVAPI32!RegSetValueExW` at `0x1400240b3`
- `ADVAPI32!RegCloseKey` at `0x140024032`
- `ADVAPI32!RegCloseKey` at `0x1400240e3`
- `ADVAPI32!RegCloseKey` at `0x140024032`
- `ADVAPI32!RegCloseKey` at `0x1400240e3`
- `ADVAPI32!RegCreateKeyExW` at `0x140024089`
- `ADVAPI32!RegCreateKeyExW` at `0x140024089`
- `ADVAPI32!RegDeleteTreeW` at `0x140024130`
- `ADVAPI32!RegDeleteTreeW` at `0x140024130`

## string_xrefs

- `0x14002410d`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\`
- `0x14002407b`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ColorFiltering::ColorFilterHelper::UpdateTransferSettingsFilterType(int a1)
{
  int Data; // [rsp+60h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+18h] BYREF

  Data = a1;
  if ( ColorFiltering::ColorFilterHelper::IsActive() )
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
      RegSetValueExW(hKey, L"FilterType", 0, 4u, (const BYTE *)&Data, 4u);
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
0x140023ff8  mov     [rsp-8+arg_18], rbx
0x140023ffd  push    rbp
0x140023ffe  mov     rbp, rsp
0x140024001  sub     rsp, 50h
0x140024005  mov     [rbp+Data], ecx
0x140024008  call    ?IsActive@ColorFilterHelper@ColorFiltering@@SA_NXZ; ColorFiltering::ColorFilterHelper::IsActive(void)
0x14002400d  test    al, al
0x14002400f  jz      loc_1400240C6
0x140024015  mov     [rbp+hKey], 0
0x14002401d  mov     rbx, [rbp+hKey]
0x140024021  test    rbx, rbx
0x140024024  jz      short loc_140024042
0x140024026  lea     rcx, [rbp+arg_10]; this
0x14002402a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14002402f  mov     rcx, rbx; hKey
0x140024032  call    cs:__imp_RegCloseKey
0x140024038  lea     rcx, [rbp+arg_10]; this
0x14002403c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140024041  nop
0x140024042  mov     [rbp+hKey], 0
0x14002404a  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x140024053  lea     rax, [rbp+hKey]
0x140024057  mov     [rsp+50h+phkResult], rax; phkResult
0x14002405c  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140024065  mov     [rsp+50h+samDesired], 3; samDesired
0x14002406d  mov     [rsp+50h+dwOptions], 1; dwOptions
0x140024075  xor     r9d, r9d; lpClass
0x140024078  xor     r8d, r8d; Reserved
0x14002407b  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Windows NT\\Curren"...
0x140024082  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140024089  call    cs:__imp_RegCreateKeyExW
0x14002408f  test    eax, eax
0x140024091  jnz     short loc_1400240BA
0x140024093  lea     r9d, [rax+4]; dwType
0x140024097  mov     [rsp+50h+samDesired], r9d; cbData
0x14002409c  lea     rax, [rbp+Data]
0x1400240a0  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x1400240a5  xor     r8d, r8d; Reserved
0x1400240a8  lea     rdx, aFiltertype; "FilterType"
0x1400240af  mov     rcx, [rbp+hKey]; hKey
0x1400240b3  call    cs:__imp_RegSetValueExW
0x1400240b9  nop
0x1400240ba  lea     rcx, [rbp+hKey]
0x1400240be  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400240c3  nop
0x1400240c4  jmp     short loc_140024141
0x1400240c6  mov     [rbp+hKey], 0
0x1400240ce  mov     rbx, [rbp+hKey]
0x1400240d2  test    rbx, rbx
0x1400240d5  jz      short loc_1400240F3
0x1400240d7  lea     rcx, [rbp+arg_10]; this
0x1400240db  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1400240e0  mov     rcx, rbx; hKey
0x1400240e3  call    cs:__imp_RegCloseKey
0x1400240e9  lea     rcx, [rbp+arg_10]; this
0x1400240ed  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1400240f2  nop
0x1400240f3  mov     [rbp+hKey], 0
0x1400240fb  lea     rax, [rbp+hKey]
0x1400240ff  mov     qword ptr [rsp+50h+dwOptions], rax; phkResult
0x140024104  mov     r9d, 0F003Fh; samDesired
0x14002410a  xor     r8d, r8d; ulOptions
0x14002410d  lea     rdx, aSoftwareMicros_18; "Software\\Microsoft\\Windows NT\\Curren"...
0x140024114  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14002411b  call    cs:__imp_RegOpenKeyExW
0x140024121  test    eax, eax
0x140024123  jnz     short loc_140024137
0x140024125  lea     rdx, aColorfiltering_0; "colorfiltering"
0x14002412c  mov     rcx, [rbp+hKey]; hKey
0x140024130  call    cs:__imp_RegDeleteTreeW
0x140024136  nop
0x140024137  lea     rcx, [rbp+hKey]
0x14002413b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140024140  nop
0x140024141  mov     rbx, [rsp+50h+arg_18]
0x140024146  add     rsp, 50h
0x14002414a  pop     rbp
0x14002414b  retn
```
