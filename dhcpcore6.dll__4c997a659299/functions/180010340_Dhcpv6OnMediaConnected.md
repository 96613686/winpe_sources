# Dhcpv6OnMediaConnected

- ea: `0x180010340`
- end: `0x1800108e9`
- name: `Dhcpv6OnMediaConnected`
- size: `1449`
- prototype: `__int64 __fastcall(NET_LUID *InterfaceLuid)`
- caller_count: `3`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d340`
- `0x18000d90c`
- `0x18001ed84`

## callees

- `0x180001bb8`
- `0x180001ca4`
- `0x180001d8c`
- `0x180004b30`
- `0x180004c3c`
- `0x180006468`
- `0x18000b350`
- `0x18000bb2c`
- `0x18000d6ac`
- `0x18000dad8`
- `0x18000e000`
- `0x18000ed18`
- `0x180010088`
- `0x180010340`
- `0x18001260c`
- `0x180014e18`
- `0x180019ad0`
- `0x18001a3ee`
- `0x18001be30`
- `0x18002f3c4`
- `0x180031008`
- `0x1800337d0`
- `0x1800338c0`
- `0x180033970`
- `0x180033b88`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010821`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010821`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001056d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001056d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180010751`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180010751`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001044d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001044d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800104ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001073e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800104ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001073e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800107d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800107d4`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x1800103ff`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x1800103ff`

## pseudocode

```c
__int64 __fastcall Dhcpv6OnMediaConnected(NET_LUID *InterfaceLuid)
{
  ULONG v2; // ecx
  ULONG64 Value; // rax
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int NsiForRASettings; // edi
  RTL_SRWLOCK *Dhcpv6ContextOnNicList; // rax
  _QWORD *v8; // rcx
  RTL_SRWLOCK *v9; // rbx
  unsigned int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  LSTATUS v13; // edi
  __int64 v14; // r9
  __int64 v15; // r8
  char IsInitState; // al
  int v17; // edx
  int v18; // r8d
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  BYTE lpData[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v24; // [rsp+44h] [rbp-BCh] BYREF
  ULONG InterfaceIndex; // [rsp+48h] [rbp-B8h] BYREF
  int Ptr_high; // [rsp+4Ch] [rbp-B4h] BYREF
  int Ptr; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  DWORD Type; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[4]; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD v31; // [rsp+60h] [rbp-A0h] BYREF
  RTL_SRWLOCK *v32; // [rsp+68h] [rbp-98h] BYREF
  int v33; // [rsp+70h] [rbp-90h] BYREF
  int v34; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v35; // [rsp+78h] [rbp-88h] BYREF
  __int64 v36; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v37[12]; // [rsp+90h] [rbp-70h] BYREF
  int v38; // [rsp+9Ch] [rbp-64h]
  ULONG v39; // [rsp+A0h] [rbp-60h]
  RTL_SRWLOCK *v40; // [rsp+B0h] [rbp-50h]
  __int64 v41; // [rsp+B8h] [rbp-48h]
  int *p_Ptr; // [rsp+C0h] [rbp-40h]
  __int64 v43; // [rsp+C8h] [rbp-38h]
  int *p_Ptr_high; // [rsp+D0h] [rbp-30h]
  __int64 v45; // [rsp+D8h] [rbp-28h]
  int *v46; // [rsp+E0h] [rbp-20h]
  __int64 v47; // [rsp+E8h] [rbp-18h]
  RTL_SRWLOCK *v48; // [rsp+F0h] [rbp-10h]
  __int64 v49; // [rsp+F8h] [rbp-8h]
  UUID *v50; // [rsp+100h] [rbp+0h]
  __int64 v51; // [rsp+108h] [rbp+8h]
  int *v52; // [rsp+110h] [rbp+10h]
  __int64 v53; // [rsp+118h] [rbp+18h]
  int *v54; // [rsp+120h] [rbp+20h]
  __int64 v55; // [rsp+128h] [rbp+28h]
  RTL_SRWLOCK **v56; // [rsp+130h] [rbp+30h]
  __int64 v57; // [rsp+138h] [rbp+38h]
  __int64 *v58; // [rsp+140h] [rbp+40h]
  __int64 v59; // [rsp+148h] [rbp+48h]

  cbData = 0;
  *(_DWORD *)Data = 0;
  Type = 0;
  *(_DWORD *)lpData = 0;
  LOWORD(v24) = 0;
  memset_0(v37, 0, 0x140u);
  v2 = 0;
  Ptr = 0;
  InterfaceIndex = 0;
  Ptr_high = 0;
  v36 = 0;
  v31 = 0;
  if ( (xmmword_1800423E0 & 2) != 0 )
  {
    WPP_SF_J(1025, 138, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, InterfaceLuid->Value);
    v2 = InterfaceIndex;
  }
  Value = InterfaceLuid->Value;
  v39 = v2;
  v49 = Value;
  v38 = 78;
  TraceLogEx(v37);
  ConvertInterfaceLuidToIndex(InterfaceLuid, &InterfaceIndex);
  if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(v4, MediaConnect, InterfaceIndex);
  NsiForRASettings = Dhcpv6QueryNsiForRASettings(InterfaceLuid);
  if ( NsiForRASettings )
    goto LABEL_43;
  EnterCriticalSection(&Dhcpv6GlobalNicListCritSect);
  Dhcpv6ContextOnNicList = (RTL_SRWLOCK *)FindDhcpv6ContextOnNicList(InterfaceLuid);
  v32 = Dhcpv6ContextOnNicList;
  v9 = Dhcpv6ContextOnNicList;
  if ( Dhcpv6ContextOnNicList )
  {
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_J(1028, 139, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, Dhcpv6ContextOnNicList[3].Ptr);
  }
  else
  {
    v10 = Dhcpv6AddNICtoListEx(v8, &v32);
    v9 = v32;
    NsiForRASettings = v10;
    if ( v32 && (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
      McTemplateU0qq_EtwEventWriteTransfer(v8, InterfaceAdded, LODWORD(v32[6].Ptr), v10);
    if ( NsiForRASettings )
    {
      LeaveCriticalSection(&Dhcpv6GlobalNicListCritSect);
      if ( NsiForRASettings != -1 && (Microsoft_Windows_DHCPv6_ClientEnableBits & 8) != 0 )
        McTemplateU0q_EtwEventWriteTransfer(v5, InitNetworkInterfaceFailed, NsiForRASettings);
LABEL_43:
      if ( (xmmword_1800423E0 & 2) != 0 )
        WPP_SF_D(1025, 144, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, NsiForRASettings);
      if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
        McTemplateU0q_EtwEventWriteTransfer(v5, ErrorMediaConnected, NsiForRASettings);
      TraceLogErrorv6(0, NsiForRASettings, 37);
      return NsiForRASettings;
    }
  }
  if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 0x20) != 0 )
  {
    McTemplateU0b16q_EtwEventWriteTransfer(v8, PerftrackDHCPv6MediaConnectEnd, &v9[4], LODWORD(v9[6].Ptr));
    if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 0x20) != 0 )
      McTemplateU0b16q_EtwEventWriteTransfer(v11, PerftrackDHCPv6MediaConnect, &v9[4], LODWORD(v9[6].Ptr));
  }
  cbData = 4;
  v13 = RegQueryValueExW((HKEY)v9[81].Ptr, L"Dhcpv6StartState", 0, &Type, Data, &cbData);
  if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(v12, MediaConnect, InterfaceIndex);
  TraceLogErrorv6(v9, 0, 78);
  if ( v13 || Type != 4 )
  {
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_SD(
        1025,
        140,
        (unsigned int)WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids,
        (unsigned int)L"Dhcpv6StartState",
        v13);
    v15 = (unsigned __int16)v24;
  }
  else
  {
    v15 = *(unsigned int *)Data;
  }
  *(_DWORD *)lpData = v15;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
  {
    IsInitState = Dhcpv6IsInitState(v9);
    WPP_SF_S_guid_Lld((_DWORD)v9 + 32, v17, v18, v9[7].Ptr, (__int64)&v9[4], (char)v9[6].Ptr, IsInitState, v18);
  }
  if ( (unsigned int)dword_180042048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180042048, 0x400000000000LL, v15, v14) )
  {
    v41 = 16;
    v40 = v9 + 4;
    Ptr = (int)v9[6].Ptr;
    p_Ptr = &Ptr;
    v43 = 4;
    Ptr_high = HIDWORD(v9[11].Ptr);
    p_Ptr_high = &Ptr_high;
    v45 = 4;
    v24 = (int)v9[12].Ptr;
    v46 = &v24;
    v48 = v9 + 1142;
    v50 = &Dhcpv6GlobalBootGuid;
    v47 = 4;
    v49 = 16;
    v51 = 16;
    v33 = Dhcpv6IsInitState(v9);
    v53 = 4;
    v52 = &v33;
    v34 = *(_DWORD *)&Dhcpv6GlobalUseNetworkHint;
    v54 = &v34;
    LODWORD(v32) = *(_DWORD *)lpData;
    v56 = &v32;
    v58 = &v35;
    v55 = 4;
    v57 = 4;
    v35 = 0x1000000;
    v59 = 8;
    tlgWriteTransfer_EtwEventWriteTransfer(v19, (unsigned int)byte_18003C2B9, v20, v21, 12, (__int64)v37);
  }
  _InterlockedIncrement((volatile signed __int32 *)&v9[2]);
  LeaveCriticalSection(&Dhcpv6GlobalNicListCritSect);
  QueryPerformanceCounter((LARGE_INTEGER *)&v9[1125]);
  if ( *(_DWORD *)&Dhcpv6GlobalUseNetworkHint )
  {
    NsiForRASettings = LockDhcpContext(v9, 1);
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_S(1028, 142, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, v9[7].Ptr);
    if ( NsiForRASettings )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v9[2], 0xFFFFFFFF) == 1 )
        Dhcpv6DestroyContextEx(v9);
      goto LABEL_43;
    }
    Dhcpv6GetCachedNetwork(v9, *(unsigned int *)lpData);
    ReleaseSemaphore(v9[73].Ptr, 1, 0);
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_S(1028, 143, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, v9[7].Ptr);
  }
  NsiForRASettings = RegSetValueExW((HKEY)v9[81].Ptr, L"Dhcpv6State", 0, 4u, lpData, 4u);
  Dhcpv6ReadSavedConfigurations((HKEY)v9[81].Ptr, &v36, &v31);
  LODWORD(v9[1124].Ptr) = v31;
  HIDWORD(v9[1127].Ptr) = 1;
  Dhcpv6SetMode(v9, *(unsigned int *)lpData);
  DhcpRefreshDnrEnabledState();
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v9[2], 0xFFFFFFFF) == 1 )
    Dhcpv6DestroyContextEx(v9);
  if ( NsiForRASettings )
    goto LABEL_43;
  return NsiForRASettings;
}

```

## disassembly

```asm
0x180010340  push    rbp
0x180010342  push    rbx
0x180010343  push    rsi
0x180010344  push    rdi
0x180010345  push    r12
0x180010347  push    r14
0x180010349  lea     rbp, [rsp-0E8h]
0x180010351  sub     rsp, 1E8h
0x180010358  mov     rax, cs:__security_cookie
0x18001035f  xor     rax, rsp
0x180010362  mov     [rbp+110h+var_40], rax
0x180010369  xor     r14d, r14d
0x18001036c  mov     rsi, rcx
0x18001036f  lea     rcx, [rbp+110h+var_180]; void *
0x180010373  mov     [rsp+210h+cbData], r14d
0x180010378  xor     edx, edx; Val
0x18001037a  mov     dword ptr [rsp+210h+Data], r14d
0x18001037f  mov     r8d, 140h; Size
0x180010385  mov     [rsp+210h+Type], r14d
0x18001038a  mov     dword ptr [rsp+210h+var_1D0], r14d
0x18001038f  mov     word ptr [rsp+210h+var_1CC], r14w
0x180010395  call    memset_0
0x18001039a  mov     ecx, r14d
0x18001039d  mov     [rsp+210h+var_1C0], r14d
0x1800103a2  mov     [rsp+210h+InterfaceIndex], ecx
0x1800103a6  mov     [rsp+210h+var_1C4], r14d
0x1800103ab  mov     [rbp+110h+var_190], r14
0x1800103af  mov     [rsp+210h+var_1B0], r14d
0x1800103b4  test    byte ptr cs:xmmword_1800423E0, 2
0x1800103bb  lea     r12, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x1800103c2  jz      short loc_1800103DD
0x1800103c4  mov     r9, [rsi]
0x1800103c7  mov     edx, 8Ah
0x1800103cc  mov     ecx, 401h
0x1800103d1  mov     r8, r12
0x1800103d4  call    WPP_SF_J
0x1800103d9  mov     ecx, [rsp+210h+InterfaceIndex]
0x1800103dd  mov     rax, [rsi]
0x1800103e0  mov     [rbp+110h+var_170], ecx
0x1800103e3  lea     rcx, [rbp+110h+var_180]
0x1800103e7  mov     [rbp+110h+var_118], rax
0x1800103eb  mov     [rbp+110h+var_174], 4Eh ; 'N'
0x1800103f2  call    TraceLogEx
0x1800103f7  lea     rdx, [rsp+210h+InterfaceIndex]; InterfaceIndex
0x1800103fc  mov     rcx, rsi; InterfaceLuid
0x1800103ff  call    cs:__imp_ConvertInterfaceLuidToIndex
0x180010406  nop     dword ptr [rax+rax+00h]
0x18001040b  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 1
0x180010412  jz      short loc_180010425
0x180010414  mov     r8d, [rsp+210h+InterfaceIndex]
0x180010419  lea     rdx, MediaConnect
0x180010420  call    McTemplateU0q_EtwEventWriteTransfer
0x180010425  lea     r9, [rsp+210h+var_1C4]
0x18001042a  mov     rcx, rsi; InterfaceLuid
0x18001042d  lea     r8, [rsp+210h+var_1C0]
0x180010432  lea     rdx, [rsp+210h+var_1CC]
0x180010437  call    Dhcpv6QueryNsiForRASettings
0x18001043c  mov     edi, eax
0x18001043e  test    eax, eax
0x180010440  jnz     loc_180010882
0x180010446  lea     rcx, Dhcpv6GlobalNicListCritSect; lpCriticalSection
0x18001044d  call    cs:__imp_EnterCriticalSection
0x180010454  nop     dword ptr [rax+rax+00h]
0x180010459  mov     rcx, rsi
0x18001045c  call    FindDhcpv6ContextOnNicList
0x180010461  mov     [rsp+210h+var_1A8], rax
0x180010466  mov     rbx, rax
0x180010469  test    rax, rax
0x18001046c  jnz     short loc_1800104E1
0x18001046e  lea     rdx, [rsp+210h+var_1A8]
0x180010473  call    Dhcpv6AddNICtoListEx
0x180010478  mov     rbx, [rsp+210h+var_1A8]
0x18001047d  mov     edi, eax
0x18001047f  test    rbx, rbx
0x180010482  jz      short loc_1800104A0
0x180010484  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 1
0x18001048b  jz      short loc_1800104A0
0x18001048d  mov     r8d, [rbx+30h]
0x180010491  lea     rdx, InterfaceAdded
0x180010498  mov     r9d, eax
0x18001049b  call    McTemplateU0qq_EtwEventWriteTransfer
0x1800104a0  test    edi, edi
0x1800104a2  jz      short loc_180010500
0x1800104a4  lea     rcx, Dhcpv6GlobalNicListCritSect; lpCriticalSection
0x1800104ab  call    cs:__imp_LeaveCriticalSection
0x1800104b2  nop     dword ptr [rax+rax+00h]
0x1800104b7  cmp     edi, 0FFFFFFFFh
0x1800104ba  jz      loc_180010882
0x1800104c0  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 8
0x1800104c7  jz      loc_180010882
0x1800104cd  mov     r8d, edi
0x1800104d0  lea     rdx, InitNetworkInterfaceFailed
0x1800104d7  call    McTemplateU0q_EtwEventWriteTransfer
0x1800104dc  jmp     loc_180010882
0x1800104e1  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800104e8  jz      short loc_180010500
0x1800104ea  mov     r9, [rax+18h]
0x1800104ee  mov     edx, 8Bh
0x1800104f3  mov     ecx, 404h
0x1800104f8  mov     r8, r12
0x1800104fb  call    WPP_SF_J
0x180010500  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 20h
0x180010507  jz      short loc_18001053A
0x180010509  mov     r9d, [rbx+30h]
0x18001050d  lea     r8, [rbx+20h]
0x180010511  lea     rdx, PerftrackDHCPv6MediaConnectEnd
0x180010518  call    McTemplateU0b16q_EtwEventWriteTransfer
0x18001051d  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 20h
0x180010524  jz      short loc_18001053A
0x180010526  mov     r9d, [rbx+30h]
0x18001052a  lea     r8, [rbx+20h]
0x18001052e  lea     rdx, PerftrackDHCPv6MediaConnect
0x180010535  call    McTemplateU0b16q_EtwEventWriteTransfer
0x18001053a  lea     rax, [rsp+210h+cbData]
0x18001053f  mov     esi, 4
0x180010544  mov     [rsp+210h+lpcbData], rax; lpcbData
0x180010549  lea     r9, [rsp+210h+Type]; lpType
0x18001054e  lea     rax, [rsp+210h+Data]
0x180010553  mov     [rsp+210h+cbData], esi
0x180010557  mov     rcx, [rbx+288h]; hKey
0x18001055e  lea     rdx, aDhcpv6startsta; "Dhcpv6StartState"
0x180010565  xor     r8d, r8d; lpReserved
0x180010568  mov     [rsp+210h+lpData], rax; lpData
0x18001056d  call    cs:__imp_RegQueryValueExW
0x180010574  nop     dword ptr [rax+rax+00h]
0x180010579  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 1
0x180010580  mov     edi, eax
0x180010582  jz      short loc_180010595
0x180010584  mov     r8d, [rsp+210h+InterfaceIndex]
0x180010589  lea     rdx, MediaConnect
0x180010590  call    McTemplateU0q_EtwEventWriteTransfer
0x180010595  xor     edx, edx
0x180010597  mov     rcx, rbx
0x18001059a  lea     r8d, [rdx+4Eh]
0x18001059e  call    TraceLogErrorv6
0x1800105a3  test    edi, edi
0x1800105a5  jnz     short loc_1800105B4
0x1800105a7  cmp     [rsp+210h+Type], esi
0x1800105ab  jnz     short loc_1800105B4
0x1800105ad  mov     r8d, dword ptr [rsp+210h+Data]
0x1800105b2  jmp     short loc_1800105E0
0x1800105b4  test    byte ptr cs:xmmword_1800423E0, 2
0x1800105bb  jz      short loc_1800105DA
0x1800105bd  mov     edx, 8Ch
0x1800105c2  mov     dword ptr [rsp+210h+lpData], edi
0x1800105c6  mov     ecx, 401h
0x1800105cb  lea     r9, aDhcpv6startsta; "Dhcpv6StartState"
0x1800105d2  mov     r8, r12
0x1800105d5  call    WPP_SF_SD
0x1800105da  movzx   r8d, word ptr [rsp+210h+var_1CC]
0x1800105e0  mov     dword ptr [rsp+210h+var_1D0], r8d
0x1800105e5  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800105ec  jz      short loc_180010618
0x1800105ee  mov     rcx, rbx
0x1800105f1  call    Dhcpv6IsInitState
0x1800105f6  mov     r9, [rbx+38h]
0x1800105fa  lea     rcx, [rbx+20h]
0x1800105fe  mov     [rsp+210h+var_1D8], r8d
0x180010603  mov     [rsp+210h+var_1E0], eax
0x180010607  mov     eax, [rbx+30h]
0x18001060a  mov     dword ptr [rsp+210h+lpcbData], eax
0x18001060e  mov     [rsp+210h+lpData], rcx
0x180010613  call    WPP_SF_S_guid_Lld
0x180010618  mov     eax, cs:dword_180042048
0x18001061e  cmp     eax, 5
0x180010621  jbe     loc_180010733
0x180010627  mov     rdx, 400000000000h
0x180010631  lea     rcx, dword_180042048
0x180010638  call    _tlgKeywordOn
0x18001063d  test    al, al
0x18001063f  jz      loc_180010733
0x180010645  mov     [rbp+110h+var_158], 10h
0x18001064d  lea     rax, [rbx+20h]
0x180010651  mov     [rbp+110h+var_160], rax
0x180010655  mov     rcx, rbx
0x180010658  mov     eax, [rbx+30h]
0x18001065b  mov     [rsp+210h+var_1C0], eax
0x18001065f  lea     rax, [rsp+210h+var_1C0]
0x180010664  mov     [rbp+110h+var_150], rax
0x180010668  mov     [rbp+110h+var_148], rsi
0x18001066c  mov     eax, [rbx+5Ch]
0x18001066f  mov     [rsp+210h+var_1C4], eax
0x180010673  lea     rax, [rsp+210h+var_1C4]
0x180010678  mov     [rbp+110h+var_140], rax
0x18001067c  mov     [rbp+110h+var_138], rsi
0x180010680  mov     eax, [rbx+60h]
0x180010683  mov     [rsp+210h+var_1CC], eax
0x180010687  lea     rax, [rsp+210h+var_1CC]
0x18001068c  mov     [rbp+110h+var_130], rax
0x180010690  lea     rax, [rbx+23B0h]
0x180010697  mov     [rbp+110h+var_120], rax
0x18001069b  lea     rax, Dhcpv6GlobalBootGuid
0x1800106a2  mov     [rbp+110h+var_110], rax
0x1800106a6  mov     [rbp+110h+var_128], rsi
0x1800106aa  mov     [rbp+110h+var_118], 10h
0x1800106b2  mov     [rbp+110h+var_108], 10h
0x1800106ba  call    Dhcpv6IsInitState
0x1800106bf  mov     [rsp+210h+var_1A0], eax
0x1800106c3  lea     rdx, byte_18003C2B9
0x1800106ca  lea     rax, [rsp+210h+var_1A0]
0x1800106cf  mov     [rbp+110h+var_F8], rsi
0x1800106d3  mov     [rbp+110h+var_100], rax
0x1800106d7  mov     eax, cs:Dhcpv6GlobalUseNetworkHint
0x1800106dd  mov     [rsp+210h+var_19C], eax
0x1800106e1  lea     rax, [rsp+210h+var_19C]
0x1800106e6  mov     [rbp+110h+var_F0], rax
0x1800106ea  mov     eax, dword ptr [rsp+210h+var_1D0]
0x1800106ee  mov     dword ptr [rsp+210h+var_1A8], eax
0x1800106f2  lea     rax, [rsp+210h+var_1A8]
0x1800106f7  mov     [rbp+110h+var_E0], rax
0x1800106fb  lea     rax, [rsp+210h+var_198]
0x180010700  mov     [rbp+110h+var_D0], rax
0x180010704  lea     rax, [rbp+110h+var_180]
0x180010708  mov     [rsp+210h+lpcbData], rax
0x18001070d  mov     dword ptr [rsp+210h+lpData], 0Ch
0x180010715  mov     [rbp+110h+var_E8], rsi
0x180010719  mov     [rbp+110h+var_D8], rsi
0x18001071d  mov     [rsp+210h+var_198], 1000000h
0x180010726  mov     [rbp+110h+var_C8], 8
0x18001072e  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180010733  lock inc dword ptr [rbx+10h]
0x180010737  lea     rcx, Dhcpv6GlobalNicListCritSect; lpCriticalSection
0x18001073e  call    cs:__imp_LeaveCriticalSection
0x180010745  nop     dword ptr [rax+rax+00h]
0x18001074a  lea     rcx, [rbx+2328h]; lpPerformanceCount
0x180010751  call    cs:__imp_QueryPerformanceCounter
0x180010758  nop     dword ptr [rax+rax+00h]
0x18001075d  cmp     cs:Dhcpv6GlobalUseNetworkHint, r14d
0x180010764  jz      loc_1800107FF
0x18001076a  mov     edx, 1
0x18001076f  mov     rcx, rbx
0x180010772  call    LockDhcpContext
0x180010777  mov     edi, eax
0x180010779  test    byte ptr cs:xmmword_1800423E0, 10h
0x180010780  jz      short loc_180010798
0x180010782  mov     r9, [rbx+38h]
0x180010786  mov     edx, 8Eh
0x18001078b  mov     ecx, 404h
0x180010790  mov     r8, r12
0x180010793  call    WPP_SF_S
0x180010798  test    edi, edi
0x18001079a  jz      short loc_1800107BA
0x18001079c  or      eax, 0FFFFFFFFh
0x18001079f  lock xadd [rbx+10h], eax
0x1800107a4  cmp     eax, 1
0x1800107a7  jnz     loc_180010882
0x1800107ad  mov     rcx, rbx
0x1800107b0  call    Dhcpv6DestroyContextEx
0x1800107b5  jmp     loc_180010882
0x1800107ba  mov     edx, dword ptr [rsp+210h+var_1D0]
0x1800107be  mov     rcx, rbx
0x1800107c1  call    Dhcpv6GetCachedNetwork
0x1800107c6  mov     rcx, [rbx+248h]; hSemaphore
0x1800107cd  xor     r8d, r8d; lpPreviousCount
0x1800107d0  lea     edx, [r8+1]; lReleaseCount
0x1800107d4  call    cs:__imp_ReleaseSemaphore
0x1800107db  nop     dword ptr [rax+rax+00h]
0x1800107e0  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800107e7  jz      short loc_1800107FF
0x1800107e9  mov     r9, [rbx+38h]
0x1800107ed  mov     edx, 8Fh
0x1800107f2  mov     ecx, 404h
0x1800107f7  mov     r8, r12
0x1800107fa  call    WPP_SF_S
0x1800107ff  mov     rcx, [rbx+288h]; hKey
0x180010806  lea     rax, [rsp+210h+var_1D0]
0x18001080b  mov     dword ptr [rsp+210h+lpcbData], esi; cbData
0x18001080f  lea     rdx, aDhcpv6state; "Dhcpv6State"
0x180010816  mov     r9d, esi; dwType
0x180010819  mov     [rsp+210h+lpData], rax; lpData
0x18001081e  xor     r8d, r8d; Reserved
0x180010821  call    cs:__imp_RegSetValueExW
0x180010828  nop     dword ptr [rax+rax+00h]
0x18001082d  mov     rcx, [rbx+288h]; hKey
0x180010834  lea     r8, [rsp+210h+var_1B0]
0x180010839  lea     rdx, [rbp+110h+var_190]
0x18001083d  mov     edi, eax
0x18001083f  call    Dhcpv6ReadSavedConfigurations
0x180010844  mov     eax, [rsp+210h+var_1B0]
0x180010848  mov     rcx, rbx
0x18001084b  mov     [rbx+2320h], eax
0x180010851  mov     dword ptr [rbx+233Ch], 1
0x18001085b  mov     edx, dword ptr [rsp+210h+var_1D0]
0x18001085f  call    Dhcpv6SetMode
0x180010864  call    DhcpRefreshDnrEnabledState
0x180010869  or      eax, 0FFFFFFFFh
0x18001086c  lock xadd [rbx+10h], eax
0x180010871  cmp     eax, 1
0x180010874  jnz     short loc_18001087E
0x180010876  mov     rcx, rbx
0x180010879  call    Dhcpv6DestroyContextEx
0x18001087e  test    edi, edi
0x180010880  jz      short loc_1800108C7
0x180010882  test    byte ptr cs:xmmword_1800423E0, 2
0x180010889  jz      short loc_1800108A0
0x18001088b  mov     edx, 90h
0x180010890  mov     ecx, 401h
0x180010895  mov     r9d, edi
0x180010898  mov     r8, r12
0x18001089b  call    WPP_SF_D
  ... truncated ...
```
