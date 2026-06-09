# OneCore::Base::Telemetry::OneSettingsQuery::SaveSettingsToRegistry(void)

- ea: `0x180006eb0`
- end: `0x180007167`
- name: `?SaveSettingsToRegistry@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ`
- size: `695`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800055f4`

## callees

- `0x180006eb0`
- `0x18000807c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180007118`
- `ADVAPI32!RegCloseKey` at `0x180007127`
- `ADVAPI32!RegCloseKey` at `0x180007136`
- `ADVAPI32!RegCloseKey` at `0x180007145`
- `ADVAPI32!RegCloseKey` at `0x180007154`
- `ADVAPI32!RegCloseKey` at `0x180007118`
- `ADVAPI32!RegCloseKey` at `0x180007127`
- `ADVAPI32!RegCloseKey` at `0x180007136`
- `ADVAPI32!RegCloseKey` at `0x180007145`
- `ADVAPI32!RegCloseKey` at `0x180007154`
- `ADVAPI32!RegDeleteTreeW` at `0x18000701e`
- `ADVAPI32!RegDeleteTreeW` at `0x180007096`
- `ADVAPI32!RegDeleteTreeW` at `0x18000701e`
- `ADVAPI32!RegDeleteTreeW` at `0x180007096`
- `ADVAPI32!RegCreateKeyExW` at `0x180006f0b`
- `ADVAPI32!RegCreateKeyExW` at `0x180006f55`
- `ADVAPI32!RegCreateKeyExW` at `0x180006f8e`
- `ADVAPI32!RegCreateKeyExW` at `0x180007061`
- `ADVAPI32!RegCreateKeyExW` at `0x1800070d2`
- `ADVAPI32!RegCreateKeyExW` at `0x180006f0b`
- `ADVAPI32!RegCreateKeyExW` at `0x180006f55`
- `ADVAPI32!RegCreateKeyExW` at `0x180006f8e`
- `ADVAPI32!RegCreateKeyExW` at `0x180007061`
- `ADVAPI32!RegCreateKeyExW` at `0x1800070d2`
- `ADVAPI32!RegSetValueExW` at `0x180006fd3`
- `ADVAPI32!RegSetValueExW` at `0x180007003`
- `ADVAPI32!RegSetValueExW` at `0x180006fd3`
- `ADVAPI32!RegSetValueExW` at `0x180007003`

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
0x180006eb0  mov     r11, rsp
0x180006eb3  push    rbp
0x180006eb4  push    rbx
0x180006eb5  push    rsi
0x180006eb6  push    rdi
0x180006eb7  push    r14
0x180006eb9  mov     rbp, rsp
0x180006ebc  sub     rsp, 60h
0x180006ec0  xor     esi, esi
0x180006ec2  lea     rax, [rbp+hKey]
0x180006ec6  mov     [r11-48h], rsi
0x180006eca  lea     rdx, [rcx+438h]; lpSubKey
0x180006ed1  mov     [r11-50h], rax
0x180006ed5  mov     rdi, rcx
0x180006ed8  mov     [r11-58h], rsi
0x180006edc  mov     r14d, 0F003Fh
0x180006ee2  mov     [r11-60h], r14d
0x180006ee6  xor     r9d, r9d; lpClass
0x180006ee9  xor     r8d, r8d; Reserved
0x180006eec  mov     [rsp+60h+dwOptions], esi; dwOptions
0x180006ef0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006ef7  mov     [rbp+arg_8], rsi
0x180006efb  mov     [rbp+arg_10], rsi
0x180006eff  mov     [rbp+arg_0], rsi
0x180006f03  mov     [rbp+arg_18], rsi
0x180006f07  mov     [rbp+hKey], rsi
0x180006f0b  call    cs:__imp_RegCreateKeyExW
0x180006f11  mov     ebx, eax
0x180006f13  test    eax, eax
0x180006f15  jz      short loc_180006F2B
0x180006f17  jle     loc_18000710F
0x180006f1d  movzx   ebx, ax
0x180006f20  or      ebx, 80070000h
0x180006f26  jmp     loc_18000710F
0x180006f2b  mov     rcx, [rbp+hKey]; hKey
0x180006f2f  lea     rax, [rbp+arg_18]
0x180006f33  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x180006f38  lea     rdx, [rdi+28h]; lpSubKey
0x180006f3c  mov     [rsp+60h+phkResult], rax; phkResult
0x180006f41  xor     r9d, r9d; lpClass
0x180006f44  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180006f49  xor     r8d, r8d; Reserved
0x180006f4c  mov     [rsp+60h+samDesired], r14d; samDesired
0x180006f51  mov     [rsp+60h+dwOptions], esi; dwOptions
0x180006f55  call    cs:__imp_RegCreateKeyExW
0x180006f5b  mov     ebx, eax
0x180006f5d  test    eax, eax
0x180006f5f  jnz     short loc_180006F17
0x180006f61  mov     rcx, [rbp+arg_18]; hKey
0x180006f65  lea     rax, [rbp+arg_0]
0x180006f69  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x180006f6e  lea     rdx, [rdi+230h]; lpSubKey
0x180006f75  mov     [rsp+60h+phkResult], rax; phkResult
0x180006f7a  xor     r9d, r9d; lpClass
0x180006f7d  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180006f82  xor     r8d, r8d; Reserved
0x180006f85  mov     [rsp+60h+samDesired], r14d; samDesired
0x180006f8a  mov     [rsp+60h+dwOptions], esi; dwOptions
0x180006f8e  call    cs:__imp_RegCreateKeyExW
0x180006f94  mov     ebx, eax
0x180006f96  test    eax, eax
0x180006f98  jnz     loc_180006F17
0x180006f9e  mov     rcx, [rdi+20h]
0x180006fa2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006fa6  inc     rax
0x180006fa9  cmp     [rcx+rax*2], si
0x180006fad  jnz     short loc_180006FA6
0x180006faf  lea     eax, ds:2[rax*2]
0x180006fb6  mov     r9d, 1; dwType
0x180006fbc  mov     [rsp+60h+samDesired], eax; cbData
0x180006fc0  lea     rdx, ValueName; "ETag"
0x180006fc7  mov     qword ptr [rsp+60h+dwOptions], rcx; lpData
0x180006fcc  xor     r8d, r8d; Reserved
0x180006fcf  mov     rcx, [rbp+arg_0]; hKey
0x180006fd3  call    cs:__imp_RegSetValueExW
0x180006fd9  mov     ebx, eax
0x180006fdb  test    eax, eax
0x180006fdd  jnz     loc_180006F17
0x180006fe3  mov     rcx, [rbp+arg_0]; hKey
0x180006fe7  lea     r9d, [rbx+4]; dwType
0x180006feb  lea     rax, [rdi+18h]
0x180006fef  mov     [rsp+60h+samDesired], r9d; cbData
0x180006ff4  xor     r8d, r8d; Reserved
0x180006ff7  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180006ffc  lea     rdx, aRefreshinterva_0; "RefreshInterval"
0x180007003  call    cs:__imp_RegSetValueExW
0x180007009  mov     ebx, eax
0x18000700b  test    eax, eax
0x18000700d  jnz     loc_180006F17
0x180007013  mov     rcx, [rbp+arg_0]; hKey
0x180007017  lea     rdx, SubKey; "Settings"
0x18000701e  call    cs:__imp_RegDeleteTreeW
0x180007024  mov     ebx, eax
0x180007026  test    eax, 0FFFFFFFDh
0x18000702b  jz      short loc_180007034
0x18000702d  test    eax, eax
0x18000702f  jmp     loc_180006F17
0x180007034  mov     rcx, [rbp+arg_0]; hKey
0x180007038  lea     rax, [rbp+arg_10]
0x18000703c  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x180007041  lea     rdx, SubKey; "Settings"
0x180007048  mov     [rsp+60h+phkResult], rax; phkResult
0x18000704d  xor     r9d, r9d; lpClass
0x180007050  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180007055  xor     r8d, r8d; Reserved
0x180007058  mov     [rsp+60h+samDesired], r14d; samDesired
0x18000705d  mov     [rsp+60h+dwOptions], esi; dwOptions
0x180007061  call    cs:__imp_RegCreateKeyExW
0x180007067  mov     ebx, eax
0x180007069  test    eax, eax
0x18000706b  jnz     loc_180006F17
0x180007071  mov     rcx, [rbp+arg_10]; hKey
0x180007075  lea     rdx, [rdi+648h]; struct RtlNameValueArray *
0x18000707c  call    ?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)
0x180007081  mov     ebx, eax
0x180007083  test    eax, eax
0x180007085  js      loc_18000710F
0x18000708b  mov     rcx, [rbp+arg_0]; hKey
0x18000708f  lea     rdx, aQueryparameter; "QueryParameters"
0x180007096  call    cs:__imp_RegDeleteTreeW
0x18000709c  mov     ebx, eax
0x18000709e  test    eax, 0FFFFFFFDh
0x1800070a3  jnz     short loc_18000702D
0x1800070a5  mov     rcx, [rbp+arg_0]; hKey
0x1800070a9  lea     rax, [rbp+arg_8]
0x1800070ad  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x1800070b2  lea     rdx, aQueryparameter; "QueryParameters"
0x1800070b9  mov     [rsp+60h+phkResult], rax; phkResult
0x1800070be  xor     r9d, r9d; lpClass
0x1800070c1  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800070c6  xor     r8d, r8d; Reserved
0x1800070c9  mov     [rsp+60h+samDesired], r14d; samDesired
0x1800070ce  mov     [rsp+60h+dwOptions], esi; dwOptions
0x1800070d2  call    cs:__imp_RegCreateKeyExW
0x1800070d8  mov     ebx, eax
0x1800070da  test    eax, eax
0x1800070dc  jnz     loc_180006F17
0x1800070e2  mov     rcx, [rbp+arg_8]; hKey
0x1800070e6  lea     rdx, [rdi+678h]; struct RtlNameValueArray *
0x1800070ed  call    ?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)
0x1800070f2  mov     ebx, eax
0x1800070f4  test    eax, eax
0x1800070f6  js      short loc_18000710F
0x1800070f8  mov     rcx, [rbp+arg_8]; hKey
0x1800070fc  lea     rdx, [rdi+6A8h]; struct RtlNameValueArray *
0x180007103  call    ?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)
0x180007108  test    eax, eax
0x18000710a  mov     ebx, eax
0x18000710c  cmovns  ebx, esi
0x18000710f  mov     rcx, [rbp+arg_8]; hKey
0x180007113  test    rcx, rcx
0x180007116  jz      short loc_18000711E
0x180007118  call    cs:__imp_RegCloseKey
0x18000711e  mov     rcx, [rbp+arg_10]; hKey
0x180007122  test    rcx, rcx
0x180007125  jz      short loc_18000712D
0x180007127  call    cs:__imp_RegCloseKey
0x18000712d  mov     rcx, [rbp+arg_0]; hKey
0x180007131  test    rcx, rcx
0x180007134  jz      short loc_18000713C
0x180007136  call    cs:__imp_RegCloseKey
0x18000713c  mov     rcx, [rbp+arg_18]; hKey
0x180007140  test    rcx, rcx
0x180007143  jz      short loc_18000714B
0x180007145  call    cs:__imp_RegCloseKey
0x18000714b  mov     rcx, [rbp+hKey]; hKey
0x18000714f  test    rcx, rcx
0x180007152  jz      short loc_18000715A
0x180007154  call    cs:__imp_RegCloseKey
0x18000715a  mov     eax, ebx
0x18000715c  add     rsp, 60h
0x180007160  pop     r14
0x180007162  pop     rdi
0x180007163  pop     rsi
0x180007164  pop     rbx
0x180007165  pop     rbp
0x180007166  retn
```
