# DhcpInitRegistry

- ea: `0x18003619c`
- end: `0x180036490`
- name: `DhcpInitRegistry`
- size: `756`
- prototype: `LSTATUS()`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021420`

## callees

- `0x1800069d0`
- `0x180011454`
- `0x18001500c`
- `0x180019cf0`
- `0x18001a840`
- `0x18003619c`
- `0x18003655c`
- `0x18004b8a0`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004d200`
- `0x18004dd28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036240`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036240`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003630b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800363d5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003630b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800363d5`

## pseudocode

```c
LSTATUS DhcpInitRegistry()
{
  unsigned int i; // ebx
  REGSAM v1; // r9d
  LSTATUS result; // eax
  int BooleanDwordValue; // eax
  unsigned int v4; // edi
  __int64 v5; // rsi
  const WCHAR *v6; // rbx
  int v7; // r8d
  __int64 v8; // rdx
  _DWORD *v9; // rcx
  unsigned int v10; // edi
  __int64 v11; // rsi
  const WCHAR *v12; // rbx
  int v13; // r8d
  __int64 v14; // rdx
  _DWORD *v15; // rcx
  unsigned int inited; // eax
  int Data; // [rsp+60h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+38h] BYREF
  DWORD Type; // [rsp+70h] [rbp+40h] BYREF

  Type = 0;
  cbData = 0;
  Data = 0;
  if ( (unsigned int)DhcpIsWCOSSystem() )
  {
    DhcpRecreateWcosKeys();
    off_180061118 = L"OSDATA\\Networking\\Dhcp\\Client4\\Parameters";
    off_180061128 = (wchar_t *)L"OSDATA\\Networking\\Dhcp\\Client4";
    off_180061148 = L"OSDATA\\Networking\\Dhcp\\Client4\\Parameters\\Options";
  }
  for ( i = 0; (int)i < 4; ++i )
  {
    v1 = 13;
    if ( &DhcpGlobalParametersKey != (HKEY *)off_180061110[2 * i] )
      v1 = 15;
    result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, (&off_180061118)[2 * i], 0, v1, (PHKEY)off_180061110[2 * i]);
    if ( result )
      return result;
  }
  if ( g_fUseIpv6OnlyPreferred )
    DhcpRefreshGlobalIpv6OnlyPreferredEnabled();
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 105, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids);
  BooleanDwordValue = DhcpRegQueryBooleanDwordValue(DhcpGlobalParametersKey, L"DhcpOnlySpecifyInterfaceOnBroadcast");
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_Dd(
      1028,
      106,
      WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids,
      (unsigned int)Dhcpv4OnlySpecifyInterfaceOnBroadcastEnabled,
      BooleanDwordValue);
  v4 = 0;
  if ( &DhcpGlobalUseMHAsyncDns )
  {
    do
    {
      v5 = 2LL * v4;
      cbData = 4;
      ++v4;
      v6 = (&off_1800529A8)[v5];
      if ( RegQueryValueExW(DhcpGlobalTcpipParametersKey, v6, 0, &Type, (LPBYTE)&Data, &cbData) )
      {
        if ( (xmmword_1800616A0 & 2) != 0 )
        {
          v8 = 18;
LABEL_18:
          WPP_SF_S(1025, v8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, v6);
        }
      }
      else
      {
        if ( Type == 4 )
        {
          v9 = (_DWORD *)*((_QWORD *)&off_1800529A0 + v5);
          *v9 = Data;
          if ( (xmmword_1800616A0 & 0x10) != 0 )
            WPP_SF_SlD((_DWORD)v9, 20, v7, (_DWORD)v6, Data, Data);
          continue;
        }
        if ( (xmmword_1800616A0 & 2) != 0 )
        {
          v8 = 19;
          goto LABEL_18;
        }
      }
    }
    while ( *((_QWORD *)&off_1800529A0 + 2 * v4) );
  }
  v10 = 0;
  if ( &DhcpGlobalCompartmentAware )
  {
    do
    {
      v11 = 2LL * v10;
      cbData = 4;
      ++v10;
      v12 = (&off_180052978)[v11];
      if ( RegQueryValueExW(DhcpGlobalParametersKey, v12, 0, &Type, (LPBYTE)&Data, &cbData) )
      {
        if ( (xmmword_1800616A0 & 2) != 0 )
        {
          v14 = 21;
LABEL_29:
          WPP_SF_S(1025, v14, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, v12);
        }
      }
      else
      {
        if ( Type == 4 )
        {
          v15 = (_DWORD *)*((_QWORD *)&off_180052970 + v11);
          *v15 = Data;
          if ( (xmmword_1800616A0 & 0x10) != 0 )
            WPP_SF_SlD((_DWORD)v15, 23, v13, (_DWORD)v12, Data, Data);
          continue;
        }
        if ( (xmmword_1800616A0 & 2) != 0 )
        {
          v14 = 22;
          goto LABEL_29;
        }
      }
    }
    while ( *((_QWORD *)&off_180052970 + 2 * v10) );
  }
  inited = DhcpInitGlobalForceBroadcastList();
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 24, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, inited);
  return DhcpRegReadOptionDefList();
}

```

## disassembly

```asm
0x18003619c  mov     [rsp-28h+arg_18], rbx
0x1800361a1  push    rbp
0x1800361a2  push    rsi
0x1800361a3  push    rdi
0x1800361a4  push    r12
0x1800361a6  push    r15
0x1800361a8  mov     rbp, rsp
0x1800361ab  sub     rsp, 30h
0x1800361af  mov     [rbp+Type], 0
0x1800361b6  mov     [rbp+cbData], 0
0x1800361bd  mov     [rbp+Data], 0
0x1800361c4  call    DhcpIsWCOSSystem
0x1800361c9  test    eax, eax
0x1800361cb  jz      short loc_1800361FC
0x1800361cd  call    DhcpRecreateWcosKeys
0x1800361d2  lea     rax, aOsdataNetworki_3; "OSDATA\\Networking\\Dhcp\\Client4\\Para"...
0x1800361d9  mov     cs:off_180061118, rax; "System\\CurrentControlSet\\Services\\Dh"...
0x1800361e0  lea     rax, aOsdataNetworki; "OSDATA\\Networking\\Dhcp\\Client4"
0x1800361e7  mov     cs:off_180061128, rax; "System\\CurrentControlSet\\Services\\Tc"...
0x1800361ee  lea     rax, aOsdataNetworki_8; "OSDATA\\Networking\\Dhcp\\Client4\\Para"...
0x1800361f5  mov     cs:off_180061148, rax; "System\\CurrentControlSet\\Services\\Dh"...
0x1800361fc  xor     ebx, ebx
0x1800361fe  lea     r12, __ImageBase
0x180036205  mov     rdi, 0FFFFFFFF80000002h
0x18003620c  xor     r8d, r8d; ulOptions
0x18003620f  mov     eax, ebx
0x180036211  add     rax, rax
0x180036214  lea     r9d, [r8+0Dh]
0x180036218  mov     rcx, rva off_180061110[r12+rax*8]
0x180036220  mov     rdx, rva off_180061118[r12+rax*8]; lpSubKey
0x180036228  lea     rax, DhcpGlobalParametersKey
0x18003622f  cmp     rax, rcx
0x180036232  mov     [rsp+30h+phkResult], rcx; phkResult
0x180036237  mov     rcx, rdi; hKey
0x18003623a  jz      short loc_180036240
0x18003623c  lea     r9d, [r8+0Fh]; samDesired
0x180036240  call    cs:__imp_RegOpenKeyExW
0x180036246  test    eax, eax
0x180036248  jnz     loc_18003647F
0x18003624e  inc     ebx
0x180036250  cmp     ebx, 4
0x180036253  jl      short loc_18003620C
0x180036255  cmp     cs:g_fUseIpv6OnlyPreferred, eax
0x18003625b  jz      short loc_180036262
0x18003625d  call    DhcpRefreshGlobalIpv6OnlyPreferredEnabled
0x180036262  test    byte ptr cs:xmmword_1800616A0, 10h
0x180036269  lea     r15, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180036270  mov     ebx, 404h
0x180036275  jz      short loc_180036286
0x180036277  mov     edx, 69h ; 'i'
0x18003627c  mov     ecx, ebx
0x18003627e  mov     r8, r15
0x180036281  call    WPP_SF_
0x180036286  mov     rcx, cs:DhcpGlobalParametersKey; hKey
0x18003628d  lea     r8, Dhcpv4OnlySpecifyInterfaceOnBroadcastEnabled
0x180036294  lea     rdx, aDhcponlyspecif; "DhcpOnlySpecifyInterfaceOnBroadcast"
0x18003629b  call    DhcpRegQueryBooleanDwordValue
0x1800362a0  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800362a7  jz      short loc_1800362C3
0x1800362a9  mov     r9d, cs:Dhcpv4OnlySpecifyInterfaceOnBroadcastEnabled
0x1800362b0  mov     edx, 6Ah ; 'j'
0x1800362b5  mov     ecx, ebx
0x1800362b7  mov     dword ptr [rsp+30h+phkResult], eax
0x1800362bb  mov     r8, r15
0x1800362be  call    WPP_SF_Dd
0x1800362c3  xor     edi, edi
0x1800362c5  cmp     cs:off_1800529A0, rdi
0x1800362cc  jz      loc_18003638D
0x1800362d2  mov     rcx, cs:DhcpGlobalTcpipParametersKey; hKey
0x1800362d9  lea     rax, [rbp+cbData]
0x1800362dd  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800362e2  lea     r9, [rbp+Type]; lpType
0x1800362e6  mov     esi, edi
0x1800362e8  lea     rax, [rbp+Data]
0x1800362ec  add     rsi, rsi
0x1800362ef  mov     [rbp+cbData], 4
0x1800362f6  xor     r8d, r8d; lpReserved
0x1800362f9  mov     [rsp+30h+phkResult], rax; lpData
0x1800362fe  inc     edi
0x180036300  mov     rbx, ds:rva off_1800529A8[r12+rsi*8]; "UseMHAsyncDns" ...
0x180036308  mov     rdx, rbx; lpValueName
0x18003630b  call    cs:__imp_RegQueryValueExW
0x180036311  test    eax, eax
0x180036313  jz      short loc_180036335
0x180036315  test    byte ptr cs:xmmword_1800616A0, 2
0x18003631c  jz      short loc_180036379
0x18003631e  mov     edx, 12h
0x180036323  mov     ecx, 401h
0x180036328  mov     r9, rbx
0x18003632b  mov     r8, r15
0x18003632e  call    WPP_SF_S
0x180036333  jmp     short loc_180036379
0x180036335  cmp     [rbp+Type], 4
0x180036339  jz      short loc_18003634B
0x18003633b  test    byte ptr cs:xmmword_1800616A0, 2
0x180036342  jz      short loc_180036379
0x180036344  mov     edx, 13h
0x180036349  jmp     short loc_180036323
0x18003634b  mov     rcx, ds:rva off_1800529A0[r12+rsi*8]
0x180036353  mov     eax, [rbp+Data]
0x180036356  mov     [rcx], eax
0x180036358  test    byte ptr cs:xmmword_1800616A0, 10h
0x18003635f  jz      short loc_180036379
0x180036361  mov     eax, [rbp+Data]
0x180036364  mov     edx, 14h
0x180036369  mov     dword ptr [rsp+30h+lpcbData], eax
0x18003636d  mov     r9, rbx
0x180036370  mov     dword ptr [rsp+30h+phkResult], eax
0x180036374  call    WPP_SF_SlD
0x180036379  mov     eax, edi
0x18003637b  add     rax, rax
0x18003637e  cmp     ds:rva off_1800529A0[r12+rax*8], 0
0x180036387  jnz     loc_1800362D2
0x18003638d  xor     edi, edi
0x18003638f  cmp     cs:off_180052970, rdi
0x180036396  jz      loc_180036457
0x18003639c  mov     rcx, cs:DhcpGlobalParametersKey; hKey
0x1800363a3  lea     rax, [rbp+cbData]
0x1800363a7  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800363ac  lea     r9, [rbp+Type]; lpType
0x1800363b0  mov     esi, edi
0x1800363b2  lea     rax, [rbp+Data]
0x1800363b6  add     rsi, rsi
0x1800363b9  mov     [rbp+cbData], 4
0x1800363c0  xor     r8d, r8d; lpReserved
0x1800363c3  mov     [rsp+30h+phkResult], rax; lpData
0x1800363c8  inc     edi
0x1800363ca  mov     rbx, ds:rva off_180052978[r12+rsi*8]; "CompartmentAware" ...
0x1800363d2  mov     rdx, rbx; lpValueName
0x1800363d5  call    cs:__imp_RegQueryValueExW
0x1800363db  test    eax, eax
0x1800363dd  jz      short loc_1800363FF
0x1800363df  test    byte ptr cs:xmmword_1800616A0, 2
0x1800363e6  jz      short loc_180036443
0x1800363e8  mov     edx, 15h
0x1800363ed  mov     ecx, 401h
0x1800363f2  mov     r9, rbx
0x1800363f5  mov     r8, r15
0x1800363f8  call    WPP_SF_S
0x1800363fd  jmp     short loc_180036443
0x1800363ff  cmp     [rbp+Type], 4
0x180036403  jz      short loc_180036415
0x180036405  test    byte ptr cs:xmmword_1800616A0, 2
0x18003640c  jz      short loc_180036443
0x18003640e  mov     edx, 16h
0x180036413  jmp     short loc_1800363ED
0x180036415  mov     rcx, ds:rva off_180052970[r12+rsi*8]
0x18003641d  mov     eax, [rbp+Data]
0x180036420  mov     [rcx], eax
0x180036422  test    byte ptr cs:xmmword_1800616A0, 10h
0x180036429  jz      short loc_180036443
0x18003642b  mov     eax, [rbp+Data]
0x18003642e  mov     edx, 17h
0x180036433  mov     dword ptr [rsp+30h+lpcbData], eax
0x180036437  mov     r9, rbx
0x18003643a  mov     dword ptr [rsp+30h+phkResult], eax
0x18003643e  call    WPP_SF_SlD
0x180036443  mov     eax, edi
0x180036445  add     rax, rax
0x180036448  cmp     ds:rva off_180052970[r12+rax*8], 0
0x180036451  jnz     loc_18003639C
0x180036457  call    DhcpInitGlobalForceBroadcastList
0x18003645c  test    byte ptr cs:xmmword_1800616A0, 10h
0x180036463  jz      short loc_18003647A
0x180036465  mov     edx, 18h
0x18003646a  mov     ecx, 404h
0x18003646f  mov     r9d, eax
0x180036472  mov     r8, r15
0x180036475  call    WPP_SF_D
0x18003647a  call    DhcpRegReadOptionDefList
0x18003647f  mov     rbx, [rsp+30h+arg_18]
0x180036484  add     rsp, 30h
0x180036488  pop     r15
0x18003648a  pop     r12
0x18003648c  pop     rdi
0x18003648d  pop     rsi
0x18003648e  pop     rbp
0x18003648f  retn
```
