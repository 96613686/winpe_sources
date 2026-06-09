# CCellularSettingHelperCommon::_GetMultiSimSlotMapping(void)

- ea: `0x18004c5cc`
- end: `0x18004c89e`
- name: `?_GetMultiSimSlotMapping@CCellularSettingHelperCommon@@IEAAJXZ`
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
- `0x1800376c8`
- `0x18004c5cc`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004c883`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004c883`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004c7a5`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004c871`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004c7a5`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004c871`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004c6ac`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004c6ac`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004c71d`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004c71d`

## string_xrefs

- `0x18004c6bd`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004c72e`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004c786`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004c645`: `CCellularSettingHelperCommon::_GetMultiSimSlotMapping`
- `0x18004c814`: `CCellularSettingHelperCommon::_GetMultiSimSlotMapping`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
int __fastcall CCellularSettingHelperCommon::_GetMultiSimSlotMapping(CCellularSettingHelperCommon *this)
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
  v16 = 429;
  StringCchPrintfW(v22[0], v22[1] - v22[0], L"%S(%d):%s", "CCellularSettingHelperCommon::_GetMultiSimSlotMapping");
  v2 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    *(unsigned __int16 **)v19 = v22[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)&dword_180078EFC,
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
             (void *)0x1AF,
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
  Interface = WwanQueryInterface(v18, (char *)this + 8, 47);
  if ( Interface )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1BD,
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
    v12 = CWwanTranslator::ProcessMultiSimSlotMappingChange(v19, (char *)this + 8, v10, v9);
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
      LODWORD(v17) = 449;
      StringCchPrintfW(
        v24[0],
        v24[1] - v24[0],
        L"%S(%d):%s",
        "CCellularSettingHelperCommon::_GetMultiSimSlotMapping",
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
          (__int64)&byte_180078F1F,
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
      (void *)0x1BF,
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
0x18004c5cc  mov     [rsp-8+arg_0], rbx
0x18004c5d1  push    rbp
0x18004c5d2  push    rsi
0x18004c5d3  push    rdi
0x18004c5d4  lea     rbp, [rsp-47h]
0x18004c5d9  sub     rsp, 0C0h
0x18004c5e0  mov     rbx, rcx
0x18004c5e3  xorps   xmm0, xmm0
0x18004c5e6  movdqu  xmmword ptr [rbp+57h+var_78], xmm0
0x18004c5eb  xor     esi, esi
0x18004c5ed  mov     [rbp+57h+var_68], rsi
0x18004c5f1  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x18004c5f6  mov     [rbp+57h+var_50], rsi
0x18004c5fa  lea     rcx, [rbp+57h+var_78]
0x18004c5fe  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004c603  lea     rcx, [rbp+57h+var_60]
0x18004c607  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004c60c  mov     rdx, [rbp+57h+var_78+8]
0x18004c610  mov     rcx, [rbp+57h+var_78]; unsigned __int16 *
0x18004c614  sub     rdx, rcx
0x18004c617  sar     rdx, 1; unsigned __int64
0x18004c61a  lea     r8, aEnter; "Enter"
0x18004c621  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004c626  mov     rdx, [rbp+57h+var_60+8]
0x18004c62a  mov     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x18004c62e  sub     rdx, rcx
0x18004c631  sar     rdx, 1; unsigned __int64
0x18004c634  mov     rax, [rbp+57h+var_78]
0x18004c638  mov     [rsp+0D0h+var_A8], rax
0x18004c63d  mov     [rsp+0D0h+var_B0], 1ADh
0x18004c645  lea     r9, aCcellularsetti_21; "CCellularSettingHelperCommon::_GetMulti"...
0x18004c64c  lea     r8, aSDS; "%S(%d):%s"
0x18004c653  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004c658  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004c65d  mov     ecx, [rax]
0x18004c65f  cmp     ecx, 5
0x18004c662  jbe     short loc_18004C685
0x18004c664  mov     rcx, [rbp+57h+var_60]
0x18004c668  mov     qword ptr [rbp+57h+var_88], rcx
0x18004c66c  lea     rcx, [rbp+57h+var_88]
0x18004c670  mov     qword ptr [rsp+0D0h+var_B0], rcx; unsigned int
0x18004c675  lea     rdx, dword_180078EFC
0x18004c67c  mov     rcx, rax
0x18004c67f  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004c684  nop
0x18004c685  lea     rcx, [rbp+57h+var_60]
0x18004c689  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004c68e  nop
0x18004c68f  lea     rcx, [rbp+57h+var_78]
0x18004c693  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004c698  mov     [rbp+57h+var_90], rsi
0x18004c69c  mov     [rbp+57h+arg_10], esi
0x18004c69f  lea     r9, [rbp+57h+var_90]
0x18004c6a3  lea     r8, [rbp+57h+arg_10]
0x18004c6a7  xor     edx, edx
0x18004c6a9  lea     ecx, [rdx+1]
0x18004c6ac  call    cs:__imp_WwanOpenHandle
0x18004c6b2  test    eax, eax
0x18004c6b4  jz      short loc_18004C6D3
0x18004c6b6  mov     rcx, [rbp+5Fh]; this
0x18004c6ba  mov     r9d, eax; char *
0x18004c6bd  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004c6c4  mov     edx, 1AFh; void *
0x18004c6c9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004c6ce  jmp     loc_18004C88B
0x18004c6d3  lea     rax, [rbp+57h+var_90]
0x18004c6d7  mov     [rbp+57h+var_78], rax
0x18004c6db  mov     byte ptr [rbp+57h+var_78+8], 1
0x18004c6df  mov     [rbp+57h+arg_8], esi
0x18004c6e2  mov     [rbp+57h+arg_18], rsi
0x18004c6e6  lea     rax, [rbp+57h+arg_18]
0x18004c6ea  mov     [rbp+57h+var_60], rax
0x18004c6ee  mov     byte ptr [rbp+57h+var_60+8], 1
0x18004c6f2  mov     [rsp+0D0h+var_98], rsi
0x18004c6f7  mov     [rsp+0D0h+var_A0], rsi
0x18004c6fc  lea     rax, [rbp+57h+arg_18]
0x18004c700  mov     [rsp+0D0h+var_A8], rax
0x18004c705  lea     rax, [rbp+57h+arg_8]
0x18004c709  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18004c70e  xor     r9d, r9d
0x18004c711  lea     r8d, [r9+2Fh]
0x18004c715  lea     rdx, [rbx+8]
0x18004c719  mov     rcx, [rbp+57h+var_90]
0x18004c71d  call    cs:__imp_WwanQueryInterface
0x18004c723  test    eax, eax
0x18004c725  jz      short loc_18004C743
0x18004c727  mov     rcx, [rbp+5Fh]; this
0x18004c72b  mov     r9d, eax; char *
0x18004c72e  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004c735  mov     edx, 1BDh; void *
0x18004c73a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004c73f  mov     ebx, eax
0x18004c741  jmp     short loc_18004C798
0x18004c743  mov     r9d, [rbp+57h+arg_8]
0x18004c747  mov     r8, [rbp+57h+arg_18]
0x18004c74b  xorps   xmm0, xmm0
0x18004c74e  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x18004c753  mov     rcx, [rbx+28h]
0x18004c757  test    rcx, rcx
0x18004c75a  jz      short loc_18004C76C
0x18004c75c  mov     rax, [rbx+20h]
0x18004c760  mov     qword ptr [rbp+57h+var_88], rax
0x18004c764  mov     qword ptr [rbp+57h+var_88+8], rcx
0x18004c768  lock inc dword ptr [rcx+0Ch]
0x18004c76c  lea     rdx, [rbx+8]
0x18004c770  lea     rcx, [rbp+57h+var_88]
0x18004c774  call    ?ProcessMultiSimSlotMappingChange@CWwanTranslator@@SAJV?$weak_ptr@VCWwanTranslator@@@std@@AEBU_GUID@@PEAEI@Z; CWwanTranslator::ProcessMultiSimSlotMappingChange(std::weak_ptr<CWwanTranslator>,_GUID const &,uchar *,uint)
0x18004c779  mov     ebx, eax
0x18004c77b  test    eax, eax
0x18004c77d  jns     short loc_18004C7B4
0x18004c77f  mov     rcx, [rbp+5Fh]; this
0x18004c783  mov     r9d, eax; char *
0x18004c786  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004c78d  mov     edx, 1BFh; void *
0x18004c792  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c797  nop
0x18004c798  mov     rcx, [rbp+57h+arg_18]
0x18004c79c  test    rcx, rcx
0x18004c79f  jz      loc_18004C87D
0x18004c7a5  call    cs:__imp_WwanFreeMemory
0x18004c7ab  mov     [rbp+57h+arg_18], rsi
0x18004c7af  jmp     loc_18004C87D
0x18004c7b4  xorps   xmm0, xmm0
0x18004c7b7  movdqu  xmmword ptr [rbp+57h+var_30], xmm0
0x18004c7bc  mov     [rbp+57h+var_20], rsi
0x18004c7c0  movdqu  xmmword ptr [rbp+57h+var_48], xmm0
0x18004c7c5  mov     [rbp+57h+var_38], rsi
0x18004c7c9  lea     rcx, [rbp+57h+var_30]
0x18004c7cd  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004c7d2  lea     rcx, [rbp+57h+var_48]
0x18004c7d6  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004c7db  mov     rdx, [rbp+57h+var_30+8]
0x18004c7df  mov     rcx, [rbp+57h+var_30]; unsigned __int16 *
0x18004c7e3  sub     rdx, rcx
0x18004c7e6  sar     rdx, 1; unsigned __int64
0x18004c7e9  lea     r8, aExit; "Exit"
0x18004c7f0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004c7f5  mov     rdx, [rbp+57h+var_48+8]
0x18004c7f9  mov     rcx, [rbp+57h+var_48]; unsigned __int16 *
0x18004c7fd  sub     rdx, rcx
0x18004c800  sar     rdx, 1; unsigned __int64
0x18004c803  mov     rax, [rbp+57h+var_30]
0x18004c807  mov     [rsp+0D0h+var_A8], rax
0x18004c80c  mov     [rsp+0D0h+var_B0], 1C1h
0x18004c814  lea     r9, aCcellularsetti_21; "CCellularSettingHelperCommon::_GetMulti"...
0x18004c81b  lea     r8, aSDS; "%S(%d):%s"
0x18004c822  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004c827  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004c82c  mov     ecx, [rax]
0x18004c82e  cmp     ecx, 5
0x18004c831  jbe     short loc_18004C854
0x18004c833  mov     rcx, [rbp+57h+var_48]
0x18004c837  mov     qword ptr [rbp+57h+var_88], rcx
0x18004c83b  lea     rcx, [rbp+57h+var_88]
0x18004c83f  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x18004c844  lea     rdx, byte_180078F1F
0x18004c84b  mov     rcx, rax
0x18004c84e  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004c853  nop
0x18004c854  lea     rcx, [rbp+57h+var_48]
0x18004c858  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004c85d  nop
0x18004c85e  lea     rcx, [rbp+57h+var_30]
0x18004c862  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004c867  nop
0x18004c868  mov     rcx, [rbp+57h+arg_18]
0x18004c86c  test    rcx, rcx
0x18004c86f  jz      short loc_18004C87B
0x18004c871  call    cs:__imp_WwanFreeMemory
0x18004c877  mov     [rbp+57h+arg_18], rsi
0x18004c87b  mov     ebx, esi
0x18004c87d  xor     edx, edx
0x18004c87f  mov     rcx, [rbp+57h+var_90]
0x18004c883  call    cs:__imp_WwanCloseHandle
0x18004c889  mov     eax, ebx
0x18004c88b  mov     rbx, [rsp+0D0h+arg_0]
0x18004c893  add     rsp, 0C0h
0x18004c89a  pop     rdi
0x18004c89b  pop     rsi
0x18004c89c  pop     rbp
0x18004c89d  retn
```
