# RegistryUtil::getGlobalConfig(bool)

- ea: `0x18001e500`
- end: `0x18001e6be`
- name: `?getGlobalConfig@RegistryUtil@@SA?AW4__MIDL___MIDL_itf_iasradius_0000_0000_0002@@_N@Z`
- size: `446`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18000b560`

## callees

- `0x180009540`
- `0x1800160b4`
- `0x18001d31c`
- `0x18001e500`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18001e615`
- `ADVAPI32!RegQueryValueExW` at `0x18001e615`
- `ADVAPI32!RegOpenKeyExW` at `0x18001e567`
- `ADVAPI32!RegOpenKeyExW` at `0x18001e567`
- `ADVAPI32!RegCloseKey` at `0x18001e6ad`
- `ADVAPI32!RegCloseKey` at `0x18001e6ad`

## string_xrefs

- `0x18001e5ad`: `RadiusProxy::getGlobalConfig RegOpenKeyEx(%S) Failed: 0x%x\n`
- `0x18001e64b`: `RadiusProxy::getGlobalConfig RegQueryValueEx(%S\%S) failed with 0x%x`
- `0x18001e54e`: `System\CurrentControlSet\Services\RemoteAccess\Policy\RadiusServer`
- `0x18001e527`: `System\CurrentControlSet\Services\RemoteAccess\Policy\RadiusClient`

## pseudocode

```c
__int64 __fastcall RegistryUtil::getGlobalConfig(char a1)
{
  const WCHAR *v1; // rbp
  const WCHAR *v2; // rsi
  unsigned int v3; // ebx
  LSTATUS v4; // eax
  char v5; // di
  LSTATUS v6; // eax
  char v7; // di
  int Data; // [rsp+70h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+10h] BYREF
  DWORD Type; // [rsp+80h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+20h] BYREF

  Data = 0;
  Type = 4;
  v1 = L"RequireMessageAuthenticator";
  cbData = 4;
  v2 = L"System\\CurrentControlSet\\Services\\RemoteAccess\\Policy\\RadiusClient";
  v3 = 0;
  hKey = 0;
  if ( !a1 )
  {
    v1 = L"LimitProxyState";
    v2 = L"System\\CurrentControlSet\\Services\\RemoteAccess\\Policy\\RadiusServer";
  }
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v2, 0, 0x20019u, &hKey);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 != 2
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("RadiusProxy::getGlobalConfig RegOpenKeyEx(%S) Failed: 0x%x\n");
      WPP_SF_sSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        (unsigned int)&WPP_71998f247ae0370d2143b01685e48c0c_Traceguids,
        (unsigned int)"NPSRAD",
        (__int64)v2,
        v5);
    }
  }
  else
  {
    v6 = RegQueryValueExW(hKey, v1, 0, &Type, (LPBYTE)&Data, &cbData);
    v7 = v6;
    if ( v6 )
    {
      if ( v6 != 2
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("RadiusProxy::getGlobalConfig RegQueryValueEx(%S\\%S) failed with 0x%x");
        WPP_SF_sSSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v2, (__int64)v1, v7);
      }
    }
    else if ( Data )
    {
      LOBYTE(v3) = Data != 1;
      ++v3;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x18001e500  mov     r11, rsp
0x18001e503  push    rbx
0x18001e504  push    rbp
0x18001e505  push    rsi
0x18001e506  push    rdi
0x18001e507  sub     rsp, 48h
0x18001e50b  mov     eax, 4
0x18001e510  mov     [rsp+68h+Data], 0
0x18001e518  mov     [r11+18h], eax
0x18001e51c  lea     rbp, ?pwszRequireMessageAuthenticator@RegistryUtil@@1QBGB; "RequireMessageAuthenticator"
0x18001e523  mov     [rsp+68h+cbData], eax
0x18001e527  lea     rsi, ?pwszRadiusClientRegKeyPath@RegistryUtil@@1QBGB; "System\\CurrentControlSet\\Services\\Re"...
0x18001e52e  xor     ebx, ebx
0x18001e530  lea     rax, ?pwszProxyStateLimit@RegistryUtil@@1QBGB; "LimitProxyState"
0x18001e537  test    cl, cl
0x18001e539  mov     [r11+20h], rbx
0x18001e53d  mov     r9d, 20019h; samDesired
0x18001e543  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e54a  cmovz   rbp, rax
0x18001e54e  lea     rax, ?pwszRadiusServerRegKeyPath@RegistryUtil@@1QBGB; "System\\CurrentControlSet\\Services\\Re"...
0x18001e555  cmovz   rsi, rax
0x18001e559  lea     rax, [r11+20h]
0x18001e55d  mov     rdx, rsi; lpSubKey
0x18001e560  mov     [r11-48h], rax
0x18001e564  xor     r8d, r8d; ulOptions
0x18001e567  call    cs:__imp_RegOpenKeyExW
0x18001e56d  mov     edi, eax
0x18001e56f  test    eax, eax
0x18001e571  jz      short loc_18001E5EB
0x18001e573  cmp     eax, 2
0x18001e576  jz      loc_18001E6A0
0x18001e57c  mov     rax, cs:WPP_GLOBAL_Control
0x18001e583  lea     rcx, WPP_GLOBAL_Control
0x18001e58a  cmp     rax, rcx
0x18001e58d  jz      loc_18001E6A0
0x18001e593  cmp     byte ptr [rax+19h], 2
0x18001e597  jb      loc_18001E6A0
0x18001e59d  test    dword ptr [rax+1Ch], 100h
0x18001e5a4  jz      loc_18001E6A0
0x18001e5aa  mov     r8d, edi
0x18001e5ad  lea     rcx, aRadiusproxyGet_0; "RadiusProxy::getGlobalConfig RegOpenKey"...
0x18001e5b4  mov     rdx, rsi
0x18001e5b7  call    WppDbgPrint
0x18001e5bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e5c3  lea     edx, [rbx+20h]
0x18001e5c6  mov     dword ptr [rsp+68h+lpcbData], edi
0x18001e5ca  lea     r9, aNpsrad; "NPSRAD"
0x18001e5d1  lea     r8, WPP_71998f247ae0370d2143b01685e48c0c_Traceguids
0x18001e5d8  mov     [rsp+68h+lpData], rsi
0x18001e5dd  mov     rcx, [rcx+10h]
0x18001e5e1  call    WPP_SF_sSD
0x18001e5e6  jmp     loc_18001E6A0
0x18001e5eb  mov     rcx, [rsp+68h+hKey]; hKey
0x18001e5f3  lea     rax, [rsp+68h+cbData]
0x18001e5f8  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18001e5fd  lea     r9, [rsp+68h+Type]; lpType
0x18001e605  lea     rax, [rsp+68h+Data]
0x18001e60a  xor     r8d, r8d; lpReserved
0x18001e60d  mov     rdx, rbp; lpValueName
0x18001e610  mov     [rsp+68h+lpData], rax; lpData
0x18001e615  call    cs:__imp_RegQueryValueExW
0x18001e61b  mov     edi, eax
0x18001e61d  test    eax, eax
0x18001e61f  jz      short loc_18001E690
0x18001e621  cmp     eax, 2
0x18001e624  jz      short loc_18001E6A0
0x18001e626  mov     rax, cs:WPP_GLOBAL_Control
0x18001e62d  lea     rcx, WPP_GLOBAL_Control
0x18001e634  cmp     rax, rcx
0x18001e637  jz      short loc_18001E6A0
0x18001e639  cmp     byte ptr [rax+19h], 2
0x18001e63d  jb      short loc_18001E6A0
0x18001e63f  test    dword ptr [rax+1Ch], 100h
0x18001e646  jz      short loc_18001E6A0
0x18001e648  mov     r9d, edi
0x18001e64b  lea     rcx, aRadiusproxyGet_1; "RadiusProxy::getGlobalConfig RegQueryVa"...
0x18001e652  mov     r8, rbp
0x18001e655  mov     rdx, rsi
0x18001e658  call    WppDbgPrint
0x18001e65d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e664  lea     r9, aNpsrad; "NPSRAD"
0x18001e66b  mov     dword ptr [rsp+68h+var_38], edi; char
0x18001e66f  lea     r8, WPP_71998f247ae0370d2143b01685e48c0c_Traceguids
0x18001e676  mov     edx, 21h ; '!'
0x18001e67b  mov     [rsp+68h+lpcbData], rbp; __int64
0x18001e680  mov     [rsp+68h+lpData], rsi; __int64
0x18001e685  mov     rcx, [rcx+10h]; LoggerHandle
0x18001e689  call    WPP_SF_sSSD
0x18001e68e  jmp     short loc_18001E6A0
0x18001e690  mov     ecx, [rsp+68h+Data]
0x18001e694  test    ecx, ecx
0x18001e696  jz      short loc_18001E6A0
0x18001e698  cmp     ecx, 1
0x18001e69b  setnz   bl
0x18001e69e  inc     ebx
0x18001e6a0  mov     rcx, [rsp+68h+hKey]; hKey
0x18001e6a8  test    rcx, rcx
0x18001e6ab  jz      short loc_18001E6B3
0x18001e6ad  call    cs:__imp_RegCloseKey
0x18001e6b3  mov     eax, ebx
0x18001e6b5  add     rsp, 48h
0x18001e6b9  pop     rdi
0x18001e6ba  pop     rsi
0x18001e6bb  pop     rbp
0x18001e6bc  pop     rbx
0x18001e6bd  retn
```
