# OSKMigratedSettings::MigrateLegacySettings(void)

- ea: `0x140017ac0`
- end: `0x140017cdd`
- name: `?MigrateLegacySettings@OSKMigratedSettings@@SAXXZ`
- size: `541`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400174f8`

## callees

- `0x140002de3`
- `0x140005c90`
- `0x140007e90`
- `0x140017ac0`
- `0x140017ce4`
- `0x140025d70`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x140017ba1`
- `ADVAPI32!RegDeleteValueW` at `0x140017c37`
- `ADVAPI32!RegDeleteValueW` at `0x140017ba1`
- `ADVAPI32!RegDeleteValueW` at `0x140017c37`
- `ADVAPI32!RegGetValueW` at `0x140017b50`
- `ADVAPI32!RegGetValueW` at `0x140017be5`
- `ADVAPI32!RegGetValueW` at `0x140017b50`
- `ADVAPI32!RegGetValueW` at `0x140017be5`

## pseudocode

```c
void OSKMigratedSettings::MigrateLegacySettings(void)
{
  char v0; // bl
  char v1; // di
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  int pvData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD v4; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v6; // [rsp+58h] [rbp-A8h]
  __int64 v7; // [rsp+60h] [rbp-A0h]
  int v8; // [rsp+68h] [rbp-98h]
  _BYTE v9[44]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v10; // [rsp+9Ch] [rbp-64h]
  int v11; // [rsp+A8h] [rbp-58h]
  unsigned int v12; // [rsp+ACh] [rbp-54h]
  unsigned int v13; // [rsp+170h] [rbp+70h]
  __int64 v14; // [rsp+174h] [rbp+74h]
  int v15; // [rsp+258h] [rbp+158h]
  unsigned int v16; // [rsp+25Ch] [rbp+15Ch]

  memset_0(v9, 0, 0x1F8u);
  v4 = 504;
  pvData = 0;
  pcbData = 4;
  v0 = 0;
  v1 = 0;
  if ( !RegGetValueW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Osk", L"Stepping", 0x10u, 0, &pvData, &pcbData) )
  {
    hKey = 0;
    v6 = 0;
    v7 = 0;
    v0 = 1;
    if ( !(unsigned int)ATL::CRegKey::Open(
                          (ATL::CRegKey *)&hKey,
                          HKEY_CURRENT_USER,
                          L"Software\\Microsoft\\Osk",
                          0x20006u) )
      RegDeleteValueW(hKey, L"Stepping");
    ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
  }
  if ( !RegGetValueW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Osk", L"Setting", 8u, 0, v9, &v4) )
  {
    hKey = 0;
    v6 = 0;
    v7 = 0;
    v1 = 1;
    if ( !(unsigned int)ATL::CRegKey::Open(
                          (ATL::CRegKey *)&hKey,
                          HKEY_CURRENT_USER,
                          L"Software\\Microsoft\\Osk",
                          0x20006u) )
      RegDeleteValueW(hKey, L"Setting");
    ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
  }
  if ( v0 && pcbData == 4 && pvData == 3 && v1 && v4 == 504 )
  {
    hKey = (HKEY)__PAIR64__(v12, v10);
    v6 = __PAIR64__(v16, v13);
    v7 = v14;
    if ( v15 )
      v8 = 3;
    else
      v8 = (v11 != 0) + 1;
    OSKMigratedSettings::SaveSettings((OSKMigratedSettings *)&hKey);
  }
}

```

## disassembly

```asm
0x140017ac0  push    rbp
0x140017ac2  push    rbx
0x140017ac3  push    rdi
0x140017ac4  push    r15
0x140017ac6  lea     rbp, [rsp-188h]
0x140017ace  sub     rsp, 288h
0x140017ad5  mov     rax, cs:__security_cookie
0x140017adc  xor     rax, rsp
0x140017adf  mov     [rbp+1A0h+var_30], rax
0x140017ae6  xor     edx, edx; Val
0x140017ae8  lea     rcx, [rsp+2A0h+var_230]; void *
0x140017aed  mov     r8d, 1F8h; Size
0x140017af3  call    memset_0
0x140017af8  lea     rax, [rsp+2A0h+var_260]
0x140017afd  mov     [rsp+2A0h+var_258], 1F8h
0x140017b05  mov     [rsp+2A0h+pcbData], rax; pcbData
0x140017b0a  lea     r8, ValueName; "Stepping"
0x140017b11  lea     rax, [rsp+2A0h+var_25C]
0x140017b16  mov     [rsp+2A0h+var_25C], 0
0x140017b1e  mov     [rsp+2A0h+pvData], rax; pvData
0x140017b23  lea     rdx, SubKey; "Software\\Microsoft\\Osk"
0x140017b2a  mov     r15, 0FFFFFFFF80000001h
0x140017b31  mov     [rsp+2A0h+pdwType], 0; pdwType
0x140017b3a  mov     r9d, 10h; dwFlags
0x140017b40  mov     [rsp+2A0h+var_260], 4
0x140017b48  mov     rcx, r15; hkey
0x140017b4b  xor     bl, bl
0x140017b4d  xor     dil, dil
0x140017b50  call    cs:__imp_RegGetValueW
0x140017b56  test    eax, eax
0x140017b58  jnz     short loc_140017BB1
0x140017b5a  mov     r9d, 20006h; unsigned int
0x140017b60  mov     [rsp+2A0h+hKey], 0
0x140017b69  lea     r8, SubKey; "Software\\Microsoft\\Osk"
0x140017b70  mov     [rsp+2A0h+var_248], 0
0x140017b79  mov     rdx, r15; hKey
0x140017b7c  mov     [rsp+2A0h+var_240], 0
0x140017b85  lea     rcx, [rsp+2A0h+hKey]; this
0x140017b8a  mov     bl, 1
0x140017b8c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140017b91  test    eax, eax
0x140017b93  jnz     short loc_140017BA7
0x140017b95  mov     rcx, [rsp+2A0h+hKey]; hKey
0x140017b9a  lea     rdx, ValueName; "Stepping"
0x140017ba1  call    cs:__imp_RegDeleteValueW
0x140017ba7  lea     rcx, [rsp+2A0h+hKey]; this
0x140017bac  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140017bb1  lea     rax, [rsp+2A0h+var_258]
0x140017bb6  mov     r9d, 8; dwFlags
0x140017bbc  mov     [rsp+2A0h+pcbData], rax; pcbData
0x140017bc1  lea     r8, Value; "Setting"
0x140017bc8  lea     rax, [rsp+2A0h+var_230]
0x140017bcd  mov     rcx, r15; hkey
0x140017bd0  mov     [rsp+2A0h+pvData], rax; pvData
0x140017bd5  lea     rdx, SubKey; "Software\\Microsoft\\Osk"
0x140017bdc  mov     [rsp+2A0h+pdwType], 0; pdwType
0x140017be5  call    cs:__imp_RegGetValueW
0x140017beb  test    eax, eax
0x140017bed  jnz     short loc_140017C47
0x140017bef  mov     r9d, 20006h; unsigned int
0x140017bf5  mov     [rsp+2A0h+hKey], 0
0x140017bfe  lea     r8, SubKey; "Software\\Microsoft\\Osk"
0x140017c05  mov     [rsp+2A0h+var_248], 0
0x140017c0e  mov     rdx, r15; hKey
0x140017c11  mov     [rsp+2A0h+var_240], 0
0x140017c1a  lea     rcx, [rsp+2A0h+hKey]; this
0x140017c1f  mov     dil, 1
0x140017c22  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140017c27  test    eax, eax
0x140017c29  jnz     short loc_140017C3D
0x140017c2b  mov     rcx, [rsp+2A0h+hKey]; hKey
0x140017c30  lea     rdx, Value; "Setting"
0x140017c37  call    cs:__imp_RegDeleteValueW
0x140017c3d  lea     rcx, [rsp+2A0h+hKey]; this
0x140017c42  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140017c47  test    bl, bl
0x140017c49  jz      short loc_140017CC1
0x140017c4b  cmp     [rsp+2A0h+var_260], 4
0x140017c50  jnz     short loc_140017CC1
0x140017c52  cmp     [rsp+2A0h+var_25C], 3
0x140017c57  jnz     short loc_140017CC1
0x140017c59  test    dil, dil
0x140017c5c  jz      short loc_140017CC1
0x140017c5e  cmp     [rsp+2A0h+var_258], 1F8h
0x140017c66  jnz     short loc_140017CC1
0x140017c68  cmp     [rbp+1A0h+var_48], 0
0x140017c6f  mov     eax, [rbp+1A0h+var_204]
0x140017c72  mov     dword ptr [rsp+2A0h+hKey], eax
0x140017c76  mov     eax, [rbp+1A0h+var_1F4]
0x140017c79  mov     dword ptr [rsp+2A0h+hKey+4], eax
0x140017c7d  mov     eax, [rbp+1A0h+var_130]
0x140017c80  mov     dword ptr [rsp+2A0h+var_248], eax
0x140017c84  mov     eax, [rbp+1A0h+var_44]
0x140017c8a  mov     dword ptr [rsp+2A0h+var_248+4], eax
0x140017c8e  mov     eax, dword ptr [rbp+1A0h+var_12C]
0x140017c91  mov     dword ptr [rsp+2A0h+var_240], eax
0x140017c95  mov     eax, dword ptr [rbp+1A0h+var_12C+4]
0x140017c98  mov     dword ptr [rsp+2A0h+var_240+4], eax
0x140017c9c  jz      short loc_140017CA8
0x140017c9e  mov     [rsp+2A0h+var_238], 3
0x140017ca6  jmp     short loc_140017CB7
0x140017ca8  mov     eax, [rbp+1A0h+var_1F8]
0x140017cab  neg     eax
0x140017cad  sbb     ecx, ecx
0x140017caf  neg     ecx
0x140017cb1  inc     ecx
0x140017cb3  mov     [rsp+2A0h+var_238], ecx
0x140017cb7  lea     rcx, [rsp+2A0h+hKey]; this
0x140017cbc  call    ?SaveSettings@OSKMigratedSettings@@QEAAJXZ; OSKMigratedSettings::SaveSettings(void)
0x140017cc1  mov     rcx, [rbp+1A0h+var_30]
0x140017cc8  xor     rcx, rsp; StackCookie
0x140017ccb  call    __security_check_cookie
0x140017cd0  add     rsp, 288h
0x140017cd7  pop     r15
0x140017cd9  pop     rdi
0x140017cda  pop     rbx
0x140017cdb  pop     rbp
0x140017cdc  retn
```
