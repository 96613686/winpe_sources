# RpcSrvEnableDhcpv6

- ea: `0x180009a70`
- end: `0x180009ef8`
- name: `RpcSrvEnableDhcpv6`
- size: `1160`
- prototype: `__int64 __fastcall(__int64, __int64 *, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001d8c`
- `0x180009a70`
- `0x180009f00`
- `0x180009f58`
- `0x18000a260`
- `0x18000a430`
- `0x18000a4c0`
- `0x18000b1e0`
- `0x18000bb2c`
- `0x18000dad8`
- `0x180019ad0`
- `0x18001a3ee`
- `0x18001be30`
- `0x1800337d0`
- `0x1800338c0`
- `0x1800340f8`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180009cb3`
- `ntdll!RtlNtStatusToDosError` at `0x180009cb3`
- `ntdll!RtlStringFromGUID` at `0x180009ca5`
- `ntdll!RtlStringFromGUID` at `0x180009ca5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009da0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009da0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009bc1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009ce3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009bc1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009ce3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009e6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009eb5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009e6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009eb5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180009e20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180009e20`
- `NSI!NsiGetAllParametersEx` at `0x180009c6c`
- `NSI!NsiGetAllParametersEx` at `0x180009c6c`

## string_xrefs

- `0x180009b96`: `System\CurrentControlSet\Services\Tcpip6\Parameters\Interfaces`

## pseudocode

```c
__int64 __fastcall RpcSrvEnableDhcpv6(__int64 a1, __int64 *a2, int a3)
{
  unsigned int v6; // esi
  CRpcWatchDog *v7; // rcx
  int v8; // r8d
  ULONG IsEnabledDHCPRegistryValue; // ebx
  HKEY v10; // rcx
  int IsWCOSSystem; // eax
  const WCHAR *v12; // rdx
  int v13; // edx
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  unsigned int AllParameters; // eax
  NTSTATUS v18; // eax
  const WCHAR *Buffer; // rcx
  __int64 *v20; // rdx
  CRpcWatchDog *v21; // rcx
  BYTE Data[8]; // [rsp+70h] [rbp-90h] BYREF
  HKEY v24; // [rsp+78h] [rbp-88h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp-80h] BYREF
  __int64 v26; // [rsp+88h] [rbp-78h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-70h] BYREF
  _UNICODE_STRING GuidString; // [rsp+98h] [rbp-68h] BYREF
  __int64 (__fastcall *v29)(); // [rsp+A8h] [rbp-58h] BYREF
  __int128 v30; // [rsp+B0h] [rbp-50h]
  __int64 v31; // [rsp+C0h] [rbp-40h]
  _BYTE v32[8]; // [rsp+D0h] [rbp-30h] BYREF
  int v33; // [rsp+D8h] [rbp-28h]
  const NPI_MODULEID *v34; // [rsp+E0h] [rbp-20h]
  int v35; // [rsp+E8h] [rbp-18h]
  __int64 v36; // [rsp+F0h] [rbp-10h]
  __int64 *v37; // [rsp+F8h] [rbp-8h]
  int v38; // [rsp+100h] [rbp+0h]
  __int64 v39; // [rsp+108h] [rbp+8h]
  int v40; // [rsp+110h] [rbp+10h]
  __int64 v41; // [rsp+118h] [rbp+18h]
  int v42; // [rsp+120h] [rbp+20h]
  _DWORD *v43; // [rsp+128h] [rbp+28h]
  int v44; // [rsp+130h] [rbp+30h]
  _DWORD v45[134]; // [rsp+140h] [rbp+40h] BYREF
  GUID Guid; // [rsp+358h] [rbp+258h] BYREF

  v24 = 0;
  phkResult = 0;
  hKey = 0;
  *(_DWORD *)Data = 0;
  GuidString = 0;
  memset_0(v45, 0, 0x238u);
  v26 = 0;
  v31 = 0;
  v29 = RpcSrvEnableDhcpv6;
  v30 = 0;
  v6 = 0;
  CRpcWatchDog::AddEntry(v7, (struct _WatchDogEntry *)&v29, v8);
  IsEnabledDHCPRegistryValue = RpcValidateRequests(a1, 4);
  if ( IsEnabledDHCPRegistryValue )
  {
LABEL_4:
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_D(1025, 53, WPP_fabc15bf7f653c75a8730223311145c5_Traceguids, IsEnabledDHCPRegistryValue);
    goto LABEL_6;
  }
  if ( !a2 )
  {
    IsEnabledDHCPRegistryValue = 87;
    goto LABEL_4;
  }
  if ( (unsigned int)Dhcpv6FindAndRefContext(a2, &v24) )
  {
    v26 = *a2;
    v24 = 0;
    IsWCOSSystem = DhcpIsWCOSSystem();
    v12 = L"OSDATA\\Networking\\Dhcp\\Client6";
    if ( !IsWCOSSystem )
      v12 = L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\Interfaces";
    IsEnabledDHCPRegistryValue = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v12, 0, 0x2001Bu, &hKey);
    if ( IsEnabledDHCPRegistryValue )
      goto LABEL_4;
    memset_0(v32, 0, 0x68u);
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_qqLqLLLLdd(v14, v13, v15, v16, (char)&NPI_MS_NDIS_MODULEID, 1, (char)&v26, 8, 0, 0, 56);
    v33 = 0;
    v37 = &v26;
    v34 = &NPI_MS_NDIS_MODULEID;
    v43 = v45;
    v35 = 1;
    v38 = 8;
    v39 = 0;
    v40 = 0;
    v41 = 0;
    v42 = 0;
    v44 = 568;
    v36 = 1;
    AllParameters = NsiGetAllParametersEx(v32);
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_D(1028, 11, WPP_427c3a8e92a933594072e65998df1ebc_Traceguids, AllParameters);
    v18 = RtlStringFromGUID(&Guid, &GuidString);
    IsEnabledDHCPRegistryValue = RtlNtStatusToDosError(v18);
    if ( IsEnabledDHCPRegistryValue )
      goto LABEL_4;
    IsEnabledDHCPRegistryValue = RegOpenKeyExW(hKey, GuidString.Buffer, 0, 0x2001Bu, &phkResult);
    if ( IsEnabledDHCPRegistryValue )
      goto LABEL_4;
    Buffer = GuidString.Buffer;
  }
  else
  {
    if ( !v24 )
    {
      IsEnabledDHCPRegistryValue = 87;
      goto LABEL_6;
    }
    phkResult = (HKEY)*((_QWORD *)v24 + 81);
    Buffer = (const WCHAR *)*((_QWORD *)v24 + 7);
  }
  IsEnabledDHCPRegistryValue = DhcpV6IsEnabledDHCPRegistryValue(Buffer);
  if ( IsEnabledDHCPRegistryValue )
  {
    if ( IsEnabledDHCPRegistryValue != 2 )
      goto LABEL_6;
    IsEnabledDHCPRegistryValue = 0;
    if ( a3 )
      goto LABEL_6;
  }
  else if ( !a3 )
  {
    IsEnabledDHCPRegistryValue = 0;
    goto LABEL_6;
  }
  if ( v24 )
    v6 = *((_DWORD *)v24 + 12);
  else
    v6 = v45[0];
  *(_DWORD *)Data = a3 != 0;
  IsEnabledDHCPRegistryValue = RegSetValueExW(phkResult, L"EnableDhcp", 0, 4u, Data, 4u);
  if ( IsEnabledDHCPRegistryValue )
    goto LABEL_4;
  if ( !v24 )
    goto LABEL_39;
  IsEnabledDHCPRegistryValue = LockDhcpContext(v24, 1);
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_S(1028, 51, WPP_fabc15bf7f653c75a8730223311145c5_Traceguids, *((_QWORD *)v24 + 7));
  if ( IsEnabledDHCPRegistryValue )
    goto LABEL_4;
  Dhcpv6SetMode(v24, *((unsigned int *)v24 + 2236));
  ReleaseSemaphore(*((HANDLE *)v24 + 73), 1, 0);
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_S(1028, 52, WPP_fabc15bf7f653c75a8730223311145c5_Traceguids, *((_QWORD *)v24 + 7));
LABEL_6:
  v10 = v24;
  if ( v24 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 4, 0xFFFFFFFF) == 1 )
      Dhcpv6DestroyContextEx(v24);
    v24 = 0;
    goto LABEL_41;
  }
LABEL_39:
  v10 = phkResult;
  if ( phkResult )
    RegCloseKey(phkResult);
LABEL_41:
  if ( a3 )
  {
    if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) == 0 )
      goto LABEL_47;
    v20 = EnableDhcpV6;
  }
  else
  {
    if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) == 0 )
      goto LABEL_47;
    v20 = DisableDhcpV6;
  }
  McTemplateU0qq_EtwEventWriteTransfer(v10, v20, v6, IsEnabledDHCPRegistryValue);
LABEL_47:
  v21 = (CRpcWatchDog *)hKey;
  if ( hKey )
    RegCloseKey(hKey);
  CRpcWatchDog::RemoveEntry(v21, (struct _WatchDogEntry *)&v29);
  return IsEnabledDHCPRegistryValue;
}

```

## disassembly

```asm
0x180009a70  mov     [rsp-8+arg_10], rbx
0x180009a75  mov     [rsp-8+arg_18], rsi
0x180009a7a  push    rbp
0x180009a7b  push    rdi
0x180009a7c  push    r12
0x180009a7e  push    r14
0x180009a80  push    r15
0x180009a82  lea     rbp, [rsp-290h]
0x180009a8a  sub     rsp, 390h
0x180009a91  mov     rax, cs:__security_cookie
0x180009a98  xor     rax, rsp
0x180009a9b  mov     [rbp+2B0h+var_30], rax
0x180009aa2  xor     r15d, r15d
0x180009aa5  mov     r14d, r8d
0x180009aa8  mov     rdi, rdx
0x180009aab  mov     [rsp+3B0h+var_338], r15
0x180009ab0  mov     rbx, rcx
0x180009ab3  mov     [rbp+2B0h+var_330], r15
0x180009ab7  xorps   xmm0, xmm0
0x180009aba  mov     [rbp+2B0h+hKey], r15
0x180009abe  xor     edx, edx; Val
0x180009ac0  mov     dword ptr [rsp+3B0h+Data], r15d
0x180009ac5  mov     r8d, 238h; Size
0x180009acb  lea     rcx, [rbp+2B0h+var_270]; void *
0x180009acf  movups  xmmword ptr [rbp+2B0h+GuidString.Length], xmm0
0x180009ad3  call    memset_0
0x180009ad8  xorps   xmm0, xmm0
0x180009adb  mov     [rbp+2B0h+var_328], r15
0x180009adf  lea     rax, RpcSrvEnableDhcpv6
0x180009ae6  mov     [rbp+2B0h+var_2F0], r15
0x180009aea  lea     rdx, [rbp+2B0h+var_308]; struct _WatchDogEntry *
0x180009aee  mov     [rbp+2B0h+var_308], rax
0x180009af2  movdqu  [rbp+2B0h+var_300], xmm0
0x180009af7  mov     esi, r15d
0x180009afa  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x180009aff  lea     edx, [r15+4]
0x180009b03  mov     rcx, rbx
0x180009b06  call    RpcValidateRequests
0x180009b0b  lea     r12d, [r15+1]
0x180009b0f  mov     ebx, eax
0x180009b11  test    eax, eax
0x180009b13  jnz     short loc_180009B1D
0x180009b15  test    rdi, rdi
0x180009b18  jnz     short loc_180009B6E
0x180009b1a  lea     ebx, [rax+57h]
0x180009b1d  test    byte ptr cs:xmmword_1800423E0, 2
0x180009b24  jz      short loc_180009B3F
0x180009b26  mov     edx, 35h ; '5'
0x180009b2b  lea     r8, WPP_fabc15bf7f653c75a8730223311145c5_Traceguids
0x180009b32  mov     ecx, 401h
0x180009b37  mov     r9d, ebx
0x180009b3a  call    WPP_SF_D
0x180009b3f  mov     rcx, [rsp+3B0h+var_338]
0x180009b44  test    rcx, rcx
0x180009b47  jz      loc_180009E65
0x180009b4d  or      eax, 0FFFFFFFFh
0x180009b50  lock xadd [rcx+10h], eax
0x180009b55  cmp     eax, r12d
0x180009b58  jnz     short loc_180009B64
0x180009b5a  mov     rcx, [rsp+3B0h+var_338]
0x180009b5f  call    Dhcpv6DestroyContextEx
0x180009b64  mov     [rsp+3B0h+var_338], r15
0x180009b69  jmp     loc_180009E7A
0x180009b6e  lea     rdx, [rsp+3B0h+var_338]
0x180009b73  mov     rcx, rdi
0x180009b76  call    Dhcpv6FindAndRefContext
0x180009b7b  test    eax, eax
0x180009b7d  jz      loc_180009CFF
0x180009b83  mov     rax, [rdi]
0x180009b86  mov     [rbp+2B0h+var_328], rax
0x180009b8a  mov     [rsp+3B0h+var_338], r15
0x180009b8f  call    DhcpIsWCOSSystem
0x180009b94  test    eax, eax
0x180009b96  lea     rcx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Tc"...
0x180009b9d  lea     rax, [rbp+2B0h+hKey]
0x180009ba1  mov     r9d, 2001Bh; samDesired
0x180009ba7  lea     rdx, aOsdataNetworki_1; "OSDATA\\Networking\\Dhcp\\Client6"
0x180009bae  mov     [rsp+3B0h+phkResult], rax; phkResult
0x180009bb3  cmovz   rdx, rcx; lpSubKey
0x180009bb7  xor     r8d, r8d; ulOptions
0x180009bba  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009bc1  call    cs:__imp_RegOpenKeyExW
0x180009bc8  nop     dword ptr [rax+rax+00h]
0x180009bcd  mov     ebx, eax
0x180009bcf  test    eax, eax
0x180009bd1  jnz     loc_180009B1D
0x180009bd7  xor     edx, edx; Val
0x180009bd9  lea     r8d, [rax+68h]; Size
0x180009bdd  lea     rcx, [rbp+2B0h+var_2E0]; void *
0x180009be1  call    memset_0
0x180009be6  test    byte ptr cs:xmmword_1800423E0, 10h
0x180009bed  lea     rdi, NPI_MS_NDIS_MODULEID
0x180009bf4  mov     ebx, 8
0x180009bf9  jz      short loc_180009C2E
0x180009bfb  mov     [rsp+3B0h+var_350], r15d
0x180009c00  lea     rax, [rbp+2B0h+var_328]
0x180009c04  mov     [rsp+3B0h+var_360], 238h
0x180009c0c  mov     [rsp+3B0h+var_368], r15d
0x180009c11  mov     [rsp+3B0h+var_370], r15d
0x180009c16  mov     [rsp+3B0h+var_378], ebx
0x180009c1a  mov     [rsp+3B0h+var_380], rax
0x180009c1f  mov     [rsp+3B0h+cbData], r12d
0x180009c24  mov     [rsp+3B0h+phkResult], rdi
0x180009c29  call    WPP_SF_qqLqLLLLdd
0x180009c2e  lea     rax, [rbp+2B0h+var_328]
0x180009c32  mov     [rbp+2B0h+var_2D8], r15d
0x180009c36  mov     [rbp+2B0h+var_2B8], rax
0x180009c3a  lea     rcx, [rbp+2B0h+var_2E0]
0x180009c3e  lea     rax, [rbp+2B0h+var_270]
0x180009c42  mov     [rbp+2B0h+var_2D0], rdi
0x180009c46  mov     [rbp+2B0h+var_288], rax
0x180009c4a  mov     [rbp+2B0h+var_2C8], r12d
0x180009c4e  mov     [rbp+2B0h+var_2B0], ebx
0x180009c51  mov     [rbp+2B0h+var_2A8], r15
0x180009c55  mov     [rbp+2B0h+var_2A0], r15d
0x180009c59  mov     [rbp+2B0h+var_298], r15
0x180009c5d  mov     [rbp+2B0h+var_290], r15d
0x180009c61  mov     [rbp+2B0h+var_280], 238h
0x180009c68  mov     [rbp+2B0h+var_2C0], r12
0x180009c6c  call    cs:__imp_NsiGetAllParametersEx
0x180009c73  nop     dword ptr [rax+rax+00h]
0x180009c78  test    byte ptr cs:xmmword_1800423E0, 10h
0x180009c7f  jz      short loc_180009C9A
0x180009c81  mov     edx, 0Bh
0x180009c86  lea     r8, WPP_427c3a8e92a933594072e65998df1ebc_Traceguids
0x180009c8d  mov     ecx, 404h
0x180009c92  mov     r9d, eax
0x180009c95  call    WPP_SF_D
0x180009c9a  lea     rdx, [rbp+2B0h+GuidString]; GuidString
0x180009c9e  lea     rcx, [rbp+2B0h+Guid]; Guid
0x180009ca5  call    cs:__imp_RtlStringFromGUID
0x180009cac  nop     dword ptr [rax+rax+00h]
0x180009cb1  mov     ecx, eax; Status
0x180009cb3  call    cs:__imp_RtlNtStatusToDosError
0x180009cba  nop     dword ptr [rax+rax+00h]
0x180009cbf  mov     ebx, eax
0x180009cc1  test    eax, eax
0x180009cc3  jnz     loc_180009B1D
0x180009cc9  mov     rdx, [rbp+2B0h+GuidString.Buffer]; lpSubKey
0x180009ccd  lea     rax, [rbp+2B0h+var_330]
0x180009cd1  mov     rcx, [rbp+2B0h+hKey]; hKey
0x180009cd5  mov     r9d, 2001Bh; samDesired
0x180009cdb  xor     r8d, r8d; ulOptions
0x180009cde  mov     [rsp+3B0h+phkResult], rax; phkResult
0x180009ce3  call    cs:__imp_RegOpenKeyExW
0x180009cea  nop     dword ptr [rax+rax+00h]
0x180009cef  mov     ebx, eax
0x180009cf1  test    eax, eax
0x180009cf3  jnz     loc_180009B1D
0x180009cf9  mov     rcx, [rbp+2B0h+GuidString.Buffer]
0x180009cfd  jmp     short loc_180009D1C
0x180009cff  mov     rcx, [rsp+3B0h+var_338]
0x180009d04  test    rcx, rcx
0x180009d07  jz      loc_180009E5B
0x180009d0d  mov     rax, [rcx+288h]
0x180009d14  mov     [rbp+2B0h+var_330], rax
0x180009d18  mov     rcx, [rcx+38h]; LPCWSTR
0x180009d1c  lea     rdx, [rsp+3B0h+Data]
0x180009d21  call    DhcpV6IsEnabledDHCPRegistryValue
0x180009d26  mov     ebx, eax
0x180009d28  test    eax, eax
0x180009d2a  jnz     short loc_180009D49
0x180009d2c  test    r14d, r14d
0x180009d2f  jz      short loc_180009D40
0x180009d31  cmp     dword ptr [rsp+3B0h+Data], r15d
0x180009d36  jz      short loc_180009D5E
0x180009d38  mov     ebx, r15d
0x180009d3b  jmp     loc_180009B3F
0x180009d40  cmp     dword ptr [rsp+3B0h+Data], r15d
0x180009d45  jnz     short loc_180009D5E
0x180009d47  jmp     short loc_180009D38
0x180009d49  cmp     ebx, 2
0x180009d4c  jnz     loc_180009B3F
0x180009d52  mov     ebx, r15d
0x180009d55  test    r14d, r14d
0x180009d58  jnz     loc_180009B3F
0x180009d5e  mov     rax, [rsp+3B0h+var_338]
0x180009d63  test    rax, rax
0x180009d66  jz      short loc_180009D6D
0x180009d68  mov     esi, [rax+30h]
0x180009d6b  jmp     short loc_180009D70
0x180009d6d  mov     esi, [rbp+2B0h+var_270]
0x180009d70  mov     rcx, [rbp+2B0h+var_330]; hKey
0x180009d74  lea     rdx, aEnabledhcp; "EnableDhcp"
0x180009d7b  mov     eax, r15d
0x180009d7e  mov     r9d, 4; dwType
0x180009d84  mov     [rsp+3B0h+cbData], r9d; cbData
0x180009d89  test    r14d, r14d
0x180009d8c  setnz   al
0x180009d8f  xor     r8d, r8d; Reserved
0x180009d92  mov     dword ptr [rsp+3B0h+Data], eax
0x180009d96  lea     rax, [rsp+3B0h+Data]
0x180009d9b  mov     [rsp+3B0h+phkResult], rax; lpData
0x180009da0  call    cs:__imp_RegSetValueExW
0x180009da7  nop     dword ptr [rax+rax+00h]
0x180009dac  mov     ebx, eax
0x180009dae  test    eax, eax
0x180009db0  jnz     loc_180009B1D
0x180009db6  mov     rcx, [rsp+3B0h+var_338]
0x180009dbb  test    rcx, rcx
0x180009dbe  jz      loc_180009E65
0x180009dc4  mov     edx, r12d
0x180009dc7  call    LockDhcpContext
0x180009dcc  mov     ebx, eax
0x180009dce  test    byte ptr cs:xmmword_1800423E0, 10h
0x180009dd5  jz      short loc_180009DF6
0x180009dd7  mov     r9, [rsp+3B0h+var_338]
0x180009ddc  lea     r8, WPP_fabc15bf7f653c75a8730223311145c5_Traceguids
0x180009de3  mov     edx, 33h ; '3'
0x180009de8  mov     ecx, 404h
0x180009ded  mov     r9, [r9+38h]
0x180009df1  call    WPP_SF_S
0x180009df6  test    ebx, ebx
0x180009df8  jnz     loc_180009B1D
0x180009dfe  mov     rcx, [rsp+3B0h+var_338]
0x180009e03  mov     edx, [rcx+22F0h]
0x180009e09  call    Dhcpv6SetMode
0x180009e0e  mov     rcx, [rsp+3B0h+var_338]
0x180009e13  xor     r8d, r8d; lpPreviousCount
0x180009e16  mov     edx, r12d; lReleaseCount
0x180009e19  mov     rcx, [rcx+248h]; hSemaphore
0x180009e20  call    cs:__imp_ReleaseSemaphore
0x180009e27  nop     dword ptr [rax+rax+00h]
0x180009e2c  test    byte ptr cs:xmmword_1800423E0, 10h
0x180009e33  jz      loc_180009B3F
0x180009e39  mov     r9, [rsp+3B0h+var_338]
0x180009e3e  lea     edx, [rbx+34h]
0x180009e41  mov     ecx, 404h
0x180009e46  lea     r8, WPP_fabc15bf7f653c75a8730223311145c5_Traceguids
0x180009e4d  mov     r9, [r9+38h]
0x180009e51  call    WPP_SF_S
0x180009e56  jmp     loc_180009B3F
0x180009e5b  mov     ebx, 57h ; 'W'
0x180009e60  jmp     loc_180009B3F
0x180009e65  mov     rcx, [rbp+2B0h+var_330]; hKey
0x180009e69  test    rcx, rcx
0x180009e6c  jz      short loc_180009E7A
0x180009e6e  call    cs:__imp_RegCloseKey
0x180009e75  nop     dword ptr [rax+rax+00h]
0x180009e7a  test    r14d, r14d
0x180009e7d  jz      short loc_180009E91
0x180009e7f  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, r12b
0x180009e86  jz      short loc_180009EAC
0x180009e88  lea     rdx, EnableDhcpV6
0x180009e8f  jmp     short loc_180009EA1
0x180009e91  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, r12b
0x180009e98  jz      short loc_180009EAC
0x180009e9a  lea     rdx, DisableDhcpV6
0x180009ea1  mov     r9d, ebx
0x180009ea4  mov     r8d, esi
0x180009ea7  call    McTemplateU0qq_EtwEventWriteTransfer
0x180009eac  mov     rcx, [rbp+2B0h+hKey]; hKey
0x180009eb0  test    rcx, rcx
0x180009eb3  jz      short loc_180009EC1
0x180009eb5  call    cs:__imp_RegCloseKey
0x180009ebc  nop     dword ptr [rax+rax+00h]
0x180009ec1  lea     rdx, [rbp+2B0h+var_308]; struct _WatchDogEntry *
0x180009ec5  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x180009eca  mov     eax, ebx
0x180009ecc  mov     rcx, [rbp+2B0h+var_30]
0x180009ed3  xor     rcx, rsp; StackCookie
0x180009ed6  call    __security_check_cookie
0x180009edb  lea     r11, [rsp+3B0h+var_20]
0x180009ee3  mov     rbx, [r11+40h]
0x180009ee7  mov     rsi, [r11+48h]
0x180009eeb  mov     rsp, r11
0x180009eee  pop     r15
0x180009ef0  pop     r14
0x180009ef2  pop     r12
0x180009ef4  pop     rdi
0x180009ef5  pop     rbp
0x180009ef6  retn
```
