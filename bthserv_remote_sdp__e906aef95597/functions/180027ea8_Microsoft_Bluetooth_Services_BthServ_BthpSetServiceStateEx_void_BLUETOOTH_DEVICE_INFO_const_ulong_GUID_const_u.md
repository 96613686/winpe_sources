# Microsoft::Bluetooth::Services::BthServ::BthpSetServiceStateEx(void *,_BLUETOOTH_DEVICE_INFO const *,ulong,_GUID const *,ulong,void *,uchar,uchar,uchar,uchar)

- ea: `0x180027ea8`
- end: `0x180028405`
- name: `?BthpSetServiceStateEx@BthServ@Services@Bluetooth@Microsoft@@YAKPEAXPEBU_BLUETOOTH_DEVICE_INFO@@KPEBU_GUID@@K0EEEE@Z`
- size: `1373`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Services::BthServ *this, unsigned __int64 *, const struct _BLUETOOTH_DEVICE_INFO *, _QWORD *)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180025648`
- `0x180027ea8`

## callees

- `0x1800017a0`
- `0x18000270c`
- `0x1800125ac`
- `0x180015158`
- `0x180016864`
- `0x18002472c`
- `0x18002478c`
- `0x180024a1c`
- `0x180024a8c`
- `0x180024c84`
- `0x180024ebc`
- `0x180024f34`
- `0x180026808`
- `0x180026b94`
- `0x180026c70`
- `0x180026dec`
- `0x180027ea8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002804d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800280d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028261`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028336`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800283bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002804d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800280d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028261`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028336`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800283bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800280eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002834a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800283d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800280eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002834a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800283d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028062`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028279`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028062`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028279`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800280c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800282fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800280c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800282fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027ffc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028026`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800280fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028316`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027ffc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028026`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800280fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028316`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028398`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028398`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800282a2`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800282a2`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800282d7`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800282d7`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18002832a`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18002832a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BthpSetServiceStateEx(
        Microsoft::Bluetooth::Services::BthServ *this,
        unsigned __int64 *a2,
        const struct _BLUETOOTH_DEVICE_INFO *a3,
        _QWORD *a4)
{
  Microsoft::Bluetooth::Services::BthServ *v4; // rsi
  unsigned int v6; // r15d
  unsigned __int64 *v7; // r13
  unsigned int SDPPriLangServiceName; // edi
  struct _BLUETOOTH_SERVICE_RECORD *v10; // r8
  void *v11; // rdx
  Microsoft::Bluetooth::Services::BthServ *v12; // r14
  HANDLE v13; // rax
  Microsoft::Bluetooth::Services::BthServ *v14; // rbx
  unsigned int *v15; // r9
  DWORD v16; // r15d
  struct _BLUETOOTH_SDP_RECORD *v17; // rax
  struct _GUID *v18; // r8
  HANDLE v19; // rax
  void *v20; // rdx
  struct _GUID *v21; // r9
  bool v22; // zf
  Microsoft::Bluetooth::Services::BthServ *v23; // rbx
  void *v24; // rcx
  char *v25; // r8
  __int64 v26; // rcx
  void *v27; // rcx
  Microsoft::Bluetooth::Services::BthServ *v28; // r14
  HANDLE ProcessHeap; // rax
  _QWORD *v30; // rsi
  __int64 DeviceInfoList; // rax
  void **v32; // r8
  DWORD LastError; // ebx
  void *v34; // rdx
  HANDLE v35; // rax
  void **v36; // r8
  void *v37; // rdx
  HANDLE v38; // rax
  struct _GUID *v40; // [rsp+20h] [rbp-E0h]
  void *v41; // [rsp+30h] [rbp-D0h]
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int32 v43; // [rsp+58h] [rbp-A8h] BYREF
  Microsoft::Bluetooth::Services::BthServ *FirstService; // [rsp+60h] [rbp-A0h]
  struct _BLUETOOTH_DEVICE_INFO v45; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 v46[8]; // [rsp+690h] [rbp+590h] BYREF
  _BYTE v47[4]; // [rsp+698h] [rbp+598h] BYREF
  int v48; // [rsp+69Ch] [rbp+59Ch]
  WORD wHour; // [rsp+6A0h] [rbp+5A0h]
  WORD wMinute; // [rsp+6A2h] [rbp+5A2h]
  WORD wSecond; // [rsp+6A6h] [rbp+5A6h]
  __int128 v52; // [rsp+6BAh] [rbp+5BAh]
  _BYTE v53[1782]; // [rsp+6CAh] [rbp+5CAh] BYREF

  v4 = 0;
  LODWORD(hObject) = (_DWORD)a3;
  *(_QWORD *)&v45.stLastSeen.wYear = this;
  v6 = (unsigned int)a3;
  v7 = a2;
  if ( a4 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (LOBYTE(a2) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
    {
      LOBYTE(a2) = 0;
    }
    if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      BYTE1(v41) = 0;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_s_guid_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
  }
  SDPPriLangServiceName = 1060;
  if ( !this )
  {
    hObject = 0;
    v28 = 0;
    ProcessHeap = GetProcessHeap();
    v30 = HeapAlloc(ProcessHeap, 8u, 0x10u);
    if ( v30 )
    {
      DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
      v30[1] = DeviceInfoList;
      if ( DeviceInfoList == -1 )
      {
        v38 = GetProcessHeap();
        HeapFree(v38, 0, v30);
      }
      else
      {
        if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_BTHPORT_DEVICE_INTERFACE, 0, 18, 0, 0) )
        {
          v28 = (Microsoft::Bluetooth::Services::BthServ *)v30;
          if ( !(unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(
                                (Microsoft::Bluetooth::Services::BthServ *)v30,
                                &hObject,
                                v32) )
          {
            LastError = GetLastError();
            Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(
              (Microsoft::Bluetooth::Services::BthServ *)v30,
              v34);
            v28 = 0;
            SetLastError(LastError);
          }
        }
        else
        {
          DevObjDestroyDeviceInfoList(v30[1]);
          v35 = GetProcessHeap();
          HeapFree(v35, 0, v30);
        }
        if ( v28 )
        {
          do
          {
            LOBYTE(v41) = 1;
            LODWORD(v40) = 1;
            SDPPriLangServiceName = Microsoft::Bluetooth::Services::BthServ::BthpSetServiceStateEx(
                                      (Microsoft::Bluetooth::Services::BthServ *)hObject,
                                      v7,
                                      (const struct _BLUETOOTH_DEVICE_INFO *)v6,
                                      (unsigned int)a4,
                                      v40,
                                      0,
                                      v41,
                                      0,
                                      0,
                                      1u,
                                      (unsigned __int8)hObject);
            CloseHandle(hObject);
          }
          while ( (unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(v28, &hObject, v36) );
          Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(v28, v37);
        }
      }
    }
    return SDPPriLangServiceName;
  }
  memset(&v45.stLastSeen.wHour, 0, 28);
  memset_0(v47, 0, 0x722u);
  *(_QWORD *)v46 = v7[1];
  v48 = 17;
  memset_0(&v45.szName[10], 0, 0x5C4u);
  *(_QWORD *)&v45.dwSize = 32;
  *(_QWORD *)&v45.fRemembered = 0;
  v45.Address.ullLong = (BTH_ADDR)v7;
  *(_QWORD *)&v45.ulClassofDevice = this;
  *(_DWORD *)&v45.szName[8] = 1480;
  FirstService = (Microsoft::Bluetooth::Services::BthServ *)Microsoft::Bluetooth::Services::BthServ::BluetoothFindFirstServiceEx(
                                                              &v45,
                                                              &v45.szName[8],
                                                              2);
  if ( !FirstService )
    return SDPPriLangServiceName;
  while ( 1 )
  {
    *(_OWORD *)&v45.dwSize = 0;
    if ( *(_DWORD *)&v45.szName[8] != 1480 )
    {
      SetLastError(0x51Au);
LABEL_12:
      v4 = 0;
      goto LABEL_13;
    }
    SetLastError(0xDu);
    if ( (v45.szName[18] & 2) == 0 )
      goto LABEL_12;
    v12 = *(Microsoft::Bluetooth::Services::BthServ **)&v45.szName[24];
    if ( !*(_QWORD *)&v45.szName[24] )
      goto LABEL_12;
    if ( (**(_BYTE **)&v45.szName[24] & 0xF8) != 0x30 )
      goto LABEL_12;
    v13 = GetProcessHeap();
    v14 = (Microsoft::Bluetooth::Services::BthServ *)HeapAlloc(v13, 0, 0x18u);
    if ( !v14 )
      goto LABEL_12;
    v43 = 0;
    v16 = 1168;
    v17 = Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(
            v12,
            (struct _BLUETOOTH_SDP_RECORD *)(*(_QWORD *)&v45.szName[12] + *(unsigned int *)&v45.szName[16]),
            &v43,
            v15);
    *(_QWORD *)v14 = v17;
    if ( v17 )
    {
      v16 = 0;
      *((_QWORD *)v14 + 1) = (char *)v17 + v43;
      v4 = v14;
      if ( Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextClassId(v14, &v45, v18) )
        goto LABEL_23;
      v16 = GetLastError();
      v4 = 0;
    }
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v14);
LABEL_23:
    SetLastError(v16);
    if ( !v4 )
      goto LABEL_12;
    v52 = *(_OWORD *)&v45.dwSize;
    Microsoft::Bluetooth::Services::BthServ::BluetoothFindClassIdClose(v4, v20);
    v4 = 0;
    if ( !a4 )
      break;
    if ( (_QWORD)v52 == *a4 )
    {
      v22 = *((_QWORD *)&v52 + 1) == a4[1];
      goto LABEL_27;
    }
LABEL_13:
    if ( !(unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextService(
                          FirstService,
                          &v45.szName[8],
                          v10) )
      goto LABEL_41;
  }
  v22 = *(_DWORD *)&v45.szName[20] == (_DWORD)hObject;
LABEL_27:
  if ( !v22 )
    goto LABEL_13;
  v23 = *(Microsoft::Bluetooth::Services::BthServ **)&v45.stLastSeen.wYear;
  *(_OWORD *)&v45.dwSize = v52;
  if ( Microsoft::Bluetooth::Services::BthServ::BthpIsTopOfServiceGroup(
         *(Microsoft::Bluetooth::Services::BthServ **)&v45.stLastSeen.wYear,
         v7,
         &v45,
         v21) )
  {
    Microsoft::Bluetooth::Services::BthServ::BthpFindPnpInfo(
      v23,
      v7,
      (const struct _BLUETOOTH_DEVICE_INFO *)&v45.stLastSeen.wHour,
      0);
    if ( (v45.szName[0] & 0xF) == 0xF )
    {
      v48 |= 4u;
      wSecond = v45.stLastSeen.wSecond;
      wHour = v45.stLastSeen.wHour;
      wMinute = v45.stLastSeen.wMinute;
    }
    if ( *(_DWORD *)v7 >= 0x230u )
    {
      SDPPriLangServiceName = BthServClientActivateService(
                                v24,
                                v7 + 1,
                                *(unsigned int *)&v45.szName[16],
                                *(unsigned __int8 *const *)&v45.szName[12]);
      if ( !SDPPriLangServiceName )
      {
        SDPPriLangServiceName = Microsoft::Bluetooth::Services::BthServ::BthpFindSDPPriLangServiceName(
                                  (Microsoft::Bluetooth::Services::BthServ *)&v45.szName[8],
                                  (const struct _BLUETOOTH_SERVICE_RECORD *)v53,
                                  v25);
        if ( SDPPriLangServiceName )
        {
          v26 = *(_QWORD *)&SerialPortServiceClass_UUID.Data1 - v52;
          if ( *(_QWORD *)&SerialPortServiceClass_UUID.Data1 == (_QWORD)v52 )
            v26 = *(_QWORD *)SerialPortServiceClass_UUID.Data4 - *((_QWORD *)&v52 + 1);
          if ( v26 )
            SDPPriLangServiceName = 0;
        }
      }
    }
    else
    {
      SDPPriLangServiceName = 122;
    }
  }
  else
  {
    SDPPriLangServiceName = 1058;
  }
LABEL_41:
  Microsoft::Bluetooth::Services::BthServ::BluetoothFindServiceClose(FirstService, v11);
  if ( !SDPPriLangServiceName )
    return BthServClientUpdateService(v27, 0x72Au, v46, 0);
  return SDPPriLangServiceName;
}

```

## disassembly

```asm
0x180027ea8  push    rbp
0x180027eaa  push    rbx
0x180027eab  push    rsi
0x180027eac  push    rdi
0x180027ead  push    r12
0x180027eaf  push    r13
0x180027eb1  push    r14
0x180027eb3  push    r15
0x180027eb5  lea     rbp, [rsp-0CD8h]
0x180027ebd  sub     rsp, 0DD8h
0x180027ec4  mov     rax, cs:__security_cookie
0x180027ecb  xor     rax, rsp
0x180027ece  mov     [rbp+0D10h+var_50], rax
0x180027ed5  xor     esi, esi
0x180027ed7  mov     dword ptr [rsp+0E10h+hObject], r8d
0x180027edc  mov     qword ptr [rbp+0D10h+var_DA0.stLastSeen.wYear], rcx
0x180027ee0  mov     r12, r9
0x180027ee3  mov     r15d, r8d
0x180027ee6  mov     r13, rdx
0x180027ee9  mov     rbx, rcx
0x180027eec  test    r9, r9
0x180027eef  jz      short loc_180027F4F
0x180027ef1  mov     rcx, cs:WPP_GLOBAL_Control
0x180027ef8  lea     rax, WPP_GLOBAL_Control
0x180027eff  cmp     rcx, rax
0x180027f02  jz      short loc_180027F0C
0x180027f04  cmp     byte ptr [rcx+19h], 4
0x180027f08  mov     dl, 1
0x180027f0a  jnb     short loc_180027F0F
0x180027f0c  mov     dl, sil
0x180027f0f  lea     rax, WPP_RECORDER_INITIALIZED
0x180027f16  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180027f1d  setnz   r8b
0x180027f21  test    dl, dl
0x180027f23  jnz     short loc_180027F2A
0x180027f25  test    r8b, r8b
0x180027f28  jz      short loc_180027F4F
0x180027f2a  mov     r9, [rcx+28h]
0x180027f2e  lea     rax, WPP_b232bbd09fa63021a92d957d702a2cb3_Traceguids
0x180027f35  mov     rcx, [rcx+10h]
0x180027f39  mov     qword ptr [rsp+0E10h+var_DC8], r12
0x180027f3e  mov     qword ptr [rsp+0E10h+var_DD8], rax
0x180027f43  mov     word ptr [rsp+0E10h+var_DE0], 10h
0x180027f4a  call    WPP_RECORDER_AND_TRACE_SF_s_guid_
0x180027f4f  mov     edi, 424h
0x180027f54  test    rbx, rbx
0x180027f57  jz      loc_180028259
0x180027f5d  xor     eax, eax
0x180027f5f  lea     rcx, [rbp+0D10h+var_778]; void *
0x180027f66  xorps   xmm0, xmm0
0x180027f69  mov     qword ptr [rbp+0D10h+var_DA0.stLastUsed.wHour], rax
0x180027f6d  xor     edx, edx; Val
0x180027f6f  mov     dword ptr [rbp+0D10h+var_DA0.szName], eax
0x180027f72  mov     r8d, 722h; Size
0x180027f78  movups  xmmword ptr [rbp+0D10h+var_DA0.stLastSeen.wHour], xmm0
0x180027f7c  call    memset_0
0x180027f81  mov     rax, [r13+8]
0x180027f85  lea     rcx, [rbp+0D10h+var_DA0.szName+14h]; void *
0x180027f89  xor     edx, edx; Val
0x180027f8b  mov     qword ptr [rbp+0D10h+var_780], rax
0x180027f92  mov     r8d, 5C4h; Size
0x180027f98  mov     [rbp+0D10h+var_774], 11h
0x180027fa2  call    memset_0
0x180027fa7  mov     r8d, 2
0x180027fad  mov     qword ptr [rsp+0E10h+var_DA0.dwSize], 20h ; ' '
0x180027fb6  lea     rdx, [rbp+0D10h+var_DA0.szName+10h]
0x180027fba  mov     qword ptr [rbp+0D10h+var_DA0.fRemembered], rsi
0x180027fbe  lea     rcx, [rsp+0E10h+var_DA0]
0x180027fc3  mov     qword ptr [rsp+0E10h+var_DA0.Address], r13
0x180027fc8  mov     qword ptr [rbp+0D10h+var_DA0.ulClassofDevice], rbx
0x180027fcc  mov     dword ptr [rbp+0D10h+var_DA0.szName+10h], 5C8h
0x180027fd3  call    ?BluetoothFindFirstServiceEx@BthServ@Services@Bluetooth@Microsoft@@YAPEAXPEBU_BLUETOOTH_SDP_SEARCH_PARAMS@@PEAU_BLUETOOTH_SERVICE_RECORD@@W4BTH_SDP_QUERY_TYPE@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindFirstServiceEx(_BLUETOOTH_SDP_SEARCH_PARAMS const *,_BLUETOOTH_SERVICE_RECORD *,BTH_SDP_QUERY_TYPE)
0x180027fd8  mov     [rsp+0E10h+var_DB0], rax
0x180027fdd  test    rax, rax
0x180027fe0  jz      loc_1800283DF
0x180027fe6  cmp     dword ptr [rbp+0D10h+var_DA0.szName+10h], 5C8h
0x180027fed  xorps   xmm0, xmm0
0x180027ff0  movups  xmmword ptr [rsp+0E10h+var_DA0.dwSize], xmm0
0x180027ff5  jz      short loc_180028021
0x180027ff7  mov     ecx, 51Ah; dwErrCode
0x180027ffc  call    cs:__imp_SetLastError
0x180028003  nop     dword ptr [rax+rax+00h]
0x180028008  xor     esi, esi
0x18002800a  mov     rcx, [rsp+0E10h+var_DB0]; this
0x18002800f  lea     rdx, [rbp+0D10h+var_DA0.szName+10h]; void *
0x180028013  call    ?BluetoothFindNextService@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAU_BLUETOOTH_SERVICE_RECORD@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextService(void *,_BLUETOOTH_SERVICE_RECORD *)
0x180028018  test    eax, eax
0x18002801a  jnz     short loc_180027FE6
0x18002801c  jmp     loc_18002822C
0x180028021  mov     ecx, 0Dh; dwErrCode
0x180028026  call    cs:__imp_SetLastError
0x18002802d  nop     dword ptr [rax+rax+00h]
0x180028032  test    byte ptr [rbp+0D10h+var_DA0.szName+24h], 2
0x180028036  jz      short loc_180028008
0x180028038  mov     r14, qword ptr [rbp+0D10h+var_DA0.szName+30h]
0x18002803c  xor     r15d, r15d
0x18002803f  test    r14, r14
0x180028042  jz      short loc_180028008
0x180028044  mov     al, [r14]
0x180028047  and     al, 0F8h
0x180028049  cmp     al, 30h ; '0'
0x18002804b  jnz     short loc_180028008
0x18002804d  call    cs:__imp_GetProcessHeap
0x180028054  nop     dword ptr [rax+rax+00h]
0x180028059  xor     edx, edx; dwFlags
0x18002805b  lea     r8d, [r15+18h]; dwBytes
0x18002805f  mov     rcx, rax; hHeap
0x180028062  call    cs:__imp_HeapAlloc
0x180028069  nop     dword ptr [rax+rax+00h]
0x18002806e  mov     rbx, rax
0x180028071  test    rax, rax
0x180028074  jz      short loc_180028008
0x180028076  mov     edx, dword ptr [rbp+0D10h+var_DA0.szName+20h]
0x180028079  lea     r8, [rsp+0E10h+var_DB8]; void *
0x18002807e  add     rdx, qword ptr [rbp+0D10h+var_DA0.szName+18h]; struct _BLUETOOTH_SDP_RECORD *
0x180028082  mov     rcx, r14; this
0x180028085  mov     [rsp+0E10h+var_DB8], r15d
0x18002808a  mov     r15d, 490h
0x180028090  call    ?BthpInnerRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAXPEAK@Z; Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(_BLUETOOTH_SDP_RECORD *,void *,ulong *)
0x180028095  xor     r14d, r14d
0x180028098  mov     [rbx], rax
0x18002809b  mov     rcx, rax
0x18002809e  test    rax, rax
0x1800280a1  jz      short loc_1800280D7
0x1800280a3  mov     eax, [rsp+0E10h+var_DB8]
0x1800280a7  lea     rdx, [rsp+0E10h+var_DA0]; void *
0x1800280ac  add     rax, rcx
0x1800280af  mov     r15d, r14d
0x1800280b2  mov     rcx, rbx; this
0x1800280b5  mov     [rbx+8], rax
0x1800280b9  mov     rsi, rbx
0x1800280bc  call    ?BluetoothFindNextClassId@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAU_GUID@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextClassId(void *,_GUID *)
0x1800280c1  test    eax, eax
0x1800280c3  jnz     short loc_1800280F7
0x1800280c5  call    cs:__imp_GetLastError
0x1800280cc  nop     dword ptr [rax+rax+00h]
0x1800280d1  mov     r15d, eax
0x1800280d4  mov     esi, r14d
0x1800280d7  call    cs:__imp_GetProcessHeap
0x1800280de  nop     dword ptr [rax+rax+00h]
0x1800280e3  mov     r8, rbx; lpMem
0x1800280e6  xor     edx, edx; dwFlags
0x1800280e8  mov     rcx, rax; hHeap
0x1800280eb  call    cs:__imp_HeapFree
0x1800280f2  nop     dword ptr [rax+rax+00h]
0x1800280f7  mov     ecx, r15d; dwErrCode
0x1800280fa  call    cs:__imp_SetLastError
0x180028101  nop     dword ptr [rax+rax+00h]
0x180028106  test    rsi, rsi
0x180028109  jz      loc_180028008
0x18002810f  movups  xmm0, xmmword ptr [rsp+0E10h+var_DA0.dwSize]
0x180028114  mov     rcx, rsi; this
0x180028117  movdqu  [rbp+0D10h+var_756], xmm0
0x18002811f  call    ?BluetoothFindClassIdClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindClassIdClose(void *)
0x180028124  xor     esi, esi
0x180028126  test    r12, r12
0x180028129  jz      short loc_18002817D
0x18002812b  mov     rax, qword ptr [rbp+0D10h+var_756]
0x180028132  cmp     rax, [r12]
0x180028136  jnz     loc_18002800A
0x18002813c  mov     rax, qword ptr [rbp+0D10h+var_756+8]
0x180028143  cmp     rax, [r12+8]
0x180028148  jnz     loc_18002800A
0x18002814e  movups  xmm0, [rbp+0D10h+var_756]
0x180028155  mov     rbx, qword ptr [rbp+0D10h+var_DA0.stLastSeen.wYear]
0x180028159  lea     r8, [rsp+0E10h+var_DA0]; struct _BLUETOOTH_DEVICE_INFO *
0x18002815e  mov     rdx, r13; void *
0x180028161  mov     rcx, rbx; this
0x180028164  movdqu  xmmword ptr [rsp+0E10h+var_DA0.dwSize], xmm0
0x18002816a  call    ?BthpIsTopOfServiceGroup@BthServ@Services@Bluetooth@Microsoft@@YAEPEAXPEBU_BLUETOOTH_DEVICE_INFO@@U_GUID@@@Z; Microsoft::Bluetooth::Services::BthServ::BthpIsTopOfServiceGroup(void *,_BLUETOOTH_DEVICE_INFO const *,_GUID)
0x18002816f  test    al, al
0x180028171  jnz     short loc_180028186
0x180028173  mov     edi, 422h
0x180028178  jmp     loc_18002822C
0x18002817d  mov     eax, dword ptr [rsp+0E10h+hObject]
0x180028181  cmp     dword ptr [rbp+0D10h+var_DA0.szName+28h], eax
0x180028184  jmp     short loc_180028148
0x180028186  xor     r9d, r9d; struct _BTH_PNP_INFO *
0x180028189  lea     r8, [rbp+0D10h+var_DA0.stLastSeen.wHour]; struct _BLUETOOTH_DEVICE_INFO *
0x18002818d  mov     rdx, r13; void *
0x180028190  mov     rcx, rbx; this
0x180028193  call    ?BthpFindPnpInfo@BthServ@Services@Bluetooth@Microsoft@@YAXPEAXPEBU_BLUETOOTH_DEVICE_INFO@@PEAU_BTH_PNP_INFO@@H@Z; Microsoft::Bluetooth::Services::BthServ::BthpFindPnpInfo(void *,_BLUETOOTH_DEVICE_INFO const *,_BTH_PNP_INFO *,int)
0x180028198  mov     eax, dword ptr [rbp+0D10h+var_DA0.szName]
0x18002819b  and     eax, 0Fh
0x18002819e  cmp     al, 0Fh
0x1800281a0  jnz     short loc_1800281CA
0x1800281a2  movzx   eax, [rbp+0D10h+var_DA0.stLastSeen.wSecond]
0x1800281a6  or      [rbp+0D10h+var_774], 4
0x1800281ad  mov     [rbp+0D10h+var_76A], ax
0x1800281b4  movzx   eax, [rbp+0D10h+var_DA0.stLastSeen.wHour]
0x1800281b8  mov     [rbp+0D10h+var_770], ax
0x1800281bf  movzx   eax, [rbp+0D10h+var_DA0.stLastSeen.wMinute]
0x1800281c3  mov     [rbp+0D10h+var_76E], ax
0x1800281ca  cmp     dword ptr [r13+0], 230h
0x1800281d2  jnb     short loc_1800281DB
0x1800281d4  mov     edi, 7Ah ; 'z'
0x1800281d9  jmp     short loc_18002822C
0x1800281db  mov     r9, qword ptr [rbp+0D10h+var_DA0.szName+18h]; unsigned __int8 *
0x1800281df  lea     rdx, [r13+8]; unsigned __int64 *
0x1800281e3  mov     r8d, dword ptr [rbp+0D10h+var_DA0.szName+20h]; unsigned int
0x1800281e7  call    ?BthServClientActivateService@@YAKQEAXPEB_KKQEAE@Z; BthServClientActivateService(void * const,unsigned __int64 const *,ulong,uchar * const)
0x1800281ec  mov     edi, eax
0x1800281ee  test    eax, eax
0x1800281f0  jnz     short loc_18002822C
0x1800281f2  lea     rdx, [rbp+0D10h+var_746]; struct _BLUETOOTH_SERVICE_RECORD *
0x1800281f9  lea     rcx, [rbp+0D10h+var_DA0.szName+10h]; this
0x1800281fd  call    ?BthpFindSDPPriLangServiceName@BthServ@Services@Bluetooth@Microsoft@@YAKPEBU_BLUETOOTH_SERVICE_RECORD@@PEADK@Z; Microsoft::Bluetooth::Services::BthServ::BthpFindSDPPriLangServiceName(_BLUETOOTH_SERVICE_RECORD const *,char *,ulong)
0x180028202  mov     edi, eax
0x180028204  test    eax, eax
0x180028206  jz      short loc_18002822C
0x180028208  mov     rcx, qword ptr cs:SerialPortServiceClass_UUID.Data1
0x18002820f  sub     rcx, qword ptr [rbp+0D10h+var_756]
0x180028216  jnz     short loc_180028226
0x180028218  mov     rcx, qword ptr cs:SerialPortServiceClass_UUID.Data4
0x18002821f  sub     rcx, qword ptr [rbp+0D10h+var_756+8]
0x180028226  test    rcx, rcx
0x180028229  cmovnz  edi, esi
0x18002822c  mov     rcx, [rsp+0E10h+var_DB0]; this
0x180028231  call    ?BluetoothFindServiceClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindServiceClose(void *)
0x180028236  test    edi, edi
0x180028238  jnz     loc_1800283DF
0x18002823e  xor     r9d, r9d; int
0x180028241  lea     r8, [rbp+0D10h+var_780]; unsigned __int8 *
0x180028248  mov     edx, 72Ah; unsigned int
0x18002824d  call    ?BthServClientUpdateService@@YAKPEAXKQEAEH@Z; BthServClientUpdateService(void *,ulong,uchar * const,int)
0x180028252  mov     edi, eax
0x180028254  jmp     loc_1800283DF
0x180028259  mov     [rsp+0E10h+hObject], rsi; unsigned __int8
0x18002825e  mov     r14, rsi
0x180028261  call    cs:__imp_GetProcessHeap
0x180028268  nop     dword ptr [rax+rax+00h]
0x18002826d  mov     edx, 8; dwFlags
0x180028272  mov     rcx, rax; hHeap
0x180028275  lea     r8d, [rdx+8]; dwBytes
0x180028279  call    cs:__imp_HeapAlloc
0x180028280  nop     dword ptr [rax+rax+00h]
0x180028285  xor     ebx, ebx
0x180028287  mov     rsi, rax
0x18002828a  test    rax, rax
0x18002828d  jz      loc_1800283DF
0x180028293  xor     r9d, r9d
0x180028296  mov     [rsp+0E10h+var_DF0], rbx
0x18002829b  xor     r8d, r8d
0x18002829e  xor     edx, edx
0x1800282a0  xor     ecx, ecx
0x1800282a2  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800282a9  nop     dword ptr [rax+rax+00h]
0x1800282ae  mov     [rsi+8], rax
0x1800282b2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800282b6  jz      loc_1800283BF
0x1800282bc  mov     qword ptr [rsp+0E10h+var_DE8], rbx
0x1800282c1  lea     r9d, [rbx+12h]
0x1800282c5  xor     r8d, r8d
0x1800282c8  mov     [rsp+0E10h+var_DF0], rbx
0x1800282cd  lea     rdx, GUID_BTHPORT_DEVICE_INTERFACE
0x1800282d4  mov     rcx, rax
0x1800282d7  call    cs:__imp_DevObjGetClassDevs
0x1800282de  nop     dword ptr [rax+rax+00h]
0x1800282e3  test    eax, eax
0x1800282e5  jz      short loc_180028326
0x1800282e7  lea     rdx, [rsp+0E10h+hObject]; void *
0x1800282ec  mov     rcx, rsi; this
0x1800282ef  mov     r14, rsi
0x1800282f2  call    ?BluetoothFindNextRadio@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(void *,void * *)
0x1800282f7  test    eax, eax
0x1800282f9  jnz     short loc_180028356
0x1800282fb  call    cs:__imp_GetLastError
0x180028302  nop     dword ptr [rax+rax+00h]
0x180028307  mov     rcx, rsi; this
0x18002830a  mov     ebx, eax
0x18002830c  call    ?BluetoothFindRadioClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(void *)
0x180028311  mov     ecx, ebx; dwErrCode
0x180028313  xor     r14d, r14d
0x180028316  call    cs:__imp_SetLastError
0x18002831d  nop     dword ptr [rax+rax+00h]
0x180028322  xor     ebx, ebx
0x180028324  jmp     short loc_180028356
0x180028326  mov     rcx, [rsi+8]
0x18002832a  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180028331  nop     dword ptr [rax+rax+00h]
0x180028336  call    cs:__imp_GetProcessHeap
0x18002833d  nop     dword ptr [rax+rax+00h]
0x180028342  mov     r8, rsi; lpMem
0x180028345  xor     edx, edx; dwFlags
0x180028347  mov     rcx, rax; hHeap
0x18002834a  call    cs:__imp_HeapFree
0x180028351  nop     dword ptr [rax+rax+00h]
0x180028356  test    r14, r14
0x180028359  jz      loc_1800283DF
0x18002835f  mov     rcx, [rsp+0E10h+hObject]; this
0x180028364  mov     r9, r12; unsigned int
0x180028367  mov     [rsp+0E10h+var_DC8], 1; unsigned __int8
0x18002836c  mov     r8d, r15d; struct _BLUETOOTH_DEVICE_INFO *
0x18002836f  mov     [rsp+0E10h+var_DD0], bl; unsigned __int8
0x180028373  mov     rdx, r13; void *
0x180028376  mov     [rsp+0E10h+var_DD8], bl; unsigned __int8
0x18002837a  mov     byte ptr [rsp+0E10h+var_DE0], 1; void *
0x18002837f  mov     qword ptr [rsp+0E10h+var_DE8], rbx; unsigned int
0x180028384  mov     dword ptr [rsp+0E10h+var_DF0], 1; struct _GUID *
0x18002838c  call    ?BthpSetServiceStateEx@BthServ@Services@Bluetooth@Microsoft@@YAKPEAXPEBU_BLUETOOTH_DEVICE_INFO@@KPEBU_GUID@@K0EEEE@Z; Microsoft::Bluetooth::Services::BthServ::BthpSetServiceStateEx(void *,_BLUETOOTH_DEVICE_INFO const *,ulong,_GUID const *,ulong,void *,uchar,uchar,uchar,uchar)
  ... truncated ...
```
