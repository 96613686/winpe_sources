# CCellularSettingHelperWwan::EnableSimPin(MBN_PIN_TYPE,ushort const *,uchar)

- ea: `0x18004d910`
- end: `0x18004dd20`
- name: `?EnableSimPin@CCellularSettingHelperWwan@@UEAAJW4MBN_PIN_TYPE@@PEBGE@Z`
- size: `1040`
- prototype: `__int64 __fastcall(CCellularSettingHelperWwan *this, enum MBN_PIN_TYPE, const unsigned __int16 *, char)`
- caller_count: `0`
- callee_count: `13`
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
- `0x18004ccc0`
- `0x18004d910`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004db21`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004db21`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004db7e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004dbfd`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004dce8`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004db7e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004dbfd`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004dce8`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004dab0`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004dab0`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetInterface` at `0x18004dbd2`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetInterface` at `0x18004dbd2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCellularSettingHelperWwan::EnableSimPin(
        CCellularSettingHelperWwan *this,
        enum MBN_PIN_TYPE a2,
        const unsigned __int16 *a3,
        char a4)
{
  const struct _tlgProvider_t *v6; // rax
  int v7; // r8d
  int v8; // r9d
  unsigned __int64 v9; // rax
  unsigned int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rcx
  int v14; // eax
  unsigned int v15; // eax
  const struct _tlgProvider_t *v16; // rax
  int v17; // r8d
  int v18; // r9d
  int v19; // [rsp+20h] [rbp-E0h]
  unsigned int *v20; // [rsp+20h] [rbp-E0h]
  char *v21; // [rsp+28h] [rbp-D8h]
  enum MBN_PIN_TYPE v22; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v25[3]; // [rsp+58h] [rbp-A8h] BYREF
  char v26; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v27[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v28; // [rsp+88h] [rbp-78h]
  char *v29[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v30; // [rsp+A0h] [rbp-60h]
  _DWORD v31[2]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v32[4]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v33[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v34[72]; // [rsp+C8h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]
  char v36; // [rsp+168h] [rbp+68h] BYREF

  v36 = a4;
  v22 = a2;
  *(_OWORD *)v29 = 0;
  v30 = 0;
  *(_OWORD *)v27 = 0;
  v28 = 0;
  std::vector<unsigned short>::resize(v29);
  std::vector<unsigned short>::resize(v27);
  StringCchPrintfW((unsigned __int16 *)v29[0], (v29[1] - v29[0]) >> 1, L"Enter");
  v21 = v29[0];
  v19 = 202;
  StringCchPrintfW(v27[0], v27[1] - v27[0], L"%S(%d):%s", "CCellularSettingHelperWwan::EnableSimPin");
  v6 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v6 > 5u )
  {
    *(unsigned __int16 **)v32 = v27[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)v6,
      (unsigned int)&word_1800797A6,
      v7,
      v8,
      (__int64)v32);
  }
  std::vector<unsigned short>::~vector<unsigned short>(v27);
  std::vector<unsigned short>::~vector<unsigned short>(v29);
  v23 = 0;
  v25[0] = &v23;
  v25[1] = &v22;
  v25[2] = &v36;
  v26 = 1;
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD8,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
      (const char *)0x80070057LL,
      v19);
LABEL_9:
    if ( v26 )
    {
      v26 = 0;
      CCellularSettingHelperWwan::EnableSimPin_::_2_::_lambda_1_::operator()(v25);
    }
    return 2147942487LL;
  }
  v9 = -1;
  do
    ++v9;
  while ( a3[v9] );
  if ( v9 > 0x11 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xDA,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
      (const char *)0x80070057LL,
      (int)"Pin is too long.",
      v21);
    goto LABEL_9;
  }
  v24 = 0;
  v31[0] = 0;
  v11 = WwanOpenHandle(1, 0, v31, &v24);
  if ( v11 )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xDD,
            (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
            (const char *)v11,
            v19);
    if ( v26 )
    {
      v26 = 0;
      CCellularSettingHelperWwan::EnableSimPin_::_2_::_lambda_1_::operator()(v25);
    }
    return v12;
  }
  memset_0(v33, 0, 0x50u);
  v33[0] = v22;
  v33[1] = 2 - (v36 != 0);
  _o_wcscpy_s(v34, 17, a3);
  *(_OWORD *)v32 = 0;
  v13 = *((_QWORD *)this + 5);
  if ( v13 )
  {
    *(_QWORD *)v32 = *((_QWORD *)this + 4);
    *(_QWORD *)&v32[2] = v13;
    _InterlockedIncrement((volatile signed __int32 *)(v13 + 12));
  }
  v14 = CWwanTranslator::SetAdapterPinActionRequest(v32, (char *)this + 8, v33);
  v12 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE6,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
      (const char *)(unsigned int)v14,
      v19);
    WwanCloseHandle(v24, 0);
    if ( v26 )
    {
      v26 = 0;
      CCellularSettingHelperWwan::EnableSimPin_::_2_::_lambda_1_::operator()(v25);
    }
    return v12;
  }
  v31[1] = 0;
  v20 = v33;
  v15 = WwanSetInterface(v24, (char *)this + 8, 0, 80);
  if ( v15 )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xEA,
            (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
            (const char *)v15,
            (unsigned int)v33);
    WwanCloseHandle(v24, 0);
    if ( v26 )
    {
      v26 = 0;
      CCellularSettingHelperWwan::EnableSimPin_::_2_::_lambda_1_::operator()(v25);
    }
    return v12;
  }
  v23 = 1;
  *(_OWORD *)v27 = 0;
  v28 = 0;
  *(_OWORD *)v29 = 0;
  v30 = 0;
  std::vector<unsigned short>::resize(v27);
  std::vector<unsigned short>::resize(v29);
  StringCchPrintfW(v27[0], v27[1] - v27[0], L"Exit");
  LODWORD(v20) = 238;
  StringCchPrintfW(
    (unsigned __int16 *)v29[0],
    (v29[1] - v29[0]) >> 1,
    L"%S(%d):%s",
    "CCellularSettingHelperWwan::EnableSimPin",
    v20,
    v27[0]);
  v16 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v16 > 5u )
  {
    *(char **)v32 = v29[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)v16,
      (unsigned int)byte_1800797C9,
      v17,
      v18,
      (__int64)v32);
  }
  std::vector<unsigned short>::~vector<unsigned short>(v29);
  std::vector<unsigned short>::~vector<unsigned short>(v27);
  WwanCloseHandle(v24, 0);
  if ( v26 )
  {
    v26 = 0;
    CCellularSettingHelperWwan::EnableSimPin_::_2_::_lambda_1_::operator()(v25);
  }
  return 0;
}

```

## disassembly

```asm
0x18004d910  mov     [rsp-8+arg_18], r9b
0x18004d915  push    rbp
0x18004d916  push    rbx
0x18004d917  push    rsi
0x18004d918  push    rdi
0x18004d919  lea     rbp, [rsp-28h]
0x18004d91e  sub     rsp, 128h
0x18004d925  mov     rax, cs:__security_cookie
0x18004d92c  xor     rax, rsp
0x18004d92f  mov     [rbp+40h+var_30], rax
0x18004d933  mov     rbx, r8
0x18004d936  mov     rdi, rcx
0x18004d939  mov     [rsp+140h+var_100], edx
0x18004d93d  xorps   xmm0, xmm0
0x18004d940  movdqu  xmmword ptr [rbp+40h+var_B0], xmm0
0x18004d945  xor     esi, esi
0x18004d947  mov     [rbp+40h+var_A0], rsi
0x18004d94b  movdqu  xmmword ptr [rsp+140h+var_C8], xmm0
0x18004d951  mov     [rbp+40h+var_B8], rsi
0x18004d955  lea     rcx, [rbp+40h+var_B0]
0x18004d959  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004d95e  lea     rcx, [rsp+140h+var_C8]
0x18004d963  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004d968  mov     rdx, [rbp+40h+var_B0+8]
0x18004d96c  mov     rcx, [rbp+40h+var_B0]; unsigned __int16 *
0x18004d970  sub     rdx, rcx
0x18004d973  sar     rdx, 1; unsigned __int64
0x18004d976  lea     r8, aEnter; "Enter"
0x18004d97d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004d982  mov     rdx, [rbp+40h+var_C8+8]
0x18004d986  mov     rcx, [rsp+140h+var_C8]; unsigned __int16 *
0x18004d98b  sub     rdx, rcx
0x18004d98e  sar     rdx, 1; unsigned __int64
0x18004d991  mov     rax, [rbp+40h+var_B0]
0x18004d995  mov     [rsp+140h+var_118], rax; char *
0x18004d99a  mov     [rsp+140h+var_120], 0CAh
0x18004d9a2  lea     r9, aCcellularsetti_7; "CCellularSettingHelperWwan::EnableSimPi"...
0x18004d9a9  lea     r8, aSDS; "%S(%d):%s"
0x18004d9b0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004d9b5  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004d9ba  mov     ecx, [rax]
0x18004d9bc  cmp     ecx, 5
0x18004d9bf  jbe     short loc_18004D9E2
0x18004d9c1  mov     rcx, [rsp+140h+var_C8]
0x18004d9c6  mov     qword ptr [rbp+40h+var_90], rcx
0x18004d9ca  lea     rcx, [rbp+40h+var_90]
0x18004d9ce  mov     qword ptr [rsp+140h+var_120], rcx; int
0x18004d9d3  lea     rdx, word_1800797A6
0x18004d9da  mov     rcx, rax
0x18004d9dd  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004d9e2  lea     rcx, [rsp+140h+var_C8]
0x18004d9e7  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004d9ec  lea     rcx, [rbp+40h+var_B0]
0x18004d9f0  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004d9f5  mov     [rsp+140h+var_F8], esi
0x18004d9f9  lea     rax, [rsp+140h+var_F8]
0x18004d9fe  mov     [rsp+140h+var_E8], rax
0x18004da03  lea     rax, [rsp+140h+var_100]
0x18004da08  mov     [rsp+140h+var_E0], rax
0x18004da0d  lea     rax, [rbp+40h+arg_18]
0x18004da11  mov     [rsp+140h+var_D8], rax
0x18004da16  mov     [rsp+140h+var_D0], 1
0x18004da1b  test    rbx, rbx
0x18004da1e  jnz     short loc_18004DA3E
0x18004da20  mov     rcx, [rbp+48h]; this
0x18004da24  mov     r9d, 80070057h; char *
0x18004da2a  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004da31  mov     edx, 0D8h; void *
0x18004da36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004da3b  nop
0x18004da3c  jmp     short loc_18004DA79
0x18004da3e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004da42  inc     rax
0x18004da45  cmp     [rbx+rax*2], si
0x18004da49  jnz     short loc_18004DA42
0x18004da4b  cmp     rax, 11h
0x18004da4f  jbe     short loc_18004DA9A
0x18004da51  mov     rcx, [rbp+48h]; this
0x18004da55  lea     rax, aPinIsTooLong; "Pin is too long."
0x18004da5c  mov     qword ptr [rsp+140h+var_120], rax; int
0x18004da61  mov     r9d, 80070057h; char *
0x18004da67  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004da6e  mov     edx, 0DAh; void *
0x18004da73  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004da78  nop
0x18004da79  cmp     [rsp+140h+var_D0], sil
0x18004da7e  jz      short loc_18004DA90
0x18004da80  mov     [rsp+140h+var_D0], sil
0x18004da85  lea     rcx, [rsp+140h+var_E8]
0x18004da8a  call    _CCellularSettingHelperWwan__EnableSimPin____2____lambda_1___operator__
0x18004da8f  nop
0x18004da90  mov     eax, 80070057h
0x18004da95  jmp     loc_18004DD08
0x18004da9a  mov     [rsp+140h+var_F0], rsi
0x18004da9f  mov     [rbp+40h+var_98], esi
0x18004daa2  lea     r9, [rsp+140h+var_F0]
0x18004daa7  lea     r8, [rbp+40h+var_98]
0x18004daab  xor     edx, edx
0x18004daad  lea     ecx, [rdx+1]
0x18004dab0  call    cs:__imp_WwanOpenHandle
0x18004dab6  test    eax, eax
0x18004dab8  jz      short loc_18004DAF2
0x18004daba  mov     rcx, [rbp+48h]; this
0x18004dabe  mov     r9d, eax; char *
0x18004dac1  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004dac8  mov     edx, 0DDh; void *
0x18004dacd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004dad2  mov     ebx, eax
0x18004dad4  cmp     [rsp+140h+var_D0], sil
0x18004dad9  jz      short loc_18004DAEB
0x18004dadb  mov     [rsp+140h+var_D0], sil
0x18004dae0  lea     rcx, [rsp+140h+var_E8]
0x18004dae5  call    _CCellularSettingHelperWwan__EnableSimPin____2____lambda_1___operator__
0x18004daea  nop
0x18004daeb  mov     eax, ebx
0x18004daed  jmp     loc_18004DD08
0x18004daf2  xor     edx, edx; Val
0x18004daf4  lea     r8d, [rdx+50h]; Size
0x18004daf8  lea     rcx, [rbp+40h+var_80]; void *
0x18004dafc  call    memset_0
0x18004db01  mov     eax, [rsp+140h+var_100]
0x18004db05  mov     [rbp+40h+var_80], eax
0x18004db08  mov     al, [rbp+40h+arg_18]
0x18004db0b  neg     al
0x18004db0d  sbb     ecx, ecx
0x18004db0f  add     ecx, 2
0x18004db12  mov     [rbp+40h+var_7C], ecx
0x18004db15  mov     r8, rbx
0x18004db18  mov     edx, 11h
0x18004db1d  lea     rcx, [rbp+40h+var_78]
0x18004db21  call    cs:__imp__o_wcscpy_s
0x18004db27  xorps   xmm0, xmm0
0x18004db2a  movdqu  xmmword ptr [rbp+40h+var_90], xmm0
0x18004db2f  mov     rcx, [rdi+28h]
0x18004db33  test    rcx, rcx
0x18004db36  jz      short loc_18004DB48
0x18004db38  mov     rax, [rdi+20h]
0x18004db3c  mov     qword ptr [rbp+40h+var_90], rax
0x18004db40  mov     qword ptr [rbp+40h+var_90+8], rcx
0x18004db44  lock inc dword ptr [rcx+0Ch]
0x18004db48  lea     r8, [rbp+40h+var_80]
0x18004db4c  lea     rdx, [rdi+8]
0x18004db50  lea     rcx, [rbp+40h+var_90]
0x18004db54  call    ?SetAdapterPinActionRequest@CWwanTranslator@@SAJV?$weak_ptr@VCWwanTranslator@@@std@@AEBU_GUID@@AEAU_WWAN_PIN_ACTION@@@Z; CWwanTranslator::SetAdapterPinActionRequest(std::weak_ptr<CWwanTranslator>,_GUID const &,_WWAN_PIN_ACTION &)
0x18004db59  mov     ebx, eax
0x18004db5b  test    eax, eax
0x18004db5d  jns     short loc_18004DBA1
0x18004db5f  mov     rcx, [rbp+48h]; this
0x18004db63  mov     r9d, eax; char *
0x18004db66  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004db6d  mov     edx, 0E6h; void *
0x18004db72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004db77  xor     edx, edx
0x18004db79  mov     rcx, [rsp+140h+var_F0]
0x18004db7e  call    cs:__imp_WwanCloseHandle
0x18004db84  nop
0x18004db85  cmp     [rsp+140h+var_D0], sil
0x18004db8a  jz      short loc_18004DB9C
0x18004db8c  mov     [rsp+140h+var_D0], sil
0x18004db91  lea     rcx, [rsp+140h+var_E8]
0x18004db96  call    _CCellularSettingHelperWwan__EnableSimPin____2____lambda_1___operator__
0x18004db9b  nop
0x18004db9c  jmp     loc_18004DAEB
0x18004dba1  mov     [rbp+40h+var_94], esi
0x18004dba4  mov     [rsp+140h+var_108], rsi
0x18004dba9  mov     [rsp+140h+var_110], rsi
0x18004dbae  lea     rax, [rbp+40h+var_94]
0x18004dbb2  mov     [rsp+140h+var_118], rax
0x18004dbb7  lea     rax, [rbp+40h+var_80]
0x18004dbbb  mov     qword ptr [rsp+140h+var_120], rax; unsigned int
0x18004dbc0  mov     r9d, 50h ; 'P'
0x18004dbc6  xor     r8d, r8d
0x18004dbc9  lea     rdx, [rdi+8]
0x18004dbcd  mov     rcx, [rsp+140h+var_F0]
0x18004dbd2  call    cs:__imp_WwanSetInterface
0x18004dbd8  test    eax, eax
0x18004dbda  jz      short loc_18004DC20
0x18004dbdc  mov     rcx, [rbp+48h]; this
0x18004dbe0  mov     r9d, eax; char *
0x18004dbe3  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004dbea  mov     edx, 0EAh; void *
0x18004dbef  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004dbf4  mov     ebx, eax
0x18004dbf6  xor     edx, edx
0x18004dbf8  mov     rcx, [rsp+140h+var_F0]
0x18004dbfd  call    cs:__imp_WwanCloseHandle
0x18004dc03  nop
0x18004dc04  cmp     [rsp+140h+var_D0], sil
0x18004dc09  jz      short loc_18004DC1B
0x18004dc0b  mov     [rsp+140h+var_D0], sil
0x18004dc10  lea     rcx, [rsp+140h+var_E8]
0x18004dc15  call    _CCellularSettingHelperWwan__EnableSimPin____2____lambda_1___operator__
0x18004dc1a  nop
0x18004dc1b  jmp     loc_18004DAEB
0x18004dc20  mov     [rsp+140h+var_F8], 1
0x18004dc28  xorps   xmm0, xmm0
0x18004dc2b  movdqu  xmmword ptr [rsp+140h+var_C8], xmm0
0x18004dc31  mov     [rbp+40h+var_B8], rsi
0x18004dc35  xorps   xmm1, xmm1
0x18004dc38  movdqu  xmmword ptr [rbp+40h+var_B0], xmm1
0x18004dc3d  mov     [rbp+40h+var_A0], rsi
0x18004dc41  lea     rcx, [rsp+140h+var_C8]
0x18004dc46  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004dc4b  lea     rcx, [rbp+40h+var_B0]
0x18004dc4f  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004dc54  mov     rdx, [rbp+40h+var_C8+8]
0x18004dc58  mov     rcx, [rsp+140h+var_C8]; unsigned __int16 *
0x18004dc5d  sub     rdx, rcx
0x18004dc60  sar     rdx, 1; unsigned __int64
0x18004dc63  lea     r8, aExit; "Exit"
0x18004dc6a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004dc6f  mov     rdx, [rbp+40h+var_B0+8]
0x18004dc73  mov     rcx, [rbp+40h+var_B0]; unsigned __int16 *
0x18004dc77  sub     rdx, rcx
0x18004dc7a  sar     rdx, 1; unsigned __int64
0x18004dc7d  mov     rax, [rsp+140h+var_C8]
0x18004dc82  mov     [rsp+140h+var_118], rax
0x18004dc87  mov     [rsp+140h+var_120], 0EEh
0x18004dc8f  lea     r9, aCcellularsetti_7; "CCellularSettingHelperWwan::EnableSimPi"...
0x18004dc96  lea     r8, aSDS; "%S(%d):%s"
0x18004dc9d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004dca2  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004dca7  mov     ecx, [rax]
0x18004dca9  cmp     ecx, 5
0x18004dcac  jbe     short loc_18004DCCE
0x18004dcae  mov     rcx, [rbp+40h+var_B0]
0x18004dcb2  mov     qword ptr [rbp+40h+var_90], rcx
0x18004dcb6  lea     rcx, [rbp+40h+var_90]
0x18004dcba  mov     qword ptr [rsp+140h+var_120], rcx
0x18004dcbf  lea     rdx, byte_1800797C9
0x18004dcc6  mov     rcx, rax
0x18004dcc9  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004dcce  lea     rcx, [rbp+40h+var_B0]
0x18004dcd2  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004dcd7  lea     rcx, [rsp+140h+var_C8]
0x18004dcdc  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004dce1  xor     edx, edx
0x18004dce3  mov     rcx, [rsp+140h+var_F0]
0x18004dce8  call    cs:__imp_WwanCloseHandle
0x18004dcee  nop
0x18004dcef  cmp     [rsp+140h+var_D0], sil
0x18004dcf4  jz      short loc_18004DD06
0x18004dcf6  mov     [rsp+140h+var_D0], sil
0x18004dcfb  lea     rcx, [rsp+140h+var_E8]
0x18004dd00  call    _CCellularSettingHelperWwan__EnableSimPin____2____lambda_1___operator__
0x18004dd05  nop
0x18004dd06  xor     eax, eax
0x18004dd08  mov     rcx, [rbp+40h+var_30]
0x18004dd0c  xor     rcx, rsp; StackCookie
0x18004dd0f  call    __security_check_cookie
0x18004dd14  add     rsp, 128h
0x18004dd1b  pop     rdi
0x18004dd1c  pop     rsi
0x18004dd1d  pop     rbx
0x18004dd1e  pop     rbp
0x18004dd1f  retn
```
