# TelCacheProvider::SendHealthEvent(char const *)

- ea: `0x180029a44`
- end: `0x18002a1b3`
- name: `?SendHealthEvent@TelCacheProvider@@SAXPEBD@Z`
- size: `1903`
- prototype: `void __fastcall(const char *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002099c`

## callees

- `0x18000145c`
- `0x180002bf0`
- `0x1800038b8`
- `0x180010ad4`
- `0x1800152d0`
- `0x180020d94`
- `0x180021384`
- `0x180021450`
- `0x1800264ec`
- `0x1800272dc`
- `0x180028308`
- `0x180029a44`
- `0x18002cc40`
- `0x18002ce04`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180029e57`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002a160`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180029e57`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002a160`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180029e4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002a153`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180029e4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002a153`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180029e2b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a134`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180029e2b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a134`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029d55`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029d55`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180029b8b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180029b8b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002a09f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002a09f`

## string_xrefs

- `0x180029ae2`: `InventoryDeviceMediaClass`
- `0x180029d47`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\TelemetryController`
- `0x18002a091`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\TelemetryController`
- `0x180029d95`: `TelCacheProvider::Initialize failed [%#x]`
- `0x18002a0b1`: `RegSetKeyValueW failed [%#x]`
- `0x18002a16e`: `TelCacheProvider::SetMetadata failed [%#x]`
- `0x180029ca6`: `TelCacheProvider::SendHealthEvent`
- `0x180029da2`: `TelCacheProvider::SendHealthEvent`
- `0x18002a17b`: `TelCacheProvider::SendHealthEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall TelCacheProvider::SendHealthEvent(const char *a1, unsigned int a2)
{
  unsigned int v3; // edx
  unsigned int v4; // edx
  unsigned int v5; // edx
  unsigned int v6; // edx
  unsigned int v7; // edx
  unsigned int v8; // edx
  unsigned int v9; // edx
  unsigned int v10; // edx
  unsigned int v11; // edx
  unsigned int v12; // edx
  unsigned int v13; // edx
  unsigned int v14; // edx
  unsigned int v15; // edx
  int wMonth; // ebx
  const unsigned __int16 *Version; // rax
  int v18; // eax
  void **v19; // rdx
  unsigned __int64 v20; // rcx
  LSTATUS ValueW; // ebx
  int v22; // eax
  wchar_t *v23; // rax
  int v24; // ebx
  int v25; // r8d
  int v26; // r9d
  __int64 v27; // rax
  LSTATUS v28; // eax
  int v29; // ebx
  int v30; // edx
  LPDWORD pdwType; // [rsp+20h] [rbp-110h]
  LPDWORD pdwTypea; // [rsp+20h] [rbp-110h]
  DWORD pcbData[2]; // [rsp+B0h] [rbp-80h] BYREF
  const unsigned __int16 *v34; // [rsp+B8h] [rbp-78h] BYREF
  wchar_t *v35; // [rsp+C0h] [rbp-70h] BYREF
  wchar_t *v36; // [rsp+C8h] [rbp-68h] BYREF
  wchar_t *v37; // [rsp+D0h] [rbp-60h] BYREF
  wchar_t *v38; // [rsp+D8h] [rbp-58h] BYREF
  wchar_t *v39; // [rsp+E0h] [rbp-50h] BYREF
  wchar_t *v40; // [rsp+E8h] [rbp-48h] BYREF
  wchar_t *v41; // [rsp+F0h] [rbp-40h] BYREF
  wchar_t *v42; // [rsp+F8h] [rbp-38h] BYREF
  wchar_t *v43; // [rsp+100h] [rbp-30h] BYREF
  wchar_t *v44; // [rsp+108h] [rbp-28h] BYREF
  wchar_t *v45; // [rsp+110h] [rbp-20h] BYREF
  wchar_t *v46; // [rsp+118h] [rbp-18h] BYREF
  wchar_t *v47; // [rsp+120h] [rbp-10h] BYREF
  wchar_t *v48; // [rsp+128h] [rbp-8h] BYREF
  const char *v49; // [rsp+130h] [rbp+0h] BYREF
  __int64 v50; // [rsp+138h] [rbp+8h] BYREF
  __int64 v51; // [rsp+140h] [rbp+10h] BYREF
  _BYTE v52[80]; // [rsp+148h] [rbp+18h] BYREF
  __int64 v53; // [rsp+198h] [rbp+68h]
  __int16 v54; // [rsp+1A0h] [rbp+70h]
  HANDLE hHandle; // [rsp+1A8h] [rbp+78h] BYREF
  HANDLE hEvent[2]; // [rsp+1B0h] [rbp+80h]
  _DWORD *v57; // [rsp+1C0h] [rbp+90h]
  int v58; // [rsp+1C8h] [rbp+98h]
  char v59; // [rsp+1CCh] [rbp+9Ch]
  struct _SYSTEMTIME SystemTime; // [rsp+1D0h] [rbp+A0h] BYREF
  wchar_t v61[8]; // [rsp+1E0h] [rbp+B0h] BYREF
  wchar_t v62[8]; // [rsp+1F0h] [rbp+C0h] BYREF
  wchar_t v63[8]; // [rsp+200h] [rbp+D0h] BYREF
  wchar_t v64[8]; // [rsp+210h] [rbp+E0h] BYREF
  wchar_t v65[8]; // [rsp+220h] [rbp+F0h] BYREF
  wchar_t v66[8]; // [rsp+230h] [rbp+100h] BYREF
  wchar_t v67[8]; // [rsp+240h] [rbp+110h] BYREF
  wchar_t v68[8]; // [rsp+250h] [rbp+120h] BYREF
  wchar_t v69[8]; // [rsp+260h] [rbp+130h] BYREF
  wchar_t v70[8]; // [rsp+270h] [rbp+140h] BYREF
  wchar_t v71[8]; // [rsp+280h] [rbp+150h] BYREF
  wchar_t v72[8]; // [rsp+290h] [rbp+160h] BYREF
  wchar_t Buffer[8]; // [rsp+2A0h] [rbp+170h] BYREF
  wchar_t v74[8]; // [rsp+2B0h] [rbp+180h] BYREF
  wchar_t Data[264]; // [rsp+2C0h] [rbp+190h] BYREF
  _BYTE pvData[528]; // [rsp+4D0h] [rbp+3A0h] BYREF

  TelCacheProvider::GetProviderCountAsString(Buffer, a2, L"DriverPackageExtended");
  TelCacheProvider::GetProviderCountAsString(v72, v3, L"InventoryApplication");
  TelCacheProvider::GetProviderCountAsString(v71, v4, L"InventoryApplicationDriver");
  TelCacheProvider::GetProviderCountAsString(v70, v5, L"InventoryApplicationFramework");
  TelCacheProvider::GetProviderCountAsString(v69, v6, L"InventoryDeviceContainer");
  TelCacheProvider::GetProviderCountAsString(v68, v7, L"InventoryDeviceInterface");
  TelCacheProvider::GetProviderCountAsString(v67, v8, L"InventoryDeviceMediaClass");
  TelCacheProvider::GetProviderCountAsString(v66, v9, L"InventoryDevicePnp");
  TelCacheProvider::GetProviderCountAsString(v65, v10, L"InventoryDriverBinary");
  TelCacheProvider::GetProviderCountAsString(v64, v11, L"InventoryDriverPackage");
  TelCacheProvider::GetProviderCountAsString(v63, v12, L"InventoryDeviceUsbHubClass");
  TelCacheProvider::GetProviderCountAsString(v62, v13, L"InventoryAcpiPhatVersionElement");
  TelCacheProvider::GetProviderCountAsString(v61, v14, L"InventoryAcpiPhatHealthRecord");
  TelCacheProvider::GetProviderCountAsString(v74, v15, L"InventoryDeviceSensor");
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  wMonth = SystemTime.wMonth;
  Version = InventoryCoreGetVersion();
  v18 = StringCchPrintfExW(
          Data,
          0x104u,
          0,
          0,
          0x800u,
          L"%d%ls%ls%ls%ls%ls%ls%ls%ls%ls%ls%ls%ls%ls%ls%ls",
          wMonth,
          Version,
          Buffer,
          v72,
          v71,
          v70,
          v69,
          v68,
          v67,
          v66,
          v65,
          v64,
          v63,
          v62,
          v61,
          v74);
  if ( v18 < 0 )
    AslLogCallPrintf(1, "TelCacheProvider::SendHealthEvent", 1579, "StringCchPrintfExW failed [%#x]", v18);
  memset_0(v52, 0, 0x4Eu);
  v54 = 0;
  hHandle = 0;
  *(_OWORD *)hEvent = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v53 = 0;
  v51 = 0;
  memset_0(pvData, 0, 0x208u);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    pcbData[0] = 520;
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\TelemetryController",
               L"Checksum",
               2u,
               0,
               pvData,
               pcbData);
    goto LABEL_17;
  }
  v22 = TelCacheProvider::Initialize(&v51, L"InventoryApplicationFile", 0, 0, 1, 3, 0x64u);
  if ( v22 < 0 )
  {
    AslLogCallPrintf(1, "TelCacheProvider::SendHealthEvent", 1604, "TelCacheProvider::Initialize failed [%#x]", v22);
    goto LABEL_22;
  }
  pcbData[0] = 260;
  if ( !v53 )
  {
    ValueW = -2147467262;
    goto LABEL_17;
  }
  Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock((Windows::Compat::Inventory::InventorySynchronization *)&hHandle);
  ValueW = (*(__int64 (__fastcall **)(__int64, const WCHAR *, _BYTE *, DWORD *))(*(_QWORD *)v53 + 56LL))(
             v53,
             L"Checksum",
             pvData,
             pcbData);
  if ( !v59 )
  {
    if ( WaitForSingleObject(hHandle, 0xFFFFFFFF) )
      goto LABEL_17;
    --*v57;
    --v58;
    ReleaseMutex(hHandle);
LABEL_16:
    SetEvent(hEvent[1]);
    goto LABEL_17;
  }
  v20 = (unsigned int)v57[1];
  if ( (_DWORD)v20 == 1 )
    v59 = 0;
  --v57[1];
  if ( (_DWORD)v20 == 1 )
    goto LABEL_16;
LABEL_17:
  if ( ValueW >= 0 )
  {
    v23 = Data;
    do
    {
      v19 = (void **)v23[264];
      v20 = *v23 - (unsigned int)v19;
      if ( (_DWORD)v20 )
        break;
      ++v23;
    }
    while ( (_DWORD)v19 );
    if ( !(_DWORD)v20 )
      goto LABEL_43;
  }
LABEL_22:
  UtcThrottle::Throttle((UtcThrottle *)v20, v19);
  v24 = xmmword_1800FF000;
  if ( *(_DWORD *)xmmword_1800FF000 > 5u
    && (*(_QWORD *)(xmmword_1800FF000 + 16) & 0x800000000000LL) != 0
    && (*(_QWORD *)(xmmword_1800FF000 + 24) & 0x800000000000LL) == *(_QWORD *)(xmmword_1800FF000 + 24) )
  {
    *(_QWORD *)pcbData = &Str;
    v34 = InventoryCoreGetVersion();
    v35 = v74;
    v36 = v61;
    v37 = v62;
    v38 = v63;
    v39 = v64;
    v40 = v65;
    v41 = v66;
    v42 = v67;
    v43 = v68;
    v44 = v69;
    v45 = v70;
    v46 = v71;
    v47 = v72;
    v48 = Buffer;
    v49 = a1;
    v50 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>>(
      v24,
      (unsigned int)byte_1800F06B5,
      v25,
      v26,
      (__int64)&v50,
      (__int64)&v49,
      (__int64)&v48,
      (__int64)&v47,
      (__int64)&v46,
      (__int64)&v45,
      (__int64)&v44,
      (__int64)&v43,
      (__int64)&v42,
      (__int64)&v41,
      (__int64)&v40,
      (__int64)&v39,
      (__int64)&v38,
      (__int64)&v37,
      (__int64)&v36,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)pcbData);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v27 = -1;
    do
      ++v27;
    while ( Data[v27] );
    v28 = RegSetKeyValueW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\TelemetryController",
            L"Checksum",
            1u,
            Data,
            2 * v27 + 2);
    if ( v28 < 0 )
    {
      LODWORD(pdwTypea) = v28;
      AslLogCallPrintf(1, "TelCacheProvider::SendHealthEvent", 1649, "RegSetKeyValueW failed [%#x]", pdwTypea);
    }
    goto LABEL_43;
  }
  if ( !v53 || !Data[0] )
    goto LABEL_43;
  Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock((Windows::Compat::Inventory::InventorySynchronization *)&hHandle);
  v29 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, wchar_t *))(*(_QWORD *)v53 + 80LL))(v53, L"Checksum", Data);
  if ( v59 )
  {
    v30 = v57[1];
    if ( v30 == 1 )
      v59 = 0;
    --v57[1];
    if ( v30 != 1 )
      goto LABEL_41;
  }
  else
  {
    if ( WaitForSingleObject(hHandle, 0xFFFFFFFF) )
      goto LABEL_41;
    --*v57;
    --v58;
    ReleaseMutex(hHandle);
  }
  SetEvent(hEvent[1]);
LABEL_41:
  if ( v29 < 0 )
  {
    LODWORD(pdwType) = v29;
    AslLogCallPrintf(
      1,
      "TelCacheProvider::SendHealthEvent",
      1659,
      "TelCacheProvider::SetMetadata failed [%#x]",
      pdwType);
  }
LABEL_43:
  TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v51);
}

```

## disassembly

```asm
0x180029a44  push    rbp
0x180029a46  push    rbx
0x180029a47  push    rsi
0x180029a48  push    rdi
0x180029a49  push    r14
0x180029a4b  push    r15
0x180029a4d  lea     rbp, [rsp-5C8h]
0x180029a55  sub     rsp, 6F8h
0x180029a5c  mov     rax, cs:__security_cookie
0x180029a63  xor     rax, rsp
0x180029a66  mov     [rbp+5F0h+var_40], rax
0x180029a6d  mov     rdi, rcx
0x180029a70  lea     r8, aDriverpackagee; "DriverPackageExtended"
0x180029a77  lea     rcx, [rbp+5F0h+Buffer]; Buffer
0x180029a7e  call    ?GetProviderCountAsString@TelCacheProvider@@SAXPEAGKPEBG@Z; TelCacheProvider::GetProviderCountAsString(ushort *,ulong,ushort const *)
0x180029a83  lea     r8, aInventoryappli; "InventoryApplication"
0x180029a8a  lea     rcx, [rbp+5F0h+var_490]; Buffer
0x180029a91  call    ?GetProviderCountAsString@TelCacheProvider@@SAXPEAGKPEBG@Z; TelCacheProvider::GetProviderCountAsString(ushort *,ulong,ushort const *)
0x180029a96  lea     r8, aInventoryappli_0; "InventoryApplicationDriver"
0x180029a9d  lea     rcx, [rbp+5F0h+var_4A0]; Buffer
0x180029aa4  call    ?GetProviderCountAsString@TelCacheProvider@@SAXPEAGKPEBG@Z; TelCacheProvider::GetProviderCountAsString(ushort *,ulong,ushort const *)
0x180029aa9  lea     r8, aInventoryappli_2; "InventoryApplicationFramework"
0x180029ab0  lea     rcx, [rbp+5F0h+var_4B0]; Buffer
0x180029ab7  call    ?GetProviderCountAsString@TelCacheProvider@@SAXPEAGKPEBG@Z; TelCacheProvider::GetProviderCountAsString(ushort *,ulong,ushort const *)
0x180029abc  lea     r8, aInventorydevic_2; "InventoryDeviceContainer"
0x180029ac3  lea     rcx, [rbp+5F0h+var_4C0]; Buffer
0x180029aca  call    ?GetProviderCountAsString@TelCacheProvider@@SAXPEAGKPEBG@Z; TelCacheProvider::GetProviderCountAsString(ushort *,ulong,ushort const *)
0x180029acf  lea     r8, aInventorydevic_0; "InventoryDeviceInterface"
0x180029ad6  lea     rcx, [rbp+5F0h+var_4D0]; Buffer
0x180029add  call    ?GetProviderCountAsString@TelCacheProvider@@SAXPEAGKPEBG@Z; TelCacheProvider::GetProviderCountAsString(ushort *,ulong,ushort const *)
0x180029ae2  lea     r8, aInventorydevic_4; "InventoryDeviceMediaClass"
0x180029ae9  lea     rcx, [rbp+5F0h+var_4E0]; Buffer
0x180029af0  call    ?GetProviderCountAsString@TelCacheProvider@@SAXPEAGKPEBG@Z; TelCacheProvider::GetProviderCountAsString(ushort *,ulong,ushort const *)
0x180029af5  lea     r8, aInventorydevic_3; "InventoryDevicePnp"
0x180029afc  lea     rcx, [rbp+5F0h+var_4F0]; Buffer
0x180029b03  call    ?GetProviderCountAsString@TelCacheProvider@@SAXPEAGKPEBG@Z; TelCacheProvider::GetProviderCountAsString(ushort *,ulong,ushort const *)
0x180029b08  lea     r8, aInventorydrive_0; "InventoryDriverBinary"
0x180029b0f  lea     rcx, [rbp+5F0h+var_500]; Buffer
0x180029b16  call    ?GetProviderCountAsString@TelCacheProvider@@SAXPEAGKPEBG@Z; TelCacheProvider::GetProviderCountAsString(ushort *,ulong,ushort const *)
0x180029b1b  lea     r8, aInventorydrive; "InventoryDriverPackage"
0x180029b22  lea     rcx, [rbp+5F0h+var_510]; Buffer
0x180029b29  call    ?GetProviderCountAsString@TelCacheProvider@@SAXPEAGKPEBG@Z; TelCacheProvider::GetProviderCountAsString(ushort *,ulong,ushort const *)
0x180029b2e  lea     r8, aInventorydevic_1; "InventoryDeviceUsbHubClass"
0x180029b35  lea     rcx, [rbp+5F0h+var_520]; Buffer
0x180029b3c  call    ?GetProviderCountAsString@TelCacheProvider@@SAXPEAGKPEBG@Z; TelCacheProvider::GetProviderCountAsString(ushort *,ulong,ushort const *)
0x180029b41  lea     r8, aInventoryacpip; "InventoryAcpiPhatVersionElement"
0x180029b48  lea     rcx, [rbp+5F0h+var_530]; Buffer
0x180029b4f  call    ?GetProviderCountAsString@TelCacheProvider@@SAXPEAGKPEBG@Z; TelCacheProvider::GetProviderCountAsString(ushort *,ulong,ushort const *)
0x180029b54  lea     r8, aInventoryacpip_0; "InventoryAcpiPhatHealthRecord"
0x180029b5b  lea     rcx, [rbp+5F0h+var_540]; Buffer
0x180029b62  call    ?GetProviderCountAsString@TelCacheProvider@@SAXPEAGKPEBG@Z; TelCacheProvider::GetProviderCountAsString(ushort *,ulong,ushort const *)
0x180029b67  lea     r8, aInventorydevic; "InventoryDeviceSensor"
0x180029b6e  lea     rcx, [rbp+5F0h+var_470]; Buffer
0x180029b75  call    ?GetProviderCountAsString@TelCacheProvider@@SAXPEAGKPEBG@Z; TelCacheProvider::GetProviderCountAsString(ushort *,ulong,ushort const *)
0x180029b7a  xorps   xmm0, xmm0
0x180029b7d  movups  xmmword ptr [rbp+5F0h+SystemTime.wYear], xmm0
0x180029b84  lea     rcx, [rbp+5F0h+SystemTime]; lpSystemTime
0x180029b8b  call    cs:__imp_GetSystemTime
0x180029b91  movzx   ebx, [rbp+5F0h+SystemTime.wMonth]
0x180029b98  call    ?InventoryCoreGetVersion@@YAPEBGXZ; InventoryCoreGetVersion(void)
0x180029b9d  lea     rcx, [rbp+5F0h+var_470]
0x180029ba4  mov     [rsp+720h+var_678], rcx
0x180029bac  lea     rcx, [rbp+5F0h+var_540]
0x180029bb3  mov     [rsp+720h+var_680], rcx
0x180029bbb  lea     rcx, [rbp+5F0h+var_530]
0x180029bc2  mov     [rsp+720h+var_688], rcx
0x180029bca  lea     rcx, [rbp+5F0h+var_520]
0x180029bd1  mov     [rsp+720h+var_690], rcx
0x180029bd9  lea     rcx, [rbp+5F0h+var_510]
0x180029be0  mov     [rsp+720h+var_698], rcx
0x180029be8  lea     rcx, [rbp+5F0h+var_500]
0x180029bef  mov     [rsp+720h+var_6A0], rcx
0x180029bf7  lea     rcx, [rbp+5F0h+var_4F0]
0x180029bfe  mov     [rsp+720h+var_6A8], rcx
0x180029c03  lea     rcx, [rbp+5F0h+var_4E0]
0x180029c0a  mov     [rsp+720h+var_6B0], rcx
0x180029c0f  lea     rcx, [rbp+5F0h+var_4D0]
0x180029c16  mov     [rsp+720h+var_6B8], rcx
0x180029c1b  lea     rcx, [rbp+5F0h+var_4C0]
0x180029c22  mov     [rsp+720h+var_6C0], rcx
0x180029c27  lea     rcx, [rbp+5F0h+var_4B0]
0x180029c2e  mov     [rsp+720h+var_6C8], rcx
0x180029c33  lea     rcx, [rbp+5F0h+var_4A0]
0x180029c3a  mov     [rsp+720h+var_6D0], rcx
0x180029c3f  lea     rcx, [rbp+5F0h+var_490]
0x180029c46  mov     [rsp+720h+var_6D8], rcx
0x180029c4b  lea     rcx, [rbp+5F0h+Buffer]
0x180029c52  mov     [rsp+720h+var_6E0], rcx
0x180029c57  mov     [rsp+720h+var_6E8], rax
0x180029c5c  mov     dword ptr [rsp+720h+pcbData], ebx
0x180029c60  lea     rax, aDLsLsLsLsLsLsL; "%d%ls%ls%ls%ls%ls%ls%ls%ls%ls%ls%ls%ls%"...
0x180029c67  mov     [rsp+720h+pvData], rax; unsigned __int16 *
0x180029c6c  mov     dword ptr [rsp+720h+pdwType], 800h; unsigned int
0x180029c74  xor     r9d, r9d; unsigned __int64 *
0x180029c77  xor     r8d, r8d; unsigned __int16 **
0x180029c7a  mov     edx, 104h; unsigned __int64
0x180029c7f  lea     rcx, [rbp+5F0h+Data]; Buffer
0x180029c86  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180029c8b  xor     esi, esi
0x180029c8d  lea     r14d, [rsi+1]
0x180029c91  test    eax, eax
0x180029c93  jns     short loc_180029CB5
0x180029c95  mov     dword ptr [rsp+720h+pdwType], eax
0x180029c99  lea     r9, aStringcchprint_0; "StringCchPrintfExW failed [%#x]"
0x180029ca0  mov     r8d, 62Bh
0x180029ca6  lea     rdx, aTelcacheprovid_2; "TelCacheProvider::SendHealthEvent"
0x180029cad  mov     ecx, r14d
0x180029cb0  call    AslLogCallPrintf
0x180029cb5  xor     edx, edx; Val
0x180029cb7  lea     r8d, [rdx+4Eh]; Size
0x180029cbb  lea     rcx, [rbp+5F0h+var_5D8]; void *
0x180029cbf  call    memset_0
0x180029cc4  mov     [rbp+5F0h+var_580], si
0x180029cc8  mov     [rbp+5F0h+hHandle], rsi
0x180029ccc  xorps   xmm0, xmm0
0x180029ccf  movdqa  xmmword ptr [rbp+5F0h+hEvent], xmm0
0x180029cd7  mov     [rbp+5F0h+var_560], rsi
0x180029cde  mov     [rbp+5F0h+var_558], esi
0x180029ce4  mov     [rbp+5F0h+var_554], sil
0x180029ceb  mov     [rbp+5F0h+var_588], rsi
0x180029cef  mov     [rbp+5F0h+var_5E0], rsi
0x180029cf3  mov     ebx, 208h
0x180029cf8  mov     r8d, ebx; Size
0x180029cfb  xor     edx, edx; Val
0x180029cfd  lea     rcx, [rbp+5F0h+var_250]; void *
0x180029d04  call    memset_0
0x180029d09  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x180029d10  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x180029d15  or      r15d, 0FFFFFFFFh
0x180029d19  test    al, al
0x180029d1b  jz      short loc_180029D62
0x180029d1d  mov     [rbp+5F0h+var_670], ebx
0x180029d20  lea     rax, [rbp+5F0h+var_670]
0x180029d24  mov     [rsp+720h+pcbData], rax; pcbData
0x180029d29  lea     rax, [rbp+5F0h+var_250]
0x180029d30  mov     [rsp+720h+pvData], rax; pvData
0x180029d35  mov     [rsp+720h+pdwType], rsi; pdwType
0x180029d3a  mov     r9d, 2; dwFlags
0x180029d40  lea     r8, aChecksum; "Checksum"
0x180029d47  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180029d4e  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180029d55  call    cs:__imp_RegGetValueW
0x180029d5b  mov     ebx, eax
0x180029d5d  jmp     loc_180029E5D
0x180029d62  mov     dword ptr [rsp+720h+pcbData], 64h ; 'd'
0x180029d6a  mov     dword ptr [rsp+720h+pvData], 3
0x180029d72  mov     dword ptr [rsp+720h+pdwType], r14d
0x180029d77  xor     r9d, r9d
0x180029d7a  xor     r8d, r8d
0x180029d7d  lea     rdx, aInventoryappli_1; "InventoryApplicationFile"
0x180029d84  lea     rcx, [rbp+5F0h+var_5E0]
0x180029d88  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x180029d8d  test    eax, eax
0x180029d8f  jns     short loc_180029DB6
0x180029d91  mov     dword ptr [rsp+720h+pdwType], eax
0x180029d95  lea     r9, aTelcacheprovid_9; "TelCacheProvider::Initialize failed [%#"...
0x180029d9c  mov     r8d, 644h
0x180029da2  lea     rdx, aTelcacheprovid_2; "TelCacheProvider::SendHealthEvent"
0x180029da9  mov     ecx, r14d
0x180029dac  call    AslLogCallPrintf
0x180029db1  jmp     loc_180029E8E
0x180029db6  mov     [rbp+5F0h+var_670], 104h
0x180029dbd  cmp     [rbp+5F0h+var_588], rsi
0x180029dc1  jnz     short loc_180029DCD
0x180029dc3  mov     ebx, 80004002h
0x180029dc8  jmp     loc_180029E5D
0x180029dcd  lea     rcx, [rbp+5F0h+hHandle]; this
0x180029dd1  call    ?AcquireSharedLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock(void)
0x180029dd6  mov     rcx, [rbp+5F0h+var_588]
0x180029dda  mov     rax, [rcx]
0x180029ddd  lea     r9, [rbp+5F0h+var_670]
0x180029de1  lea     r8, [rbp+5F0h+var_250]
0x180029de8  lea     rdx, aChecksum; "Checksum"
0x180029def  mov     rax, [rax+38h]
0x180029df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029df8  mov     ebx, eax
0x180029dfa  cmp     [rbp+5F0h+var_554], sil
0x180029e01  jz      short loc_180029E24
0x180029e03  mov     rax, [rbp+5F0h+var_560]
0x180029e0a  mov     ecx, [rax+4]
0x180029e0d  cmp     ecx, r14d
0x180029e10  jnz     short loc_180029E19
0x180029e12  mov     [rbp+5F0h+var_554], sil
0x180029e19  add     [rax+4], r15d
0x180029e1d  cmp     ecx, r14d
0x180029e20  jnz     short loc_180029E5D
0x180029e22  jmp     short loc_180029E50
0x180029e24  mov     edx, r15d; dwMilliseconds
0x180029e27  mov     rcx, [rbp+5F0h+hHandle]; hHandle
0x180029e2b  call    cs:__imp_WaitForSingleObject
0x180029e31  test    eax, eax
0x180029e33  jnz     short loc_180029E5D
0x180029e35  mov     rax, [rbp+5F0h+var_560]
0x180029e3c  add     [rax], r15d
0x180029e3f  add     [rbp+5F0h+var_558], r15d
0x180029e46  mov     rcx, [rbp+5F0h+hHandle]; hMutex
0x180029e4a  call    cs:__imp_ReleaseMutex
0x180029e50  mov     rcx, [rbp+5F0h+hEvent+8]; hEvent
0x180029e57  call    cs:__imp_SetEvent
0x180029e5d  test    ebx, ebx
0x180029e5f  js      short loc_180029E8E
0x180029e61  lea     rax, [rbp+5F0h+Data]
0x180029e68  lea     r8, [rbp+5F0h+var_250]
0x180029e6f  sub     r8, rax
0x180029e72  movzx   ecx, word ptr [rax]
0x180029e75  movzx   edx, word ptr [rax+r8]; void **
0x180029e7a  sub     ecx, edx; this
0x180029e7c  jnz     short loc_180029E86
0x180029e7e  add     rax, 2
0x180029e82  test    edx, edx
0x180029e84  jnz     short loc_180029E72
0x180029e86  test    ecx, ecx
0x180029e88  jz      loc_18002A18B
0x180029e8e  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x180029e93  mov     rbx, qword ptr cs:xmmword_1800FF000
0x180029e9a  mov     eax, [rbx]
0x180029e9c  cmp     eax, 5
0x180029e9f  jbe     loc_18002A04C
0x180029ea5  mov     rcx, [rbx+18h]
0x180029ea9  mov     rax, [rbx+10h]
0x180029ead  mov     rdx, 800000000000h
0x180029eb7  test    rdx, rax
0x180029eba  jz      loc_18002A04C
0x180029ec0  mov     rax, rcx
0x180029ec3  and     rax, rdx
0x180029ec6  cmp     rax, rcx
0x180029ec9  jnz     loc_18002A04C
0x180029ecf  lea     rax, Str
0x180029ed6  mov     qword ptr [rbp+5F0h+var_670], rax
0x180029eda  call    ?InventoryCoreGetVersion@@YAPEBGXZ; InventoryCoreGetVersion(void)
0x180029edf  mov     [rbp+5F0h+var_668], rax
0x180029ee3  lea     rax, [rbp+5F0h+var_470]
0x180029eea  mov     [rbp+5F0h+var_660], rax
0x180029eee  lea     rax, [rbp+5F0h+var_540]
0x180029ef5  mov     [rbp+5F0h+var_658], rax
0x180029ef9  lea     rax, [rbp+5F0h+var_530]
0x180029f00  mov     [rbp+5F0h+var_650], rax
0x180029f04  lea     rax, [rbp+5F0h+var_520]
0x180029f0b  mov     [rbp+5F0h+var_648], rax
0x180029f0f  lea     rax, [rbp+5F0h+var_510]
0x180029f16  mov     [rbp+5F0h+var_640], rax
0x180029f1a  lea     rax, [rbp+5F0h+var_500]
0x180029f21  mov     [rbp+5F0h+var_638], rax
0x180029f25  lea     rax, [rbp+5F0h+var_4F0]
0x180029f2c  mov     [rbp+5F0h+var_630], rax
0x180029f30  lea     rax, [rbp+5F0h+var_4E0]
0x180029f37  mov     [rbp+5F0h+var_628], rax
0x180029f3b  lea     rax, [rbp+5F0h+var_4D0]
0x180029f42  mov     [rbp+5F0h+var_620], rax
0x180029f46  lea     rax, [rbp+5F0h+var_4C0]
0x180029f4d  mov     [rbp+5F0h+var_618], rax
0x180029f51  lea     rax, [rbp+5F0h+var_4B0]
0x180029f58  mov     [rbp+5F0h+var_610], rax
0x180029f5c  lea     rax, [rbp+5F0h+var_4A0]
0x180029f63  mov     [rbp+5F0h+var_608], rax
0x180029f67  lea     rax, [rbp+5F0h+var_490]
0x180029f6e  mov     [rbp+5F0h+var_600], rax
0x180029f72  lea     rax, [rbp+5F0h+Buffer]
0x180029f79  mov     [rbp+5F0h+var_5F8], rax
0x180029f7d  mov     [rbp+5F0h+var_5F0], rdi
0x180029f81  mov     [rbp+5F0h+var_5E8], 1000000h
0x180029f89  lea     rax, [rbp+5F0h+var_670]
0x180029f8d  mov     [rsp+720h+var_678], rax
0x180029f95  lea     rax, [rbp+5F0h+var_668]
0x180029f99  mov     [rsp+720h+var_680], rax
0x180029fa1  lea     rax, [rbp+5F0h+var_660]
0x180029fa5  mov     [rsp+720h+var_688], rax
0x180029fad  lea     rax, [rbp+5F0h+var_658]
0x180029fb1  mov     [rsp+720h+var_690], rax
0x180029fb9  lea     rax, [rbp+5F0h+var_650]
0x180029fbd  mov     [rsp+720h+var_698], rax
0x180029fc5  lea     rax, [rbp+5F0h+var_648]
0x180029fc9  mov     [rsp+720h+var_6A0], rax
0x180029fd1  lea     rax, [rbp+5F0h+var_640]
0x180029fd5  mov     [rsp+720h+var_6A8], rax
0x180029fda  lea     rax, [rbp+5F0h+var_638]
0x180029fde  mov     [rsp+720h+var_6B0], rax
0x180029fe3  lea     rax, [rbp+5F0h+var_630]
0x180029fe7  mov     [rsp+720h+var_6B8], rax
0x180029fec  lea     rax, [rbp+5F0h+var_628]
0x180029ff0  mov     [rsp+720h+var_6C0], rax
0x180029ff5  lea     rax, [rbp+5F0h+var_620]
0x180029ff9  mov     [rsp+720h+var_6C8], rax
0x180029ffe  lea     rax, [rbp+5F0h+var_618]
0x18002a002  mov     [rsp+720h+var_6D0], rax
0x18002a007  lea     rax, [rbp+5F0h+var_610]
0x18002a00b  mov     [rsp+720h+var_6D8], rax
0x18002a010  lea     rax, [rbp+5F0h+var_608]
0x18002a014  mov     [rsp+720h+var_6E0], rax
0x18002a019  lea     rax, [rbp+5F0h+var_600]
0x18002a01d  mov     [rsp+720h+var_6E8], rax
0x18002a022  lea     rax, [rbp+5F0h+var_5F8]
0x18002a026  mov     [rsp+720h+pcbData], rax
0x18002a02b  lea     rax, [rbp+5F0h+var_5F0]
0x18002a02f  mov     [rsp+720h+pvData], rax
0x18002a034  lea     rax, [rbp+5F0h+var_5E8]
0x18002a038  mov     [rsp+720h+pdwType], rax
0x18002a03d  lea     rdx, byte_1800F06B5
0x18002a044  mov     rcx, rbx
0x18002a047  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@555555555555554@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &)
  ... truncated ...
```
