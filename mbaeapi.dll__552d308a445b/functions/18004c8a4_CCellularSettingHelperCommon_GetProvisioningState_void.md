# CCellularSettingHelperCommon::_GetProvisioningState(void)

- ea: `0x18004c8a4`
- end: `0x18004cb76`
- name: `?_GetProvisioningState@CCellularSettingHelperCommon@@IEAAJXZ`
- size: `722`
- prototype: `int __fastcall(CCellularSettingHelperCommon *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180047de0`

## callees

- `0x18000178c`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x18001dd10`
- `0x1800378d8`
- `0x18004c8a4`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004cb5b`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004cb5b`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004ca7d`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004cb49`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004ca7d`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004cb49`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004c984`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004c984`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004c9f5`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004c9f5`

## string_xrefs

- `0x18004c995`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004ca06`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004ca5e`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004c91d`: `CCellularSettingHelperCommon::_GetProvisioningState`
- `0x18004caec`: `CCellularSettingHelperCommon::_GetProvisioningState`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
int __fastcall CCellularSettingHelperCommon::_GetProvisioningState(CCellularSettingHelperCommon *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  unsigned int v5; // eax
  unsigned int Interface; // eax
  int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // r8
  __int64 v11; // rcx
  int v12; // eax
  const struct _tlgProvider_t *v13; // rax
  __int64 v14; // r8
  __int64 v15; // r9
  unsigned int v16; // [rsp+20h] [rbp-59h]
  unsigned int *v17; // [rsp+20h] [rbp-59h]
  __int64 v18; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v19[4]; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int16 *v20[2]; // [rsp+58h] [rbp-21h] BYREF
  __int64 v21; // [rsp+68h] [rbp-11h]
  unsigned __int16 *v22[2]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v23; // [rsp+80h] [rbp+7h]
  unsigned __int16 *v24[2]; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v25; // [rsp+98h] [rbp+1Fh]
  unsigned __int16 *v26[2]; // [rsp+A0h] [rbp+27h] BYREF
  __int64 v27; // [rsp+B0h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  unsigned int v29; // [rsp+E8h] [rbp+6Fh] BYREF
  int v30; // [rsp+F0h] [rbp+77h] BYREF
  __int64 v31; // [rsp+F8h] [rbp+7Fh] BYREF

  *(_OWORD *)v20 = 0;
  v21 = 0;
  *(_OWORD *)v22 = 0;
  v23 = 0;
  std::vector<unsigned short>::resize(v20);
  std::vector<unsigned short>::resize(v22);
  StringCchPrintfW(v20[0], v20[1] - v20[0], L"Enter");
  v16 = 199;
  StringCchPrintfW(v22[0], v22[1] - v22[0], L"%S(%d):%s", "CCellularSettingHelperCommon::_GetProvisioningState");
  v2 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    *(unsigned __int16 **)v19 = v22[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)qword_1800791F0,
      v3,
      v4,
      (const unsigned __int16 **)v19);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v22);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v20);
  v18 = 0;
  v30 = 0;
  v5 = WwanOpenHandle(1, 0, &v30, &v18);
  if ( v5 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xC9,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
             (const char *)v5,
             v16);
  v20[0] = (unsigned __int16 *)&v18;
  LOBYTE(v20[1]) = 1;
  v29 = 0;
  v31 = 0;
  v22[0] = (unsigned __int16 *)&v31;
  LOBYTE(v22[1]) = 1;
  v17 = &v29;
  Interface = WwanQueryInterface(v18, (char *)this + 8, 41);
  if ( Interface )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xD7,
           (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
           (const char *)Interface,
           (unsigned int)&v29);
  }
  else
  {
    v9 = v29;
    v10 = v31;
    *(_OWORD *)v19 = 0;
    v11 = *((_QWORD *)this + 5);
    if ( v11 )
    {
      *(_QWORD *)v19 = *((_QWORD *)this + 4);
      *(_QWORD *)&v19[2] = v11;
      _InterlockedIncrement((volatile signed __int32 *)(v11 + 12));
    }
    v12 = CWwanTranslator::ProcessProvisioningStateChange(v19, (char *)this + 8, v10, v9);
    v8 = v12;
    if ( v12 >= 0 )
    {
      *(_OWORD *)v26 = 0;
      v27 = 0;
      *(_OWORD *)v24 = 0;
      v25 = 0;
      std::vector<unsigned short>::resize(v26);
      std::vector<unsigned short>::resize(v24);
      StringCchPrintfW(v26[0], v26[1] - v26[0], L"Exit");
      LODWORD(v17) = 219;
      StringCchPrintfW(
        v24[0],
        v24[1] - v24[0],
        L"%S(%d):%s",
        "CCellularSettingHelperCommon::_GetProvisioningState",
        v17,
        v26[0],
        0,
        0);
      v13 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v13 > 5u )
      {
        *(unsigned __int16 **)v19 = v24[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v13,
          (__int64)&byte_180079187,
          v14,
          v15,
          (const unsigned __int16 **)v19);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v24);
      std::vector<unsigned short>::~vector<unsigned short>((char **)v26);
      if ( v31 )
      {
        WwanFreeMemory(v31);
        v31 = 0;
      }
      v8 = 0;
      goto LABEL_18;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
      (const char *)(unsigned int)v12,
      (int)&v29);
  }
  if ( v31 )
  {
    WwanFreeMemory(v31);
    v31 = 0;
  }
LABEL_18:
  WwanCloseHandle(v18, 0);
  return v8;
}

```

## disassembly

```asm
0x18004c8a4  mov     [rsp-8+arg_0], rbx
0x18004c8a9  push    rbp
0x18004c8aa  push    rsi
0x18004c8ab  push    rdi
0x18004c8ac  lea     rbp, [rsp-47h]
0x18004c8b1  sub     rsp, 0C0h
0x18004c8b8  mov     rbx, rcx
0x18004c8bb  xorps   xmm0, xmm0
0x18004c8be  movdqu  xmmword ptr [rbp+57h+var_78], xmm0
0x18004c8c3  xor     esi, esi
0x18004c8c5  mov     [rbp+57h+var_68], rsi
0x18004c8c9  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x18004c8ce  mov     [rbp+57h+var_50], rsi
0x18004c8d2  lea     rcx, [rbp+57h+var_78]
0x18004c8d6  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004c8db  lea     rcx, [rbp+57h+var_60]
0x18004c8df  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004c8e4  mov     rdx, [rbp+57h+var_78+8]
0x18004c8e8  mov     rcx, [rbp+57h+var_78]; unsigned __int16 *
0x18004c8ec  sub     rdx, rcx
0x18004c8ef  sar     rdx, 1; unsigned __int64
0x18004c8f2  lea     r8, aEnter; "Enter"
0x18004c8f9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004c8fe  mov     rdx, [rbp+57h+var_60+8]
0x18004c902  mov     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x18004c906  sub     rdx, rcx
0x18004c909  sar     rdx, 1; unsigned __int64
0x18004c90c  mov     rax, [rbp+57h+var_78]
0x18004c910  mov     [rsp+0D0h+var_A8], rax
0x18004c915  mov     [rsp+0D0h+var_B0], 0C7h
0x18004c91d  lea     r9, aCcellularsetti_36; "CCellularSettingHelperCommon::_GetProvi"...
0x18004c924  lea     r8, aSDS; "%S(%d):%s"
0x18004c92b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004c930  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004c935  mov     ecx, [rax]
0x18004c937  cmp     ecx, 5
0x18004c93a  jbe     short loc_18004C95D
0x18004c93c  mov     rcx, [rbp+57h+var_60]
0x18004c940  mov     qword ptr [rbp+57h+var_88], rcx
0x18004c944  lea     rcx, [rbp+57h+var_88]
0x18004c948  mov     qword ptr [rsp+0D0h+var_B0], rcx; unsigned int
0x18004c94d  lea     rdx, qword_1800791F0
0x18004c954  mov     rcx, rax
0x18004c957  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004c95c  nop
0x18004c95d  lea     rcx, [rbp+57h+var_60]
0x18004c961  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004c966  nop
0x18004c967  lea     rcx, [rbp+57h+var_78]
0x18004c96b  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004c970  mov     [rbp+57h+var_90], rsi
0x18004c974  mov     [rbp+57h+arg_10], esi
0x18004c977  lea     r9, [rbp+57h+var_90]
0x18004c97b  lea     r8, [rbp+57h+arg_10]
0x18004c97f  xor     edx, edx
0x18004c981  lea     ecx, [rdx+1]
0x18004c984  call    cs:__imp_WwanOpenHandle
0x18004c98a  test    eax, eax
0x18004c98c  jz      short loc_18004C9AB
0x18004c98e  mov     rcx, [rbp+5Fh]; this
0x18004c992  mov     r9d, eax; char *
0x18004c995  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004c99c  mov     edx, 0C9h; void *
0x18004c9a1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004c9a6  jmp     loc_18004CB63
0x18004c9ab  lea     rax, [rbp+57h+var_90]
0x18004c9af  mov     [rbp+57h+var_78], rax
0x18004c9b3  mov     byte ptr [rbp+57h+var_78+8], 1
0x18004c9b7  mov     [rbp+57h+arg_8], esi
0x18004c9ba  mov     [rbp+57h+arg_18], rsi
0x18004c9be  lea     rax, [rbp+57h+arg_18]
0x18004c9c2  mov     [rbp+57h+var_60], rax
0x18004c9c6  mov     byte ptr [rbp+57h+var_60+8], 1
0x18004c9ca  mov     [rsp+0D0h+var_98], rsi
0x18004c9cf  mov     [rsp+0D0h+var_A0], rsi
0x18004c9d4  lea     rax, [rbp+57h+arg_18]
0x18004c9d8  mov     [rsp+0D0h+var_A8], rax
0x18004c9dd  lea     rax, [rbp+57h+arg_8]
0x18004c9e1  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18004c9e6  xor     r9d, r9d
0x18004c9e9  lea     r8d, [r9+29h]
0x18004c9ed  lea     rdx, [rbx+8]
0x18004c9f1  mov     rcx, [rbp+57h+var_90]
0x18004c9f5  call    cs:__imp_WwanQueryInterface
0x18004c9fb  test    eax, eax
0x18004c9fd  jz      short loc_18004CA1B
0x18004c9ff  mov     rcx, [rbp+5Fh]; this
0x18004ca03  mov     r9d, eax; char *
0x18004ca06  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004ca0d  mov     edx, 0D7h; void *
0x18004ca12  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004ca17  mov     ebx, eax
0x18004ca19  jmp     short loc_18004CA70
0x18004ca1b  mov     r9d, [rbp+57h+arg_8]
0x18004ca1f  mov     r8, [rbp+57h+arg_18]
0x18004ca23  xorps   xmm0, xmm0
0x18004ca26  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x18004ca2b  mov     rcx, [rbx+28h]
0x18004ca2f  test    rcx, rcx
0x18004ca32  jz      short loc_18004CA44
0x18004ca34  mov     rax, [rbx+20h]
0x18004ca38  mov     qword ptr [rbp+57h+var_88], rax
0x18004ca3c  mov     qword ptr [rbp+57h+var_88+8], rcx
0x18004ca40  lock inc dword ptr [rcx+0Ch]
0x18004ca44  lea     rdx, [rbx+8]
0x18004ca48  lea     rcx, [rbp+57h+var_88]
0x18004ca4c  call    ?ProcessProvisioningStateChange@CWwanTranslator@@SAJV?$weak_ptr@VCWwanTranslator@@@std@@AEBU_GUID@@PEAEI@Z; CWwanTranslator::ProcessProvisioningStateChange(std::weak_ptr<CWwanTranslator>,_GUID const &,uchar *,uint)
0x18004ca51  mov     ebx, eax
0x18004ca53  test    eax, eax
0x18004ca55  jns     short loc_18004CA8C
0x18004ca57  mov     rcx, [rbp+5Fh]; this
0x18004ca5b  mov     r9d, eax; char *
0x18004ca5e  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004ca65  mov     edx, 0D9h; void *
0x18004ca6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ca6f  nop
0x18004ca70  mov     rcx, [rbp+57h+arg_18]
0x18004ca74  test    rcx, rcx
0x18004ca77  jz      loc_18004CB55
0x18004ca7d  call    cs:__imp_WwanFreeMemory
0x18004ca83  mov     [rbp+57h+arg_18], rsi
0x18004ca87  jmp     loc_18004CB55
0x18004ca8c  xorps   xmm0, xmm0
0x18004ca8f  movdqu  xmmword ptr [rbp+57h+var_30], xmm0
0x18004ca94  mov     [rbp+57h+var_20], rsi
0x18004ca98  movdqu  xmmword ptr [rbp+57h+var_48], xmm0
0x18004ca9d  mov     [rbp+57h+var_38], rsi
0x18004caa1  lea     rcx, [rbp+57h+var_30]
0x18004caa5  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004caaa  lea     rcx, [rbp+57h+var_48]
0x18004caae  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004cab3  mov     rdx, [rbp+57h+var_30+8]
0x18004cab7  mov     rcx, [rbp+57h+var_30]; unsigned __int16 *
0x18004cabb  sub     rdx, rcx
0x18004cabe  sar     rdx, 1; unsigned __int64
0x18004cac1  lea     r8, aExit; "Exit"
0x18004cac8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004cacd  mov     rdx, [rbp+57h+var_48+8]
0x18004cad1  mov     rcx, [rbp+57h+var_48]; unsigned __int16 *
0x18004cad5  sub     rdx, rcx
0x18004cad8  sar     rdx, 1; unsigned __int64
0x18004cadb  mov     rax, [rbp+57h+var_30]
0x18004cadf  mov     [rsp+0D0h+var_A8], rax
0x18004cae4  mov     [rsp+0D0h+var_B0], 0DBh
0x18004caec  lea     r9, aCcellularsetti_36; "CCellularSettingHelperCommon::_GetProvi"...
0x18004caf3  lea     r8, aSDS; "%S(%d):%s"
0x18004cafa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004caff  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004cb04  mov     ecx, [rax]
0x18004cb06  cmp     ecx, 5
0x18004cb09  jbe     short loc_18004CB2C
0x18004cb0b  mov     rcx, [rbp+57h+var_48]
0x18004cb0f  mov     qword ptr [rbp+57h+var_88], rcx
0x18004cb13  lea     rcx, [rbp+57h+var_88]
0x18004cb17  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x18004cb1c  lea     rdx, byte_180079187
0x18004cb23  mov     rcx, rax
0x18004cb26  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004cb2b  nop
0x18004cb2c  lea     rcx, [rbp+57h+var_48]
0x18004cb30  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004cb35  nop
0x18004cb36  lea     rcx, [rbp+57h+var_30]
0x18004cb3a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004cb3f  nop
0x18004cb40  mov     rcx, [rbp+57h+arg_18]
0x18004cb44  test    rcx, rcx
0x18004cb47  jz      short loc_18004CB53
0x18004cb49  call    cs:__imp_WwanFreeMemory
0x18004cb4f  mov     [rbp+57h+arg_18], rsi
0x18004cb53  mov     ebx, esi
0x18004cb55  xor     edx, edx
0x18004cb57  mov     rcx, [rbp+57h+var_90]
0x18004cb5b  call    cs:__imp_WwanCloseHandle
0x18004cb61  mov     eax, ebx
0x18004cb63  mov     rbx, [rsp+0D0h+arg_0]
0x18004cb6b  add     rsp, 0C0h
0x18004cb72  pop     rdi
0x18004cb73  pop     rsi
0x18004cb74  pop     rbp
0x18004cb75  retn
```
