# Microsoft::Bluetooth::Services::BthServ::BthpRemoveLocalDeviceInstance(void *,_GUID const *,int)

- ea: `0x180027c48`
- end: `0x180027ea1`
- name: `?BthpRemoveLocalDeviceInstance@BthServ@Services@Bluetooth@Microsoft@@YAKPEAXPEBU_GUID@@H@Z`
- size: `601`
- prototype: `unsigned int __fastcall(Microsoft::Bluetooth::Services::BthServ *__hidden this, void *, const struct _GUID *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180025304`

## callees

- `0x1800017a0`
- `0x18000270c`
- `0x180008af8`
- `0x180017944`
- `0x18001b3b0`
- `0x180027c48`
- `0x180031788`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027d32`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027d81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027d32`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027d81`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027dbd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027dbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027dcf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027ddf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027dcf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027ddf`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180027d00`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180027d00`

## string_xrefs

- `0x180027c84`: `System\CurrentControlSet\Services\BTHPORT\Parameters\LocalServices\`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BthpRemoveLocalDeviceInstance(
        Microsoft::Bluetooth::Services::BthServ *this,
        void *a2,
        const struct _GUID *a3)
{
  unsigned int v3; // edi
  __int128 v4; // xmm1
  __int128 v5; // xmm0
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int64 v10; // rax
  unsigned int v11; // ebx
  __int64 v12; // rcx
  PHKEY phkResult; // [rsp+28h] [rbp-E0h]
  LPDWORD lpcbData; // [rsp+30h] [rbp-D8h]
  BYTE Data[4]; // [rsp+88h] [rbp-80h] BYREF
  DWORD cbData; // [rsp+8Ch] [rbp-7Ch] BYREF
  HKEY v18; // [rsp+90h] [rbp-78h] BYREF
  HKEY hKey; // [rsp+98h] [rbp-70h] BYREF
  WCHAR v20[64]; // [rsp+A8h] [rbp-60h] BYREF
  _OWORD SubKey[8]; // [rsp+128h] [rbp+20h] BYREF
  __int64 v22; // [rsp+1A8h] [rbp+A0h] BYREF
  _BYTE v23[88]; // [rsp+1B0h] [rbp+A8h] BYREF

  hKey = 0;
  *(_DWORD *)Data = 0;
  v3 = (unsigned int)a3;
  v4 = *(_OWORD *)L"urrentControlSet\\Services\\BTHPORT\\Parameters\\LocalServices\\";
  SubKey[0] = *(_OWORD *)L"System\\CurrentControlSet\\Services\\BTHPORT\\Parameters\\LocalServices\\";
  v5 = *(_OWORD *)L"ntrolSet\\Services\\BTHPORT\\Parameters\\LocalServices\\";
  SubKey[1] = v4;
  v6 = *(_OWORD *)L"\\Services\\BTHPORT\\Parameters\\LocalServices\\";
  SubKey[2] = v5;
  v7 = *(_OWORD *)L"s\\BTHPORT\\Parameters\\LocalServices\\";
  SubKey[3] = v6;
  v8 = *(_OWORD *)L"T\\Parameters\\LocalServices\\";
  SubKey[4] = v7;
  v9 = *(_OWORD *)L"ters\\LocalServices\\";
  SubKey[5] = v8;
  SubKey[6] = v9;
  v10 = *(_QWORD *)L"es\\";
  SubKey[7] = *(_OWORD *)L"alServices\\";
  v22 = v10;
  memset_0(v23, 0, 0x4Eu);
  if ( StringFromGUID2(&SerialPortServiceClass_UUID, (LPOLESTR)&v22 + 3, 39) != 39 )
    return 87;
  v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)SubKey, 0, 0x20019u, &hKey);
  if ( !v11 )
  {
    if ( (int)StringCchPrintfW(v20, 0x20u, L"%u", v3) >= 0 )
    {
      v18 = 0;
      v11 = RegOpenKeyExW(hKey, v20, 0, 0x20019u, &v18);
      if ( !v11 )
      {
        cbData = 4;
        v11 = RegQueryValueExW(v18, L"PnpInstance", 0, 0, Data, &cbData);
        RegCloseKey(v18);
      }
    }
    RegCloseKey(hKey);
    if ( !v11 )
    {
      LODWORD(lpcbData) = 4096;
      LODWORD(phkResult) = 0;
      if ( (int)StringCbPrintfW(
                  v20,
                  0x7Cu,
                  L"{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}#000000000000_%08x",
                  4353,
                  phkResult,
                  lpcbData,
                  128,
                  0,
                  0,
                  128,
                  95,
                  155,
                  52,
                  251,
                  *(_DWORD *)Data) >= 0 )
      {
        if ( (int)BthDevnodeSearchAndUninstallEnumerator(v12, v20) < 0 )
          return (unsigned int)BthServClientUninstallDevice(0, (char *)v20);
        return v11;
      }
      return 87;
    }
  }
  return v11;
}

```

## disassembly

```asm
0x180027c48  mov     rax, rsp
0x180027c4b  mov     [rax+8], rbx
0x180027c4f  mov     [rax+10h], rdi
0x180027c53  mov     [rax+20h], r15
0x180027c57  push    rbp
0x180027c58  lea     rbp, [rax-118h]
0x180027c5f  sub     rsp, 210h
0x180027c66  mov     rax, cs:__security_cookie
0x180027c6d  xor     rax, rsp
0x180027c70  mov     [rbp+110h+var_10], rax
0x180027c77  and     [rbp+110h+hKey], 0
0x180027c7c  lea     rcx, [rbp+110h+SubKey]
0x180027c80  and     dword ptr [rbp+110h+Data], 0
0x180027c84  lea     rax, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\BT"...
0x180027c8b  movups  xmm0, xmmword ptr [rax]
0x180027c8e  mov     r15d, 80h
0x180027c94  mov     edi, r8d
0x180027c97  movups  xmm1, xmmword ptr [rax+10h]
0x180027c9b  xor     edx, edx; Val
0x180027c9d  movups  xmmword ptr [rcx], xmm0
0x180027ca0  lea     r8d, [r15-32h]; Size
0x180027ca4  movups  xmm0, xmmword ptr [rax+20h]
0x180027ca8  movups  xmmword ptr [rcx+10h], xmm1
0x180027cac  movups  xmm1, xmmword ptr [rax+30h]
0x180027cb0  movups  xmmword ptr [rcx+20h], xmm0
0x180027cb4  movups  xmm0, xmmword ptr [rax+40h]
0x180027cb8  movups  xmmword ptr [rcx+30h], xmm1
0x180027cbc  movups  xmm1, xmmword ptr [rax+50h]
0x180027cc0  movups  xmmword ptr [rcx+40h], xmm0
0x180027cc4  movups  xmm0, xmmword ptr [rax+60h]
0x180027cc8  movups  xmmword ptr [rcx+50h], xmm1
0x180027ccc  movups  xmmword ptr [rcx+60h], xmm0
0x180027cd0  movups  xmm0, xmmword ptr [rax+70h]
0x180027cd4  mov     rax, [rax+r15]
0x180027cd8  movups  xmmword ptr [rcx+r15-10h], xmm0
0x180027cde  mov     [rcx+r15], rax
0x180027ce2  lea     rcx, [rbp+110h+var_68]; void *
0x180027ce9  call    memset_0
0x180027cee  lea     r8d, [r15-59h]; cchMax
0x180027cf2  lea     rdx, [rbp+110h+sz]; lpsz
0x180027cf9  lea     rcx, SerialPortServiceClass_UUID; rguid
0x180027d00  call    cs:__imp_StringFromGUID2
0x180027d07  nop     dword ptr [rax+rax+00h]
0x180027d0c  cmp     eax, 27h ; '''
0x180027d0f  jnz     loc_180027E71
0x180027d15  lea     rax, [rbp+110h+hKey]
0x180027d19  mov     r9d, 20019h; samDesired
0x180027d1f  xor     r8d, r8d; ulOptions
0x180027d22  mov     [rsp+210h+phkResult], rax; phkResult
0x180027d27  lea     rdx, [rbp+110h+SubKey]; lpSubKey
0x180027d2b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027d32  call    cs:__imp_RegOpenKeyExW
0x180027d39  nop     dword ptr [rax+rax+00h]
0x180027d3e  mov     ebx, eax
0x180027d40  test    eax, eax
0x180027d42  jnz     loc_180027E76
0x180027d48  mov     r9d, edi
0x180027d4b  lea     r8, aU; "%u"
0x180027d52  lea     edx, [rax+20h]; unsigned __int64
0x180027d55  lea     rcx, [rbp+110h+var_170]; unsigned __int16 *
0x180027d59  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027d5e  test    eax, eax
0x180027d60  js      short loc_180027DDB
0x180027d62  mov     rcx, [rbp+110h+hKey]; hKey
0x180027d66  lea     rax, [rbp+110h+var_188]
0x180027d6a  and     [rbp+110h+var_188], 0
0x180027d6f  lea     rdx, [rbp+110h+var_170]; lpSubKey
0x180027d73  mov     r9d, 20019h; samDesired
0x180027d79  mov     [rsp+210h+phkResult], rax; phkResult
0x180027d7e  xor     r8d, r8d; ulOptions
0x180027d81  call    cs:__imp_RegOpenKeyExW
0x180027d88  nop     dword ptr [rax+rax+00h]
0x180027d8d  mov     ebx, eax
0x180027d8f  test    eax, eax
0x180027d91  jnz     short loc_180027DDB
0x180027d93  mov     rcx, [rbp+110h+var_188]; hKey
0x180027d97  lea     rax, [rbp+110h+cbData]
0x180027d9b  mov     [rsp+210h+lpcbData], rax; lpcbData
0x180027da0  lea     rdx, aPnpinstance; "PnpInstance"
0x180027da7  lea     rax, [rbp+110h+Data]
0x180027dab  mov     [rbp+110h+cbData], 4
0x180027db2  xor     r9d, r9d; lpType
0x180027db5  mov     [rsp+210h+phkResult], rax; lpData
0x180027dba  xor     r8d, r8d; lpReserved
0x180027dbd  call    cs:__imp_RegQueryValueExW
0x180027dc4  nop     dword ptr [rax+rax+00h]
0x180027dc9  mov     rcx, [rbp+110h+var_188]; hKey
0x180027dcd  mov     ebx, eax
0x180027dcf  call    cs:__imp_RegCloseKey
0x180027dd6  nop     dword ptr [rax+rax+00h]
0x180027ddb  mov     rcx, [rbp+110h+hKey]; hKey
0x180027ddf  call    cs:__imp_RegCloseKey
0x180027de6  nop     dword ptr [rax+rax+00h]
0x180027deb  test    ebx, ebx
0x180027ded  jnz     loc_180027E76
0x180027df3  mov     eax, dword ptr [rbp+110h+Data]
0x180027df6  lea     r8, a08lx04x04x02x0_0; "{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%"...
0x180027dfd  mov     [rsp+210h+var_1A0], eax
0x180027e01  lea     edx, [rbx+7Ch]; unsigned __int64
0x180027e04  mov     [rsp+210h+var_1A8], 0FBh
0x180027e0c  lea     rcx, [rbp+110h+var_170]; unsigned __int16 *
0x180027e10  mov     [rsp+210h+var_1B0], 34h ; '4'
0x180027e18  mov     r9d, 1101h
0x180027e1e  mov     [rsp+210h+var_1B8], 9Bh
0x180027e26  mov     [rsp+210h+var_1C0], 5Fh ; '_'
0x180027e2e  mov     [rsp+210h+var_1C8], r15d
0x180027e33  and     [rsp+210h+var_1D0], ebx
0x180027e37  and     [rsp+210h+var_1D8], ebx
0x180027e3b  mov     [rsp+210h+var_1E0], r15d
0x180027e40  mov     dword ptr [rsp+210h+lpcbData], 1000h
0x180027e48  and     dword ptr [rsp+210h+phkResult], ebx
0x180027e4c  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027e51  test    eax, eax
0x180027e53  js      short loc_180027E71
0x180027e55  lea     rdx, [rbp+110h+var_170]
0x180027e59  call    BthDevnodeSearchAndUninstallEnumerator
0x180027e5e  test    eax, eax
0x180027e60  jns     short loc_180027E76
0x180027e62  lea     rdx, [rbp+110h+var_170]; unsigned __int16 *
0x180027e66  xor     ecx, ecx; void *
0x180027e68  call    ?BthServClientUninstallDevice@@YAJPEAXPEAG@Z; BthServClientUninstallDevice(void *,ushort *)
0x180027e6d  mov     ebx, eax
0x180027e6f  jmp     short loc_180027E76
0x180027e71  mov     ebx, 57h ; 'W'
0x180027e76  mov     eax, ebx
0x180027e78  mov     rcx, [rbp+110h+var_10]
0x180027e7f  xor     rcx, rsp; StackCookie
0x180027e82  call    __security_check_cookie
0x180027e87  lea     r11, [rsp+210h+var_s0]
0x180027e8f  mov     rbx, [r11+10h]
0x180027e93  mov     rdi, [r11+18h]
0x180027e97  mov     r15, [r11+28h]
0x180027e9b  mov     rsp, r11
0x180027e9e  pop     rbp
0x180027e9f  retn
```
