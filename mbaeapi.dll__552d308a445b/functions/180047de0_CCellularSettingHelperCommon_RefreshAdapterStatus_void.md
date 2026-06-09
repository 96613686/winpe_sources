# CCellularSettingHelperCommon::RefreshAdapterStatus(void)

- ea: `0x180047de0`
- end: `0x1800482f0`
- name: `?RefreshAdapterStatus@CCellularSettingHelperCommon@@UEAAJXZ`
- size: `1296`
- prototype: `__int64 __fastcall(CCellularSettingHelperCommon *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x18004ea60`

## callees

- `0x18000178c`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x180016134`
- `0x1800172bc`
- `0x18001adf8`
- `0x18001dd10`
- `0x180033768`
- `0x180047de0`
- `0x18004b05c`
- `0x18004b3f8`
- `0x18004b6ec`
- `0x18004b9c4`
- `0x18004bd28`
- `0x18004c01c`
- `0x18004c2f4`
- `0x18004c5cc`
- `0x18004c8a4`
- `0x18005c010`

## string_xrefs

- `0x180047ee0`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x180047f03`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x180047e3c`: `CCellularSettingHelperCommon::RefreshAdapterStatus`
- `0x1800480f1`: `CCellularSettingHelperCommon::RefreshAdapterStatus`
- `0x1800481bd`: `CCellularSettingHelperCommon::RefreshAdapterStatus`
- `0x180048279`: `CCellularSettingHelperCommon::RefreshAdapterStatus`

## pseudocode

```c
__int64 __fastcall CCellularSettingHelperCommon::RefreshAdapterStatus(CCellularSettingHelperCommon *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // rcx
  int v6; // eax
  int DisallowAutoConnect; // esi
  int MultiSimInfo; // eax
  int MultiSimSlotMapping; // eax
  int ModemOptionalFeatures; // eax
  const char *v12; // rax
  __int64 v13; // rdx
  int AdminProvisionedDataProfileInformation; // eax
  const struct _tlgProvider_t *v15; // rax
  __int64 v16; // r8
  __int64 v17; // r9
  const struct _tlgProvider_t *v18; // rax
  __int64 v19; // r8
  __int64 v20; // r9
  const struct _tlgProvider_t *v21; // rax
  __int64 v22; // r8
  __int64 v23; // r9
  int v24[2]; // [rsp+20h] [rbp-48h]
  char *v25; // [rsp+28h] [rbp-40h]
  unsigned __int16 *v26[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v27; // [rsp+40h] [rbp-28h]
  char *v28[2]; // [rsp+48h] [rbp-20h] BYREF
  __int64 v29; // [rsp+58h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]
  unsigned __int16 *v31; // [rsp+90h] [rbp+28h] BYREF

  v29 = 0;
  v27 = 0;
  *(_OWORD *)v28 = 0;
  *(_OWORD *)v26 = 0;
  std::vector<unsigned short>::resize(v28);
  std::vector<unsigned short>::resize(v26);
  StringCchPrintfW((unsigned __int16 *)v28[0], (v28[1] - v28[0]) >> 1, L"Enter");
  v25 = v28[0];
  v24[0] = 86;
  StringCchPrintfW(v26[0], v26[1] - v26[0], L"%S(%d):%s", "CCellularSettingHelperCommon::RefreshAdapterStatus");
  v2 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    v31 = v26[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)qword_180079308,
      v3,
      v4,
      (const unsigned __int16 **)&v31);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v26);
  std::vector<unsigned short>::~vector<unsigned short>(v28);
  v5 = *((_QWORD *)this + 5);
  *(_OWORD *)v26 = 0;
  if ( v5 )
  {
    v26[0] = *((unsigned __int16 **)this + 4);
    v26[1] = (unsigned __int16 *)v5;
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 12));
  }
  v6 = CWwanTranslator::AddInterface(v26, (char *)this + 8);
  DisallowAutoConnect = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x57,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
      (const char *)(unsigned int)v6,
      v24[0]);
    return (unsigned int)DisallowAutoConnect;
  }
  MultiSimInfo = CCellularSettingHelperCommon::_GetMultiSimInfo(this);
  if ( MultiSimInfo < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5A,
      (int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
      (const char *)(unsigned int)MultiSimInfo);
  MultiSimSlotMapping = CCellularSettingHelperCommon::_GetMultiSimSlotMapping(this);
  if ( MultiSimSlotMapping < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5B,
      (int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
      (const char *)(unsigned int)MultiSimSlotMapping);
  ModemOptionalFeatures = CCellularSettingHelperCommon::_GetModemOptionalFeatures(this);
  if ( ModemOptionalFeatures < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5C,
      (int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
      (const char *)(unsigned int)ModemOptionalFeatures);
  DisallowAutoConnect = (*(__int64 (__fastcall **)(CCellularSettingHelperCommon *))(*(_QWORD *)this + 280LL))(this);
  if ( DisallowAutoConnect < 0 )
  {
    v12 = "GetSubscriberInformation failed";
    v13 = 96;
LABEL_16:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
      (const char *)(unsigned int)DisallowAutoConnect,
      (int)v12,
      v25);
    return (unsigned int)DisallowAutoConnect;
  }
  AdminProvisionedDataProfileInformation = CCellularSettingHelperCommon::_GetAdminProvisionedDataProfileInformation(this);
  if ( AdminProvisionedDataProfileInformation < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x64,
      (int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
      (const char *)(unsigned int)AdminProvisionedDataProfileInformation);
  DisallowAutoConnect = (*(__int64 (__fastcall **)(CCellularSettingHelperCommon *))(*(_QWORD *)this + 232LL))(this);
  if ( DisallowAutoConnect < 0 )
  {
    v12 = "GetInternetDataEnabled failed";
    v13 = 102;
    goto LABEL_16;
  }
  DisallowAutoConnect = CCellularSettingHelperCommon::_GetDisallowAutoConnect(this);
  if ( DisallowAutoConnect < 0 )
  {
    v12 = "GetDisallowAutoConnect failed";
    v13 = 103;
    goto LABEL_16;
  }
  DisallowAutoConnect = (*(__int64 (__fastcall **)(CCellularSettingHelperCommon *))(*(_QWORD *)this + 264LL))(this);
  if ( DisallowAutoConnect < 0 )
  {
    v12 = "GetInternetDataRoamingType failed.";
    v13 = 104;
    goto LABEL_16;
  }
  DisallowAutoConnect = (*(__int64 (__fastcall **)(CCellularSettingHelperCommon *))(*(_QWORD *)this + 200LL))(this);
  if ( DisallowAutoConnect < 0 )
  {
    v12 = "GetPinInformation failed";
    v13 = 105;
    goto LABEL_16;
  }
  DisallowAutoConnect = CCellularSettingHelperCommon::_GetInterfaceObject(this);
  if ( DisallowAutoConnect < 0 )
  {
    v12 = "GetInterfaceObject failed";
    v13 = 106;
    goto LABEL_16;
  }
  DisallowAutoConnect = CCellularSettingHelperCommon::_GetProvisioningState(this);
  if ( DisallowAutoConnect < 0 )
  {
    v12 = "GetProvisioningState failed";
    v13 = 107;
    goto LABEL_16;
  }
  if ( CCellularSettingHelperCommon::_GetConnectionIStream(this) < 0 )
  {
    v27 = 0;
    v29 = 0;
    *(_OWORD *)v26 = 0;
    *(_OWORD *)v28 = 0;
    std::vector<unsigned short>::resize(v26);
    std::vector<unsigned short>::resize(v28);
    StringCchPrintfW(v26[0], v26[1] - v26[0], L"GetConnectionIStream failed. Could be due to no registration available");
    v24[0] = 114;
    StringCchPrintfW(
      (unsigned __int16 *)v28[0],
      (v28[1] - v28[0]) >> 1,
      L"%S(%d):%s",
      "CCellularSettingHelperCommon::RefreshAdapterStatus",
      *(_QWORD *)v24,
      v26[0]);
    v15 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v15 > 3u )
    {
      v31 = (unsigned __int16 *)v28[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v15,
        (__int64)byte_18007932B,
        v16,
        v17,
        (const unsigned __int16 **)&v31);
    }
    std::vector<unsigned short>::~vector<unsigned short>(v28);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v26);
  }
  if ( CCellularSettingHelperCommon::_GetLTEAttachInfo(this) < 0 )
  {
    v27 = 0;
    v29 = 0;
    *(_OWORD *)v26 = 0;
    *(_OWORD *)v28 = 0;
    std::vector<unsigned short>::resize(v26);
    std::vector<unsigned short>::resize(v28);
    StringCchPrintfW(v26[0], v26[1] - v26[0], L"GetLTEAttachAPN failed.");
    v24[0] = 120;
    StringCchPrintfW(
      (unsigned __int16 *)v28[0],
      (v28[1] - v28[0]) >> 1,
      L"%S(%d):%s",
      "CCellularSettingHelperCommon::RefreshAdapterStatus",
      *(_QWORD *)v24,
      v26[0]);
    v18 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v18 > 3u )
    {
      v31 = (unsigned __int16 *)v28[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v18,
        (__int64)word_1800792C2,
        v19,
        v20,
        (const unsigned __int16 **)&v31);
    }
    std::vector<unsigned short>::~vector<unsigned short>(v28);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v26);
  }
  v27 = 0;
  v29 = 0;
  *(_OWORD *)v26 = 0;
  *(_OWORD *)v28 = 0;
  std::vector<unsigned short>::resize(v26);
  std::vector<unsigned short>::resize(v28);
  StringCchPrintfW(v26[0], v26[1] - v26[0], L"Exit");
  v24[0] = 123;
  StringCchPrintfW(
    (unsigned __int16 *)v28[0],
    (v28[1] - v28[0]) >> 1,
    L"%S(%d):%s",
    "CCellularSettingHelperCommon::RefreshAdapterStatus",
    *(_QWORD *)v24,
    v26[0]);
  v21 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v21 > 5u )
  {
    v31 = (unsigned __int16 *)v28[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v21,
      (__int64)byte_1800792E5,
      v22,
      v23,
      (const unsigned __int16 **)&v31);
  }
  std::vector<unsigned short>::~vector<unsigned short>(v28);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v26);
  return 0;
}

```

## disassembly

```asm
0x180047de0  push    rbp
0x180047de2  push    rbx
0x180047de3  push    rsi
0x180047de4  push    rdi
0x180047de5  mov     rbp, rsp
0x180047de8  sub     rsp, 68h
0x180047dec  xorps   xmm0, xmm0
0x180047def  mov     [rbp+var_10], 0
0x180047df7  mov     rbx, rcx
0x180047dfa  mov     [rbp+var_28], 0
0x180047e02  lea     rcx, [rbp+var_20]
0x180047e06  movdqu  xmmword ptr [rbp+var_20], xmm0
0x180047e0b  movdqu  xmmword ptr [rbp+var_38], xmm0
0x180047e10  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180047e15  lea     rcx, [rbp+var_38]
0x180047e19  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180047e1e  mov     rdx, [rbp+var_20+8]
0x180047e22  lea     r8, aEnter; "Enter"
0x180047e29  mov     rcx, [rbp+var_20]; unsigned __int16 *
0x180047e2d  sub     rdx, rcx
0x180047e30  sar     rdx, 1; unsigned __int64
0x180047e33  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180047e38  mov     rdx, [rbp+var_38+8]
0x180047e3c  lea     r9, aCcellularsetti_2; "CCellularSettingHelperCommon::RefreshAd"...
0x180047e43  mov     rcx, [rbp+var_38]; unsigned __int16 *
0x180047e47  lea     r8, aSDS; "%S(%d):%s"
0x180047e4e  mov     rax, [rbp+var_20]
0x180047e52  sub     rdx, rcx
0x180047e55  mov     [rsp+68h+var_40], rax; char *
0x180047e5a  sar     rdx, 1; unsigned __int64
0x180047e5d  mov     [rsp+68h+var_48], 56h ; 'V'
0x180047e65  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180047e6a  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180047e6f  mov     ecx, [rax]
0x180047e71  cmp     ecx, 5
0x180047e74  jbe     short loc_180047E96
0x180047e76  mov     rcx, [rbp+var_38]
0x180047e7a  lea     rdx, qword_180079308
0x180047e81  mov     [rbp+arg_0], rcx
0x180047e85  lea     rcx, [rbp+arg_0]
0x180047e89  mov     qword ptr [rsp+68h+var_48], rcx; int
0x180047e8e  mov     rcx, rax
0x180047e91  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180047e96  lea     rcx, [rbp+var_38]
0x180047e9a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180047e9f  lea     rcx, [rbp+var_20]
0x180047ea3  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180047ea8  mov     rcx, [rbx+28h]
0x180047eac  xorps   xmm0, xmm0
0x180047eaf  movdqu  xmmword ptr [rbp+var_38], xmm0
0x180047eb4  test    rcx, rcx
0x180047eb7  jz      short loc_180047EC9
0x180047eb9  mov     rax, [rbx+20h]
0x180047ebd  mov     [rbp+var_38], rax
0x180047ec1  mov     [rbp+var_38+8], rcx
0x180047ec5  lock inc dword ptr [rcx+0Ch]
0x180047ec9  lea     rdx, [rbx+8]
0x180047ecd  lea     rcx, [rbp+var_38]
0x180047ed1  call    ?AddInterface@CWwanTranslator@@SAJV?$weak_ptr@VCWwanTranslator@@@std@@AEBU_GUID@@@Z; CWwanTranslator::AddInterface(std::weak_ptr<CWwanTranslator>,_GUID const &)
0x180047ed6  mov     esi, eax
0x180047ed8  test    eax, eax
0x180047eda  jns     short loc_180047EFB
0x180047edc  mov     rcx, [rbp+20h]; this
0x180047ee0  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180047ee7  mov     r9d, eax; char *
0x180047eea  mov     edx, 57h ; 'W'; void *
0x180047eef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047ef4  mov     eax, esi
0x180047ef6  jmp     loc_1800482E7
0x180047efb  mov     rcx, rbx; this
0x180047efe  call    ?_GetMultiSimInfo@CCellularSettingHelperCommon@@IEAAJXZ; CCellularSettingHelperCommon::_GetMultiSimInfo(void)
0x180047f03  lea     rdi, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180047f0a  test    eax, eax
0x180047f0c  jns     short loc_180047F22
0x180047f0e  mov     rcx, [rbp+20h]; this
0x180047f12  mov     r9d, eax; char *
0x180047f15  mov     r8, rdi; unsigned int
0x180047f18  mov     edx, 5Ah ; 'Z'; void *
0x180047f1d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180047f22  mov     rcx, rbx; this
0x180047f25  call    ?_GetMultiSimSlotMapping@CCellularSettingHelperCommon@@IEAAJXZ; CCellularSettingHelperCommon::_GetMultiSimSlotMapping(void)
0x180047f2a  test    eax, eax
0x180047f2c  jns     short loc_180047F42
0x180047f2e  mov     rcx, [rbp+20h]; this
0x180047f32  mov     r9d, eax; char *
0x180047f35  mov     r8, rdi; unsigned int
0x180047f38  mov     edx, 5Bh ; '['; void *
0x180047f3d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180047f42  mov     rcx, rbx; this
0x180047f45  call    ?_GetModemOptionalFeatures@CCellularSettingHelperCommon@@IEAAJXZ; CCellularSettingHelperCommon::_GetModemOptionalFeatures(void)
0x180047f4a  test    eax, eax
0x180047f4c  jns     short loc_180047F62
0x180047f4e  mov     rcx, [rbp+20h]; this
0x180047f52  mov     r9d, eax; char *
0x180047f55  mov     r8, rdi; unsigned int
0x180047f58  mov     edx, 5Ch ; '\'; void *
0x180047f5d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180047f62  mov     rax, [rbx]
0x180047f65  mov     rcx, rbx
0x180047f68  mov     rax, [rax+118h]
0x180047f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047f74  mov     esi, eax
0x180047f76  test    eax, eax
0x180047f78  jns     short loc_180047F9F
0x180047f7a  lea     rax, aGetsubscriberi; "GetSubscriberInformation failed"
0x180047f81  mov     edx, 60h ; '`'; void *
0x180047f86  mov     rcx, [rbp+20h]; this
0x180047f8a  mov     r9d, esi; char *
0x180047f8d  mov     r8, rdi; unsigned int
0x180047f90  mov     qword ptr [rsp+68h+var_48], rax; int
0x180047f95  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180047f9a  jmp     loc_180047EF4
0x180047f9f  mov     rcx, rbx; this
0x180047fa2  call    ?_GetAdminProvisionedDataProfileInformation@CCellularSettingHelperCommon@@IEAAJXZ; CCellularSettingHelperCommon::_GetAdminProvisionedDataProfileInformation(void)
0x180047fa7  test    eax, eax
0x180047fa9  jns     short loc_180047FBF
0x180047fab  mov     rcx, [rbp+20h]; this
0x180047faf  mov     r9d, eax; char *
0x180047fb2  mov     r8, rdi; unsigned int
0x180047fb5  mov     edx, 64h ; 'd'; void *
0x180047fba  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180047fbf  mov     rax, [rbx]
0x180047fc2  mov     rcx, rbx
0x180047fc5  mov     rax, [rax+0E8h]
0x180047fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047fd1  mov     esi, eax
0x180047fd3  test    eax, eax
0x180047fd5  jns     short loc_180047FE5
0x180047fd7  lea     rax, aGetinternetdat; "GetInternetDataEnabled failed"
0x180047fde  mov     edx, 66h ; 'f'
0x180047fe3  jmp     short loc_180047F86
0x180047fe5  mov     rcx, rbx; this
0x180047fe8  call    ?_GetDisallowAutoConnect@CCellularSettingHelperCommon@@IEAAJXZ; CCellularSettingHelperCommon::_GetDisallowAutoConnect(void)
0x180047fed  mov     esi, eax
0x180047fef  test    eax, eax
0x180047ff1  jns     short loc_180048001
0x180047ff3  lea     rax, aGetdisallowaut; "GetDisallowAutoConnect failed"
0x180047ffa  mov     edx, 67h ; 'g'
0x180047fff  jmp     short loc_180047F86
0x180048001  mov     rax, [rbx]
0x180048004  mov     rcx, rbx
0x180048007  mov     rax, [rax+108h]
0x18004800e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048013  mov     esi, eax
0x180048015  test    eax, eax
0x180048017  jns     short loc_18004802A
0x180048019  lea     rax, aGetinternetdat_0; "GetInternetDataRoamingType failed."
0x180048020  mov     edx, 68h ; 'h'
0x180048025  jmp     loc_180047F86
0x18004802a  mov     rax, [rbx]
0x18004802d  mov     rcx, rbx
0x180048030  mov     rax, [rax+0C8h]
0x180048037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004803c  mov     esi, eax
0x18004803e  test    eax, eax
0x180048040  jns     short loc_180048053
0x180048042  lea     rax, aGetpininformat; "GetPinInformation failed"
0x180048049  mov     edx, 69h ; 'i'
0x18004804e  jmp     loc_180047F86
0x180048053  mov     rcx, rbx; this
0x180048056  call    ?_GetInterfaceObject@CCellularSettingHelperCommon@@IEAAJXZ; CCellularSettingHelperCommon::_GetInterfaceObject(void)
0x18004805b  mov     esi, eax
0x18004805d  test    eax, eax
0x18004805f  jns     short loc_180048072
0x180048061  lea     rax, aGetinterfaceob; "GetInterfaceObject failed"
0x180048068  mov     edx, 6Ah ; 'j'
0x18004806d  jmp     loc_180047F86
0x180048072  mov     rcx, rbx; this
0x180048075  call    ?_GetProvisioningState@CCellularSettingHelperCommon@@IEAAJXZ; CCellularSettingHelperCommon::_GetProvisioningState(void)
0x18004807a  mov     esi, eax
0x18004807c  test    eax, eax
0x18004807e  jns     short loc_180048091
0x180048080  lea     rax, aGetprovisionin; "GetProvisioningState failed"
0x180048087  mov     edx, 6Bh ; 'k'
0x18004808c  jmp     loc_180047F86
0x180048091  mov     rcx, rbx; this
0x180048094  call    ?_GetConnectionIStream@CCellularSettingHelperCommon@@IEAAJXZ; CCellularSettingHelperCommon::_GetConnectionIStream(void)
0x180048099  test    eax, eax
0x18004809b  jns     loc_18004815D
0x1800480a1  xorps   xmm0, xmm0
0x1800480a4  mov     [rbp+var_28], 0
0x1800480ac  xorps   xmm1, xmm1
0x1800480af  mov     [rbp+var_10], 0
0x1800480b7  lea     rcx, [rbp+var_38]
0x1800480bb  movdqu  xmmword ptr [rbp+var_38], xmm0
0x1800480c0  movdqu  xmmword ptr [rbp+var_20], xmm1
0x1800480c5  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800480ca  lea     rcx, [rbp+var_20]
0x1800480ce  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800480d3  mov     rdx, [rbp+var_38+8]
0x1800480d7  lea     r8, aGetconnectioni; "GetConnectionIStream failed. Could be d"...
0x1800480de  mov     rcx, [rbp+var_38]; unsigned __int16 *
0x1800480e2  sub     rdx, rcx
0x1800480e5  sar     rdx, 1; unsigned __int64
0x1800480e8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800480ed  mov     rdx, [rbp+var_20+8]
0x1800480f1  lea     r9, aCcellularsetti_2; "CCellularSettingHelperCommon::RefreshAd"...
0x1800480f8  mov     rcx, [rbp+var_20]; unsigned __int16 *
0x1800480fc  lea     r8, aSDS; "%S(%d):%s"
0x180048103  mov     rax, [rbp+var_38]
0x180048107  sub     rdx, rcx
0x18004810a  mov     [rsp+68h+var_40], rax
0x18004810f  sar     rdx, 1; unsigned __int64
0x180048112  mov     [rsp+68h+var_48], 72h ; 'r'
0x18004811a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004811f  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180048124  mov     ecx, [rax]
0x180048126  cmp     ecx, 3
0x180048129  jbe     short loc_18004814B
0x18004812b  mov     rcx, [rbp+var_20]
0x18004812f  lea     rdx, byte_18007932B
0x180048136  mov     [rbp+arg_0], rcx
0x18004813a  lea     rcx, [rbp+arg_0]
0x18004813e  mov     qword ptr [rsp+68h+var_48], rcx
0x180048143  mov     rcx, rax
0x180048146  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004814b  lea     rcx, [rbp+var_20]
0x18004814f  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180048154  lea     rcx, [rbp+var_38]
0x180048158  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004815d  mov     rcx, rbx; this
0x180048160  call    ?_GetLTEAttachInfo@CCellularSettingHelperCommon@@IEAAJXZ; CCellularSettingHelperCommon::_GetLTEAttachInfo(void)
0x180048165  test    eax, eax
0x180048167  jns     loc_180048229
0x18004816d  xorps   xmm0, xmm0
0x180048170  mov     [rbp+var_28], 0
0x180048178  xorps   xmm1, xmm1
0x18004817b  mov     [rbp+var_10], 0
0x180048183  lea     rcx, [rbp+var_38]
0x180048187  movdqu  xmmword ptr [rbp+var_38], xmm0
0x18004818c  movdqu  xmmword ptr [rbp+var_20], xmm1
0x180048191  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180048196  lea     rcx, [rbp+var_20]
0x18004819a  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004819f  mov     rdx, [rbp+var_38+8]
0x1800481a3  lea     r8, aGetlteattachap; "GetLTEAttachAPN failed."
0x1800481aa  mov     rcx, [rbp+var_38]; unsigned __int16 *
0x1800481ae  sub     rdx, rcx
0x1800481b1  sar     rdx, 1; unsigned __int64
0x1800481b4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800481b9  mov     rdx, [rbp+var_20+8]
0x1800481bd  lea     r9, aCcellularsetti_2; "CCellularSettingHelperCommon::RefreshAd"...
0x1800481c4  mov     rcx, [rbp+var_20]; unsigned __int16 *
0x1800481c8  lea     r8, aSDS; "%S(%d):%s"
0x1800481cf  mov     rax, [rbp+var_38]
0x1800481d3  sub     rdx, rcx
0x1800481d6  mov     [rsp+68h+var_40], rax
0x1800481db  sar     rdx, 1; unsigned __int64
0x1800481de  mov     [rsp+68h+var_48], 78h ; 'x'
0x1800481e6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800481eb  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x1800481f0  mov     ecx, [rax]
0x1800481f2  cmp     ecx, 3
0x1800481f5  jbe     short loc_180048217
0x1800481f7  mov     rcx, [rbp+var_20]
0x1800481fb  lea     rdx, word_1800792C2
0x180048202  mov     [rbp+arg_0], rcx
0x180048206  lea     rcx, [rbp+arg_0]
0x18004820a  mov     qword ptr [rsp+68h+var_48], rcx
0x18004820f  mov     rcx, rax
0x180048212  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180048217  lea     rcx, [rbp+var_20]
0x18004821b  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180048220  lea     rcx, [rbp+var_38]
0x180048224  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180048229  xorps   xmm0, xmm0
0x18004822c  mov     [rbp+var_28], 0
0x180048234  xorps   xmm1, xmm1
0x180048237  mov     [rbp+var_10], 0
0x18004823f  lea     rcx, [rbp+var_38]
0x180048243  movdqu  xmmword ptr [rbp+var_38], xmm0
0x180048248  movdqu  xmmword ptr [rbp+var_20], xmm1
0x18004824d  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180048252  lea     rcx, [rbp+var_20]
0x180048256  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004825b  mov     rdx, [rbp+var_38+8]
0x18004825f  lea     r8, aExit; "Exit"
0x180048266  mov     rcx, [rbp+var_38]; unsigned __int16 *
0x18004826a  sub     rdx, rcx
0x18004826d  sar     rdx, 1; unsigned __int64
0x180048270  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180048275  mov     rdx, [rbp+var_20+8]
0x180048279  lea     r9, aCcellularsetti_2; "CCellularSettingHelperCommon::RefreshAd"...
0x180048280  mov     rcx, [rbp+var_20]; unsigned __int16 *
0x180048284  lea     r8, aSDS; "%S(%d):%s"
0x18004828b  mov     rax, [rbp+var_38]
0x18004828f  sub     rdx, rcx
0x180048292  mov     [rsp+68h+var_40], rax
0x180048297  sar     rdx, 1; unsigned __int64
0x18004829a  mov     [rsp+68h+var_48], 7Bh ; '{'
0x1800482a2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800482a7  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x1800482ac  mov     ecx, [rax]
0x1800482ae  cmp     ecx, 5
0x1800482b1  jbe     short loc_1800482D3
0x1800482b3  mov     rcx, [rbp+var_20]
0x1800482b7  lea     rdx, byte_1800792E5
0x1800482be  mov     [rbp+arg_0], rcx
0x1800482c2  lea     rcx, [rbp+arg_0]
0x1800482c6  mov     qword ptr [rsp+68h+var_48], rcx
  ... truncated ...
```
