# RegistryUtil::isConfigEnabled(ushort *,bool)

- ea: `0x18001eaf4`
- end: `0x18001ed65`
- name: `?isConfigEnabled@RegistryUtil@@KA?AW4__MIDL___MIDL_itf_iasradius_0000_0000_0002@@PEAG_N@Z`
- size: `625`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180004c70`
- `0x18001debc`

## callees

- `0x180009540`
- `0x1800160b4`
- `0x18001d31c`
- `0x18001eaf4`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18001ec1d`
- `ADVAPI32!RegQueryValueExW` at `0x18001ece2`
- `ADVAPI32!RegQueryValueExW` at `0x18001ec1d`
- `ADVAPI32!RegQueryValueExW` at `0x18001ece2`
- `ADVAPI32!RegOpenKeyExW` at `0x18001eb77`
- `ADVAPI32!RegOpenKeyExW` at `0x18001eb77`
- `ADVAPI32!RegCloseKey` at `0x18001ed4e`
- `ADVAPI32!RegCloseKey` at `0x18001ed4e`

## string_xrefs

- `0x18001ebbd`: `RadiusProxy::isConfigEnabled RegOpenKeyEx(%S) Failed: 0x%x\n`
- `0x18001ec67`: `RadiusProxy::isConfigEnabled RegQueryValueEx(%S\%S) failed with 0x%x`
- `0x18001ed18`: `RadiusProxy::isConfigEnabled RegQueryValueEx(%S\%S) failed with 0x%x`
- `0x18001eb56`: `System\CurrentControlSet\Services\RemoteAccess\Policy\RadiusServer`
- `0x18001eb4f`: `System\CurrentControlSet\Services\RemoteAccess\Policy\RadiusClient`

## pseudocode

```c
__int64 __fastcall RegistryUtil::isConfigEnabled(const WCHAR *a1, char a2)
{
  unsigned int v3; // ebx
  const WCHAR *v4; // r15
  const WCHAR *v5; // r14
  LSTATUS v6; // eax
  char v7; // si
  LSTATUS v8; // eax
  char v9; // si
  LSTATUS v10; // eax
  char v11; // si
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  int Data; // [rsp+90h] [rbp+40h] BYREF
  DWORD cbData; // [rsp+A0h] [rbp+50h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+58h] BYREF

  Type = 4;
  Data = 0;
  v3 = 0;
  cbData = 4;
  hKey = 0;
  if ( a1 && *a1 )
  {
    v4 = L"RequireMessageAuthenticator";
    if ( !a2 )
      v4 = L"LimitProxyState";
    v5 = L"System\\CurrentControlSet\\Services\\RemoteAccess\\Policy\\RadiusClient";
    if ( !a2 )
      v5 = L"System\\CurrentControlSet\\Services\\RemoteAccess\\Policy\\RadiusServer";
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20019u, &hKey);
    v7 = v6;
    if ( v6 )
    {
      if ( v6 != 2
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("RadiusProxy::isConfigEnabled RegOpenKeyEx(%S) Failed: 0x%x\n");
        WPP_SF_sSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          (unsigned int)&WPP_71998f247ae0370d2143b01685e48c0c_Traceguids,
          (unsigned int)"NPSRAD",
          (__int64)v5,
          v7);
      }
    }
    else
    {
      v8 = RegQueryValueExW(hKey, v4, 0, &Type, (LPBYTE)&Data, &cbData);
      v9 = v8;
      if ( v8 )
      {
        if ( v8 != 2
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WppDbgPrint("RadiusProxy::isConfigEnabled RegQueryValueEx(%S\\%S) failed with 0x%x");
          WPP_SF_sSSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v5, (__int64)v4, v9);
        }
      }
      else if ( Data )
      {
        LOBYTE(v3) = Data != 1;
        ++v3;
        v10 = RegQueryValueExW(hKey, a1, 0, &Type, (LPBYTE)&Data, &cbData);
        v11 = v10;
        if ( v10 )
        {
          if ( v10 != 2
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WppDbgPrint("RadiusProxy::isConfigEnabled RegQueryValueEx(%S\\%S) failed with 0x%x");
            WPP_SF_sSSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v5, (__int64)a1, v11);
          }
        }
        else if ( Data )
        {
          v3 = 0;
        }
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v3;
}

```

## disassembly

```asm
0x18001eaf4  push    rbp
0x18001eaf6  push    rbx
0x18001eaf7  push    rsi
0x18001eaf8  push    rdi
0x18001eaf9  push    r12
0x18001eafb  push    r14
0x18001eafd  push    r15
0x18001eaff  mov     rbp, rsp
0x18001eb02  sub     rsp, 50h
0x18001eb06  xor     r12d, r12d
0x18001eb09  mov     eax, 4
0x18001eb0e  mov     [rbp+Type], eax
0x18001eb11  mov     rdi, rcx
0x18001eb14  mov     [rbp+Data], r12d
0x18001eb18  mov     ebx, r12d
0x18001eb1b  mov     [rbp+cbData], eax
0x18001eb1e  mov     [rbp+hKey], r12
0x18001eb22  test    rcx, rcx
0x18001eb25  jz      loc_18001ED54
0x18001eb2b  cmp     [rcx], r12w
0x18001eb2f  jz      loc_18001ED54
0x18001eb35  test    dl, dl
0x18001eb37  lea     rax, ?pwszProxyStateLimit@RegistryUtil@@1QBGB; "LimitProxyState"
0x18001eb3e  lea     r15, ?pwszRequireMessageAuthenticator@RegistryUtil@@1QBGB; "RequireMessageAuthenticator"
0x18001eb45  mov     r9d, 20019h; samDesired
0x18001eb4b  cmovz   r15, rax
0x18001eb4f  lea     r14, ?pwszRadiusClientRegKeyPath@RegistryUtil@@1QBGB; "System\\CurrentControlSet\\Services\\Re"...
0x18001eb56  lea     rax, ?pwszRadiusServerRegKeyPath@RegistryUtil@@1QBGB; "System\\CurrentControlSet\\Services\\Re"...
0x18001eb5d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001eb64  cmovz   r14, rax
0x18001eb68  lea     rax, [rbp+hKey]
0x18001eb6c  mov     rdx, r14; lpSubKey
0x18001eb6f  mov     [rsp+50h+phkResult], rax; phkResult
0x18001eb74  xor     r8d, r8d; ulOptions
0x18001eb77  call    cs:__imp_RegOpenKeyExW
0x18001eb7d  mov     esi, eax
0x18001eb7f  test    eax, eax
0x18001eb81  jz      short loc_18001EBFD
0x18001eb83  cmp     eax, 2
0x18001eb86  jz      loc_18001ED45
0x18001eb8c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eb93  lea     rax, WPP_GLOBAL_Control
0x18001eb9a  cmp     rcx, rax
0x18001eb9d  jz      loc_18001ED45
0x18001eba3  cmp     byte ptr [rcx+19h], 2
0x18001eba7  jb      loc_18001ED45
0x18001ebad  test    dword ptr [rcx+1Ch], 100h
0x18001ebb4  jz      loc_18001ED45
0x18001ebba  mov     r8d, esi
0x18001ebbd  lea     rcx, aRadiusproxyIsc_0; "RadiusProxy::isConfigEnabled RegOpenKey"...
0x18001ebc4  mov     rdx, r14
0x18001ebc7  call    WppDbgPrint
0x18001ebcc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ebd3  lea     edx, [r12+1Dh]
0x18001ebd8  mov     dword ptr [rsp+50h+lpcbData], esi
0x18001ebdc  lea     r9, aNpsrad; "NPSRAD"
0x18001ebe3  lea     r8, WPP_71998f247ae0370d2143b01685e48c0c_Traceguids
0x18001ebea  mov     [rsp+50h+phkResult], r14
0x18001ebef  mov     rcx, [rcx+10h]
0x18001ebf3  call    WPP_SF_sSD
0x18001ebf8  jmp     loc_18001ED45
0x18001ebfd  mov     rcx, [rbp+hKey]; hKey
0x18001ec01  lea     rax, [rbp+cbData]
0x18001ec05  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18001ec0a  lea     r9, [rbp+Type]; lpType
0x18001ec0e  lea     rax, [rbp+Data]
0x18001ec12  xor     r8d, r8d; lpReserved
0x18001ec15  mov     rdx, r15; lpValueName
0x18001ec18  mov     [rsp+50h+phkResult], rax; lpData
0x18001ec1d  call    cs:__imp_RegQueryValueExW
0x18001ec23  mov     esi, eax
0x18001ec25  test    eax, eax
0x18001ec27  jz      loc_18001ECAF
0x18001ec2d  cmp     eax, 2
0x18001ec30  jz      loc_18001ED45
0x18001ec36  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec3d  lea     rax, WPP_GLOBAL_Control
0x18001ec44  cmp     rcx, rax
0x18001ec47  jz      loc_18001ED45
0x18001ec4d  cmp     byte ptr [rcx+19h], 2
0x18001ec51  jb      loc_18001ED45
0x18001ec57  test    dword ptr [rcx+1Ch], 100h
0x18001ec5e  jz      loc_18001ED45
0x18001ec64  mov     r9d, esi
0x18001ec67  lea     rcx, aRadiusproxyIsc; "RadiusProxy::isConfigEnabled RegQueryVa"...
0x18001ec6e  mov     r8, r15
0x18001ec71  mov     rdx, r14
0x18001ec74  call    WppDbgPrint
0x18001ec79  mov     dword ptr [rsp+50h+var_20], esi; char
0x18001ec7d  mov     edx, 1Eh
0x18001ec82  mov     [rsp+50h+lpcbData], r15; __int64
0x18001ec87  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec8e  lea     r9, aNpsrad; "NPSRAD"
0x18001ec95  lea     r8, WPP_71998f247ae0370d2143b01685e48c0c_Traceguids
0x18001ec9c  mov     [rsp+50h+phkResult], r14; __int64
0x18001eca1  mov     rcx, [rcx+10h]; LoggerHandle
0x18001eca5  call    WPP_SF_sSSD
0x18001ecaa  jmp     loc_18001ED45
0x18001ecaf  mov     eax, [rbp+Data]
0x18001ecb2  test    eax, eax
0x18001ecb4  jz      loc_18001ED45
0x18001ecba  mov     rcx, [rbp+hKey]; hKey
0x18001ecbe  lea     r9, [rbp+Type]; lpType
0x18001ecc2  cmp     eax, 1
0x18001ecc5  mov     rdx, rdi; lpValueName
0x18001ecc8  lea     rax, [rbp+cbData]
0x18001eccc  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18001ecd1  setnz   bl
0x18001ecd4  lea     rax, [rbp+Data]
0x18001ecd8  xor     r8d, r8d; lpReserved
0x18001ecdb  mov     [rsp+50h+phkResult], rax; lpData
0x18001ece0  inc     ebx
0x18001ece2  call    cs:__imp_RegQueryValueExW
0x18001ece8  mov     esi, eax
0x18001ecea  test    eax, eax
0x18001ecec  jz      short loc_18001ED3D
0x18001ecee  cmp     eax, 2
0x18001ecf1  jz      short loc_18001ED45
0x18001ecf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ecfa  lea     rax, WPP_GLOBAL_Control
0x18001ed01  cmp     rcx, rax
0x18001ed04  jz      short loc_18001ED45
0x18001ed06  cmp     byte ptr [rcx+19h], 2
0x18001ed0a  jb      short loc_18001ED45
0x18001ed0c  test    dword ptr [rcx+1Ch], 100h
0x18001ed13  jz      short loc_18001ED45
0x18001ed15  mov     r9d, esi
0x18001ed18  lea     rcx, aRadiusproxyIsc; "RadiusProxy::isConfigEnabled RegQueryVa"...
0x18001ed1f  mov     r8, rdi
0x18001ed22  mov     rdx, r14
0x18001ed25  call    WppDbgPrint
0x18001ed2a  mov     dword ptr [rsp+50h+var_20], esi
0x18001ed2e  mov     edx, 1Fh
0x18001ed33  mov     [rsp+50h+lpcbData], rdi
0x18001ed38  jmp     loc_18001EC87
0x18001ed3d  cmp     [rbp+Data], r12d
0x18001ed41  cmovnz  ebx, r12d
0x18001ed45  mov     rcx, [rbp+hKey]; hKey
0x18001ed49  test    rcx, rcx
0x18001ed4c  jz      short loc_18001ED54
0x18001ed4e  call    cs:__imp_RegCloseKey
0x18001ed54  mov     eax, ebx
0x18001ed56  add     rsp, 50h
0x18001ed5a  pop     r15
0x18001ed5c  pop     r14
0x18001ed5e  pop     r12
0x18001ed60  pop     rdi
0x18001ed61  pop     rsi
0x18001ed62  pop     rbx
0x18001ed63  pop     rbp
0x18001ed64  retn
```
