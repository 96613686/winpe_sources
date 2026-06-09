# ColorFiltering::ColorFilterHelper::UpdateTransferSettingsGain(ulong)

- ea: `0x140024154`
- end: `0x1400242a8`
- name: `?UpdateTransferSettingsGain@ColorFilterHelper@ColorFiltering@@SAXK@Z`
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
- `0x140024154`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140024277`
- `ADVAPI32!RegOpenKeyExW` at `0x140024277`
- `ADVAPI32!RegSetValueExW` at `0x14002420f`
- `ADVAPI32!RegSetValueExW` at `0x14002420f`
- `ADVAPI32!RegCloseKey` at `0x14002418e`
- `ADVAPI32!RegCloseKey` at `0x14002423f`
- `ADVAPI32!RegCloseKey` at `0x14002418e`
- `ADVAPI32!RegCloseKey` at `0x14002423f`
- `ADVAPI32!RegCreateKeyExW` at `0x1400241e5`
- `ADVAPI32!RegCreateKeyExW` at `0x1400241e5`
- `ADVAPI32!RegDeleteTreeW` at `0x14002428c`
- `ADVAPI32!RegDeleteTreeW` at `0x14002428c`

## string_xrefs

- `0x140024269`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\`
- `0x1400241d7`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

## pseudocode

```c
void __fastcall ColorFiltering::ColorFilterHelper::UpdateTransferSettingsGain(int a1)
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
      RegSetValueExW(hKey, L"Gain", 0, 4u, (const BYTE *)&Data, 4u);
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
0x140024154  mov     [rsp-8+arg_18], rbx
0x140024159  push    rbp
0x14002415a  mov     rbp, rsp
0x14002415d  sub     rsp, 50h
0x140024161  mov     [rbp+Data], ecx
0x140024164  call    ?IsActive@ColorFilterHelper@ColorFiltering@@SA_NXZ; ColorFiltering::ColorFilterHelper::IsActive(void)
0x140024169  test    al, al
0x14002416b  jz      loc_140024222
0x140024171  mov     [rbp+hKey], 0
0x140024179  mov     rbx, [rbp+hKey]
0x14002417d  test    rbx, rbx
0x140024180  jz      short loc_14002419E
0x140024182  lea     rcx, [rbp+arg_10]; this
0x140024186  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14002418b  mov     rcx, rbx; hKey
0x14002418e  call    cs:__imp_RegCloseKey
0x140024194  lea     rcx, [rbp+arg_10]; this
0x140024198  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14002419d  nop
0x14002419e  mov     [rbp+hKey], 0
0x1400241a6  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x1400241af  lea     rax, [rbp+hKey]
0x1400241b3  mov     [rsp+50h+phkResult], rax; phkResult
0x1400241b8  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1400241c1  mov     [rsp+50h+samDesired], 3; samDesired
0x1400241c9  mov     [rsp+50h+dwOptions], 1; dwOptions
0x1400241d1  xor     r9d, r9d; lpClass
0x1400241d4  xor     r8d, r8d; Reserved
0x1400241d7  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400241de  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400241e5  call    cs:__imp_RegCreateKeyExW
0x1400241eb  test    eax, eax
0x1400241ed  jnz     short loc_140024216
0x1400241ef  lea     r9d, [rax+4]; dwType
0x1400241f3  mov     [rsp+50h+samDesired], r9d; cbData
0x1400241f8  lea     rax, [rbp+Data]
0x1400241fc  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x140024201  xor     r8d, r8d; Reserved
0x140024204  lea     rdx, aGain; "Gain"
0x14002420b  mov     rcx, [rbp+hKey]; hKey
0x14002420f  call    cs:__imp_RegSetValueExW
0x140024215  nop
0x140024216  lea     rcx, [rbp+hKey]
0x14002421a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14002421f  nop
0x140024220  jmp     short loc_14002429D
0x140024222  mov     [rbp+hKey], 0
0x14002422a  mov     rbx, [rbp+hKey]
0x14002422e  test    rbx, rbx
0x140024231  jz      short loc_14002424F
0x140024233  lea     rcx, [rbp+arg_10]; this
0x140024237  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14002423c  mov     rcx, rbx; hKey
0x14002423f  call    cs:__imp_RegCloseKey
0x140024245  lea     rcx, [rbp+arg_10]; this
0x140024249  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14002424e  nop
0x14002424f  mov     [rbp+hKey], 0
0x140024257  lea     rax, [rbp+hKey]
0x14002425b  mov     qword ptr [rsp+50h+dwOptions], rax; phkResult
0x140024260  mov     r9d, 0F003Fh; samDesired
0x140024266  xor     r8d, r8d; ulOptions
0x140024269  lea     rdx, aSoftwareMicros_18; "Software\\Microsoft\\Windows NT\\Curren"...
0x140024270  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140024277  call    cs:__imp_RegOpenKeyExW
0x14002427d  test    eax, eax
0x14002427f  jnz     short loc_140024293
0x140024281  lea     rdx, aColorfiltering_0; "colorfiltering"
0x140024288  mov     rcx, [rbp+hKey]; hKey
0x14002428c  call    cs:__imp_RegDeleteTreeW
0x140024292  nop
0x140024293  lea     rcx, [rbp+hKey]
0x140024297  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14002429c  nop
0x14002429d  mov     rbx, [rsp+50h+arg_18]
0x1400242a2  add     rsp, 50h
0x1400242a6  pop     rbp
0x1400242a7  retn
```
