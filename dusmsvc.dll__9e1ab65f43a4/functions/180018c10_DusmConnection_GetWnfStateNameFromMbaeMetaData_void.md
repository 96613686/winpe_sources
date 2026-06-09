# DusmConnection::GetWnfStateNameFromMbaeMetaData(void)

- ea: `0x180018c10`
- end: `0x180018fa2`
- name: `?GetWnfStateNameFromMbaeMetaData@DusmConnection@@AEAAJXZ`
- size: `914`
- prototype: `__int64 __fastcall(DusmConnection *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180018fa8`

## callees

- `0x180001234`
- `0x180007c90`
- `0x180008704`
- `0x18000d428`
- `0x180013444`
- `0x180018c10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180018c7d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180018e20`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180018c7d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180018e20`
- `MobileNetworking!GetNetworkAccountBindingDeviceInterfacePath` at `0x180018cfc`
- `MobileNetworking!GetNetworkAccountBindingDeviceInterfacePath` at `0x180018cfc`
- `MobileNetworking!GetNetworkAccountIdBoundToInterfaceId` at `0x180018c9d`
- `MobileNetworking!GetNetworkAccountIdBoundToInterfaceId` at `0x180018c9d`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180018dcd`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180018e9b`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180018f38`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180018f7b`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180018dcd`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180018e9b`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180018f38`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180018f7b`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180018d88`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180018e54`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180018d88`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180018e54`

## pseudocode

```c
__int64 __fastcall DusmConnection::GetWnfStateNameFromMbaeMetaData(const GUID *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  int NetworkAccountIdBoundToInterfaceId; // ebx
  _DWORD *v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  char *v8; // rdx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  _DWORD *v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  _DWORD *v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+48h] [rbp-B8h]
  DEVPROPKEY v22; // [rsp+58h] [rbp-A8h]
  int v23; // [rsp+6Ch] [rbp-94h]
  __int64 v24; // [rsp+70h] [rbp-90h]
  __int128 v25; // [rsp+78h] [rbp-88h]
  int v26; // [rsp+88h] [rbp-78h]
  int v27; // [rsp+8Ch] [rbp-74h]
  __int64 v28; // [rsp+90h] [rbp-70h]
  int v29; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v30; // [rsp+9Ch] [rbp-64h]
  OLECHAR sz[40]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v32[80]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v33[528]; // [rsp+190h] [rbp+90h] BYREF

  v26 = 108;
  v27 = 0;
  v28 = 0;
  v25 = DEVPKEY_DeviceContainer_DCA_WnfStateName;
  memset_0(sz, 0, sizeof(sz));
  StringFromGUID2(this + 2, sz, 40);
  memset_0(v32, 0, sizeof(v32));
  NetworkAccountIdBoundToInterfaceId = GetNetworkAccountIdBoundToInterfaceId(sz, 40, v32);
  if ( NetworkAccountIdBoundToInterfaceId < 0 )
  {
    v5 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v3, v2) + 8);
    if ( *v5 <= 5u )
      return (unsigned int)NetworkAccountIdBoundToInterfaceId;
    v8 = byte_180056649;
LABEL_4:
    v29 = NetworkAccountIdBoundToInterfaceId;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (int)v5,
      (int)v8,
      v6,
      v7,
      (__int64)&v29);
    return (unsigned int)NetworkAccountIdBoundToInterfaceId;
  }
  memset_0(v33, 0, 0x208u);
  NetworkAccountIdBoundToInterfaceId = GetNetworkAccountBindingDeviceInterfacePath(v32, 260, v33);
  if ( NetworkAccountIdBoundToInterfaceId < 0 )
  {
    v5 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v11, v10) + 8);
    if ( *v5 <= 5u )
      return (unsigned int)NetworkAccountIdBoundToInterfaceId;
    v8 = byte_1800565D3;
    goto LABEL_4;
  }
  v22 = DEVPKEY_Device_ContainerId;
  v21 = 0;
  v30 = 0;
  v23 = 0;
  v24 = 0;
  NetworkAccountIdBoundToInterfaceId = DevGetObjectProperties(1, v33, 0);
  if ( NetworkAccountIdBoundToInterfaceId < 0 )
  {
    v14 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v13, v12) + 8);
    if ( *v14 > 5u )
    {
      v29 = NetworkAccountIdBoundToInterfaceId;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (int)v14,
        (int)&dword_180056554,
        v15,
        v16,
        (__int64)&v29);
    }
    return (unsigned int)NetworkAccountIdBoundToInterfaceId;
  }
  v17 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v13, v12) + 8);
  if ( *v17 > 5u )
  {
    v20 = -2147024809;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (int)v17,
      (int)byte_1800563B9,
      v18,
      v19,
      (__int64)&v20);
  }
  if ( v21 )
    DevFreeObjectProperties(v30);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180018c10  push    rbp
0x180018c12  push    rbx
0x180018c13  push    rdi
0x180018c14  push    r15
0x180018c16  lea     rbp, [rsp-2B8h]
0x180018c1e  sub     rsp, 3B8h
0x180018c25  mov     rax, cs:__security_cookie
0x180018c2c  xor     rax, rsp
0x180018c2f  mov     [rbp+2D0h+var_30], rax
0x180018c36  movups  xmm0, cs:DEVPKEY_DeviceContainer_DCA_WnfStateName
0x180018c3d  mov     eax, cs:dword_180050848
0x180018c43  mov     rdi, rcx
0x180018c46  mov     r15d, 50h ; 'P'
0x180018c4c  mov     [rbp+2D0h+var_348], eax
0x180018c4f  mov     r8d, r15d; Size
0x180018c52  mov     [rbp+2D0h+var_344], 0
0x180018c59  xor     edx, edx; Val
0x180018c5b  mov     [rbp+2D0h+var_340], 0
0x180018c63  lea     rcx, [rbp+2D0h+sz]; void *
0x180018c67  movups  [rsp+3D0h+var_358], xmm0
0x180018c6c  call    memset_0
0x180018c71  lea     rcx, [rdi+20h]; rguid
0x180018c75  lea     r8d, [r15-28h]; cchMax
0x180018c79  lea     rdx, [rbp+2D0h+sz]; lpsz
0x180018c7d  call    cs:__imp_StringFromGUID2
0x180018c83  mov     r8d, r15d; Size
0x180018c86  lea     rcx, [rbp+2D0h+var_2E0]; void *
0x180018c8a  xor     edx, edx; Val
0x180018c8c  call    memset_0
0x180018c91  lea     r8, [rbp+2D0h+var_2E0]
0x180018c95  lea     edx, [r15-28h]
0x180018c99  lea     rcx, [rbp+2D0h+sz]
0x180018c9d  call    cs:__imp_GetNetworkAccountIdBoundToInterfaceId
0x180018ca3  mov     ebx, eax
0x180018ca5  test    eax, eax
0x180018ca7  jns     short loc_180018CD8
0x180018ca9  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180018cae  mov     rcx, [rax+8]
0x180018cb2  mov     edx, [rcx]
0x180018cb4  cmp     edx, 5
0x180018cb7  jbe     short loc_180018CD1
0x180018cb9  lea     rdx, byte_180056649
0x180018cc0  lea     rax, [rbp+2D0h+var_338]
0x180018cc4  mov     [rsp+3D0h+var_3B0], rax
0x180018cc9  mov     [rbp+2D0h+var_338], ebx
0x180018ccc  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180018cd1  mov     eax, ebx
0x180018cd3  jmp     loc_180018F86
0x180018cd8  xor     edx, edx; Val
0x180018cda  lea     rcx, [rbp+2D0h+var_240]; void *
0x180018ce1  mov     r8d, 208h; Size
0x180018ce7  call    memset_0
0x180018cec  lea     r8, [rbp+2D0h+var_240]
0x180018cf3  mov     edx, 104h
0x180018cf8  lea     rcx, [rbp+2D0h+var_2E0]
0x180018cfc  call    cs:__imp_GetNetworkAccountBindingDeviceInterfacePath
0x180018d02  mov     ebx, eax
0x180018d04  test    eax, eax
0x180018d06  jns     short loc_180018D21
0x180018d08  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180018d0d  mov     rcx, [rax+8]
0x180018d11  mov     edx, [rcx]
0x180018d13  cmp     edx, 5
0x180018d16  jbe     short loc_180018CD1
0x180018d18  lea     rdx, byte_1800565D3
0x180018d1f  jmp     short loc_180018CC0
0x180018d21  mov     eax, cs:DEVPKEY_Device_ContainerId.pid
0x180018d27  lea     rdx, [rbp+2D0h+var_240]
0x180018d2e  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ContainerId.fmtid.Data1
0x180018d35  mov     [rsp+3D0h+var_368], eax
0x180018d39  mov     r9d, 1
0x180018d3f  lea     rax, [rsp+3D0h+var_388]
0x180018d44  mov     [rsp+3D0h+var_388], 0
0x180018d4d  mov     [rsp+3D0h+var_3A0], rax
0x180018d52  xor     r8d, r8d
0x180018d55  lea     rax, [rbp+2D0h+var_334]
0x180018d59  mov     [rbp+2D0h+var_334], 0
0x180018d60  mov     [rsp+3D0h+var_3A8], rax
0x180018d65  mov     ecx, r9d
0x180018d68  lea     rax, [rsp+3D0h+var_378]
0x180018d6d  mov     [rsp+3D0h+var_364], 0
0x180018d75  mov     [rsp+3D0h+var_3B0], rax
0x180018d7a  movups  [rsp+3D0h+var_378], xmm0
0x180018d7f  mov     [rsp+3D0h+var_360], 0
0x180018d88  call    cs:__imp_DevGetObjectProperties
0x180018d8e  mov     ebx, eax
0x180018d90  test    eax, eax
0x180018d92  jns     short loc_180018DD8
0x180018d94  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180018d99  mov     rcx, [rax+8]
0x180018d9d  mov     edx, [rcx]
0x180018d9f  cmp     edx, 5
0x180018da2  jbe     short loc_180018DBC
0x180018da4  lea     rax, [rbp+2D0h+var_338]
0x180018da8  mov     [rbp+2D0h+var_338], ebx
0x180018dab  lea     rdx, dword_180056554
0x180018db2  mov     [rsp+3D0h+var_3B0], rax
0x180018db7  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180018dbc  mov     rdx, [rsp+3D0h+var_388]
0x180018dc1  test    rdx, rdx
0x180018dc4  jz      loc_180018CD1
0x180018dca  mov     ecx, [rbp+2D0h+var_334]
0x180018dcd  call    cs:__imp_DevFreeObjectProperties
0x180018dd3  jmp     loc_180018CD1
0x180018dd8  cmp     [rbp+2D0h+var_334], 1
0x180018ddc  jnz     loc_180018F40
0x180018de2  mov     rbx, [rsp+3D0h+var_388]
0x180018de7  cmp     dword ptr [rbx+20h], 0Dh
0x180018deb  jnz     loc_180018F40
0x180018df1  mov     [rsp+3D0h+var_380], 0
0x180018dfa  lea     rcx, [rbp+2D0h+var_290]; void *
0x180018dfe  mov     [rbp+2D0h+var_338], 0
0x180018e05  mov     r8, r15; Size
0x180018e08  mov     rbx, [rbx+28h]
0x180018e0c  xor     edx, edx; Val
0x180018e0e  call    memset_0
0x180018e13  mov     r8d, 28h ; '('; cchMax
0x180018e19  lea     rdx, [rbp+2D0h+var_290]; lpsz
0x180018e1d  mov     rcx, rbx; rguid
0x180018e20  call    cs:__imp_StringFromGUID2
0x180018e26  lea     rax, [rsp+3D0h+var_380]
0x180018e2b  mov     r9d, 1
0x180018e31  mov     [rsp+3D0h+var_3A0], rax
0x180018e36  lea     rdx, [rbp+2D0h+var_290]
0x180018e3a  lea     rax, [rbp+2D0h+var_338]
0x180018e3e  xor     r8d, r8d
0x180018e41  mov     [rsp+3D0h+var_3A8], rax
0x180018e46  lea     rax, [rsp+3D0h+var_358]
0x180018e4b  lea     ecx, [r9+1]
0x180018e4f  mov     [rsp+3D0h+var_3B0], rax
0x180018e54  call    cs:__imp_DevGetObjectProperties
0x180018e5a  mov     ebx, eax
0x180018e5c  test    eax, eax
0x180018e5e  jns     short loc_180018EA6
0x180018e60  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180018e65  mov     rcx, [rax+8]
0x180018e69  mov     edx, [rcx]
0x180018e6b  cmp     edx, 5
0x180018e6e  jbe     short loc_180018E8A
0x180018e70  lea     rax, [rsp+3D0h+var_390]
0x180018e75  mov     [rsp+3D0h+var_390], ebx
0x180018e79  lea     rdx, byte_1800564D5
0x180018e80  mov     [rsp+3D0h+var_3B0], rax
0x180018e85  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180018e8a  mov     rdx, [rsp+3D0h+var_380]
0x180018e8f  test    rdx, rdx
0x180018e92  jz      loc_180018DBC
0x180018e98  mov     ecx, [rbp+2D0h+var_338]
0x180018e9b  call    cs:__imp_DevFreeObjectProperties
0x180018ea1  jmp     loc_180018DBC
0x180018ea6  cmp     [rbp+2D0h+var_338], 1
0x180018eaa  jnz     short loc_180018EFD
0x180018eac  mov     rax, [rsp+3D0h+var_380]
0x180018eb1  cmp     dword ptr [rax+20h], 1003h
0x180018eb8  jnz     short loc_180018EFD
0x180018eba  cmp     dword ptr [rax+24h], 8
0x180018ebe  jnz     short loc_180018EFD
0x180018ec0  mov     r8, [rsp+3D0h+var_388]
0x180018ec5  lea     rcx, [rdi+11Ch]; Destination
0x180018ecc  mov     edx, 10h; DestinationSize
0x180018ed1  mov     r9d, edx; SourceSize
0x180018ed4  mov     r8, [r8+28h]; Source
0x180018ed8  call    memcpy_s
0x180018edd  mov     r8, [rsp+3D0h+var_380]
0x180018ee2  lea     rcx, [rdi+114h]; Destination
0x180018ee9  mov     edx, 8; DestinationSize
0x180018eee  mov     r9d, [r8+24h]; SourceSize
0x180018ef2  mov     r8, [r8+28h]; Source
0x180018ef6  call    memcpy_s
0x180018efb  jmp     short loc_180018E8A
0x180018efd  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180018f02  mov     rcx, [rax+8]
0x180018f06  mov     eax, [rcx]
0x180018f08  cmp     eax, 5
0x180018f0b  jbe     short loc_180018F2B
0x180018f0d  lea     rax, [rsp+3D0h+var_390]
0x180018f12  mov     [rsp+3D0h+var_390], 80070057h
0x180018f1a  lea     rdx, byte_180056447
0x180018f21  mov     [rsp+3D0h+var_3B0], rax
0x180018f26  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180018f2b  mov     rdx, [rsp+3D0h+var_380]
0x180018f30  test    rdx, rdx
0x180018f33  jz      short loc_180018F6E
0x180018f35  mov     ecx, [rbp+2D0h+var_338]
0x180018f38  call    cs:__imp_DevFreeObjectProperties
0x180018f3e  jmp     short loc_180018F6E
0x180018f40  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180018f45  mov     rcx, [rax+8]
0x180018f49  mov     eax, [rcx]
0x180018f4b  cmp     eax, 5
0x180018f4e  jbe     short loc_180018F6E
0x180018f50  lea     rax, [rsp+3D0h+var_390]
0x180018f55  mov     [rsp+3D0h+var_390], 80070057h
0x180018f5d  lea     rdx, byte_1800563B9
0x180018f64  mov     [rsp+3D0h+var_3B0], rax
0x180018f69  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180018f6e  mov     rdx, [rsp+3D0h+var_388]
0x180018f73  test    rdx, rdx
0x180018f76  jz      short loc_180018F81
0x180018f78  mov     ecx, [rbp+2D0h+var_334]
0x180018f7b  call    cs:__imp_DevFreeObjectProperties
0x180018f81  mov     eax, 80070057h
0x180018f86  mov     rcx, [rbp+2D0h+var_30]
0x180018f8d  xor     rcx, rsp; StackCookie
0x180018f90  call    __security_check_cookie
0x180018f95  add     rsp, 3B8h
0x180018f9c  pop     r15
0x180018f9e  pop     rdi
0x180018f9f  pop     rbx
0x180018fa0  pop     rbp
0x180018fa1  retn
```
