# Microsoft::Bluetooth::Services::BthServ::BthpIsTopOfServiceGroup(void *,_BLUETOOTH_DEVICE_INFO const *,_GUID)

- ea: `0x180026dec`
- end: `0x180027781`
- name: `?BthpIsTopOfServiceGroup@BthServ@Services@Bluetooth@Microsoft@@YAEPEAXPEBU_BLUETOOTH_DEVICE_INFO@@U_GUID@@@Z`
- size: `2453`
- prototype: `char __fastcall(Microsoft::Bluetooth::Services::BthServ *this, void *, const struct _BLUETOOTH_DEVICE_INFO *, struct _GUID *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180027ea8`

## callees

- `0x1800017a0`
- `0x18000270c`
- `0x180012004`
- `0x1800120b8`
- `0x18001245c`
- `0x180017944`
- `0x18002472c`
- `0x1800247d0`
- `0x180024a1c`
- `0x180024c84`
- `0x180024f34`
- `0x180026c70`
- `0x180026dec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027187`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027450`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027187`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027450`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026fd7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027001`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800272ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027357`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800275e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027616`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026fd7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027001`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800272ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027357`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800275e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027616`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002736b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800275fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002762a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002736b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800275fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002762a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026feb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027015`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800272e3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026feb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027015`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800272e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027346`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027346`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027289`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002729f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002737a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027289`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002729f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002737a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026ee9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026ee9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180026f90`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180026f90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027747`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027747`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800270a1`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800270a1`

## string_xrefs

- `0x180026edb`: `System\CurrentControlSet\Services\BTHPORT\Parameters\ServiceGroups`

## pseudocode

```c
char __fastcall Microsoft::Bluetooth::Services::BthServ::BthpIsTopOfServiceGroup(
        Microsoft::Bluetooth::Services::BthServ *this,
        void *a2,
        const struct _BLUETOOTH_DEVICE_INFO *a3,
        struct _GUID *a4)
{
  int v4; // ecx
  int v5; // edx
  int v6; // r9d
  int v7; // r10d
  char v8; // r12
  int v9; // r11d
  int v10; // ebx
  int v11; // edi
  int v12; // esi
  _QWORD *v13; // rcx
  char v14; // dl
  bool v15; // r8
  DWORD v16; // ecx
  unsigned __int64 v17; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v19; // rax
  DWORD v20; // ebx
  WCHAR *v21; // rdi
  HANDLE v22; // rax
  void *v23; // rax
  BYTE *v24; // r14
  DWORD v25; // esi
  unsigned __int64 v26; // rdx
  __int64 v27; // r8
  _BYTE *v28; // rcx
  _UNKNOWN **v29; // rax
  BYTE *v30; // rdi
  __int64 v31; // rsi
  Microsoft::Bluetooth::Services::BthServ *FirstServiceInternal; // rax
  Microsoft::Bluetooth::Services::BthServ *v33; // rbx
  Microsoft::Bluetooth::Services::BthServ *v34; // rsi
  struct _BLUETOOTH_SERVICE_RECORD *v35; // r8
  Microsoft::Bluetooth::Services::BthServ *v36; // rdi
  HANDLE v37; // rax
  Microsoft::Bluetooth::Services::BthServ *v38; // rbx
  unsigned int *v39; // r9
  DWORD LastError; // r14d
  struct _BLUETOOTH_SDP_RECORD *v41; // rax
  struct _GUID *v42; // r8
  HANDLE v43; // rax
  void *v44; // rdx
  __int64 v45; // r9
  _WORD *v46; // rbx
  __int64 v47; // rdi
  void *v48; // rdx
  Microsoft::Bluetooth::Services::BthServ *v49; // rcx
  char v50; // dl
  HANDLE v51; // rax
  HANDLE v52; // rax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int lpcbMaxSubKeyLen; // [rsp+28h] [rbp-D8h]
  int lpcbMaxValueNameLen; // [rsp+40h] [rbp-C0h]
  char v57; // [rsp+70h] [rbp-90h]
  DWORD cbMaxValueNameLen; // [rsp+74h] [rbp-8Ch] BYREF
  Microsoft::Bluetooth::Services::BthServ *v59; // [rsp+78h] [rbp-88h]
  unsigned int v60; // [rsp+80h] [rbp-80h]
  DWORD v61; // [rsp+84h] [rbp-7Ch]
  DWORD cValues; // [rsp+88h] [rbp-78h] BYREF
  DWORD cbMaxValueLen; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v64; // [rsp+90h] [rbp-70h]
  DWORD Type; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned __int32 v66; // [rsp+98h] [rbp-68h] BYREF
  LPVOID lpMem; // [rsp+A0h] [rbp-60h]
  WCHAR *v68; // [rsp+A8h] [rbp-58h]
  HKEY hKey; // [rsp+B0h] [rbp-50h] BYREF
  DWORD cbData; // [rsp+B8h] [rbp-48h] BYREF
  DWORD cchValueName; // [rsp+BCh] [rbp-44h] BYREF
  void *v72; // [rsp+C0h] [rbp-40h]
  Microsoft::Bluetooth::Services::BthServ *v73; // [rsp+C8h] [rbp-38h]
  const struct _BLUETOOTH_DEVICE_INFO *v74; // [rsp+D0h] [rbp-30h]
  __int128 v75; // [rsp+D8h] [rbp-28h] BYREF
  Microsoft::Bluetooth::Services::BthServ *v76; // [rsp+E8h] [rbp-18h]
  __int64 v77; // [rsp+F0h] [rbp-10h]
  int v78; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v79[4]; // [rsp+104h] [rbp+4h] BYREF
  __int64 v80; // [rsp+108h] [rbp+8h]
  unsigned int v81; // [rsp+110h] [rbp+10h]
  char v82; // [rsp+114h] [rbp+14h]
  Microsoft::Bluetooth::Services::BthServ *v83; // [rsp+120h] [rbp+20h]
  unsigned __int16 v84[40]; // [rsp+6D0h] [rbp+5D0h] BYREF
  unsigned __int16 v85[40]; // [rsp+720h] [rbp+620h] BYREF

  v73 = this;
  v4 = a3->Address.rgBytes[6];
  v72 = a2;
  v5 = a3->Address.rgBytes[5];
  v6 = a3->Address.rgBytes[3];
  v7 = a3->Address.rgBytes[2];
  v8 = 1;
  v9 = a3->Address.rgBytes[1];
  v10 = a3->Address.rgBytes[0];
  v11 = *((unsigned __int16 *)&a3->dwSize + 3);
  v12 = *((unsigned __int16 *)&a3->dwSize + 2);
  v74 = a3;
  hKey = 0;
  v57 = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  v59 = 0;
  if ( (int)StringCbPrintfW(
              v84,
              0x4Eu,
              L"{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
              a3->dwSize,
              v12,
              v11,
              v10,
              v9,
              v7,
              v6,
              a3->Address.rgBytes[4],
              v5,
              v4,
              a3->Address.rgBytes[7]) < 0 )
    goto LABEL_119;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\BTHPORT\\Parameters\\ServiceGroups",
         0,
         0x20019u,
         &hKey) )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v14 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
      v14 = 0;
    v15 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v14 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_119;
    goto LABEL_118;
  }
  if ( RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0) || !cValues )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v14 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
      v14 = 0;
    v15 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v14 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_119;
LABEL_118:
    WPP_RECORDER_AND_TRACE_SF_s(v13[2], v14, v15, v13[5]);
    goto LABEL_119;
  }
  v16 = cbMaxValueNameLen + 1;
  if ( cbMaxValueNameLen + 1 < cbMaxValueNameLen )
  {
    cbMaxValueNameLen = -1;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v14 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u) )
      v14 = 0;
    v15 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v14 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_119;
    goto LABEL_118;
  }
  ++cbMaxValueNameLen;
  v17 = 2LL * v16;
  if ( v17 > 0xFFFFFFFF )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v14 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u) )
      v14 = 0;
    v15 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v14 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_119;
    goto LABEL_118;
  }
  ProcessHeap = GetProcessHeap();
  v19 = (WCHAR *)HeapAlloc(ProcessHeap, 0, (unsigned int)v17);
  v20 = cbMaxValueLen;
  v21 = v19;
  v68 = v19;
  v22 = GetProcessHeap();
  v23 = HeapAlloc(v22, 0, v20);
  lpMem = v23;
  v24 = (BYTE *)v23;
  if ( !v21 || !v23 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v50 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u) )
      v50 = 0;
    if ( v50 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v50,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
    if ( v24 )
      goto LABEL_98;
    goto LABEL_99;
  }
  v25 = 0;
  v61 = 0;
  if ( !cValues )
    goto LABEL_98;
  while ( 1 )
  {
    cbData = cbMaxValueLen;
    cchValueName = cbMaxValueNameLen;
    Type = 0;
    v60 = 0;
    if ( RegEnumValueW(hKey, v25, v21, &cchValueName, 0, &Type, v24, &cbData) )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (LOBYTE(v26) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u) )
      {
        LOBYTE(v26) = 0;
      }
      if ( (_BYTE)v26 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v27) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v26, v27, *((_QWORD *)WPP_GLOBAL_Control + 5));
      }
LABEL_89:
      v49 = v59;
      if ( v59 )
        goto LABEL_82;
      goto LABEL_98;
    }
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (LOBYTE(v26) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u) )
    {
      LOBYTE(v26) = 0;
    }
    v29 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
    LOBYTE(v27) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v26 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_AND_TRACE_SF_sS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v26,
        v27,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        phkResult,
        lpcbMaxSubKeyLen,
        23,
        (__int64)&WPP_b232bbd09fa63021a92d957d702a2cb3_Traceguids,
        lpcbMaxValueNameLen,
        (__int64)v21);
      v28 = WPP_GLOBAL_Control;
      v29 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
    }
    if ( Type != 7 )
    {
      if ( v28 == (_BYTE *)&WPP_GLOBAL_Control || (LOBYTE(v26) = 1, v28[25] < 3u) )
        LOBYTE(v26) = 0;
      if ( (_BYTE)v26 || v29 != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)v28 + 2), v26, v29 != &WPP_RECORDER_INITIALIZED, *((_QWORD *)v28 + 5));
      goto LABEL_72;
    }
    v30 = v24;
    if ( *(_WORD *)v24 )
    {
      while ( 1 )
      {
        v31 = -1;
        do
          ++v31;
        while ( *(_WORD *)&v30[2 * v31] );
        if ( !(unsigned int)_o__wcsicmp(v30, v84, v27, 0) )
          break;
        ++v60;
        v30 += 2 * v31 + 2;
        if ( !*(_WORD *)v30 )
          goto LABEL_43;
      }
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (LOBYTE(v26) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
      {
        LOBYTE(v26) = 0;
      }
      if ( (_BYTE)v26 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v27) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v26, v27, *((_QWORD *)WPP_GLOBAL_Control + 5));
      }
      v57 = 1;
LABEL_43:
      v25 = v61;
    }
    if ( v57 )
    {
      memset_0(v79, 0, 0x5C4u);
      *(_QWORD *)&v75 = 32;
      v77 = 0;
      *((_QWORD *)&v75 + 1) = v72;
      v76 = v73;
      v78 = 1480;
      FirstServiceInternal = (Microsoft::Bluetooth::Services::BthServ *)Microsoft::Bluetooth::Services::BthServ::BluetoothFindFirstServiceInternal(
                                                                          (__int64)&v75,
                                                                          &v78,
                                                                          2u);
      v59 = FirstServiceInternal;
      if ( FirstServiceInternal )
        break;
    }
LABEL_71:
    v21 = v68;
LABEL_72:
    v61 = ++v25;
    if ( v25 >= cValues )
      goto LABEL_89;
  }
  v33 = FirstServiceInternal;
  while ( 1 )
  {
    v75 = 0;
    v64 = 0;
    v34 = 0;
    if ( v78 == 1480 )
      break;
    SetLastError(0x51Au);
LABEL_69:
    if ( !(unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextService(v33, &v78, v35) )
    {
      Microsoft::Bluetooth::Services::BthServ::BluetoothFindServiceClose(v33, v48);
      v25 = v61;
      v59 = 0;
      goto LABEL_71;
    }
  }
  SetLastError(0xDu);
  if ( (v82 & 2) == 0 )
    goto LABEL_69;
  v36 = v83;
  if ( !v83 || (*(_BYTE *)v83 & 0xF8) != 0x30 )
    goto LABEL_69;
  v37 = GetProcessHeap();
  v38 = (Microsoft::Bluetooth::Services::BthServ *)HeapAlloc(v37, 0, 0x18u);
  if ( !v38 )
  {
LABEL_68:
    v33 = v59;
    goto LABEL_69;
  }
  v66 = 0;
  LastError = 1168;
  v41 = Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(
          v36,
          (struct _BLUETOOTH_SDP_RECORD *)(v80 + v81),
          &v66,
          v39);
  *(_QWORD *)v38 = v41;
  if ( !v41 )
    goto LABEL_56;
  LastError = 0;
  *((_QWORD *)v38 + 1) = (char *)v41 + v66;
  v34 = v38;
  if ( !Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextClassId(v38, &v75, v42) )
  {
    LastError = GetLastError();
    v34 = 0;
LABEL_56:
    v43 = GetProcessHeap();
    HeapFree(v43, 0, v38);
  }
  SetLastError(LastError);
  if ( !v34
    || (Microsoft::Bluetooth::Services::BthServ::BluetoothFindClassIdClose(v34, v44), v75 == *(_OWORD *)&v74->dwSize) )
  {
    v24 = (BYTE *)lpMem;
    goto LABEL_68;
  }
  lpcbMaxValueNameLen = BYTE10(v75);
  if ( (int)StringCbPrintfW(v85, 0x4Eu, L"{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}") < 0 )
    goto LABEL_81;
  v24 = (BYTE *)lpMem;
  v46 = lpMem;
  if ( !*(_WORD *)lpMem )
    goto LABEL_68;
  while ( 1 )
  {
    v47 = -1;
    do
      ++v47;
    while ( v46[v47] );
    if ( !(unsigned int)_o__wcsicmp(v46, v85, v35, v45) )
    {
      v26 = v60;
      if ( v64 < v60 )
        break;
    }
    v46 += v47 + 1;
    ++v64;
    if ( !*v46 )
      goto LABEL_68;
  }
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    v8 = 0;
  if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v26) = v8;
    LOBYTE(v35) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v26,
      (_DWORD)v35,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  }
  v8 = 0;
LABEL_81:
  v49 = v59;
LABEL_82:
  Microsoft::Bluetooth::Services::BthServ::BluetoothFindServiceClose(v49, (void *)v26);
LABEL_98:
  v51 = GetProcessHeap();
  HeapFree(v51, 0, lpMem);
  v21 = v68;
LABEL_99:
  if ( v21 )
  {
    v52 = GetProcessHeap();
    HeapFree(v52, 0, v21);
  }
LABEL_119:
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x180026dec  mov     [rsp-8+arg_18], rbx
0x180026df1  push    rbp
0x180026df2  push    rsi
0x180026df3  push    rdi
0x180026df4  push    r12
0x180026df6  push    r13
0x180026df8  push    r14
0x180026dfa  push    r15
0x180026dfc  lea     rbp, [rsp-680h]
0x180026e04  sub     rsp, 780h
0x180026e0b  mov     rax, cs:__security_cookie
0x180026e12  xor     rax, rsp
0x180026e15  mov     [rbp+6B0h+var_40], rax
0x180026e1c  mov     r14, r8
0x180026e1f  mov     [rbp+6B0h+var_6E8], rcx
0x180026e23  movzx   ecx, byte ptr [r8+0Eh]
0x180026e28  xor     eax, eax
0x180026e2a  mov     [rbp+6B0h+var_6F0], rdx
0x180026e2e  movzx   edx, byte ptr [r8+0Dh]
0x180026e33  movzx   r9d, byte ptr [r14+0Bh]
0x180026e38  movzx   r10d, byte ptr [r14+0Ah]
0x180026e3d  lea     r12d, [rax+1]
0x180026e41  movzx   r11d, byte ptr [r14+9]
0x180026e46  movzx   ebx, byte ptr [r14+8]
0x180026e4b  movzx   edi, word ptr [r14+6]
0x180026e50  movzx   esi, word ptr [r14+4]
0x180026e55  mov     [rbp+6B0h+var_6E0], r8
0x180026e59  mov     [rbp+6B0h+hKey], rax
0x180026e5d  mov     [rsp+7B0h+var_740], al
0x180026e61  mov     [rbp+6B0h+cValues], eax
0x180026e64  mov     [rsp+7B0h+cbMaxValueNameLen], eax
0x180026e68  mov     [rbp+6B0h+cbMaxValueLen], eax
0x180026e6b  mov     [rsp+7B0h+var_738], rax
0x180026e70  movzx   eax, byte ptr [r8+0Fh]
0x180026e75  movzx   r8d, byte ptr [r8+0Ch]
0x180026e7a  mov     [rsp+7B0h+var_748], eax
0x180026e7e  mov     [rsp+7B0h+var_750], ecx
0x180026e82  lea     rcx, [rbp+6B0h+var_E0]; unsigned __int16 *
0x180026e89  mov     dword ptr [rsp+7B0h+lpftLastWriteTime], edx
0x180026e8d  lea     edx, [r12+4Dh]; unsigned __int64
0x180026e92  mov     dword ptr [rsp+7B0h+lpcbSecurityDescriptor], r8d
0x180026e97  lea     r8, a08lx04x04x02x0; "{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%"...
0x180026e9e  mov     dword ptr [rsp+7B0h+lpcbMaxValueLen], r9d
0x180026ea3  mov     r9d, [r14]
0x180026ea6  mov     dword ptr [rsp+7B0h+lpcbMaxValueNameLen], r10d
0x180026eab  mov     dword ptr [rsp+7B0h+lpcValues], r11d
0x180026eb0  mov     dword ptr [rsp+7B0h+lpcbMaxClassLen], ebx
0x180026eb4  mov     dword ptr [rsp+7B0h+lpcbMaxSubKeyLen], edi
0x180026eb8  mov     dword ptr [rsp+7B0h+phkResult], esi
0x180026ebc  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026ec1  test    eax, eax
0x180026ec3  js      loc_18002773E
0x180026ec9  lea     rax, [rbp+6B0h+hKey]
0x180026ecd  mov     r9d, 20019h; samDesired
0x180026ed3  xor     r8d, r8d; ulOptions
0x180026ed6  mov     [rsp+7B0h+phkResult], rax; phkResult
0x180026edb  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\BT"...
0x180026ee2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026ee9  call    cs:__imp_RegOpenKeyExW
0x180026ef0  nop     dword ptr [rax+rax+00h]
0x180026ef5  xor     r9d, r9d; lpReserved
0x180026ef8  test    eax, eax
0x180026efa  jz      short loc_180026F52
0x180026efc  mov     rcx, cs:WPP_GLOBAL_Control
0x180026f03  lea     r15, WPP_GLOBAL_Control
0x180026f0a  cmp     rcx, r15
0x180026f0d  jz      short loc_180026F18
0x180026f0f  cmp     byte ptr [rcx+19h], 4
0x180026f13  mov     dl, r12b
0x180026f16  jnb     short loc_180026F1B
0x180026f18  mov     dl, r9b
0x180026f1b  lea     r13, WPP_RECORDER_INITIALIZED
0x180026f22  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180026f29  setnz   r8b
0x180026f2d  test    dl, dl
0x180026f2f  jnz     short loc_180026F3A
0x180026f31  test    r8b, r8b
0x180026f34  jz      loc_18002773E
0x180026f3a  lea     rax, WPP_b232bbd09fa63021a92d957d702a2cb3_Traceguids
0x180026f41  mov     [rsp+7B0h+lpcValues], rax
0x180026f46  mov     word ptr [rsp+7B0h+lpcbMaxClassLen], 11h
0x180026f4d  jmp     loc_180027731
0x180026f52  mov     rcx, [rbp+6B0h+hKey]; hKey
0x180026f56  lea     rax, [rbp+6B0h+cbMaxValueLen]
0x180026f5a  mov     [rsp+7B0h+lpftLastWriteTime], r9; lpftLastWriteTime
0x180026f5f  xor     r8d, r8d; lpcchClass
0x180026f62  mov     [rsp+7B0h+lpcbSecurityDescriptor], r9; lpcbSecurityDescriptor
0x180026f67  xor     edx, edx; lpClass
0x180026f69  mov     [rsp+7B0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180026f6e  lea     rax, [rsp+7B0h+cbMaxValueNameLen]
0x180026f73  mov     [rsp+7B0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180026f78  lea     rax, [rbp+6B0h+cValues]
0x180026f7c  mov     [rsp+7B0h+lpcValues], rax; lpcValues
0x180026f81  mov     [rsp+7B0h+lpcbMaxClassLen], r9; lpcbMaxClassLen
0x180026f86  mov     [rsp+7B0h+lpcbMaxSubKeyLen], r9; lpcbMaxSubKeyLen
0x180026f8b  mov     [rsp+7B0h+phkResult], r9; lpcSubKeys
0x180026f90  call    cs:__imp_RegQueryInfoKeyW
0x180026f97  nop     dword ptr [rax+rax+00h]
0x180026f9c  xor     r9d, r9d
0x180026f9f  test    eax, eax
0x180026fa1  jnz     loc_1800276E4
0x180026fa7  cmp     [rbp+6B0h+cValues], r9d
0x180026fab  jz      loc_1800276E4
0x180026fb1  mov     eax, [rsp+7B0h+cbMaxValueNameLen]
0x180026fb5  lea     ecx, [rax+1]
0x180026fb8  cmp     ecx, eax
0x180026fba  mov     eax, 0FFFFFFFFh
0x180026fbf  jb      loc_180027691
0x180026fc5  mov     ebx, ecx
0x180026fc7  mov     [rsp+7B0h+cbMaxValueNameLen], ebx
0x180026fcb  add     rbx, rbx
0x180026fce  cmp     rbx, rax
0x180026fd1  ja      loc_18002763B
0x180026fd7  call    cs:__imp_GetProcessHeap
0x180026fde  nop     dword ptr [rax+rax+00h]
0x180026fe3  mov     r8d, ebx; dwBytes
0x180026fe6  xor     edx, edx; dwFlags
0x180026fe8  mov     rcx, rax; hHeap
0x180026feb  call    cs:__imp_HeapAlloc
0x180026ff2  nop     dword ptr [rax+rax+00h]
0x180026ff7  mov     ebx, [rbp+6B0h+cbMaxValueLen]
0x180026ffa  mov     rdi, rax
0x180026ffd  mov     [rbp+6B0h+var_708], rax
0x180027001  call    cs:__imp_GetProcessHeap
0x180027008  nop     dword ptr [rax+rax+00h]
0x18002700d  mov     r8d, ebx; dwBytes
0x180027010  xor     edx, edx; dwFlags
0x180027012  mov     rcx, rax; hHeap
0x180027015  call    cs:__imp_HeapAlloc
0x18002701c  nop     dword ptr [rax+rax+00h]
0x180027021  xor     r9d, r9d
0x180027024  mov     [rbp+6B0h+lpMem], rax
0x180027028  mov     r14, rax
0x18002702b  test    rdi, rdi
0x18002702e  jz      loc_180027589
0x180027034  test    rax, rax
0x180027037  jz      loc_180027589
0x18002703d  mov     esi, r9d
0x180027040  mov     [rbp+6B0h+var_72C], r9d
0x180027044  cmp     [rbp+6B0h+cValues], r9d
0x180027048  jbe     loc_1800275E8
0x18002704e  lea     r15, WPP_GLOBAL_Control
0x180027055  lea     r13, WPP_RECORDER_INITIALIZED
0x18002705c  lea     rbx, WPP_b232bbd09fa63021a92d957d702a2cb3_Traceguids
0x180027063  mov     eax, [rbp+6B0h+cbMaxValueLen]
0x180027066  mov     r8, rdi; lpValueName
0x180027069  mov     rcx, [rbp+6B0h+hKey]; hKey
0x18002706d  mov     edx, esi; dwIndex
0x18002706f  mov     [rbp+6B0h+cbData], eax
0x180027072  mov     eax, [rsp+7B0h+cbMaxValueNameLen]
0x180027076  mov     [rbp+6B0h+cchValueName], eax
0x180027079  lea     rax, [rbp+6B0h+cbData]
0x18002707d  mov     [rsp+7B0h+lpcValues], rax; lpcbData
0x180027082  lea     rax, [rbp+6B0h+Type]
0x180027086  mov     [rsp+7B0h+lpcbMaxClassLen], r14; lpData
0x18002708b  mov     [rsp+7B0h+lpcbMaxSubKeyLen], rax; lpType
0x180027090  mov     [rsp+7B0h+phkResult], r9; lpReserved
0x180027095  mov     [rbp+6B0h+Type], r9d
0x180027099  mov     [rbp+6B0h+var_730], r9d
0x18002709d  lea     r9, [rbp+6B0h+cchValueName]; lpcchValueName
0x1800270a1  call    cs:__imp_RegEnumValueW
0x1800270a8  nop     dword ptr [rax+rax+00h]
0x1800270ad  xor     r9d, r9d
0x1800270b0  test    eax, eax
0x1800270b2  jnz     loc_180027534
0x1800270b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800270bf  cmp     rcx, r15
0x1800270c2  jz      short loc_1800270CD
0x1800270c4  cmp     byte ptr [rcx+19h], 2
0x1800270c8  mov     dl, r12b
0x1800270cb  jnb     short loc_1800270D0
0x1800270cd  mov     dl, r9b
0x1800270d0  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x1800270d7  cmp     rax, r13
0x1800270da  setnz   r8b
0x1800270de  test    dl, dl
0x1800270e0  jnz     short loc_1800270E7
0x1800270e2  test    r8b, r8b
0x1800270e5  jz      short loc_180027116
0x1800270e7  mov     r9, [rcx+28h]
0x1800270eb  mov     rcx, [rcx+10h]
0x1800270ef  mov     [rsp+7B0h+lpcbMaxValueLen], rdi
0x1800270f4  mov     [rsp+7B0h+lpcValues], rbx
0x1800270f9  mov     word ptr [rsp+7B0h+lpcbMaxClassLen], 17h
0x180027100  call    WPP_RECORDER_AND_TRACE_SF_sS
0x180027105  mov     rcx, cs:WPP_GLOBAL_Control
0x18002710c  xor     r9d, r9d
0x18002710f  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x180027116  cmp     [rbp+6B0h+Type], 7
0x18002711a  jz      short loc_180027162
0x18002711c  cmp     rcx, r15
0x18002711f  jz      short loc_18002712A
0x180027121  cmp     byte ptr [rcx+19h], 3
0x180027125  mov     dl, r12b
0x180027128  jnb     short loc_18002712D
0x18002712a  mov     dl, r9b
0x18002712d  cmp     rax, r13
0x180027130  setnz   r8b
0x180027134  test    dl, dl
0x180027136  jnz     short loc_180027141
0x180027138  test    r8b, r8b
0x18002713b  jz      loc_1800274BD
0x180027141  mov     r9, [rcx+28h]
0x180027145  mov     rcx, [rcx+10h]
0x180027149  mov     [rsp+7B0h+lpcValues], rbx
0x18002714e  mov     word ptr [rsp+7B0h+lpcbMaxClassLen], 18h
0x180027155  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002715a  xor     r9d, r9d
0x18002715d  jmp     loc_1800274BD
0x180027162  mov     rdi, r14
0x180027165  cmp     [r14], r9w
0x180027169  jz      loc_180027205
0x18002716f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180027173  inc     rsi
0x180027176  cmp     [rdi+rsi*2], r9w
0x18002717b  jnz     short loc_180027173
0x18002717d  lea     rdx, [rbp+6B0h+var_E0]
0x180027184  mov     rcx, rdi
0x180027187  call    cs:__imp__o__wcsicmp
0x18002718e  nop     dword ptr [rax+rax+00h]
0x180027193  xor     r9d, r9d
0x180027196  test    eax, eax
0x180027198  jz      short loc_1800271AE
0x18002719a  add     [rbp+6B0h+var_730], r12d
0x18002719e  lea     rdi, [rdi+rsi*2]
0x1800271a2  add     rdi, 2
0x1800271a6  cmp     [rdi], r9w
0x1800271aa  jnz     short loc_18002716F
0x1800271ac  jmp     short loc_180027202
0x1800271ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800271b5  cmp     rcx, r15
0x1800271b8  jz      short loc_1800271C3
0x1800271ba  cmp     byte ptr [rcx+19h], 4
0x1800271be  mov     dl, r12b
0x1800271c1  jnb     short loc_1800271C6
0x1800271c3  mov     dl, r9b
0x1800271c6  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1800271cd  setnz   r8b
0x1800271d1  test    dl, dl
0x1800271d3  jnz     short loc_1800271DA
0x1800271d5  test    r8b, r8b
0x1800271d8  jz      short loc_1800271FD
0x1800271da  mov     eax, [rbp+6B0h+var_730]
0x1800271dd  mov     r9, [rcx+28h]
0x1800271e1  mov     rcx, [rcx+10h]
0x1800271e5  mov     dword ptr [rsp+7B0h+lpcbMaxValueLen], eax
0x1800271e9  mov     [rsp+7B0h+lpcValues], rbx
0x1800271ee  mov     word ptr [rsp+7B0h+lpcbMaxClassLen], 19h
0x1800271f5  call    WPP_RECORDER_AND_TRACE_SF_sD
0x1800271fa  xor     r9d, r9d
0x1800271fd  mov     [rsp+7B0h+var_740], r12b
0x180027202  mov     esi, [rbp+6B0h+var_72C]
0x180027205  cmp     [rsp+7B0h+var_740], r9b
0x18002720a  jz      loc_1800274B9
0x180027210  xor     edx, edx; Val
0x180027212  lea     rcx, [rbp+6B0h+var_6AC]; void *
0x180027216  mov     r8d, 5C4h; Size
0x18002721c  call    memset_0
0x180027221  xor     eax, eax
0x180027223  mov     qword ptr [rbp+6B0h+var_6D8], 20h ; ' '
0x18002722b  mov     [rbp+6B0h+var_6C0], rax
0x18002722f  lea     rdx, [rbp+6B0h+var_6B0]
0x180027233  mov     rax, [rbp+6B0h+var_6F0]
0x180027237  lea     rcx, [rbp+6B0h+var_6D8]
0x18002723b  mov     qword ptr [rbp+6B0h+var_6D8+8], rax
0x18002723f  mov     r8d, 2
0x180027245  mov     rax, [rbp+6B0h+var_6E8]
0x180027249  mov     [rbp+6B0h+var_6C8], rax
0x18002724d  mov     [rbp+6B0h+var_6B0], 5C8h
0x180027254  call    ?BluetoothFindFirstServiceInternal@BthServ@Services@Bluetooth@Microsoft@@YAPEAXPEBU_BLUETOOTH_SDP_SEARCH_PARAMS@@PEAU_BLUETOOTH_SERVICE_RECORD@@W4_BTHSERV_QUERY_TYPE@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindFirstServiceInternal(_BLUETOOTH_SDP_SEARCH_PARAMS const *,_BLUETOOTH_SERVICE_RECORD *,_BTHSERV_QUERY_TYPE)
0x180027259  xor     r9d, r9d
0x18002725c  mov     [rsp+7B0h+var_738], rax
0x180027261  test    rax, rax
0x180027264  jz      loc_1800274B9
0x18002726a  mov     rbx, rax
0x18002726d  cmp     [rbp+6B0h+var_6B0], 5C8h
0x180027274  xorps   xmm0, xmm0
0x180027277  movups  [rbp+6B0h+var_6D8], xmm0
0x18002727b  mov     [rbp+6B0h+var_720], r9d
0x18002727f  mov     rsi, r9
0x180027282  jz      short loc_18002729A
0x180027284  mov     ecx, 51Ah; dwErrCode
0x180027289  call    cs:__imp_SetLastError
0x180027290  nop     dword ptr [rax+rax+00h]
0x180027295  jmp     loc_180027488
0x18002729a  mov     ecx, 0Dh; dwErrCode
0x18002729f  call    cs:__imp_SetLastError
0x1800272a6  nop     dword ptr [rax+rax+00h]
0x1800272ab  test    [rbp+6B0h+var_69C], 2
0x1800272af  jz      loc_180027488
0x1800272b5  mov     rdi, [rbp+6B0h+var_690]
0x1800272b9  test    rdi, rdi
0x1800272bc  jz      loc_180027488
0x1800272c2  mov     al, [rdi]
0x1800272c4  and     al, 0F8h
0x1800272c6  cmp     al, 30h ; '0'
0x1800272c8  jnz     loc_180027488
0x1800272ce  call    cs:__imp_GetProcessHeap
0x1800272d5  nop     dword ptr [rax+rax+00h]
0x1800272da  xor     edx, edx; dwFlags
  ... truncated ...
```
