# Microsoft::Bluetooth::Services::BthServ::BthpEnableAllServices(void *,_BLUETOOTH_DEVICE_INFO const *,uchar)

- ea: `0x180025648`
- end: `0x180025e0a`
- name: `?BthpEnableAllServices@BthServ@Services@Bluetooth@Microsoft@@YAKPEAXPEBU_BLUETOOTH_DEVICE_INFO@@E@Z`
- size: `1986`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Services::BthServ *this, _QWORD *, const struct _BLUETOOTH_DEVICE_INFO *)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001ee00`

## callees

- `0x1800017a0`
- `0x180001d20`
- `0x180001d88`
- `0x18000270c`
- `0x180008af8`
- `0x1800120b8`
- `0x180012384`
- `0x18002424c`
- `0x18002472c`
- `0x1800247d0`
- `0x180024a1c`
- `0x180024c84`
- `0x180024f34`
- `0x180024fc8`
- `0x180025648`
- `0x180025ecc`
- `0x180026808`
- `0x180026c70`
- `0x180027ea8`
- `0x180029e84`
- `0x180029ea4`
- `0x18002a020`
- `0x18002a3e0`
- `0x18002a4e4`
- `0x180034af0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002580c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025899`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002580c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025899`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800258ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800258ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025821`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025821`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025887`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025887`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800257c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800257d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800258bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800257c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800257d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800258bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025d64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025d64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800259f6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800259f6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025a40`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025a40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025a6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025a6e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180025d3a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180025d3a`

## string_xrefs

- `0x1800259b0`: `System\CurrentControlSet\Services\BTHPORT\Parameters\Restrictions\COD Major %02x Minor %02x`
- `0x180025a34`: `DontAddIncomingSPPInWizard`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BthpEnableAllServices(
        Microsoft::Bluetooth::Services::BthServ *this,
        _QWORD *a2,
        const struct _BLUETOOTH_DEVICE_INFO *a3)
{
  char v5; // bl
  char v6; // di
  Microsoft::Bluetooth::Services::BthServ *FirstServiceInternal; // r12
  const struct _BLUETOOTH_DEVICE_INFO *v8; // rdx
  int v9; // eax
  int v10; // edx
  int v11; // r8d
  Microsoft::Bluetooth::Services::BthServ *v12; // r14
  struct _BLUETOOTH_SERVICE_RECORD *v13; // r8
  Microsoft::Bluetooth::Services::BthServ *v14; // rsi
  HANDLE ProcessHeap; // rax
  Microsoft::Bluetooth::Services::BthServ *v16; // rbx
  unsigned int *v17; // r9
  DWORD LastError; // r15d
  struct _BLUETOOTH_SDP_RECORD *v19; // rax
  struct _GUID *v20; // r8
  HANDLE v21; // rax
  void *v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rcx
  BOOL v25; // ebx
  unsigned int v26; // ebx
  void *v27; // rdx
  __int64 *v28; // rax
  void *v29; // rdx
  int v30; // r8d
  __int64 v31; // rbx
  void *v32; // rcx
  const GUID *v33; // rdx
  int v34; // eax
  void *v35; // rdx
  unsigned int v36; // r8d
  HKEY v37; // rcx
  HKEY v38; // rbx
  void *v39; // rdx
  unsigned int v40; // r8d
  const char *v41; // r9
  const struct _GUID *phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int lpcbData; // [rsp+28h] [rbp-D8h]
  LPDWORD lpBytesReturned; // [rsp+30h] [rbp-D0h]
  LPOVERLAPPED lpOverlapped; // [rsp+38h] [rbp-C8h]
  int v47; // [rsp+40h] [rbp-C0h]
  unsigned __int8 v48[8]; // [rsp+48h] [rbp-B8h]
  unsigned __int8 v49; // [rsp+50h] [rbp-B0h]
  DWORD Type; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[4]; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbData; // [rsp+70h] [rbp-90h] BYREF
  Microsoft::Bluetooth::Services::BthServ *v54; // [rsp+78h] [rbp-88h]
  unsigned int v55[4]; // [rsp+80h] [rbp-80h] BYREF
  Microsoft::Bluetooth::Services::BthServ *v56; // [rsp+90h] [rbp-70h]
  __int64 v57; // [rsp+98h] [rbp-68h]
  _BLUETOOTH_DEVICE_INFO v58; // [rsp+A0h] [rbp-60h] BYREF
  int v59; // [rsp+2F0h] [rbp+1F0h] BYREF
  _BYTE v60[4]; // [rsp+2F4h] [rbp+1F4h] BYREF
  __int64 v61; // [rsp+2F8h] [rbp+1F8h]
  unsigned int v62; // [rsp+300h] [rbp+200h]
  char v63; // [rsp+304h] [rbp+204h]
  struct _BLUETOOTH_DEVICE_INFO *v64; // [rsp+308h] [rbp+208h]
  Microsoft::Bluetooth::Services::BthServ *v65; // [rsp+310h] [rbp+210h]
  WCHAR SubKey[6]; // [rsp+8C0h] [rbp+7C0h] BYREF
  int v67; // [rsp+8CCh] [rbp+7CCh]
  wil::details::in1diag3 *retaddr; // [rsp+1038h] [rbp+F38h]

  v54 = this;
  memset_0(&v58.stLastSeen, 0, sizeof(_BLUETOOTH_DEVICE_INFO));
  *(_QWORD *)&v58.stLastSeen.wHour = a2[1];
  *(_DWORD *)&v58.stLastSeen.wYear = 560;
  *(_QWORD *)v55 = 32;
  v57 = 0;
  *(_QWORD *)&v55[2] = &v58.stLastSeen;
  v56 = this;
  memset_0(v60, 0, 0x5C4u);
  v59 = 1480;
  v5 = 0;
  v6 = 1;
  do
  {
    if ( v5 )
      return 1168;
    FirstServiceInternal = (Microsoft::Bluetooth::Services::BthServ *)Microsoft::Bluetooth::Services::BthServ::BluetoothFindFirstServiceInternal(
                                                                        (__int64)v55,
                                                                        &v59,
                                                                        1u);
    v5 = 1;
  }
  while ( !FirstServiceInternal );
  memset(&v58, 0, 28);
  Microsoft::Bluetooth::Services::BthServ::BthpFindPnpInfo(this, a2, &v58, (struct _BTH_PNP_INFO *)1);
  if ( (v58.fRemembered & 0xF) != 0xF )
  {
    v9 = Microsoft::Bluetooth::Services::BthServ::BthpFindAndStampPnpInfoFromServiceSearch(
           (Microsoft::Bluetooth::Services::BthServ *)a2,
           v8);
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (LOBYTE(v10) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
      {
        LOBYTE(v10) = 0;
      }
      if ( (_BYTE)v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v48[0] = v9;
        lpOverlapped = (LPOVERLAPPED)&WPP_b232bbd09fa63021a92d957d702a2cb3_Traceguids;
        LOWORD(lpBytesReturned) = 11;
        LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, *((_QWORD *)WPP_GLOBAL_Control + 5));
      }
    }
  }
  do
  {
    *(_OWORD *)v55 = 0;
    v12 = 0;
    if ( v59 != 1480 )
    {
      SetLastError(0x51Au);
      continue;
    }
    SetLastError(0xDu);
    if ( (v63 & 2) == 0 )
      continue;
    v14 = v65;
    if ( !v65 )
      continue;
    if ( (*(_BYTE *)v65 & 0xF8) != 0x30 )
      continue;
    ProcessHeap = GetProcessHeap();
    v16 = (Microsoft::Bluetooth::Services::BthServ *)HeapAlloc(ProcessHeap, 0, 0x18u);
    if ( !v16 )
      continue;
    Type = 0;
    LastError = 1168;
    v19 = Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(
            v14,
            (struct _BLUETOOTH_SDP_RECORD *)(v61 + v62),
            &Type,
            v17);
    *(_QWORD *)v16 = v19;
    if ( !v19 )
      goto LABEL_21;
    LastError = 0;
    *((_QWORD *)v16 + 1) = (char *)v19 + Type;
    v12 = v16;
    if ( !Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextClassId(v16, v55, v20) )
    {
      LastError = GetLastError();
      v12 = 0;
LABEL_21:
      v21 = GetProcessHeap();
      HeapFree(v21, 0, v16);
    }
    SetLastError(LastError);
    if ( !v12 )
      continue;
    Microsoft::Bluetooth::Services::BthServ::BluetoothFindClassIdClose(v12, v22);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56664216>::GetImpl'::`2'::impl) )
    {
      v23 = *(_QWORD *)&v55[2];
      v24 = *(_QWORD *)v55;
    }
    else
    {
      if ( dword_18004732C > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                       + 4LL) )
      {
        Init_thread_header(&dword_18004732C);
        if ( dword_18004732C == -1 )
        {
          xmmword_180047240 = (__int128)AudioSinkServiceClass_UUID;
          xmmword_180047250 = (__int128)AVRemoteControlTargetServiceClass_UUID;
          xmmword_180047260 = (__int128)AVRemoteControlServiceClass_UUID;
          xmmword_180047270 = (__int128)HandsfreeServiceClass_UUID;
          Init_thread_footer(&dword_18004732C);
        }
      }
      v28 = (__int64 *)&xmmword_180047240;
      v23 = *(_QWORD *)&v55[2];
      v24 = *(_QWORD *)v55;
      do
      {
        if ( *v28 == *(_QWORD *)v55 && v28[1] == *(_QWORD *)&v55[2] )
          break;
        v28 += 2;
      }
      while ( v28 != ____PchSym__00_KxulyqvxgPillgKxulmvxlivUwirevihUdwnUyofvgllgsUfhviUygshvieUhvieviUyofvgllgszkrhUoryUlyquivUznwGEUkxsOlyq_bthserv_bluetoothapis );
      if ( v28 != ____PchSym__00_KxulyqvxgPillgKxulmvxlivUwirevihUdwnUyofvgllgsUfhviUygshvieUhvieviUyofvgllgszkrhUoryUlyquivUznwGEUkxsOlyq_bthserv_bluetoothapis )
      {
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (LOBYTE(v23) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
        {
          LOBYTE(v23) = 0;
        }
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( (_BYTE)v23 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_AND_TRACE_SF_s_guid_i(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v23,
            (_DWORD)v13,
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            (_DWORD)phkResult,
            lpcbData,
            12,
            (_DWORD)lpOverlapped,
            v47,
            (__int64)v55,
            a2[1]);
        continue;
      }
    }
    if ( v24 == *(_QWORD *)&SerialPortServiceClass_UUID.Data1 && v23 == *(_QWORD *)SerialPortServiceClass_UUID.Data4 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (LOBYTE(v23) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
      {
        LOBYTE(v23) = 0;
      }
      if ( (_BYTE)v23 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        *(_QWORD *)v48 = a2[1];
        lpOverlapped = (LPOVERLAPPED)&WPP_b232bbd09fa63021a92d957d702a2cb3_Traceguids;
        LOWORD(lpBytesReturned) = 14;
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_si(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v23,
          (_DWORD)v13,
          *((_QWORD *)WPP_GLOBAL_Control + 5));
      }
      if ( !Microsoft::Bluetooth::Services::BthServ::BthpSetServiceStateEx(
              v54,
              &v58.stLastSeen,
              (const struct _BLUETOOTH_DEVICE_INFO *)(unsigned int)v64,
              0,
              phkResult,
              lpcbData,
              lpBytesReturned,
              (unsigned __int8)lpOverlapped,
              v47,
              v48[0],
              v49) )
      {
        v25 = 1;
        LODWORD(phkResult) = LOBYTE(v58.stLastUsed.wYear) >> 2;
        if ( (int)StringCchPrintfW(
                    SubKey,
                    0xB8u,
                    L"System\\CurrentControlSet\\Services\\BTHPORT\\Parameters\\Restrictions\\COD Major %02x Minor %02x",
                    (*(_DWORD *)&v58.stLastUsed.wYear >> 8) & 0x1F) < 0 )
          goto LABEL_42;
        hKey = 0;
        if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
        {
          Type = 0;
          *(_DWORD *)Data = 0;
          cbData = 4;
          if ( !RegQueryValueExW(hKey, L"DontAddIncomingSPPInWizard", 0, &Type, Data, &cbData)
            && Type == 4
            && cbData == 4 )
          {
            v25 = *(_DWORD *)Data == 0;
          }
          RegCloseKey(hKey);
        }
        if ( v25 )
        {
LABEL_42:
          v26 = 0;
          while ( 1 )
          {
            memset_0(SubKey, 0, 0x410u);
            if ( (unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothGetLocalServiceInfo(
                                 0,
                                 v27,
                                 (const struct _GUID *)v26,
                                 (__int64)SubKey)
              || !*(_DWORD *)SubKey )
            {
              break;
            }
            if ( ++v26 >= 0xFF )
              goto LABEL_67;
          }
          Microsoft::Bluetooth::Services::BthServ::InstallIncomingComPort(
            (Microsoft::Bluetooth::Services::BthServ *)&v58.stLastSeen,
            (const struct _BLUETOOTH_DEVICE_INFO *)v26,
            (unsigned int)v13);
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (LOBYTE(v23) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
      {
        LOBYTE(v23) = 0;
      }
      if ( (_BYTE)v23 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_s_guid_i(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v23,
          (_DWORD)v13,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          (_DWORD)phkResult,
          lpcbData,
          13,
          (_DWORD)lpOverlapped,
          v47,
          (__int64)v55,
          a2[1]);
      }
      Microsoft::Bluetooth::Services::BthServ::BthpSetServiceStateEx(
        v54,
        &v58.stLastSeen,
        0,
        (unsigned int)v55,
        phkResult,
        lpcbData,
        lpBytesReturned,
        (unsigned __int8)lpOverlapped,
        v47,
        v48[0],
        v49);
    }
LABEL_67:
    ;
  }
  while ( (unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextService(
                          FirstServiceInternal,
                          &v59,
                          v13) );
  Microsoft::Bluetooth::Services::BthServ::BluetoothFindServiceClose(FirstServiceInternal, v29);
  v31 = a2[1];
  v32 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    v6 = 0;
  if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v33 = &WPP_b232bbd09fa63021a92d957d702a2cb3_Traceguids;
    LOBYTE(v33) = v6;
    LOBYTE(v30) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)v33,
      v30,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  }
  hKey = 0;
  v34 = BthDevnodeOpenInterfaceHandle(v32, 0, &hKey);
  if ( v34 >= 0 )
  {
    memset_0(SubKey, 0, 0x72Au);
    *(_QWORD *)SubKey = v31;
    v67 = 128;
    *(_DWORD *)Data = 0;
    v38 = hKey;
    if ( !DeviceIoControl(hKey, 0x411030u, SubKey, 0x72Au, 0, 0, (LPDWORD)Data, 0) )
      wil::details::in1diag3::_Log_GetLastError(retaddr, v39, v40, v41);
    if ( (unsigned __int64)v38 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v37 = v38;
      goto LABEL_81;
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(retaddr, v35, v36, (const char *)(unsigned int)v34, (int)phkResult);
    v37 = hKey;
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
LABEL_81:
      CloseHandle(v37);
  }
  return 0;
}

```

## disassembly

```asm
0x180025648  mov     [rsp-8+arg_10], rbx
0x18002564d  push    rbp
0x18002564e  push    rsi
0x18002564f  push    rdi
0x180025650  push    r12
0x180025652  push    r13
0x180025654  push    r14
0x180025656  push    r15
0x180025658  lea     rbp, [rsp-0F00h]
0x180025660  mov     eax, 1000h
0x180025665  call    _alloca_probe
0x18002566a  sub     rsp, rax
0x18002566d  mov     rax, cs:__security_cookie
0x180025674  xor     rax, rsp
0x180025677  mov     [rbp+0F30h+var_40], rax
0x18002567e  mov     r13, rdx
0x180025681  mov     rsi, rcx
0x180025684  mov     [rsp+1030h+var_FB8], rcx
0x180025689  mov     ebx, 230h
0x18002568e  mov     r8d, ebx; Size
0x180025691  xor     edx, edx; Val
0x180025693  lea     rcx, [rbp+0F30h+var_F90.stLastSeen]; void *
0x180025697  call    memset_0
0x18002569c  mov     rax, [r13+8]
0x1800256a0  mov     qword ptr [rbp+0F30h+var_F90.stLastSeen.wHour], rax
0x1800256a4  mov     dword ptr [rbp+0F30h+var_F90.stLastSeen.wYear], ebx
0x1800256a7  xor     r15d, r15d
0x1800256aa  mov     qword ptr [rbp+0F30h+var_FB0], 20h ; ' '
0x1800256b2  mov     [rbp+0F30h+var_F98], r15
0x1800256b6  lea     rax, [rbp+0F30h+var_F90.stLastSeen]
0x1800256ba  mov     qword ptr [rbp+0F30h+var_FB0+8], rax
0x1800256be  mov     [rbp+0F30h+var_FA0], rsi
0x1800256c2  xor     edx, edx; Val
0x1800256c4  mov     r8d, 5C4h; Size
0x1800256ca  lea     rcx, [rbp+0F30h+var_D3C]; void *
0x1800256d1  call    memset_0
0x1800256d6  mov     [rbp+0F30h+var_D40], 5C8h
0x1800256e0  mov     bl, r15b
0x1800256e3  lea     edi, [r15+1]
0x1800256e7  cmp     bl, dil
0x1800256ea  jnb     loc_180025D74
0x1800256f0  mov     r8d, edi
0x1800256f3  lea     rdx, [rbp+0F30h+var_D40]
0x1800256fa  lea     rcx, [rbp+0F30h+var_FB0]
0x1800256fe  call    ?BluetoothFindFirstServiceInternal@BthServ@Services@Bluetooth@Microsoft@@YAPEAXPEBU_BLUETOOTH_SDP_SEARCH_PARAMS@@PEAU_BLUETOOTH_SERVICE_RECORD@@W4_BTHSERV_QUERY_TYPE@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindFirstServiceInternal(_BLUETOOTH_SDP_SEARCH_PARAMS const *,_BLUETOOTH_SERVICE_RECORD *,_BTHSERV_QUERY_TYPE)
0x180025703  mov     r12, rax
0x180025706  add     bl, dil
0x180025709  test    rax, rax
0x18002570c  jz      short loc_1800256E7
0x18002570e  xorps   xmm0, xmm0
0x180025711  xor     eax, eax
0x180025713  movups  xmmword ptr [rbp+0F30h+var_F90.dwSize], xmm0
0x180025717  mov     qword ptr [rbp+0F30h+var_F90.ulClassofDevice], rax
0x18002571b  mov     [rbp+0F30h+var_F90.fRemembered], eax
0x18002571e  mov     r9d, edi; struct _BTH_PNP_INFO *
0x180025721  lea     r8, [rbp+0F30h+var_F90]; struct _BLUETOOTH_DEVICE_INFO *
0x180025725  mov     rdx, r13; void *
0x180025728  mov     rcx, rsi; this
0x18002572b  call    ?BthpFindPnpInfo@BthServ@Services@Bluetooth@Microsoft@@YAXPEAXPEBU_BLUETOOTH_DEVICE_INFO@@PEAU_BTH_PNP_INFO@@H@Z; Microsoft::Bluetooth::Services::BthServ::BthpFindPnpInfo(void *,_BLUETOOTH_DEVICE_INFO const *,_BTH_PNP_INFO *,int)
0x180025730  mov     eax, [rbp+0F30h+var_F90.fRemembered]
0x180025733  and     eax, 0Fh
0x180025736  lea     rsi, WPP_GLOBAL_Control
0x18002573d  lea     rbx, WPP_RECORDER_INITIALIZED
0x180025744  lea     r14, WPP_b232bbd09fa63021a92d957d702a2cb3_Traceguids
0x18002574b  cmp     al, 0Fh
0x18002574d  jz      short loc_1800257A4
0x18002574f  mov     rcx, r13; this
0x180025752  call    ?BthpFindAndStampPnpInfoFromServiceSearch@BthServ@Services@Bluetooth@Microsoft@@YAJPEBU_BLUETOOTH_DEVICE_INFO@@@Z; Microsoft::Bluetooth::Services::BthServ::BthpFindAndStampPnpInfoFromServiceSearch(_BLUETOOTH_DEVICE_INFO const *)
0x180025757  test    eax, eax
0x180025759  jns     short loc_1800257A4
0x18002575b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025762  cmp     rcx, rsi
0x180025765  jz      short loc_180025770
0x180025767  cmp     byte ptr [rcx+19h], 3
0x18002576b  mov     dl, dil
0x18002576e  jnb     short loc_180025773
0x180025770  mov     dl, r15b
0x180025773  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x18002577a  setnz   r8b
0x18002577e  test    dl, dl
0x180025780  jnz     short loc_180025787
0x180025782  test    r8b, r8b
0x180025785  jz      short loc_1800257A4
0x180025787  mov     dword ptr [rsp+1030h+var_FE8], eax
0x18002578b  mov     [rsp+1030h+lpOverlapped], r14; unsigned __int8
0x180025790  mov     word ptr [rsp+1030h+lpBytesReturned], 0Bh
0x180025797  mov     r9, [rcx+28h]
0x18002579b  mov     rcx, [rcx+10h]
0x18002579f  call    WPP_RECORDER_AND_TRACE_SF_sD
0x1800257a4  mov     eax, 0Dh
0x1800257a9  xorps   xmm0, xmm0
0x1800257ac  movups  xmmword ptr [rbp+0F30h+var_FB0], xmm0
0x1800257b0  mov     r14, r15
0x1800257b3  cmp     [rbp+0F30h+var_D40], 5C8h
0x1800257bd  jz      short loc_1800257D5
0x1800257bf  mov     ecx, 51Ah; dwErrCode
0x1800257c4  call    cs:__imp_SetLastError
0x1800257cb  nop     dword ptr [rax+rax+00h]
0x1800257d0  jmp     loc_180025C1F
0x1800257d5  mov     ecx, eax; dwErrCode
0x1800257d7  call    cs:__imp_SetLastError
0x1800257de  nop     dword ptr [rax+rax+00h]
0x1800257e3  test    [rbp+0F30h+var_D2C], 2
0x1800257ea  jz      loc_180025C1F
0x1800257f0  mov     rsi, [rbp+0F30h+var_D20]
0x1800257f7  test    rsi, rsi
0x1800257fa  jz      loc_180025C18
0x180025800  mov     al, [rsi]
0x180025802  and     al, 0F8h
0x180025804  cmp     al, 30h ; '0'
0x180025806  jnz     loc_180025C18
0x18002580c  call    cs:__imp_GetProcessHeap
0x180025813  nop     dword ptr [rax+rax+00h]
0x180025818  mov     rcx, rax; hHeap
0x18002581b  xor     edx, edx; dwFlags
0x18002581d  lea     r8d, [rdx+18h]; dwBytes
0x180025821  call    cs:__imp_HeapAlloc
0x180025828  nop     dword ptr [rax+rax+00h]
0x18002582d  mov     rbx, rax
0x180025830  test    rax, rax
0x180025833  jz      loc_180025C18
0x180025839  mov     [rsp+1030h+Type], r15d
0x18002583e  mov     r15d, 490h
0x180025844  mov     edx, [rbp+0F30h+var_D30]
0x18002584a  add     rdx, [rbp+0F30h+var_D38]; struct _BLUETOOTH_SDP_RECORD *
0x180025851  lea     r8, [rsp+1030h+Type]; void *
0x180025856  mov     rcx, rsi; this
0x180025859  call    ?BthpInnerRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAXPEAK@Z; Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(_BLUETOOTH_SDP_RECORD *,void *,ulong *)
0x18002585e  mov     [rbx], rax
0x180025861  test    rax, rax
0x180025864  jz      short loc_180025899
0x180025866  xor     r15d, r15d
0x180025869  mov     ecx, [rsp+1030h+Type]
0x18002586d  add     rcx, rax
0x180025870  mov     [rbx+8], rcx
0x180025874  mov     r14, rbx
0x180025877  lea     rdx, [rbp+0F30h+var_FB0]; void *
0x18002587b  mov     rcx, rbx; this
0x18002587e  call    ?BluetoothFindNextClassId@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAU_GUID@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextClassId(void *,_GUID *)
0x180025883  test    eax, eax
0x180025885  jnz     short loc_1800258B9
0x180025887  call    cs:__imp_GetLastError
0x18002588e  nop     dword ptr [rax+rax+00h]
0x180025893  mov     r15d, eax
0x180025896  xor     r14d, r14d
0x180025899  call    cs:__imp_GetProcessHeap
0x1800258a0  nop     dword ptr [rax+rax+00h]
0x1800258a5  mov     rcx, rax; hHeap
0x1800258a8  mov     r8, rbx; lpMem
0x1800258ab  xor     edx, edx; dwFlags
0x1800258ad  call    cs:__imp_HeapFree
0x1800258b4  nop     dword ptr [rax+rax+00h]
0x1800258b9  mov     ecx, r15d; dwErrCode
0x1800258bc  call    cs:__imp_SetLastError
0x1800258c3  nop     dword ptr [rax+rax+00h]
0x1800258c8  xor     r15d, r15d
0x1800258cb  test    r14, r14
0x1800258ce  jz      loc_180025C18
0x1800258d4  mov     rcx, r14; this
0x1800258d7  call    ?BluetoothFindClassIdClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindClassIdClose(void *)
0x1800258dc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56664216@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56664216@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216> `wil::Feature<__WilFeatureTraits_Feature_56664216>::GetImpl(void)'::`2'::impl
0x1800258e3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56664216@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216>::__private_IsEnabled(void)
0x1800258e8  test    al, al
0x1800258ea  jz      loc_180025ACE
0x1800258f0  mov     rdx, qword ptr [rbp+0F30h+var_FB0+8]
0x1800258f4  mov     rcx, qword ptr [rbp+0F30h+var_FB0]
0x1800258f8  cmp     rcx, qword ptr cs:SerialPortServiceClass_UUID.Data1
0x1800258ff  jnz     loc_180025BA1
0x180025905  cmp     rdx, qword ptr cs:SerialPortServiceClass_UUID.Data4
0x18002590c  jnz     loc_180025BA1
0x180025912  mov     rcx, cs:WPP_GLOBAL_Control
0x180025919  lea     rsi, WPP_GLOBAL_Control
0x180025920  cmp     rcx, rsi
0x180025923  jz      short loc_18002592E
0x180025925  cmp     byte ptr [rcx+19h], 4
0x180025929  mov     dl, dil
0x18002592c  jnb     short loc_180025931
0x18002592e  mov     dl, r15b
0x180025931  lea     r14, WPP_RECORDER_INITIALIZED
0x180025938  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18002593f  setnz   r8b
0x180025943  test    dl, dl
0x180025945  jnz     short loc_18002594C
0x180025947  test    r8b, r8b
0x18002594a  jz      short loc_180025975
0x18002594c  mov     rax, [r13+8]
0x180025950  mov     qword ptr [rsp+1030h+var_FE8], rax; unsigned __int8
0x180025955  lea     rax, WPP_b232bbd09fa63021a92d957d702a2cb3_Traceguids
0x18002595c  mov     [rsp+1030h+lpOverlapped], rax; unsigned __int8
0x180025961  mov     word ptr [rsp+1030h+lpBytesReturned], 0Eh; void *
0x180025968  mov     r9, [rcx+28h]
0x18002596c  mov     rcx, [rcx+10h]
0x180025970  call    WPP_RECORDER_AND_TRACE_SF_si
0x180025975  xor     r9d, r9d; unsigned int
0x180025978  mov     r8d, dword ptr [rbp+0F30h+var_D28]; struct _BLUETOOTH_DEVICE_INFO *
0x18002597f  lea     rdx, [rbp+0F30h+var_F90.stLastSeen]; void *
0x180025983  mov     rcx, [rsp+1030h+var_FB8]; this
0x180025988  call    ?BthpSetServiceStateEx@BthServ@Services@Bluetooth@Microsoft@@YAKPEAXPEBU_BLUETOOTH_DEVICE_INFO@@KPEBU_GUID@@K0EEEE@Z; Microsoft::Bluetooth::Services::BthServ::BthpSetServiceStateEx(void *,_BLUETOOTH_DEVICE_INFO const *,ulong,_GUID const *,ulong,void *,uchar,uchar,uchar,uchar)
0x18002598d  test    eax, eax
0x18002598f  jnz     loc_180025C26
0x180025995  mov     ebx, edi
0x180025997  mov     r9d, dword ptr [rbp+0F30h+var_F90.stLastUsed.wYear]
0x18002599b  mov     eax, r9d
0x18002599e  shr     eax, 2
0x1800259a1  and     eax, 3Fh
0x1800259a4  shr     r9d, 8
0x1800259a8  and     r9d, 1Fh
0x1800259ac  mov     dword ptr [rsp+1030h+phkResult], eax
0x1800259b0  lea     r8, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\BT"...
0x1800259b7  mov     edx, 0B8h; unsigned __int64
0x1800259bc  lea     rcx, [rbp+0F30h+SubKey]; unsigned __int16 *
0x1800259c3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800259c8  test    eax, eax
0x1800259ca  js      loc_180025A82
0x1800259d0  mov     [rsp+1030h+hKey], r15
0x1800259d5  lea     rax, [rsp+1030h+hKey]
0x1800259da  mov     [rsp+1030h+phkResult], rax; phkResult
0x1800259df  mov     r9d, 20019h; samDesired
0x1800259e5  xor     r8d, r8d; ulOptions
0x1800259e8  lea     rdx, [rbp+0F30h+SubKey]; lpSubKey
0x1800259ef  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800259f6  call    cs:__imp_RegOpenKeyExW
0x1800259fd  nop     dword ptr [rax+rax+00h]
0x180025a02  test    eax, eax
0x180025a04  jnz     short loc_180025A7A
0x180025a06  mov     [rsp+1030h+Type], r15d
0x180025a0b  mov     dword ptr [rsp+1030h+Data], r15d
0x180025a10  mov     [rsp+1030h+cbData], 4
0x180025a18  lea     rax, [rsp+1030h+cbData]
0x180025a1d  mov     [rsp+1030h+lpcbData], rax; lpcbData
0x180025a22  lea     rax, [rsp+1030h+Data]
0x180025a27  mov     [rsp+1030h+phkResult], rax; struct _BLUETOOTH_LOCAL_SERVICE_INFO *
0x180025a2c  lea     r9, [rsp+1030h+Type]; lpType
0x180025a31  xor     r8d, r8d; lpReserved
0x180025a34  lea     rdx, aDontaddincomin; "DontAddIncomingSPPInWizard"
0x180025a3b  mov     rcx, [rsp+1030h+hKey]; hKey
0x180025a40  call    cs:__imp_RegQueryValueExW
0x180025a47  nop     dword ptr [rax+rax+00h]
0x180025a4c  test    eax, eax
0x180025a4e  jnz     short loc_180025A69
0x180025a50  cmp     [rsp+1030h+Type], 4
0x180025a55  jnz     short loc_180025A69
0x180025a57  cmp     [rsp+1030h+cbData], 4
0x180025a5c  jnz     short loc_180025A69
0x180025a5e  mov     ebx, r15d
0x180025a61  cmp     dword ptr [rsp+1030h+Data], r15d
0x180025a66  setz    bl
0x180025a69  mov     rcx, [rsp+1030h+hKey]; hKey
0x180025a6e  call    cs:__imp_RegCloseKey
0x180025a75  nop     dword ptr [rax+rax+00h]
0x180025a7a  test    ebx, ebx
0x180025a7c  jz      loc_180025C26
0x180025a82  mov     ebx, r15d
0x180025a85  xor     edx, edx; Val
0x180025a87  mov     r8d, 410h; Size
0x180025a8d  lea     rcx, [rbp+0F30h+SubKey]; void *
0x180025a94  call    memset_0
0x180025a99  lea     r9, [rbp+0F30h+SubKey]; unsigned int
0x180025aa0  mov     r8d, ebx; struct _GUID *
0x180025aa3  xor     ecx, ecx; this
0x180025aa5  call    ?BluetoothGetLocalServiceInfo@BthServ@Services@Bluetooth@Microsoft@@YAKPEAXPEBU_GUID@@KPEAU_BLUETOOTH_LOCAL_SERVICE_INFO@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothGetLocalServiceInfo(void *,_GUID const *,ulong,_BLUETOOTH_LOCAL_SERVICE_INFO *)
0x180025aaa  test    eax, eax
0x180025aac  jnz     loc_180025B91
0x180025ab2  cmp     dword ptr [rbp+0F30h+SubKey], r15d
0x180025ab9  jz      loc_180025B91
0x180025abf  add     ebx, edi
0x180025ac1  cmp     ebx, 0FFh
0x180025ac7  jb      short loc_180025A85
0x180025ac9  jmp     loc_180025C26
0x180025ace  mov     edx, 4
0x180025ad3  mov     eax, cs:_tls_index
0x180025ad9  mov     rcx, gs:58h
0x180025ae2  mov     rax, [rcx+rax*8]
0x180025ae6  mov     ecx, [rdx+rax]
0x180025ae9  cmp     cs:dword_18004732C, ecx
0x180025aef  jg      loc_180025DA4
0x180025af5  lea     rax, xmmword_180047240
0x180025afc  mov     rdx, qword ptr [rbp+0F30h+var_FB0+8]
0x180025b00  mov     rcx, qword ptr [rbp+0F30h+var_FB0]
0x180025b04  lea     rbx, __@@_PchSym_@00@KxulyqvxgPillgKxulmvxlivUwirevihUdwnUyofvgllgsUfhviUygshvieUhvieviUyofvgllgszkrhUoryUlyquivUznwGEUkxsOlyq@bthserv_bluetoothapis
0x180025b0b  cmp     [rax], rcx
0x180025b0e  jnz     short loc_180025B16
0x180025b10  cmp     [rax+8], rdx
0x180025b14  jz      short loc_180025B1F
0x180025b16  add     rax, 10h
0x180025b1a  cmp     rax, rbx
0x180025b1d  jnz     short loc_180025B0B
0x180025b1f  cmp     rax, rbx
0x180025b22  jz      loc_1800258F8
0x180025b28  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b2f  lea     rsi, WPP_GLOBAL_Control
0x180025b36  cmp     rcx, rsi
0x180025b39  jz      short loc_180025B44
0x180025b3b  cmp     byte ptr [rcx+19h], 4
0x180025b3f  mov     dl, dil
0x180025b42  jnb     short loc_180025B47
0x180025b44  mov     dl, r15b
0x180025b47  lea     r14, WPP_RECORDER_INITIALIZED
0x180025b4e  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180025b55  setnz   r8b
  ... truncated ...
```
