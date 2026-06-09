# Reg_OpenSession

- ea: `0x180062660`
- end: `0x180062823`
- name: `Reg_OpenSession`
- size: `451`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800623a4`

## callees

- `0x18002025c`
- `0x180046ec0`
- `0x180062350`
- `0x180062660`
- `0x180086384`
- `0x180086ab0`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800627a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800627a7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800626da`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800626da`

## string_xrefs

- `0x180062767`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x180062777`: `Dnscache`
- `0x1800626a9`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x1800626f1`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18006272f`: `System\CurrentControlSet\Services\Tcpip\Parameters`

## pseudocode

```c
__int64 __fastcall Reg_OpenSession(PHKEY phkResult)
{
  unsigned int v2; // ebx
  int v3; // r9d
  char v4; // al
  LSTATUS v5; // eax
  HKEY v7; // [rsp+50h] [rbp-28h] BYREF
  DWORD v8; // [rsp+58h] [rbp-20h] BYREF

  v7 = 0;
  v8 = 0;
  *(_OWORD *)phkResult = 0;
  phkResult[2] = 0;
  v2 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters",
         0,
         (LPWSTR)L"Class",
         0,
         0x20019u,
         0,
         &v7,
         &v8);
  v4 = BYTE1(xmmword_1800AB5A0);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    WPP_SF_Sd(
      1035,
      10,
      (unsigned int)WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids,
      (unsigned int)L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters",
      v8);
    v4 = BYTE1(xmmword_1800AB5A0);
  }
  if ( v2 )
  {
    if ( (v4 & 8) != 0 )
      WPP_SF_SD(
        1035,
        11,
        (unsigned int)WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids,
        (unsigned int)L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters",
        v2);
    Reg_CloseSession(phkResult);
  }
  else
  {
    CreatePersistedRegistryKeyHelper(
      (unsigned int)L"Dnscache",
      (unsigned int)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
      (unsigned int)L"Parameters",
      v3,
      131097,
      0,
      0,
      (__int64)(phkResult + 2));
    v5 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Policies\\Microsoft\\Windows NT\\DnsClient",
           0,
           0x20019u,
           phkResult);
    if ( v5 && (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_SD(
        1035,
        12,
        (unsigned int)WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids,
        (unsigned int)L"Software\\Policies\\Microsoft\\Windows NT\\DnsClient",
        v5);
    phkResult[1] = v7;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 13, WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x180062660  mov     r11, rsp
0x180062663  mov     [r11+10h], rbx
0x180062667  push    rdi
0x180062668  sub     rsp, 70h
0x18006266c  mov     rax, cs:__security_cookie
0x180062673  xor     rax, rsp
0x180062676  mov     [rsp+78h+var_18], rax
0x18006267b  xor     eax, eax
0x18006267d  mov     qword ptr [r11-28h], 0
0x180062685  xorps   xmm0, xmm0
0x180062688  mov     [rsp+78h+var_20], 0
0x180062690  movups  xmmword ptr [rcx], xmm0
0x180062693  mov     [rcx+10h], rax
0x180062697  lea     r9, aClass; "Class"
0x18006269e  lea     rax, [r11-20h]
0x1800626a2  mov     rdi, rcx
0x1800626a5  mov     [r11-38h], rax
0x1800626a9  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\Tc"...
0x1800626b0  lea     rax, [r11-28h]
0x1800626b4  xor     r8d, r8d; Reserved
0x1800626b7  mov     [r11-40h], rax
0x1800626bb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800626c2  mov     qword ptr [r11-48h], 0
0x1800626ca  mov     [rsp+78h+samDesired], 20019h; samDesired
0x1800626d2  mov     [rsp+78h+dwOptions], 0; dwOptions
0x1800626da  call    cs:__imp_RegCreateKeyExW
0x1800626e0  mov     ebx, eax
0x1800626e2  mov     al, byte ptr cs:xmmword_1800AB5A0+1
0x1800626e8  test    al, 8
0x1800626ea  jz      short loc_180062719
0x1800626ec  mov     r8d, [rsp+78h+var_20]
0x1800626f1  lea     r9, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\Tc"...
0x1800626f8  mov     [rsp+78h+dwOptions], r8d
0x1800626fd  mov     edx, 0Ah
0x180062702  lea     r8, WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids
0x180062709  mov     ecx, 40Bh
0x18006270e  call    WPP_SF_Sd
0x180062713  mov     al, byte ptr cs:xmmword_1800AB5A0+1
0x180062719  test    ebx, ebx
0x18006271b  jz      short loc_18006274F
0x18006271d  test    al, 8
0x18006271f  jz      short loc_180062742
0x180062721  mov     edx, 0Bh
0x180062726  mov     [rsp+78h+dwOptions], ebx
0x18006272a  mov     ecx, 40Bh
0x18006272f  lea     r9, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\Tc"...
0x180062736  lea     r8, WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids
0x18006273d  call    WPP_SF_SD
0x180062742  mov     rcx, rdi
0x180062745  call    Reg_CloseSession
0x18006274a  jmp     loc_1800627E4
0x18006274f  lea     rax, [rdi+10h]
0x180062753  mov     [rsp+78h+var_40], rax
0x180062758  lea     r8, aParameters; "Parameters"
0x18006275f  mov     [rsp+78h+var_48], 0
0x180062767  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18006276e  mov     qword ptr [rsp+78h+samDesired], 0
0x180062777  lea     rcx, aDnscache_0; "Dnscache"
0x18006277e  mov     [rsp+78h+dwOptions], 20019h
0x180062786  call    CreatePersistedRegistryKeyHelper
0x18006278b  mov     r9d, 20019h; samDesired
0x180062791  mov     qword ptr [rsp+78h+dwOptions], rdi; phkResult
0x180062796  xor     r8d, r8d; ulOptions
0x180062799  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x1800627a0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800627a7  call    cs:__imp_RegOpenKeyExW
0x1800627ad  test    eax, eax
0x1800627af  jz      short loc_1800627DB
0x1800627b1  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800627b8  jz      short loc_1800627DB
0x1800627ba  mov     edx, 0Ch
0x1800627bf  mov     [rsp+78h+dwOptions], eax
0x1800627c3  mov     ecx, 40Bh
0x1800627c8  lea     r9, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x1800627cf  lea     r8, WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids
0x1800627d6  call    WPP_SF_SD
0x1800627db  mov     rax, [rsp+78h+var_28]
0x1800627e0  mov     [rdi+8], rax
0x1800627e4  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800627eb  jz      short loc_180062806
0x1800627ed  mov     edx, 0Dh
0x1800627f2  lea     r8, WPP_e863ea8ca75532f1bb84a1ddbc806e72_Traceguids
0x1800627f9  mov     ecx, 40Bh
0x1800627fe  mov     r9d, ebx
0x180062801  call    WPP_SF_d
0x180062806  mov     eax, ebx
0x180062808  mov     rcx, [rsp+78h+var_18]
0x18006280d  xor     rcx, rsp; StackCookie
0x180062810  call    __security_check_cookie
0x180062815  mov     rbx, [rsp+78h+arg_8]
0x18006281d  add     rsp, 70h
0x180062821  pop     rdi
0x180062822  retn
```
