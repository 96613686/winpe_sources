# CCellularSettingHelperCommon::_GetMultiSimInfo(void)

- ea: `0x18004c2f4`
- end: `0x18004c5c6`
- name: `?_GetMultiSimInfo@CCellularSettingHelperCommon@@IEAAJXZ`
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
- `0x1800374b8`
- `0x18004c2f4`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004c5ab`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004c5ab`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004c4cd`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004c599`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004c4cd`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004c599`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004c3d4`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004c3d4`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004c445`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004c445`

## string_xrefs

- `0x18004c3e5`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004c456`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004c4ae`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004c36d`: `CCellularSettingHelperCommon::_GetMultiSimInfo`
- `0x18004c53c`: `CCellularSettingHelperCommon::_GetMultiSimInfo`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
int __fastcall CCellularSettingHelperCommon::_GetMultiSimInfo(CCellularSettingHelperCommon *this)
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
  v16 = 403;
  StringCchPrintfW(v22[0], v22[1] - v22[0], L"%S(%d):%s", "CCellularSettingHelperCommon::_GetMultiSimInfo");
  v2 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    *(unsigned __int16 **)v19 = v22[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)word_180078F42,
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
             (void *)0x195,
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
  Interface = WwanQueryInterface(v18, (char *)this + 8, 46);
  if ( Interface )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1A3,
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
    v12 = CWwanTranslator::ProcessMultiSimInfoChange(v19, (char *)this + 8, v10, v9);
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
      LODWORD(v17) = 423;
      StringCchPrintfW(
        v24[0],
        v24[1] - v24[0],
        L"%S(%d):%s",
        "CCellularSettingHelperCommon::_GetMultiSimInfo",
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
          (__int64)byte_180078F65,
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
      (void *)0x1A5,
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
0x18004c2f4  mov     [rsp-8+arg_0], rbx
0x18004c2f9  push    rbp
0x18004c2fa  push    rsi
0x18004c2fb  push    rdi
0x18004c2fc  lea     rbp, [rsp-47h]
0x18004c301  sub     rsp, 0C0h
0x18004c308  mov     rbx, rcx
0x18004c30b  xorps   xmm0, xmm0
0x18004c30e  movdqu  xmmword ptr [rbp+57h+var_78], xmm0
0x18004c313  xor     esi, esi
0x18004c315  mov     [rbp+57h+var_68], rsi
0x18004c319  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x18004c31e  mov     [rbp+57h+var_50], rsi
0x18004c322  lea     rcx, [rbp+57h+var_78]
0x18004c326  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004c32b  lea     rcx, [rbp+57h+var_60]
0x18004c32f  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004c334  mov     rdx, [rbp+57h+var_78+8]
0x18004c338  mov     rcx, [rbp+57h+var_78]; unsigned __int16 *
0x18004c33c  sub     rdx, rcx
0x18004c33f  sar     rdx, 1; unsigned __int64
0x18004c342  lea     r8, aEnter; "Enter"
0x18004c349  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004c34e  mov     rdx, [rbp+57h+var_60+8]
0x18004c352  mov     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x18004c356  sub     rdx, rcx
0x18004c359  sar     rdx, 1; unsigned __int64
0x18004c35c  mov     rax, [rbp+57h+var_78]
0x18004c360  mov     [rsp+0D0h+var_A8], rax
0x18004c365  mov     [rsp+0D0h+var_B0], 193h
0x18004c36d  lea     r9, aCcellularsetti_14; "CCellularSettingHelperCommon::_GetMulti"...
0x18004c374  lea     r8, aSDS; "%S(%d):%s"
0x18004c37b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004c380  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004c385  mov     ecx, [rax]
0x18004c387  cmp     ecx, 5
0x18004c38a  jbe     short loc_18004C3AD
0x18004c38c  mov     rcx, [rbp+57h+var_60]
0x18004c390  mov     qword ptr [rbp+57h+var_88], rcx
0x18004c394  lea     rcx, [rbp+57h+var_88]
0x18004c398  mov     qword ptr [rsp+0D0h+var_B0], rcx; unsigned int
0x18004c39d  lea     rdx, word_180078F42
0x18004c3a4  mov     rcx, rax
0x18004c3a7  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004c3ac  nop
0x18004c3ad  lea     rcx, [rbp+57h+var_60]
0x18004c3b1  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004c3b6  nop
0x18004c3b7  lea     rcx, [rbp+57h+var_78]
0x18004c3bb  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004c3c0  mov     [rbp+57h+var_90], rsi
0x18004c3c4  mov     [rbp+57h+arg_10], esi
0x18004c3c7  lea     r9, [rbp+57h+var_90]
0x18004c3cb  lea     r8, [rbp+57h+arg_10]
0x18004c3cf  xor     edx, edx
0x18004c3d1  lea     ecx, [rdx+1]
0x18004c3d4  call    cs:__imp_WwanOpenHandle
0x18004c3da  test    eax, eax
0x18004c3dc  jz      short loc_18004C3FB
0x18004c3de  mov     rcx, [rbp+5Fh]; this
0x18004c3e2  mov     r9d, eax; char *
0x18004c3e5  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004c3ec  mov     edx, 195h; void *
0x18004c3f1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004c3f6  jmp     loc_18004C5B3
0x18004c3fb  lea     rax, [rbp+57h+var_90]
0x18004c3ff  mov     [rbp+57h+var_78], rax
0x18004c403  mov     byte ptr [rbp+57h+var_78+8], 1
0x18004c407  mov     [rbp+57h+arg_8], esi
0x18004c40a  mov     [rbp+57h+arg_18], rsi
0x18004c40e  lea     rax, [rbp+57h+arg_18]
0x18004c412  mov     [rbp+57h+var_60], rax
0x18004c416  mov     byte ptr [rbp+57h+var_60+8], 1
0x18004c41a  mov     [rsp+0D0h+var_98], rsi
0x18004c41f  mov     [rsp+0D0h+var_A0], rsi
0x18004c424  lea     rax, [rbp+57h+arg_18]
0x18004c428  mov     [rsp+0D0h+var_A8], rax
0x18004c42d  lea     rax, [rbp+57h+arg_8]
0x18004c431  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18004c436  xor     r9d, r9d
0x18004c439  lea     r8d, [r9+2Eh]
0x18004c43d  lea     rdx, [rbx+8]
0x18004c441  mov     rcx, [rbp+57h+var_90]
0x18004c445  call    cs:__imp_WwanQueryInterface
0x18004c44b  test    eax, eax
0x18004c44d  jz      short loc_18004C46B
0x18004c44f  mov     rcx, [rbp+5Fh]; this
0x18004c453  mov     r9d, eax; char *
0x18004c456  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004c45d  mov     edx, 1A3h; void *
0x18004c462  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004c467  mov     ebx, eax
0x18004c469  jmp     short loc_18004C4C0
0x18004c46b  mov     r9d, [rbp+57h+arg_8]
0x18004c46f  mov     r8, [rbp+57h+arg_18]
0x18004c473  xorps   xmm0, xmm0
0x18004c476  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x18004c47b  mov     rcx, [rbx+28h]
0x18004c47f  test    rcx, rcx
0x18004c482  jz      short loc_18004C494
0x18004c484  mov     rax, [rbx+20h]
0x18004c488  mov     qword ptr [rbp+57h+var_88], rax
0x18004c48c  mov     qword ptr [rbp+57h+var_88+8], rcx
0x18004c490  lock inc dword ptr [rcx+0Ch]
0x18004c494  lea     rdx, [rbx+8]
0x18004c498  lea     rcx, [rbp+57h+var_88]
0x18004c49c  call    ?ProcessMultiSimInfoChange@CWwanTranslator@@SAJV?$weak_ptr@VCWwanTranslator@@@std@@AEBU_GUID@@PEAEI@Z; CWwanTranslator::ProcessMultiSimInfoChange(std::weak_ptr<CWwanTranslator>,_GUID const &,uchar *,uint)
0x18004c4a1  mov     ebx, eax
0x18004c4a3  test    eax, eax
0x18004c4a5  jns     short loc_18004C4DC
0x18004c4a7  mov     rcx, [rbp+5Fh]; this
0x18004c4ab  mov     r9d, eax; char *
0x18004c4ae  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004c4b5  mov     edx, 1A5h; void *
0x18004c4ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c4bf  nop
0x18004c4c0  mov     rcx, [rbp+57h+arg_18]
0x18004c4c4  test    rcx, rcx
0x18004c4c7  jz      loc_18004C5A5
0x18004c4cd  call    cs:__imp_WwanFreeMemory
0x18004c4d3  mov     [rbp+57h+arg_18], rsi
0x18004c4d7  jmp     loc_18004C5A5
0x18004c4dc  xorps   xmm0, xmm0
0x18004c4df  movdqu  xmmword ptr [rbp+57h+var_30], xmm0
0x18004c4e4  mov     [rbp+57h+var_20], rsi
0x18004c4e8  movdqu  xmmword ptr [rbp+57h+var_48], xmm0
0x18004c4ed  mov     [rbp+57h+var_38], rsi
0x18004c4f1  lea     rcx, [rbp+57h+var_30]
0x18004c4f5  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004c4fa  lea     rcx, [rbp+57h+var_48]
0x18004c4fe  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004c503  mov     rdx, [rbp+57h+var_30+8]
0x18004c507  mov     rcx, [rbp+57h+var_30]; unsigned __int16 *
0x18004c50b  sub     rdx, rcx
0x18004c50e  sar     rdx, 1; unsigned __int64
0x18004c511  lea     r8, aExit; "Exit"
0x18004c518  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004c51d  mov     rdx, [rbp+57h+var_48+8]
0x18004c521  mov     rcx, [rbp+57h+var_48]; unsigned __int16 *
0x18004c525  sub     rdx, rcx
0x18004c528  sar     rdx, 1; unsigned __int64
0x18004c52b  mov     rax, [rbp+57h+var_30]
0x18004c52f  mov     [rsp+0D0h+var_A8], rax
0x18004c534  mov     [rsp+0D0h+var_B0], 1A7h
0x18004c53c  lea     r9, aCcellularsetti_14; "CCellularSettingHelperCommon::_GetMulti"...
0x18004c543  lea     r8, aSDS; "%S(%d):%s"
0x18004c54a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004c54f  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004c554  mov     ecx, [rax]
0x18004c556  cmp     ecx, 5
0x18004c559  jbe     short loc_18004C57C
0x18004c55b  mov     rcx, [rbp+57h+var_48]
0x18004c55f  mov     qword ptr [rbp+57h+var_88], rcx
0x18004c563  lea     rcx, [rbp+57h+var_88]
0x18004c567  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x18004c56c  lea     rdx, byte_180078F65
0x18004c573  mov     rcx, rax
0x18004c576  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004c57b  nop
0x18004c57c  lea     rcx, [rbp+57h+var_48]
0x18004c580  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004c585  nop
0x18004c586  lea     rcx, [rbp+57h+var_30]
0x18004c58a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004c58f  nop
0x18004c590  mov     rcx, [rbp+57h+arg_18]
0x18004c594  test    rcx, rcx
0x18004c597  jz      short loc_18004C5A3
0x18004c599  call    cs:__imp_WwanFreeMemory
0x18004c59f  mov     [rbp+57h+arg_18], rsi
0x18004c5a3  mov     ebx, esi
0x18004c5a5  xor     edx, edx
0x18004c5a7  mov     rcx, [rbp+57h+var_90]
0x18004c5ab  call    cs:__imp_WwanCloseHandle
0x18004c5b1  mov     eax, ebx
0x18004c5b3  mov     rbx, [rsp+0D0h+arg_0]
0x18004c5bb  add     rsp, 0C0h
0x18004c5c2  pop     rdi
0x18004c5c3  pop     rsi
0x18004c5c4  pop     rbp
0x18004c5c5  retn
```
