# RasInterfaceUpdateDefaultRouteSettings

- ea: `0x18009e2b0`
- end: `0x18009e657`
- name: `RasInterfaceUpdateDefaultRouteSettings`
- size: `935`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180032f80`

## callees

- `0x18009dcfc`
- `0x18009e2b0`
- `0x18009e788`
- `0x18009e8ac`
- `0x1800a4b9c`
- `0x1800a4e5c`
- `0x1800a5370`
- `0x1800aa074`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009e2f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009e2f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e5a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e5a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18009e437`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18009e437`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18009e471`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18009e471`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009e4a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009e4a0`

## string_xrefs

- `0x18009e364`: `RasUpdateDefaultRouteSettings(fIpv4:%u)(fSet:%u)(Luid:%I64X)(type:%s)(updateMetric: %s)`
- `0x18009e58f`: `RasUpdateDefaultRouteSettings: AdjustVPNInterfaceDefaultRoute failed. Error %d`
- `0x18009e3ad`: `RasUpdateDefaultRouteSettings: AdjustOtherInterfaceMetrics failed. Error %d`
- `0x18009e5f8`: `RasUpdateDefaultRouteSettings: AdjustOtherInterfaceDefaultRoute failed. Error %d`
- `0x18009e424`: `SYSTEM\CurrentControlSet\services\RemoteAccess\Parameters\IKEV2`

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
  int v25; // r8d
  int v26; // ecx
  int v27; // r8d
  bool v28; // zf
  __int64 v29; // rcx
  int v30; // eax
  bool v31; // zf
  int v32; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  int phkResultc; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  BYTE Data[8]; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD Type; // [rsp+70h] [rbp-90h] BYREF
  DWORD cbData; // [rsp+74h] [rbp-8Ch] BYREF
  HKEY v43; // [rsp+78h] [rbp-88h] BYREF
  __int128 v44; // [rsp+80h] [rbp-80h]
  _BYTE v45[32]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v46; // [rsp+B0h] [rbp-50h]
  int v47; // [rsp+B8h] [rbp-48h]
  int v48; // [rsp+108h] [rbp+8h]
  bool v49; // [rsp+128h] [rbp+28h]
  int v50; // [rsp+168h] [rbp+68h]

  v44 = 0;
  EnterCriticalSection(&g_csInterfaceCache);
  v43 = a3;
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
    *((_QWORD *)&v44 + 1) = g_RasVpnLuids;
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
      memset_0(v45, 0, 0xF0u);
      hKey = a3;
      v23 = &NPI_MS_IPV4_MODULEID;
      if ( !a2 )
        v23 = &NPI_MS_IPV6_MODULEID;
      AllParameters = GetAllParameters(v21, (_DWORD)v23, v22, (unsigned int)&hKey, phkResulta, (__int64)v45);
      if ( AllParameters )
        goto LABEL_42;
      memset_0(v45, 255, 0xF0u);
      v46 = 0;
      v47 = 0;
      v48 = 0;
      v50 = 0;
      v49 = a1 == 0;
      AllParameters = SetAllParameters(v24, (_DWORD)v23, v25, (unsigned int)&hKey, phkResultb, (__int64)v45);
      if ( AllParameters )
        goto LABEL_42;
      memset_0(v45, 0, 0xF0u);
      AllParameters = GetAllParameters(v26, (_DWORD)v23, v27, (unsigned int)&hKey, phkResultc, (__int64)v45);
      if ( AllParameters )
        goto LABEL_42;
      if ( a1 )
        v28 = !v49;
      else
        v28 = v49;
      if ( !v28 )
      {
        AllParameters = 1003;
LABEL_42:
        v16 = "RasUpdateDefaultRouteSettings: AdjustVPNInterfaceDefaultRoute failed. Error %d";
        goto LABEL_43;
      }
    }
    LOBYTE(v18) = a1;
    LOBYTE(v20) = a2;
    AllParameters = AdjustOtherInterfaceDefaultRoute(v20, v18, &v43);
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
  AllParameters = AdjustOtherInterfaceMetrics(v13, v12, &v43, v14, phkResult, lpcbData);
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
    v30 = g_NumVpnIpv4RouteTableChanges;
    if ( !g_NumVpnIpv4RouteTableChanges )
      goto LABEL_49;
    if ( !g_hInterfaceChangeNotificationV4 )
    {
      LOBYTE(v29) = 1;
      RegisterInterfaceChangeNotifications(v29);
      v30 = g_NumVpnIpv4RouteTableChanges;
    }
    if ( !v30 )
    {
LABEL_49:
      v31 = g_hInterfaceChangeNotificationV4 == 0;
      goto LABEL_57;
    }
  }
  else
  {
    v32 = g_NumVpnIpv6RouteTableChanges;
    if ( !g_NumVpnIpv6RouteTableChanges )
      goto LABEL_56;
    if ( !g_hInterfaceChangeNotificationV6 )
    {
      RegisterInterfaceChangeNotifications(0);
      v32 = g_NumVpnIpv6RouteTableChanges;
    }
    if ( !v32 )
    {
LABEL_56:
      v31 = g_hInterfaceChangeNotificationV6 == 0;
LABEL_57:
      if ( !v31 )
        DeregisterInterfaceChangeNotifications();
    }
  }
  return AllParameters;
}

```

## disassembly

```asm
0x18009e2b0  push    rbp
0x18009e2b2  push    rbx
0x18009e2b3  push    rsi
0x18009e2b4  push    rdi
0x18009e2b5  push    r12
0x18009e2b7  push    r14
0x18009e2b9  push    r15
0x18009e2bb  lea     rbp, [rsp-90h]
0x18009e2c3  sub     rsp, 190h
0x18009e2ca  mov     rax, cs:__security_cookie
0x18009e2d1  xor     rax, rsp
0x18009e2d4  mov     [rbp+0C0h+var_40], rax
0x18009e2db  movzx   esi, cl
0x18009e2de  xorps   xmm0, xmm0
0x18009e2e1  lea     rcx, g_csInterfaceCache; lpCriticalSection
0x18009e2e8  movzx   r14d, dl
0x18009e2ec  movdqu  [rbp+0C0h+var_140], xmm0
0x18009e2f1  mov     dil, r9b
0x18009e2f4  mov     rbx, r8
0x18009e2f7  call    cs:__imp_EnterCriticalSection
0x18009e2fe  nop     dword ptr [rax+rax+00h]
0x18009e303  mov     rcx, cs:g_RasVpnLuids
0x18009e30a  xor     r15d, r15d
0x18009e30d  mov     [rsp+1C0h+var_148], rbx
0x18009e312  mov     rax, rcx
0x18009e315  test    rcx, rcx
0x18009e318  jz      short loc_18009E32C
0x18009e31a  cmp     [rax], rbx
0x18009e31d  jz      loc_18009E3B9
0x18009e323  mov     rax, [rax+10h]
0x18009e327  test    rax, rax
0x18009e32a  jnz     short loc_18009E31A
0x18009e32c  mov     dl, r15b
0x18009e32f  mov     qword ptr [rbp+0C0h+var_140+8], rcx
0x18009e333  lea     r8, aInternet; "internet"
0x18009e33a  test    dil, dil
0x18009e33d  lea     rax, aNo; "no"
0x18009e344  mov     r9, rbx
0x18009e347  lea     rcx, aYes; "yes"
0x18009e34e  cmovz   rcx, rax
0x18009e352  test    dl, dl
0x18009e354  mov     [rsp+1C0h+lpcbData], rcx
0x18009e359  lea     rax, aVpn_1; "vpn"
0x18009e360  cmovz   rax, r8
0x18009e364  lea     rcx, aRasupdatedefau_1; "RasUpdateDefaultRouteSettings(fIpv4:%u)"...
0x18009e36b  mov     r8d, esi
0x18009e36e  mov     [rsp+1C0h+phkResult], rax
0x18009e373  mov     edx, r14d
0x18009e376  call    TraceMsg
0x18009e37b  test    dil, dil
0x18009e37e  jz      short loc_18009E3FC
0x18009e380  lea     rax, g_IpV6InterfaceTable
0x18009e387  test    r14b, r14b
0x18009e38a  lea     r9, g_IpV4InterfaceTable
0x18009e391  mov     dl, sil
0x18009e394  cmovz   r9, rax
0x18009e398  lea     r8, [rsp+1C0h+var_148]
0x18009e39d  mov     cl, r14b
0x18009e3a0  call    AdjustOtherInterfaceMetrics
0x18009e3a5  mov     ebx, eax
0x18009e3a7  test    eax, eax
0x18009e3a9  jz      short loc_18009E3C0
0x18009e3ab  mov     edx, eax
0x18009e3ad  lea     rcx, aRasupdatedefau; "RasUpdateDefaultRouteSettings: AdjustOt"...
0x18009e3b4  jmp     loc_18009E596
0x18009e3b9  mov     dl, 1
0x18009e3bb  jmp     loc_18009E333
0x18009e3c0  test    r14b, r14b
0x18009e3c3  jz      short loc_18009E3E1
0x18009e3c5  mov     eax, cs:g_NumVpnIpv4RouteTableChanges
0x18009e3cb  test    sil, sil
0x18009e3ce  jz      short loc_18009E3D4
0x18009e3d0  inc     eax
0x18009e3d2  jmp     short loc_18009E3D6
0x18009e3d4  dec     eax
0x18009e3d6  mov     cs:g_NumVpnIpv4RouteTableChanges, eax
0x18009e3dc  jmp     loc_18009E59B
0x18009e3e1  test    sil, sil
0x18009e3e4  jz      short loc_18009E3F1
0x18009e3e6  inc     cs:g_NumVpnIpv6RouteTableChanges
0x18009e3ec  jmp     loc_18009E59B
0x18009e3f1  dec     cs:g_NumVpnIpv6RouteTableChanges
0x18009e3f7  jmp     loc_18009E59B
0x18009e3fc  mov     r12d, 4
0x18009e402  mov     [rsp+1C0h+hKey], r15
0x18009e407  lea     rax, [rsp+1C0h+hKey]
0x18009e40c  mov     [rsp+1C0h+Type], r12d
0x18009e411  mov     r9d, 20019h; samDesired
0x18009e417  mov     [rsp+1C0h+cbData], r12d
0x18009e41c  xor     r8d, r8d; ulOptions
0x18009e41f  mov     [rsp+1C0h+phkResult], rax; phkResult
0x18009e424  lea     rdx, aSystemCurrentc_17; "SYSTEM\\CurrentControlSet\\services\\Re"...
0x18009e42b  mov     dword ptr [rsp+1C0h+Data], r15d
0x18009e430  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009e437  call    cs:__imp_RegOpenKeyExA
0x18009e43e  nop     dword ptr [rax+rax+00h]
0x18009e443  mov     edi, eax
0x18009e445  test    eax, eax
0x18009e447  jnz     short loc_18009E496
0x18009e449  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18009e44e  lea     rax, [rsp+1C0h+cbData]
0x18009e453  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x18009e458  lea     r9, [rsp+1C0h+Type]; lpType
0x18009e45d  lea     rax, [rsp+1C0h+Data]
0x18009e462  xor     r8d, r8d; lpReserved
0x18009e465  lea     rdx, aDisabledefault_0; "DisableDefaultRouteHandling"
0x18009e46c  mov     [rsp+1C0h+phkResult], rax; lpData
0x18009e471  call    cs:__imp_RegQueryValueExA
0x18009e478  nop     dword ptr [rax+rax+00h]
0x18009e47d  mov     edi, eax
0x18009e47f  test    eax, eax
0x18009e481  jnz     short loc_18009E48A
0x18009e483  cmp     [rsp+1C0h+Type], r12d
0x18009e488  jz      short loc_18009E496
0x18009e48a  cmp     edi, 2
0x18009e48d  mov     dword ptr [rsp+1C0h+Data], r15d
0x18009e492  cmovz   edi, r15d
0x18009e496  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18009e49b  test    rcx, rcx
0x18009e49e  jz      short loc_18009E4AC
0x18009e4a0  call    cs:__imp_RegCloseKey
0x18009e4a7  nop     dword ptr [rax+rax+00h]
0x18009e4ac  test    edi, edi
0x18009e4ae  jnz     short loc_18009E4BB
0x18009e4b0  cmp     dword ptr [rsp+1C0h+Data], 1
0x18009e4b5  jz      loc_18009E5E0
0x18009e4bb  mov     r12d, 0F0h
0x18009e4c1  lea     rcx, [rbp+0C0h+var_130]; void *
0x18009e4c5  mov     r8d, r12d; Size
0x18009e4c8  xor     edx, edx; Val
0x18009e4ca  call    memset_0
0x18009e4cf  lea     rax, NPI_MS_IPV6_MODULEID
0x18009e4d6  mov     [rsp+1C0h+hKey], rbx
0x18009e4db  test    r14b, r14b
0x18009e4de  lea     rdi, NPI_MS_IPV4_MODULEID
0x18009e4e5  lea     r9, [rsp+1C0h+hKey]
0x18009e4ea  cmovz   rdi, rax
0x18009e4ee  lea     rax, [rbp+0C0h+var_130]
0x18009e4f2  mov     rdx, rdi
0x18009e4f5  mov     [rsp+1C0h+lpcbData], rax
0x18009e4fa  call    GetAllParameters
0x18009e4ff  mov     ebx, eax
0x18009e501  test    eax, eax
0x18009e503  jnz     loc_18009E58D
0x18009e509  mov     r8d, r12d; Size
0x18009e50c  lea     edx, [r12+0Fh]; Val
0x18009e511  lea     rcx, [rbp+0C0h+var_130]; void *
0x18009e515  call    memset_0
0x18009e51a  lea     rax, [rbp+0C0h+var_130]
0x18009e51e  mov     [rbp+0C0h+var_110], r15
0x18009e522  test    sil, sil
0x18009e525  mov     [rbp+0C0h+var_108], r15d
0x18009e529  lea     r9, [rsp+1C0h+hKey]
0x18009e52e  mov     [rbp+0C0h+var_B8], r15d
0x18009e532  mov     rdx, rdi
0x18009e535  mov     [rbp+0C0h+var_58], r15d
0x18009e539  setz    [rbp+0C0h+var_98]
0x18009e53d  mov     [rsp+1C0h+lpcbData], rax
0x18009e542  call    SetAllParameters
0x18009e547  mov     ebx, eax
0x18009e549  test    eax, eax
0x18009e54b  jnz     short loc_18009E58D
0x18009e54d  mov     r8d, r12d; Size
0x18009e550  lea     rcx, [rbp+0C0h+var_130]; void *
0x18009e554  xor     edx, edx; Val
0x18009e556  call    memset_0
0x18009e55b  lea     rax, [rbp+0C0h+var_130]
0x18009e55f  mov     rdx, rdi
0x18009e562  lea     r9, [rsp+1C0h+hKey]
0x18009e567  mov     [rsp+1C0h+lpcbData], rax
0x18009e56c  call    GetAllParameters
0x18009e571  mov     ebx, eax
0x18009e573  test    eax, eax
0x18009e575  jnz     short loc_18009E58D
0x18009e577  test    sil, sil
0x18009e57a  jz      short loc_18009E582
0x18009e57c  cmp     [rbp+0C0h+var_98], r15b
0x18009e580  jmp     short loc_18009E586
0x18009e582  cmp     [rbp+0C0h+var_98], 1
0x18009e586  jz      short loc_18009E5E0
0x18009e588  mov     ebx, 3EBh
0x18009e58d  mov     edx, ebx
0x18009e58f  lea     rcx, aRasupdatedefau_2; "RasUpdateDefaultRouteSettings: AdjustVP"...
0x18009e596  call    TraceMsg
0x18009e59b  lea     rcx, g_csInterfaceCache; lpCriticalSection
0x18009e5a2  call    cs:__imp_LeaveCriticalSection
0x18009e5a9  nop     dword ptr [rax+rax+00h]
0x18009e5ae  test    r14b, r14b
0x18009e5b1  jz      short loc_18009E601
0x18009e5b3  mov     eax, cs:g_NumVpnIpv4RouteTableChanges
0x18009e5b9  test    eax, eax
0x18009e5bb  jz      short loc_18009E5D7
0x18009e5bd  cmp     cs:g_hInterfaceChangeNotificationV4, r15
0x18009e5c4  jnz     short loc_18009E5D3
0x18009e5c6  mov     cl, 1
0x18009e5c8  call    RegisterInterfaceChangeNotifications
0x18009e5cd  mov     eax, cs:g_NumVpnIpv4RouteTableChanges
0x18009e5d3  test    eax, eax
0x18009e5d5  jnz     short loc_18009E633
0x18009e5d7  cmp     cs:g_hInterfaceChangeNotificationV4, r15
0x18009e5de  jmp     short loc_18009E62C
0x18009e5e0  lea     r8, [rsp+1C0h+var_148]
0x18009e5e5  mov     dl, sil
0x18009e5e8  mov     cl, r14b
0x18009e5eb  call    AdjustOtherInterfaceDefaultRoute
0x18009e5f0  mov     ebx, eax
0x18009e5f2  test    eax, eax
0x18009e5f4  jz      short loc_18009E59B
0x18009e5f6  mov     edx, eax
0x18009e5f8  lea     rcx, aRasupdatedefau_0; "RasUpdateDefaultRouteSettings: AdjustOt"...
0x18009e5ff  jmp     short loc_18009E596
0x18009e601  mov     eax, cs:g_NumVpnIpv6RouteTableChanges
0x18009e607  test    eax, eax
0x18009e609  jz      short loc_18009E625
0x18009e60b  cmp     cs:g_hInterfaceChangeNotificationV6, r15
0x18009e612  jnz     short loc_18009E621
0x18009e614  xor     ecx, ecx
0x18009e616  call    RegisterInterfaceChangeNotifications
0x18009e61b  mov     eax, cs:g_NumVpnIpv6RouteTableChanges
0x18009e621  test    eax, eax
0x18009e623  jnz     short loc_18009E633
0x18009e625  cmp     cs:g_hInterfaceChangeNotificationV6, r15
0x18009e62c  jz      short loc_18009E633
0x18009e62e  call    DeregisterInterfaceChangeNotifications
0x18009e633  mov     eax, ebx
0x18009e635  mov     rcx, [rbp+0C0h+var_40]
0x18009e63c  xor     rcx, rsp; StackCookie
0x18009e63f  call    __security_check_cookie
0x18009e644  add     rsp, 190h
0x18009e64b  pop     r15
0x18009e64d  pop     r14
0x18009e64f  pop     r12
0x18009e651  pop     rdi
0x18009e652  pop     rsi
0x18009e653  pop     rbx
0x18009e654  pop     rbp
0x18009e655  retn
```
