# CCellularSettingHelperCommon::_GetDisallowAutoConnect(void)

- ea: `0x18004b6ec`
- end: `0x18004b9be`
- name: `?_GetDisallowAutoConnect@CCellularSettingHelperCommon@@IEAAJXZ`
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
- `0x180036858`
- `0x18004b6ec`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004b9a3`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004b9a3`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004b8c5`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004b991`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004b8c5`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004b991`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004b7cc`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004b7cc`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004b83d`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004b83d`

## string_xrefs

- `0x18004b7dd`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004b84e`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004b8a6`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004b765`: `CCellularSettingHelperCommon::_GetDisallowAutoConnect`
- `0x18004b934`: `CCellularSettingHelperCommon::_GetDisallowAutoConnect`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
int __fastcall CCellularSettingHelperCommon::_GetDisallowAutoConnect(CCellularSettingHelperCommon *this)
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
  v16 = 173;
  StringCchPrintfW(v22[0], v22[1] - v22[0], L"%S(%d):%s", "CCellularSettingHelperCommon::_GetDisallowAutoConnect");
  v2 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    *(unsigned __int16 **)v19 = v22[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)byte_180079213,
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
             (void *)0xAF,
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
  Interface = WwanQueryInterface(v18, (char *)this + 8, 39);
  if ( Interface )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xBD,
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
    v12 = CWwanTranslator::ProcessDisallowAutoConnectChange(v19, (char *)this + 8, v10, v9);
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
      LODWORD(v17) = 193;
      StringCchPrintfW(
        v24[0],
        v24[1] - v24[0],
        L"%S(%d):%s",
        "CCellularSettingHelperCommon::_GetDisallowAutoConnect",
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
          (__int64)byte_1800791CD,
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
      (void *)0xBF,
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
0x18004b6ec  mov     [rsp-8+arg_0], rbx
0x18004b6f1  push    rbp
0x18004b6f2  push    rsi
0x18004b6f3  push    rdi
0x18004b6f4  lea     rbp, [rsp-47h]
0x18004b6f9  sub     rsp, 0C0h
0x18004b700  mov     rbx, rcx
0x18004b703  xorps   xmm0, xmm0
0x18004b706  movdqu  xmmword ptr [rbp+57h+var_78], xmm0
0x18004b70b  xor     esi, esi
0x18004b70d  mov     [rbp+57h+var_68], rsi
0x18004b711  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x18004b716  mov     [rbp+57h+var_50], rsi
0x18004b71a  lea     rcx, [rbp+57h+var_78]
0x18004b71e  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004b723  lea     rcx, [rbp+57h+var_60]
0x18004b727  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004b72c  mov     rdx, [rbp+57h+var_78+8]
0x18004b730  mov     rcx, [rbp+57h+var_78]; unsigned __int16 *
0x18004b734  sub     rdx, rcx
0x18004b737  sar     rdx, 1; unsigned __int64
0x18004b73a  lea     r8, aEnter; "Enter"
0x18004b741  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004b746  mov     rdx, [rbp+57h+var_60+8]
0x18004b74a  mov     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x18004b74e  sub     rdx, rcx
0x18004b751  sar     rdx, 1; unsigned __int64
0x18004b754  mov     rax, [rbp+57h+var_78]
0x18004b758  mov     [rsp+0D0h+var_A8], rax
0x18004b75d  mov     [rsp+0D0h+var_B0], 0ADh
0x18004b765  lea     r9, aCcellularsetti_38; "CCellularSettingHelperCommon::_GetDisal"...
0x18004b76c  lea     r8, aSDS; "%S(%d):%s"
0x18004b773  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004b778  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004b77d  mov     ecx, [rax]
0x18004b77f  cmp     ecx, 5
0x18004b782  jbe     short loc_18004B7A5
0x18004b784  mov     rcx, [rbp+57h+var_60]
0x18004b788  mov     qword ptr [rbp+57h+var_88], rcx
0x18004b78c  lea     rcx, [rbp+57h+var_88]
0x18004b790  mov     qword ptr [rsp+0D0h+var_B0], rcx; unsigned int
0x18004b795  lea     rdx, byte_180079213
0x18004b79c  mov     rcx, rax
0x18004b79f  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004b7a4  nop
0x18004b7a5  lea     rcx, [rbp+57h+var_60]
0x18004b7a9  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004b7ae  nop
0x18004b7af  lea     rcx, [rbp+57h+var_78]
0x18004b7b3  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004b7b8  mov     [rbp+57h+var_90], rsi
0x18004b7bc  mov     [rbp+57h+arg_10], esi
0x18004b7bf  lea     r9, [rbp+57h+var_90]
0x18004b7c3  lea     r8, [rbp+57h+arg_10]
0x18004b7c7  xor     edx, edx
0x18004b7c9  lea     ecx, [rdx+1]
0x18004b7cc  call    cs:__imp_WwanOpenHandle
0x18004b7d2  test    eax, eax
0x18004b7d4  jz      short loc_18004B7F3
0x18004b7d6  mov     rcx, [rbp+5Fh]; this
0x18004b7da  mov     r9d, eax; char *
0x18004b7dd  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004b7e4  mov     edx, 0AFh; void *
0x18004b7e9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004b7ee  jmp     loc_18004B9AB
0x18004b7f3  lea     rax, [rbp+57h+var_90]
0x18004b7f7  mov     [rbp+57h+var_78], rax
0x18004b7fb  mov     byte ptr [rbp+57h+var_78+8], 1
0x18004b7ff  mov     [rbp+57h+arg_8], esi
0x18004b802  mov     [rbp+57h+arg_18], rsi
0x18004b806  lea     rax, [rbp+57h+arg_18]
0x18004b80a  mov     [rbp+57h+var_60], rax
0x18004b80e  mov     byte ptr [rbp+57h+var_60+8], 1
0x18004b812  mov     [rsp+0D0h+var_98], rsi
0x18004b817  mov     [rsp+0D0h+var_A0], rsi
0x18004b81c  lea     rax, [rbp+57h+arg_18]
0x18004b820  mov     [rsp+0D0h+var_A8], rax
0x18004b825  lea     rax, [rbp+57h+arg_8]
0x18004b829  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18004b82e  xor     r9d, r9d
0x18004b831  lea     r8d, [r9+27h]
0x18004b835  lea     rdx, [rbx+8]
0x18004b839  mov     rcx, [rbp+57h+var_90]
0x18004b83d  call    cs:__imp_WwanQueryInterface
0x18004b843  test    eax, eax
0x18004b845  jz      short loc_18004B863
0x18004b847  mov     rcx, [rbp+5Fh]; this
0x18004b84b  mov     r9d, eax; char *
0x18004b84e  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004b855  mov     edx, 0BDh; void *
0x18004b85a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004b85f  mov     ebx, eax
0x18004b861  jmp     short loc_18004B8B8
0x18004b863  mov     r9d, [rbp+57h+arg_8]
0x18004b867  mov     r8, [rbp+57h+arg_18]
0x18004b86b  xorps   xmm0, xmm0
0x18004b86e  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x18004b873  mov     rcx, [rbx+28h]
0x18004b877  test    rcx, rcx
0x18004b87a  jz      short loc_18004B88C
0x18004b87c  mov     rax, [rbx+20h]
0x18004b880  mov     qword ptr [rbp+57h+var_88], rax
0x18004b884  mov     qword ptr [rbp+57h+var_88+8], rcx
0x18004b888  lock inc dword ptr [rcx+0Ch]
0x18004b88c  lea     rdx, [rbx+8]
0x18004b890  lea     rcx, [rbp+57h+var_88]
0x18004b894  call    ?ProcessDisallowAutoConnectChange@CWwanTranslator@@SAJV?$weak_ptr@VCWwanTranslator@@@std@@AEBU_GUID@@PEAEI@Z; CWwanTranslator::ProcessDisallowAutoConnectChange(std::weak_ptr<CWwanTranslator>,_GUID const &,uchar *,uint)
0x18004b899  mov     ebx, eax
0x18004b89b  test    eax, eax
0x18004b89d  jns     short loc_18004B8D4
0x18004b89f  mov     rcx, [rbp+5Fh]; this
0x18004b8a3  mov     r9d, eax; char *
0x18004b8a6  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004b8ad  mov     edx, 0BFh; void *
0x18004b8b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b8b7  nop
0x18004b8b8  mov     rcx, [rbp+57h+arg_18]
0x18004b8bc  test    rcx, rcx
0x18004b8bf  jz      loc_18004B99D
0x18004b8c5  call    cs:__imp_WwanFreeMemory
0x18004b8cb  mov     [rbp+57h+arg_18], rsi
0x18004b8cf  jmp     loc_18004B99D
0x18004b8d4  xorps   xmm0, xmm0
0x18004b8d7  movdqu  xmmword ptr [rbp+57h+var_30], xmm0
0x18004b8dc  mov     [rbp+57h+var_20], rsi
0x18004b8e0  movdqu  xmmword ptr [rbp+57h+var_48], xmm0
0x18004b8e5  mov     [rbp+57h+var_38], rsi
0x18004b8e9  lea     rcx, [rbp+57h+var_30]
0x18004b8ed  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004b8f2  lea     rcx, [rbp+57h+var_48]
0x18004b8f6  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004b8fb  mov     rdx, [rbp+57h+var_30+8]
0x18004b8ff  mov     rcx, [rbp+57h+var_30]; unsigned __int16 *
0x18004b903  sub     rdx, rcx
0x18004b906  sar     rdx, 1; unsigned __int64
0x18004b909  lea     r8, aExit; "Exit"
0x18004b910  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004b915  mov     rdx, [rbp+57h+var_48+8]
0x18004b919  mov     rcx, [rbp+57h+var_48]; unsigned __int16 *
0x18004b91d  sub     rdx, rcx
0x18004b920  sar     rdx, 1; unsigned __int64
0x18004b923  mov     rax, [rbp+57h+var_30]
0x18004b927  mov     [rsp+0D0h+var_A8], rax
0x18004b92c  mov     [rsp+0D0h+var_B0], 0C1h
0x18004b934  lea     r9, aCcellularsetti_38; "CCellularSettingHelperCommon::_GetDisal"...
0x18004b93b  lea     r8, aSDS; "%S(%d):%s"
0x18004b942  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004b947  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004b94c  mov     ecx, [rax]
0x18004b94e  cmp     ecx, 5
0x18004b951  jbe     short loc_18004B974
0x18004b953  mov     rcx, [rbp+57h+var_48]
0x18004b957  mov     qword ptr [rbp+57h+var_88], rcx
0x18004b95b  lea     rcx, [rbp+57h+var_88]
0x18004b95f  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x18004b964  lea     rdx, byte_1800791CD
0x18004b96b  mov     rcx, rax
0x18004b96e  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004b973  nop
0x18004b974  lea     rcx, [rbp+57h+var_48]
0x18004b978  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004b97d  nop
0x18004b97e  lea     rcx, [rbp+57h+var_30]
0x18004b982  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004b987  nop
0x18004b988  mov     rcx, [rbp+57h+arg_18]
0x18004b98c  test    rcx, rcx
0x18004b98f  jz      short loc_18004B99B
0x18004b991  call    cs:__imp_WwanFreeMemory
0x18004b997  mov     [rbp+57h+arg_18], rsi
0x18004b99b  mov     ebx, esi
0x18004b99d  xor     edx, edx
0x18004b99f  mov     rcx, [rbp+57h+var_90]
0x18004b9a3  call    cs:__imp_WwanCloseHandle
0x18004b9a9  mov     eax, ebx
0x18004b9ab  mov     rbx, [rsp+0D0h+arg_0]
0x18004b9b3  add     rsp, 0C0h
0x18004b9ba  pop     rdi
0x18004b9bb  pop     rsi
0x18004b9bc  pop     rbp
0x18004b9bd  retn
```
