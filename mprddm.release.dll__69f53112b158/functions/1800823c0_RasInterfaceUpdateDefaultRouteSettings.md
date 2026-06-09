# RasInterfaceUpdateDefaultRouteSettings

- ea: `0x1800823c0`
- end: `0x180082789`
- name: `RasInterfaceUpdateDefaultRouteSettings`
- size: `969`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180014c90`

## callees

- `0x180078a34`
- `0x180078d24`
- `0x180079580`
- `0x18007f074`
- `0x180081e24`
- `0x1800823c0`
- `0x180082790`
- `0x1800828b4`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800826f5`
- `KERNEL32!LeaveCriticalSection` at `0x1800826f5`
- `KERNEL32!EnterCriticalSection` at `0x18008240d`
- `KERNEL32!EnterCriticalSection` at `0x18008240d`
- `ADVAPI32!RegCloseKey` at `0x1800825b0`
- `ADVAPI32!RegCloseKey` at `0x1800825b0`
- `ADVAPI32!RegOpenKeyExA` at `0x180082547`
- `ADVAPI32!RegOpenKeyExA` at `0x180082547`
- `ADVAPI32!RegQueryValueExA` at `0x180082581`
- `ADVAPI32!RegQueryValueExA` at `0x180082581`

## string_xrefs

- `0x180082534`: `SYSTEM\CurrentControlSet\services\RemoteAccess\Parameters\IKEV2`
- `0x180082478`: `RasUpdateDefaultRouteSettings(fIpv4:%u)(fSet:%u)(Luid:%I64X)(type:%s)(updateMetric: %s)`
- `0x1800824bc`: `RasUpdateDefaultRouteSettings: AdjustOtherInterfaceMetrics failed. Error %d`
- `0x1800826c1`: `RasUpdateDefaultRouteSettings: AdjustVPNInterfaceDefaultRoute failed. Error %d`
- `0x1800826e0`: `RasUpdateDefaultRouteSettings: AdjustOtherInterfaceDefaultRoute failed. Error %d`

## pseudocode

```c
__int64 __fastcall RasInterfaceUpdateDefaultRouteSettings(char a1, char a2, HKEY a3, char a4)
{
  char v6; // di
  HKEY *v9; // rax
  const char *v10; // rcx
  const char *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  LPVOID *v14; // r9
  unsigned int v15; // ebx
  const CHAR *v16; // rcx
  int v17; // eax
  __int64 v18; // rdx
  LSTATUS v19; // edi
  HKEY v20; // rcx
  char v21; // al
  int v22; // ecx
  int v23; // r8d
  const NPI_MODULEID *v24; // rdi
  unsigned int AllParameters; // eax
  int v26; // ecx
  int v27; // ecx
  int v28; // r8d
  __int64 v30; // rcx
  int v31; // eax
  bool v32; // zf
  int v33; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
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

  v6 = 0;
  v44 = 0;
  EnterCriticalSection(&g_csInterfaceCache);
  v43 = a3;
  v9 = (HKEY *)g_RasVpnLuids;
  if ( g_RasVpnLuids )
  {
    while ( *v9 != a3 )
    {
      v9 = (HKEY *)v9[2];
      if ( !v9 )
        goto LABEL_4;
    }
    v6 = 1;
  }
  else
  {
LABEL_4:
    *((_QWORD *)&v44 + 1) = g_RasVpnLuids;
  }
  v10 = "yes";
  if ( !a4 )
    v10 = "no";
  lpcbData = (LPDWORD)v10;
  v11 = "vpn";
  if ( !v6 )
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
    if ( v19 || (v21 = 1, *(_DWORD *)Data != 1) )
      v21 = 0;
    if ( !v21 )
    {
      memset_0(v45, 0, 0xF0u);
      hKey = a3;
      v24 = &NPI_MS_IPV4_MODULEID;
      if ( !a2 )
        v24 = &NPI_MS_IPV6_MODULEID;
      AllParameters = GetAllParameters(v22, (_DWORD)v24, v23, (unsigned int)&hKey, phkResulta, (__int64)v45);
      if ( !AllParameters )
      {
        memset_0(v45, 255, 0xF0u);
        v46 = 0;
        v49 = a1 == 0;
        v47 = 0;
        v48 = 0;
        v50 = 0;
        AllParameters = SetAllParameters(v26, (_DWORD)v24, 7, (unsigned int)&hKey, 8, (__int64)v45, 240, 0);
        if ( !AllParameters )
        {
          memset_0(v45, 0, 0xF0u);
          AllParameters = GetAllParameters(v27, (_DWORD)v24, v28, (unsigned int)&hKey, phkResultb, (__int64)v45);
          if ( !AllParameters && !(a1 ? !v49 : v49) )
          {
            v15 = 1003;
LABEL_45:
            v16 = "RasUpdateDefaultRouteSettings: AdjustVPNInterfaceDefaultRoute failed. Error %d";
            goto LABEL_48;
          }
        }
      }
      v15 = AllParameters;
      if ( AllParameters )
        goto LABEL_45;
    }
    LOBYTE(v18) = a1;
    LOBYTE(v20) = a2;
    v15 = AdjustOtherInterfaceDefaultRoute(v20, v18, &v43);
    if ( !v15 )
      goto LABEL_49;
    v16 = "RasUpdateDefaultRouteSettings: AdjustOtherInterfaceDefaultRoute failed. Error %d";
    goto LABEL_48;
  }
  v14 = &g_IpV4InterfaceTable;
  LOBYTE(v12) = a1;
  if ( !a2 )
    v14 = &g_IpV6InterfaceTable;
  LOBYTE(v13) = a2;
  v15 = AdjustOtherInterfaceMetrics(v13, v12, &v43, v14, phkResult, lpcbData);
  if ( v15 )
  {
    v16 = "RasUpdateDefaultRouteSettings: AdjustOtherInterfaceMetrics failed. Error %d";
LABEL_48:
    TraceMsg(v16);
    goto LABEL_49;
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
LABEL_49:
  LeaveCriticalSection(&g_csInterfaceCache);
  if ( a2 )
  {
    v31 = g_NumVpnIpv4RouteTableChanges;
    if ( !g_NumVpnIpv4RouteTableChanges )
      goto LABEL_54;
    if ( !g_hInterfaceChangeNotificationV4 )
    {
      LOBYTE(v30) = 1;
      RegisterInterfaceChangeNotifications(v30);
      v31 = g_NumVpnIpv4RouteTableChanges;
    }
    if ( !v31 )
    {
LABEL_54:
      v32 = g_hInterfaceChangeNotificationV4 == 0;
      goto LABEL_60;
    }
  }
  else
  {
    v33 = g_NumVpnIpv6RouteTableChanges;
    if ( !g_NumVpnIpv6RouteTableChanges )
      goto LABEL_59;
    if ( !g_hInterfaceChangeNotificationV6 )
    {
      RegisterInterfaceChangeNotifications(0);
      v33 = g_NumVpnIpv6RouteTableChanges;
    }
    if ( !v33 )
    {
LABEL_59:
      v32 = g_hInterfaceChangeNotificationV6 == 0;
LABEL_60:
      if ( !v32 )
        DeregisterInterfaceChangeNotifications();
    }
  }
  return v15;
}

```

## disassembly

```asm
0x1800823c0  push    rbp
0x1800823c2  push    rbx
0x1800823c3  push    rsi
0x1800823c4  push    rdi
0x1800823c5  push    r12
0x1800823c7  push    r14
0x1800823c9  push    r15
0x1800823cb  lea     rbp, [rsp-90h]
0x1800823d3  sub     rsp, 190h
0x1800823da  mov     rax, cs:__security_cookie
0x1800823e1  xor     rax, rsp
0x1800823e4  mov     [rbp+0C0h+var_40], rax
0x1800823eb  movzx   esi, cl
0x1800823ee  xorps   xmm0, xmm0
0x1800823f1  xor     r12d, r12d
0x1800823f4  movzx   r14d, dl
0x1800823f8  lea     rcx, g_csInterfaceCache; lpCriticalSection
0x1800823ff  mov     dil, r12b
0x180082402  movdqu  [rbp+0C0h+var_140], xmm0
0x180082407  mov     r15b, r9b
0x18008240a  mov     rbx, r8
0x18008240d  call    cs:__imp_EnterCriticalSection
0x180082414  nop     dword ptr [rax+rax+00h]
0x180082419  mov     rcx, cs:g_RasVpnLuids
0x180082420  mov     [rsp+1C0h+var_148], rbx
0x180082425  mov     rax, rcx
0x180082428  test    rcx, rcx
0x18008242b  jz      short loc_18008243F
0x18008242d  cmp     [rax], rbx
0x180082430  jz      loc_1800824C8
0x180082436  mov     rax, [rax+10h]
0x18008243a  test    rax, rax
0x18008243d  jnz     short loc_18008242D
0x18008243f  mov     qword ptr [rbp+0C0h+var_140+8], rcx
0x180082443  lea     rdx, aInternet; "internet"
0x18008244a  test    r15b, r15b
0x18008244d  lea     rax, aNo; "no"
0x180082454  mov     r8d, esi
0x180082457  lea     rcx, aYes; "yes"
0x18008245e  mov     r9, rbx
0x180082461  cmovz   rcx, rax
0x180082465  test    dil, dil
0x180082468  mov     [rsp+1C0h+lpcbData], rcx
0x18008246d  lea     rax, aVpn; "vpn"
0x180082474  cmovz   rax, rdx
0x180082478  lea     rcx, aRasupdatedefau_1; "RasUpdateDefaultRouteSettings(fIpv4:%u)"...
0x18008247f  mov     edx, r14d
0x180082482  mov     [rsp+1C0h+phkResult], rax
0x180082487  call    TraceMsg
0x18008248c  test    r15b, r15b
0x18008248f  jz      short loc_18008250C
0x180082491  lea     rax, g_IpV6InterfaceTable
0x180082498  test    r14b, r14b
0x18008249b  lea     r9, g_IpV4InterfaceTable
0x1800824a2  mov     dl, sil
0x1800824a5  cmovz   r9, rax
0x1800824a9  lea     r8, [rsp+1C0h+var_148]
0x1800824ae  mov     cl, r14b
0x1800824b1  call    AdjustOtherInterfaceMetrics
0x1800824b6  mov     ebx, eax
0x1800824b8  test    eax, eax
0x1800824ba  jz      short loc_1800824D0
0x1800824bc  lea     rcx, aRasupdatedefau; "RasUpdateDefaultRouteSettings: AdjustOt"...
0x1800824c3  jmp     loc_1800826E7
0x1800824c8  mov     dil, 1
0x1800824cb  jmp     loc_180082443
0x1800824d0  test    r14b, r14b
0x1800824d3  jz      short loc_1800824F1
0x1800824d5  mov     eax, cs:g_NumVpnIpv4RouteTableChanges
0x1800824db  test    sil, sil
0x1800824de  jz      short loc_1800824E4
0x1800824e0  inc     eax
0x1800824e2  jmp     short loc_1800824E6
0x1800824e4  dec     eax
0x1800824e6  mov     cs:g_NumVpnIpv4RouteTableChanges, eax
0x1800824ec  jmp     loc_1800826EE
0x1800824f1  test    sil, sil
0x1800824f4  jz      short loc_180082501
0x1800824f6  inc     cs:g_NumVpnIpv6RouteTableChanges
0x1800824fc  jmp     loc_1800826EE
0x180082501  dec     cs:g_NumVpnIpv6RouteTableChanges
0x180082507  jmp     loc_1800826EE
0x18008250c  mov     r15d, 4
0x180082512  mov     [rsp+1C0h+hKey], r12
0x180082517  lea     rax, [rsp+1C0h+hKey]
0x18008251c  mov     [rsp+1C0h+Type], r15d
0x180082521  mov     r9d, 20019h; samDesired
0x180082527  mov     [rsp+1C0h+cbData], r15d
0x18008252c  xor     r8d, r8d; ulOptions
0x18008252f  mov     [rsp+1C0h+phkResult], rax; phkResult
0x180082534  lea     rdx, aSystemCurrentc_20; "SYSTEM\\CurrentControlSet\\services\\Re"...
0x18008253b  mov     dword ptr [rsp+1C0h+Data], r12d
0x180082540  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180082547  call    cs:__imp_RegOpenKeyExA
0x18008254e  nop     dword ptr [rax+rax+00h]
0x180082553  mov     edi, eax
0x180082555  test    eax, eax
0x180082557  jnz     short loc_1800825A6
0x180082559  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18008255e  lea     rax, [rsp+1C0h+cbData]
0x180082563  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x180082568  lea     r9, [rsp+1C0h+Type]; lpType
0x18008256d  lea     rax, [rsp+1C0h+Data]
0x180082572  xor     r8d, r8d; lpReserved
0x180082575  lea     rdx, aDisabledefault; "DisableDefaultRouteHandling"
0x18008257c  mov     [rsp+1C0h+phkResult], rax; lpData
0x180082581  call    cs:__imp_RegQueryValueExA
0x180082588  nop     dword ptr [rax+rax+00h]
0x18008258d  mov     edi, eax
0x18008258f  test    eax, eax
0x180082591  jnz     short loc_18008259A
0x180082593  cmp     [rsp+1C0h+Type], r15d
0x180082598  jz      short loc_1800825A6
0x18008259a  cmp     edi, 2
0x18008259d  mov     dword ptr [rsp+1C0h+Data], r12d
0x1800825a2  cmovz   edi, r12d
0x1800825a6  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800825ab  test    rcx, rcx
0x1800825ae  jz      short loc_1800825BC
0x1800825b0  call    cs:__imp_RegCloseKey
0x1800825b7  nop     dword ptr [rax+rax+00h]
0x1800825bc  test    edi, edi
0x1800825be  jnz     short loc_1800825C9
0x1800825c0  cmp     dword ptr [rsp+1C0h+Data], 1
0x1800825c5  mov     al, 1
0x1800825c7  jz      short loc_1800825CC
0x1800825c9  mov     al, r12b
0x1800825cc  test    al, al
0x1800825ce  jnz     loc_1800826CA
0x1800825d4  mov     r15d, 0F0h
0x1800825da  lea     rcx, [rbp+0C0h+var_130]; void *
0x1800825de  mov     r8d, r15d; Size
0x1800825e1  xor     edx, edx; Val
0x1800825e3  call    memset_0
0x1800825e8  lea     rax, NPI_MS_IPV6_MODULEID
0x1800825ef  mov     [rsp+1C0h+hKey], rbx
0x1800825f4  test    r14b, r14b
0x1800825f7  lea     rdi, NPI_MS_IPV4_MODULEID
0x1800825fe  lea     r9, [rsp+1C0h+hKey]
0x180082603  cmovz   rdi, rax
0x180082607  lea     rax, [rbp+0C0h+var_130]
0x18008260b  mov     rdx, rdi
0x18008260e  mov     [rsp+1C0h+lpcbData], rax
0x180082613  call    GetAllParameters
0x180082618  test    eax, eax
0x18008261a  jnz     loc_1800826BB
0x180082620  mov     r8d, r15d; Size
0x180082623  lea     edx, [r15+0Fh]; Val
0x180082627  lea     rcx, [rbp+0C0h+var_130]; void *
0x18008262b  call    memset_0
0x180082630  mov     [rsp+1C0h+var_188], r12d
0x180082635  lea     rax, [rbp+0C0h+var_130]
0x180082639  mov     [rsp+1C0h+var_190], r15d
0x18008263e  lea     r9, [rsp+1C0h+hKey]
0x180082643  mov     [rsp+1C0h+lpcbData], rax
0x180082648  test    sil, sil
0x18008264b  mov     r8d, 7
0x180082651  mov     dword ptr [rsp+1C0h+phkResult], 8
0x180082659  mov     rdx, rdi
0x18008265c  mov     [rbp+0C0h+var_110], r12
0x180082660  setz    [rbp+0C0h+var_98]
0x180082664  mov     [rbp+0C0h+var_108], r12d
0x180082668  mov     [rbp+0C0h+var_B8], r12d
0x18008266c  mov     [rbp+0C0h+var_58], r12d
0x180082670  call    SetAllParameters
0x180082675  test    eax, eax
0x180082677  jnz     short loc_1800826BB
0x180082679  mov     r8d, r15d; Size
0x18008267c  lea     rcx, [rbp+0C0h+var_130]; void *
0x180082680  xor     edx, edx; Val
0x180082682  call    memset_0
0x180082687  lea     rax, [rbp+0C0h+var_130]
0x18008268b  mov     rdx, rdi
0x18008268e  lea     r9, [rsp+1C0h+hKey]
0x180082693  mov     [rsp+1C0h+lpcbData], rax
0x180082698  call    GetAllParameters
0x18008269d  test    eax, eax
0x18008269f  jnz     short loc_1800826BB
0x1800826a1  test    sil, sil
0x1800826a4  jz      short loc_1800826AC
0x1800826a6  cmp     [rbp+0C0h+var_98], r12b
0x1800826aa  jmp     short loc_1800826B0
0x1800826ac  cmp     [rbp+0C0h+var_98], 1
0x1800826b0  jz      short loc_1800826BB
0x1800826b2  mov     ebx, 3EBh
0x1800826b7  mov     eax, ebx
0x1800826b9  jmp     short loc_1800826C1
0x1800826bb  mov     ebx, eax
0x1800826bd  test    eax, eax
0x1800826bf  jz      short loc_1800826CA
0x1800826c1  lea     rcx, aRasupdatedefau_2; "RasUpdateDefaultRouteSettings: AdjustVP"...
0x1800826c8  jmp     short loc_1800826E7
0x1800826ca  lea     r8, [rsp+1C0h+var_148]
0x1800826cf  mov     dl, sil
0x1800826d2  mov     cl, r14b
0x1800826d5  call    AdjustOtherInterfaceDefaultRoute
0x1800826da  mov     ebx, eax
0x1800826dc  test    eax, eax
0x1800826de  jz      short loc_1800826EE
0x1800826e0  lea     rcx, aRasupdatedefau_0; "RasUpdateDefaultRouteSettings: AdjustOt"...
0x1800826e7  mov     edx, eax
0x1800826e9  call    TraceMsg
0x1800826ee  lea     rcx, g_csInterfaceCache; lpCriticalSection
0x1800826f5  call    cs:__imp_LeaveCriticalSection
0x1800826fc  nop     dword ptr [rax+rax+00h]
0x180082701  test    r14b, r14b
0x180082704  jz      short loc_180082733
0x180082706  mov     eax, cs:g_NumVpnIpv4RouteTableChanges
0x18008270c  test    eax, eax
0x18008270e  jz      short loc_18008272A
0x180082710  cmp     cs:g_hInterfaceChangeNotificationV4, r12
0x180082717  jnz     short loc_180082726
0x180082719  mov     cl, 1
0x18008271b  call    RegisterInterfaceChangeNotifications
0x180082720  mov     eax, cs:g_NumVpnIpv4RouteTableChanges
0x180082726  test    eax, eax
0x180082728  jnz     short loc_180082765
0x18008272a  cmp     cs:g_hInterfaceChangeNotificationV4, r12
0x180082731  jmp     short loc_18008275E
0x180082733  mov     eax, cs:g_NumVpnIpv6RouteTableChanges
0x180082739  test    eax, eax
0x18008273b  jz      short loc_180082757
0x18008273d  cmp     cs:g_hInterfaceChangeNotificationV6, r12
0x180082744  jnz     short loc_180082753
0x180082746  xor     ecx, ecx
0x180082748  call    RegisterInterfaceChangeNotifications
0x18008274d  mov     eax, cs:g_NumVpnIpv6RouteTableChanges
0x180082753  test    eax, eax
0x180082755  jnz     short loc_180082765
0x180082757  cmp     cs:g_hInterfaceChangeNotificationV6, r12
0x18008275e  jz      short loc_180082765
0x180082760  call    DeregisterInterfaceChangeNotifications
0x180082765  mov     eax, ebx
0x180082767  mov     rcx, [rbp+0C0h+var_40]
0x18008276e  xor     rcx, rsp; StackCookie
0x180082771  call    __security_check_cookie
0x180082776  add     rsp, 190h
0x18008277d  pop     r15
0x18008277f  pop     r14
0x180082781  pop     r12
0x180082783  pop     rdi
0x180082784  pop     rsi
0x180082785  pop     rbx
0x180082786  pop     rbp
0x180082787  retn
```
