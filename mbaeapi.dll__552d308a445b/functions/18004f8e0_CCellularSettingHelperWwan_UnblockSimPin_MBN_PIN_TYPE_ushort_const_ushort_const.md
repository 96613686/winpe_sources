# CCellularSettingHelperWwan::UnblockSimPin(MBN_PIN_TYPE,ushort const *,ushort const *)

- ea: `0x18004f8e0`
- end: `0x18004fd8f`
- name: `?UnblockSimPin@CCellularSettingHelperWwan@@UEAAJW4MBN_PIN_TYPE@@PEBG1@Z`
- size: `1199`
- prototype: `__int64 __fastcall(CCellularSettingHelperWwan *__hidden this, enum MBN_PIN_TYPE, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x18000178c`
- `0x1800024e0`
- `0x180002efc`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x18001adf8`
- `0x18001dd10`
- `0x180039a8c`
- `0x18004ce4c`
- `0x18004e808`
- `0x18004f8e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004fb78`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004fb8a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004fb78`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004fb8a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004fb32`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004fbeb`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004fc6b`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004fd53`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004fb32`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004fbeb`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004fc6b`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004fd53`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004fab8`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004fab8`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetInterface` at `0x18004fc40`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetInterface` at `0x18004fc40`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCellularSettingHelperWwan::UnblockSimPin(
        CCellularSettingHelperWwan *this,
        enum MBN_PIN_TYPE a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rcx
  unsigned int v13; // eax
  unsigned int v14; // ebx
  int WwanPukFromMbnPin; // eax
  __int64 v16; // rcx
  int v17; // eax
  unsigned int v18; // eax
  const struct _tlgProvider_t *v19; // rax
  __int64 v20; // r8
  __int64 v21; // r9
  int v22; // [rsp+20h] [rbp-E0h]
  unsigned int *v23; // [rsp+20h] [rbp-E0h]
  char *v24; // [rsp+28h] [rbp-D8h]
  int *v25; // [rsp+40h] [rbp-C0h] BYREF
  MBN_PIN_TYPE *v26; // [rsp+48h] [rbp-B8h]
  char v27; // [rsp+50h] [rbp-B0h]
  __int64 v28; // [rsp+58h] [rbp-A8h] BYREF
  MBN_PIN_TYPE v29; // [rsp+60h] [rbp-A0h] BYREF
  int v30; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v31[4]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v32[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v33; // [rsp+90h] [rbp-70h]
  char *v34[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v35; // [rsp+A8h] [rbp-58h]
  _DWORD v36[4]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v37[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v38[34]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v39[38]; // [rsp+EAh] [rbp-16h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v29 = a2;
  *(_OWORD *)v34 = 0;
  v35 = 0;
  *(_OWORD *)v32 = 0;
  v33 = 0;
  std::vector<unsigned short>::resize(v34);
  std::vector<unsigned short>::resize(v32);
  StringCchPrintfW((unsigned __int16 *)v34[0], (v34[1] - v34[0]) >> 1, L"Enter");
  v24 = v34[0];
  v22 = 310;
  StringCchPrintfW(v32[0], v32[1] - v32[0], L"%S(%d):%s", "CCellularSettingHelperWwan::UnblockSimPin");
  v7 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v7 > 5u )
  {
    *(unsigned __int16 **)v31 = v32[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v7,
      (__int64)&word_180079656,
      v8,
      v9,
      (const unsigned __int16 **)v31);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v32);
  std::vector<unsigned short>::~vector<unsigned short>(v34);
  v30 = 0;
  v25 = &v30;
  v26 = &v29;
  v27 = 1;
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x143,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
      (const char *)0x80070057LL,
      v22);
LABEL_12:
    v27 = 0;
    CCellularSettingHelperWwan::UnblockSimPin_::_2_::_lambda_1_::operator()(&v25);
    return 2147942487LL;
  }
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( a3[v11] );
  if ( v11 > 0x11 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x145,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
      (const char *)0x80070057LL,
      (int)"Current pin is too long.",
      v24);
    goto LABEL_12;
  }
  do
    ++v10;
  while ( a4[v10] );
  if ( v10 > 0x11 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x147,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
      (const char *)0x80070057LL,
      (int)"New pin is too long.",
      v24);
    goto LABEL_12;
  }
  v28 = 0;
  v36[0] = 0;
  v13 = WwanOpenHandle(1, 0, v36, &v28);
  if ( v13 )
  {
    v14 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x14A,
            (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
            (const char *)v13,
            v22);
    v27 = 0;
    CCellularSettingHelperWwan::UnblockSimPin_::_2_::_lambda_1_::operator()(&v25);
    return v14;
  }
  v31[0] = 0;
  WwanPukFromMbnPin = GetWwanPukFromMbnPin(v29, (enum _WWAN_PIN_TYPE *)v31);
  v14 = WwanPukFromMbnPin;
  if ( WwanPukFromMbnPin < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14D,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
      (const char *)(unsigned int)WwanPukFromMbnPin,
      v22);
    WwanCloseHandle(v28, 0);
    v27 = 0;
    CCellularSettingHelperWwan::UnblockSimPin_::_2_::_lambda_1_::operator()(&v25);
    return v14;
  }
  memset_0(v37, 0, 0x50u);
  v37[0] = v31[0];
  v37[1] = 0;
  _o_wcscpy_s(v38, 17, a3);
  _o_wcscpy_s(v39, 17, a4);
  *(_OWORD *)v31 = 0;
  v16 = *((_QWORD *)this + 5);
  if ( v16 )
  {
    *(_QWORD *)v31 = *((_QWORD *)this + 4);
    *(_QWORD *)&v31[2] = v16;
    _InterlockedIncrement((volatile signed __int32 *)(v16 + 12));
  }
  v17 = CWwanTranslator::SetAdapterPinActionRequest(v31, (char *)this + 8, v37);
  v14 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x157,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
      (const char *)(unsigned int)v17,
      v22);
    WwanCloseHandle(v28, 0);
    v27 = 0;
    CCellularSettingHelperWwan::UnblockSimPin_::_2_::_lambda_1_::operator()(&v25);
    return v14;
  }
  v36[1] = 0;
  v23 = v37;
  v18 = WwanSetInterface(v28, (char *)this + 8, 0, 80);
  if ( v18 )
  {
    v14 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x15B,
            (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
            (const char *)v18,
            (unsigned int)v37);
    WwanCloseHandle(v28, 0);
    v27 = 0;
    CCellularSettingHelperWwan::UnblockSimPin_::_2_::_lambda_1_::operator()(&v25);
    return v14;
  }
  v30 = 1;
  *(_OWORD *)v32 = 0;
  v33 = 0;
  *(_OWORD *)v34 = 0;
  v35 = 0;
  std::vector<unsigned short>::resize(v32);
  std::vector<unsigned short>::resize(v34);
  StringCchPrintfW(v32[0], v32[1] - v32[0], L"Exit");
  LODWORD(v23) = 351;
  StringCchPrintfW(
    (unsigned __int16 *)v34[0],
    (v34[1] - v34[0]) >> 1,
    L"%S(%d):%s",
    "CCellularSettingHelperWwan::UnblockSimPin",
    v23,
    v32[0],
    0,
    0,
    v25,
    v26);
  v19 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v19 > 5u )
  {
    *(char **)v31 = v34[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v19,
      (__int64)byte_180079679,
      v20,
      v21,
      (const unsigned __int16 **)v31);
  }
  std::vector<unsigned short>::~vector<unsigned short>(v34);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v32);
  WwanCloseHandle(v28, 0);
  v27 = 0;
  CCellularSettingHelperWwan::UnblockSimPin_::_2_::_lambda_1_::operator()(&v25);
  return 0;
}

```

## disassembly

```asm
0x18004f8e0  push    rbp
0x18004f8e2  push    rbx
0x18004f8e3  push    rsi
0x18004f8e4  push    rdi
0x18004f8e5  push    r14
0x18004f8e7  push    r15
0x18004f8e9  lea     rbp, [rsp-28h]
0x18004f8ee  sub     rsp, 128h
0x18004f8f5  mov     rax, cs:__security_cookie
0x18004f8fc  xor     rax, rsp
0x18004f8ff  mov     [rbp+50h+var_40], rax
0x18004f903  mov     r14, r9
0x18004f906  mov     rdi, r8
0x18004f909  mov     rsi, rcx
0x18004f90c  mov     [rsp+150h+var_F0], edx
0x18004f910  xorps   xmm0, xmm0
0x18004f913  movdqu  xmmword ptr [rbp+50h+var_B8], xmm0
0x18004f918  xor     r15d, r15d
0x18004f91b  mov     [rbp+50h+var_A8], r15
0x18004f91f  movdqu  xmmword ptr [rbp+50h+var_D0], xmm0
0x18004f924  mov     [rbp+50h+var_C0], r15
0x18004f928  lea     rcx, [rbp+50h+var_B8]
0x18004f92c  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004f931  lea     rcx, [rbp+50h+var_D0]
0x18004f935  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004f93a  mov     rdx, [rbp+50h+var_B8+8]
0x18004f93e  mov     rcx, [rbp+50h+var_B8]; unsigned __int16 *
0x18004f942  sub     rdx, rcx
0x18004f945  sar     rdx, 1; unsigned __int64
0x18004f948  lea     r8, aEnter; "Enter"
0x18004f94f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004f954  mov     rdx, [rbp+50h+var_D0+8]
0x18004f958  mov     rcx, [rbp+50h+var_D0]; unsigned __int16 *
0x18004f95c  sub     rdx, rcx
0x18004f95f  sar     rdx, 1; unsigned __int64
0x18004f962  mov     rax, [rbp+50h+var_B8]
0x18004f966  mov     [rsp+150h+var_128], rax; char *
0x18004f96b  mov     [rsp+150h+var_130], 136h
0x18004f973  lea     r9, aCcellularsetti_22; "CCellularSettingHelperWwan::UnblockSimP"...
0x18004f97a  lea     r8, aSDS; "%S(%d):%s"
0x18004f981  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004f986  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004f98b  mov     ecx, [rax]
0x18004f98d  cmp     ecx, 5
0x18004f990  jbe     short loc_18004F9B4
0x18004f992  mov     rcx, [rbp+50h+var_D0]
0x18004f996  mov     qword ptr [rsp+150h+var_E0], rcx
0x18004f99b  lea     rcx, [rsp+150h+var_E0]
0x18004f9a0  mov     qword ptr [rsp+150h+var_130], rcx; int
0x18004f9a5  lea     rdx, word_180079656
0x18004f9ac  mov     rcx, rax
0x18004f9af  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004f9b4  lea     rcx, [rbp+50h+var_D0]
0x18004f9b8  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004f9bd  lea     rcx, [rbp+50h+var_B8]
0x18004f9c1  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004f9c6  mov     [rsp+150h+var_E8], r15d
0x18004f9cb  lea     rax, [rsp+150h+var_E8]
0x18004f9d0  mov     [rsp+150h+var_110], rax
0x18004f9d5  lea     rax, [rsp+150h+var_F0]
0x18004f9da  mov     [rsp+150h+var_108], rax
0x18004f9df  mov     [rsp+150h+var_100], 1
0x18004f9e4  test    rdi, rdi
0x18004f9e7  jnz     short loc_18004FA07
0x18004f9e9  mov     rcx, [rbp+58h]; this
0x18004f9ed  mov     r9d, 80070057h; char *
0x18004f9f3  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004f9fa  mov     edx, 143h; void *
0x18004f9ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fa04  nop
0x18004fa05  jmp     short loc_18004FA80
0x18004fa07  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004fa0b  mov     rcx, rax
0x18004fa0e  inc     rcx
0x18004fa11  cmp     [rdi+rcx*2], r15w
0x18004fa16  jnz     short loc_18004FA0E
0x18004fa18  cmp     rcx, 11h
0x18004fa1c  jbe     short loc_18004FA48
0x18004fa1e  mov     rcx, [rbp+58h]; this
0x18004fa22  lea     rax, aCurrentPinIsTo; "Current pin is too long."
0x18004fa29  mov     qword ptr [rsp+150h+var_130], rax; int
0x18004fa2e  mov     r9d, 80070057h; char *
0x18004fa34  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004fa3b  mov     edx, 145h; void *
0x18004fa40  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004fa45  nop
0x18004fa46  jmp     short loc_18004FA80
0x18004fa48  inc     rax
0x18004fa4b  cmp     [r14+rax*2], r15w
0x18004fa50  jnz     short loc_18004FA48
0x18004fa52  cmp     rax, 11h
0x18004fa56  jbe     short loc_18004FAA1
0x18004fa58  mov     rcx, [rbp+58h]; this
0x18004fa5c  lea     rax, aNewPinIsTooLon; "New pin is too long."
0x18004fa63  mov     qword ptr [rsp+150h+var_130], rax; int
0x18004fa68  mov     r9d, 80070057h; char *
0x18004fa6e  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004fa75  mov     edx, 147h; void *
0x18004fa7a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004fa7f  nop
0x18004fa80  cmp     [rsp+150h+var_100], r15b
0x18004fa85  jz      short loc_18004FA97
0x18004fa87  mov     [rsp+150h+var_100], r15b
0x18004fa8c  lea     rcx, [rsp+150h+var_110]
0x18004fa91  call    _CCellularSettingHelperWwan__UnblockSimPin____2____lambda_1___operator__
0x18004fa96  nop
0x18004fa97  mov     eax, 80070057h
0x18004fa9c  jmp     loc_18004FD73
0x18004faa1  mov     [rsp+150h+var_F8], r15
0x18004faa6  mov     [rbp+50h+var_A0], r15d
0x18004faaa  lea     r9, [rsp+150h+var_F8]
0x18004faaf  lea     r8, [rbp+50h+var_A0]
0x18004fab3  xor     edx, edx
0x18004fab5  lea     ecx, [rdx+1]
0x18004fab8  call    cs:__imp_WwanOpenHandle
0x18004fabe  test    eax, eax
0x18004fac0  jz      short loc_18004FAFA
0x18004fac2  mov     rcx, [rbp+58h]; this
0x18004fac6  mov     r9d, eax; char *
0x18004fac9  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004fad0  mov     edx, 14Ah; void *
0x18004fad5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004fada  mov     ebx, eax
0x18004fadc  cmp     [rsp+150h+var_100], r15b
0x18004fae1  jz      short loc_18004FAF3
0x18004fae3  mov     [rsp+150h+var_100], r15b
0x18004fae8  lea     rcx, [rsp+150h+var_110]
0x18004faed  call    _CCellularSettingHelperWwan__UnblockSimPin____2____lambda_1___operator__
0x18004faf2  nop
0x18004faf3  mov     eax, ebx
0x18004faf5  jmp     loc_18004FD73
0x18004fafa  mov     [rsp+150h+var_E0], r15d
0x18004faff  lea     rdx, [rsp+150h+var_E0]; enum _WWAN_PIN_TYPE *
0x18004fb04  mov     ecx, [rsp+150h+var_F0]; enum MBN_PIN_TYPE
0x18004fb08  call    ?GetWwanPukFromMbnPin@@YAJW4MBN_PIN_TYPE@@AEAW4_WWAN_PIN_TYPE@@@Z; GetWwanPukFromMbnPin(MBN_PIN_TYPE,_WWAN_PIN_TYPE &)
0x18004fb0d  mov     ebx, eax
0x18004fb0f  test    eax, eax
0x18004fb11  jns     short loc_18004FB52
0x18004fb13  mov     rcx, [rbp+58h]; this
0x18004fb17  mov     r9d, eax; char *
0x18004fb1a  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004fb21  mov     edx, 14Dh; void *
0x18004fb26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fb2b  xor     edx, edx
0x18004fb2d  mov     rcx, [rsp+150h+var_F8]
0x18004fb32  call    cs:__imp_WwanCloseHandle
0x18004fb38  nop
0x18004fb39  cmp     [rsp+150h+var_100], r15b
0x18004fb3e  jz      short loc_18004FB50
0x18004fb40  mov     [rsp+150h+var_100], r15b
0x18004fb45  lea     rcx, [rsp+150h+var_110]
0x18004fb4a  call    _CCellularSettingHelperWwan__UnblockSimPin____2____lambda_1___operator__
0x18004fb4f  nop
0x18004fb50  jmp     short loc_18004FAF3
0x18004fb52  xor     edx, edx; Val
0x18004fb54  lea     r8d, [rdx+50h]; Size
0x18004fb58  lea     rcx, [rbp+50h+var_90]; void *
0x18004fb5c  call    memset_0
0x18004fb61  mov     eax, [rsp+150h+var_E0]
0x18004fb65  mov     [rbp+50h+var_90], eax
0x18004fb68  mov     [rbp+50h+var_8C], r15d
0x18004fb6c  mov     r8, rdi
0x18004fb6f  mov     edx, 11h
0x18004fb74  lea     rcx, [rbp+50h+var_88]
0x18004fb78  call    cs:__imp__o_wcscpy_s
0x18004fb7e  mov     r8, r14
0x18004fb81  mov     edx, 11h
0x18004fb86  lea     rcx, [rbp+50h+var_66]
0x18004fb8a  call    cs:__imp__o_wcscpy_s
0x18004fb90  xorps   xmm0, xmm0
0x18004fb93  movdqu  xmmword ptr [rsp+150h+var_E0], xmm0
0x18004fb99  mov     rcx, [rsi+28h]
0x18004fb9d  test    rcx, rcx
0x18004fba0  jz      short loc_18004FBB4
0x18004fba2  mov     rax, [rsi+20h]
0x18004fba6  mov     qword ptr [rsp+150h+var_E0], rax
0x18004fbab  mov     qword ptr [rsp+150h+var_E0+8], rcx
0x18004fbb0  lock inc dword ptr [rcx+0Ch]
0x18004fbb4  lea     r8, [rbp+50h+var_90]
0x18004fbb8  lea     rdx, [rsi+8]
0x18004fbbc  lea     rcx, [rsp+150h+var_E0]
0x18004fbc1  call    ?SetAdapterPinActionRequest@CWwanTranslator@@SAJV?$weak_ptr@VCWwanTranslator@@@std@@AEBU_GUID@@AEAU_WWAN_PIN_ACTION@@@Z; CWwanTranslator::SetAdapterPinActionRequest(std::weak_ptr<CWwanTranslator>,_GUID const &,_WWAN_PIN_ACTION &)
0x18004fbc6  mov     ebx, eax
0x18004fbc8  test    eax, eax
0x18004fbca  jns     short loc_18004FC0E
0x18004fbcc  mov     rcx, [rbp+58h]; this
0x18004fbd0  mov     r9d, eax; char *
0x18004fbd3  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004fbda  mov     edx, 157h; void *
0x18004fbdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fbe4  xor     edx, edx
0x18004fbe6  mov     rcx, [rsp+150h+var_F8]
0x18004fbeb  call    cs:__imp_WwanCloseHandle
0x18004fbf1  nop
0x18004fbf2  cmp     [rsp+150h+var_100], r15b
0x18004fbf7  jz      short loc_18004FC09
0x18004fbf9  mov     [rsp+150h+var_100], r15b
0x18004fbfe  lea     rcx, [rsp+150h+var_110]
0x18004fc03  call    _CCellularSettingHelperWwan__UnblockSimPin____2____lambda_1___operator__
0x18004fc08  nop
0x18004fc09  jmp     loc_18004FAF3
0x18004fc0e  mov     [rbp+50h+var_9C], r15d
0x18004fc12  mov     [rsp+150h+var_118], r15
0x18004fc17  mov     [rsp+150h+var_120], r15
0x18004fc1c  lea     rax, [rbp+50h+var_9C]
0x18004fc20  mov     [rsp+150h+var_128], rax
0x18004fc25  lea     rax, [rbp+50h+var_90]
0x18004fc29  mov     qword ptr [rsp+150h+var_130], rax; unsigned int
0x18004fc2e  mov     r9d, 50h ; 'P'
0x18004fc34  xor     r8d, r8d
0x18004fc37  lea     rdx, [rsi+8]
0x18004fc3b  mov     rcx, [rsp+150h+var_F8]
0x18004fc40  call    cs:__imp_WwanSetInterface
0x18004fc46  test    eax, eax
0x18004fc48  jz      short loc_18004FC8E
0x18004fc4a  mov     rcx, [rbp+58h]; this
0x18004fc4e  mov     r9d, eax; char *
0x18004fc51  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004fc58  mov     edx, 15Bh; void *
0x18004fc5d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004fc62  mov     ebx, eax
0x18004fc64  xor     edx, edx
0x18004fc66  mov     rcx, [rsp+150h+var_F8]
0x18004fc6b  call    cs:__imp_WwanCloseHandle
0x18004fc71  nop
0x18004fc72  cmp     [rsp+150h+var_100], r15b
0x18004fc77  jz      short loc_18004FC89
0x18004fc79  mov     [rsp+150h+var_100], r15b
0x18004fc7e  lea     rcx, [rsp+150h+var_110]
0x18004fc83  call    _CCellularSettingHelperWwan__UnblockSimPin____2____lambda_1___operator__
0x18004fc88  nop
0x18004fc89  jmp     loc_18004FAF3
0x18004fc8e  mov     [rsp+150h+var_E8], 1
0x18004fc96  xorps   xmm0, xmm0
0x18004fc99  movdqu  xmmword ptr [rbp+50h+var_D0], xmm0
0x18004fc9e  mov     [rbp+50h+var_C0], r15
0x18004fca2  xorps   xmm1, xmm1
0x18004fca5  movdqu  xmmword ptr [rbp+50h+var_B8], xmm1
0x18004fcaa  mov     [rbp+50h+var_A8], r15
0x18004fcae  lea     rcx, [rbp+50h+var_D0]
0x18004fcb2  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004fcb7  lea     rcx, [rbp+50h+var_B8]
0x18004fcbb  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004fcc0  mov     rdx, [rbp+50h+var_D0+8]
0x18004fcc4  mov     rcx, [rbp+50h+var_D0]; unsigned __int16 *
0x18004fcc8  sub     rdx, rcx
0x18004fccb  sar     rdx, 1; unsigned __int64
0x18004fcce  lea     r8, aExit; "Exit"
0x18004fcd5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004fcda  mov     rdx, [rbp+50h+var_B8+8]
0x18004fcde  mov     rcx, [rbp+50h+var_B8]; unsigned __int16 *
0x18004fce2  sub     rdx, rcx
0x18004fce5  sar     rdx, 1; unsigned __int64
0x18004fce8  mov     rax, [rbp+50h+var_D0]
0x18004fcec  mov     [rsp+150h+var_128], rax
0x18004fcf1  mov     [rsp+150h+var_130], 15Fh
0x18004fcf9  lea     r9, aCcellularsetti_22; "CCellularSettingHelperWwan::UnblockSimP"...
0x18004fd00  lea     r8, aSDS; "%S(%d):%s"
0x18004fd07  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004fd0c  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004fd11  mov     ecx, [rax]
0x18004fd13  cmp     ecx, 5
0x18004fd16  jbe     short loc_18004FD3A
0x18004fd18  mov     rcx, [rbp+50h+var_B8]
0x18004fd1c  mov     qword ptr [rsp+150h+var_E0], rcx
0x18004fd21  lea     rcx, [rsp+150h+var_E0]
0x18004fd26  mov     qword ptr [rsp+150h+var_130], rcx
0x18004fd2b  lea     rdx, byte_180079679
0x18004fd32  mov     rcx, rax
0x18004fd35  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004fd3a  lea     rcx, [rbp+50h+var_B8]
0x18004fd3e  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004fd43  lea     rcx, [rbp+50h+var_D0]
0x18004fd47  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004fd4c  xor     edx, edx
0x18004fd4e  mov     rcx, [rsp+150h+var_F8]
0x18004fd53  call    cs:__imp_WwanCloseHandle
0x18004fd59  nop
0x18004fd5a  cmp     [rsp+150h+var_100], r15b
0x18004fd5f  jz      short loc_18004FD71
0x18004fd61  mov     [rsp+150h+var_100], r15b
0x18004fd66  lea     rcx, [rsp+150h+var_110]
0x18004fd6b  call    _CCellularSettingHelperWwan__UnblockSimPin____2____lambda_1___operator__
0x18004fd70  nop
0x18004fd71  xor     eax, eax
0x18004fd73  mov     rcx, [rbp+50h+var_40]
0x18004fd77  xor     rcx, rsp; StackCookie
0x18004fd7a  call    __security_check_cookie
0x18004fd7f  add     rsp, 128h
0x18004fd86  pop     r15
0x18004fd88  pop     r14
0x18004fd8a  pop     rdi
0x18004fd8b  pop     rsi
0x18004fd8c  pop     rbx
0x18004fd8d  pop     rbp
0x18004fd8e  retn
```
