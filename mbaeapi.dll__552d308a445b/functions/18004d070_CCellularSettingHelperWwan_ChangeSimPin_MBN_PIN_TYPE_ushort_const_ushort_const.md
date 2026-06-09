# CCellularSettingHelperWwan::ChangeSimPin(MBN_PIN_TYPE,ushort const *,ushort const *)

- ea: `0x18004d070`
- end: `0x18004d4ca`
- name: `?ChangeSimPin@CCellularSettingHelperWwan@@UEAAJW4MBN_PIN_TYPE@@PEBG1@Z`
- size: `1114`
- prototype: `__int64 __fastcall(CCellularSettingHelperWwan *__hidden this, enum MBN_PIN_TYPE, const unsigned __int16 *, const unsigned __int16 *)`
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
- `0x18004cbf8`
- `0x18004d070`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004d2b5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004d2c7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004d2b5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004d2c7`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004d324`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004d3a4`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004d490`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004d324`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004d3a4`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004d490`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004d24a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004d24a`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetInterface` at `0x18004d379`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetInterface` at `0x18004d379`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCellularSettingHelperWwan::ChangeSimPin(
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
  __int64 v15; // rcx
  int v16; // eax
  unsigned int v17; // eax
  const struct _tlgProvider_t *v18; // rax
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // [rsp+20h] [rbp-E0h]
  unsigned int *v22; // [rsp+20h] [rbp-E0h]
  char *v23; // [rsp+28h] [rbp-D8h]
  int *v24; // [rsp+40h] [rbp-C0h] BYREF
  enum MBN_PIN_TYPE *v25; // [rsp+48h] [rbp-B8h]
  char v26; // [rsp+50h] [rbp-B0h]
  enum MBN_PIN_TYPE v27; // [rsp+58h] [rbp-A8h] BYREF
  int v28; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v30[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v31; // [rsp+80h] [rbp-80h]
  char *v32[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v33; // [rsp+98h] [rbp-68h]
  _DWORD v34[2]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v35[4]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v36[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v37[34]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v38[38]; // [rsp+EAh] [rbp-16h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v27 = a2;
  *(_OWORD *)v32 = 0;
  v33 = 0;
  *(_OWORD *)v30 = 0;
  v31 = 0;
  std::vector<unsigned short>::resize(v32);
  std::vector<unsigned short>::resize(v30);
  StringCchPrintfW((unsigned __int16 *)v32[0], (v32[1] - v32[0]) >> 1, L"Enter");
  v23 = v32[0];
  v21 = 244;
  StringCchPrintfW(v30[0], v30[1] - v30[0], L"%S(%d):%s", "CCellularSettingHelperWwan::ChangeSimPin");
  v7 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v7 > 5u )
  {
    *(unsigned __int16 **)v35 = v30[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v7,
      (__int64)byte_180079783,
      v8,
      v9,
      (const unsigned __int16 **)v35);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v30);
  std::vector<unsigned short>::~vector<unsigned short>(v32);
  v28 = 0;
  v24 = &v28;
  v25 = &v27;
  v26 = 1;
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
      (const char *)0x80070057LL,
      v21);
LABEL_12:
    v26 = 0;
    CCellularSettingHelperWwan::ChangeSimPin_::_2_::_lambda_1_::operator()(&v24);
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
      (void *)0x103,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
      (const char *)0x80070057LL,
      (int)"Current pin is too long.",
      v23);
    goto LABEL_12;
  }
  do
    ++v10;
  while ( a4[v10] );
  if ( v10 > 0x11 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x105,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
      (const char *)0x80070057LL,
      (int)"New pin is too long.",
      v23);
    goto LABEL_12;
  }
  v29 = 0;
  v34[0] = 0;
  v13 = WwanOpenHandle(1, 0, v34, &v29);
  if ( v13 )
  {
    v14 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x108,
            (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
            (const char *)v13,
            v21);
    v26 = 0;
    CCellularSettingHelperWwan::ChangeSimPin_::_2_::_lambda_1_::operator()(&v24);
    return v14;
  }
  memset_0(v36, 0, 0x50u);
  v36[0] = v27;
  v36[1] = 3;
  _o_wcscpy_s(v37, 17, a3);
  _o_wcscpy_s(v38, 17, a4);
  *(_OWORD *)v35 = 0;
  v15 = *((_QWORD *)this + 5);
  if ( v15 )
  {
    *(_QWORD *)v35 = *((_QWORD *)this + 4);
    *(_QWORD *)&v35[2] = v15;
    _InterlockedIncrement((volatile signed __int32 *)(v15 + 12));
  }
  v16 = CWwanTranslator::SetAdapterPinActionRequest(v35, (char *)this + 8, v36);
  v14 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x112,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
      (const char *)(unsigned int)v16,
      v21);
    WwanCloseHandle(v29, 0);
    v26 = 0;
    CCellularSettingHelperWwan::ChangeSimPin_::_2_::_lambda_1_::operator()(&v24);
    return v14;
  }
  v34[1] = 0;
  v22 = v36;
  v17 = WwanSetInterface(v29, (char *)this + 8, 0, 80);
  if ( v17 )
  {
    v14 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x116,
            (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
            (const char *)v17,
            (unsigned int)v36);
    WwanCloseHandle(v29, 0);
    v26 = 0;
    CCellularSettingHelperWwan::ChangeSimPin_::_2_::_lambda_1_::operator()(&v24);
    return v14;
  }
  v28 = 1;
  *(_OWORD *)v30 = 0;
  v31 = 0;
  *(_OWORD *)v32 = 0;
  v33 = 0;
  std::vector<unsigned short>::resize(v30);
  std::vector<unsigned short>::resize(v32);
  StringCchPrintfW(v30[0], v30[1] - v30[0], L"Exit");
  LODWORD(v22) = 282;
  StringCchPrintfW(
    (unsigned __int16 *)v32[0],
    (v32[1] - v32[0]) >> 1,
    L"%S(%d):%s",
    "CCellularSettingHelperWwan::ChangeSimPin",
    v22,
    v30[0],
    0,
    0,
    v24,
    v25);
  v18 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v18 > 5u )
  {
    *(char **)v35 = v32[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v18,
      (__int64)&byte_1800796FF,
      v19,
      v20,
      (const unsigned __int16 **)v35);
  }
  std::vector<unsigned short>::~vector<unsigned short>(v32);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v30);
  WwanCloseHandle(v29, 0);
  v26 = 0;
  CCellularSettingHelperWwan::ChangeSimPin_::_2_::_lambda_1_::operator()(&v24);
  return 0;
}

```

## disassembly

```asm
0x18004d070  push    rbp
0x18004d072  push    rbx
0x18004d073  push    rsi
0x18004d074  push    rdi
0x18004d075  push    r14
0x18004d077  lea     rbp, [rsp-20h]
0x18004d07c  sub     rsp, 120h
0x18004d083  mov     rax, cs:__security_cookie
0x18004d08a  xor     rax, rsp
0x18004d08d  mov     [rbp+40h+var_30], rax
0x18004d091  mov     rsi, r9
0x18004d094  mov     rbx, r8
0x18004d097  mov     rdi, rcx
0x18004d09a  mov     [rsp+140h+var_E8], edx
0x18004d09e  xorps   xmm0, xmm0
0x18004d0a1  movdqu  xmmword ptr [rbp+40h+var_B8], xmm0
0x18004d0a6  xor     r14d, r14d
0x18004d0a9  mov     [rbp+40h+var_A8], r14
0x18004d0ad  movdqu  xmmword ptr [rsp+140h+var_D0], xmm0
0x18004d0b3  mov     [rbp+40h+var_C0], r14
0x18004d0b7  lea     rcx, [rbp+40h+var_B8]
0x18004d0bb  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004d0c0  lea     rcx, [rsp+140h+var_D0]
0x18004d0c5  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004d0ca  mov     rdx, [rbp+40h+var_B8+8]
0x18004d0ce  mov     rcx, [rbp+40h+var_B8]; unsigned __int16 *
0x18004d0d2  sub     rdx, rcx
0x18004d0d5  sar     rdx, 1; unsigned __int64
0x18004d0d8  lea     r8, aEnter; "Enter"
0x18004d0df  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004d0e4  mov     rdx, [rsp+140h+var_D0+8]
0x18004d0e9  mov     rcx, [rsp+140h+var_D0]; unsigned __int16 *
0x18004d0ee  sub     rdx, rcx
0x18004d0f1  sar     rdx, 1; unsigned __int64
0x18004d0f4  mov     rax, [rbp+40h+var_B8]
0x18004d0f8  mov     [rsp+140h+var_118], rax; char *
0x18004d0fd  mov     [rsp+140h+var_120], 0F4h
0x18004d105  lea     r9, aCcellularsetti_32; "CCellularSettingHelperWwan::ChangeSimPi"...
0x18004d10c  lea     r8, aSDS; "%S(%d):%s"
0x18004d113  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004d118  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004d11d  mov     ecx, [rax]
0x18004d11f  cmp     ecx, 5
0x18004d122  jbe     short loc_18004D145
0x18004d124  mov     rcx, [rsp+140h+var_D0]
0x18004d129  mov     qword ptr [rbp+40h+var_98], rcx
0x18004d12d  lea     rcx, [rbp+40h+var_98]
0x18004d131  mov     qword ptr [rsp+140h+var_120], rcx; int
0x18004d136  lea     rdx, byte_180079783
0x18004d13d  mov     rcx, rax
0x18004d140  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004d145  lea     rcx, [rsp+140h+var_D0]
0x18004d14a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004d14f  lea     rcx, [rbp+40h+var_B8]
0x18004d153  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004d158  mov     [rsp+140h+var_E0], r14d
0x18004d15d  lea     rax, [rsp+140h+var_E0]
0x18004d162  mov     [rsp+140h+var_100], rax
0x18004d167  lea     rax, [rsp+140h+var_E8]
0x18004d16c  mov     [rsp+140h+var_F8], rax
0x18004d171  mov     [rsp+140h+var_F0], 1
0x18004d176  test    rbx, rbx
0x18004d179  jnz     short loc_18004D199
0x18004d17b  mov     rcx, [rbp+48h]; this
0x18004d17f  mov     r9d, 80070057h; char *
0x18004d185  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004d18c  mov     edx, 101h; void *
0x18004d191  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d196  nop
0x18004d197  jmp     short loc_18004D212
0x18004d199  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004d19d  mov     rcx, rax
0x18004d1a0  inc     rcx
0x18004d1a3  cmp     [rbx+rcx*2], r14w
0x18004d1a8  jnz     short loc_18004D1A0
0x18004d1aa  cmp     rcx, 11h
0x18004d1ae  jbe     short loc_18004D1DA
0x18004d1b0  mov     rcx, [rbp+48h]; this
0x18004d1b4  lea     rax, aCurrentPinIsTo; "Current pin is too long."
0x18004d1bb  mov     qword ptr [rsp+140h+var_120], rax; int
0x18004d1c0  mov     r9d, 80070057h; char *
0x18004d1c6  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004d1cd  mov     edx, 103h; void *
0x18004d1d2  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004d1d7  nop
0x18004d1d8  jmp     short loc_18004D212
0x18004d1da  inc     rax
0x18004d1dd  cmp     [rsi+rax*2], r14w
0x18004d1e2  jnz     short loc_18004D1DA
0x18004d1e4  cmp     rax, 11h
0x18004d1e8  jbe     short loc_18004D233
0x18004d1ea  mov     rcx, [rbp+48h]; this
0x18004d1ee  lea     rax, aNewPinIsTooLon; "New pin is too long."
0x18004d1f5  mov     qword ptr [rsp+140h+var_120], rax; int
0x18004d1fa  mov     r9d, 80070057h; char *
0x18004d200  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004d207  mov     edx, 105h; void *
0x18004d20c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004d211  nop
0x18004d212  cmp     [rsp+140h+var_F0], r14b
0x18004d217  jz      short loc_18004D229
0x18004d219  mov     [rsp+140h+var_F0], r14b
0x18004d21e  lea     rcx, [rsp+140h+var_100]
0x18004d223  call    _CCellularSettingHelperWwan__ChangeSimPin____2____lambda_1___operator__
0x18004d228  nop
0x18004d229  mov     eax, 80070057h
0x18004d22e  jmp     loc_18004D4B0
0x18004d233  mov     [rsp+140h+var_D8], r14
0x18004d238  mov     [rbp+40h+var_A0], r14d
0x18004d23c  lea     r9, [rsp+140h+var_D8]
0x18004d241  lea     r8, [rbp+40h+var_A0]
0x18004d245  xor     edx, edx
0x18004d247  lea     ecx, [rdx+1]
0x18004d24a  call    cs:__imp_WwanOpenHandle
0x18004d250  test    eax, eax
0x18004d252  jz      short loc_18004D28C
0x18004d254  mov     rcx, [rbp+48h]; this
0x18004d258  mov     r9d, eax; char *
0x18004d25b  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004d262  mov     edx, 108h; void *
0x18004d267  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004d26c  mov     ebx, eax
0x18004d26e  cmp     [rsp+140h+var_F0], r14b
0x18004d273  jz      short loc_18004D285
0x18004d275  mov     [rsp+140h+var_F0], r14b
0x18004d27a  lea     rcx, [rsp+140h+var_100]
0x18004d27f  call    _CCellularSettingHelperWwan__ChangeSimPin____2____lambda_1___operator__
0x18004d284  nop
0x18004d285  mov     eax, ebx
0x18004d287  jmp     loc_18004D4B0
0x18004d28c  xor     edx, edx; Val
0x18004d28e  lea     r8d, [rdx+50h]; Size
0x18004d292  lea     rcx, [rbp+40h+var_80]; void *
0x18004d296  call    memset_0
0x18004d29b  mov     eax, [rsp+140h+var_E8]
0x18004d29f  mov     [rbp+40h+var_80], eax
0x18004d2a2  mov     [rbp+40h+var_7C], 3
0x18004d2a9  mov     r8, rbx
0x18004d2ac  mov     edx, 11h
0x18004d2b1  lea     rcx, [rbp+40h+var_78]
0x18004d2b5  call    cs:__imp__o_wcscpy_s
0x18004d2bb  mov     r8, rsi
0x18004d2be  mov     edx, 11h
0x18004d2c3  lea     rcx, [rbp+40h+var_56]
0x18004d2c7  call    cs:__imp__o_wcscpy_s
0x18004d2cd  xorps   xmm0, xmm0
0x18004d2d0  movdqu  xmmword ptr [rbp+40h+var_98], xmm0
0x18004d2d5  mov     rcx, [rdi+28h]
0x18004d2d9  test    rcx, rcx
0x18004d2dc  jz      short loc_18004D2EE
0x18004d2de  mov     rax, [rdi+20h]
0x18004d2e2  mov     qword ptr [rbp+40h+var_98], rax
0x18004d2e6  mov     qword ptr [rbp+40h+var_98+8], rcx
0x18004d2ea  lock inc dword ptr [rcx+0Ch]
0x18004d2ee  lea     r8, [rbp+40h+var_80]
0x18004d2f2  lea     rdx, [rdi+8]
0x18004d2f6  lea     rcx, [rbp+40h+var_98]
0x18004d2fa  call    ?SetAdapterPinActionRequest@CWwanTranslator@@SAJV?$weak_ptr@VCWwanTranslator@@@std@@AEBU_GUID@@AEAU_WWAN_PIN_ACTION@@@Z; CWwanTranslator::SetAdapterPinActionRequest(std::weak_ptr<CWwanTranslator>,_GUID const &,_WWAN_PIN_ACTION &)
0x18004d2ff  mov     ebx, eax
0x18004d301  test    eax, eax
0x18004d303  jns     short loc_18004D347
0x18004d305  mov     rcx, [rbp+48h]; this
0x18004d309  mov     r9d, eax; char *
0x18004d30c  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004d313  mov     edx, 112h; void *
0x18004d318  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d31d  xor     edx, edx
0x18004d31f  mov     rcx, [rsp+140h+var_D8]
0x18004d324  call    cs:__imp_WwanCloseHandle
0x18004d32a  nop
0x18004d32b  cmp     [rsp+140h+var_F0], r14b
0x18004d330  jz      short loc_18004D342
0x18004d332  mov     [rsp+140h+var_F0], r14b
0x18004d337  lea     rcx, [rsp+140h+var_100]
0x18004d33c  call    _CCellularSettingHelperWwan__ChangeSimPin____2____lambda_1___operator__
0x18004d341  nop
0x18004d342  jmp     loc_18004D285
0x18004d347  mov     [rbp+40h+var_9C], r14d
0x18004d34b  mov     [rsp+140h+var_108], r14
0x18004d350  mov     [rsp+140h+var_110], r14
0x18004d355  lea     rax, [rbp+40h+var_9C]
0x18004d359  mov     [rsp+140h+var_118], rax
0x18004d35e  lea     rax, [rbp+40h+var_80]
0x18004d362  mov     qword ptr [rsp+140h+var_120], rax; unsigned int
0x18004d367  mov     r9d, 50h ; 'P'
0x18004d36d  xor     r8d, r8d
0x18004d370  lea     rdx, [rdi+8]
0x18004d374  mov     rcx, [rsp+140h+var_D8]
0x18004d379  call    cs:__imp_WwanSetInterface
0x18004d37f  test    eax, eax
0x18004d381  jz      short loc_18004D3C7
0x18004d383  mov     rcx, [rbp+48h]; this
0x18004d387  mov     r9d, eax; char *
0x18004d38a  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004d391  mov     edx, 116h; void *
0x18004d396  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004d39b  mov     ebx, eax
0x18004d39d  xor     edx, edx
0x18004d39f  mov     rcx, [rsp+140h+var_D8]
0x18004d3a4  call    cs:__imp_WwanCloseHandle
0x18004d3aa  nop
0x18004d3ab  cmp     [rsp+140h+var_F0], r14b
0x18004d3b0  jz      short loc_18004D3C2
0x18004d3b2  mov     [rsp+140h+var_F0], r14b
0x18004d3b7  lea     rcx, [rsp+140h+var_100]
0x18004d3bc  call    _CCellularSettingHelperWwan__ChangeSimPin____2____lambda_1___operator__
0x18004d3c1  nop
0x18004d3c2  jmp     loc_18004D285
0x18004d3c7  mov     [rsp+140h+var_E0], 1
0x18004d3cf  xorps   xmm0, xmm0
0x18004d3d2  movdqu  xmmword ptr [rsp+140h+var_D0], xmm0
0x18004d3d8  mov     [rbp+40h+var_C0], r14
0x18004d3dc  xorps   xmm1, xmm1
0x18004d3df  movdqu  xmmword ptr [rbp+40h+var_B8], xmm1
0x18004d3e4  mov     [rbp+40h+var_A8], r14
0x18004d3e8  lea     rcx, [rsp+140h+var_D0]
0x18004d3ed  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004d3f2  lea     rcx, [rbp+40h+var_B8]
0x18004d3f6  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004d3fb  mov     rdx, [rsp+140h+var_D0+8]
0x18004d400  mov     rcx, [rsp+140h+var_D0]; unsigned __int16 *
0x18004d405  sub     rdx, rcx
0x18004d408  sar     rdx, 1; unsigned __int64
0x18004d40b  lea     r8, aExit; "Exit"
0x18004d412  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004d417  mov     rdx, [rbp+40h+var_B8+8]
0x18004d41b  mov     rcx, [rbp+40h+var_B8]; unsigned __int16 *
0x18004d41f  sub     rdx, rcx
0x18004d422  sar     rdx, 1; unsigned __int64
0x18004d425  mov     rax, [rsp+140h+var_D0]
0x18004d42a  mov     [rsp+140h+var_118], rax
0x18004d42f  mov     [rsp+140h+var_120], 11Ah
0x18004d437  lea     r9, aCcellularsetti_32; "CCellularSettingHelperWwan::ChangeSimPi"...
0x18004d43e  lea     r8, aSDS; "%S(%d):%s"
0x18004d445  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004d44a  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004d44f  mov     ecx, [rax]
0x18004d451  cmp     ecx, 5
0x18004d454  jbe     short loc_18004D476
0x18004d456  mov     rcx, [rbp+40h+var_B8]
0x18004d45a  mov     qword ptr [rbp+40h+var_98], rcx
0x18004d45e  lea     rcx, [rbp+40h+var_98]
0x18004d462  mov     qword ptr [rsp+140h+var_120], rcx
0x18004d467  lea     rdx, byte_1800796FF
0x18004d46e  mov     rcx, rax
0x18004d471  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004d476  lea     rcx, [rbp+40h+var_B8]
0x18004d47a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004d47f  lea     rcx, [rsp+140h+var_D0]
0x18004d484  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004d489  xor     edx, edx
0x18004d48b  mov     rcx, [rsp+140h+var_D8]
0x18004d490  call    cs:__imp_WwanCloseHandle
0x18004d496  nop
0x18004d497  cmp     [rsp+140h+var_F0], r14b
0x18004d49c  jz      short loc_18004D4AE
0x18004d49e  mov     [rsp+140h+var_F0], r14b
0x18004d4a3  lea     rcx, [rsp+140h+var_100]
0x18004d4a8  call    _CCellularSettingHelperWwan__ChangeSimPin____2____lambda_1___operator__
0x18004d4ad  nop
0x18004d4ae  xor     eax, eax
0x18004d4b0  mov     rcx, [rbp+40h+var_30]
0x18004d4b4  xor     rcx, rsp; StackCookie
0x18004d4b7  call    __security_check_cookie
0x18004d4bc  add     rsp, 120h
0x18004d4c3  pop     r14
0x18004d4c5  pop     rdi
0x18004d4c6  pop     rsi
0x18004d4c7  pop     rbx
0x18004d4c8  pop     rbp
0x18004d4c9  retn
```
