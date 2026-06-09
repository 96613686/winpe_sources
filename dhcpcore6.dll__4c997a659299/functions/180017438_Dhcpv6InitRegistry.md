# Dhcpv6InitRegistry

- ea: `0x180017438`
- end: `0x18001773b`
- name: `Dhcpv6InitRegistry`
- size: `771`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001b808`

## callees

- `0x180009f58`
- `0x180017438`
- `0x180017744`
- `0x18002a274`
- `0x180032994`
- `0x1800337d0`
- `0x180033970`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800174ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800174ed`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180017546`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180017546`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800175b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017694`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800175b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017694`

## pseudocode

```c
LSTATUS __fastcall Dhcpv6InitRegistry(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int i; // ebx
  REGSAM v5; // r9d
  LSTATUS result; // eax
  unsigned int v7; // edi
  __int64 v8; // rsi
  const WCHAR *v9; // rbx
  LSTATUS v10; // eax
  int v11; // r8d
  _DWORD *v12; // rcx
  unsigned int v13; // edi
  __int64 v14; // rsi
  const WCHAR *v15; // rbx
  int v16; // r8d
  __int64 v17; // rdx
  __int64 v18; // rcx
  _DWORD *v19; // rcx
  int Data; // [rsp+80h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+38h] BYREF
  DWORD Type; // [rsp+90h] [rbp+40h] BYREF

  Type = 0;
  cbData = 0;
  Data = 0;
  if ( (unsigned int)DhcpIsWCOSSystem(a1, a2, a3, a4) )
  {
    DhcpRecreateWcosKeys();
    off_1800420B8 = L"OSDATA\\Networking\\Dhcp\\Client6\\Parameters";
    off_1800420D8 = (wchar_t *)L"OSDATA\\Networking\\Dhcp\\Client6";
    off_1800420E8 = L"OSDATA\\Networking\\Dhcp\\Client6\\Parameters\\Options";
  }
  for ( i = 0; i < 4; ++i )
  {
    v5 = 13;
    if ( &Dhcpv6GlobalParametersKey != (HKEY *)off_1800420B0[2 * i] )
      v5 = 15;
    result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, (&off_1800420B8)[2 * i], 0, v5, (PHKEY)off_1800420B0[2 * i]);
    if ( result )
    {
      if ( (HKEY *)off_1800420B0[2 * i] != &Dhcpv6GlobalInterfacesKey )
        return result;
      result = RegCreateKeyExW(
                 Dhcpv6GlobalTcpipParametersKey,
                 L"Interfaces",
                 0,
                 0,
                 1u,
                 0xFu,
                 0,
                 &Dhcpv6GlobalInterfacesKey,
                 0);
      if ( result )
        return result;
    }
  }
  v7 = 0;
  if ( &Dhcpv6GlobalUseMHAsyncDns )
  {
    do
    {
      v8 = 2LL * v7;
      cbData = 4;
      ++v7;
      v9 = (&off_180036038)[v8];
      v10 = RegQueryValueExW(Dhcpv6GlobalTcpipParametersKey, v9, 0, &Type, (LPBYTE)&Data, &cbData);
      if ( v10 )
      {
        if ( (xmmword_1800423E0 & 2) != 0 )
          WPP_SF_SD(1025, 63, (unsigned int)WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, (_DWORD)v9, v10);
      }
      else if ( Type == 4 )
      {
        v12 = (_DWORD *)*((_QWORD *)&off_180036030 + v8);
        *v12 = Data;
        if ( (xmmword_1800423E0 & 0x10) != 0 )
          WPP_SF_SlD((_DWORD)v12, 65, v11, (_DWORD)v9, Data, Data);
      }
      else if ( (xmmword_1800423E0 & 0x10) != 0 )
      {
        WPP_SF_S(1028, 64, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, v9);
      }
    }
    while ( *((_QWORD *)&off_180036030 + 2 * v7) );
  }
  v13 = 0;
  if ( &Dhcpv6GlobalDisableDs )
  {
    do
    {
      v14 = 2LL * v13;
      cbData = 4;
      ++v13;
      v15 = (&off_180036008)[v14];
      if ( RegQueryValueExW(Dhcpv6GlobalParametersKey, v15, 0, &Type, (LPBYTE)&Data, &cbData) )
      {
        if ( (xmmword_1800423E0 & 2) != 0 )
        {
          v17 = 66;
          v18 = 1025;
LABEL_25:
          WPP_SF_S(v18, v17, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, v15);
        }
      }
      else
      {
        if ( Type == 4 )
        {
          v19 = (_DWORD *)*((_QWORD *)&off_180036000 + v14);
          *v19 = Data;
          if ( (xmmword_1800423E0 & 0x10) != 0 )
            WPP_SF_SlD((_DWORD)v19, 68, v16, (_DWORD)v15, Data, Data);
          continue;
        }
        if ( (xmmword_1800423E0 & 0x10) != 0 )
        {
          v17 = 67;
          v18 = 1028;
          goto LABEL_25;
        }
      }
    }
    while ( *((_QWORD *)&off_180036000 + 2 * v13) );
  }
  return Dhcpv6RegReadOptionDefList();
}

```

## disassembly

```asm
0x180017438  mov     [rsp-28h+arg_18], rbx
0x18001743d  push    rbp
0x18001743e  push    rsi
0x18001743f  push    rdi
0x180017440  push    r13
0x180017442  push    r15
0x180017444  mov     rbp, rsp
0x180017447  sub     rsp, 50h
0x18001744b  mov     [rbp+Type], 0
0x180017452  mov     [rbp+cbData], 0
0x180017459  mov     [rbp+Data], 0
0x180017460  call    DhcpIsWCOSSystem
0x180017465  test    eax, eax
0x180017467  jz      short loc_180017498
0x180017469  call    DhcpRecreateWcosKeys
0x18001746e  lea     rax, aOsdataNetworki_3; "OSDATA\\Networking\\Dhcp\\Client6\\Para"...
0x180017475  mov     cs:off_1800420B8, rax; "System\\CurrentControlSet\\Services\\Dh"...
0x18001747c  lea     rax, aOsdataNetworki_1; "OSDATA\\Networking\\Dhcp\\Client6"
0x180017483  mov     cs:off_1800420D8, rax; "System\\CurrentControlSet\\Services\\Tc"...
0x18001748a  lea     rax, aOsdataNetworki_2; "OSDATA\\Networking\\Dhcp\\Client6\\Para"...
0x180017491  mov     cs:off_1800420E8, rax; "System\\CurrentControlSet\\Services\\Dh"...
0x180017498  xor     ebx, ebx
0x18001749a  lea     r15, __ImageBase
0x1800174a1  mov     r13, 0FFFFFFFF80000002h
0x1800174a8  lea     rsi, Dhcpv6GlobalInterfacesKey
0x1800174af  cmp     ebx, 4
0x1800174b2  jge     loc_180017561
0x1800174b8  xor     r8d, r8d; ulOptions
0x1800174bb  movsxd  rdi, ebx
0x1800174be  add     rdi, rdi
0x1800174c1  lea     rcx, Dhcpv6GlobalParametersKey
0x1800174c8  lea     r9d, [r8+0Dh]
0x1800174cc  mov     rax, rva off_1800420B0[r15+rdi*8]
0x1800174d4  mov     rdx, rva off_1800420B8[r15+rdi*8]; lpSubKey
0x1800174dc  cmp     rcx, rax
0x1800174df  mov     rcx, r13; hKey
0x1800174e2  mov     [rsp+50h+phkResult], rax; phkResult
0x1800174e7  jz      short loc_1800174ED
0x1800174e9  lea     r9d, [r8+0Fh]; samDesired
0x1800174ed  call    cs:__imp_RegOpenKeyExW
0x1800174f4  nop     dword ptr [rax+rax+00h]
0x1800174f9  test    eax, eax
0x1800174fb  jz      short loc_18001755A
0x1800174fd  cmp     rva off_1800420B0[r15+rdi*8], rsi
0x180017505  jnz     loc_180017726
0x18001750b  mov     rcx, cs:Dhcpv6GlobalTcpipParametersKey; hKey
0x180017512  lea     rdx, aInterfaces; "Interfaces"
0x180017519  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x180017522  xor     r9d, r9d; lpClass
0x180017525  mov     [rsp+50h+var_18], rsi; phkResult
0x18001752a  xor     r8d, r8d; Reserved
0x18001752d  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180017536  mov     [rsp+50h+samDesired], 0Fh; samDesired
0x18001753e  mov     dword ptr [rsp+50h+phkResult], 1; dwOptions
0x180017546  call    cs:__imp_RegCreateKeyExW
0x18001754d  nop     dword ptr [rax+rax+00h]
0x180017552  test    eax, eax
0x180017554  jnz     loc_180017726
0x18001755a  inc     ebx
0x18001755c  jmp     loc_1800174AF
0x180017561  xor     edi, edi
0x180017563  lea     r13, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18001756a  cmp     cs:off_180036030, rdi
0x180017571  jz      loc_18001764C
0x180017577  mov     rcx, cs:Dhcpv6GlobalTcpipParametersKey; hKey
0x18001757e  lea     rax, [rbp+cbData]
0x180017582  mov     qword ptr [rsp+50h+samDesired], rax; lpcbData
0x180017587  lea     r9, [rbp+Type]; lpType
0x18001758b  mov     esi, edi
0x18001758d  lea     rax, [rbp+Data]
0x180017591  add     rsi, rsi
0x180017594  mov     [rbp+cbData], 4
0x18001759b  xor     r8d, r8d; lpReserved
0x18001759e  mov     [rsp+50h+phkResult], rax; lpData
0x1800175a3  inc     edi
0x1800175a5  mov     rbx, ds:rva off_180036038[r15+rsi*8]; "Dhcpv6UseMHAsyncDns" ...
0x1800175ad  mov     rdx, rbx; lpValueName
0x1800175b0  call    cs:__imp_RegQueryValueExW
0x1800175b7  nop     dword ptr [rax+rax+00h]
0x1800175bc  test    eax, eax
0x1800175be  jz      short loc_1800175E4
0x1800175c0  test    byte ptr cs:xmmword_1800423E0, 2
0x1800175c7  jz      short loc_180017638
0x1800175c9  mov     edx, 3Fh ; '?'
0x1800175ce  mov     dword ptr [rsp+50h+phkResult], eax
0x1800175d2  mov     ecx, 401h
0x1800175d7  mov     r9, rbx
0x1800175da  mov     r8, r13
0x1800175dd  call    WPP_SF_SD
0x1800175e2  jmp     short loc_180017638
0x1800175e4  cmp     [rbp+Type], 4
0x1800175e8  jz      short loc_18001760A
0x1800175ea  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800175f1  jz      short loc_180017638
0x1800175f3  mov     edx, 40h ; '@'
0x1800175f8  mov     ecx, 404h
0x1800175fd  mov     r9, rbx
0x180017600  mov     r8, r13
0x180017603  call    WPP_SF_S
0x180017608  jmp     short loc_180017638
0x18001760a  mov     rcx, ds:rva off_180036030[r15+rsi*8]
0x180017612  mov     eax, [rbp+Data]
0x180017615  mov     [rcx], eax
0x180017617  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001761e  jz      short loc_180017638
0x180017620  mov     eax, [rbp+Data]
0x180017623  mov     edx, 41h ; 'A'
0x180017628  mov     [rsp+50h+samDesired], eax
0x18001762c  mov     r9, rbx
0x18001762f  mov     dword ptr [rsp+50h+phkResult], eax
0x180017633  call    WPP_SF_SlD
0x180017638  mov     eax, edi
0x18001763a  add     rax, rax
0x18001763d  cmp     ds:rva off_180036030[r15+rax*8], 0
0x180017646  jnz     loc_180017577
0x18001764c  xor     edi, edi
0x18001764e  cmp     cs:off_180036000, rdi
0x180017655  jz      loc_180017721
0x18001765b  mov     rcx, cs:Dhcpv6GlobalParametersKey; hKey
0x180017662  lea     rax, [rbp+cbData]
0x180017666  mov     qword ptr [rsp+50h+samDesired], rax; lpcbData
0x18001766b  lea     r9, [rbp+Type]; lpType
0x18001766f  mov     esi, edi
0x180017671  lea     rax, [rbp+Data]
0x180017675  add     rsi, rsi
0x180017678  mov     [rbp+cbData], 4
0x18001767f  xor     r8d, r8d; lpReserved
0x180017682  mov     [rsp+50h+phkResult], rax; lpData
0x180017687  inc     edi
0x180017689  mov     rbx, ds:rva off_180036008[r15+rsi*8]; "DisableDisconnectedStandby" ...
0x180017691  mov     rdx, rbx; lpValueName
0x180017694  call    cs:__imp_RegQueryValueExW
0x18001769b  nop     dword ptr [rax+rax+00h]
0x1800176a0  test    eax, eax
0x1800176a2  jz      short loc_1800176C4
0x1800176a4  test    byte ptr cs:xmmword_1800423E0, 2
0x1800176ab  jz      short loc_18001770D
0x1800176ad  mov     edx, 42h ; 'B'
0x1800176b2  mov     ecx, 401h
0x1800176b7  mov     r9, rbx
0x1800176ba  mov     r8, r13
0x1800176bd  call    WPP_SF_S
0x1800176c2  jmp     short loc_18001770D
0x1800176c4  cmp     [rbp+Type], 4
0x1800176c8  jz      short loc_1800176DF
0x1800176ca  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800176d1  jz      short loc_18001770D
0x1800176d3  mov     edx, 43h ; 'C'
0x1800176d8  mov     ecx, 404h
0x1800176dd  jmp     short loc_1800176B7
0x1800176df  mov     rcx, ds:rva off_180036000[r15+rsi*8]
0x1800176e7  mov     eax, [rbp+Data]
0x1800176ea  mov     [rcx], eax
0x1800176ec  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800176f3  jz      short loc_18001770D
0x1800176f5  mov     eax, [rbp+Data]
0x1800176f8  mov     edx, 44h ; 'D'
0x1800176fd  mov     [rsp+50h+samDesired], eax
0x180017701  mov     r9, rbx
0x180017704  mov     dword ptr [rsp+50h+phkResult], eax
0x180017708  call    WPP_SF_SlD
0x18001770d  mov     eax, edi
0x18001770f  add     rax, rax
0x180017712  cmp     ds:rva off_180036000[r15+rax*8], 0
0x18001771b  jnz     loc_18001765B
0x180017721  call    Dhcpv6RegReadOptionDefList
0x180017726  mov     rbx, [rsp+50h+arg_18]
0x18001772e  add     rsp, 50h
0x180017732  pop     r15
0x180017734  pop     r13
0x180017736  pop     rdi
0x180017737  pop     rsi
0x180017738  pop     rbp
0x180017739  retn
```
