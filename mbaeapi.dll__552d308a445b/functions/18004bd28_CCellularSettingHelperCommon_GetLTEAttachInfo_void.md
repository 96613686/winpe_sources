# CCellularSettingHelperCommon::_GetLTEAttachInfo(void)

- ea: `0x18004bd28`
- end: `0x18004c013`
- name: `?_GetLTEAttachInfo@CCellularSettingHelperCommon@@IEAAJXZ`
- size: `747`
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
- `0x180036e88`
- `0x18004bd28`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004c000`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004c000`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004bf22`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004bff2`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004bf22`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004bff2`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004be12`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004be12`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004be9a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004be9a`

## string_xrefs

- `0x18004be23`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004beab`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004bf03`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004bda3`: `CCellularSettingHelperCommon::_GetLTEAttachInfo`
- `0x18004bf95`: `CCellularSettingHelperCommon::_GetLTEAttachInfo`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
int __fastcall CCellularSettingHelperCommon::_GetLTEAttachInfo(CCellularSettingHelperCommon *this)
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
  __int64 v19; // [rsp+48h] [rbp-31h] BYREF
  unsigned int v20[4]; // [rsp+50h] [rbp-29h] BYREF
  unsigned __int16 *v21[2]; // [rsp+60h] [rbp-19h] BYREF
  __int64 v22; // [rsp+70h] [rbp-9h]
  unsigned __int16 *v23[2]; // [rsp+78h] [rbp-1h] BYREF
  __int64 v24; // [rsp+88h] [rbp+Fh]
  unsigned __int16 *v25[2]; // [rsp+90h] [rbp+17h] BYREF
  __int64 v26; // [rsp+A0h] [rbp+27h]
  unsigned __int16 *v27[2]; // [rsp+A8h] [rbp+2Fh] BYREF
  __int64 v28; // [rsp+B8h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  unsigned int v30; // [rsp+E8h] [rbp+6Fh] BYREF
  int v31; // [rsp+F0h] [rbp+77h] BYREF
  int v32; // [rsp+F8h] [rbp+7Fh] BYREF

  *(_OWORD *)v21 = 0;
  v22 = 0;
  *(_OWORD *)v23 = 0;
  v24 = 0;
  std::vector<unsigned short>::resize(v21);
  std::vector<unsigned short>::resize(v23);
  StringCchPrintfW(v21[0], v21[1] - v21[0], L"Enter");
  v16 = 993;
  StringCchPrintfW(v23[0], v23[1] - v23[0], L"%S(%d):%s", "CCellularSettingHelperCommon::_GetLTEAttachInfo");
  v2 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    *(unsigned __int16 **)v20 = v23[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)byte_180078A2B,
      v3,
      v4,
      (const unsigned __int16 **)v20);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v23);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v21);
  v19 = 0;
  v31 = 0;
  v5 = WwanOpenHandle(1, 0, &v31, &v19);
  if ( v5 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x3E4,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
             (const char *)v5,
             v16);
  v21[0] = (unsigned __int16 *)&v19;
  LOBYTE(v21[1]) = 1;
  v18 = 0;
  v30 = 0;
  v32 = 0;
  v23[0] = (unsigned __int16 *)&v18;
  LOBYTE(v23[1]) = 1;
  v17 = &v30;
  Interface = WwanQueryInterface(v19, (char *)this + 8, 31);
  if ( Interface )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x3F1,
           (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
           (const char *)Interface,
           (unsigned int)&v30);
  }
  else
  {
    v9 = v30;
    v10 = v18;
    *(_OWORD *)v20 = 0;
    v11 = *((_QWORD *)this + 5);
    if ( v11 )
    {
      *(_QWORD *)v20 = *((_QWORD *)this + 4);
      *(_QWORD *)&v20[2] = v11;
      _InterlockedIncrement((volatile signed __int32 *)(v11 + 12));
    }
    v12 = CWwanTranslator::ProcessLTEAttachInfoChanged(v20, (char *)this + 8, v10, v9);
    v8 = v12;
    if ( v12 >= 0 )
    {
      *(_OWORD *)v27 = 0;
      v28 = 0;
      *(_OWORD *)v25 = 0;
      v26 = 0;
      std::vector<unsigned short>::resize(v27);
      std::vector<unsigned short>::resize(v25);
      StringCchPrintfW(v27[0], v27[1] - v27[0], L"Exit");
      LODWORD(v17) = 1012;
      StringCchPrintfW(
        v25[0],
        v25[1] - v25[0],
        L"%S(%d):%s",
        "CCellularSettingHelperCommon::_GetLTEAttachInfo",
        v17,
        v27[0],
        &v32,
        0);
      v13 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v13 > 5u )
      {
        *(unsigned __int16 **)v20 = v25[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v13,
          (__int64)byte_1800789E5,
          v14,
          v15,
          (const unsigned __int16 **)v20);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v25);
      std::vector<unsigned short>::~vector<unsigned short>((char **)v27);
      if ( v18 )
        WwanFreeMemory(v18);
      v8 = 0;
      goto LABEL_18;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F2,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
      (const char *)(unsigned int)v12,
      (int)&v30);
  }
  if ( v18 )
    WwanFreeMemory(v18);
LABEL_18:
  WwanCloseHandle(v19, 0);
  return v8;
}

```

## disassembly

```asm
0x18004bd28  push    rbp
0x18004bd2a  push    rbx
0x18004bd2b  push    rdi
0x18004bd2c  lea     rbp, [rsp-47h]
0x18004bd31  sub     rsp, 0C0h
0x18004bd38  mov     rbx, rcx
0x18004bd3b  xorps   xmm0, xmm0
0x18004bd3e  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x18004bd43  mov     [rbp+57h+var_60], 0
0x18004bd4b  movdqu  xmmword ptr [rbp+57h+var_58], xmm0
0x18004bd50  mov     [rbp+57h+var_48], 0
0x18004bd58  lea     rcx, [rbp+57h+var_70]
0x18004bd5c  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004bd61  lea     rcx, [rbp+57h+var_58]
0x18004bd65  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004bd6a  mov     rdx, [rbp+57h+var_70+8]
0x18004bd6e  mov     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x18004bd72  sub     rdx, rcx
0x18004bd75  sar     rdx, 1; unsigned __int64
0x18004bd78  lea     r8, aEnter; "Enter"
0x18004bd7f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004bd84  mov     rdx, [rbp+57h+var_58+8]
0x18004bd88  mov     rcx, [rbp+57h+var_58]; unsigned __int16 *
0x18004bd8c  sub     rdx, rcx
0x18004bd8f  sar     rdx, 1; unsigned __int64
0x18004bd92  mov     rax, [rbp+57h+var_70]
0x18004bd96  mov     [rsp+0D0h+var_A8], rax
0x18004bd9b  mov     [rsp+0D0h+var_B0], 3E1h
0x18004bda3  lea     r9, aCcellularsetti_16; "CCellularSettingHelperCommon::_GetLTEAt"...
0x18004bdaa  lea     r8, aSDS; "%S(%d):%s"
0x18004bdb1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004bdb6  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004bdbb  mov     ecx, [rax]
0x18004bdbd  cmp     ecx, 5
0x18004bdc0  jbe     short loc_18004BDE3
0x18004bdc2  mov     rcx, [rbp+57h+var_58]
0x18004bdc6  mov     qword ptr [rbp+57h+var_80], rcx
0x18004bdca  lea     rcx, [rbp+57h+var_80]
0x18004bdce  mov     qword ptr [rsp+0D0h+var_B0], rcx; unsigned int
0x18004bdd3  lea     rdx, byte_180078A2B
0x18004bdda  mov     rcx, rax
0x18004bddd  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004bde2  nop
0x18004bde3  lea     rcx, [rbp+57h+var_58]
0x18004bde7  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004bdec  nop
0x18004bded  lea     rcx, [rbp+57h+var_70]
0x18004bdf1  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004bdf6  mov     [rbp+57h+var_88], 0
0x18004bdfe  mov     [rbp+57h+arg_10], 0
0x18004be05  lea     r9, [rbp+57h+var_88]
0x18004be09  lea     r8, [rbp+57h+arg_10]
0x18004be0d  xor     edx, edx
0x18004be0f  lea     ecx, [rdx+1]
0x18004be12  call    cs:__imp_WwanOpenHandle
0x18004be18  test    eax, eax
0x18004be1a  jz      short loc_18004BE39
0x18004be1c  mov     rcx, [rbp+5Fh]; this
0x18004be20  mov     r9d, eax; char *
0x18004be23  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004be2a  mov     edx, 3E4h; void *
0x18004be2f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004be34  jmp     loc_18004C008
0x18004be39  lea     rax, [rbp+57h+var_88]
0x18004be3d  mov     [rbp+57h+var_70], rax
0x18004be41  mov     byte ptr [rbp+57h+var_70+8], 1
0x18004be45  mov     [rbp+57h+var_90], 0
0x18004be4d  mov     [rbp+57h+arg_8], 0
0x18004be54  mov     [rbp+57h+arg_18], 0
0x18004be5b  lea     rax, [rbp+57h+var_90]
0x18004be5f  mov     [rbp+57h+var_58], rax
0x18004be63  mov     byte ptr [rbp+57h+var_58+8], 1
0x18004be67  mov     [rsp+0D0h+var_98], 0
0x18004be70  lea     rax, [rbp+57h+arg_18]
0x18004be74  mov     [rsp+0D0h+var_A0], rax
0x18004be79  lea     rax, [rbp+57h+var_90]
0x18004be7d  mov     [rsp+0D0h+var_A8], rax
0x18004be82  lea     rax, [rbp+57h+arg_8]
0x18004be86  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18004be8b  xor     r9d, r9d
0x18004be8e  lea     r8d, [r9+1Fh]
0x18004be92  lea     rdx, [rbx+8]
0x18004be96  mov     rcx, [rbp+57h+var_88]
0x18004be9a  call    cs:__imp_WwanQueryInterface
0x18004bea0  test    eax, eax
0x18004bea2  jz      short loc_18004BEC0
0x18004bea4  mov     rcx, [rbp+5Fh]; this
0x18004bea8  mov     r9d, eax; char *
0x18004beab  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004beb2  mov     edx, 3F1h; void *
0x18004beb7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004bebc  mov     ebx, eax
0x18004bebe  jmp     short loc_18004BF15
0x18004bec0  mov     r9d, [rbp+57h+arg_8]
0x18004bec4  mov     r8, [rbp+57h+var_90]
0x18004bec8  xorps   xmm0, xmm0
0x18004becb  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x18004bed0  mov     rcx, [rbx+28h]
0x18004bed4  test    rcx, rcx
0x18004bed7  jz      short loc_18004BEE9
0x18004bed9  mov     rax, [rbx+20h]
0x18004bedd  mov     qword ptr [rbp+57h+var_80], rax
0x18004bee1  mov     qword ptr [rbp+57h+var_80+8], rcx
0x18004bee5  lock inc dword ptr [rcx+0Ch]
0x18004bee9  lea     rdx, [rbx+8]
0x18004beed  lea     rcx, [rbp+57h+var_80]
0x18004bef1  call    ?ProcessLTEAttachInfoChanged@CWwanTranslator@@SAJV?$weak_ptr@VCWwanTranslator@@@std@@AEBU_GUID@@PEAEI@Z; CWwanTranslator::ProcessLTEAttachInfoChanged(std::weak_ptr<CWwanTranslator>,_GUID const &,uchar *,uint)
0x18004bef6  mov     ebx, eax
0x18004bef8  test    eax, eax
0x18004befa  jns     short loc_18004BF2D
0x18004befc  mov     rcx, [rbp+5Fh]; this
0x18004bf00  mov     r9d, eax; char *
0x18004bf03  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004bf0a  mov     edx, 3F2h; void *
0x18004bf0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bf14  nop
0x18004bf15  mov     rcx, [rbp+57h+var_90]
0x18004bf19  test    rcx, rcx
0x18004bf1c  jz      loc_18004BFFA
0x18004bf22  call    cs:__imp_WwanFreeMemory
0x18004bf28  jmp     loc_18004BFFA
0x18004bf2d  xorps   xmm0, xmm0
0x18004bf30  movdqu  xmmword ptr [rbp+57h+var_28], xmm0
0x18004bf35  mov     [rbp+57h+var_18], 0
0x18004bf3d  movdqu  xmmword ptr [rbp+57h+var_40], xmm0
0x18004bf42  mov     [rbp+57h+var_30], 0
0x18004bf4a  lea     rcx, [rbp+57h+var_28]
0x18004bf4e  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004bf53  lea     rcx, [rbp+57h+var_40]
0x18004bf57  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004bf5c  mov     rdx, [rbp+57h+var_28+8]
0x18004bf60  mov     rcx, [rbp+57h+var_28]; unsigned __int16 *
0x18004bf64  sub     rdx, rcx
0x18004bf67  sar     rdx, 1; unsigned __int64
0x18004bf6a  lea     r8, aExit; "Exit"
0x18004bf71  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004bf76  mov     rdx, [rbp+57h+var_40+8]
0x18004bf7a  mov     rcx, [rbp+57h+var_40]; unsigned __int16 *
0x18004bf7e  sub     rdx, rcx
0x18004bf81  sar     rdx, 1; unsigned __int64
0x18004bf84  mov     rax, [rbp+57h+var_28]
0x18004bf88  mov     [rsp+0D0h+var_A8], rax
0x18004bf8d  mov     [rsp+0D0h+var_B0], 3F4h
0x18004bf95  lea     r9, aCcellularsetti_16; "CCellularSettingHelperCommon::_GetLTEAt"...
0x18004bf9c  lea     r8, aSDS; "%S(%d):%s"
0x18004bfa3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004bfa8  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004bfad  mov     ecx, [rax]
0x18004bfaf  cmp     ecx, 5
0x18004bfb2  jbe     short loc_18004BFD5
0x18004bfb4  mov     rcx, [rbp+57h+var_40]
0x18004bfb8  mov     qword ptr [rbp+57h+var_80], rcx
0x18004bfbc  lea     rcx, [rbp+57h+var_80]
0x18004bfc0  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x18004bfc5  lea     rdx, byte_1800789E5
0x18004bfcc  mov     rcx, rax
0x18004bfcf  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004bfd4  nop
0x18004bfd5  lea     rcx, [rbp+57h+var_40]
0x18004bfd9  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004bfde  nop
0x18004bfdf  lea     rcx, [rbp+57h+var_28]
0x18004bfe3  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004bfe8  nop
0x18004bfe9  mov     rcx, [rbp+57h+var_90]
0x18004bfed  test    rcx, rcx
0x18004bff0  jz      short loc_18004BFF8
0x18004bff2  call    cs:__imp_WwanFreeMemory
0x18004bff8  xor     ebx, ebx
0x18004bffa  xor     edx, edx
0x18004bffc  mov     rcx, [rbp+57h+var_88]
0x18004c000  call    cs:__imp_WwanCloseHandle
0x18004c006  mov     eax, ebx
0x18004c008  add     rsp, 0C0h
0x18004c00f  pop     rdi
0x18004c010  pop     rbx
0x18004c011  pop     rbp
0x18004c012  retn
```
