# OneCore::Base::Telemetry::OneSettingsQuery::UpdateQueryParameters(void)

- ea: `0x180007c90`
- end: `0x180007e2b`
- name: `?UpdateQueryParameters@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ`
- size: `411`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1800055f4`

## callees

- `0x180007b54`
- `0x180007c90`
- `0x18000807c`
- `0x1800191f0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180007def`
- `ADVAPI32!RegCloseKey` at `0x180007dff`
- `ADVAPI32!RegCloseKey` at `0x180007def`
- `ADVAPI32!RegCloseKey` at `0x180007dff`
- `ADVAPI32!RegDeleteTreeW` at `0x180007d57`
- `ADVAPI32!RegDeleteTreeW` at `0x180007d57`
- `ADVAPI32!RegCreateKeyExW` at `0x180007da8`
- `ADVAPI32!RegCreateKeyExW` at `0x180007da8`
- `ADVAPI32!RegOpenKeyExW` at `0x180007d2b`
- `ADVAPI32!RegOpenKeyExW` at `0x180007d2b`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::UpdateQueryParameters(
        OneCore::Base::Telemetry::OneSettingsQuery *this)
{
  signed int v2; // ebx
  LSTATUS v3; // eax
  bool v4; // cc
  HKEY v6; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  v6 = 0;
  hKey = 0;
  v2 = StringCchPrintfW(SubKey, 0x104u, L"%ls\\%ls\\%ls", (char *)this + 1080, (char *)this + 40, (char *)this + 560);
  if ( v2 < 0 )
    goto LABEL_11;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0xF003Fu, &hKey);
  v2 = v3;
  v4 = v3 <= 0;
  if ( v3 )
    goto LABEL_3;
  v3 = RegDeleteTreeW(hKey, L"QueryParameters");
  v2 = v3;
  if ( (v3 & 0xFFFFFFFD) != 0 )
  {
    v4 = v3 <= 0;
    goto LABEL_3;
  }
  v3 = RegCreateKeyExW(hKey, L"QueryParameters", 0, 0, 0, 0xF003Fu, 0, &v6, 0);
  v2 = v3;
  v4 = v3 <= 0;
  if ( v3 )
  {
LABEL_3:
    if ( !v4 )
      v2 = (unsigned __int16)v3 | 0x80070000;
    goto LABEL_11;
  }
  v2 = OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(
         v6,
         (OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1656));
  if ( v2 >= 0 )
  {
    v2 = OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(
           v6,
           (OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1704));
    if ( v2 >= 0 )
      v2 = 0;
  }
LABEL_11:
  if ( v6 )
    RegCloseKey(v6);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180007c90  mov     [rsp-8+arg_8], rbx
0x180007c95  mov     [rsp-8+arg_10], rdi
0x180007c9a  push    rbp
0x180007c9b  lea     rbp, [rsp-180h]
0x180007ca3  sub     rsp, 280h
0x180007caa  mov     rax, cs:__security_cookie
0x180007cb1  xor     rax, rsp
0x180007cb4  mov     [rbp+180h+var_10], rax
0x180007cbb  lea     rdx, [rcx+28h]
0x180007cbf  mov     [rsp+280h+var_230], 0
0x180007cc8  lea     rax, [rcx+230h]
0x180007ccf  mov     [rsp+280h+hKey], 0
0x180007cd8  mov     qword ptr [rsp+280h+samDesired], rax
0x180007cdd  lea     r9, [rcx+438h]
0x180007ce4  mov     [rsp+280h+phkResult], rdx
0x180007ce9  lea     r8, aLsLsLs; "%ls\\%ls\\%ls"
0x180007cf0  mov     rdi, rcx
0x180007cf3  mov     edx, 104h; unsigned __int64
0x180007cf8  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x180007cfd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007d02  mov     ebx, eax
0x180007d04  test    eax, eax
0x180007d06  js      loc_180007DE5
0x180007d0c  lea     rax, [rsp+280h+hKey]
0x180007d11  mov     r9d, 0F003Fh; samDesired
0x180007d17  xor     r8d, r8d; ulOptions
0x180007d1a  mov     [rsp+280h+phkResult], rax; phkResult
0x180007d1f  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x180007d24  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007d2b  call    cs:__imp_RegOpenKeyExW
0x180007d31  mov     ebx, eax
0x180007d33  test    eax, eax
0x180007d35  jz      short loc_180007D4B
0x180007d37  jle     loc_180007DE5
0x180007d3d  movzx   ebx, ax
0x180007d40  or      ebx, 80070000h
0x180007d46  jmp     loc_180007DE5
0x180007d4b  mov     rcx, [rsp+280h+hKey]; hKey
0x180007d50  lea     rdx, aQueryparameter; "QueryParameters"
0x180007d57  call    cs:__imp_RegDeleteTreeW
0x180007d5d  mov     ebx, eax
0x180007d5f  test    eax, 0FFFFFFFDh
0x180007d64  jz      short loc_180007D6A
0x180007d66  test    eax, eax
0x180007d68  jmp     short loc_180007D37
0x180007d6a  mov     rcx, [rsp+280h+hKey]; hKey
0x180007d6f  lea     rax, [rsp+280h+var_230]
0x180007d74  mov     [rsp+280h+lpdwDisposition], 0; lpdwDisposition
0x180007d7d  lea     rdx, aQueryparameter; "QueryParameters"
0x180007d84  mov     [rsp+280h+var_248], rax; phkResult
0x180007d89  xor     r9d, r9d; lpClass
0x180007d8c  mov     [rsp+280h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180007d95  xor     r8d, r8d; Reserved
0x180007d98  mov     [rsp+280h+samDesired], 0F003Fh; samDesired
0x180007da0  mov     dword ptr [rsp+280h+phkResult], 0; dwOptions
0x180007da8  call    cs:__imp_RegCreateKeyExW
0x180007dae  mov     ebx, eax
0x180007db0  test    eax, eax
0x180007db2  jnz     short loc_180007D37
0x180007db4  mov     rcx, [rsp+280h+var_230]; hKey
0x180007db9  lea     rdx, [rdi+678h]; struct RtlNameValueArray *
0x180007dc0  call    ?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)
0x180007dc5  mov     ebx, eax
0x180007dc7  test    eax, eax
0x180007dc9  js      short loc_180007DE5
0x180007dcb  mov     rcx, [rsp+280h+var_230]; hKey
0x180007dd0  lea     rdx, [rdi+6A8h]; struct RtlNameValueArray *
0x180007dd7  call    ?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)
0x180007ddc  mov     ebx, eax
0x180007dde  xor     eax, eax
0x180007de0  test    ebx, ebx
0x180007de2  cmovns  ebx, eax
0x180007de5  mov     rcx, [rsp+280h+var_230]; hKey
0x180007dea  test    rcx, rcx
0x180007ded  jz      short loc_180007DF5
0x180007def  call    cs:__imp_RegCloseKey
0x180007df5  mov     rcx, [rsp+280h+hKey]; hKey
0x180007dfa  test    rcx, rcx
0x180007dfd  jz      short loc_180007E05
0x180007dff  call    cs:__imp_RegCloseKey
0x180007e05  mov     eax, ebx
0x180007e07  mov     rcx, [rbp+180h+var_10]
0x180007e0e  xor     rcx, rsp; StackCookie
0x180007e11  call    __security_check_cookie
0x180007e16  lea     r11, [rsp+280h+var_s0]
0x180007e1e  mov     rbx, [r11+18h]
0x180007e22  mov     rdi, [r11+20h]
0x180007e26  mov     rsp, r11
0x180007e29  pop     rbp
0x180007e2a  retn
```
