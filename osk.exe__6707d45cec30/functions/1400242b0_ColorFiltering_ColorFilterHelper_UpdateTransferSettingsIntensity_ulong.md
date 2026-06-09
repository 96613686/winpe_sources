# ColorFiltering::ColorFilterHelper::UpdateTransferSettingsIntensity(ulong)

- ea: `0x1400242b0`
- end: `0x140024404`
- name: `?UpdateTransferSettingsIntensity@ColorFilterHelper@ColorFiltering@@SAXK@Z`
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
- `0x1400242b0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1400243d3`
- `ADVAPI32!RegOpenKeyExW` at `0x1400243d3`
- `ADVAPI32!RegSetValueExW` at `0x14002436b`
- `ADVAPI32!RegSetValueExW` at `0x14002436b`
- `ADVAPI32!RegCloseKey` at `0x1400242ea`
- `ADVAPI32!RegCloseKey` at `0x14002439b`
- `ADVAPI32!RegCloseKey` at `0x1400242ea`
- `ADVAPI32!RegCloseKey` at `0x14002439b`
- `ADVAPI32!RegCreateKeyExW` at `0x140024341`
- `ADVAPI32!RegCreateKeyExW` at `0x140024341`
- `ADVAPI32!RegDeleteTreeW` at `0x1400243e8`
- `ADVAPI32!RegDeleteTreeW` at `0x1400243e8`

## string_xrefs

- `0x1400243c5`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\`
- `0x140024333`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

## pseudocode

```c
void __fastcall ColorFiltering::ColorFilterHelper::UpdateTransferSettingsIntensity(int a1)
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
      RegSetValueExW(hKey, L"Intensity", 0, 4u, (const BYTE *)&Data, 4u);
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
0x1400242b0  mov     [rsp-8+arg_18], rbx
0x1400242b5  push    rbp
0x1400242b6  mov     rbp, rsp
0x1400242b9  sub     rsp, 50h
0x1400242bd  mov     [rbp+Data], ecx
0x1400242c0  call    ?IsActive@ColorFilterHelper@ColorFiltering@@SA_NXZ; ColorFiltering::ColorFilterHelper::IsActive(void)
0x1400242c5  test    al, al
0x1400242c7  jz      loc_14002437E
0x1400242cd  mov     [rbp+hKey], 0
0x1400242d5  mov     rbx, [rbp+hKey]
0x1400242d9  test    rbx, rbx
0x1400242dc  jz      short loc_1400242FA
0x1400242de  lea     rcx, [rbp+arg_10]; this
0x1400242e2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1400242e7  mov     rcx, rbx; hKey
0x1400242ea  call    cs:__imp_RegCloseKey
0x1400242f0  lea     rcx, [rbp+arg_10]; this
0x1400242f4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1400242f9  nop
0x1400242fa  mov     [rbp+hKey], 0
0x140024302  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x14002430b  lea     rax, [rbp+hKey]
0x14002430f  mov     [rsp+50h+phkResult], rax; phkResult
0x140024314  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14002431d  mov     [rsp+50h+samDesired], 3; samDesired
0x140024325  mov     [rsp+50h+dwOptions], 1; dwOptions
0x14002432d  xor     r9d, r9d; lpClass
0x140024330  xor     r8d, r8d; Reserved
0x140024333  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Windows NT\\Curren"...
0x14002433a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140024341  call    cs:__imp_RegCreateKeyExW
0x140024347  test    eax, eax
0x140024349  jnz     short loc_140024372
0x14002434b  lea     r9d, [rax+4]; dwType
0x14002434f  mov     [rsp+50h+samDesired], r9d; cbData
0x140024354  lea     rax, [rbp+Data]
0x140024358  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x14002435d  xor     r8d, r8d; Reserved
0x140024360  lea     rdx, aIntensity; "Intensity"
0x140024367  mov     rcx, [rbp+hKey]; hKey
0x14002436b  call    cs:__imp_RegSetValueExW
0x140024371  nop
0x140024372  lea     rcx, [rbp+hKey]
0x140024376  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14002437b  nop
0x14002437c  jmp     short loc_1400243F9
0x14002437e  mov     [rbp+hKey], 0
0x140024386  mov     rbx, [rbp+hKey]
0x14002438a  test    rbx, rbx
0x14002438d  jz      short loc_1400243AB
0x14002438f  lea     rcx, [rbp+arg_10]; this
0x140024393  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140024398  mov     rcx, rbx; hKey
0x14002439b  call    cs:__imp_RegCloseKey
0x1400243a1  lea     rcx, [rbp+arg_10]; this
0x1400243a5  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1400243aa  nop
0x1400243ab  mov     [rbp+hKey], 0
0x1400243b3  lea     rax, [rbp+hKey]
0x1400243b7  mov     qword ptr [rsp+50h+dwOptions], rax; phkResult
0x1400243bc  mov     r9d, 0F003Fh; samDesired
0x1400243c2  xor     r8d, r8d; ulOptions
0x1400243c5  lea     rdx, aSoftwareMicros_18; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400243cc  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400243d3  call    cs:__imp_RegOpenKeyExW
0x1400243d9  test    eax, eax
0x1400243db  jnz     short loc_1400243EF
0x1400243dd  lea     rdx, aColorfiltering_0; "colorfiltering"
0x1400243e4  mov     rcx, [rbp+hKey]; hKey
0x1400243e8  call    cs:__imp_RegDeleteTreeW
0x1400243ee  nop
0x1400243ef  lea     rcx, [rbp+hKey]
0x1400243f3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400243f8  nop
0x1400243f9  mov     rbx, [rsp+50h+arg_18]
0x1400243fe  add     rsp, 50h
0x140024402  pop     rbp
0x140024403  retn
```
