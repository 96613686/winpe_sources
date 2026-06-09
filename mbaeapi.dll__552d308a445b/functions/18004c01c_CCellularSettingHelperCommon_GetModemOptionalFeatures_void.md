# CCellularSettingHelperCommon::_GetModemOptionalFeatures(void)

- ea: `0x18004c01c`
- end: `0x18004c2ee`
- name: `?_GetModemOptionalFeatures@CCellularSettingHelperCommon@@IEAAJXZ`
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
- `0x1800372a8`
- `0x18004c01c`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004c2d3`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004c2d3`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004c1f5`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004c2c1`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004c1f5`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004c2c1`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004c0fc`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004c0fc`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004c16d`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004c16d`

## string_xrefs

- `0x18004c10d`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004c17e`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004c1d6`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004c095`: `CCellularSettingHelperCommon::_GetModemOptionalFeatures`
- `0x18004c264`: `CCellularSettingHelperCommon::_GetModemOptionalFeatures`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
int __fastcall CCellularSettingHelperCommon::_GetModemOptionalFeatures(CCellularSettingHelperCommon *this)
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
  v16 = 1018;
  StringCchPrintfW(v22[0], v22[1] - v22[0], L"%S(%d):%s", "CCellularSettingHelperCommon::_GetModemOptionalFeatures");
  v2 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    *(unsigned __int16 **)v19 = v22[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)&byte_18007899F,
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
             (void *)0x3FC,
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
  Interface = WwanQueryInterface(v18, (char *)this + 8, 53);
  if ( Interface )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x40A,
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
    v12 = CWwanTranslator::ProcessModemOptionalFeaturesPresent(v19, (char *)this + 8, v10, v9);
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
      LODWORD(v17) = 1038;
      StringCchPrintfW(
        v24[0],
        v24[1] - v24[0],
        L"%S(%d):%s",
        "CCellularSettingHelperCommon::_GetModemOptionalFeatures",
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
          (__int64)word_1800789C2,
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
      (void *)0x40C,
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
0x18004c01c  mov     [rsp-8+arg_0], rbx
0x18004c021  push    rbp
0x18004c022  push    rsi
0x18004c023  push    rdi
0x18004c024  lea     rbp, [rsp-47h]
0x18004c029  sub     rsp, 0C0h
0x18004c030  mov     rbx, rcx
0x18004c033  xorps   xmm0, xmm0
0x18004c036  movdqu  xmmword ptr [rbp+57h+var_78], xmm0
0x18004c03b  xor     esi, esi
0x18004c03d  mov     [rbp+57h+var_68], rsi
0x18004c041  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x18004c046  mov     [rbp+57h+var_50], rsi
0x18004c04a  lea     rcx, [rbp+57h+var_78]
0x18004c04e  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004c053  lea     rcx, [rbp+57h+var_60]
0x18004c057  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004c05c  mov     rdx, [rbp+57h+var_78+8]
0x18004c060  mov     rcx, [rbp+57h+var_78]; unsigned __int16 *
0x18004c064  sub     rdx, rcx
0x18004c067  sar     rdx, 1; unsigned __int64
0x18004c06a  lea     r8, aEnter; "Enter"
0x18004c071  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004c076  mov     rdx, [rbp+57h+var_60+8]
0x18004c07a  mov     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x18004c07e  sub     rdx, rcx
0x18004c081  sar     rdx, 1; unsigned __int64
0x18004c084  mov     rax, [rbp+57h+var_78]
0x18004c088  mov     [rsp+0D0h+var_A8], rax
0x18004c08d  mov     [rsp+0D0h+var_B0], 3FAh
0x18004c095  lea     r9, aCcellularsetti_11; "CCellularSettingHelperCommon::_GetModem"...
0x18004c09c  lea     r8, aSDS; "%S(%d):%s"
0x18004c0a3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004c0a8  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004c0ad  mov     ecx, [rax]
0x18004c0af  cmp     ecx, 5
0x18004c0b2  jbe     short loc_18004C0D5
0x18004c0b4  mov     rcx, [rbp+57h+var_60]
0x18004c0b8  mov     qword ptr [rbp+57h+var_88], rcx
0x18004c0bc  lea     rcx, [rbp+57h+var_88]
0x18004c0c0  mov     qword ptr [rsp+0D0h+var_B0], rcx; unsigned int
0x18004c0c5  lea     rdx, byte_18007899F
0x18004c0cc  mov     rcx, rax
0x18004c0cf  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004c0d4  nop
0x18004c0d5  lea     rcx, [rbp+57h+var_60]
0x18004c0d9  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004c0de  nop
0x18004c0df  lea     rcx, [rbp+57h+var_78]
0x18004c0e3  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004c0e8  mov     [rbp+57h+var_90], rsi
0x18004c0ec  mov     [rbp+57h+arg_10], esi
0x18004c0ef  lea     r9, [rbp+57h+var_90]
0x18004c0f3  lea     r8, [rbp+57h+arg_10]
0x18004c0f7  xor     edx, edx
0x18004c0f9  lea     ecx, [rdx+1]
0x18004c0fc  call    cs:__imp_WwanOpenHandle
0x18004c102  test    eax, eax
0x18004c104  jz      short loc_18004C123
0x18004c106  mov     rcx, [rbp+5Fh]; this
0x18004c10a  mov     r9d, eax; char *
0x18004c10d  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004c114  mov     edx, 3FCh; void *
0x18004c119  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004c11e  jmp     loc_18004C2DB
0x18004c123  lea     rax, [rbp+57h+var_90]
0x18004c127  mov     [rbp+57h+var_78], rax
0x18004c12b  mov     byte ptr [rbp+57h+var_78+8], 1
0x18004c12f  mov     [rbp+57h+arg_8], esi
0x18004c132  mov     [rbp+57h+arg_18], rsi
0x18004c136  lea     rax, [rbp+57h+arg_18]
0x18004c13a  mov     [rbp+57h+var_60], rax
0x18004c13e  mov     byte ptr [rbp+57h+var_60+8], 1
0x18004c142  mov     [rsp+0D0h+var_98], rsi
0x18004c147  mov     [rsp+0D0h+var_A0], rsi
0x18004c14c  lea     rax, [rbp+57h+arg_18]
0x18004c150  mov     [rsp+0D0h+var_A8], rax
0x18004c155  lea     rax, [rbp+57h+arg_8]
0x18004c159  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18004c15e  xor     r9d, r9d
0x18004c161  lea     r8d, [r9+35h]
0x18004c165  lea     rdx, [rbx+8]
0x18004c169  mov     rcx, [rbp+57h+var_90]
0x18004c16d  call    cs:__imp_WwanQueryInterface
0x18004c173  test    eax, eax
0x18004c175  jz      short loc_18004C193
0x18004c177  mov     rcx, [rbp+5Fh]; this
0x18004c17b  mov     r9d, eax; char *
0x18004c17e  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004c185  mov     edx, 40Ah; void *
0x18004c18a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004c18f  mov     ebx, eax
0x18004c191  jmp     short loc_18004C1E8
0x18004c193  mov     r9d, [rbp+57h+arg_8]
0x18004c197  mov     r8, [rbp+57h+arg_18]
0x18004c19b  xorps   xmm0, xmm0
0x18004c19e  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x18004c1a3  mov     rcx, [rbx+28h]
0x18004c1a7  test    rcx, rcx
0x18004c1aa  jz      short loc_18004C1BC
0x18004c1ac  mov     rax, [rbx+20h]
0x18004c1b0  mov     qword ptr [rbp+57h+var_88], rax
0x18004c1b4  mov     qword ptr [rbp+57h+var_88+8], rcx
0x18004c1b8  lock inc dword ptr [rcx+0Ch]
0x18004c1bc  lea     rdx, [rbx+8]
0x18004c1c0  lea     rcx, [rbp+57h+var_88]
0x18004c1c4  call    ?ProcessModemOptionalFeaturesPresent@CWwanTranslator@@SAJV?$weak_ptr@VCWwanTranslator@@@std@@AEBU_GUID@@PEAEI@Z; CWwanTranslator::ProcessModemOptionalFeaturesPresent(std::weak_ptr<CWwanTranslator>,_GUID const &,uchar *,uint)
0x18004c1c9  mov     ebx, eax
0x18004c1cb  test    eax, eax
0x18004c1cd  jns     short loc_18004C204
0x18004c1cf  mov     rcx, [rbp+5Fh]; this
0x18004c1d3  mov     r9d, eax; char *
0x18004c1d6  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004c1dd  mov     edx, 40Ch; void *
0x18004c1e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c1e7  nop
0x18004c1e8  mov     rcx, [rbp+57h+arg_18]
0x18004c1ec  test    rcx, rcx
0x18004c1ef  jz      loc_18004C2CD
0x18004c1f5  call    cs:__imp_WwanFreeMemory
0x18004c1fb  mov     [rbp+57h+arg_18], rsi
0x18004c1ff  jmp     loc_18004C2CD
0x18004c204  xorps   xmm0, xmm0
0x18004c207  movdqu  xmmword ptr [rbp+57h+var_30], xmm0
0x18004c20c  mov     [rbp+57h+var_20], rsi
0x18004c210  movdqu  xmmword ptr [rbp+57h+var_48], xmm0
0x18004c215  mov     [rbp+57h+var_38], rsi
0x18004c219  lea     rcx, [rbp+57h+var_30]
0x18004c21d  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004c222  lea     rcx, [rbp+57h+var_48]
0x18004c226  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004c22b  mov     rdx, [rbp+57h+var_30+8]
0x18004c22f  mov     rcx, [rbp+57h+var_30]; unsigned __int16 *
0x18004c233  sub     rdx, rcx
0x18004c236  sar     rdx, 1; unsigned __int64
0x18004c239  lea     r8, aExit; "Exit"
0x18004c240  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004c245  mov     rdx, [rbp+57h+var_48+8]
0x18004c249  mov     rcx, [rbp+57h+var_48]; unsigned __int16 *
0x18004c24d  sub     rdx, rcx
0x18004c250  sar     rdx, 1; unsigned __int64
0x18004c253  mov     rax, [rbp+57h+var_30]
0x18004c257  mov     [rsp+0D0h+var_A8], rax
0x18004c25c  mov     [rsp+0D0h+var_B0], 40Eh
0x18004c264  lea     r9, aCcellularsetti_11; "CCellularSettingHelperCommon::_GetModem"...
0x18004c26b  lea     r8, aSDS; "%S(%d):%s"
0x18004c272  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004c277  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004c27c  mov     ecx, [rax]
0x18004c27e  cmp     ecx, 5
0x18004c281  jbe     short loc_18004C2A4
0x18004c283  mov     rcx, [rbp+57h+var_48]
0x18004c287  mov     qword ptr [rbp+57h+var_88], rcx
0x18004c28b  lea     rcx, [rbp+57h+var_88]
0x18004c28f  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x18004c294  lea     rdx, word_1800789C2
0x18004c29b  mov     rcx, rax
0x18004c29e  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004c2a3  nop
0x18004c2a4  lea     rcx, [rbp+57h+var_48]
0x18004c2a8  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004c2ad  nop
0x18004c2ae  lea     rcx, [rbp+57h+var_30]
0x18004c2b2  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004c2b7  nop
0x18004c2b8  mov     rcx, [rbp+57h+arg_18]
0x18004c2bc  test    rcx, rcx
0x18004c2bf  jz      short loc_18004C2CB
0x18004c2c1  call    cs:__imp_WwanFreeMemory
0x18004c2c7  mov     [rbp+57h+arg_18], rsi
0x18004c2cb  mov     ebx, esi
0x18004c2cd  xor     edx, edx
0x18004c2cf  mov     rcx, [rbp+57h+var_90]
0x18004c2d3  call    cs:__imp_WwanCloseHandle
0x18004c2d9  mov     eax, ebx
0x18004c2db  mov     rbx, [rsp+0D0h+arg_0]
0x18004c2e3  add     rsp, 0C0h
0x18004c2ea  pop     rdi
0x18004c2eb  pop     rsi
0x18004c2ec  pop     rbp
0x18004c2ed  retn
```
