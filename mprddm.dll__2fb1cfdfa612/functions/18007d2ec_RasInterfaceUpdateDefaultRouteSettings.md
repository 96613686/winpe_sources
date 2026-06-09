# RasInterfaceUpdateDefaultRouteSettings

- ea: `0x18007d2ec`
- end: `0x18007d68a`
- name: `RasInterfaceUpdateDefaultRouteSettings`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180014920`

## callees

- `0x180074d24`
- `0x180074fb4`
- `0x1800757c0`
- `0x18007a204`
- `0x18007cd94`
- `0x18007d2ec`
- `0x18007d690`
- `0x18007d7ac`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18007d5dc`
- `KERNEL32!LeaveCriticalSection` at `0x18007d5dc`
- `KERNEL32!EnterCriticalSection` at `0x18007d333`
- `KERNEL32!EnterCriticalSection` at `0x18007d333`
- `ADVAPI32!RegCloseKey` at `0x18007d4ca`
- `ADVAPI32!RegCloseKey` at `0x18007d4ca`
- `ADVAPI32!RegOpenKeyExA` at `0x18007d46d`
- `ADVAPI32!RegOpenKeyExA` at `0x18007d46d`
- `ADVAPI32!RegQueryValueExA` at `0x18007d4a1`
- `ADVAPI32!RegQueryValueExA` at `0x18007d4a1`

## string_xrefs

- `0x18007d45a`: `SYSTEM\CurrentControlSet\services\RemoteAccess\Parameters\IKEV2`
- `0x18007d39a`: `RasUpdateDefaultRouteSettings(fIpv4:%u)(fSet:%u)(Luid:%I64X)(type:%s)(updateMetric: %s)`
- `0x18007d3e3`: `RasUpdateDefaultRouteSettings: AdjustOtherInterfaceMetrics failed. Error %d`
- `0x18007d5c9`: `RasUpdateDefaultRouteSettings: AdjustVPNInterfaceDefaultRoute failed. Error %d`
- `0x18007d62c`: `RasUpdateDefaultRouteSettings: AdjustOtherInterfaceDefaultRoute failed. Error %d`

## pseudocode

```c
__int64 __fastcall RasInterfaceUpdateDefaultRouteSettings(char a1, char a2, HKEY a3, char a4)
{
  HKEY *v8; // rax
  char v9; // dl
  const char *v10; // rcx
  const char *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  LPVOID *v14; // r9
  unsigned int AllParameters; // ebx
  const CHAR *v16; // rcx
  int v17; // eax
  __int64 v18; // rdx
  LSTATUS v19; // edi
  HKEY v20; // rcx
  int v21; // ecx
  int v22; // r8d
  const NPI_MODULEID *v23; // rdi
  int v24; // ecx
  int v25; // ecx
  int v26; // r8d
  bool v27; // zf
  __int64 v28; // rcx
  int v29; // eax
  bool v30; // zf
  int v31; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  BYTE Data[8]; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD Type; // [rsp+70h] [rbp-90h] BYREF
  DWORD cbData; // [rsp+74h] [rbp-8Ch] BYREF
  HKEY v41; // [rsp+78h] [rbp-88h] BYREF
  __int128 v42; // [rsp+80h] [rbp-80h]
  _BYTE v43[32]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v44; // [rsp+B0h] [rbp-50h]
  int v45; // [rsp+B8h] [rbp-48h]
  int v46; // [rsp+108h] [rbp+8h]
  bool v47; // [rsp+128h] [rbp+28h]
  int v48; // [rsp+168h] [rbp+68h]

  v42 = 0;
  EnterCriticalSection(&g_csInterfaceCache);
  v41 = a3;
  v8 = (HKEY *)g_RasVpnLuids;
  if ( g_RasVpnLuids )
  {
    while ( *v8 != a3 )
    {
      v8 = (HKEY *)v8[2];
      if ( !v8 )
        goto LABEL_4;
    }
    v9 = 1;
  }
  else
  {
LABEL_4:
    v9 = 0;
    *((_QWORD *)&v42 + 1) = g_RasVpnLuids;
  }
  v10 = "yes";
  if ( !a4 )
    v10 = "no";
  lpcbData = (LPDWORD)v10;
  v11 = "vpn";
  if ( !v9 )
    v11 = "internet";
  phkResult = (PHKEY)v11;
  TraceMsg("RasUpdateDefaultRouteSettings(fIpv4:%u)(fSet:%u)(Luid:%I64X)(type:%s)(updateMetric: %s)");
  if ( !a4 )
  {
    hKey = 0;
    Type = 4;
    cbData = 4;
    *(_DWORD *)Data = 0;
    v19 = RegOpenKeyExA(
            HKEY_LOCAL_MACHINE,
            "SYSTEM\\CurrentControlSet\\services\\RemoteAccess\\Parameters\\IKEV2",
            0,
            0x20019u,
            &hKey);
    if ( !v19 )
    {
      v19 = RegQueryValueExA(hKey, "DisableDefaultRouteHandling", 0, &Type, Data, &cbData);
      if ( v19 || Type != 4 )
      {
        *(_DWORD *)Data = 0;
        if ( v19 == 2 )
          v19 = 0;
      }
    }
    v20 = hKey;
    if ( hKey )
      RegCloseKey(hKey);
    if ( v19 || *(_DWORD *)Data != 1 )
    {
      memset_0(v43, 0, 0xF0u);
      hKey = a3;
      v23 = &NPI_MS_IPV4_MODULEID;
      if ( !a2 )
        v23 = &NPI_MS_IPV6_MODULEID;
      AllParameters = GetAllParameters(v21, (_DWORD)v23, v22, (unsigned int)&hKey, phkResulta, (__int64)v43);
      if ( AllParameters )
        goto LABEL_42;
      memset_0(v43, 255, 0xF0u);
      v44 = 0;
      v47 = a1 == 0;
      v45 = 0;
      v46 = 0;
      v48 = 0;
      AllParameters = SetAllParameters(v24, (_DWORD)v23, 7, (unsigned int)&hKey, 8, (__int64)v43, 240, 0);
      if ( AllParameters )
        goto LABEL_42;
      memset_0(v43, 0, 0xF0u);
      AllParameters = GetAllParameters(v25, (_DWORD)v23, v26, (unsigned int)&hKey, phkResultb, (__int64)v43);
      if ( AllParameters )
        goto LABEL_42;
      if ( a1 )
        v27 = !v47;
      else
        v27 = v47;
      if ( !v27 )
      {
        AllParameters = 1003;
LABEL_42:
        v16 = "RasUpdateDefaultRouteSettings: AdjustVPNInterfaceDefaultRoute failed. Error %d";
        goto LABEL_43;
      }
    }
    LOBYTE(v18) = a1;
    LOBYTE(v20) = a2;
    AllParameters = AdjustOtherInterfaceDefaultRoute(v20, v18, &v41);
    if ( AllParameters )
    {
      v16 = "RasUpdateDefaultRouteSettings: AdjustOtherInterfaceDefaultRoute failed. Error %d";
      goto LABEL_43;
    }
    goto LABEL_44;
  }
  v14 = &g_IpV4InterfaceTable;
  LOBYTE(v12) = a1;
  if ( !a2 )
    v14 = &g_IpV6InterfaceTable;
  LOBYTE(v13) = a2;
  AllParameters = AdjustOtherInterfaceMetrics(v13, v12, &v41, v14, phkResult, lpcbData);
  if ( AllParameters )
  {
    v16 = "RasUpdateDefaultRouteSettings: AdjustOtherInterfaceMetrics failed. Error %d";
LABEL_43:
    TraceMsg(v16);
    goto LABEL_44;
  }
  if ( a2 )
  {
    if ( a1 )
      v17 = g_NumVpnIpv4RouteTableChanges + 1;
    else
      v17 = g_NumVpnIpv4RouteTableChanges - 1;
    g_NumVpnIpv4RouteTableChanges = v17;
  }
  else if ( a1 )
  {
    ++g_NumVpnIpv6RouteTableChanges;
  }
  else
  {
    --g_NumVpnIpv6RouteTableChanges;
  }
LABEL_44:
  LeaveCriticalSection(&g_csInterfaceCache);
  if ( a2 )
  {
    v29 = g_NumVpnIpv4RouteTableChanges;
    if ( !g_NumVpnIpv4RouteTableChanges )
      goto LABEL_49;
    if ( !g_hInterfaceChangeNotificationV4 )
    {
      LOBYTE(v28) = 1;
      RegisterInterfaceChangeNotifications(v28);
      v29 = g_NumVpnIpv4RouteTableChanges;
    }
    if ( !v29 )
    {
LABEL_49:
      v30 = g_hInterfaceChangeNotificationV4 == 0;
      goto LABEL_57;
    }
  }
  else
  {
    v31 = g_NumVpnIpv6RouteTableChanges;
    if ( !g_NumVpnIpv6RouteTableChanges )
      goto LABEL_56;
    if ( !g_hInterfaceChangeNotificationV6 )
    {
      RegisterInterfaceChangeNotifications(0);
      v31 = g_NumVpnIpv6RouteTableChanges;
    }
    if ( !v31 )
    {
LABEL_56:
      v30 = g_hInterfaceChangeNotificationV6 == 0;
LABEL_57:
      if ( !v30 )
        DeregisterInterfaceChangeNotifications();
    }
  }
  return AllParameters;
}

```

## disassembly

```asm
0x18007d2ec  push    rbp
0x18007d2ee  push    rbx
0x18007d2ef  push    rsi
0x18007d2f0  push    rdi
0x18007d2f1  push    r12
0x18007d2f3  push    r14
0x18007d2f5  push    r15
0x18007d2f7  lea     rbp, [rsp-90h]
0x18007d2ff  sub     rsp, 190h
0x18007d306  mov     rax, cs:__security_cookie
0x18007d30d  xor     rax, rsp
0x18007d310  mov     [rbp+0C0h+var_40], rax
0x18007d317  movzx   esi, cl
0x18007d31a  xorps   xmm0, xmm0
0x18007d31d  lea     rcx, g_csInterfaceCache; lpCriticalSection
0x18007d324  movzx   r14d, dl
0x18007d328  movdqu  [rbp+0C0h+var_140], xmm0
0x18007d32d  mov     dil, r9b
0x18007d330  mov     rbx, r8
0x18007d333  call    cs:__imp_EnterCriticalSection
0x18007d339  mov     rcx, cs:g_RasVpnLuids
0x18007d340  xor     r15d, r15d
0x18007d343  mov     [rsp+1C0h+var_148], rbx
0x18007d348  mov     rax, rcx
0x18007d34b  test    rcx, rcx
0x18007d34e  jz      short loc_18007D362
0x18007d350  cmp     [rax], rbx
0x18007d353  jz      loc_18007D3EF
0x18007d359  mov     rax, [rax+10h]
0x18007d35d  test    rax, rax
0x18007d360  jnz     short loc_18007D350
0x18007d362  mov     dl, r15b
0x18007d365  mov     qword ptr [rbp+0C0h+var_140+8], rcx
0x18007d369  lea     r8, aInternet; "internet"
0x18007d370  test    dil, dil
0x18007d373  lea     rax, aNo; "no"
0x18007d37a  mov     r9, rbx
0x18007d37d  lea     rcx, aYes; "yes"
0x18007d384  cmovz   rcx, rax
0x18007d388  test    dl, dl
0x18007d38a  mov     [rsp+1C0h+lpcbData], rcx
0x18007d38f  lea     rax, aVpn; "vpn"
0x18007d396  cmovz   rax, r8
0x18007d39a  lea     rcx, aRasupdatedefau_1; "RasUpdateDefaultRouteSettings(fIpv4:%u)"...
0x18007d3a1  mov     r8d, esi
0x18007d3a4  mov     [rsp+1C0h+phkResult], rax
0x18007d3a9  mov     edx, r14d
0x18007d3ac  call    TraceMsg
0x18007d3b1  test    dil, dil
0x18007d3b4  jz      short loc_18007D432
0x18007d3b6  lea     rax, g_IpV6InterfaceTable
0x18007d3bd  test    r14b, r14b
0x18007d3c0  lea     r9, g_IpV4InterfaceTable
0x18007d3c7  mov     dl, sil
0x18007d3ca  cmovz   r9, rax
0x18007d3ce  lea     r8, [rsp+1C0h+var_148]
0x18007d3d3  mov     cl, r14b
0x18007d3d6  call    AdjustOtherInterfaceMetrics
0x18007d3db  mov     ebx, eax
0x18007d3dd  test    eax, eax
0x18007d3df  jz      short loc_18007D3F6
0x18007d3e1  mov     edx, eax
0x18007d3e3  lea     rcx, aRasupdatedefau; "RasUpdateDefaultRouteSettings: AdjustOt"...
0x18007d3ea  jmp     loc_18007D5D0
0x18007d3ef  mov     dl, 1
0x18007d3f1  jmp     loc_18007D369
0x18007d3f6  test    r14b, r14b
0x18007d3f9  jz      short loc_18007D417
0x18007d3fb  mov     eax, cs:g_NumVpnIpv4RouteTableChanges
0x18007d401  test    sil, sil
0x18007d404  jz      short loc_18007D40A
0x18007d406  inc     eax
0x18007d408  jmp     short loc_18007D40C
0x18007d40a  dec     eax
0x18007d40c  mov     cs:g_NumVpnIpv4RouteTableChanges, eax
0x18007d412  jmp     loc_18007D5D5
0x18007d417  test    sil, sil
0x18007d41a  jz      short loc_18007D427
0x18007d41c  inc     cs:g_NumVpnIpv6RouteTableChanges
0x18007d422  jmp     loc_18007D5D5
0x18007d427  dec     cs:g_NumVpnIpv6RouteTableChanges
0x18007d42d  jmp     loc_18007D5D5
0x18007d432  mov     r12d, 4
0x18007d438  mov     [rsp+1C0h+hKey], r15
0x18007d43d  lea     rax, [rsp+1C0h+hKey]
0x18007d442  mov     [rsp+1C0h+Type], r12d
0x18007d447  mov     r9d, 20019h; samDesired
0x18007d44d  mov     [rsp+1C0h+cbData], r12d
0x18007d452  xor     r8d, r8d; ulOptions
0x18007d455  mov     [rsp+1C0h+phkResult], rax; phkResult
0x18007d45a  lea     rdx, aSystemCurrentc_20; "SYSTEM\\CurrentControlSet\\services\\Re"...
0x18007d461  mov     dword ptr [rsp+1C0h+Data], r15d
0x18007d466  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007d46d  call    cs:__imp_RegOpenKeyExA
0x18007d473  mov     edi, eax
0x18007d475  test    eax, eax
0x18007d477  jnz     short loc_18007D4C0
0x18007d479  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18007d47e  lea     rax, [rsp+1C0h+cbData]
0x18007d483  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x18007d488  lea     r9, [rsp+1C0h+Type]; lpType
0x18007d48d  lea     rax, [rsp+1C0h+Data]
0x18007d492  xor     r8d, r8d; lpReserved
0x18007d495  lea     rdx, aDisabledefault; "DisableDefaultRouteHandling"
0x18007d49c  mov     [rsp+1C0h+phkResult], rax; lpData
0x18007d4a1  call    cs:__imp_RegQueryValueExA
0x18007d4a7  mov     edi, eax
0x18007d4a9  test    eax, eax
0x18007d4ab  jnz     short loc_18007D4B4
0x18007d4ad  cmp     [rsp+1C0h+Type], r12d
0x18007d4b2  jz      short loc_18007D4C0
0x18007d4b4  cmp     edi, 2
0x18007d4b7  mov     dword ptr [rsp+1C0h+Data], r15d
0x18007d4bc  cmovz   edi, r15d
0x18007d4c0  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18007d4c5  test    rcx, rcx
0x18007d4c8  jz      short loc_18007D4D0
0x18007d4ca  call    cs:__imp_RegCloseKey
0x18007d4d0  test    edi, edi
0x18007d4d2  jnz     short loc_18007D4DF
0x18007d4d4  cmp     dword ptr [rsp+1C0h+Data], 1
0x18007d4d9  jz      loc_18007D614
0x18007d4df  mov     r12d, 0F0h
0x18007d4e5  lea     rcx, [rbp+0C0h+var_130]; void *
0x18007d4e9  mov     r8d, r12d; Size
0x18007d4ec  xor     edx, edx; Val
0x18007d4ee  call    memset_0
0x18007d4f3  lea     rax, NPI_MS_IPV6_MODULEID
0x18007d4fa  mov     [rsp+1C0h+hKey], rbx
0x18007d4ff  test    r14b, r14b
0x18007d502  lea     rdi, NPI_MS_IPV4_MODULEID
0x18007d509  lea     r9, [rsp+1C0h+hKey]
0x18007d50e  cmovz   rdi, rax
0x18007d512  lea     rax, [rbp+0C0h+var_130]
0x18007d516  mov     rdx, rdi
0x18007d519  mov     [rsp+1C0h+lpcbData], rax
0x18007d51e  call    GetAllParameters
0x18007d523  mov     ebx, eax
0x18007d525  test    eax, eax
0x18007d527  jnz     loc_18007D5C7
0x18007d52d  mov     r8d, r12d; Size
0x18007d530  lea     edx, [r12+0Fh]; Val
0x18007d535  lea     rcx, [rbp+0C0h+var_130]; void *
0x18007d539  call    memset_0
0x18007d53e  mov     [rsp+1C0h+var_188], r15d
0x18007d543  lea     rax, [rbp+0C0h+var_130]
0x18007d547  mov     [rsp+1C0h+var_190], r12d
0x18007d54c  lea     r9, [rsp+1C0h+hKey]
0x18007d551  mov     [rsp+1C0h+lpcbData], rax
0x18007d556  lea     r8d, [rbx+7]
0x18007d55a  test    sil, sil
0x18007d55d  mov     dword ptr [rsp+1C0h+phkResult], 8
0x18007d565  mov     rdx, rdi
0x18007d568  mov     [rbp+0C0h+var_110], r15
0x18007d56c  setz    [rbp+0C0h+var_98]
0x18007d570  mov     [rbp+0C0h+var_108], r15d
0x18007d574  mov     [rbp+0C0h+var_B8], r15d
0x18007d578  mov     [rbp+0C0h+var_58], r15d
0x18007d57c  call    SetAllParameters
0x18007d581  mov     ebx, eax
0x18007d583  test    eax, eax
0x18007d585  jnz     short loc_18007D5C7
0x18007d587  mov     r8d, r12d; Size
0x18007d58a  lea     rcx, [rbp+0C0h+var_130]; void *
0x18007d58e  xor     edx, edx; Val
0x18007d590  call    memset_0
0x18007d595  lea     rax, [rbp+0C0h+var_130]
0x18007d599  mov     rdx, rdi
0x18007d59c  lea     r9, [rsp+1C0h+hKey]
0x18007d5a1  mov     [rsp+1C0h+lpcbData], rax
0x18007d5a6  call    GetAllParameters
0x18007d5ab  mov     ebx, eax
0x18007d5ad  test    eax, eax
0x18007d5af  jnz     short loc_18007D5C7
0x18007d5b1  test    sil, sil
0x18007d5b4  jz      short loc_18007D5BC
0x18007d5b6  cmp     [rbp+0C0h+var_98], r15b
0x18007d5ba  jmp     short loc_18007D5C0
0x18007d5bc  cmp     [rbp+0C0h+var_98], 1
0x18007d5c0  jz      short loc_18007D614
0x18007d5c2  mov     ebx, 3EBh
0x18007d5c7  mov     edx, ebx
0x18007d5c9  lea     rcx, aRasupdatedefau_2; "RasUpdateDefaultRouteSettings: AdjustVP"...
0x18007d5d0  call    TraceMsg
0x18007d5d5  lea     rcx, g_csInterfaceCache; lpCriticalSection
0x18007d5dc  call    cs:__imp_LeaveCriticalSection
0x18007d5e2  test    r14b, r14b
0x18007d5e5  jz      short loc_18007D635
0x18007d5e7  mov     eax, cs:g_NumVpnIpv4RouteTableChanges
0x18007d5ed  test    eax, eax
0x18007d5ef  jz      short loc_18007D60B
0x18007d5f1  cmp     cs:g_hInterfaceChangeNotificationV4, r15
0x18007d5f8  jnz     short loc_18007D607
0x18007d5fa  mov     cl, 1
0x18007d5fc  call    RegisterInterfaceChangeNotifications
0x18007d601  mov     eax, cs:g_NumVpnIpv4RouteTableChanges
0x18007d607  test    eax, eax
0x18007d609  jnz     short loc_18007D667
0x18007d60b  cmp     cs:g_hInterfaceChangeNotificationV4, r15
0x18007d612  jmp     short loc_18007D660
0x18007d614  lea     r8, [rsp+1C0h+var_148]
0x18007d619  mov     dl, sil
0x18007d61c  mov     cl, r14b
0x18007d61f  call    AdjustOtherInterfaceDefaultRoute
0x18007d624  mov     ebx, eax
0x18007d626  test    eax, eax
0x18007d628  jz      short loc_18007D5D5
0x18007d62a  mov     edx, eax
0x18007d62c  lea     rcx, aRasupdatedefau_0; "RasUpdateDefaultRouteSettings: AdjustOt"...
0x18007d633  jmp     short loc_18007D5D0
0x18007d635  mov     eax, cs:g_NumVpnIpv6RouteTableChanges
0x18007d63b  test    eax, eax
0x18007d63d  jz      short loc_18007D659
0x18007d63f  cmp     cs:g_hInterfaceChangeNotificationV6, r15
0x18007d646  jnz     short loc_18007D655
0x18007d648  xor     ecx, ecx
0x18007d64a  call    RegisterInterfaceChangeNotifications
0x18007d64f  mov     eax, cs:g_NumVpnIpv6RouteTableChanges
0x18007d655  test    eax, eax
0x18007d657  jnz     short loc_18007D667
0x18007d659  cmp     cs:g_hInterfaceChangeNotificationV6, r15
0x18007d660  jz      short loc_18007D667
0x18007d662  call    DeregisterInterfaceChangeNotifications
0x18007d667  mov     eax, ebx
0x18007d669  mov     rcx, [rbp+0C0h+var_40]
0x18007d670  xor     rcx, rsp; StackCookie
0x18007d673  call    __security_check_cookie
0x18007d678  add     rsp, 190h
0x18007d67f  pop     r15
0x18007d681  pop     r14
0x18007d683  pop     r12
0x18007d685  pop     rdi
0x18007d686  pop     rsi
0x18007d687  pop     rbx
0x18007d688  pop     rbp
0x18007d689  retn
```
