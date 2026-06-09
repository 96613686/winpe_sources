# NgcUtils::IsSecureBioEnabled(void)

- ea: `0x1800420d4`
- end: `0x1800422d5`
- name: `?IsSecureBioEnabled@NgcUtils@@YA_NXZ`
- size: `513`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `6`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180035f60`
- `0x180036258`
- `0x1800374f0`
- `0x180037920`
- `0x1800394d8`
- `0x18003aa98`

## callees

- `0x18000102c`
- `0x18002d3e8`
- `0x18002d41c`
- `0x180032fcc`
- `0x180036b24`
- `0x180041ccc`
- `0x180041cf0`
- `0x180042048`
- `0x1800420d4`
- `0x180042330`
- `0x180046ce0`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x18004216e`
- `ntdll!NtQuerySystemInformation` at `0x18004216e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004222b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180042245`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004222b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180042245`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800421ed`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800421ed`
- `tbs!Tbsi_GetDeviceInfo` at `0x1800420fb`
- `tbs!Tbsi_GetDeviceInfo` at `0x1800420fb`

## string_xrefs

- `0x18004210c`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`
- `0x18004217f`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`
- `0x1800421b5`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall NgcUtils::IsSecureBioEnabled(NgcUtils *this)
{
  int DeviceInfo; // eax
  NTSTATUS v2; // eax
  unsigned int v3; // edx
  int v4; // eax
  NgcUtils *v5; // rcx
  NgcUtils *v7; // rcx
  int ppv; // [rsp+20h] [rbp-50h]
  _BYTE v9[4]; // [rsp+30h] [rbp-40h] BYREF
  ULONG ReturnLength; // [rsp+34h] [rbp-3Ch] BYREF
  LPVOID v11; // [rsp+38h] [rbp-38h] BYREF
  __int128 v12; // [rsp+40h] [rbp-30h] BYREF
  __int128 SystemInformation; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v12 = 0;
  DeviceInfo = Tbsi_GetDeviceInfo(16, &v12);
  if ( DeviceInfo < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x17C,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\securebioutils.cpp",
      (const char *)(unsigned int)DeviceInfo,
      ppv);
  if ( DWORD1(v12) < 2 )
  {
    if ( (unsigned int)dword_18006E000 > 4 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_18006E000,
        &dword_1800633DC,
        0);
    return 0;
  }
  SystemInformation = 0;
  ReturnLength = 0;
  v2 = NtQuerySystemInformation(SystemRegistryQuotaInformation|0x80, &SystemInformation, 0x10u, &ReturnLength);
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_NtStatus(
      retaddr,
      (void *)0x18D,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\securebioutils.cpp",
      (const char *)(unsigned int)v2,
      ppv);
  if ( (SystemInformation & 0x21) != 0x21 )
  {
    if ( (unsigned int)dword_18006E000 > 4 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_18006E000,
        byte_1800633B3,
        0);
    return 0;
  }
  v9[0] = 0;
  v4 = NgcUtils::CoInitializer::Initialize((NgcUtils::CoInitializer *)v9, v3);
  if ( v4 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x19D,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\securebioutils.cpp",
      (const char *)(unsigned int)v4,
      ppv);
LABEL_15:
    if ( v9[0] )
      CoUninitialize();
    return 0;
  }
  v11 = 0;
  if ( CoCreateInstance(
         &GUID_8aa829d6_e867_492a_8ab7_7363e4859ba9,
         0,
         1u,
         &GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00,
         &v11) < 0 )
  {
    if ( (unsigned int)dword_18006E000 > 4 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_18006E000,
        qword_180063380,
        0);
    wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v11);
    goto LABEL_15;
  }
  wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v11);
  if ( v9[0] )
    CoUninitialize();
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
    return 1;
  if ( NgcUtils::IsSDEVTablePresent(v5) || NgcUtils::ExistsSecureFpRegKey(v7) )
    return (unsigned int)NgcUtils::SecureBioRegKeyState() != 0;
  if ( (unsigned int)dword_18006E000 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_18006E000,
      &unk_180063358,
      0);
  return 0;
}

```

## disassembly

```asm
0x1800420d4  push    rbp
0x1800420d6  mov     rbp, rsp
0x1800420d9  sub     rsp, 70h
0x1800420dd  mov     rax, cs:__security_cookie
0x1800420e4  xor     rax, rsp
0x1800420e7  mov     [rbp+var_10], rax
0x1800420eb  xorps   xmm0, xmm0
0x1800420ee  movups  [rbp+var_30], xmm0
0x1800420f2  lea     rdx, [rbp+var_30]
0x1800420f6  mov     ecx, 10h
0x1800420fb  call    cs:__imp_Tbsi_GetDeviceInfo
0x180042101  mov     rcx, [rbp+8]; this
0x180042105  test    eax, eax
0x180042107  jns     short loc_18004211D
0x180042109  mov     r9d, eax; char *
0x18004210c  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x180042113  mov     edx, 17Ch; void *
0x180042118  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004211d  cmp     dword ptr [rbp+var_30+4], 2
0x180042121  jnb     short loc_18004214D
0x180042123  mov     eax, cs:dword_18006E000
0x180042129  cmp     eax, 4
0x18004212c  jbe     loc_1800422C1
0x180042132  xor     r8d, r8d
0x180042135  lea     rdx, dword_1800633DC
0x18004213c  lea     rcx, dword_18006E000
0x180042143  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180042148  jmp     loc_1800422C1
0x18004214d  xorps   xmm0, xmm0
0x180042150  movups  [rbp+SystemInformation], xmm0
0x180042154  mov     [rbp+ReturnLength], 0
0x18004215b  lea     r9, [rbp+ReturnLength]; ReturnLength
0x18004215f  mov     r8d, 10h; SystemInformationLength
0x180042165  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x180042169  mov     ecx, 0A5h; SystemInformationClass
0x18004216e  call    cs:__imp_NtQuerySystemInformation
0x180042174  mov     rcx, [rbp+8]; this
0x180042178  test    eax, eax
0x18004217a  jns     short loc_180042190
0x18004217c  mov     r9d, eax; char *
0x18004217f  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x180042186  mov     edx, 18Dh; void *
0x18004218b  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180042190  mov     al, byte ptr [rbp+SystemInformation]
0x180042193  and     al, 21h
0x180042195  cmp     al, 21h ; '!'
0x180042197  jnz     loc_1800422A0
0x18004219d  mov     [rbp+var_40], 0
0x1800421a1  lea     rcx, [rbp+var_40]; this
0x1800421a5  call    ?Initialize@CoInitializer@NgcUtils@@QEAAJK@Z; NgcUtils::CoInitializer::Initialize(ulong)
0x1800421aa  mov     rcx, [rbp+8]; this
0x1800421ae  test    eax, eax
0x1800421b0  jns     short loc_1800421C8
0x1800421b2  mov     r9d, eax; char *
0x1800421b5  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x1800421bc  mov     edx, 19Dh; void *
0x1800421c1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800421c6  jmp     short loc_180042221
0x1800421c8  mov     [rbp+var_38], 0
0x1800421d0  lea     rax, [rbp+var_38]
0x1800421d4  mov     qword ptr [rsp+70h+ppv], rax; ppv
0x1800421d9  lea     r9, _GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00; riid
0x1800421e0  xor     edx, edx; pUnkOuter
0x1800421e2  lea     r8d, [rdx+1]; dwClsContext
0x1800421e6  lea     rcx, _GUID_8aa829d6_e867_492a_8ab7_7363e4859ba9; rclsid
0x1800421ed  call    cs:__imp_CoCreateInstance
0x1800421f3  test    eax, eax
0x1800421f5  jns     short loc_180042236
0x1800421f7  mov     eax, cs:dword_18006E000
0x1800421fd  cmp     eax, 4
0x180042200  jbe     short loc_180042218
0x180042202  xor     r8d, r8d
0x180042205  lea     rdx, qword_180063380
0x18004220c  lea     rcx, dword_18006E000
0x180042213  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180042218  lea     rcx, [rbp+var_38]
0x18004221c  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x180042221  cmp     [rbp+var_40], 0
0x180042225  jz      loc_1800422C1
0x18004222b  call    cs:__imp_CoUninitialize
0x180042231  jmp     loc_1800422C1
0x180042236  lea     rcx, [rbp+var_38]
0x18004223a  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18004223f  cmp     [rbp+var_40], 0
0x180042243  jz      short loc_18004224B
0x180042245  call    cs:__imp_CoUninitialize
0x18004224b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x180042252  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x180042257  test    al, al
0x180042259  jz      short loc_18004225F
0x18004225b  mov     al, 1
0x18004225d  jmp     short loc_1800422C3
0x18004225f  call    ?IsSDEVTablePresent@NgcUtils@@YA_NXZ; NgcUtils::IsSDEVTablePresent(void)
0x180042264  test    al, al
0x180042266  jnz     short loc_180042294
0x180042268  call    ?ExistsSecureFpRegKey@NgcUtils@@YA_NXZ; NgcUtils::ExistsSecureFpRegKey(void)
0x18004226d  test    al, al
0x18004226f  jnz     short loc_180042294
0x180042271  mov     eax, cs:dword_18006E000
0x180042277  cmp     eax, 4
0x18004227a  jbe     short loc_1800422C1
0x18004227c  xor     r8d, r8d
0x18004227f  lea     rdx, unk_180063358
0x180042286  lea     rcx, dword_18006E000
0x18004228d  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180042292  jmp     short loc_1800422C1
0x180042294  call    ?SecureBioRegKeyState@NgcUtils@@YA?AW4_NGC_ENABLED_STATE@@XZ; NgcUtils::SecureBioRegKeyState(void)
0x180042299  test    eax, eax
0x18004229b  setnz   al
0x18004229e  jmp     short loc_1800422C3
0x1800422a0  mov     eax, cs:dword_18006E000
0x1800422a6  cmp     eax, 4
0x1800422a9  jbe     short loc_1800422C1
0x1800422ab  xor     r8d, r8d
0x1800422ae  lea     rdx, byte_1800633B3
0x1800422b5  lea     rcx, dword_18006E000
0x1800422bc  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800422c1  xor     al, al
0x1800422c3  mov     rcx, [rbp+var_10]
0x1800422c7  xor     rcx, rsp; StackCookie
0x1800422ca  call    __security_check_cookie
0x1800422cf  add     rsp, 70h
0x1800422d3  pop     rbp
0x1800422d4  retn
```
