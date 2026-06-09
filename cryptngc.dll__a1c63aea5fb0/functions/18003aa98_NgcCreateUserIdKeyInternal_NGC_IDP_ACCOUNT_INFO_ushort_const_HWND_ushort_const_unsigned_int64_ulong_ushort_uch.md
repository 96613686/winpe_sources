# NgcCreateUserIdKeyInternal(_NGC_IDP_ACCOUNT_INFO *,ushort const *,HWND__ *,ushort const *,unsigned __int64,ulong,ushort * *,uchar * *,ulong *,unsigned __int64 *)

- ea: `0x18003aa98`
- end: `0x18003ae73`
- name: `?NgcCreateUserIdKeyInternal@@YAJPEAU_NGC_IDP_ACCOUNT_INFO@@PEBGPEAUHWND__@@1_KKPEAPEAGPEAPEAEPEAKPEA_K@Z`
- size: `987`
- prototype: `__int64 __fastcall(struct _NGC_IDP_ACCOUNT_INFO *, const unsigned __int16 *, HWND, const unsigned __int16 *, unsigned __int64, unsigned int, unsigned __int16 **, unsigned __int8 **, unsigned int *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003b370`
- `0x18003b570`

## callees

- `0x18000166c`
- `0x180006538`
- `0x18000a240`
- `0x1800158e0`
- `0x18001a4b8`
- `0x18001c630`
- `0x18002cb98`
- `0x180038e00`
- `0x180039084`
- `0x18003a57c`
- `0x18003aa98`
- `0x1800420d4`
- `0x18004367c`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18003ab1a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18003ab46`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18003ab1a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18003ab46`

## string_xrefs

- `0x18003ae2f`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NgcCreateUserIdKeyInternal(
        struct _NGC_IDP_ACCOUNT_INFO *a1,
        bool *a2,
        HWND a3,
        const unsigned __int16 *a4,
        unsigned __int64 a5,
        unsigned int a6,
        unsigned __int16 **a7,
        unsigned __int8 **a8,
        unsigned int *a9,
        unsigned __int64 *a10)
{
  NgcUtils *v10; // rcx
  NgcUtils *v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  bool IsZero; // al
  GUID *v15; // r9
  bool *v16; // rdx
  int v17; // eax
  unsigned int v18; // ebx
  int v20; // [rsp+28h] [rbp-F0h]
  char v21; // [rsp+98h] [rbp-80h] BYREF
  char v22; // [rsp+99h] [rbp-7Fh] BYREF
  _BYTE v23[2]; // [rsp+9Ah] [rbp-7Eh] BYREF
  int IsCertTrustEnabled; // [rsp+9Ch] [rbp-7Ch] BYREF
  char v25; // [rsp+A0h] [rbp-78h] BYREF
  char v26; // [rsp+A1h] [rbp-77h] BYREF
  bool v27; // [rsp+A2h] [rbp-76h] BYREF
  char v28; // [rsp+A3h] [rbp-75h] BYREF
  char v29; // [rsp+A4h] [rbp-74h] BYREF
  bool IsNgcInVsmEnabled; // [rsp+A5h] [rbp-73h] BYREF
  bool v31[2]; // [rsp+A6h] [rbp-72h] BYREF
  int v32; // [rsp+A8h] [rbp-70h] BYREF
  int v33; // [rsp+ACh] [rbp-6Ch] BYREF
  unsigned int v34; // [rsp+B0h] [rbp-68h] BYREF
  int v35; // [rsp+B4h] [rbp-64h] BYREF
  __int64 v36; // [rsp+B8h] [rbp-60h] BYREF
  __int64 v37; // [rsp+C0h] [rbp-58h] BYREF
  __int64 v38; // [rsp+C8h] [rbp-50h] BYREF
  _QWORD v39[9]; // [rsp+D8h] [rbp-40h] BYREF
  __int16 v40; // [rsp+120h] [rbp+8h]
  _QWORD v41[13]; // [rsp+128h] [rbp+10h] BYREF
  int v42; // [rsp+190h] [rbp+78h] BYREF
  char v43; // [rsp+194h] [rbp+7Ch]
  GUID ActivityId; // [rsp+198h] [rbp+80h] BYREF
  GUID v45; // [rsp+1A8h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E0h] [rbp+C8h]
  struct _NGC_IDP_ACCOUNT_INFO *v47; // [rsp+1E8h] [rbp+D0h] BYREF
  bool *v48; // [rsp+1F0h] [rbp+D8h] BYREF
  HWND v49; // [rsp+1F8h] [rbp+E0h] BYREF
  const unsigned __int16 *v50; // [rsp+200h] [rbp+E8h] BYREF

  v50 = a4;
  v49 = a3;
  v48 = a2;
  v47 = a1;
  IsCertTrustEnabled = 0;
  v21 = 0;
  v22 = 0;
  v23[0] = 0;
  v33 = 0;
  v42 = 0;
  v43 = 0;
  if ( (unsigned int)dword_18006E000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18006E000, 0x800000000000LL) )
  {
    EventActivityIdControl(3u, &ActivityId);
    v45 = ActivityId;
    EventActivityIdControl(4u, &v45);
    v43 = 1;
  }
  else
  {
    ActivityId = 0;
  }
  v42 = 1;
  if ( (unsigned int)dword_18006E000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18006E000, 0x800000000000LL) )
  {
    v25 = v22;
    v26 = v21;
    v27 = a5 != 0;
    v34 = a6;
    v28 = v23[0];
    v35 = v33;
    v29 = 0;
    IsNgcInVsmEnabled = NgcUtils::IsNgcInVsmEnabled(v10);
    v31[0] = NgcUtils::IsSecureBioEnabled(v11);
    if ( v47 )
      v12 = *((_QWORD *)v47 + 1);
    else
      v12 = 0;
    v36 = v12;
    if ( v47 )
      v13 = *(_QWORD *)v47;
    else
      v13 = 0;
    v37 = v13;
    v38 = 16779264;
    v32 = IsCertTrustEnabled;
    if ( !v43 || (IsZero = _tlgGuidIsZero(&v45), v15 = &v45, IsZero) )
      LODWORD(v15) = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
      (unsigned int)&dword_18006E000,
      (unsigned int)&dword_18006103C,
      (unsigned int)&ActivityId,
      (_DWORD)v15,
      (__int64)&v32,
      (__int64)&v38,
      (__int64)&v37,
      (__int64)&v36,
      (__int64)v31,
      (__int64)&IsNgcInVsmEnabled,
      (__int64)&v29,
      (__int64)&v35,
      (__int64)&v28,
      (__int64)&v34,
      (__int64)&v27,
      (__int64)&v26,
      (__int64)&v25);
  }
  v39[0] = &v42;
  v39[1] = &IsCertTrustEnabled;
  v39[2] = &v47;
  v39[3] = &v33;
  v39[4] = v23;
  v39[5] = &a6;
  v39[6] = &a5;
  v39[7] = &v21;
  v39[8] = &v22;
  v40 = 256;
  IsCertTrustEnabled = NgcUtils::IsCertTrustEnabled((NgcUtils *)&v21, a2);
  if ( IsCertTrustEnabled < 0 )
  {
    if ( (unsigned int)dword_18006E000 > 3 )
    {
      v32 = IsCertTrustEnabled;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)&unk_180061008,
        0,
        0,
        (__int64)&v32);
    }
    IsCertTrustEnabled = 0;
  }
  IsCertTrustEnabled = NgcUtils::IsCloudTrustEnabled((NgcUtils *)&v22, v16);
  if ( IsCertTrustEnabled < 0 )
  {
    if ( (unsigned int)dword_18006E000 > 3 )
    {
      v32 = IsCertTrustEnabled;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)byte_180060FD3,
        0,
        0,
        (__int64)&v32);
    }
    IsCertTrustEnabled = 0;
  }
  v41[0] = v23;
  v41[1] = &a6;
  v41[2] = &v47;
  v41[3] = &v48;
  v41[4] = &v49;
  v41[5] = &v50;
  v41[6] = &a5;
  v41[7] = &a7;
  v41[8] = &a8;
  v41[9] = &a9;
  v41[10] = &IsCertTrustEnabled;
  v41[11] = &v33;
  v41[12] = &a10;
  v17 = HResultErrorContract__lambda_98035bf61e9b1594e64e902427a9b114_(v41);
  v18 = v17;
  IsCertTrustEnabled = v17;
  if ( v17 >= 0 )
    v18 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F6,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)(unsigned int)v17,
      v20);
  wil::details::ScopeExitFnGuard__lambda_3065d27111b209621a0d4756139e2ce5___::operator()(v39);
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>(&v42);
  return v18;
}

```

## disassembly

```asm
0x18003aa98  mov     rax, rsp
0x18003aa9b  mov     [rax+20h], r9
0x18003aa9f  mov     [rax+18h], r8
0x18003aaa3  mov     [rax+10h], rdx
0x18003aaa7  mov     [rax+8], rcx
0x18003aaab  push    rbp
0x18003aaac  push    rbx
0x18003aaad  push    rdi
0x18003aaae  lea     rbp, [rax-0C8h]
0x18003aab5  sub     rsp, 1C0h
0x18003aabc  mov     rax, cs:__security_cookie
0x18003aac3  xor     rax, rsp
0x18003aac6  mov     [rbp+0C0h+var_20], rax
0x18003aacd  xor     edi, edi
0x18003aacf  mov     [rbp+0C0h+var_13C], edi
0x18003aad2  mov     [rbp+0C0h+var_140], dil
0x18003aad6  mov     [rbp+0C0h+var_13F], dil
0x18003aada  mov     [rbp+0C0h+var_13E], dil
0x18003aade  mov     [rbp+0C0h+var_12C], edi
0x18003aae1  mov     [rbp+0C0h+var_48], edi
0x18003aae4  mov     [rbp+0C0h+var_44], dil
0x18003aae8  mov     eax, cs:dword_18006E000
0x18003aaee  lea     rbx, dword_18006E000
0x18003aaf5  cmp     eax, 5
0x18003aaf8  jbe     short loc_18003AB52
0x18003aafa  mov     rdx, 800000000000h
0x18003ab04  mov     rcx, rbx
0x18003ab07  call    _tlgKeywordOn
0x18003ab0c  test    al, al
0x18003ab0e  jz      short loc_18003AB52
0x18003ab10  lea     rdx, [rbp+0C0h+ActivityId]; ActivityId
0x18003ab17  lea     ecx, [rdi+3]; ControlCode
0x18003ab1a  call    cs:__imp_EventActivityIdControl
0x18003ab20  mov     rax, qword ptr [rbp+0C0h+ActivityId.Data1]
0x18003ab27  mov     qword ptr [rbp+0C0h+var_30.Data1], rax
0x18003ab2e  mov     rax, qword ptr [rbp+0C0h+ActivityId.Data4]
0x18003ab35  mov     qword ptr [rbp+0C0h+var_30.Data4], rax
0x18003ab3c  lea     rdx, [rbp+0C0h+var_30]; ActivityId
0x18003ab43  lea     ecx, [rdi+4]; ControlCode
0x18003ab46  call    cs:__imp_EventActivityIdControl
0x18003ab4c  mov     [rbp+0C0h+var_44], 1
0x18003ab50  jmp     short loc_18003AB5C
0x18003ab52  xorps   xmm0, xmm0
0x18003ab55  movups  xmmword ptr [rbp+0C0h+ActivityId.Data1], xmm0
0x18003ab5c  mov     [rbp+0C0h+var_48], 1
0x18003ab63  mov     eax, cs:dword_18006E000
0x18003ab69  cmp     eax, 5
0x18003ab6c  jbe     loc_18003ACB2
0x18003ab72  mov     rdx, 800000000000h
0x18003ab7c  mov     rcx, rbx
0x18003ab7f  call    _tlgKeywordOn
0x18003ab84  test    al, al
0x18003ab86  jz      loc_18003ACB2
0x18003ab8c  mov     al, [rbp+0C0h+var_13F]
0x18003ab8f  mov     [rbp+0C0h+var_138], al
0x18003ab92  mov     al, [rbp+0C0h+var_140]
0x18003ab95  mov     [rbp+0C0h+var_137], al
0x18003ab98  cmp     [rbp+0C0h+arg_20], rdi
0x18003ab9f  setnz   [rbp+0C0h+var_136]
0x18003aba3  mov     eax, [rbp+0C0h+arg_28]
0x18003aba9  mov     [rbp+0C0h+var_128], eax
0x18003abac  mov     al, [rbp+0C0h+var_13E]
0x18003abaf  mov     [rbp+0C0h+var_135], al
0x18003abb2  mov     eax, [rbp+0C0h+var_12C]
0x18003abb5  mov     [rbp+0C0h+var_124], eax
0x18003abb8  mov     [rbp+0C0h+var_134], dil
0x18003abbc  call    ?IsNgcInVsmEnabled@NgcUtils@@YA_NXZ; NgcUtils::IsNgcInVsmEnabled(void)
0x18003abc1  mov     [rbp+0C0h+var_133], al
0x18003abc4  call    ?IsSecureBioEnabled@NgcUtils@@YA_NXZ; NgcUtils::IsSecureBioEnabled(void)
0x18003abc9  mov     [rbp+0C0h+var_132], al
0x18003abcc  mov     rax, [rbp+0C0h+arg_0]
0x18003abd3  test    rax, rax
0x18003abd6  jz      short loc_18003ABDE
0x18003abd8  mov     rcx, [rax+8]
0x18003abdc  jmp     short loc_18003ABE1
0x18003abde  mov     rcx, rdi
0x18003abe1  mov     [rbp+0C0h+var_120], rcx
0x18003abe5  test    rax, rax
0x18003abe8  jz      short loc_18003ABEF
0x18003abea  mov     rcx, [rax]
0x18003abed  jmp     short loc_18003ABF2
0x18003abef  mov     rcx, rdi
0x18003abf2  mov     [rbp+0C0h+var_118], rcx
0x18003abf6  mov     [rbp+0C0h+var_110], 1000800h
0x18003abfe  mov     eax, [rbp+0C0h+var_13C]
0x18003ac01  mov     [rbp+0C0h+var_130], eax
0x18003ac04  cmp     [rbp+0C0h+var_44], dil
0x18003ac08  jz      short loc_18003AC21
0x18003ac0a  lea     rcx, [rbp+0C0h+var_30]; struct _GUID *
0x18003ac11  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18003ac16  test    al, al
0x18003ac18  lea     r9, [rbp+0C0h+var_30]
0x18003ac1f  jz      short loc_18003AC24
0x18003ac21  mov     r9, rdi
0x18003ac24  lea     rax, [rbp+0C0h+var_138]
0x18003ac28  mov     [rsp+80h], rax
0x18003ac30  lea     rax, [rbp+0C0h+var_137]
0x18003ac34  mov     [rsp+1D0h+var_158], rax
0x18003ac39  lea     rax, [rbp+0C0h+var_136]
0x18003ac3d  mov     [rsp+1D0h+var_160], rax
0x18003ac42  lea     rax, [rbp+0C0h+var_128]
0x18003ac46  mov     [rsp+1D0h+var_168], rax
0x18003ac4b  lea     rax, [rbp+0C0h+var_135]
0x18003ac4f  mov     [rsp+1D0h+var_170], rax
0x18003ac54  lea     rax, [rbp+0C0h+var_124]
0x18003ac58  mov     [rsp+1D0h+var_178], rax
0x18003ac5d  lea     rax, [rbp+0C0h+var_134]
0x18003ac61  mov     [rsp+1D0h+var_180], rax
0x18003ac66  lea     rax, [rbp+0C0h+var_133]
0x18003ac6a  mov     [rsp+1D0h+var_188], rax
0x18003ac6f  lea     rax, [rbp+0C0h+var_132]
0x18003ac73  mov     [rsp+1D0h+var_190], rax
0x18003ac78  lea     rax, [rbp+0C0h+var_120]
0x18003ac7c  mov     [rsp+1D0h+var_198], rax
0x18003ac81  lea     rax, [rbp+0C0h+var_118]
0x18003ac85  mov     [rsp+1D0h+var_1A0], rax
0x18003ac8a  lea     rax, [rbp+0C0h+var_110]
0x18003ac8e  mov     [rsp+1D0h+var_1A8], rax
0x18003ac93  lea     rax, [rbp+0C0h+var_130]
0x18003ac97  mov     qword ptr [rsp+1D0h+var_1B0], rax
0x18003ac9c  lea     r8, [rbp+0C0h+ActivityId]
0x18003aca3  lea     rdx, dword_18006103C
0x18003acaa  mov     rcx, rbx
0x18003acad  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$00@@U4@U4@U1@U4@U1@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$00@@66363666@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)
0x18003acb2  lea     rax, [rbp+0C0h+var_48]
0x18003acb6  mov     [rbp+0C0h+var_100], rax
0x18003acba  lea     rax, [rbp+0C0h+var_13C]
0x18003acbe  mov     [rbp+0C0h+var_F8], rax
0x18003acc2  lea     rax, [rbp+0C0h+arg_0]
0x18003acc9  mov     [rbp+0C0h+var_F0], rax
0x18003accd  lea     rax, [rbp+0C0h+var_12C]
0x18003acd1  mov     [rbp+0C0h+var_E8], rax
0x18003acd5  lea     rax, [rbp+0C0h+var_13E]
0x18003acd9  mov     [rbp+0C0h+var_E0], rax
0x18003acdd  lea     rax, [rbp+0C0h+arg_28]
0x18003ace4  mov     [rbp+0C0h+var_D8], rax
0x18003ace8  lea     rax, [rbp+0C0h+arg_20]
0x18003acef  mov     [rbp+0C0h+var_D0], rax
0x18003acf3  lea     rax, [rbp+0C0h+var_140]
0x18003acf7  mov     [rbp+0C0h+var_C8], rax
0x18003acfb  lea     rax, [rbp+0C0h+var_13F]
0x18003acff  mov     [rbp+0C0h+var_C0], rax
0x18003ad03  mov     [rbp+0C0h+var_B8], 100h
0x18003ad09  lea     rcx, [rbp+0C0h+var_140]; this
0x18003ad0d  call    ?IsCertTrustEnabled@NgcUtils@@YAJPEA_N@Z; NgcUtils::IsCertTrustEnabled(bool *)
0x18003ad12  mov     [rbp+0C0h+var_13C], eax
0x18003ad15  test    eax, eax
0x18003ad17  jns     short loc_18003AD4B
0x18003ad19  mov     eax, cs:dword_18006E000
0x18003ad1f  cmp     eax, 3
0x18003ad22  jbe     short loc_18003AD48
0x18003ad24  mov     eax, [rbp+0C0h+var_13C]
0x18003ad27  mov     [rbp+0C0h+var_130], eax
0x18003ad2a  lea     rax, [rbp+0C0h+var_130]
0x18003ad2e  mov     qword ptr [rsp+1D0h+var_1B0], rax
0x18003ad33  xor     r9d, r9d
0x18003ad36  xor     r8d, r8d
0x18003ad39  lea     rdx, unk_180061008
0x18003ad40  mov     rcx, rbx
0x18003ad43  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003ad48  mov     [rbp+0C0h+var_13C], edi
0x18003ad4b  lea     rcx, [rbp+0C0h+var_13F]; this
0x18003ad4f  call    ?IsCloudTrustEnabled@NgcUtils@@YAJPEA_N@Z; NgcUtils::IsCloudTrustEnabled(bool *)
0x18003ad54  mov     [rbp+0C0h+var_13C], eax
0x18003ad57  test    eax, eax
0x18003ad59  jns     short loc_18003AD8D
0x18003ad5b  mov     eax, cs:dword_18006E000
0x18003ad61  cmp     eax, 3
0x18003ad64  jbe     short loc_18003AD8A
0x18003ad66  mov     eax, [rbp+0C0h+var_13C]
0x18003ad69  mov     [rbp+0C0h+var_130], eax
0x18003ad6c  lea     rax, [rbp+0C0h+var_130]
0x18003ad70  mov     qword ptr [rsp+1D0h+var_1B0], rax; int
0x18003ad75  xor     r9d, r9d
0x18003ad78  xor     r8d, r8d
0x18003ad7b  lea     rdx, byte_180060FD3
0x18003ad82  mov     rcx, rbx
0x18003ad85  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003ad8a  mov     [rbp+0C0h+var_13C], edi
0x18003ad8d  lea     rax, [rbp+0C0h+var_13E]
0x18003ad91  mov     [rbp+0C0h+var_B0], rax
0x18003ad95  lea     rax, [rbp+0C0h+arg_28]
0x18003ad9c  mov     [rbp+0C0h+var_A8], rax
0x18003ada0  lea     rax, [rbp+0C0h+arg_0]
0x18003ada7  mov     [rbp+0C0h+var_A0], rax
0x18003adab  lea     rax, [rbp+0C0h+arg_8]
0x18003adb2  mov     [rbp+0C0h+var_98], rax
0x18003adb6  lea     rax, [rbp+0C0h+arg_10]
0x18003adbd  mov     [rbp+0C0h+var_90], rax
0x18003adc1  lea     rax, [rbp+0C0h+arg_18]
0x18003adc8  mov     [rbp+0C0h+var_88], rax
0x18003adcc  lea     rax, [rbp+0C0h+arg_20]
0x18003add3  mov     [rbp+0C0h+var_80], rax
0x18003add7  lea     rax, [rbp+0C0h+arg_30]
0x18003adde  mov     [rbp+0C0h+var_78], rax
0x18003ade2  lea     rax, [rbp+0C0h+arg_38]
0x18003ade9  mov     [rbp+0C0h+var_70], rax
0x18003aded  lea     rax, [rbp+0C0h+arg_40]
0x18003adf4  mov     [rbp+0C0h+var_68], rax
0x18003adf8  lea     rax, [rbp+0C0h+var_13C]
0x18003adfc  mov     [rbp+0C0h+var_60], rax
0x18003ae00  lea     rax, [rbp+0C0h+var_12C]
0x18003ae04  mov     [rbp+0C0h+var_58], rax
0x18003ae08  lea     rax, [rbp+0C0h+arg_48]
0x18003ae0f  mov     [rbp+0C0h+var_50], rax
0x18003ae13  lea     rcx, [rbp+0C0h+var_B0]
0x18003ae17  call    HResultErrorContract__lambda_98035bf61e9b1594e64e902427a9b114___; HResultErrorContract__lambda_98035bf61e9b1594e64e902427a9b114_
0x18003ae1c  mov     ebx, eax
0x18003ae1e  mov     [rbp+0C0h+var_13C], eax
0x18003ae21  test    eax, eax
0x18003ae23  jns     short loc_18003AE42
0x18003ae25  mov     rcx, [rbp+0C8h]; this
0x18003ae2c  mov     r9d, eax; char *
0x18003ae2f  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18003ae36  mov     edx, 2F6h; void *
0x18003ae3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ae40  jmp     short loc_18003AE44
0x18003ae42  mov     ebx, edi
0x18003ae44  lea     rcx, [rbp+0C0h+var_100]
0x18003ae48  call    wil__details__ScopeExitFnGuard__lambda_3065d27111b209621a0d4756139e2ce5_____operator__
0x18003ae4d  nop
0x18003ae4e  lea     rcx, [rbp+0C0h+var_48]
0x18003ae52  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0IAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0IAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>(void)
0x18003ae57  mov     eax, ebx
0x18003ae59  mov     rcx, [rbp+0C0h+var_20]
0x18003ae60  xor     rcx, rsp; StackCookie
0x18003ae63  call    __security_check_cookie
0x18003ae68  add     rsp, 1C0h
0x18003ae6f  pop     rdi
0x18003ae70  pop     rbx
0x18003ae71  pop     rbp
0x18003ae72  retn
```
