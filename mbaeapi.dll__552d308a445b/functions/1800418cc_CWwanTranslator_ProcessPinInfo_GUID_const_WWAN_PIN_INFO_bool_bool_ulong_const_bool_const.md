# CWwanTranslator::_ProcessPinInfo(_GUID const &,_WWAN_PIN_INFO *,bool &,bool &,ulong const &,bool const &)

- ea: `0x1800418cc`
- end: `0x180041e68`
- name: `?_ProcessPinInfo@CWwanTranslator@@AEAAJAEBU_GUID@@PEAU_WWAN_PIN_INFO@@AEA_N2AEBKAEB_N@Z`
- size: `1436`
- prototype: `int __fastcall(CWwanTranslator *this, const struct _GUID *, struct _WWAN_PIN_INFO *, bool *, bool *, unsigned int *, bool *)`
- caller_count: `3`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x18003812c`
- `0x18004162c`
- `0x18004177c`

## callees

- `0x18000178c`
- `0x1800024e0`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x18001adf8`
- `0x18001dd10`
- `0x18003994c`
- `0x18003a8e0`
- `0x18003ab44`
- `0x18003ada4`
- `0x18003df60`
- `0x18003e1c0`
- `0x18003e20c`
- `0x1800418cc`
- `0x18005c010`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180041e36`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180041e36`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180041ad1`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180041b79`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180041e26`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180041ad1`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180041b79`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180041e26`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180041a16`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180041a16`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180041a9c`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180041a9c`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
int __fastcall CWwanTranslator::_ProcessPinInfo(
        CWwanTranslator *this,
        const struct _GUID *a2,
        struct _WWAN_PIN_INFO *a3,
        bool *a4,
        bool *a5,
        unsigned int *a6,
        bool *a7)
{
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // ebx
  unsigned int v15; // eax
  unsigned int Interface; // eax
  CWwanTranslator *v18; // rcx
  __int64 v19; // r14
  const char *v20; // r9
  CWwanTranslator *v21; // rcx
  bool v22; // r8
  int v23; // esi
  bool v24; // r8
  __int64 v25; // rdx
  bool v26; // r8
  _QWORD *v27; // rdx
  bool v28; // r8
  _QWORD *v29; // rdx
  _QWORD *v30; // rdx
  const struct _tlgProvider_t *v31; // rax
  __int64 v32; // r8
  __int64 v33; // r9
  unsigned int v34; // [rsp+20h] [rbp-E0h]
  bool *v35; // [rsp+20h] [rbp-E0h]
  const char *v36; // [rsp+28h] [rbp-D8h]
  __int64 v37; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v38; // [rsp+48h] [rbp-B8h] BYREF
  char *v39[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v40; // [rsp+60h] [rbp-A0h]
  int v41; // [rsp+68h] [rbp-98h] BYREF
  int v42; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v43; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v44[2]; // [rsp+78h] [rbp-88h] BYREF
  char v45; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v46[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v47; // [rsp+98h] [rbp-68h]
  unsigned __int16 *v48[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v49; // [rsp+B0h] [rbp-50h]
  int v50; // [rsp+B8h] [rbp-48h]
  _DWORD v51[4]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v52; // [rsp+D0h] [rbp-30h]
  int v53; // [rsp+D8h] [rbp-28h]
  _DWORD v54[8]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v55[7]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD *v56; // [rsp+138h] [rbp+38h]
  _QWORD v57[7]; // [rsp+140h] [rbp+40h] BYREF
  _QWORD *v58; // [rsp+178h] [rbp+78h]
  _QWORD v59[7]; // [rsp+180h] [rbp+80h] BYREF
  _QWORD *v60; // [rsp+1B8h] [rbp+B8h]
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  *(_OWORD *)v39 = 0;
  v40 = 0;
  *(_OWORD *)v46 = 0;
  v47 = 0;
  std::vector<unsigned short>::resize(v39);
  std::vector<unsigned short>::resize(v46);
  StringCchPrintfW((unsigned __int16 *)v39[0], (v39[1] - v39[0]) >> 1, L"Enter");
  v36 = v39[0];
  v34 = 1659;
  StringCchPrintfW(v46[0], v46[1] - v46[0], L"%S(%d):%s", "CWwanTranslator::_ProcessPinInfo");
  v11 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v11 > 5u )
  {
    *(unsigned __int16 **)v44 = v46[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v11,
      (__int64)byte_180076FC5,
      v12,
      v13,
      (const unsigned __int16 **)v44);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v46);
  std::vector<unsigned short>::~vector<unsigned short>(v39);
  if ( a3 )
  {
    v38 = 0;
    v41 = 0;
    v15 = WwanOpenHandle(1, 0, &v41, &v38);
    if ( v15 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x680,
               (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
               (const char *)v15,
               v34);
    *(_QWORD *)v44 = &v38;
    v45 = 1;
    v37 = 0;
    v43 = 0;
    v42 = 0;
    v46[0] = (unsigned __int16 *)&v37;
    LOBYTE(v46[1]) = 1;
    Interface = WwanQueryInterface(v38, a2, 7);
    v18 = retaddr;
    if ( Interface )
    {
      v14 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x68C,
              (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
              (const char *)Interface,
              (unsigned int)&v43);
      if ( v37 )
        WwanFreeMemory(v37);
LABEL_40:
      WwanCloseHandle(v38, 0);
      return v14;
    }
    v19 = v37;
    v20 = (const char *)*(unsigned int *)(v37 + 1216);
    if ( (_DWORD)v20 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x68F,
        (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
        v20,
        (unsigned int)&v43);
    memset(v54, 0, 28);
    CWwanTranslator::_FillPinState(
      v18,
      (struct _WWAN_PIN_LIST *)(v19 + 1056),
      a3,
      a6,
      a7,
      (struct CellularSettingsPinState *)v54);
    if ( *(_DWORD *)a3 == 2 )
    {
      v23 = CWwanTranslator::SetPin1PreviousState(this, a2, *((unsigned int *)a3 + 1));
      if ( v23 < 0 )
      {
        v25 = 1685;
LABEL_15:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v25,
          (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
          (const char *)(unsigned int)v23,
          (int)v35);
        if ( v37 )
          WwanFreeMemory(v37);
        v14 = v23;
        goto LABEL_40;
      }
      CWwanTranslator::SetPin1ReportedByAdapterId(this, a2, v24);
    }
    else if ( *(_DWORD *)a3 == 3 )
    {
      CWwanTranslator::SetPin2ReportedByAdapterId(this, a2, v22);
    }
    if ( !*a4 && v54[0] != 2 )
    {
      v51[2] = 0;
      v52 = 0;
      v53 = 0;
      v51[0] = 2;
      CWwanTranslator::_FillPinStateBasic(
        v21,
        (struct _WWAN_PIN_DESC *)(v19 + 1056),
        (struct CellularSettingsPinState *)v51);
      v51[3] = 0;
      v51[1] = 0;
      v23 = CWwanTranslator::SetPin1PreviousState(this, a2, 0);
      if ( v23 < 0 )
      {
        v25 = 1708;
        goto LABEL_15;
      }
      v55[0] = off_18005F068;
      v55[1] = this;
      v55[2] = a2;
      v55[3] = v51;
      v56 = v55;
      CWwanTranslator::SafelyNotify(this, v55);
      if ( v56 )
      {
        v27 = v55;
        LOBYTE(v27) = v56 != v55;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v56 + 32LL))(v56, v27);
      }
      CWwanTranslator::SetPin1ReportedByAdapterId(this, a2, v26);
    }
    if ( !*a5 && v54[0] != 3 )
    {
      LODWORD(v48[1]) = 0;
      v49 = 0;
      v50 = 0;
      LODWORD(v48[0]) = 3;
      CWwanTranslator::_FillPinStateBasic(
        v21,
        (struct _WWAN_PIN_DESC *)(v19 + 1072),
        (struct CellularSettingsPinState *)v48);
      HIDWORD(v48[1]) = 0;
      HIDWORD(v48[0]) = 0;
      v57[0] = off_18005EFD8;
      v57[1] = this;
      v57[2] = a2;
      v57[3] = v48;
      v58 = v57;
      CWwanTranslator::SafelyNotify(this, v57);
      if ( v58 )
      {
        v29 = v57;
        LOBYTE(v29) = v58 != v57;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v58 + 32LL))(v58, v29);
      }
      CWwanTranslator::SetPin2ReportedByAdapterId(this, a2, v28);
    }
    v59[0] = off_18005F008;
    v59[1] = this;
    v59[2] = a2;
    v59[3] = v54;
    v60 = v59;
    CWwanTranslator::SafelyNotify(this, v59);
    if ( v60 )
    {
      v30 = v59;
      LOBYTE(v30) = v60 != v59;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v60 + 32LL))(v60, v30);
    }
    *(_OWORD *)v48 = 0;
    v49 = 0;
    *(_OWORD *)v39 = 0;
    v40 = 0;
    std::vector<unsigned short>::resize(v48);
    std::vector<unsigned short>::resize(v39);
    StringCchPrintfW(v48[0], v48[1] - v48[0], L"Exit");
    LODWORD(v35) = 1736;
    StringCchPrintfW(
      (unsigned __int16 *)v39[0],
      (v39[1] - v39[0]) >> 1,
      L"%S(%d):%s",
      "CWwanTranslator::_ProcessPinInfo",
      v35,
      v48[0],
      &v42,
      0);
    v31 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v31 > 5u )
    {
      *(char **)v44 = v39[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v31,
        (__int64)&byte_180076F7F,
        v32,
        v33,
        (const unsigned __int16 **)v44);
    }
    std::vector<unsigned short>::~vector<unsigned short>(v39);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v48);
    if ( v37 )
      WwanFreeMemory(v37);
    v14 = 0;
    goto LABEL_40;
  }
  v14 = -2147467259;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x67C,
    (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
    (const char *)0x80004005LL,
    (int)"WwanQueryInterface returns null pinInfo",
    v36);
  return v14;
}

```

## disassembly

```asm
0x1800418cc  mov     [rsp-8+arg_18], rbx
0x1800418d1  push    rbp
0x1800418d2  push    rsi
0x1800418d3  push    rdi
0x1800418d4  push    r12
0x1800418d6  push    r13
0x1800418d8  push    r14
0x1800418da  push    r15
0x1800418dc  lea     rbp, [rsp-0D0h]
0x1800418e4  sub     rsp, 1D0h
0x1800418eb  mov     rax, cs:__security_cookie
0x1800418f2  xor     rax, rsp
0x1800418f5  mov     [rbp+100h+var_40], rax
0x1800418fc  mov     r12, r9
0x1800418ff  mov     rsi, r8
0x180041902  mov     rdi, rdx
0x180041905  mov     rbx, rcx
0x180041908  xorps   xmm0, xmm0
0x18004190b  movdqu  xmmword ptr [rsp+200h+var_1B0], xmm0
0x180041911  xor     r13d, r13d
0x180041914  mov     [rsp+200h+var_1A0], r13
0x180041919  movdqu  xmmword ptr [rbp+100h+var_178], xmm0
0x18004191e  mov     [rbp+100h+var_168], r13
0x180041922  lea     rcx, [rsp+200h+var_1B0]
0x180041927  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004192c  lea     rcx, [rbp+100h+var_178]
0x180041930  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180041935  mov     rdx, [rsp+200h+var_1B0+8]
0x18004193a  mov     rcx, [rsp+200h+var_1B0]; unsigned __int16 *
0x18004193f  sub     rdx, rcx
0x180041942  sar     rdx, 1; unsigned __int64
0x180041945  lea     r8, aEnter; "Enter"
0x18004194c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180041951  mov     rdx, [rbp+100h+var_178+8]
0x180041955  mov     rcx, [rbp+100h+var_178]; unsigned __int16 *
0x180041959  sub     rdx, rcx
0x18004195c  sar     rdx, 1; unsigned __int64
0x18004195f  mov     rax, [rsp+200h+var_1B0]
0x180041964  mov     [rsp+200h+var_1D8], rax; char *
0x180041969  mov     dword ptr [rsp+200h+var_1E0], 67Bh
0x180041971  lea     r9, aCwwantranslato_68; "CWwanTranslator::_ProcessPinInfo"
0x180041978  lea     r8, aSDS; "%S(%d):%s"
0x18004197f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180041984  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180041989  mov     ecx, [rax]
0x18004198b  cmp     ecx, 5
0x18004198e  jbe     short loc_1800419B3
0x180041990  mov     rcx, [rbp+100h+var_178]
0x180041994  mov     qword ptr [rsp+200h+var_188], rcx
0x180041999  lea     rcx, [rsp+200h+var_188]
0x18004199e  mov     [rsp+200h+var_1E0], rcx; unsigned int
0x1800419a3  lea     rdx, byte_180076FC5
0x1800419aa  mov     rcx, rax
0x1800419ad  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800419b2  nop
0x1800419b3  lea     rcx, [rbp+100h+var_178]
0x1800419b7  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800419bc  nop
0x1800419bd  lea     rcx, [rsp+200h+var_1B0]
0x1800419c2  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800419c7  test    rsi, rsi
0x1800419ca  jnz     short loc_1800419FD
0x1800419cc  mov     rcx, [rbp+108h]; this
0x1800419d3  lea     rax, aWwanqueryinter_1; "WwanQueryInterface returns null pinInfo"
0x1800419da  mov     [rsp+200h+var_1E0], rax; int
0x1800419df  mov     ebx, 80004005h
0x1800419e4  mov     r9d, ebx; char *
0x1800419e7  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x1800419ee  mov     edx, 67Ch; void *
0x1800419f3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800419f8  jmp     loc_180041E3C
0x1800419fd  mov     [rsp+200h+var_1B8], r13
0x180041a02  mov     [rsp+200h+var_198], r13d
0x180041a07  lea     r9, [rsp+200h+var_1B8]
0x180041a0c  lea     r8, [rsp+200h+var_198]
0x180041a11  xor     edx, edx
0x180041a13  lea     ecx, [rdx+1]
0x180041a16  call    cs:__imp_WwanOpenHandle
0x180041a1c  test    eax, eax
0x180041a1e  jz      short loc_180041A40
0x180041a20  mov     rcx, [rbp+108h]; this
0x180041a27  mov     r9d, eax; char *
0x180041a2a  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180041a31  mov     edx, 680h; void *
0x180041a36  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180041a3b  jmp     loc_180041E3E
0x180041a40  lea     rax, [rsp+200h+var_1B8]
0x180041a45  mov     qword ptr [rsp+200h+var_188], rax
0x180041a4a  mov     [rbp+100h+var_180], 1
0x180041a4e  mov     [rsp+200h+var_1C0], r13
0x180041a53  mov     [rsp+200h+var_190], r13d
0x180041a58  mov     [rsp+200h+var_194], r13d
0x180041a5d  lea     rax, [rsp+200h+var_1C0]
0x180041a62  mov     [rbp+100h+var_178], rax
0x180041a66  mov     byte ptr [rbp+100h+var_178+8], 1
0x180041a6a  mov     [rsp+200h+var_1C8], r13
0x180041a6f  lea     rax, [rsp+200h+var_194]
0x180041a74  mov     [rsp+200h+var_1D0], rax
0x180041a79  lea     rax, [rsp+200h+var_1C0]
0x180041a7e  mov     [rsp+200h+var_1D8], rax
0x180041a83  lea     rax, [rsp+200h+var_190]
0x180041a88  mov     [rsp+200h+var_1E0], rax; unsigned int
0x180041a8d  xor     r9d, r9d
0x180041a90  lea     r8d, [r9+7]
0x180041a94  mov     rdx, rdi
0x180041a97  mov     rcx, [rsp+200h+var_1B8]
0x180041a9c  call    cs:__imp_WwanQueryInterface
0x180041aa2  mov     rcx, [rbp+108h]; this
0x180041aa9  test    eax, eax
0x180041aab  jz      short loc_180041ADC
0x180041aad  mov     r9d, eax; char *
0x180041ab0  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180041ab7  mov     edx, 68Ch; void *
0x180041abc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180041ac1  mov     ebx, eax
0x180041ac3  mov     rcx, [rsp+200h+var_1C0]
0x180041ac8  test    rcx, rcx
0x180041acb  jz      loc_180041E2F
0x180041ad1  call    cs:__imp_WwanFreeMemory
0x180041ad7  jmp     loc_180041E2F
0x180041adc  mov     r14, [rsp+200h+var_1C0]
0x180041ae1  mov     r9d, [r14+4C0h]; char *
0x180041ae8  test    r9d, r9d
0x180041aeb  jz      short loc_180041AFE
0x180041aed  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180041af4  mov     edx, 68Fh; void *
0x180041af9  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180041afe  xorps   xmm0, xmm0
0x180041b01  movups  xmmword ptr [rbp+100h+var_120], xmm0
0x180041b05  movups  xmmword ptr [rbp+100h+var_120+0Ch], xmm0
0x180041b09  lea     r15, [r14+420h]
0x180041b10  lea     rax, [rbp+100h+var_120]
0x180041b14  mov     [rsp+200h+var_1D8], rax; struct CellularSettingsPinState *
0x180041b19  mov     rax, [rbp+100h+arg_30]
0x180041b20  mov     [rsp+200h+var_1E0], rax; int
0x180041b25  mov     r9, [rbp+100h+arg_28]; unsigned int *
0x180041b2c  mov     r8, rsi; struct _WWAN_PIN_INFO *
0x180041b2f  mov     rdx, r15; struct _WWAN_PIN_LIST *
0x180041b32  call    ?_FillPinState@CWwanTranslator@@AEAAJAEAU_WWAN_PIN_LIST@@PEAU_WWAN_PIN_INFO@@AEBKAEB_NAEAUCellularSettingsPinState@@@Z; CWwanTranslator::_FillPinState(_WWAN_PIN_LIST &,_WWAN_PIN_INFO *,ulong const &,bool const &,CellularSettingsPinState &)
0x180041b37  mov     eax, [rsi]
0x180041b39  cmp     eax, 2
0x180041b3c  jnz     short loc_180041B93
0x180041b3e  mov     r8d, [rsi+4]
0x180041b42  mov     rdx, rdi
0x180041b45  mov     rcx, rbx
0x180041b48  call    ?SetPin1PreviousState@CWwanTranslator@@AEAAJAEBU_GUID@@W4_WWAN_PIN_STATE@@@Z; CWwanTranslator::SetPin1PreviousState(_GUID const &,_WWAN_PIN_STATE)
0x180041b4d  mov     esi, eax
0x180041b4f  test    eax, eax
0x180041b51  jns     short loc_180041B86
0x180041b53  mov     edx, 695h; void *
0x180041b58  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180041b5f  mov     r9d, esi; char *
0x180041b62  mov     rcx, [rbp+108h]; this
0x180041b69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041b6e  nop
0x180041b6f  mov     rcx, [rsp+200h+var_1C0]
0x180041b74  test    rcx, rcx
0x180041b77  jz      short loc_180041B7F
0x180041b79  call    cs:__imp_WwanFreeMemory
0x180041b7f  mov     ebx, esi
0x180041b81  jmp     loc_180041E2F
0x180041b86  mov     rdx, rdi; struct _GUID *
0x180041b89  mov     rcx, rbx; this
0x180041b8c  call    ?SetPin1ReportedByAdapterId@CWwanTranslator@@AEAAJAEBU_GUID@@_N@Z; CWwanTranslator::SetPin1ReportedByAdapterId(_GUID const &,bool)
0x180041b91  jmp     short loc_180041BA3
0x180041b93  cmp     eax, 3
0x180041b96  jnz     short loc_180041BA3
0x180041b98  mov     rdx, rdi; struct _GUID *
0x180041b9b  mov     rcx, rbx; this
0x180041b9e  call    ?SetPin2ReportedByAdapterId@CWwanTranslator@@AEAAJAEBU_GUID@@_N@Z; CWwanTranslator::SetPin2ReportedByAdapterId(_GUID const &,bool)
0x180041ba3  cmp     [r12], r13b
0x180041ba7  jnz     loc_180041C56
0x180041bad  cmp     [rbp+100h+var_120], 2
0x180041bb1  jz      loc_180041C56
0x180041bb7  mov     [rbp+100h+var_138], r13d
0x180041bbb  mov     [rbp+100h+var_130], r13
0x180041bbf  mov     [rbp+100h+var_128], r13d
0x180041bc3  mov     [rbp+100h+var_140], 2
0x180041bca  lea     r8, [rbp+100h+var_140]; struct CellularSettingsPinState *
0x180041bce  mov     rdx, r15; struct _WWAN_PIN_DESC *
0x180041bd1  call    ?_FillPinStateBasic@CWwanTranslator@@AEAAXAEAU_WWAN_PIN_DESC@@AEAUCellularSettingsPinState@@@Z; CWwanTranslator::_FillPinStateBasic(_WWAN_PIN_DESC &,CellularSettingsPinState &)
0x180041bd6  mov     [rbp+100h+var_134], r13d
0x180041bda  mov     [rbp+100h+var_13C], r13d
0x180041bde  xor     r8d, r8d
0x180041be1  mov     rdx, rdi
0x180041be4  mov     rcx, rbx
0x180041be7  call    ?SetPin1PreviousState@CWwanTranslator@@AEAAJAEBU_GUID@@W4_WWAN_PIN_STATE@@@Z; CWwanTranslator::SetPin1PreviousState(_GUID const &,_WWAN_PIN_STATE)
0x180041bec  mov     esi, eax
0x180041bee  test    eax, eax
0x180041bf0  jns     short loc_180041BFC
0x180041bf2  mov     edx, 6ACh
0x180041bf7  jmp     loc_180041B58
0x180041bfc  lea     rax, off_18005F068
0x180041c03  mov     [rbp+100h+var_100], rax
0x180041c07  mov     [rbp+100h+var_F8], rbx
0x180041c0b  mov     [rbp+100h+var_F0], rdi
0x180041c0f  lea     rax, [rbp+100h+var_140]
0x180041c13  mov     [rbp+100h+var_E8], rax
0x180041c17  lea     rax, [rbp+100h+var_100]
0x180041c1b  mov     [rbp+100h+var_C8], rax
0x180041c1f  lea     rdx, [rbp+100h+var_100]
0x180041c23  mov     rcx, rbx
0x180041c26  call    ?SafelyNotify@CWwanTranslator@@AEAAJ$$QEAV?$function@$$A6AXXZ@std@@@Z; CWwanTranslator::SafelyNotify(std::function<void (void)> &&)
0x180041c2b  nop
0x180041c2c  mov     rcx, [rbp+100h+var_C8]
0x180041c30  test    rcx, rcx
0x180041c33  jz      short loc_180041C4B
0x180041c35  mov     rax, [rcx]
0x180041c38  lea     rdx, [rbp+100h+var_100]
0x180041c3c  cmp     rcx, rdx
0x180041c3f  setnz   dl
0x180041c42  mov     rax, [rax+20h]
0x180041c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c4b  mov     rdx, rdi; struct _GUID *
0x180041c4e  mov     rcx, rbx; this
0x180041c51  call    ?SetPin1ReportedByAdapterId@CWwanTranslator@@AEAAJAEBU_GUID@@_N@Z; CWwanTranslator::SetPin1ReportedByAdapterId(_GUID const &,bool)
0x180041c56  mov     rax, [rbp+100h+arg_20]
0x180041c5d  cmp     [rax], r13b
0x180041c60  jnz     loc_180041CF5
0x180041c66  cmp     [rbp+100h+var_120], 3
0x180041c6a  jz      loc_180041CF5
0x180041c70  mov     dword ptr [rbp+100h+var_160+8], r13d
0x180041c74  mov     [rbp+100h+var_150], r13
0x180041c78  mov     [rbp+100h+var_148], r13d
0x180041c7c  mov     dword ptr [rbp+100h+var_160], 3
0x180041c83  lea     rdx, [r14+430h]; struct _WWAN_PIN_DESC *
0x180041c8a  lea     r8, [rbp+100h+var_160]; struct CellularSettingsPinState *
0x180041c8e  call    ?_FillPinStateBasic@CWwanTranslator@@AEAAXAEAU_WWAN_PIN_DESC@@AEAUCellularSettingsPinState@@@Z; CWwanTranslator::_FillPinStateBasic(_WWAN_PIN_DESC &,CellularSettingsPinState &)
0x180041c93  mov     dword ptr [rbp+100h+var_160+0Ch], r13d
0x180041c97  mov     dword ptr [rbp+100h+var_160+4], r13d
0x180041c9b  lea     rax, off_18005EFD8
0x180041ca2  mov     [rbp+100h+var_C0], rax
0x180041ca6  mov     [rbp+100h+var_B8], rbx
0x180041caa  mov     [rbp+100h+var_B0], rdi
0x180041cae  lea     rax, [rbp+100h+var_160]
0x180041cb2  mov     [rbp+100h+var_A8], rax
0x180041cb6  lea     rax, [rbp+100h+var_C0]
0x180041cba  mov     [rbp+100h+var_88], rax
0x180041cbe  lea     rdx, [rbp+100h+var_C0]
0x180041cc2  mov     rcx, rbx
0x180041cc5  call    ?SafelyNotify@CWwanTranslator@@AEAAJ$$QEAV?$function@$$A6AXXZ@std@@@Z; CWwanTranslator::SafelyNotify(std::function<void (void)> &&)
0x180041cca  nop
0x180041ccb  mov     rcx, [rbp+100h+var_88]
0x180041ccf  test    rcx, rcx
0x180041cd2  jz      short loc_180041CEA
0x180041cd4  mov     rax, [rcx]
0x180041cd7  lea     rdx, [rbp+100h+var_C0]
0x180041cdb  cmp     rcx, rdx
0x180041cde  setnz   dl
0x180041ce1  mov     rax, [rax+20h]
0x180041ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041cea  mov     rdx, rdi; struct _GUID *
0x180041ced  mov     rcx, rbx; this
0x180041cf0  call    ?SetPin2ReportedByAdapterId@CWwanTranslator@@AEAAJAEBU_GUID@@_N@Z; CWwanTranslator::SetPin2ReportedByAdapterId(_GUID const &,bool)
0x180041cf5  lea     rax, off_18005F008
0x180041cfc  mov     [rbp+100h+var_80], rax
0x180041d03  mov     [rbp+100h+var_78], rbx
0x180041d0a  mov     [rbp+100h+var_70], rdi
0x180041d11  lea     rax, [rbp+100h+var_120]
0x180041d15  mov     [rbp+100h+var_68], rax
0x180041d1c  lea     rax, [rbp+100h+var_80]
0x180041d23  mov     [rbp+100h+var_48], rax
0x180041d2a  lea     rdx, [rbp+100h+var_80]
0x180041d31  mov     rcx, rbx
0x180041d34  call    ?SafelyNotify@CWwanTranslator@@AEAAJ$$QEAV?$function@$$A6AXXZ@std@@@Z; CWwanTranslator::SafelyNotify(std::function<void (void)> &&)
0x180041d39  nop
0x180041d3a  mov     rcx, [rbp+100h+var_48]
0x180041d41  test    rcx, rcx
0x180041d44  jz      short loc_180041D5F
0x180041d46  mov     rax, [rcx]
0x180041d49  lea     rdx, [rbp+100h+var_80]
0x180041d50  cmp     rcx, rdx
0x180041d53  setnz   dl
0x180041d56  mov     rax, [rax+20h]
0x180041d5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041d5f  xorps   xmm0, xmm0
0x180041d62  movdqu  xmmword ptr [rbp+100h+var_160], xmm0
0x180041d67  mov     [rbp+100h+var_150], r13
0x180041d6b  movdqu  xmmword ptr [rsp+200h+var_1B0], xmm0
0x180041d71  mov     [rsp+200h+var_1A0], r13
0x180041d76  lea     rcx, [rbp+100h+var_160]
0x180041d7a  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180041d7f  lea     rcx, [rsp+200h+var_1B0]
0x180041d84  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180041d89  mov     rdx, [rbp+100h+var_160+8]
0x180041d8d  mov     rcx, [rbp+100h+var_160]; unsigned __int16 *
0x180041d91  sub     rdx, rcx
0x180041d94  sar     rdx, 1; unsigned __int64
0x180041d97  lea     r8, aExit; "Exit"
0x180041d9e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180041da3  mov     rdx, [rsp+200h+var_1B0+8]
0x180041da8  mov     rcx, [rsp+200h+var_1B0]; unsigned __int16 *
0x180041dad  sub     rdx, rcx
0x180041db0  sar     rdx, 1; unsigned __int64
0x180041db3  mov     rax, [rbp+100h+var_160]
0x180041db7  mov     [rsp+200h+var_1D8], rax
0x180041dbc  mov     dword ptr [rsp+200h+var_1E0], 6C8h
0x180041dc4  lea     r9, aCwwantranslato_68; "CWwanTranslator::_ProcessPinInfo"
0x180041dcb  lea     r8, aSDS; "%S(%d):%s"
0x180041dd2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
  ... truncated ...
```
