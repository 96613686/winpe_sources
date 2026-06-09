# CCellularSettingHelperCommon::SetInternetDataRoamingType(CellularSettingsDataRoamingType)

- ea: `0x180048b30`
- end: `0x180048de4`
- name: `?SetInternetDataRoamingType@CCellularSettingHelperCommon@@UEAAJW4CellularSettingsDataRoamingType@@@Z`
- size: `692`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000178c`
- `0x1800024e0`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x18001dd10`
- `0x18003e20c`
- `0x180046898`
- `0x180048b30`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180048dbb`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180048dbb`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180048c22`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180048c22`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetInterface` at `0x180048cc3`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetInterface` at `0x180048cc3`

## string_xrefs

- `0x180048c33`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x180048cd4`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x180048bbd`: `CCellularSettingHelperCommon::SetInternetDataRoamingType`
- `0x180048d4f`: `CCellularSettingHelperCommon::SetInternetDataRoamingType`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall CCellularSettingHelperCommon::SetInternetDataRoamingType(__int64 a1, int a2)
{
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  unsigned int v6; // eax
  unsigned int v8; // eax
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned int v12; // [rsp+28h] [rbp-59h]
  unsigned int *v13; // [rsp+28h] [rbp-59h]
  int v14; // [rsp+48h] [rbp-39h] BYREF
  unsigned __int16 *v15[2]; // [rsp+50h] [rbp-31h] BYREF
  __int64 v16; // [rsp+60h] [rbp-21h]
  unsigned __int16 *v17[2]; // [rsp+68h] [rbp-19h] BYREF
  __int64 v18; // [rsp+78h] [rbp-9h]
  int v19; // [rsp+80h] [rbp-1h] BYREF
  __int64 v20; // [rsp+88h] [rbp+7h] BYREF
  unsigned int v21[2]; // [rsp+90h] [rbp+Fh] BYREF
  _QWORD v22[2]; // [rsp+98h] [rbp+17h] BYREF
  char v23; // [rsp+A8h] [rbp+27h]
  unsigned int v24[4]; // [rsp+B0h] [rbp+2Fh] BYREF
  int v25; // [rsp+C0h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]
  int v27; // [rsp+F0h] [rbp+6Fh] BYREF

  v27 = a2;
  *(_OWORD *)v17 = 0;
  v18 = 0;
  *(_OWORD *)v15 = 0;
  v16 = 0;
  std::vector<unsigned short>::resize(v17);
  std::vector<unsigned short>::resize(v15);
  StringCchPrintfW(v17[0], v17[1] - v17[0], L"Enter");
  v12 = 250;
  StringCchPrintfW(v15[0], v15[1] - v15[0], L"%S(%d):%s", "CCellularSettingHelperCommon::SetInternetDataRoamingType");
  v3 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v3 > 5u )
  {
    *(unsigned __int16 **)v21 = v15[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v3,
      (__int64)word_18007907A,
      v4,
      v5,
      (const unsigned __int16 **)v21);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v15);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v17);
  v20 = 0;
  v19 = 0;
  v6 = WwanOpenHandle(1, 0, &v19, &v20);
  if ( v6 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xFC,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
             (const char *)v6,
             v12);
  v14 = 0;
  v22[0] = &v14;
  v22[1] = &v27;
  v23 = 1;
  v25 = 0;
  *(_OWORD *)v24 = WWAN_PROFILE_SET_GUID_INTERNET_AO;
  if ( v27 )
  {
    if ( v27 == 1 )
    {
      v25 = 1;
    }
    else if ( v27 == 2 )
    {
      v25 = 2;
    }
  }
  else
  {
    v25 = 0;
  }
  v13 = v24;
  v8 = WwanSetInterface(v20, a1 + 8, 16, 20);
  if ( v8 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x11A,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
      (const char *)v8,
      (unsigned int)v24);
  v14 = 1;
  *(_OWORD *)v15 = 0;
  v16 = 0;
  *(_OWORD *)v17 = 0;
  v18 = 0;
  std::vector<unsigned short>::resize(v15);
  std::vector<unsigned short>::resize(v17);
  StringCchPrintfW(v15[0], v15[1] - v15[0], L"Exit");
  LODWORD(v13) = 286;
  StringCchPrintfW(
    v17[0],
    v17[1] - v17[0],
    L"%S(%d):%s",
    "CCellularSettingHelperCommon::SetInternetDataRoamingType",
    v13,
    v15[0],
    0,
    0);
  v9 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v9 > 5u )
  {
    *(unsigned __int16 **)v21 = v17[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v9,
      (__int64)byte_18007909D,
      v10,
      v11,
      (const unsigned __int16 **)v21);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v17);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v15);
  if ( v23 )
  {
    v23 = 0;
    CCellularSettingHelperCommon::SetInternetDataRoamingType_::_2_::_lambda_2_::operator()(v22);
  }
  WwanCloseHandle(v20, 0);
  return 0;
}

```

## disassembly

```asm
0x180048b30  mov     rax, rsp
0x180048b33  mov     [rax+18h], rbx
0x180048b37  mov     [rax+20h], rdi
0x180048b3b  mov     [rax+10h], edx
0x180048b3e  push    rbp
0x180048b3f  lea     rbp, [rax-5Fh]
0x180048b43  sub     rsp, 0D0h
0x180048b4a  mov     rax, cs:__security_cookie
0x180048b51  xor     rax, rsp
0x180048b54  mov     [rbp+57h+var_10], rax
0x180048b58  mov     rbx, rcx
0x180048b5b  xorps   xmm0, xmm0
0x180048b5e  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x180048b63  xor     edi, edi
0x180048b65  mov     [rbp+57h+var_60], rdi
0x180048b69  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x180048b6e  mov     [rbp+57h+var_78], rdi
0x180048b72  lea     rcx, [rbp+57h+var_70]
0x180048b76  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180048b7b  lea     rcx, [rbp+57h+var_88]
0x180048b7f  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180048b84  mov     rdx, [rbp+57h+var_70+8]
0x180048b88  mov     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x180048b8c  sub     rdx, rcx
0x180048b8f  sar     rdx, 1; unsigned __int64
0x180048b92  lea     r8, aEnter; "Enter"
0x180048b99  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180048b9e  mov     rdx, [rbp+57h+var_88+8]
0x180048ba2  mov     rcx, [rbp+57h+var_88]; unsigned __int16 *
0x180048ba6  sub     rdx, rcx
0x180048ba9  sar     rdx, 1; unsigned __int64
0x180048bac  mov     rax, [rbp+57h+var_70]
0x180048bb0  mov     [rsp+0D0h+var_A8], rax
0x180048bb5  mov     [rsp+0D0h+var_B0], 0FAh
0x180048bbd  lea     r9, aCcellularsetti_35; "CCellularSettingHelperCommon::SetIntern"...
0x180048bc4  lea     r8, aSDS; "%S(%d):%s"
0x180048bcb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180048bd0  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180048bd5  mov     ecx, [rax]
0x180048bd7  cmp     ecx, 5
0x180048bda  jbe     short loc_180048BFC
0x180048bdc  mov     rcx, [rbp+57h+var_88]
0x180048be0  mov     qword ptr [rbp+57h+var_48], rcx
0x180048be4  lea     rcx, [rbp+57h+var_48]
0x180048be8  mov     qword ptr [rsp+0D0h+var_B0], rcx; unsigned int
0x180048bed  lea     rdx, word_18007907A
0x180048bf4  mov     rcx, rax
0x180048bf7  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180048bfc  lea     rcx, [rbp+57h+var_88]
0x180048c00  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180048c05  lea     rcx, [rbp+57h+var_70]
0x180048c09  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180048c0e  mov     [rbp+57h+var_50], rdi
0x180048c12  mov     [rbp+57h+var_58], edi
0x180048c15  lea     r9, [rbp+57h+var_50]
0x180048c19  lea     r8, [rbp+57h+var_58]
0x180048c1d  xor     edx, edx
0x180048c1f  lea     ecx, [rdx+1]
0x180048c22  call    cs:__imp_WwanOpenHandle
0x180048c28  test    eax, eax
0x180048c2a  jz      short loc_180048C49
0x180048c2c  mov     rcx, [rbp+5Fh]; this
0x180048c30  mov     r9d, eax; char *
0x180048c33  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180048c3a  mov     edx, 0FCh; void *
0x180048c3f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180048c44  jmp     loc_180048DC3
0x180048c49  mov     [rbp+57h+var_90], edi
0x180048c4c  lea     rax, [rbp+57h+var_90]
0x180048c50  mov     [rbp+57h+var_40], rax
0x180048c54  lea     rax, [rbp+57h+arg_8]
0x180048c58  mov     [rbp+57h+var_38], rax
0x180048c5c  mov     [rbp+57h+var_30], 1
0x180048c60  xorps   xmm0, xmm0
0x180048c63  movups  xmmword ptr [rbp+57h+var_28+4], xmm0
0x180048c67  movups  xmm1, cs:WWAN_PROFILE_SET_GUID_INTERNET_AO
0x180048c6e  movdqu  xmmword ptr [rbp+57h+var_28], xmm1
0x180048c73  mov     ecx, [rbp+57h+arg_8]
0x180048c76  test    ecx, ecx
0x180048c78  jz      short loc_180048C96
0x180048c7a  sub     ecx, 1
0x180048c7d  jz      short loc_180048C8D
0x180048c7f  cmp     ecx, 1
0x180048c82  jnz     short loc_180048C99
0x180048c84  mov     [rbp+57h+var_18], 2
0x180048c8b  jmp     short loc_180048C99
0x180048c8d  mov     [rbp+57h+var_18], 1
0x180048c94  jmp     short loc_180048C99
0x180048c96  mov     [rbp+57h+var_18], edi
0x180048c99  lea     rdx, [rbx+8]
0x180048c9d  mov     [rsp+0D0h+var_98], rdi
0x180048ca2  mov     [rsp+0D0h+var_A0], rdi
0x180048ca7  mov     [rsp+0D0h+var_A8], rdi
0x180048cac  lea     rax, [rbp+57h+var_28]
0x180048cb0  mov     qword ptr [rsp+0D0h+var_B0], rax; unsigned int
0x180048cb5  mov     r9d, 14h
0x180048cbb  lea     r8d, [r9-4]
0x180048cbf  mov     rcx, [rbp+57h+var_50]
0x180048cc3  call    cs:__imp_WwanSetInterface
0x180048cc9  mov     rcx, [rbp+5Fh]; this
0x180048ccd  test    eax, eax
0x180048ccf  jz      short loc_180048CE5
0x180048cd1  mov     r9d, eax; char *
0x180048cd4  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180048cdb  mov     edx, 11Ah; void *
0x180048ce0  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180048ce5  mov     [rbp+57h+var_90], 1
0x180048cec  xorps   xmm0, xmm0
0x180048cef  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x180048cf4  mov     [rbp+57h+var_78], rdi
0x180048cf8  xorps   xmm1, xmm1
0x180048cfb  movdqu  xmmword ptr [rbp+57h+var_70], xmm1
0x180048d00  mov     [rbp+57h+var_60], rdi
0x180048d04  lea     rcx, [rbp+57h+var_88]
0x180048d08  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180048d0d  lea     rcx, [rbp+57h+var_70]
0x180048d11  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180048d16  mov     rdx, [rbp+57h+var_88+8]
0x180048d1a  mov     rcx, [rbp+57h+var_88]; unsigned __int16 *
0x180048d1e  sub     rdx, rcx
0x180048d21  sar     rdx, 1; unsigned __int64
0x180048d24  lea     r8, aExit; "Exit"
0x180048d2b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180048d30  mov     rdx, [rbp+57h+var_70+8]
0x180048d34  mov     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x180048d38  sub     rdx, rcx
0x180048d3b  sar     rdx, 1; unsigned __int64
0x180048d3e  mov     rax, [rbp+57h+var_88]
0x180048d42  mov     [rsp+0D0h+var_A8], rax
0x180048d47  mov     [rsp+0D0h+var_B0], 11Eh
0x180048d4f  lea     r9, aCcellularsetti_35; "CCellularSettingHelperCommon::SetIntern"...
0x180048d56  lea     r8, aSDS; "%S(%d):%s"
0x180048d5d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180048d62  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180048d67  mov     ecx, [rax]
0x180048d69  cmp     ecx, 5
0x180048d6c  jbe     short loc_180048D8E
0x180048d6e  mov     rcx, [rbp+57h+var_70]
0x180048d72  mov     qword ptr [rbp+57h+var_48], rcx
0x180048d76  lea     rcx, [rbp+57h+var_48]
0x180048d7a  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x180048d7f  lea     rdx, byte_18007909D
0x180048d86  mov     rcx, rax
0x180048d89  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180048d8e  lea     rcx, [rbp+57h+var_70]
0x180048d92  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180048d97  lea     rcx, [rbp+57h+var_88]
0x180048d9b  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180048da0  nop
0x180048da1  cmp     [rbp+57h+var_30], dil
0x180048da5  jz      short loc_180048DB5
0x180048da7  mov     [rbp+57h+var_30], dil
0x180048dab  lea     rcx, [rbp+57h+var_40]
0x180048daf  call    _CCellularSettingHelperCommon__SetInternetDataRoamingType____2____lambda_2___operator__
0x180048db4  nop
0x180048db5  xor     edx, edx
0x180048db7  mov     rcx, [rbp+57h+var_50]
0x180048dbb  call    cs:__imp_WwanCloseHandle
0x180048dc1  xor     eax, eax
0x180048dc3  mov     rcx, [rbp+57h+var_10]
0x180048dc7  xor     rcx, rsp; StackCookie
0x180048dca  call    __security_check_cookie
0x180048dcf  lea     r11, [rsp+0D0h+var_s0]
0x180048dd7  mov     rbx, [r11+20h]
0x180048ddb  mov     rdi, [r11+28h]
0x180048ddf  mov     rsp, r11
0x180048de2  pop     rbp
0x180048de3  retn
```
