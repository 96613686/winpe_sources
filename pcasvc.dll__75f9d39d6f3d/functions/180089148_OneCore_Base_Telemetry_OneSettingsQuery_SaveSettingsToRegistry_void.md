# OneCore::Base::Telemetry::OneSettingsQuery::SaveSettingsToRegistry(void)

- ea: `0x180089148`
- end: `0x1800893ff`
- name: `?SaveSettingsToRegistry@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ`
- size: `695`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002a8e4`

## callees

- `0x18003c11c`
- `0x180089148`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800891a3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800891ed`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180089226`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800892f9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008936a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800891a3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800891ed`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180089226`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800892f9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008936a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800893b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800893bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800893ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800893dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800893ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800893b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800893bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800893ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800893dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800893ec`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800892b6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18008932e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800892b6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18008932e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008926b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008929b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008926b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008929b`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::SaveSettingsToRegistry(
        OneCore::Base::Telemetry::OneSettingsQuery *this)
{
  LSTATUS v2; // eax
  signed int v3; // ebx
  bool v4; // cc
  const BYTE *v5; // rcx
  __int64 v6; // rax
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  HKEY v9; // [rsp+90h] [rbp+30h] BYREF
  HKEY v10; // [rsp+98h] [rbp+38h] BYREF
  HKEY v11; // [rsp+A0h] [rbp+40h] BYREF
  HKEY phkResult; // [rsp+A8h] [rbp+48h] BYREF

  v10 = 0;
  v11 = 0;
  v9 = 0;
  phkResult = 0;
  hKey = 0;
  v2 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)this + 540, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  v3 = v2;
  v4 = v2 <= 0;
  if ( v2 )
    goto LABEL_2;
  v2 = RegCreateKeyExW(hKey, (LPCWSTR)this + 20, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  v3 = v2;
  v4 = v2 <= 0;
  if ( v2 )
    goto LABEL_2;
  v2 = RegCreateKeyExW(phkResult, (LPCWSTR)this + 280, 0, 0, 0, 0xF003Fu, 0, &v9, 0);
  v3 = v2;
  v4 = v2 <= 0;
  if ( v2 )
    goto LABEL_2;
  v5 = (const BYTE *)*((_QWORD *)this + 4);
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)&v5[2 * v6] );
  v2 = RegSetValueExW(v9, L"ETag", 0, 1u, v5, 2 * v6 + 2);
  v3 = v2;
  v4 = v2 <= 0;
  if ( v2 )
    goto LABEL_2;
  v2 = RegSetValueExW(v9, L"RefreshInterval", 0, 4u, (const BYTE *)this + 24, 4u);
  v3 = v2;
  v4 = v2 <= 0;
  if ( v2 )
    goto LABEL_2;
  v2 = RegDeleteTreeW(v9, L"Settings");
  v3 = v2;
  if ( (v2 & 0xFFFFFFFD) != 0 )
  {
LABEL_11:
    v4 = v2 <= 0;
    goto LABEL_2;
  }
  v2 = RegCreateKeyExW(v9, L"Settings", 0, 0, 0, 0xF003Fu, 0, &v11, 0);
  v3 = v2;
  v4 = v2 <= 0;
  if ( v2 )
    goto LABEL_2;
  v3 = OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(
         v11,
         (OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1608));
  if ( v3 < 0 )
    goto LABEL_19;
  v2 = RegDeleteTreeW(v9, L"QueryParameters");
  v3 = v2;
  if ( (v2 & 0xFFFFFFFD) != 0 )
    goto LABEL_11;
  v2 = RegCreateKeyExW(v9, L"QueryParameters", 0, 0, 0, 0xF003Fu, 0, &v10, 0);
  v3 = v2;
  v4 = v2 <= 0;
  if ( v2 )
  {
LABEL_2:
    if ( !v4 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    goto LABEL_19;
  }
  v3 = OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(
         v10,
         (OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1656));
  if ( v3 >= 0 )
  {
    v3 = OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(
           v10,
           (OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1704));
    if ( v3 >= 0 )
      v3 = 0;
  }
LABEL_19:
  if ( v10 )
    RegCloseKey(v10);
  if ( v11 )
    RegCloseKey(v11);
  if ( v9 )
    RegCloseKey(v9);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180089148  mov     r11, rsp
0x18008914b  push    rbp
0x18008914c  push    rbx
0x18008914d  push    rsi
0x18008914e  push    rdi
0x18008914f  push    r14
0x180089151  mov     rbp, rsp
0x180089154  sub     rsp, 60h
0x180089158  xor     esi, esi
0x18008915a  lea     rax, [rbp+hKey]
0x18008915e  mov     [r11-48h], rsi
0x180089162  lea     rdx, [rcx+438h]; lpSubKey
0x180089169  mov     [r11-50h], rax
0x18008916d  mov     rdi, rcx
0x180089170  mov     [r11-58h], rsi
0x180089174  mov     r14d, 0F003Fh
0x18008917a  mov     [r11-60h], r14d
0x18008917e  xor     r9d, r9d; lpClass
0x180089181  xor     r8d, r8d; Reserved
0x180089184  mov     [rsp+60h+dwOptions], esi; dwOptions
0x180089188  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008918f  mov     [rbp+arg_8], rsi
0x180089193  mov     [rbp+arg_10], rsi
0x180089197  mov     [rbp+arg_0], rsi
0x18008919b  mov     [rbp+arg_18], rsi
0x18008919f  mov     [rbp+hKey], rsi
0x1800891a3  call    cs:__imp_RegCreateKeyExW
0x1800891a9  mov     ebx, eax
0x1800891ab  test    eax, eax
0x1800891ad  jz      short loc_1800891C3
0x1800891af  jle     loc_1800893A7
0x1800891b5  movzx   ebx, ax
0x1800891b8  or      ebx, 80070000h
0x1800891be  jmp     loc_1800893A7
0x1800891c3  mov     rcx, [rbp+hKey]; hKey
0x1800891c7  lea     rax, [rbp+arg_18]
0x1800891cb  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x1800891d0  lea     rdx, [rdi+28h]; lpSubKey
0x1800891d4  mov     [rsp+60h+phkResult], rax; phkResult
0x1800891d9  xor     r9d, r9d; lpClass
0x1800891dc  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800891e1  xor     r8d, r8d; Reserved
0x1800891e4  mov     [rsp+60h+samDesired], r14d; samDesired
0x1800891e9  mov     [rsp+60h+dwOptions], esi; dwOptions
0x1800891ed  call    cs:__imp_RegCreateKeyExW
0x1800891f3  mov     ebx, eax
0x1800891f5  test    eax, eax
0x1800891f7  jnz     short loc_1800891AF
0x1800891f9  mov     rcx, [rbp+arg_18]; hKey
0x1800891fd  lea     rax, [rbp+arg_0]
0x180089201  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x180089206  lea     rdx, [rdi+230h]; lpSubKey
0x18008920d  mov     [rsp+60h+phkResult], rax; phkResult
0x180089212  xor     r9d, r9d; lpClass
0x180089215  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18008921a  xor     r8d, r8d; Reserved
0x18008921d  mov     [rsp+60h+samDesired], r14d; samDesired
0x180089222  mov     [rsp+60h+dwOptions], esi; dwOptions
0x180089226  call    cs:__imp_RegCreateKeyExW
0x18008922c  mov     ebx, eax
0x18008922e  test    eax, eax
0x180089230  jnz     loc_1800891AF
0x180089236  mov     rcx, [rdi+20h]
0x18008923a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008923e  inc     rax
0x180089241  cmp     [rcx+rax*2], si
0x180089245  jnz     short loc_18008923E
0x180089247  lea     eax, ds:2[rax*2]
0x18008924e  mov     r9d, 1; dwType
0x180089254  mov     [rsp+60h+samDesired], eax; cbData
0x180089258  lea     rdx, aEtag; "ETag"
0x18008925f  mov     qword ptr [rsp+60h+dwOptions], rcx; lpData
0x180089264  xor     r8d, r8d; Reserved
0x180089267  mov     rcx, [rbp+arg_0]; hKey
0x18008926b  call    cs:__imp_RegSetValueExW
0x180089271  mov     ebx, eax
0x180089273  test    eax, eax
0x180089275  jnz     loc_1800891AF
0x18008927b  mov     rcx, [rbp+arg_0]; hKey
0x18008927f  lea     r9d, [rbx+4]; dwType
0x180089283  lea     rax, [rdi+18h]
0x180089287  mov     [rsp+60h+samDesired], r9d; cbData
0x18008928c  xor     r8d, r8d; Reserved
0x18008928f  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180089294  lea     rdx, aRefreshinterva_0; "RefreshInterval"
0x18008929b  call    cs:__imp_RegSetValueExW
0x1800892a1  mov     ebx, eax
0x1800892a3  test    eax, eax
0x1800892a5  jnz     loc_1800891AF
0x1800892ab  mov     rcx, [rbp+arg_0]; hKey
0x1800892af  lea     rdx, aSettings_0; "Settings"
0x1800892b6  call    cs:__imp_RegDeleteTreeW
0x1800892bc  mov     ebx, eax
0x1800892be  test    eax, 0FFFFFFFDh
0x1800892c3  jz      short loc_1800892CC
0x1800892c5  test    eax, eax
0x1800892c7  jmp     loc_1800891AF
0x1800892cc  mov     rcx, [rbp+arg_0]; hKey
0x1800892d0  lea     rax, [rbp+arg_10]
0x1800892d4  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x1800892d9  lea     rdx, aSettings_0; "Settings"
0x1800892e0  mov     [rsp+60h+phkResult], rax; phkResult
0x1800892e5  xor     r9d, r9d; lpClass
0x1800892e8  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800892ed  xor     r8d, r8d; Reserved
0x1800892f0  mov     [rsp+60h+samDesired], r14d; samDesired
0x1800892f5  mov     [rsp+60h+dwOptions], esi; dwOptions
0x1800892f9  call    cs:__imp_RegCreateKeyExW
0x1800892ff  mov     ebx, eax
0x180089301  test    eax, eax
0x180089303  jnz     loc_1800891AF
0x180089309  mov     rcx, [rbp+arg_10]; hKey
0x18008930d  lea     rdx, [rdi+648h]; this
0x180089314  call    ?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)
0x180089319  mov     ebx, eax
0x18008931b  test    eax, eax
0x18008931d  js      loc_1800893A7
0x180089323  mov     rcx, [rbp+arg_0]; hKey
0x180089327  lea     rdx, aQueryparameter; "QueryParameters"
0x18008932e  call    cs:__imp_RegDeleteTreeW
0x180089334  mov     ebx, eax
0x180089336  test    eax, 0FFFFFFFDh
0x18008933b  jnz     short loc_1800892C5
0x18008933d  mov     rcx, [rbp+arg_0]; hKey
0x180089341  lea     rax, [rbp+arg_8]
0x180089345  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x18008934a  lea     rdx, aQueryparameter; "QueryParameters"
0x180089351  mov     [rsp+60h+phkResult], rax; phkResult
0x180089356  xor     r9d, r9d; lpClass
0x180089359  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18008935e  xor     r8d, r8d; Reserved
0x180089361  mov     [rsp+60h+samDesired], r14d; samDesired
0x180089366  mov     [rsp+60h+dwOptions], esi; dwOptions
0x18008936a  call    cs:__imp_RegCreateKeyExW
0x180089370  mov     ebx, eax
0x180089372  test    eax, eax
0x180089374  jnz     loc_1800891AF
0x18008937a  mov     rcx, [rbp+arg_8]; hKey
0x18008937e  lea     rdx, [rdi+678h]; this
0x180089385  call    ?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)
0x18008938a  mov     ebx, eax
0x18008938c  test    eax, eax
0x18008938e  js      short loc_1800893A7
0x180089390  mov     rcx, [rbp+arg_8]; hKey
0x180089394  lea     rdx, [rdi+6A8h]; this
0x18008939b  call    ?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)
0x1800893a0  test    eax, eax
0x1800893a2  mov     ebx, eax
0x1800893a4  cmovns  ebx, esi
0x1800893a7  mov     rcx, [rbp+arg_8]; hKey
0x1800893ab  test    rcx, rcx
0x1800893ae  jz      short loc_1800893B6
0x1800893b0  call    cs:__imp_RegCloseKey
0x1800893b6  mov     rcx, [rbp+arg_10]; hKey
0x1800893ba  test    rcx, rcx
0x1800893bd  jz      short loc_1800893C5
0x1800893bf  call    cs:__imp_RegCloseKey
0x1800893c5  mov     rcx, [rbp+arg_0]; hKey
0x1800893c9  test    rcx, rcx
0x1800893cc  jz      short loc_1800893D4
0x1800893ce  call    cs:__imp_RegCloseKey
0x1800893d4  mov     rcx, [rbp+arg_18]; hKey
0x1800893d8  test    rcx, rcx
0x1800893db  jz      short loc_1800893E3
0x1800893dd  call    cs:__imp_RegCloseKey
0x1800893e3  mov     rcx, [rbp+hKey]; hKey
0x1800893e7  test    rcx, rcx
0x1800893ea  jz      short loc_1800893F2
0x1800893ec  call    cs:__imp_RegCloseKey
0x1800893f2  mov     eax, ebx
0x1800893f4  add     rsp, 60h
0x1800893f8  pop     r14
0x1800893fa  pop     rdi
0x1800893fb  pop     rsi
0x1800893fc  pop     rbx
0x1800893fd  pop     rbp
0x1800893fe  retn
```
