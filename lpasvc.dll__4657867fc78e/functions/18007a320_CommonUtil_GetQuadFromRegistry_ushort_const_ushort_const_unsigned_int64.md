# CommonUtil::GetQuadFromRegistry(ushort const *,ushort const *,unsigned __int64 &)

- ea: `0x18007a320`
- end: `0x18007a3fe`
- name: `?GetQuadFromRegistry@CommonUtil@@YAJPEBG0AEA_K@Z`
- size: `222`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007a878`
- `0x18007ac3c`

## callees

- `0x18007a320`
- `0x180080dfc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007a3eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007a3eb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007a356`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007a356`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007a3bc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007a3bc`

## string_xrefs

- `0x18007a390`: `DatetimeLatestAttempt`

## pseudocode

```c
__int64 __fastcall CommonUtil::GetQuadFromRegistry(
        LPCWSTR lpSubKey,
        const unsigned __int16 *a2,
        BYTE *a3,
        unsigned __int64 *a4)
{
  LSTATUS v5; // eax
  signed int v6; // ebx
  unsigned __int8 IsEnabled; // al
  LSTATUS v8; // eax
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  const unsigned __int16 *cbData; // [rsp+58h] [rbp+10h] BYREF
  DWORD Type; // [rsp+68h] [rbp+20h] BYREF

  cbData = a2;
  hKey = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 >= 0 )
  {
    LODWORD(cbData) = 0;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::GetImpl'::`2'::impl);
    Type = 0;
    LODWORD(cbData) = 4 * IsEnabled + 4;
    v8 = RegQueryValueExW(hKey, L"DatetimeLatestAttempt", 0, &Type, a3, (LPDWORD)&cbData);
    v6 = v8;
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    if ( v6 >= 0 && Type != 11 )
      v6 = -2147418113;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18007a320  mov     r11, rsp
0x18007a323  mov     [r11+8], rbx
0x18007a327  mov     [r11+10h], rdx
0x18007a32b  push    rdi
0x18007a32c  sub     rsp, 40h
0x18007a330  mov     rdi, r8
0x18007a333  mov     qword ptr [r11-18h], 0
0x18007a33b  lea     rax, [r11-18h]
0x18007a33f  mov     rdx, rcx; lpSubKey
0x18007a342  xor     r8d, r8d; ulOptions
0x18007a345  mov     [r11-28h], rax
0x18007a349  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007a350  mov     r9d, 20019h; samDesired
0x18007a356  call    cs:__imp_RegOpenKeyExW
0x18007a35c  mov     ebx, eax
0x18007a35e  test    eax, eax
0x18007a360  jle     short loc_18007A36B
0x18007a362  movzx   ebx, ax
0x18007a365  or      ebx, 80070000h
0x18007a36b  test    ebx, ebx
0x18007a36d  js      short loc_18007A3E1
0x18007a36f  mov     dword ptr [rsp+48h+cbData], 0
0x18007a377  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY> `wil::Feature<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::GetImpl(void)'::`2'::impl
0x18007a37e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::__private_IsEnabled(void)
0x18007a383  mov     rcx, [rsp+48h+hKey]; hKey
0x18007a388  lea     r9, [rsp+48h+Type]; lpType
0x18007a38d  movzx   eax, al
0x18007a390  lea     rdx, ValueName; "DatetimeLatestAttempt"
0x18007a397  xor     r8d, r8d; lpReserved
0x18007a39a  mov     [rsp+48h+Type], 0
0x18007a3a2  lea     eax, ds:4[rax*4]
0x18007a3a9  mov     dword ptr [rsp+48h+cbData], eax
0x18007a3ad  lea     rax, [rsp+48h+cbData]
0x18007a3b2  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18007a3b7  mov     [rsp+48h+lpData], rdi; lpData
0x18007a3bc  call    cs:__imp_RegQueryValueExW
0x18007a3c2  mov     ebx, eax
0x18007a3c4  test    eax, eax
0x18007a3c6  jle     short loc_18007A3D1
0x18007a3c8  movzx   ebx, ax
0x18007a3cb  or      ebx, 80070000h
0x18007a3d1  test    ebx, ebx
0x18007a3d3  js      short loc_18007A3E1
0x18007a3d5  cmp     [rsp+48h+Type], 0Bh
0x18007a3da  jz      short loc_18007A3E1
0x18007a3dc  mov     ebx, 8000FFFFh
0x18007a3e1  mov     rcx, [rsp+48h+hKey]; hKey
0x18007a3e6  test    rcx, rcx
0x18007a3e9  jz      short loc_18007A3F1
0x18007a3eb  call    cs:__imp_RegCloseKey
0x18007a3f1  mov     eax, ebx
0x18007a3f3  mov     rbx, [rsp+48h+arg_0]
0x18007a3f8  add     rsp, 40h
0x18007a3fc  pop     rdi
0x18007a3fd  retn
```
