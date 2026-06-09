# Reg_CreateKey

- ea: `0x18003f31c`
- end: `0x18003f652`
- name: `Reg_CreateKey`
- size: `822`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180008010`
- `0x18008148c`

## callees

- `0x180001780`
- `0x18003de30`
- `0x18003f31c`
- `0x18007f24c`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800cccb0`
- `0x1800dc4ac`
- `0x1800dc670`
- `0x1800dc9e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f4b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f4b6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003f56c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003f56c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f476`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f476`
- `ntdll!RtlGetPersistedStateLocation` at `0x18003f3b6`
- `ntdll!RtlGetPersistedStateLocation` at `0x18003f3b6`

## string_xrefs

- `0x18003f5e6`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18003f62a`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18003f382`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`
- `0x18003f4d5`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`
- `0x18003f58a`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`
- `0x18003f60f`: `Dnscache`
- `0x18003f608`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x18003f39c`: `DnscacheTcpipInterfaces`
- `0x18003f4ce`: `DnscacheTcpipInterfaces`
- `0x18003f524`: `DnscacheTcpipInterfaces`
- `0x18003f596`: `DnscacheTcpipInterfaces`

## pseudocode

```c
HKEY __fastcall Reg_CreateKey(unsigned __int64 a1, int a2)
{
  int v4; // edx
  int v5; // ecx
  int v6; // r8d
  int PersistedStateLocation; // eax
  int v8; // edx
  int v9; // ecx
  int v10; // r8d
  int v11; // esi
  unsigned __int64 v12; // rdx
  WCHAR *v13; // r8
  __int64 v14; // rax
  WCHAR *v15; // rcx
  WCHAR *v16; // rcx
  unsigned int v17; // ebx
  WCHAR *v18; // rdx
  LSTATUS v19; // eax
  __int64 v21; // rcx
  int PersistedRegistryLocation; // eax
  const WCHAR *v23; // rax
  unsigned int v24; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition[4]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF

  phkResult = 0;
  dwDisposition[0] = 0;
  memset_0(SubKey, 0, 0x20Au);
  if ( a1 > 3 )
  {
    v24 = 0;
    if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
      WPP_SF_SSSqd(
        v5,
        v4,
        v6,
        (unsigned int)L"DnscacheTcpipInterfaces",
        (__int64)L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces",
        a1,
        (__int64)SubKey,
        10);
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"DnscacheTcpipInterfaces",
                               0,
                               L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces",
                               0,
                               SubKey,
                               522,
                               &v24);
    v11 = PersistedStateLocation;
    if ( PersistedStateLocation < 0 )
    {
      if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
        WPP_SF_SSSd(
          v9,
          v8,
          v10,
          (unsigned int)L"DnscacheTcpipInterfaces",
          (__int64)L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces",
          a1,
          PersistedStateLocation);
      v17 = HRESULT_FROM_NTSTATUS(v11);
      goto LABEL_24;
    }
    v12 = (unsigned __int64)(522 - v24) >> 1;
    v13 = &SubKey[(unsigned __int64)v24 >> 1];
    *(v13 - 1) = 92;
    if ( v12 )
    {
      v14 = 2147483646;
      v15 = (WCHAR *)a1;
      do
      {
        if ( !v14 )
          break;
        if ( !*v15 )
          break;
        *v13++ = *v15++;
        --v14;
        --v12;
      }
      while ( v12 );
      v16 = v13 - 1;
      if ( v12 )
        v16 = v13;
      *v16 = 0;
      v17 = v12 == 0 ? 0x8007007A : 0;
      if ( v12 )
      {
        if ( (BYTE3(xmmword_1801119E0) & 0x20) == 0 )
        {
LABEL_14:
          if ( (v17 & 0x80000000) == 0 )
          {
LABEL_15:
            v18 = SubKey;
            goto LABEL_16;
          }
          v21 = v17;
LABEL_22:
          v19 = WX_WIN32_FROM_HR(v21);
          goto LABEL_18;
        }
        WPP_SF_SSSS(
          (_DWORD)v16,
          v12,
          (_DWORD)v13,
          (unsigned int)L"DnscacheTcpipInterfaces",
          (__int64)L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces",
          a1,
          (__int64)SubKey);
LABEL_24:
        if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
          WPP_SF_d(1053, 14, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids, v17);
        goto LABEL_14;
      }
    }
    else
    {
      v17 = -2147024809;
    }
    if ( (BYTE3(xmmword_1801119E0) & 0x20) == 0 )
      goto LABEL_14;
    WPP_SF_d(1053, 12, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids, v17);
    goto LABEL_24;
  }
  if ( a1 != 1 )
  {
    if ( a1 != 2 )
    {
      v23 = L"Software\\Policies\\Microsoft\\Windows NT\\DnsClient";
      if ( a1 != 3 )
        v23 = L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters";
      v18 = (WCHAR *)v23;
      goto LABEL_16;
    }
    PersistedRegistryLocation = WxGetPersistedRegistryLocation(
                                  (unsigned int)L"Dnscache",
                                  (unsigned int)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
                                  (unsigned int)L"Parameters",
                                  (unsigned int)SubKey,
                                  522);
    if ( PersistedRegistryLocation >= 0 )
      goto LABEL_15;
    v21 = (unsigned int)PersistedRegistryLocation;
    goto LABEL_22;
  }
  v18 = (WCHAR *)L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters";
LABEL_16:
  if ( a2 )
    v19 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v18, 0, (LPWSTR)L"Class", 0, 0x20006u, 0, &phkResult, dwDisposition);
  else
    v19 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v18, 0, 1u, &phkResult);
LABEL_18:
  if ( v19 )
    SetLastError(v19);
  return phkResult;
}

```

## disassembly

```asm
0x18003f31c  push    rbp
0x18003f31e  push    rbx
0x18003f31f  push    rsi
0x18003f320  push    rdi
0x18003f321  push    r14
0x18003f323  push    r15
0x18003f325  lea     rbp, [rsp-198h]
0x18003f32d  sub     rsp, 298h
0x18003f334  mov     rax, cs:__security_cookie
0x18003f33b  xor     rax, rsp
0x18003f33e  mov     [rbp+1C0h+var_40], rax
0x18003f345  mov     r14d, edx
0x18003f348  mov     rdi, rcx
0x18003f34b  xor     r15d, r15d
0x18003f34e  lea     rcx, [rsp+2C0h+SubKey]; void *
0x18003f353  mov     ebx, 20Ah
0x18003f358  mov     [rsp+2C0h+var_268], r15
0x18003f35d  mov     r8d, ebx; Size
0x18003f360  mov     [rsp+2C0h+dwDisposition], r15d
0x18003f365  xor     edx, edx; Val
0x18003f367  call    memset_0
0x18003f36c  cmp     rdi, 3
0x18003f370  jbe     loc_18003F5E0
0x18003f376  mov     [rsp+2C0h+var_270], r15d
0x18003f37b  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x18003f382  lea     rsi, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Tc"...
0x18003f389  jnz     loc_18003F516
0x18003f38f  lea     rax, [rsp+2C0h+var_270]
0x18003f394  xor     r9d, r9d
0x18003f397  mov     [rsp+2C0h+lpSecurityAttributes], rax
0x18003f39c  lea     rcx, aDnscachetcpipi; "DnscacheTcpipInterfaces"
0x18003f3a3  lea     rax, [rsp+2C0h+SubKey]
0x18003f3a8  mov     [rsp+2C0h+samDesired], ebx
0x18003f3ac  mov     r8, rsi
0x18003f3af  mov     [rsp+2C0h+phkResult], rax
0x18003f3b4  xor     edx, edx
0x18003f3b6  call    cs:__imp_RtlGetPersistedStateLocation
0x18003f3bd  nop     dword ptr [rax+rax+00h]
0x18003f3c2  mov     esi, eax
0x18003f3c4  test    eax, eax
0x18003f3c6  js      loc_18003F57D
0x18003f3cc  sub     ebx, [rsp+2C0h+var_270]
0x18003f3d0  lea     r8, [rsp+2C0h+SubKey]
0x18003f3d5  mov     eax, [rsp+2C0h+var_270]
0x18003f3d9  shr     rax, 1
0x18003f3dc  mov     edx, ebx
0x18003f3de  shr     rdx, 1
0x18003f3e1  lea     r8, [r8+rax*2]
0x18003f3e5  mov     word ptr [r8-2], 5Ch ; '\'
0x18003f3ec  jz      loc_18003F648
0x18003f3f2  mov     eax, 7FFFFFFEh
0x18003f3f7  mov     rcx, rdi
0x18003f3fa  test    rax, rax
0x18003f3fd  jz      short loc_18003F41E
0x18003f3ff  movzx   r9d, word ptr [rcx]
0x18003f403  test    r9w, r9w
0x18003f407  jz      short loc_18003F41E
0x18003f409  mov     [r8], r9w
0x18003f40d  add     rcx, 2
0x18003f411  add     r8, 2
0x18003f415  dec     rax
0x18003f418  sub     rdx, 1
0x18003f41c  jnz     short loc_18003F3FA
0x18003f41e  mov     rax, rdx
0x18003f421  lea     rcx, [r8-2]
0x18003f425  neg     rax
0x18003f428  sbb     ebx, ebx
0x18003f42a  test    rdx, rdx
0x18003f42d  not     ebx
0x18003f42f  cmovnz  rcx, r8
0x18003f433  mov     [rcx], r15w
0x18003f437  and     ebx, 8007007Ah
0x18003f43d  js      loc_18003F5B5
0x18003f443  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x18003f44a  jnz     short loc_18003F4C4
0x18003f44c  test    ebx, ebx
0x18003f44e  js      short loc_18003F4AB
0x18003f450  lea     rdx, [rsp+2C0h+SubKey]; lpSubKey
0x18003f455  xor     r8d, r8d; Reserved
0x18003f458  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003f45f  test    r14d, r14d
0x18003f462  jnz     loc_18003F53F
0x18003f468  lea     rax, [rsp+2C0h+var_268]
0x18003f46d  lea     r9d, [r8+1]; samDesired
0x18003f471  mov     [rsp+2C0h+phkResult], rax; phkResult
0x18003f476  call    cs:__imp_RegOpenKeyExW
0x18003f47d  nop     dword ptr [rax+rax+00h]
0x18003f482  test    eax, eax
0x18003f484  jnz     short loc_18003F4B4
0x18003f486  mov     rax, [rsp+2C0h+var_268]
0x18003f48b  mov     rcx, [rbp+1C0h+var_40]
0x18003f492  xor     rcx, rsp; StackCookie
0x18003f495  call    __security_check_cookie
0x18003f49a  add     rsp, 298h
0x18003f4a1  pop     r15
0x18003f4a3  pop     r14
0x18003f4a5  pop     rdi
0x18003f4a6  pop     rsi
0x18003f4a7  pop     rbx
0x18003f4a8  pop     rbp
0x18003f4a9  retn
0x18003f4ab  mov     ecx, ebx
0x18003f4ad  call    WX_WIN32_FROM_HR
0x18003f4b2  jmp     short loc_18003F482
0x18003f4b4  mov     ecx, eax; dwErrCode
0x18003f4b6  call    cs:__imp_SetLastError
0x18003f4bd  nop     dword ptr [rax+rax+00h]
0x18003f4c2  jmp     short loc_18003F486
0x18003f4c4  lea     rax, [rsp+2C0h+SubKey]
0x18003f4c9  mov     [rsp+2C0h+lpSecurityAttributes], rax
0x18003f4ce  lea     r9, aDnscachetcpipi; "DnscacheTcpipInterfaces"
0x18003f4d5  lea     rax, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Tc"...
0x18003f4dc  mov     qword ptr [rsp+2C0h+samDesired], rdi
0x18003f4e1  mov     [rsp+2C0h+phkResult], rax
0x18003f4e6  call    WPP_SF_SSSS
0x18003f4eb  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x18003f4f2  jz      loc_18003F44C
0x18003f4f8  mov     edx, 0Eh
0x18003f4fd  lea     r8, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids
0x18003f504  mov     ecx, 41Dh
0x18003f509  mov     r9d, ebx
0x18003f50c  call    WPP_SF_d
0x18003f511  jmp     loc_18003F44C
0x18003f516  mov     dword ptr [rsp+2C0h+var_288], ebx
0x18003f51a  lea     rax, [rsp+2C0h+SubKey]
0x18003f51f  mov     [rsp+2C0h+lpSecurityAttributes], rax
0x18003f524  lea     r9, aDnscachetcpipi; "DnscacheTcpipInterfaces"
0x18003f52b  mov     qword ptr [rsp+2C0h+samDesired], rdi
0x18003f530  mov     [rsp+2C0h+phkResult], rsi
0x18003f535  call    WPP_SF_SSSqd
0x18003f53a  jmp     loc_18003F38F
0x18003f53f  lea     rax, [rsp+2C0h+dwDisposition]
0x18003f544  mov     [rsp+2C0h+lpdwDisposition], rax; lpdwDisposition
0x18003f549  lea     r9, Class; "Class"
0x18003f550  lea     rax, [rsp+2C0h+var_268]
0x18003f555  mov     [rsp+2C0h+var_288], rax; phkResult
0x18003f55a  mov     [rsp+2C0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18003f55f  mov     [rsp+2C0h+samDesired], 20006h; samDesired
0x18003f567  mov     dword ptr [rsp+2C0h+phkResult], r15d; dwOptions
0x18003f56c  call    cs:__imp_RegCreateKeyExW
0x18003f573  nop     dword ptr [rax+rax+00h]
0x18003f578  jmp     loc_18003F482
0x18003f57d  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x18003f584  jz      short loc_18003F5A7
0x18003f586  mov     dword ptr [rsp+2C0h+lpSecurityAttributes], esi
0x18003f58a  lea     rax, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Tc"...
0x18003f591  mov     qword ptr [rsp+2C0h+samDesired], rdi
0x18003f596  lea     r9, aDnscachetcpipi; "DnscacheTcpipInterfaces"
0x18003f59d  mov     [rsp+2C0h+phkResult], rax
0x18003f5a2  call    WPP_SF_SSSd
0x18003f5a7  mov     ecx, esi; int
0x18003f5a9  call    ?HRESULT_FROM_NTSTATUS@@YAJJ@Z; HRESULT_FROM_NTSTATUS(long)
0x18003f5ae  mov     ebx, eax
0x18003f5b0  jmp     loc_18003F4EB
0x18003f5b5  mov     r9d, ebx
0x18003f5b8  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x18003f5bf  jz      loc_18003F44C
0x18003f5c5  mov     edx, 0Ch
0x18003f5ca  lea     r8, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids
0x18003f5d1  mov     ecx, 41Dh
0x18003f5d6  call    WPP_SF_d
0x18003f5db  jmp     loc_18003F4EB
0x18003f5e0  cmp     rdi, 1
0x18003f5e4  jnz     short loc_18003F5F2
0x18003f5e6  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Tc"...
0x18003f5ed  jmp     loc_18003F455
0x18003f5f2  cmp     rdi, 2
0x18003f5f6  jnz     short loc_18003F62A
0x18003f5f8  lea     r9, [rsp+2C0h+SubKey]
0x18003f5fd  mov     dword ptr [rsp+2C0h+phkResult], ebx
0x18003f601  lea     r8, aParameters; "Parameters"
0x18003f608  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18003f60f  lea     rcx, aDnscache_1; "Dnscache"
0x18003f616  call    WxGetPersistedRegistryLocation
0x18003f61b  test    eax, eax
0x18003f61d  jns     loc_18003F450
0x18003f623  mov     ecx, eax
0x18003f625  jmp     loc_18003F4AD
0x18003f62a  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Tc"...
0x18003f631  cmp     rdi, 3
0x18003f635  lea     rax, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows "...
0x18003f63c  cmovnz  rax, rdx
0x18003f640  mov     rdx, rax
0x18003f643  jmp     loc_18003F455
0x18003f648  mov     ebx, 80070057h
0x18003f64d  jmp     loc_18003F5B5
```
