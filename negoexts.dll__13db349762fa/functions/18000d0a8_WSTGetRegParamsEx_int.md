# WSTGetRegParamsEx(int)

- ea: `0x18000d0a8`
- end: `0x18000d22b`
- name: `?WSTGetRegParamsEx@@YAXH@Z`
- size: `387`
- prototype: `void __fastcall(int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d090`
- `0x180018560`

## callees

- `0x18000d0a8`
- `0x1800187ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d19f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d1e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d205`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d21c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d19f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d1e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d205`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d21c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d18c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d1cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d18c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d1cd`

## string_xrefs

- `0x18000d0c3`: `MaxTokenSize`

## pseudocode

```c
void __fastcall WSTGetRegParamsEx()
{
  LSTATUS v0; // eax
  unsigned int v1; // r8d
  HKEY v2; // rdx
  _QWORD v3[3]; // [rsp+30h] [rbp-49h] BYREF
  int v4; // [rsp+48h] [rbp-31h]
  const wchar_t *v5; // [rsp+50h] [rbp-29h]
  unsigned int *v6; // [rsp+58h] [rbp-21h]
  __int64 v7; // [rsp+60h] [rbp-19h]
  int v8; // [rsp+68h] [rbp-11h]
  const wchar_t *v9; // [rsp+70h] [rbp-9h]
  unsigned int *v10; // [rsp+78h] [rbp-1h]
  __int64 v11; // [rsp+80h] [rbp+7h]
  int v12; // [rsp+88h] [rbp+Fh]
  const wchar_t *v13; // [rsp+90h] [rbp+17h]
  unsigned int *v14; // [rsp+98h] [rbp+1Fh]
  __int64 v15; // [rsp+A0h] [rbp+27h]
  int v16; // [rsp+A8h] [rbp+2Fh]
  const wchar_t *v17; // [rsp+B0h] [rbp+37h]
  unsigned int *v18; // [rsp+B8h] [rbp+3Fh]
  __int64 v19; // [rsp+C0h] [rbp+47h]
  int v20; // [rsp+C8h] [rbp+4Fh]
  HKEY hKey; // [rsp+E8h] [rbp+6Fh] BYREF
  HKEY phkResult; // [rsp+F0h] [rbp+77h] BYREF

  hKey = 0;
  v4 = 1;
  v3[0] = L"MaxTokenSize";
  v7 = 1;
  v3[1] = &WSTGlobalMaxTokenSize;
  v8 = 1;
  v5 = L"Active";
  v12 = 1;
  v6 = &WSTGlobalExtenderActive;
  v9 = L"ServerExpiry";
  v10 = &WSTGlobalExpiration;
  v13 = L"ClientExpiry";
  v14 = &WSTGlobalClientExpiration;
  v17 = L"ScavengerInterval";
  v18 = &WSTGlobalScavengerInterval;
  v16 = 1;
  v20 = 1;
  phkResult = 0;
  v3[2] = 12000;
  v11 = 900000;
  v15 = 7200000;
  v19 = 14400;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Lsa\\NegoExtender\\Parameters",
         0,
         0x20019u,
         &hKey)
    && hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System\\NegoExtender\\Parameters",
         0,
         0x20019u,
         &phkResult);
  v2 = phkResult;
  if ( v0 && phkResult )
  {
    RegCloseKey(phkResult);
    v2 = 0;
    phkResult = 0;
  }
  WSTGetRegistryDwords(hKey, v2, v1, (struct _NEGOEXTS_REG_PARAMETER *)v3);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
}

```

## disassembly

```asm
0x18000d0a8  push    rbp
0x18000d0aa  lea     rbp, [rsp-57h]
0x18000d0af  sub     rsp, 0D0h
0x18000d0b6  mov     ecx, 1
0x18000d0bb  mov     [rbp+57h+hKey], 0
0x18000d0c3  lea     rax, aMaxtokensize; "MaxTokenSize"
0x18000d0ca  mov     [rbp+57h+var_88], ecx
0x18000d0cd  mov     [rbp+57h+var_A0], rax
0x18000d0d1  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Lsa"...
0x18000d0d8  lea     rax, ?WSTGlobalMaxTokenSize@@3KA; ulong WSTGlobalMaxTokenSize
0x18000d0df  mov     [rbp+57h+var_70], rcx
0x18000d0e3  mov     [rbp+57h+var_98], rax
0x18000d0e7  mov     r9d, 20019h; samDesired
0x18000d0ed  lea     rax, aActive; "Active"
0x18000d0f4  mov     [rbp+57h+var_68], ecx
0x18000d0f7  mov     [rbp+57h+var_80], rax
0x18000d0fb  xor     r8d, r8d; ulOptions
0x18000d0fe  lea     rax, ?WSTGlobalExtenderActive@@3KA; ulong WSTGlobalExtenderActive
0x18000d105  mov     [rbp+57h+var_48], ecx
0x18000d108  mov     [rbp+57h+var_78], rax
0x18000d10c  lea     rax, aServerexpiry; "ServerExpiry"
0x18000d113  mov     [rbp+57h+var_60], rax
0x18000d117  lea     rax, ?WSTGlobalExpiration@@3KA; ulong WSTGlobalExpiration
0x18000d11e  mov     [rbp+57h+var_58], rax
0x18000d122  lea     rax, aClientexpiry; "ClientExpiry"
0x18000d129  mov     [rbp+57h+var_40], rax
0x18000d12d  lea     rax, ?WSTGlobalClientExpiration@@3KA; ulong WSTGlobalClientExpiration
0x18000d134  mov     [rbp+57h+var_38], rax
0x18000d138  lea     rax, aScavengerinter; "ScavengerInterval"
0x18000d13f  mov     [rbp+57h+var_20], rax
0x18000d143  lea     rax, ?WSTGlobalScavengerInterval@@3KA; ulong WSTGlobalScavengerInterval
0x18000d14a  mov     [rbp+57h+var_18], rax
0x18000d14e  lea     rax, [rbp+57h+hKey]
0x18000d152  mov     [rbp+57h+var_28], ecx
0x18000d155  mov     [rbp+57h+var_8], ecx
0x18000d158  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d15f  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18000d164  mov     [rbp+57h+arg_10], 0
0x18000d16c  mov     [rbp+57h+var_90], 2EE0h
0x18000d174  mov     [rbp+57h+var_50], 0DBBA0h
0x18000d17c  mov     [rbp+57h+var_30], 6DDD00h
0x18000d184  mov     [rbp+57h+var_10], 3840h
0x18000d18c  call    cs:__imp_RegOpenKeyExW
0x18000d192  test    eax, eax
0x18000d194  jz      short loc_18000D1AD
0x18000d196  mov     rcx, [rbp+57h+hKey]; hKey
0x18000d19a  test    rcx, rcx
0x18000d19d  jz      short loc_18000D1AD
0x18000d19f  call    cs:__imp_RegCloseKey
0x18000d1a5  mov     [rbp+57h+hKey], 0
0x18000d1ad  lea     rax, [rbp+57h+arg_10]
0x18000d1b1  mov     r9d, 20019h; samDesired
0x18000d1b7  xor     r8d, r8d; ulOptions
0x18000d1ba  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18000d1bf  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000d1c6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d1cd  call    cs:__imp_RegOpenKeyExW
0x18000d1d3  mov     rdx, [rbp+57h+arg_10]
0x18000d1d7  test    eax, eax
0x18000d1d9  jz      short loc_18000D1EF
0x18000d1db  test    rdx, rdx
0x18000d1de  jz      short loc_18000D1EF
0x18000d1e0  mov     rcx, rdx; hKey
0x18000d1e3  call    cs:__imp_RegCloseKey
0x18000d1e9  xor     edx, edx; HKEY
0x18000d1eb  mov     [rbp+57h+arg_10], rdx
0x18000d1ef  mov     rcx, [rbp+57h+hKey]; hKey
0x18000d1f3  lea     r9, [rbp+57h+var_A0]; struct _NEGOEXTS_REG_PARAMETER *
0x18000d1f7  call    ?WSTGetRegistryDwords@@YAKPEAUHKEY__@@0KPEAU_NEGOEXTS_REG_PARAMETER@@@Z; WSTGetRegistryDwords(HKEY__ *,HKEY__ *,ulong,_NEGOEXTS_REG_PARAMETER *)
0x18000d1fc  mov     rcx, [rbp+57h+hKey]; hKey
0x18000d200  test    rcx, rcx
0x18000d203  jz      short loc_18000D213
0x18000d205  call    cs:__imp_RegCloseKey
0x18000d20b  mov     [rbp+57h+hKey], 0
0x18000d213  mov     rcx, [rbp+57h+arg_10]; hKey
0x18000d217  test    rcx, rcx
0x18000d21a  jz      short loc_18000D222
0x18000d21c  call    cs:__imp_RegCloseKey
0x18000d222  add     rsp, 0D0h
0x18000d229  pop     rbp
0x18000d22a  retn
```
