# LPA::Lpd::DownloadInstance::InitiateCommonMutualAuthentication(char const *,char const *,char const *,bool,char const *,LPA_ERROR_DETAILS *)

- ea: `0x1800b0e38`
- end: `0x1800b11ae`
- name: `?InitiateCommonMutualAuthentication@DownloadInstance@Lpd@LPA@@AEAAJPEBD00_N0PEAULPA_ERROR_DETAILS@@@Z`
- size: `886`
- prototype: `__int64 __usercall@<rax>(LPA::Lpd::DownloadInstance *__hidden this@<rcx>, const char *@<rdx>, const char *@<r8>, const char *@<r9>, bool, const char *, struct LPA_ERROR_DETAILS *)`
- caller_count: `4`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b1768`
- `0x1800b2530`
- `0x1800b75d0`
- `0x1800b7b04`

## callees

- `0x180005d6c`
- `0x18000df90`
- `0x18005fe14`
- `0x1800709e4`
- `0x180071650`
- `0x180071994`
- `0x180071a8c`
- `0x1800815e0`
- `0x1800b0e38`
- `0x1800b7f0c`
- `0x1800b95e8`
- `0x1800d97c8`
- `0x180101010`

## string_xrefs

- `0x1800b0e80`: `LpaServiceLpd`
- `0x1800b1136`: `LpaServiceLpd`
- `0x1800b0e9a`: `OnInitiateCommonMutualAuthentication`
- `0x1800b0e79`: `LPA::Lpd::DownloadInstance::InitiateCommonMutualAuthentication`
- `0x1800b112b`: `LPA::Lpd::DownloadInstance::InitiateCommonMutualAuthentication`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall LPA::Lpd::DownloadInstance::InitiateCommonMutualAuthentication(
        LPA::Lpd::DownloadInstance *this,
        const char *a2,
        const char *a3,
        const char *a4,
        bool a5,
        const char *a6,
        struct LPA_ERROR_DETAILS *a7)
{
  int v11; // r8d
  int v12; // r9d
  int v13; // ebx
  __int64 v14; // rbx
  __int64 v15; // r8
  __int64 v16; // r8
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, char *, _QWORD, __int64 *, char *); // rbx
  _QWORD *v19; // rax
  __int64 *v20; // rax
  int v21; // ecx
  const char *v22; // rcx
  const char *v23; // rax
  char *v24; // rdx
  int v26; // [rsp+60h] [rbp-61h] BYREF
  int v27; // [rsp+64h] [rbp-5Dh] BYREF
  int v28; // [rsp+68h] [rbp-59h] BYREF
  int v29; // [rsp+6Ch] [rbp-55h] BYREF
  const char *v30; // [rsp+70h] [rbp-51h] BYREF
  std::_Ref_count_base *v31; // [rsp+78h] [rbp-49h]
  const char *v32; // [rsp+80h] [rbp-41h] BYREF
  std::_Ref_count_base *v33; // [rsp+88h] [rbp-39h]
  _OWORD v34[2]; // [rsp+90h] [rbp-31h] BYREF

  if ( (unsigned int)CallbackContext > 4 )
  {
    v26 = 0;
    v27 = 3;
    v32 = "OnInitiateCommonMutualAuthentication";
    v28 = *((_DWORD *)this + 228);
    v29 = 2;
    v30 = "LPA::Lpd::DownloadInstance::InitiateCommonMutualAuthentication";
    *(_QWORD *)&v34[0] = "LpaServiceLpd";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)"LPA::Lpd::DownloadInstance::InitiateCommonMutualAuthentication",
      (unsigned int)byte_18012FF39,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)v34,
      (__int64)&v30,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v32,
      (__int64)&v27,
      (__int64)&v26);
  }
  LPA::Lpd::DownloadInstance::ResetPostCmaStateVariables(this);
  *((_BYTE *)this + 139) = a5;
  if ( !a2 )
  {
    v13 = -2147024809;
    goto LABEL_27;
  }
  v14 = -1;
  v15 = -1;
  do
    ++v15;
  while ( a2[v15] );
  std::string::_Assign<char>((char *)this + 272, a2);
  if ( a3 )
  {
    v16 = -1;
    do
      ++v16;
    while ( a3[v16] );
    std::string::_Assign<char>((char *)this + 304, a3);
  }
  if ( a4 )
  {
    do
      ++v14;
    while ( a4[v14] );
    std::string::_Assign<char>((char *)this + 336, a4);
  }
  if ( a6 )
  {
    v34[0] = 0;
    v34[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v34[0]) = 0;
    LPA::Util::ConvertUtf8ToUtf16(a6, v34);
    CommonUtil::WStringToByteVector(v34, (char *)this + 496);
    std::wstring::_Tidy_deallocate(v34);
  }
  std::weak_ptr<LPA::Lpd::DownloadInstance>::lock((char *)this + 32, &v30);
  if ( v30 )
  {
    v17 = *((_QWORD *)v30 + 7);
    v18 = *(__int64 (__fastcall **)(__int64, char *, _QWORD, __int64 *, char *))(*(_QWORD *)(v17 + 8) + 32LL);
    v19 = (_QWORD *)std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this((char *)this + 16, &v32);
    v20 = std::weak_ptr<LPA::ApduHelperEs10bCompletionHandler>::weak_ptr<LPA::ApduHelperEs10bCompletionHandler>(
            (__int64 *)v34,
            v19);
    v13 = v18(v17 + 8, (char *)this + 884, *((unsigned int *)this + 259), v20, (char *)this + 920);
    if ( v33 )
      std::_Ref_count_base::_Decref(v33);
    if ( v13 < 0 )
    {
      v21 = *((_DWORD *)this + 256);
      if ( (v21 & 1) == 0 || !*((_DWORD *)this + 257) )
      {
        *((_DWORD *)this + 256) = v21 | 1;
        *((_DWORD *)this + 257) = 1;
      }
    }
  }
  else
  {
    v13 = -2147418113;
  }
  LODWORD(v22) = (_DWORD)v31;
  if ( v31 )
    std::_Ref_count_base::_Decref(v31);
  if ( v13 < 0 )
  {
LABEL_27:
    if ( a7 )
    {
      *(_QWORD *)a7 = *((_QWORD *)this + 128);
      *((_DWORD *)a7 + 2) = *((_DWORD *)this + 258);
    }
    if ( (unsigned int)CallbackContext > 2 )
    {
      v29 = *((_DWORD *)this + 230);
      v28 = ((v13 >> 31) & 0xE) + 3;
      v22 = "Failure";
      v23 = "Failure";
      v24 = byte_18012FED5;
      goto LABEL_35;
    }
    return (unsigned int)v13;
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    v29 = *((_DWORD *)this + 230);
    v28 = 3;
    v23 = "WaitEs10bGetEuiccInfo1";
    v24 = byte_18012FE71;
LABEL_35:
    *(_QWORD *)&v34[0] = v23;
    v27 = *((_DWORD *)this + 228);
    v30 = "LPA::Lpd::DownloadInstance::InitiateCommonMutualAuthentication";
    v32 = "LpaServiceLpd";
    v26 = 2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v22,
      (_DWORD)v24,
      v11,
      v12,
      (__int64)&v32,
      (__int64)&v30,
      (__int64)&v26,
      (__int64)&v27,
      (__int64)v34,
      (__int64)&v28,
      (__int64)&v29);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800b0e38  push    rbp
0x1800b0e3a  push    rbx
0x1800b0e3b  push    rsi
0x1800b0e3c  push    rdi
0x1800b0e3d  push    r12
0x1800b0e3f  push    r13
0x1800b0e41  push    r14
0x1800b0e43  push    r15
0x1800b0e45  lea     rbp, [rsp-7]
0x1800b0e4a  sub     rsp, 0C8h
0x1800b0e51  mov     rax, cs:__security_cookie
0x1800b0e58  xor     rax, rsp
0x1800b0e5b  mov     [rbp+3Fh+var_50], rax
0x1800b0e5f  mov     r14, r9
0x1800b0e62  mov     r15, r8
0x1800b0e65  mov     rdi, rdx
0x1800b0e68  mov     rsi, rcx
0x1800b0e6b  mov     r12, [rbp+3Fh+arg_28]
0x1800b0e6f  mov     r13, [rbp+3Fh+arg_30]
0x1800b0e73  mov     eax, cs:CallbackContext
0x1800b0e79  lea     rcx, aLpaLpdDownload_33; "LPA::Lpd::DownloadInstance::InitiateCom"...
0x1800b0e80  lea     rdx, aLpaservicelpd; "LpaServiceLpd"
0x1800b0e87  cmp     eax, 4
0x1800b0e8a  jbe     short loc_1800B0F08
0x1800b0e8c  mov     [rbp+3Fh+var_A0], 0
0x1800b0e93  mov     [rbp+3Fh+var_9C], 3
0x1800b0e9a  lea     rax, aOninitiatecomm; "OnInitiateCommonMutualAuthentication"
0x1800b0ea1  mov     [rbp+3Fh+var_80], rax
0x1800b0ea5  mov     eax, [rsi+390h]
0x1800b0eab  mov     [rbp+3Fh+var_98], eax
0x1800b0eae  mov     [rbp+3Fh+var_94], 2
0x1800b0eb5  mov     [rbp+3Fh+var_90], rcx
0x1800b0eb9  mov     qword ptr [rbp+3Fh+var_70], rdx
0x1800b0ebd  lea     rax, [rbp+3Fh+var_A0]
0x1800b0ec1  mov     [rsp+100h+var_B0], rax
0x1800b0ec6  lea     rax, [rbp+3Fh+var_9C]
0x1800b0eca  mov     [rsp+100h+var_B8], rax
0x1800b0ecf  lea     rax, [rbp+3Fh+var_80]
0x1800b0ed3  mov     [rsp+100h+var_C0], rax
0x1800b0ed8  lea     rax, [rbp+3Fh+var_98]
0x1800b0edc  mov     [rsp+100h+var_C8], rax
0x1800b0ee1  lea     rax, [rbp+3Fh+var_94]
0x1800b0ee5  mov     [rsp+100h+var_D0], rax
0x1800b0eea  lea     rax, [rbp+3Fh+var_90]
0x1800b0eee  mov     [rsp+100h+var_D8], rax
0x1800b0ef3  lea     rax, [rbp+3Fh+var_70]
0x1800b0ef7  mov     [rsp+100h+var_E0], rax
0x1800b0efc  lea     rdx, byte_18012FF39
0x1800b0f03  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b0f08  mov     rcx, rsi; this
0x1800b0f0b  call    ?ResetPostCmaStateVariables@DownloadInstance@Lpd@LPA@@AEAAXXZ; LPA::Lpd::DownloadInstance::ResetPostCmaStateVariables(void)
0x1800b0f10  mov     al, [rbp+3Fh+arg_20]
0x1800b0f13  mov     [rsi+8Bh], al
0x1800b0f19  test    rdi, rdi
0x1800b0f1c  jnz     short loc_1800B0F28
0x1800b0f1e  mov     ebx, 80070057h
0x1800b0f23  jmp     loc_1800B108D
0x1800b0f28  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800b0f2c  mov     r8, rbx
0x1800b0f2f  inc     r8
0x1800b0f32  cmp     byte ptr [rdi+r8], 0
0x1800b0f37  jnz     short loc_1800B0F2F
0x1800b0f39  lea     rcx, [rsi+110h]
0x1800b0f40  mov     rdx, rdi
0x1800b0f43  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x1800b0f48  test    r15, r15
0x1800b0f4b  jz      short loc_1800B0F69
0x1800b0f4d  mov     r8, rbx
0x1800b0f50  inc     r8
0x1800b0f53  cmp     byte ptr [r15+r8], 0
0x1800b0f58  jnz     short loc_1800B0F50
0x1800b0f5a  lea     rcx, [rsi+130h]
0x1800b0f61  mov     rdx, r15
0x1800b0f64  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x1800b0f69  test    r14, r14
0x1800b0f6c  jz      short loc_1800B0F8A
0x1800b0f6e  inc     rbx
0x1800b0f71  cmp     byte ptr [r14+rbx], 0
0x1800b0f76  jnz     short loc_1800B0F6E
0x1800b0f78  lea     rcx, [rsi+150h]
0x1800b0f7f  mov     r8, rbx
0x1800b0f82  mov     rdx, r14
0x1800b0f85  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x1800b0f8a  test    r12, r12
0x1800b0f8d  jz      short loc_1800B0FCF
0x1800b0f8f  xorps   xmm0, xmm0
0x1800b0f92  movups  [rbp+3Fh+var_70], xmm0
0x1800b0f96  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800b0f9e  movdqu  [rbp+3Fh+var_60], xmm1
0x1800b0fa3  xor     eax, eax
0x1800b0fa5  mov     word ptr [rbp+3Fh+var_70], ax
0x1800b0fa9  lea     rdx, [rbp+3Fh+var_70]
0x1800b0fad  mov     rcx, r12
0x1800b0fb0  call    ?ConvertUtf8ToUtf16@Util@LPA@@YAJPEBDAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@4@@Z; LPA::Util::ConvertUtf8ToUtf16(char const *,std::wstring &,std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>> *)
0x1800b0fb5  lea     rdx, [rsi+1F0h]
0x1800b0fbc  lea     rcx, [rbp+3Fh+var_70]
0x1800b0fc0  call    ?WStringToByteVector@CommonUtil@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@3@@Z; CommonUtil::WStringToByteVector(std::wstring const &,std::vector<uchar> &)
0x1800b0fc5  nop
0x1800b0fc6  lea     rcx, [rbp+3Fh+var_70]
0x1800b0fca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b0fcf  lea     rcx, [rsi+20h]
0x1800b0fd3  lea     rdx, [rbp+3Fh+var_90]
0x1800b0fd7  call    ?lock@?$weak_ptr@VDownloadInstance@Lpd@LPA@@@std@@QEBA?AV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@2@XZ; std::weak_ptr<LPA::Lpd::DownloadInstance>::lock(void)
0x1800b0fdc  nop
0x1800b0fdd  mov     rax, [rbp+3Fh+var_90]
0x1800b0fe1  test    rax, rax
0x1800b0fe4  jz      loc_1800B1076
0x1800b0fea  mov     rdi, [rax+38h]
0x1800b0fee  mov     rax, [rdi+8]
0x1800b0ff2  mov     rbx, [rax+20h]
0x1800b0ff6  lea     rcx, [rsi+10h]
0x1800b0ffa  lea     rdx, [rbp+3Fh+var_80]
0x1800b0ffe  call    ?shared_from_this@?$enable_shared_from_this@VEnterpriseManager@LPA@@@std@@QEAA?AV?$shared_ptr@VEnterpriseManager@LPA@@@2@XZ; std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(void)
0x1800b1003  nop
0x1800b1004  mov     rdx, rax
0x1800b1007  lea     rcx, [rbp+3Fh+var_70]
0x1800b100b  call    ??$?0VEsimManager@LPA@@$0A@@?$weak_ptr@UApduHelperEs10bCompletionHandler@LPA@@@std@@QEAA@AEBV?$shared_ptr@VEsimManager@LPA@@@1@@Z; std::weak_ptr<LPA::ApduHelperEs10bCompletionHandler>::weak_ptr<LPA::ApduHelperEs10bCompletionHandler>(std::shared_ptr<LPA::EsimManager> const &)
0x1800b1010  lea     r8, [rsi+398h]
0x1800b1017  lea     rdx, [rsi+374h]
0x1800b101e  mov     [rsp+100h+var_E0], r8
0x1800b1023  mov     r9, rax
0x1800b1026  mov     r8d, [rsi+40Ch]
0x1800b102d  lea     rcx, [rdi+8]
0x1800b1031  mov     rax, rbx
0x1800b1034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1039  mov     ebx, eax
0x1800b103b  mov     rcx, [rbp+3Fh+var_78]; this
0x1800b103f  test    rcx, rcx
0x1800b1042  jz      short loc_1800B1049
0x1800b1044  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b1049  test    ebx, ebx
0x1800b104b  jns     short loc_1800B107B
0x1800b104d  mov     ecx, [rsi+400h]
0x1800b1053  test    cl, 1
0x1800b1056  jz      short loc_1800B1061
0x1800b1058  cmp     dword ptr [rsi+404h], 0
0x1800b105f  jnz     short loc_1800B107B
0x1800b1061  or      ecx, 1
0x1800b1064  mov     [rsi+400h], ecx
0x1800b106a  mov     dword ptr [rsi+404h], 1
0x1800b1074  jmp     short loc_1800B107B
0x1800b1076  mov     ebx, 8000FFFFh
0x1800b107b  mov     rcx, [rbp+3Fh+var_88]; this
0x1800b107f  test    rcx, rcx
0x1800b1082  jz      short loc_1800B1089
0x1800b1084  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b1089  test    ebx, ebx
0x1800b108b  jns     short loc_1800B10F1
0x1800b108d  test    r13, r13
0x1800b1090  jz      short loc_1800B10AE
0x1800b1092  movsd   xmm0, qword ptr [rsi+400h]
0x1800b109a  movsd   qword ptr [r13+0], xmm0
0x1800b10a0  mov     eax, [rsi+408h]
0x1800b10a6  mov     [r13+8], eax
0x1800b10aa  test    ebx, ebx
0x1800b10ac  jns     short loc_1800B10F1
0x1800b10ae  mov     eax, cs:CallbackContext
0x1800b10b4  cmp     eax, 2
0x1800b10b7  jbe     loc_1800B118C
0x1800b10bd  mov     eax, [rsi+398h]
0x1800b10c3  mov     [rbp+3Fh+var_94], eax
0x1800b10c6  mov     eax, ebx
0x1800b10c8  sar     eax, 1Fh
0x1800b10cb  and     eax, 0Eh
0x1800b10ce  add     eax, 3
0x1800b10d1  mov     [rbp+3Fh+var_98], eax
0x1800b10d4  lea     rcx, aFailure; "Failure"
0x1800b10db  lea     rax, aWaites10bgeteu; "WaitEs10bGetEuiccInfo1"
0x1800b10e2  test    ebx, ebx
0x1800b10e4  cmovs   rax, rcx
0x1800b10e8  lea     rdx, byte_18012FED5
0x1800b10ef  jmp     short loc_1800B111E
0x1800b10f1  mov     eax, cs:CallbackContext
0x1800b10f7  cmp     eax, 4
0x1800b10fa  jbe     loc_1800B118C
0x1800b1100  mov     eax, [rsi+398h]
0x1800b1106  mov     [rbp+3Fh+var_94], eax
0x1800b1109  mov     [rbp+3Fh+var_98], 3
0x1800b1110  lea     rax, aWaites10bgeteu; "WaitEs10bGetEuiccInfo1"
0x1800b1117  lea     rdx, byte_18012FE71
0x1800b111e  mov     qword ptr [rbp+3Fh+var_70], rax
0x1800b1122  mov     eax, [rsi+390h]
0x1800b1128  mov     [rbp+3Fh+var_9C], eax
0x1800b112b  lea     rax, aLpaLpdDownload_33; "LPA::Lpd::DownloadInstance::InitiateCom"...
0x1800b1132  mov     [rbp+3Fh+var_90], rax
0x1800b1136  lea     rax, aLpaservicelpd; "LpaServiceLpd"
0x1800b113d  mov     [rbp+3Fh+var_80], rax
0x1800b1141  lea     rax, [rbp+3Fh+var_94]
0x1800b1145  mov     [rsp+100h+var_B0], rax
0x1800b114a  lea     rax, [rbp+3Fh+var_98]
0x1800b114e  mov     [rsp+100h+var_B8], rax
0x1800b1153  lea     rax, [rbp+3Fh+var_70]
0x1800b1157  mov     [rsp+100h+var_C0], rax
0x1800b115c  lea     rax, [rbp+3Fh+var_9C]
0x1800b1160  mov     [rsp+100h+var_C8], rax
0x1800b1165  lea     rax, [rbp+3Fh+var_A0]
0x1800b1169  mov     [rsp+100h+var_D0], rax
0x1800b116e  lea     rax, [rbp+3Fh+var_90]
0x1800b1172  mov     [rsp+100h+var_D8], rax
0x1800b1177  lea     rax, [rbp+3Fh+var_80]
0x1800b117b  mov     [rsp+100h+var_E0], rax
0x1800b1180  mov     [rbp+3Fh+var_A0], 2
0x1800b1187  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b118c  mov     eax, ebx
0x1800b118e  mov     rcx, [rbp+3Fh+var_50]
0x1800b1192  xor     rcx, rsp; StackCookie
0x1800b1195  call    __security_check_cookie
0x1800b119a  add     rsp, 0C8h
0x1800b11a1  pop     r15
0x1800b11a3  pop     r14
0x1800b11a5  pop     r13
0x1800b11a7  pop     r12
0x1800b11a9  pop     rdi
0x1800b11aa  pop     rsi
0x1800b11ab  pop     rbx
0x1800b11ac  pop     rbp
0x1800b11ad  retn
```
