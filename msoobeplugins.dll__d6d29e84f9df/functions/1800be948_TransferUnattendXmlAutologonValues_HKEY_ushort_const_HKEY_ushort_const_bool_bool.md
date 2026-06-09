# TransferUnattendXmlAutologonValues(HKEY__ *,ushort const *,HKEY__ *,ushort const *,bool,bool)

- ea: `0x1800be948`
- end: `0x1800bed60`
- name: `?TransferUnattendXmlAutologonValues@@YAJPEAUHKEY__@@PEBG01_N2@Z`
- size: `1048`
- prototype: `int(HKEY, const unsigned __int16 *, HKEY, const unsigned __int16 *, bool, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180053060`

## callees

- `0x180003470`
- `0x180019080`
- `0x180019140`
- `0x18001de58`
- `0x1800230b0`
- `0x180046c9c`
- `0x1800b8834`
- `0x1800be948`
- `0x1800bee24`

## import_xrefs

- `SHLWAPI!SHDeleteValueW` at `0x1800be9e1`
- `SHLWAPI!SHDeleteValueW` at `0x1800bea81`
- `SHLWAPI!SHDeleteValueW` at `0x1800bea97`
- `SHLWAPI!SHDeleteValueW` at `0x1800beb2f`
- `SHLWAPI!SHDeleteValueW` at `0x1800beb45`
- `SHLWAPI!SHDeleteValueW` at `0x1800bebdd`
- `SHLWAPI!SHDeleteValueW` at `0x1800bebf3`
- `SHLWAPI!SHDeleteValueW` at `0x1800bec4f`
- `SHLWAPI!SHDeleteValueW` at `0x1800bec65`
- `SHLWAPI!SHDeleteValueW` at `0x1800becf7`
- `SHLWAPI!SHDeleteValueW` at `0x1800be9e1`
- `SHLWAPI!SHDeleteValueW` at `0x1800bea81`
- `SHLWAPI!SHDeleteValueW` at `0x1800bea97`
- `SHLWAPI!SHDeleteValueW` at `0x1800beb2f`
- `SHLWAPI!SHDeleteValueW` at `0x1800beb45`
- `SHLWAPI!SHDeleteValueW` at `0x1800bebdd`
- `SHLWAPI!SHDeleteValueW` at `0x1800bebf3`
- `SHLWAPI!SHDeleteValueW` at `0x1800bec4f`
- `SHLWAPI!SHDeleteValueW` at `0x1800bec65`
- `SHLWAPI!SHDeleteValueW` at `0x1800becf7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bea22`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bead3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800beb81`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bec9f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bea22`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bead3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800beb81`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bec9f`

## string_xrefs

- `0x1800bea3f`: `shell\oobe\common\lib\autologon.cpp`
- `0x1800becfd`: `CachedDefaultPassword`
- `0x1800bea87`: `DefaultSID`
- `0x1800be9c3`: `Transferring unattend.xml autologon values`

## pseudocode

```c
__int64 __fastcall TransferUnattendXmlAutologonValues(
        HKEY a1,
        const unsigned __int16 *a2,
        HKEY a3,
        const unsigned __int16 *a4)
{
  int ValueW; // eax
  int v7; // eax
  LSTATUS v8; // eax
  bool v9; // sf
  int v10; // eax
  LSTATUS v11; // eax
  bool v12; // sf
  int v13; // eax
  int v14; // eax
  LSTATUS v15; // eax
  bool v16; // sf
  int v17; // eax
  int v18; // eax
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  int pdwTypeb; // [rsp+20h] [rbp-E0h]
  int pdwTypec; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v25; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int16 v26; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 pvData[264]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v28[264]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v29[264]; // [rsp+470h] [rbp+370h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6B8h] [rbp+5B8h]

  pcbData = 0;
  if ( (int)SHRegGetBOOLWithREGSAM(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE",
              L"UnattendSetAutologon",
              (unsigned int)a4,
              (int *)&pcbData) < 0
    || !pcbData )
  {
    return 2147549183LL;
  }
  UnattendLogW(0, L"Transferring unattend.xml autologon values");
  SHDeleteValueW(a3, a4, L"DefaultUserName");
  pcbData = 514;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
             L"DefaultUserName",
             2u,
             0,
             pvData,
             &pcbData);
  if ( ValueW )
  {
    pvData[0] = 0;
    if ( ValueW > 0 )
      ValueW = (unsigned __int16)ValueW | 0x80070000;
  }
  if ( ValueW >= 0 )
  {
    v7 = SHRegSetString(a3, a4, L"DefaultUserName", pvData);
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC1,
        (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
        (const char *)(unsigned int)v7,
        pdwType);
  }
  SHDeleteValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", L"DefaultUserName");
  SHDeleteValueW(a3, a4, L"DefaultSID");
  pcbData = 514;
  v8 = RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
         L"DefaultSID",
         2u,
         0,
         v28,
         &pcbData);
  v9 = v8 < 0;
  if ( v8 )
  {
    v28[0] = 0;
    v9 = v8 < 0;
    if ( v8 > 0 )
      v9 = 1;
  }
  if ( !v9 )
  {
    v10 = SHRegSetString(a3, a4, L"DefaultSID", v28);
    if ( v10 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC9,
        (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
        (const char *)(unsigned int)v10,
        pdwTypea);
  }
  SHDeleteValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", L"DefaultSID");
  SHDeleteValueW(a3, a4, L"DefaultDomainName");
  pcbData = 514;
  v11 = RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
          L"DefaultDomainName",
          2u,
          0,
          v29,
          &pcbData);
  v12 = v11 < 0;
  if ( v11 )
  {
    v29[0] = 0;
    v12 = v11 < 0;
    if ( v11 > 0 )
      v12 = 1;
  }
  if ( !v12 )
  {
    v13 = SHRegSetString(a3, a4, L"DefaultDomainName", v29);
    if ( v13 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xD1,
        (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
        (const char *)(unsigned int)v13,
        pdwTypeb);
  }
  SHDeleteValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", L"DefaultDomainName");
  SHDeleteValueW(a3, a4, L"AutoLogonCount");
  v25 = 0;
  if ( (int)SHRegGetDWORD(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
              L"AutoLogonCount",
              &v25) >= 0 )
  {
    v14 = SHRegSetDWORD(a3, a4, L"AutoLogonCount", v25);
    if ( v14 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xD9,
        (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
        (const char *)(unsigned int)v14,
        pdwTypeb);
  }
  SHDeleteValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", L"AutoLogonCount");
  SHDeleteValueW(a3, a4, L"AutoAdminLogon");
  pcbData = 4;
  v15 = RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
          L"AutoAdminLogon",
          2u,
          0,
          &v26,
          &pcbData);
  v16 = v15 < 0;
  if ( v15 )
  {
    v26 = 0;
    v16 = v15 < 0;
    if ( v15 > 0 )
      v16 = 1;
  }
  if ( !v16 )
  {
    v17 = SHRegSetString(a3, a4, L"AutoAdminLogon", &v26);
    if ( v17 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE1,
        (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
        (const char *)(unsigned int)v17,
        pdwTypec);
  }
  SHDeleteValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", L"AutoAdminLogon");
  v18 = _MoveLsaSecret(L"DefaultPassword", L"CachedDefaultPassword");
  if ( v18 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xF6,
      (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
      (const char *)(unsigned int)v18,
      pdwTypec);
  return 0;
}

```

## disassembly

```asm
0x1800be948  mov     [rsp-8+arg_0], rbx
0x1800be94d  mov     [rsp-8+arg_8], rdi
0x1800be952  push    rbp
0x1800be953  push    r12
0x1800be955  push    r13
0x1800be957  push    r14
0x1800be959  push    r15
0x1800be95b  lea     rbp, [rsp-590h]
0x1800be963  sub     rsp, 690h
0x1800be96a  mov     rax, cs:__security_cookie
0x1800be971  xor     rax, rsp
0x1800be974  mov     [rbp+5B0h+var_30], rax
0x1800be97b  mov     rbx, r8
0x1800be97e  mov     [rsp+6B0h+var_670], 0
0x1800be986  lea     rax, [rsp+6B0h+var_670]
0x1800be98b  mov     r15, 0FFFFFFFF80000002h
0x1800be992  mov     rcx, r15; HKEY
0x1800be995  mov     [rsp+6B0h+pdwType], rax; int *
0x1800be99a  lea     r8, aUnattendsetaut; "UnattendSetAutologon"
0x1800be9a1  mov     rdi, r9
0x1800be9a4  lea     rdx, aSoftwareMicros_19; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800be9ab  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1800be9b0  test    eax, eax
0x1800be9b2  js      loc_1800BED2F
0x1800be9b8  cmp     [rsp+6B0h+var_670], 0
0x1800be9bd  jz      loc_1800BED2F
0x1800be9c3  lea     rdx, aTransferringUn; "Transferring unattend.xml autologon val"...
0x1800be9ca  xor     ecx, ecx
0x1800be9cc  call    UnattendLogW
0x1800be9d1  lea     r12, aDefaultusernam; "DefaultUserName"
0x1800be9d8  mov     rdx, rdi; pszSubKey
0x1800be9db  mov     r8, r12; pszValue
0x1800be9de  mov     rcx, rbx; hkey
0x1800be9e1  call    cs:__imp_SHDeleteValueW
0x1800be9e7  lea     rax, [rsp+6B0h+var_670]
0x1800be9ec  mov     [rsp+6B0h+var_670], 202h
0x1800be9f4  mov     [rsp+6B0h+pcbData], rax; pcbData
0x1800be9f9  lea     r13, aSoftwareMicros_16; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800bea00  lea     rax, [rsp+6B0h+var_660]
0x1800bea05  mov     r9d, 2; dwFlags
0x1800bea0b  mov     [rsp+6B0h+pvData], rax; pvData
0x1800bea10  mov     r8, r12; lpValue
0x1800bea13  mov     rdx, r13; lpSubKey
0x1800bea16  mov     [rsp+6B0h+pdwType], 0; int
0x1800bea1f  mov     rcx, r15; hkey
0x1800bea22  call    cs:__imp_RegGetValueW
0x1800bea28  test    eax, eax
0x1800bea2a  jz      short loc_1800BEA3F
0x1800bea2c  xor     ecx, ecx
0x1800bea2e  mov     [rsp+6B0h+var_660], cx
0x1800bea33  test    eax, eax
0x1800bea35  jle     short loc_1800BEA3F
0x1800bea37  movzx   eax, ax
0x1800bea3a  or      eax, 80070000h
0x1800bea3f  lea     r14, aShellOobeCommo; "shell\\oobe\\common\\lib\\autologon.cpp"
0x1800bea46  test    eax, eax
0x1800bea48  js      short loc_1800BEA78
0x1800bea4a  lea     r9, [rsp+6B0h+var_660]; unsigned __int16 *
0x1800bea4f  mov     r8, r12; unsigned __int16 *
0x1800bea52  mov     rdx, rdi; unsigned __int16 *
0x1800bea55  mov     rcx, rbx; HKEY
0x1800bea58  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800bea5d  test    eax, eax
0x1800bea5f  jns     short loc_1800BEA78
0x1800bea61  mov     rcx, [rbp+5B8h]; this
0x1800bea68  mov     r9d, eax; char *
0x1800bea6b  mov     r8, r14; unsigned int
0x1800bea6e  mov     edx, 0C1h; void *
0x1800bea73  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bea78  mov     r8, r12; pszValue
0x1800bea7b  mov     rdx, r13; pszSubKey
0x1800bea7e  mov     rcx, r15; hkey
0x1800bea81  call    cs:__imp_SHDeleteValueW
0x1800bea87  lea     r12, aDefaultsid; "DefaultSID"
0x1800bea8e  mov     rdx, rdi; pszSubKey
0x1800bea91  mov     r8, r12; pszValue
0x1800bea94  mov     rcx, rbx; hkey
0x1800bea97  call    cs:__imp_SHDeleteValueW
0x1800bea9d  lea     rax, [rsp+6B0h+var_670]
0x1800beaa2  mov     [rsp+6B0h+var_670], 202h
0x1800beaaa  mov     [rsp+6B0h+pcbData], rax; pcbData
0x1800beaaf  mov     r9d, 2; dwFlags
0x1800beab5  lea     rax, [rbp+5B0h+var_450]
0x1800beabc  mov     r8, r12; lpValue
0x1800beabf  mov     [rsp+6B0h+pvData], rax; pvData
0x1800beac4  mov     rdx, r13; lpSubKey
0x1800beac7  mov     rcx, r15; hkey
0x1800beaca  mov     [rsp+6B0h+pdwType], 0; int
0x1800bead3  call    cs:__imp_RegGetValueW
0x1800bead9  test    eax, eax
0x1800beadb  jz      short loc_1800BEAF4
0x1800beadd  xor     ecx, ecx
0x1800beadf  mov     [rbp+5B0h+var_450], cx
0x1800beae6  test    eax, eax
0x1800beae8  jle     short loc_1800BEAF4
0x1800beaea  movzx   eax, ax
0x1800beaed  or      eax, 80070000h
0x1800beaf2  test    eax, eax
0x1800beaf4  js      short loc_1800BEB26
0x1800beaf6  lea     r9, [rbp+5B0h+var_450]; unsigned __int16 *
0x1800beafd  mov     r8, r12; unsigned __int16 *
0x1800beb00  mov     rdx, rdi; unsigned __int16 *
0x1800beb03  mov     rcx, rbx; HKEY
0x1800beb06  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800beb0b  test    eax, eax
0x1800beb0d  jns     short loc_1800BEB26
0x1800beb0f  mov     rcx, [rbp+5B8h]; this
0x1800beb16  mov     r9d, eax; char *
0x1800beb19  mov     r8, r14; unsigned int
0x1800beb1c  mov     edx, 0C9h; void *
0x1800beb21  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800beb26  mov     r8, r12; pszValue
0x1800beb29  mov     rdx, r13; pszSubKey
0x1800beb2c  mov     rcx, r15; hkey
0x1800beb2f  call    cs:__imp_SHDeleteValueW
0x1800beb35  lea     r12, aDefaultdomainn; "DefaultDomainName"
0x1800beb3c  mov     rdx, rdi; pszSubKey
0x1800beb3f  mov     r8, r12; pszValue
0x1800beb42  mov     rcx, rbx; hkey
0x1800beb45  call    cs:__imp_SHDeleteValueW
0x1800beb4b  lea     rax, [rsp+6B0h+var_670]
0x1800beb50  mov     [rsp+6B0h+var_670], 202h
0x1800beb58  mov     [rsp+6B0h+pcbData], rax; pcbData
0x1800beb5d  mov     r9d, 2; dwFlags
0x1800beb63  lea     rax, [rbp+5B0h+var_240]
0x1800beb6a  mov     r8, r12; lpValue
0x1800beb6d  mov     [rsp+6B0h+pvData], rax; pvData
0x1800beb72  mov     rdx, r13; lpSubKey
0x1800beb75  mov     rcx, r15; hkey
0x1800beb78  mov     [rsp+6B0h+pdwType], 0; int
0x1800beb81  call    cs:__imp_RegGetValueW
0x1800beb87  test    eax, eax
0x1800beb89  jz      short loc_1800BEBA2
0x1800beb8b  xor     ecx, ecx
0x1800beb8d  mov     [rbp+5B0h+var_240], cx
0x1800beb94  test    eax, eax
0x1800beb96  jle     short loc_1800BEBA2
0x1800beb98  movzx   eax, ax
0x1800beb9b  or      eax, 80070000h
0x1800beba0  test    eax, eax
0x1800beba2  js      short loc_1800BEBD4
0x1800beba4  lea     r9, [rbp+5B0h+var_240]; unsigned __int16 *
0x1800bebab  mov     r8, r12; unsigned __int16 *
0x1800bebae  mov     rdx, rdi; unsigned __int16 *
0x1800bebb1  mov     rcx, rbx; HKEY
0x1800bebb4  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800bebb9  test    eax, eax
0x1800bebbb  jns     short loc_1800BEBD4
0x1800bebbd  mov     rcx, [rbp+5B8h]; this
0x1800bebc4  mov     r9d, eax; char *
0x1800bebc7  mov     r8, r14; unsigned int
0x1800bebca  mov     edx, 0D1h; void *
0x1800bebcf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bebd4  mov     r8, r12; pszValue
0x1800bebd7  mov     rdx, r13; pszSubKey
0x1800bebda  mov     rcx, r15; hkey
0x1800bebdd  call    cs:__imp_SHDeleteValueW
0x1800bebe3  lea     r12, aAutologoncount; "AutoLogonCount"
0x1800bebea  mov     rdx, rdi; pszSubKey
0x1800bebed  mov     r8, r12; pszValue
0x1800bebf0  mov     rcx, rbx; hkey
0x1800bebf3  call    cs:__imp_SHDeleteValueW
0x1800bebf9  lea     r9, [rsp+6B0h+var_66C]; unsigned int *
0x1800bebfe  mov     [rsp+6B0h+var_66C], 0
0x1800bec06  mov     r8, r12; unsigned __int16 *
0x1800bec09  mov     rdx, r13; unsigned __int16 *
0x1800bec0c  mov     rcx, r15; HKEY
0x1800bec0f  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800bec14  test    eax, eax
0x1800bec16  js      short loc_1800BEC46
0x1800bec18  mov     r9d, [rsp+6B0h+var_66C]; unsigned int
0x1800bec1d  mov     r8, r12; unsigned __int16 *
0x1800bec20  mov     rdx, rdi; unsigned __int16 *
0x1800bec23  mov     rcx, rbx; HKEY
0x1800bec26  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800bec2b  test    eax, eax
0x1800bec2d  jns     short loc_1800BEC46
0x1800bec2f  mov     rcx, [rbp+5B8h]; this
0x1800bec36  mov     r9d, eax; char *
0x1800bec39  mov     r8, r14; unsigned int
0x1800bec3c  mov     edx, 0D9h; void *
0x1800bec41  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bec46  mov     r8, r12; pszValue
0x1800bec49  mov     rdx, r13; pszSubKey
0x1800bec4c  mov     rcx, r15; hkey
0x1800bec4f  call    cs:__imp_SHDeleteValueW
0x1800bec55  lea     r12, aAutoadminlogon; "AutoAdminLogon"
0x1800bec5c  mov     rdx, rdi; pszSubKey
0x1800bec5f  mov     r8, r12; pszValue
0x1800bec62  mov     rcx, rbx; hkey
0x1800bec65  call    cs:__imp_SHDeleteValueW
0x1800bec6b  lea     rax, [rsp+6B0h+var_670]
0x1800bec70  mov     [rsp+6B0h+var_670], 4
0x1800bec78  mov     [rsp+6B0h+pcbData], rax; pcbData
0x1800bec7d  mov     r9d, 2; dwFlags
0x1800bec83  lea     rax, [rsp+6B0h+var_668]
0x1800bec88  mov     r8, r12; lpValue
0x1800bec8b  mov     [rsp+6B0h+pvData], rax; pvData
0x1800bec90  mov     rdx, r13; lpSubKey
0x1800bec93  mov     rcx, r15; hkey
0x1800bec96  mov     [rsp+6B0h+pdwType], 0; int
0x1800bec9f  call    cs:__imp_RegGetValueW
0x1800beca5  test    eax, eax
0x1800beca7  jz      short loc_1800BECBE
0x1800beca9  xor     ecx, ecx
0x1800becab  mov     [rsp+6B0h+var_668], cx
0x1800becb0  test    eax, eax
0x1800becb2  jle     short loc_1800BECBE
0x1800becb4  movzx   eax, ax
0x1800becb7  or      eax, 80070000h
0x1800becbc  test    eax, eax
0x1800becbe  js      short loc_1800BECEE
0x1800becc0  lea     r9, [rsp+6B0h+var_668]; unsigned __int16 *
0x1800becc5  mov     r8, r12; unsigned __int16 *
0x1800becc8  mov     rdx, rdi; unsigned __int16 *
0x1800beccb  mov     rcx, rbx; HKEY
0x1800becce  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800becd3  test    eax, eax
0x1800becd5  jns     short loc_1800BECEE
0x1800becd7  mov     rcx, [rbp+5B8h]; this
0x1800becde  mov     r9d, eax; char *
0x1800bece1  mov     r8, r14; unsigned int
0x1800bece4  mov     edx, 0E1h; void *
0x1800bece9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800becee  mov     r8, r12; pszValue
0x1800becf1  mov     rdx, r13; pszSubKey
0x1800becf4  mov     rcx, r15; hkey
0x1800becf7  call    cs:__imp_SHDeleteValueW
0x1800becfd  lea     rdx, aCacheddefaultp; "CachedDefaultPassword"
0x1800bed04  lea     rcx, aDefaultpasswor; "DefaultPassword"
0x1800bed0b  call    ?_MoveLsaSecret@@YAJPEBG0@Z; _MoveLsaSecret(ushort const *,ushort const *)
0x1800bed10  test    eax, eax
0x1800bed12  jns     short loc_1800BED2B
0x1800bed14  mov     rcx, [rbp+5B8h]; this
0x1800bed1b  mov     r9d, eax; char *
0x1800bed1e  mov     r8, r14; unsigned int
0x1800bed21  mov     edx, 0F6h; void *
0x1800bed26  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bed2b  xor     eax, eax
0x1800bed2d  jmp     short loc_1800BED34
0x1800bed2f  mov     eax, 8000FFFFh
0x1800bed34  mov     rcx, [rbp+5B0h+var_30]
0x1800bed3b  xor     rcx, rsp; StackCookie
0x1800bed3e  call    __security_check_cookie
0x1800bed43  lea     r11, [rsp+6B0h+var_20]
0x1800bed4b  mov     rbx, [r11+30h]
0x1800bed4f  mov     rdi, [r11+38h]
0x1800bed53  mov     rsp, r11
0x1800bed56  pop     r15
0x1800bed58  pop     r14
0x1800bed5a  pop     r13
0x1800bed5c  pop     r12
0x1800bed5e  pop     rbp
0x1800bed5f  retn
```
