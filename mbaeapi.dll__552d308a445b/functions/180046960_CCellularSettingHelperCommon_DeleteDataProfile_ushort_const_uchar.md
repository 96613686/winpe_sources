# CCellularSettingHelperCommon::DeleteDataProfile(ushort const *,uchar)

- ea: `0x180046960`
- end: `0x180046e26`
- name: `?DeleteDataProfile@CCellularSettingHelperCommon@@UEAAJPEBGE@Z`
- size: `1222`
- prototype: `__int64 __fastcall(CCellularSettingHelperCommon *__hidden this, const unsigned __int16 *, unsigned __int8)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000178c`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x18001dd10`
- `0x180033b84`
- `0x180046540`
- `0x180046960`
- `0x18005811c`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180046bd1`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180046c15`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180046cf6`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180046e06`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180046bd1`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180046c15`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180046cf6`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180046e06`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180046a77`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180046a77`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanDeleteProfile` at `0x180046ba3`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanDeleteProfile` at `0x180046ba3`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanDeleteDMConfigProfile` at `0x180046d26`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanDeleteDMConfigProfile` at `0x180046d26`

## string_xrefs

- `0x180046a88`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x180046bb8`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x180046bfc`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x1800469e1`: `CCellularSettingHelperCommon::DeleteDataProfile`
- `0x180046b3b`: `CCellularSettingHelperCommon::DeleteDataProfile`
- `0x180046c9f`: `CCellularSettingHelperCommon::DeleteDataProfile`
- `0x180046da2`: `CCellularSettingHelperCommon::DeleteDataProfile`
- `0x180046d77`: `WwanDeleteDMConfigProfile return Win32 error code 0x%08x.`
- `0x180046b10`: `Cannot find the connection entry in Wcm. Could be deleted already.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCellularSettingHelperCommon::DeleteDataProfile(
        CCellularSettingHelperCommon *this,
        const unsigned __int16 *a2,
        char a3)
{
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  unsigned int v8; // eax
  unsigned int v9; // ebx
  const struct _GUID *v11; // rbx
  unsigned int v12; // eax
  const struct _tlgProvider_t *v13; // rax
  __int64 v14; // r8
  __int64 v15; // r9
  unsigned int v16; // eax
  const struct _tlgProvider_t *v17; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  const struct _tlgProvider_t *v20; // rax
  __int64 v21; // r8
  __int64 v22; // r9
  unsigned int v23[2]; // [rsp+20h] [rbp-49h]
  unsigned __int16 *v24[2]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v25; // [rsp+40h] [rbp-29h]
  unsigned __int16 *v26[2]; // [rsp+48h] [rbp-21h] BYREF
  __int64 v27; // [rsp+58h] [rbp-11h]
  __int64 v28; // [rsp+60h] [rbp-9h] BYREF
  unsigned int v29[2]; // [rsp+68h] [rbp-1h] BYREF
  unsigned int v30; // [rsp+70h] [rbp+7h] BYREF
  int v31; // [rsp+74h] [rbp+Bh] BYREF
  int v32; // [rsp+78h] [rbp+Fh] BYREF
  _QWORD v33[4]; // [rsp+80h] [rbp+17h] BYREF
  char v34; // [rsp+A0h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  LPCWSTR lpSubKey; // [rsp+D8h] [rbp+6Fh] BYREF
  int v37; // [rsp+E8h] [rbp+7Fh] BYREF

  lpSubKey = a2;
  *(_OWORD *)v26 = 0;
  v27 = 0;
  *(_OWORD *)v24 = 0;
  v25 = 0;
  std::vector<unsigned short>::resize(v26);
  std::vector<unsigned short>::resize(v24);
  StringCchPrintfW(v26[0], v26[1] - v26[0], L"Enter");
  v23[0] = 882;
  StringCchPrintfW(v24[0], v24[1] - v24[0], L"%S(%d):%s", "CCellularSettingHelperCommon::DeleteDataProfile");
  v5 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v5 > 5u )
  {
    *(unsigned __int16 **)v29 = v24[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v5,
      (__int64)byte_180078B1B,
      v6,
      v7,
      (const unsigned __int16 **)v29);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v24);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v26);
  v37 = 0;
  v31 = 1;
  v30 = 0;
  v33[0] = &v37;
  v33[1] = &v31;
  v33[2] = &v30;
  v33[3] = &lpSubKey;
  v34 = 1;
  v28 = 0;
  v32 = 0;
  v8 = WwanOpenHandle(1, 0, &v32, &v28);
  if ( v8 )
  {
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x384,
           (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
           (const char *)v8,
           v23[0]);
    if ( v34 )
    {
      v34 = 0;
      CCellularSettingHelperCommon::DeleteDataProfile_::_2_::_lambda_1_::operator()(v33);
    }
    return v9;
  }
  v11 = (const struct _GUID *)((char *)this + 8);
  CWwanTranslator::DeleteProxy(lpSubKey, v11);
  v12 = RemoveWcmMultiplexingTableConnectionEntry(lpSubKey);
  if ( v12 == 2 )
  {
    *(_OWORD *)v24 = 0;
    v25 = 0;
    *(_OWORD *)v26 = 0;
    v27 = 0;
    std::vector<unsigned short>::resize(v24);
    std::vector<unsigned short>::resize(v26);
    StringCchPrintfW(v24[0], v24[1] - v24[0], L"Cannot find the connection entry in Wcm. Could be deleted already.");
    v23[0] = 908;
    StringCchPrintfW(v26[0], v26[1] - v26[0], L"%S(%d):%s", "CCellularSettingHelperCommon::DeleteDataProfile");
    v13 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v13 > 4u )
    {
      *(unsigned __int16 **)v29 = v26[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v13,
        (__int64)&word_180078B3E,
        v14,
        v15,
        (const unsigned __int16 **)v29);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v26);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v24);
  }
  else if ( v12 )
  {
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x390,
           (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
           (const char *)v12,
           v23[0]);
    WwanCloseHandle(v28, 0);
    if ( v34 )
    {
      v34 = 0;
      CCellularSettingHelperCommon::DeleteDataProfile_::_2_::_lambda_1_::operator()(v33);
    }
    return v9;
  }
  if ( a3 )
  {
    v9 = WwanDeleteDMConfigProfile(v28, v11, lpSubKey);
    v30 = v9;
    if ( v9 )
    {
      v31 = 0;
      *(_OWORD *)v24 = 0;
      v25 = 0;
      *(_OWORD *)v26 = 0;
      v27 = 0;
      std::vector<unsigned short>::resize(v24);
      std::vector<unsigned short>::resize(v26);
      StringCchPrintfW(v24[0], v24[1] - v24[0], L"WwanDeleteDMConfigProfile return Win32 error code 0x%08x.", v9);
      v23[0] = 930;
      StringCchPrintfW(
        v26[0],
        v26[1] - v26[0],
        L"%S(%d):%s",
        "CCellularSettingHelperCommon::DeleteDataProfile",
        *(_QWORD *)v23,
        v24[0]);
      v20 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v20 > 2u )
      {
        *(unsigned __int16 **)v29 = v26[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v20,
          (__int64)word_180078AFA,
          v21,
          v22,
          (const unsigned __int16 **)v29);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v26);
      std::vector<unsigned short>::~vector<unsigned short>((char **)v24);
      if ( (int)v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      WwanCloseHandle(v28, 0);
      if ( v34 )
      {
        v34 = 0;
        CCellularSettingHelperCommon::DeleteDataProfile_::_2_::_lambda_1_::operator()(v33);
      }
      return v9;
    }
  }
  else
  {
    v16 = WwanDeleteProfile(v28, v11, lpSubKey, 0);
    if ( v16 )
    {
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x395,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
             (const char *)v16,
             v23[0]);
      WwanCloseHandle(v28, 0);
      if ( v34 )
      {
        v34 = 0;
        CCellularSettingHelperCommon::DeleteDataProfile_::_2_::_lambda_1_::operator()(v33);
      }
      return v9;
    }
    v37 = 1;
  }
  *(_OWORD *)v24 = 0;
  v25 = 0;
  *(_OWORD *)v26 = 0;
  v27 = 0;
  std::vector<unsigned short>::resize(v24);
  std::vector<unsigned short>::resize(v26);
  StringCchPrintfW(v24[0], v24[1] - v24[0], L"Exit");
  v23[0] = 935;
  StringCchPrintfW(
    v26[0],
    v26[1] - v26[0],
    L"%S(%d):%s",
    "CCellularSettingHelperCommon::DeleteDataProfile",
    *(_QWORD *)v23,
    v24[0]);
  v17 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v17 > 5u )
  {
    *(unsigned __int16 **)v29 = v26[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v17,
      (__int64)&dword_180078AB4,
      v18,
      v19,
      (const unsigned __int16 **)v29);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v26);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v24);
  WwanCloseHandle(v28, 0);
  if ( v34 )
  {
    v34 = 0;
    CCellularSettingHelperCommon::DeleteDataProfile_::_2_::_lambda_1_::operator()(v33);
  }
  return 0;
}

```

## disassembly

```asm
0x180046960  mov     [rsp-8+arg_0], rbx
0x180046965  mov     [rsp-8+lpSubKey], rdx
0x18004696a  push    rbp
0x18004696b  push    rsi
0x18004696c  push    rdi
0x18004696d  lea     rbp, [rsp-47h]
0x180046972  sub     rsp, 0B0h
0x180046979  mov     dil, r8b
0x18004697c  mov     rbx, rcx
0x18004697f  xorps   xmm0, xmm0
0x180046982  movdqu  xmmword ptr [rbp+57h+var_78], xmm0
0x180046987  xor     esi, esi
0x180046989  mov     [rbp+57h+var_68], rsi
0x18004698d  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x180046992  mov     [rbp+57h+var_80], rsi
0x180046996  lea     rcx, [rbp+57h+var_78]
0x18004699a  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004699f  lea     rcx, [rbp+57h+var_90]
0x1800469a3  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800469a8  mov     rdx, [rbp+57h+var_78+8]
0x1800469ac  mov     rcx, [rbp+57h+var_78]; unsigned __int16 *
0x1800469b0  sub     rdx, rcx
0x1800469b3  sar     rdx, 1; unsigned __int64
0x1800469b6  lea     r8, aEnter; "Enter"
0x1800469bd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800469c2  mov     rdx, [rbp+57h+var_90+8]
0x1800469c6  mov     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x1800469ca  sub     rdx, rcx
0x1800469cd  sar     rdx, 1; unsigned __int64
0x1800469d0  mov     rax, [rbp+57h+var_78]
0x1800469d4  mov     [rsp+0C0h+var_98], rax
0x1800469d9  mov     [rsp+0C0h+var_A0], 372h
0x1800469e1  lea     r9, aCcellularsetti_0; "CCellularSettingHelperCommon::DeleteDat"...
0x1800469e8  lea     r8, aSDS; "%S(%d):%s"
0x1800469ef  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800469f4  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x1800469f9  mov     ecx, [rax]
0x1800469fb  cmp     ecx, 5
0x1800469fe  jbe     short loc_180046A20
0x180046a00  mov     rcx, [rbp+57h+var_90]
0x180046a04  mov     qword ptr [rbp+57h+var_58], rcx
0x180046a08  lea     rcx, [rbp+57h+var_58]
0x180046a0c  mov     qword ptr [rsp+0C0h+var_A0], rcx; unsigned int
0x180046a11  lea     rdx, byte_180078B1B
0x180046a18  mov     rcx, rax
0x180046a1b  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180046a20  lea     rcx, [rbp+57h+var_90]
0x180046a24  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180046a29  lea     rcx, [rbp+57h+var_78]
0x180046a2d  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180046a32  mov     [rbp+57h+arg_18], esi
0x180046a35  mov     [rbp+57h+var_4C], 1
0x180046a3c  mov     [rbp+57h+var_50], esi
0x180046a3f  lea     rax, [rbp+57h+arg_18]
0x180046a43  mov     [rbp+57h+var_40], rax
0x180046a47  lea     rax, [rbp+57h+var_4C]
0x180046a4b  mov     [rbp+57h+var_38], rax
0x180046a4f  lea     rax, [rbp+57h+var_50]
0x180046a53  mov     [rbp+57h+var_30], rax
0x180046a57  lea     rax, [rbp+57h+lpSubKey]
0x180046a5b  mov     [rbp+57h+var_28], rax
0x180046a5f  mov     [rbp+57h+var_20], 1
0x180046a63  mov     [rbp+57h+var_60], rsi
0x180046a67  mov     [rbp+57h+var_48], esi
0x180046a6a  lea     r9, [rbp+57h+var_60]
0x180046a6e  lea     r8, [rbp+57h+var_48]
0x180046a72  xor     edx, edx
0x180046a74  lea     ecx, [rdx+1]
0x180046a77  call    cs:__imp_WwanOpenHandle
0x180046a7d  test    eax, eax
0x180046a7f  jz      short loc_180046AB6
0x180046a81  mov     rcx, [rbp+5Fh]; this
0x180046a85  mov     r9d, eax; char *
0x180046a88  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180046a8f  mov     edx, 384h; void *
0x180046a94  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180046a99  mov     ebx, eax
0x180046a9b  cmp     [rbp+57h+var_20], sil
0x180046a9f  jz      short loc_180046AAF
0x180046aa1  mov     [rbp+57h+var_20], sil
0x180046aa5  lea     rcx, [rbp+57h+var_40]
0x180046aa9  call    _CCellularSettingHelperCommon__DeleteDataProfile____2____lambda_1___operator__
0x180046aae  nop
0x180046aaf  mov     eax, ebx
0x180046ab1  jmp     loc_180046D13
0x180046ab6  add     rbx, 8
0x180046aba  mov     rdx, rbx; struct _GUID *
0x180046abd  mov     rcx, [rbp+57h+lpSubKey]; unsigned __int16 *
0x180046ac1  call    ?DeleteProxy@CWwanTranslator@@SAJPEBGAEBU_GUID@@@Z; CWwanTranslator::DeleteProxy(ushort const *,_GUID const &)
0x180046ac6  mov     rcx, [rbp+57h+lpSubKey]; lpSubKey
0x180046aca  call    ?RemoveWcmMultiplexingTableConnectionEntry@@YAKPEBG@Z; RemoveWcmMultiplexingTableConnectionEntry(ushort const *)
0x180046acf  cmp     eax, 2
0x180046ad2  jnz     loc_180046BF1
0x180046ad8  xorps   xmm0, xmm0
0x180046adb  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x180046ae0  mov     [rbp+57h+var_80], rsi
0x180046ae4  xorps   xmm1, xmm1
0x180046ae7  movdqu  xmmword ptr [rbp+57h+var_78], xmm1
0x180046aec  mov     [rbp+57h+var_68], rsi
0x180046af0  lea     rcx, [rbp+57h+var_90]
0x180046af4  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180046af9  lea     rcx, [rbp+57h+var_78]
0x180046afd  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180046b02  mov     rdx, [rbp+57h+var_90+8]
0x180046b06  mov     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x180046b0a  sub     rdx, rcx
0x180046b0d  sar     rdx, 1; unsigned __int64
0x180046b10  lea     r8, aCannotFindTheC_0; "Cannot find the connection entry in Wcm"...
0x180046b17  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180046b1c  mov     rdx, [rbp+57h+var_78+8]
0x180046b20  mov     rcx, [rbp+57h+var_78]; unsigned __int16 *
0x180046b24  sub     rdx, rcx
0x180046b27  sar     rdx, 1; unsigned __int64
0x180046b2a  mov     rax, [rbp+57h+var_90]
0x180046b2e  mov     [rsp+0C0h+var_98], rax
0x180046b33  mov     [rsp+0C0h+var_A0], 38Ch
0x180046b3b  lea     r9, aCcellularsetti_0; "CCellularSettingHelperCommon::DeleteDat"...
0x180046b42  lea     r8, aSDS; "%S(%d):%s"
0x180046b49  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180046b4e  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180046b53  mov     ecx, [rax]
0x180046b55  cmp     ecx, 4
0x180046b58  jbe     short loc_180046B7A
0x180046b5a  mov     rcx, [rbp+57h+var_78]
0x180046b5e  mov     qword ptr [rbp+57h+var_58], rcx
0x180046b62  lea     rcx, [rbp+57h+var_58]
0x180046b66  mov     qword ptr [rsp+0C0h+var_A0], rcx; unsigned int
0x180046b6b  lea     rdx, word_180078B3E
0x180046b72  mov     rcx, rax
0x180046b75  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180046b7a  lea     rcx, [rbp+57h+var_78]
0x180046b7e  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180046b83  lea     rcx, [rbp+57h+var_90]
0x180046b87  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180046b8c  mov     r8, [rbp+57h+lpSubKey]
0x180046b90  mov     rdx, rbx
0x180046b93  mov     rcx, [rbp+57h+var_60]
0x180046b97  test    dil, dil
0x180046b9a  jnz     loc_180046D26
0x180046ba0  xor     r9d, r9d
0x180046ba3  call    cs:__imp_WwanDeleteProfile
0x180046ba9  test    eax, eax
0x180046bab  jz      loc_180046C35
0x180046bb1  mov     rcx, [rbp+5Fh]; this
0x180046bb5  mov     r9d, eax; char *
0x180046bb8  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180046bbf  mov     edx, 395h; void *
0x180046bc4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180046bc9  mov     ebx, eax
0x180046bcb  xor     edx, edx
0x180046bcd  mov     rcx, [rbp+57h+var_60]
0x180046bd1  call    cs:__imp_WwanCloseHandle
0x180046bd7  nop
0x180046bd8  cmp     [rbp+57h+var_20], sil
0x180046bdc  jz      short loc_180046BEC
0x180046bde  mov     [rbp+57h+var_20], sil
0x180046be2  lea     rcx, [rbp+57h+var_40]
0x180046be6  call    _CCellularSettingHelperCommon__DeleteDataProfile____2____lambda_1___operator__
0x180046beb  nop
0x180046bec  jmp     loc_180046AAF
0x180046bf1  test    eax, eax
0x180046bf3  jz      short loc_180046B8C
0x180046bf5  mov     rcx, [rbp+5Fh]; this
0x180046bf9  mov     r9d, eax; char *
0x180046bfc  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180046c03  mov     edx, 390h; void *
0x180046c08  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180046c0d  mov     ebx, eax
0x180046c0f  xor     edx, edx
0x180046c11  mov     rcx, [rbp+57h+var_60]
0x180046c15  call    cs:__imp_WwanCloseHandle
0x180046c1b  nop
0x180046c1c  cmp     [rbp+57h+var_20], sil
0x180046c20  jz      short loc_180046C30
0x180046c22  mov     [rbp+57h+var_20], sil
0x180046c26  lea     rcx, [rbp+57h+var_40]
0x180046c2a  call    _CCellularSettingHelperCommon__DeleteDataProfile____2____lambda_1___operator__
0x180046c2f  nop
0x180046c30  jmp     loc_180046AAF
0x180046c35  mov     [rbp+57h+arg_18], 1
0x180046c3c  xorps   xmm0, xmm0
0x180046c3f  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x180046c44  mov     [rbp+57h+var_80], rsi
0x180046c48  xorps   xmm1, xmm1
0x180046c4b  movdqu  xmmword ptr [rbp+57h+var_78], xmm1
0x180046c50  mov     [rbp+57h+var_68], rsi
0x180046c54  lea     rcx, [rbp+57h+var_90]
0x180046c58  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180046c5d  lea     rcx, [rbp+57h+var_78]
0x180046c61  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180046c66  mov     rdx, [rbp+57h+var_90+8]
0x180046c6a  mov     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x180046c6e  sub     rdx, rcx
0x180046c71  sar     rdx, 1; unsigned __int64
0x180046c74  lea     r8, aExit; "Exit"
0x180046c7b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180046c80  mov     rdx, [rbp+57h+var_78+8]
0x180046c84  mov     rcx, [rbp+57h+var_78]; unsigned __int16 *
0x180046c88  sub     rdx, rcx
0x180046c8b  sar     rdx, 1; unsigned __int64
0x180046c8e  mov     rax, [rbp+57h+var_90]
0x180046c92  mov     [rsp+0C0h+var_98], rax
0x180046c97  mov     [rsp+0C0h+var_A0], 3A7h
0x180046c9f  lea     r9, aCcellularsetti_0; "CCellularSettingHelperCommon::DeleteDat"...
0x180046ca6  lea     r8, aSDS; "%S(%d):%s"
0x180046cad  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180046cb2  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180046cb7  mov     ecx, [rax]
0x180046cb9  cmp     ecx, 5
0x180046cbc  jbe     short loc_180046CDE
0x180046cbe  mov     rcx, [rbp+57h+var_78]
0x180046cc2  mov     qword ptr [rbp+57h+var_58], rcx
0x180046cc6  lea     rcx, [rbp+57h+var_58]
0x180046cca  mov     qword ptr [rsp+0C0h+var_A0], rcx
0x180046ccf  lea     rdx, dword_180078AB4
0x180046cd6  mov     rcx, rax
0x180046cd9  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180046cde  lea     rcx, [rbp+57h+var_78]
0x180046ce2  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180046ce7  lea     rcx, [rbp+57h+var_90]
0x180046ceb  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180046cf0  xor     edx, edx
0x180046cf2  mov     rcx, [rbp+57h+var_60]
0x180046cf6  call    cs:__imp_WwanCloseHandle
0x180046cfc  nop
0x180046cfd  cmp     [rbp+57h+var_20], sil
0x180046d01  jz      short loc_180046D11
0x180046d03  mov     [rbp+57h+var_20], sil
0x180046d07  lea     rcx, [rbp+57h+var_40]
0x180046d0b  call    _CCellularSettingHelperCommon__DeleteDataProfile____2____lambda_1___operator__
0x180046d10  nop
0x180046d11  xor     eax, eax
0x180046d13  mov     rbx, [rsp+0C0h+arg_0]
0x180046d1b  add     rsp, 0B0h
0x180046d22  pop     rdi
0x180046d23  pop     rsi
0x180046d24  pop     rbp
0x180046d25  retn
0x180046d26  call    cs:__imp_WwanDeleteDMConfigProfile
0x180046d2c  mov     ebx, eax
0x180046d2e  mov     [rbp+57h+var_50], eax
0x180046d31  test    eax, eax
0x180046d33  jz      loc_180046C3C
0x180046d39  mov     [rbp+57h+var_4C], esi
0x180046d3c  xorps   xmm0, xmm0
0x180046d3f  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x180046d44  mov     [rbp+57h+var_80], rsi
0x180046d48  xorps   xmm1, xmm1
0x180046d4b  movdqu  xmmword ptr [rbp+57h+var_78], xmm1
0x180046d50  mov     [rbp+57h+var_68], rsi
0x180046d54  lea     rcx, [rbp+57h+var_90]
0x180046d58  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180046d5d  lea     rcx, [rbp+57h+var_78]
0x180046d61  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180046d66  mov     rdx, [rbp+57h+var_90+8]
0x180046d6a  mov     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x180046d6e  sub     rdx, rcx
0x180046d71  sar     rdx, 1; unsigned __int64
0x180046d74  mov     r9d, ebx
0x180046d77  lea     r8, aWwandeletedmco_0; "WwanDeleteDMConfigProfile return Win32 "...
0x180046d7e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180046d83  mov     rdx, [rbp+57h+var_78+8]
0x180046d87  mov     rcx, [rbp+57h+var_78]; unsigned __int16 *
0x180046d8b  sub     rdx, rcx
0x180046d8e  sar     rdx, 1; unsigned __int64
0x180046d91  mov     rax, [rbp+57h+var_90]
0x180046d95  mov     [rsp+0C0h+var_98], rax
0x180046d9a  mov     [rsp+0C0h+var_A0], 3A2h
0x180046da2  lea     r9, aCcellularsetti_0; "CCellularSettingHelperCommon::DeleteDat"...
0x180046da9  lea     r8, aSDS; "%S(%d):%s"
0x180046db0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180046db5  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180046dba  mov     ecx, [rax]
0x180046dbc  cmp     ecx, 2
0x180046dbf  jbe     short loc_180046DE1
0x180046dc1  mov     rcx, [rbp+57h+var_78]
0x180046dc5  mov     qword ptr [rbp+57h+var_58], rcx
0x180046dc9  lea     rcx, [rbp+57h+var_58]
0x180046dcd  mov     qword ptr [rsp+0C0h+var_A0], rcx
0x180046dd2  lea     rdx, word_180078AFA
0x180046dd9  mov     rcx, rax
0x180046ddc  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180046de1  lea     rcx, [rbp+57h+var_78]
0x180046de5  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180046dea  lea     rcx, [rbp+57h+var_90]
0x180046dee  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180046df3  test    ebx, ebx
0x180046df5  jle     short loc_180046E00
0x180046df7  movzx   ebx, bx
0x180046dfa  or      ebx, 80070000h
0x180046e00  xor     edx, edx
0x180046e02  mov     rcx, [rbp+57h+var_60]
0x180046e06  call    cs:__imp_WwanCloseHandle
0x180046e0c  nop
0x180046e0d  cmp     [rbp+57h+var_20], sil
0x180046e11  jz      short loc_180046E21
0x180046e13  mov     [rbp+57h+var_20], sil
0x180046e17  lea     rcx, [rbp+57h+var_40]
0x180046e1b  call    _CCellularSettingHelperCommon__DeleteDataProfile____2____lambda_1___operator__
0x180046e20  nop
  ... truncated ...
```
