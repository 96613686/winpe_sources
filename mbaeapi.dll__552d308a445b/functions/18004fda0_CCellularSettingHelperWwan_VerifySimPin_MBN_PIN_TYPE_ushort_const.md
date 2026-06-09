# CCellularSettingHelperWwan::VerifySimPin(MBN_PIN_TYPE,ushort const *)

- ea: `0x18004fda0`
- end: `0x1800501a3`
- name: `?VerifySimPin@CCellularSettingHelperWwan@@UEAAJW4MBN_PIN_TYPE@@PEBG@Z`
- size: `1027`
- prototype: `__int64 __fastcall(CCellularSettingHelperWwan *__hidden this, enum MBN_PIN_TYPE, const unsigned __int16 *)`
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
- `0x18004cf14`
- `0x18004fda0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004ff9c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004ff9c`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004fff9`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180050078`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180050164`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004fff9`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180050078`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180050164`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004ff35`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004ff35`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetInterface` at `0x18005004d`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetInterface` at `0x18005004d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCellularSettingHelperWwan::VerifySimPin(
        CCellularSettingHelperWwan *this,
        enum MBN_PIN_TYPE a2,
        const unsigned __int16 *a3)
{
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  unsigned __int64 v8; // rax
  unsigned int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rcx
  int v13; // eax
  unsigned int v14; // eax
  const struct _tlgProvider_t *v15; // rax
  __int64 v16; // r8
  __int64 v17; // r9
  int v18; // [rsp+20h] [rbp-E0h]
  unsigned int *v19; // [rsp+20h] [rbp-E0h]
  char *v20; // [rsp+28h] [rbp-D8h]
  int *v21; // [rsp+40h] [rbp-C0h] BYREF
  enum MBN_PIN_TYPE *v22; // [rsp+48h] [rbp-B8h]
  char v23; // [rsp+50h] [rbp-B0h]
  enum MBN_PIN_TYPE v24; // [rsp+58h] [rbp-A8h] BYREF
  int v25; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v27[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v28; // [rsp+80h] [rbp-80h]
  char *v29[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v30; // [rsp+98h] [rbp-68h]
  _DWORD v31[2]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v32[4]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v33[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v34[72]; // [rsp+C8h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v24 = a2;
  *(_OWORD *)v29 = 0;
  v30 = 0;
  *(_OWORD *)v27 = 0;
  v28 = 0;
  std::vector<unsigned short>::resize(v29);
  std::vector<unsigned short>::resize(v27);
  StringCchPrintfW((unsigned __int16 *)v29[0], (v29[1] - v29[0]) >> 1, L"Enter");
  v20 = v29[0];
  v18 = 68;
  StringCchPrintfW(v27[0], v27[1] - v27[0], L"%S(%d):%s", "CCellularSettingHelperWwan::VerifySimPin");
  v5 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v5 > 5u )
  {
    *(unsigned __int16 **)v32 = v27[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v5,
      (__int64)&byte_180079927,
      v6,
      v7,
      (const unsigned __int16 **)v32);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v27);
  std::vector<unsigned short>::~vector<unsigned short>(v29);
  v25 = 0;
  v21 = &v25;
  v22 = &v24;
  v23 = 1;
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
      (const char *)0x80070057LL,
      v18);
LABEL_9:
    v23 = 0;
    CCellularSettingHelperWwan::VerifySimPin_::_2_::_lambda_1_::operator()(&v21);
    return 2147942487LL;
  }
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  if ( v8 > 0x11 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
      (const char *)0x80070057LL,
      (int)"Pin is too long.",
      v20);
    goto LABEL_9;
  }
  v26 = 0;
  v31[0] = 0;
  v10 = WwanOpenHandle(1, 0, v31, &v26);
  if ( v10 )
  {
    v11 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x56,
            (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
            (const char *)v10,
            v18);
    v23 = 0;
    CCellularSettingHelperWwan::VerifySimPin_::_2_::_lambda_1_::operator()(&v21);
    return v11;
  }
  memset_0(v33, 0, 0x50u);
  v33[0] = v24;
  v33[1] = 0;
  _o_wcscpy_s(v34, 17, a3);
  *(_OWORD *)v32 = 0;
  v12 = *((_QWORD *)this + 5);
  if ( v12 )
  {
    *(_QWORD *)v32 = *((_QWORD *)this + 4);
    *(_QWORD *)&v32[2] = v12;
    _InterlockedIncrement((volatile signed __int32 *)(v12 + 12));
  }
  v13 = CWwanTranslator::SetAdapterPinActionRequest(v32, (char *)this + 8, v33);
  v11 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5F,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
      (const char *)(unsigned int)v13,
      v18);
    WwanCloseHandle(v26, 0);
    v23 = 0;
    CCellularSettingHelperWwan::VerifySimPin_::_2_::_lambda_1_::operator()(&v21);
    return v11;
  }
  v31[1] = 0;
  v19 = v33;
  v14 = WwanSetInterface(v26, (char *)this + 8, 0, 80);
  if ( v14 )
  {
    v11 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x63,
            (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
            (const char *)v14,
            (unsigned int)v33);
    WwanCloseHandle(v26, 0);
    v23 = 0;
    CCellularSettingHelperWwan::VerifySimPin_::_2_::_lambda_1_::operator()(&v21);
    return v11;
  }
  v25 = 1;
  *(_OWORD *)v27 = 0;
  v28 = 0;
  *(_OWORD *)v29 = 0;
  v30 = 0;
  std::vector<unsigned short>::resize(v27);
  std::vector<unsigned short>::resize(v29);
  StringCchPrintfW(v27[0], v27[1] - v27[0], L"Exit");
  LODWORD(v19) = 103;
  StringCchPrintfW(
    (unsigned __int16 *)v29[0],
    (v29[1] - v29[0]) >> 1,
    L"%S(%d):%s",
    "CCellularSettingHelperWwan::VerifySimPin",
    v19,
    v27[0],
    0,
    0,
    v21,
    v22);
  v15 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v15 > 5u )
  {
    *(char **)v32 = v29[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v15,
      (__int64)qword_1800798C0,
      v16,
      v17,
      (const unsigned __int16 **)v32);
  }
  std::vector<unsigned short>::~vector<unsigned short>(v29);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v27);
  WwanCloseHandle(v26, 0);
  v23 = 0;
  CCellularSettingHelperWwan::VerifySimPin_::_2_::_lambda_1_::operator()(&v21);
  return 0;
}

```

## disassembly

```asm
0x18004fda0  mov     [rsp-8+arg_18], rbx
0x18004fda5  push    rbp
0x18004fda6  push    rsi
0x18004fda7  push    rdi
0x18004fda8  lea     rbp, [rsp-20h]
0x18004fdad  sub     rsp, 120h
0x18004fdb4  mov     rax, cs:__security_cookie
0x18004fdbb  xor     rax, rsp
0x18004fdbe  mov     [rbp+30h+var_20], rax
0x18004fdc2  mov     rbx, r8
0x18004fdc5  mov     rdi, rcx
0x18004fdc8  mov     [rsp+130h+var_D8], edx
0x18004fdcc  xorps   xmm0, xmm0
0x18004fdcf  movdqu  xmmword ptr [rbp+30h+var_A8], xmm0
0x18004fdd4  xor     esi, esi
0x18004fdd6  mov     [rbp+30h+var_98], rsi
0x18004fdda  movdqu  xmmword ptr [rsp+130h+var_C0], xmm0
0x18004fde0  mov     [rbp+30h+var_B0], rsi
0x18004fde4  lea     rcx, [rbp+30h+var_A8]
0x18004fde8  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004fded  lea     rcx, [rsp+130h+var_C0]
0x18004fdf2  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004fdf7  mov     rdx, [rbp+30h+var_A8+8]
0x18004fdfb  mov     rcx, [rbp+30h+var_A8]; unsigned __int16 *
0x18004fdff  sub     rdx, rcx
0x18004fe02  sar     rdx, 1; unsigned __int64
0x18004fe05  lea     r8, aEnter; "Enter"
0x18004fe0c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004fe11  mov     rdx, [rsp+130h+var_C0+8]
0x18004fe16  mov     rcx, [rsp+130h+var_C0]; unsigned __int16 *
0x18004fe1b  sub     rdx, rcx
0x18004fe1e  sar     rdx, 1; unsigned __int64
0x18004fe21  mov     rax, [rbp+30h+var_A8]
0x18004fe25  mov     [rsp+130h+var_108], rax; char *
0x18004fe2a  mov     [rsp+130h+var_110], 44h ; 'D'
0x18004fe32  lea     r9, aCcellularsetti_28; "CCellularSettingHelperWwan::VerifySimPi"...
0x18004fe39  lea     r8, aSDS; "%S(%d):%s"
0x18004fe40  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004fe45  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004fe4a  mov     ecx, [rax]
0x18004fe4c  cmp     ecx, 5
0x18004fe4f  jbe     short loc_18004FE72
0x18004fe51  mov     rcx, [rsp+130h+var_C0]
0x18004fe56  mov     qword ptr [rbp+30h+var_88], rcx
0x18004fe5a  lea     rcx, [rbp+30h+var_88]
0x18004fe5e  mov     qword ptr [rsp+130h+var_110], rcx; int
0x18004fe63  lea     rdx, byte_180079927
0x18004fe6a  mov     rcx, rax
0x18004fe6d  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004fe72  lea     rcx, [rsp+130h+var_C0]
0x18004fe77  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004fe7c  lea     rcx, [rbp+30h+var_A8]
0x18004fe80  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004fe85  mov     [rsp+130h+var_D0], esi
0x18004fe89  lea     rax, [rsp+130h+var_D0]
0x18004fe8e  mov     [rsp+130h+var_F0], rax
0x18004fe93  lea     rax, [rsp+130h+var_D8]
0x18004fe98  mov     [rsp+130h+var_E8], rax
0x18004fe9d  mov     [rsp+130h+var_E0], 1
0x18004fea2  test    rbx, rbx
0x18004fea5  jnz     short loc_18004FEC3
0x18004fea7  mov     rcx, [rbp+38h]; this
0x18004feab  mov     r9d, 80070057h; char *
0x18004feb1  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004feb8  lea     edx, [rbx+51h]; void *
0x18004febb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fec0  nop
0x18004fec1  jmp     short loc_18004FEFE
0x18004fec3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004fec7  inc     rax
0x18004feca  cmp     [rbx+rax*2], si
0x18004fece  jnz     short loc_18004FEC7
0x18004fed0  cmp     rax, 11h
0x18004fed4  jbe     short loc_18004FF1F
0x18004fed6  mov     rcx, [rbp+38h]; this
0x18004feda  lea     rax, aPinIsTooLong; "Pin is too long."
0x18004fee1  mov     qword ptr [rsp+130h+var_110], rax; int
0x18004fee6  mov     r9d, 80070057h; char *
0x18004feec  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004fef3  mov     edx, 53h ; 'S'; void *
0x18004fef8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004fefd  nop
0x18004fefe  cmp     [rsp+130h+var_E0], sil
0x18004ff03  jz      short loc_18004FF15
0x18004ff05  mov     [rsp+130h+var_E0], sil
0x18004ff0a  lea     rcx, [rsp+130h+var_F0]
0x18004ff0f  call    _CCellularSettingHelperWwan__VerifySimPin____2____lambda_1___operator__
0x18004ff14  nop
0x18004ff15  mov     eax, 80070057h
0x18004ff1a  jmp     loc_180050184
0x18004ff1f  mov     [rsp+130h+var_C8], rsi
0x18004ff24  mov     [rbp+30h+var_90], esi
0x18004ff27  lea     r9, [rsp+130h+var_C8]
0x18004ff2c  lea     r8, [rbp+30h+var_90]
0x18004ff30  xor     edx, edx
0x18004ff32  lea     ecx, [rdx+1]
0x18004ff35  call    cs:__imp_WwanOpenHandle
0x18004ff3b  test    eax, eax
0x18004ff3d  jz      short loc_18004FF77
0x18004ff3f  mov     rcx, [rbp+38h]; this
0x18004ff43  mov     r9d, eax; char *
0x18004ff46  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004ff4d  mov     edx, 56h ; 'V'; void *
0x18004ff52  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004ff57  mov     ebx, eax
0x18004ff59  cmp     [rsp+130h+var_E0], sil
0x18004ff5e  jz      short loc_18004FF70
0x18004ff60  mov     [rsp+130h+var_E0], sil
0x18004ff65  lea     rcx, [rsp+130h+var_F0]
0x18004ff6a  call    _CCellularSettingHelperWwan__VerifySimPin____2____lambda_1___operator__
0x18004ff6f  nop
0x18004ff70  mov     eax, ebx
0x18004ff72  jmp     loc_180050184
0x18004ff77  xor     edx, edx; Val
0x18004ff79  lea     r8d, [rdx+50h]; Size
0x18004ff7d  lea     rcx, [rbp+30h+var_70]; void *
0x18004ff81  call    memset_0
0x18004ff86  mov     eax, [rsp+130h+var_D8]
0x18004ff8a  mov     [rbp+30h+var_70], eax
0x18004ff8d  mov     [rbp+30h+var_6C], esi
0x18004ff90  mov     r8, rbx
0x18004ff93  mov     edx, 11h
0x18004ff98  lea     rcx, [rbp+30h+var_68]
0x18004ff9c  call    cs:__imp__o_wcscpy_s
0x18004ffa2  xorps   xmm0, xmm0
0x18004ffa5  movdqu  xmmword ptr [rbp+30h+var_88], xmm0
0x18004ffaa  mov     rcx, [rdi+28h]
0x18004ffae  test    rcx, rcx
0x18004ffb1  jz      short loc_18004FFC3
0x18004ffb3  mov     rax, [rdi+20h]
0x18004ffb7  mov     qword ptr [rbp+30h+var_88], rax
0x18004ffbb  mov     qword ptr [rbp+30h+var_88+8], rcx
0x18004ffbf  lock inc dword ptr [rcx+0Ch]
0x18004ffc3  lea     r8, [rbp+30h+var_70]
0x18004ffc7  lea     rdx, [rdi+8]
0x18004ffcb  lea     rcx, [rbp+30h+var_88]
0x18004ffcf  call    ?SetAdapterPinActionRequest@CWwanTranslator@@SAJV?$weak_ptr@VCWwanTranslator@@@std@@AEBU_GUID@@AEAU_WWAN_PIN_ACTION@@@Z; CWwanTranslator::SetAdapterPinActionRequest(std::weak_ptr<CWwanTranslator>,_GUID const &,_WWAN_PIN_ACTION &)
0x18004ffd4  mov     ebx, eax
0x18004ffd6  test    eax, eax
0x18004ffd8  jns     short loc_18005001C
0x18004ffda  mov     rcx, [rbp+38h]; this
0x18004ffde  mov     r9d, eax; char *
0x18004ffe1  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004ffe8  mov     edx, 5Fh ; '_'; void *
0x18004ffed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fff2  xor     edx, edx
0x18004fff4  mov     rcx, [rsp+130h+var_C8]
0x18004fff9  call    cs:__imp_WwanCloseHandle
0x18004ffff  nop
0x180050000  cmp     [rsp+130h+var_E0], sil
0x180050005  jz      short loc_180050017
0x180050007  mov     [rsp+130h+var_E0], sil
0x18005000c  lea     rcx, [rsp+130h+var_F0]
0x180050011  call    _CCellularSettingHelperWwan__VerifySimPin____2____lambda_1___operator__
0x180050016  nop
0x180050017  jmp     loc_18004FF70
0x18005001c  mov     [rbp+30h+var_8C], esi
0x18005001f  mov     [rsp+130h+var_F8], rsi
0x180050024  mov     [rsp+130h+var_100], rsi
0x180050029  lea     rax, [rbp+30h+var_8C]
0x18005002d  mov     [rsp+130h+var_108], rax
0x180050032  lea     rax, [rbp+30h+var_70]
0x180050036  mov     qword ptr [rsp+130h+var_110], rax; unsigned int
0x18005003b  mov     r9d, 50h ; 'P'
0x180050041  xor     r8d, r8d
0x180050044  lea     rdx, [rdi+8]
0x180050048  mov     rcx, [rsp+130h+var_C8]
0x18005004d  call    cs:__imp_WwanSetInterface
0x180050053  test    eax, eax
0x180050055  jz      short loc_18005009B
0x180050057  mov     rcx, [rbp+38h]; this
0x18005005b  mov     r9d, eax; char *
0x18005005e  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180050065  mov     edx, 63h ; 'c'; void *
0x18005006a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005006f  mov     ebx, eax
0x180050071  xor     edx, edx
0x180050073  mov     rcx, [rsp+130h+var_C8]
0x180050078  call    cs:__imp_WwanCloseHandle
0x18005007e  nop
0x18005007f  cmp     [rsp+130h+var_E0], sil
0x180050084  jz      short loc_180050096
0x180050086  mov     [rsp+130h+var_E0], sil
0x18005008b  lea     rcx, [rsp+130h+var_F0]
0x180050090  call    _CCellularSettingHelperWwan__VerifySimPin____2____lambda_1___operator__
0x180050095  nop
0x180050096  jmp     loc_18004FF70
0x18005009b  mov     [rsp+130h+var_D0], 1
0x1800500a3  xorps   xmm0, xmm0
0x1800500a6  movdqu  xmmword ptr [rsp+130h+var_C0], xmm0
0x1800500ac  mov     [rbp+30h+var_B0], rsi
0x1800500b0  xorps   xmm1, xmm1
0x1800500b3  movdqu  xmmword ptr [rbp+30h+var_A8], xmm1
0x1800500b8  mov     [rbp+30h+var_98], rsi
0x1800500bc  lea     rcx, [rsp+130h+var_C0]
0x1800500c1  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800500c6  lea     rcx, [rbp+30h+var_A8]
0x1800500ca  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800500cf  mov     rdx, [rsp+130h+var_C0+8]
0x1800500d4  mov     rcx, [rsp+130h+var_C0]; unsigned __int16 *
0x1800500d9  sub     rdx, rcx
0x1800500dc  sar     rdx, 1; unsigned __int64
0x1800500df  lea     r8, aExit; "Exit"
0x1800500e6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800500eb  mov     rdx, [rbp+30h+var_A8+8]
0x1800500ef  mov     rcx, [rbp+30h+var_A8]; unsigned __int16 *
0x1800500f3  sub     rdx, rcx
0x1800500f6  sar     rdx, 1; unsigned __int64
0x1800500f9  mov     rax, [rsp+130h+var_C0]
0x1800500fe  mov     [rsp+130h+var_108], rax
0x180050103  mov     [rsp+130h+var_110], 67h ; 'g'
0x18005010b  lea     r9, aCcellularsetti_28; "CCellularSettingHelperWwan::VerifySimPi"...
0x180050112  lea     r8, aSDS; "%S(%d):%s"
0x180050119  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005011e  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180050123  mov     ecx, [rax]
0x180050125  cmp     ecx, 5
0x180050128  jbe     short loc_18005014A
0x18005012a  mov     rcx, [rbp+30h+var_A8]
0x18005012e  mov     qword ptr [rbp+30h+var_88], rcx
0x180050132  lea     rcx, [rbp+30h+var_88]
0x180050136  mov     qword ptr [rsp+130h+var_110], rcx
0x18005013b  lea     rdx, qword_1800798C0
0x180050142  mov     rcx, rax
0x180050145  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18005014a  lea     rcx, [rbp+30h+var_A8]
0x18005014e  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180050153  lea     rcx, [rsp+130h+var_C0]
0x180050158  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18005015d  xor     edx, edx
0x18005015f  mov     rcx, [rsp+130h+var_C8]
0x180050164  call    cs:__imp_WwanCloseHandle
0x18005016a  nop
0x18005016b  cmp     [rsp+130h+var_E0], sil
0x180050170  jz      short loc_180050182
0x180050172  mov     [rsp+130h+var_E0], sil
0x180050177  lea     rcx, [rsp+130h+var_F0]
0x18005017c  call    _CCellularSettingHelperWwan__VerifySimPin____2____lambda_1___operator__
0x180050181  nop
0x180050182  xor     eax, eax
0x180050184  mov     rcx, [rbp+30h+var_20]
0x180050188  xor     rcx, rsp; StackCookie
0x18005018b  call    __security_check_cookie
0x180050190  mov     rbx, [rsp+130h+arg_18]
0x180050198  add     rsp, 120h
0x18005019f  pop     rdi
0x1800501a0  pop     rsi
0x1800501a1  pop     rbp
0x1800501a2  retn
```
