# CCellularSettingHelperCommon::GetInternetDataEnabled(void)

- ea: `0x180046fc0`
- end: `0x180047277`
- name: `?GetInternetDataEnabled@CCellularSettingHelperCommon@@UEAAJXZ`
- size: `695`
- prototype: `__int64 __fastcall(CCellularSettingHelperCommon *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000178c`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x18001dd10`
- `0x180036648`
- `0x180046fc0`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004725c`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004725c`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004717e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004724a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004717e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004724a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004709e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004709e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x1800470f7`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x1800470f7`

## string_xrefs

- `0x1800470ac`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x180047105`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004715d`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004701e`: `CCellularSettingHelperCommon::GetInternetDataEnabled`
- `0x1800471d5`: `CCellularSettingHelperCommon::GetInternetDataEnabled`

## pseudocode

```c
int __fastcall CCellularSettingHelperCommon::GetInternetDataEnabled(CCellularSettingHelperCommon *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  unsigned int v5; // eax
  unsigned int Interface; // eax
  int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // r9
  __int64 v11; // r8
  int v12; // eax
  const struct _tlgProvider_t *v13; // rax
  __int64 v14; // r8
  __int64 v15; // r9
  unsigned int v16; // [rsp+20h] [rbp-29h]
  unsigned int *v17; // [rsp+20h] [rbp-29h]
  __int64 v18; // [rsp+40h] [rbp-9h] BYREF
  unsigned int v19[4]; // [rsp+48h] [rbp-1h] BYREF
  unsigned __int16 *v20[2]; // [rsp+58h] [rbp+Fh] BYREF
  __int64 v21; // [rsp+68h] [rbp+1Fh]
  unsigned __int16 *v22[2]; // [rsp+70h] [rbp+27h] BYREF
  __int64 v23; // [rsp+80h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]
  unsigned int v25; // [rsp+B8h] [rbp+6Fh] BYREF
  int v26; // [rsp+C0h] [rbp+77h] BYREF
  __int64 v27; // [rsp+C8h] [rbp+7Fh]

  *(_OWORD *)v22 = 0;
  v23 = 0;
  *(_OWORD *)v20 = 0;
  v21 = 0;
  std::vector<unsigned short>::resize(v22);
  std::vector<unsigned short>::resize(v20);
  StringCchPrintfW(v22[0], v22[1] - v22[0], L"Enter");
  v16 = 129;
  StringCchPrintfW(v20[0], v20[1] - v20[0], L"%S(%d):%s", "CCellularSettingHelperCommon::GetInternetDataEnabled");
  v2 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    *(unsigned __int16 **)v19 = v20[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)&dword_18007927C,
      v3,
      v4,
      (const unsigned __int16 **)v19);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v20);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v22);
  v18 = 0;
  v26 = 0;
  v5 = WwanOpenHandle(1, 0, &v26, &v18);
  if ( v5 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x83,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
             (const char *)v5,
             v16);
  v25 = 0;
  v27 = 0;
  v17 = &v25;
  Interface = WwanQueryInterface(v18, (char *)this + 8, 15);
  if ( Interface )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x91,
           (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
           (const char *)Interface,
           (unsigned int)&v25);
  }
  else
  {
    v9 = *((_QWORD *)this + 5);
    v10 = v25;
    v11 = v27;
    *(_OWORD *)v19 = 0;
    if ( v9 )
    {
      *(_QWORD *)v19 = *((_QWORD *)this + 4);
      *(_QWORD *)&v19[2] = v9;
      _InterlockedIncrement((volatile signed __int32 *)(v9 + 12));
    }
    v12 = CWwanTranslator::ProcessDataEnablementChange(v19, (char *)this + 8, v11, v10);
    v8 = v12;
    if ( v12 >= 0 )
    {
      v21 = 0;
      v23 = 0;
      *(_OWORD *)v20 = 0;
      *(_OWORD *)v22 = 0;
      std::vector<unsigned short>::resize(v20);
      std::vector<unsigned short>::resize(v22);
      StringCchPrintfW(v20[0], v20[1] - v20[0], L"Exit");
      LODWORD(v17) = 149;
      StringCchPrintfW(
        v22[0],
        v22[1] - v22[0],
        L"%S(%d):%s",
        "CCellularSettingHelperCommon::GetInternetDataEnabled",
        v17,
        v20[0],
        0,
        0);
      v13 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v13 > 5u )
      {
        *(unsigned __int16 **)v19 = v22[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v13,
          (__int64)&byte_18007929F,
          v14,
          v15,
          (const unsigned __int16 **)v19);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v22);
      std::vector<unsigned short>::~vector<unsigned short>((char **)v20);
      if ( v27 )
      {
        WwanFreeMemory(v27);
        v27 = 0;
      }
      v8 = 0;
      goto LABEL_18;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x93,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
      (const char *)(unsigned int)v12,
      (int)&v25);
  }
  if ( v27 )
  {
    WwanFreeMemory(v27);
    v27 = 0;
  }
LABEL_18:
  WwanCloseHandle(v18, 0);
  return v8;
}

```

## disassembly

```asm
0x180046fc0  mov     [rsp-8+arg_0], rbx
0x180046fc5  push    rbp
0x180046fc6  push    rsi
0x180046fc7  push    rdi
0x180046fc8  lea     rbp, [rsp-47h]
0x180046fcd  sub     rsp, 90h
0x180046fd4  xorps   xmm0, xmm0
0x180046fd7  mov     rbx, rcx
0x180046fda  xor     esi, esi
0x180046fdc  lea     rcx, [rbp+57h+var_30]
0x180046fe0  movdqu  xmmword ptr [rbp+57h+var_30], xmm0
0x180046fe5  mov     [rbp+57h+var_20], rsi
0x180046fe9  movdqu  xmmword ptr [rbp+57h+var_48], xmm0
0x180046fee  mov     [rbp+57h+var_38], rsi
0x180046ff2  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180046ff7  lea     rcx, [rbp+57h+var_48]
0x180046ffb  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180047000  mov     rdx, [rbp+57h+var_30+8]
0x180047004  lea     r8, aEnter; "Enter"
0x18004700b  mov     rcx, [rbp+57h+var_30]; unsigned __int16 *
0x18004700f  sub     rdx, rcx
0x180047012  sar     rdx, 1; unsigned __int64
0x180047015  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004701a  mov     rdx, [rbp+57h+var_48+8]
0x18004701e  lea     r9, aCcellularsetti_19; "CCellularSettingHelperCommon::GetIntern"...
0x180047025  mov     rcx, [rbp+57h+var_48]; unsigned __int16 *
0x180047029  lea     r8, aSDS; "%S(%d):%s"
0x180047030  mov     rax, [rbp+57h+var_30]
0x180047034  sub     rdx, rcx
0x180047037  mov     [rsp+0A0h+var_78], rax
0x18004703c  sar     rdx, 1; unsigned __int64
0x18004703f  mov     [rsp+0A0h+var_80], 81h
0x180047047  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004704c  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180047051  mov     ecx, [rax]
0x180047053  cmp     ecx, 5
0x180047056  jbe     short loc_180047078
0x180047058  mov     rcx, [rbp+57h+var_48]
0x18004705c  lea     rdx, dword_18007927C
0x180047063  mov     qword ptr [rbp+57h+var_58], rcx
0x180047067  lea     rcx, [rbp+57h+var_58]
0x18004706b  mov     qword ptr [rsp+0A0h+var_80], rcx; unsigned int
0x180047070  mov     rcx, rax
0x180047073  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180047078  lea     rcx, [rbp+57h+var_48]
0x18004707c  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180047081  lea     rcx, [rbp+57h+var_30]
0x180047085  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004708a  xor     edx, edx
0x18004708c  mov     [rbp+57h+var_60], rsi
0x180047090  lea     r9, [rbp+57h+var_60]
0x180047094  mov     [rbp+57h+arg_10], esi
0x180047097  lea     r8, [rbp+57h+arg_10]
0x18004709b  lea     ecx, [rdx+1]
0x18004709e  call    cs:__imp_WwanOpenHandle
0x1800470a4  test    eax, eax
0x1800470a6  jz      short loc_1800470C5
0x1800470a8  mov     rcx, [rbp+5Fh]; this
0x1800470ac  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x1800470b3  mov     r9d, eax; char *
0x1800470b6  mov     edx, 83h; void *
0x1800470bb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800470c0  jmp     loc_180047264
0x1800470c5  mov     rcx, [rbp+57h+var_60]
0x1800470c9  lea     rax, [rbp+57h+arg_18]
0x1800470cd  mov     [rsp+0A0h+var_68], rsi
0x1800470d2  lea     rdx, [rbx+8]
0x1800470d6  xor     r9d, r9d
0x1800470d9  mov     [rsp+0A0h+var_70], rsi
0x1800470de  mov     [rsp+0A0h+var_78], rax
0x1800470e3  lea     rax, [rbp+57h+arg_8]
0x1800470e7  mov     [rbp+57h+arg_8], esi
0x1800470ea  mov     [rbp+57h+arg_18], rsi
0x1800470ee  lea     r8d, [r9+0Fh]
0x1800470f2  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x1800470f7  call    cs:__imp_WwanQueryInterface
0x1800470fd  test    eax, eax
0x1800470ff  jz      short loc_18004711D
0x180047101  mov     rcx, [rbp+5Fh]; this
0x180047105  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004710c  mov     r9d, eax; char *
0x18004710f  mov     edx, 91h; void *
0x180047114  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180047119  mov     ebx, eax
0x18004711b  jmp     short loc_180047171
0x18004711d  mov     rcx, [rbx+28h]
0x180047121  xorps   xmm0, xmm0
0x180047124  mov     r9d, [rbp+57h+arg_8]
0x180047128  mov     r8, [rbp+57h+arg_18]
0x18004712c  movdqu  xmmword ptr [rbp+57h+var_58], xmm0
0x180047131  test    rcx, rcx
0x180047134  jz      short loc_180047146
0x180047136  mov     rax, [rbx+20h]
0x18004713a  mov     qword ptr [rbp+57h+var_58], rax
0x18004713e  mov     qword ptr [rbp+57h+var_58+8], rcx
0x180047142  lock inc dword ptr [rcx+0Ch]
0x180047146  lea     rdx, [rbx+8]
0x18004714a  lea     rcx, [rbp+57h+var_58]
0x18004714e  call    ?ProcessDataEnablementChange@CWwanTranslator@@SAJV?$weak_ptr@VCWwanTranslator@@@std@@AEBU_GUID@@PEAEI@Z; CWwanTranslator::ProcessDataEnablementChange(std::weak_ptr<CWwanTranslator>,_GUID const &,uchar *,uint)
0x180047153  mov     ebx, eax
0x180047155  test    eax, eax
0x180047157  jns     short loc_18004718D
0x180047159  mov     rcx, [rbp+5Fh]; this
0x18004715d  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180047164  mov     r9d, eax; char *
0x180047167  mov     edx, 93h; void *
0x18004716c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047171  mov     rcx, [rbp+57h+arg_18]
0x180047175  test    rcx, rcx
0x180047178  jz      loc_180047256
0x18004717e  call    cs:__imp_WwanFreeMemory
0x180047184  mov     [rbp+57h+arg_18], rsi
0x180047188  jmp     loc_180047256
0x18004718d  xorps   xmm0, xmm0
0x180047190  mov     [rbp+57h+var_38], rsi
0x180047194  xorps   xmm1, xmm1
0x180047197  mov     [rbp+57h+var_20], rsi
0x18004719b  lea     rcx, [rbp+57h+var_48]
0x18004719f  movdqu  xmmword ptr [rbp+57h+var_48], xmm0
0x1800471a4  movdqu  xmmword ptr [rbp+57h+var_30], xmm1
0x1800471a9  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800471ae  lea     rcx, [rbp+57h+var_30]
0x1800471b2  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800471b7  mov     rdx, [rbp+57h+var_48+8]
0x1800471bb  lea     r8, aExit; "Exit"
0x1800471c2  mov     rcx, [rbp+57h+var_48]; unsigned __int16 *
0x1800471c6  sub     rdx, rcx
0x1800471c9  sar     rdx, 1; unsigned __int64
0x1800471cc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800471d1  mov     rdx, [rbp+57h+var_30+8]
0x1800471d5  lea     r9, aCcellularsetti_19; "CCellularSettingHelperCommon::GetIntern"...
0x1800471dc  mov     rcx, [rbp+57h+var_30]; unsigned __int16 *
0x1800471e0  lea     r8, aSDS; "%S(%d):%s"
0x1800471e7  mov     rax, [rbp+57h+var_48]
0x1800471eb  sub     rdx, rcx
0x1800471ee  mov     [rsp+0A0h+var_78], rax
0x1800471f3  sar     rdx, 1; unsigned __int64
0x1800471f6  mov     [rsp+0A0h+var_80], 95h
0x1800471fe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180047203  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180047208  mov     ecx, [rax]
0x18004720a  cmp     ecx, 5
0x18004720d  jbe     short loc_18004722F
0x18004720f  mov     rcx, [rbp+57h+var_30]
0x180047213  lea     rdx, byte_18007929F
0x18004721a  mov     qword ptr [rbp+57h+var_58], rcx
0x18004721e  lea     rcx, [rbp+57h+var_58]
0x180047222  mov     qword ptr [rsp+0A0h+var_80], rcx
0x180047227  mov     rcx, rax
0x18004722a  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004722f  lea     rcx, [rbp+57h+var_30]
0x180047233  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180047238  lea     rcx, [rbp+57h+var_48]
0x18004723c  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180047241  mov     rcx, [rbp+57h+arg_18]
0x180047245  test    rcx, rcx
0x180047248  jz      short loc_180047254
0x18004724a  call    cs:__imp_WwanFreeMemory
0x180047250  mov     [rbp+57h+arg_18], rsi
0x180047254  mov     ebx, esi
0x180047256  mov     rcx, [rbp+57h+var_60]
0x18004725a  xor     edx, edx
0x18004725c  call    cs:__imp_WwanCloseHandle
0x180047262  mov     eax, ebx
0x180047264  mov     rbx, [rsp+0A0h+arg_0]
0x18004726c  add     rsp, 90h
0x180047273  pop     rdi
0x180047274  pop     rsi
0x180047275  pop     rbp
0x180047276  retn
```
