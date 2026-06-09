# Reg_OpenSession

- ea: `0x180007cfc`
- end: `0x180007ecb`
- name: `Reg_OpenSession`
- size: `463`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `9`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800065c0`
- `0x180006d40`
- `0x18000702c`
- `0x1800072a0`
- `0x180008010`
- `0x1800082e4`
- `0x18007e1f0`
- `0x18009af10`
- `0x18009ecd0`

## callees

- `0x18000723c`
- `0x180007cfc`
- `0x180008830`
- `0x1800097e0`
- `0x18008b5f0`
- `0x1800dbadc`
- `0x1800dbb48`
- `0x1800dc9e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007d88`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007d88`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007e4d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007e4d`

## string_xrefs

- `0x180007d43`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x180007da5`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x180007dde`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x180007e1d`: `Dnscache`
- `0x180007e16`: `SYSTEM\CurrentControlSet\Services\Dnscache`

## pseudocode

```c
__int64 __fastcall Reg_OpenSession(PHKEY phkResult)
{
  int v2; // ecx
  unsigned int v3; // edi
  int v4; // r9d
  char v5; // al
  LSTATUS v6; // eax
  int v7; // ecx
  HKEY v9; // [rsp+50h] [rbp-28h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-20h] BYREF

  v9 = 0;
  dwDisposition = 0;
  if ( !g_fVelocityDisableInternalExports )
    Reg_Init();
  *(_OWORD *)phkResult = 0;
  phkResult[2] = 0;
  v3 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters",
         0,
         (LPWSTR)L"Class",
         0,
         0x20019u,
         0,
         &v9,
         &dwDisposition);
  v5 = BYTE1(xmmword_1801119E0);
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
  {
    WPP_SF_Sd(
      1035,
      10,
      (unsigned int)WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids,
      (unsigned int)L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters",
      dwDisposition);
    v5 = BYTE1(xmmword_1801119E0);
  }
  if ( v3 )
  {
    if ( (v5 & 8) != 0 )
      WPP_SF_SD(
        v2,
        11,
        (unsigned int)WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids,
        (unsigned int)L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters",
        v3);
    Reg_CloseSession(phkResult);
  }
  else
  {
    CreatePersistedRegistryKeyHelper(
      (unsigned int)L"Dnscache",
      (unsigned int)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
      (unsigned int)L"Parameters",
      v4,
      131097);
    v6 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Policies\\Microsoft\\Windows NT\\DnsClient",
           0,
           0x20019u,
           phkResult);
    if ( v6 && (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_SD(
        v7,
        12,
        (unsigned int)WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids,
        (unsigned int)L"Software\\Policies\\Microsoft\\Windows NT\\DnsClient",
        v6);
    phkResult[1] = v9;
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 13, WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180007cfc  mov     [rsp+arg_8], rbx
0x180007d01  push    rdi
0x180007d02  sub     rsp, 70h
0x180007d06  mov     rax, cs:__security_cookie
0x180007d0d  xor     rax, rsp
0x180007d10  mov     [rsp+78h+var_18], rax
0x180007d15  cmp     cs:g_fVelocityDisableInternalExports, 0
0x180007d1c  mov     rbx, rcx
0x180007d1f  mov     [rsp+78h+var_28], 0
0x180007d28  mov     [rsp+78h+dwDisposition], 0
0x180007d30  jnz     short loc_180007D37
0x180007d32  call    Reg_Init
0x180007d37  xor     eax, eax
0x180007d39  lea     r9, Class; "Class"
0x180007d40  xorps   xmm0, xmm0
0x180007d43  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Tc"...
0x180007d4a  movups  xmmword ptr [rbx], xmm0
0x180007d4d  mov     [rbx+10h], rax
0x180007d51  xor     r8d, r8d; Reserved
0x180007d54  lea     rax, [rsp+78h+dwDisposition]
0x180007d59  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007d60  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x180007d65  lea     rax, [rsp+78h+var_28]
0x180007d6a  mov     [rsp+78h+phkResult], rax; phkResult
0x180007d6f  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180007d78  mov     [rsp+78h+samDesired], 20019h; samDesired
0x180007d80  mov     [rsp+78h+dwOptions], 0; dwOptions
0x180007d88  call    cs:__imp_RegCreateKeyExW
0x180007d8f  nop     dword ptr [rax+rax+00h]
0x180007d94  mov     edi, eax
0x180007d96  mov     al, byte ptr cs:xmmword_1801119E0+1
0x180007d9c  test    al, 8
0x180007d9e  jz      short loc_180007DCD
0x180007da0  mov     r8d, [rsp+78h+dwDisposition]
0x180007da5  lea     r9, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Tc"...
0x180007dac  mov     [rsp+78h+dwOptions], r8d
0x180007db1  mov     edx, 0Ah
0x180007db6  lea     r8, WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids
0x180007dbd  mov     ecx, 40Bh
0x180007dc2  call    WPP_SF_Sd
0x180007dc7  mov     al, byte ptr cs:xmmword_1801119E0+1
0x180007dcd  test    edi, edi
0x180007dcf  jz      short loc_180007DFE
0x180007dd1  test    al, 8
0x180007dd3  jz      short loc_180007DF1
0x180007dd5  mov     edx, 0Bh
0x180007dda  mov     [rsp+78h+dwOptions], edi
0x180007dde  lea     r9, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Tc"...
0x180007de5  lea     r8, WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids
0x180007dec  call    WPP_SF_SD
0x180007df1  mov     rcx, rbx
0x180007df4  call    Reg_CloseSession
0x180007df9  jmp     loc_180007E8B
0x180007dfe  lea     rax, [rbx+10h]
0x180007e02  mov     [rsp+78h+phkResult], rax
0x180007e07  lea     r8, aParameters; "Parameters"
0x180007e0e  mov     dword ptr [rsp+78h+lpSecurityAttributes], 0
0x180007e16  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x180007e1d  lea     rcx, aDnscache_1; "Dnscache"
0x180007e24  mov     [rsp+78h+dwOptions], 20019h
0x180007e2c  call    CreatePersistedRegistryKeyHelper
0x180007e31  mov     r9d, 20019h; samDesired
0x180007e37  mov     qword ptr [rsp+78h+dwOptions], rbx; phkResult
0x180007e3c  xor     r8d, r8d; ulOptions
0x180007e3f  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows "...
0x180007e46  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007e4d  call    cs:__imp_RegOpenKeyExW
0x180007e54  nop     dword ptr [rax+rax+00h]
0x180007e59  test    eax, eax
0x180007e5b  jz      short loc_180007E82
0x180007e5d  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180007e64  jz      short loc_180007E82
0x180007e66  mov     edx, 0Ch
0x180007e6b  mov     [rsp+78h+dwOptions], eax
0x180007e6f  lea     r9, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows "...
0x180007e76  lea     r8, WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids
0x180007e7d  call    WPP_SF_SD
0x180007e82  mov     rax, [rsp+78h+var_28]
0x180007e87  mov     [rbx+8], rax
0x180007e8b  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180007e92  jz      short loc_180007EAD
0x180007e94  mov     edx, 0Dh
0x180007e99  lea     r8, WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids
0x180007ea0  mov     ecx, 40Bh
0x180007ea5  mov     r9d, edi
0x180007ea8  call    WPP_SF_d
0x180007ead  mov     eax, edi
0x180007eaf  mov     rcx, [rsp+78h+var_18]
0x180007eb4  xor     rcx, rsp; StackCookie
0x180007eb7  call    __security_check_cookie
0x180007ebc  mov     rbx, [rsp+78h+arg_8]
0x180007ec4  add     rsp, 70h
0x180007ec8  pop     rdi
0x180007ec9  retn
```
