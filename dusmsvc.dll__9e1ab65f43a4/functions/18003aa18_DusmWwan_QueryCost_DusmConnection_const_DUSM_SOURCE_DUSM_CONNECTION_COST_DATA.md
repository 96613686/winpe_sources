# DusmWwan::QueryCost(DusmConnection const &,_DUSM_SOURCE,_DUSM_CONNECTION_COST_DATA *)

- ea: `0x18003aa18`
- end: `0x18003ad7c`
- name: `?QueryCost@DusmWwan@@SAHAEBVDusmConnection@@W4_DUSM_SOURCE@@PEAU_DUSM_CONNECTION_COST_DATA@@@Z`
- size: `868`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, installer_update`

## callers

- `0x18001b1f0`
- `0x18003050c`

## callees

- `0x1800021e4`
- `0x180006158`
- `0x1800065cc`
- `0x180007c90`
- `0x180008704`
- `0x18000f214`
- `0x180012fcc`
- `0x180013444`
- `0x180017464`
- `0x180017cec`
- `0x180018080`
- `0x1800183f8`
- `0x180019154`
- `0x18001d87c`
- `0x1800289c0`
- `0x1800295e0`
- `0x180029b98`
- `0x18002a860`
- `0x180039824`
- `0x18003aa18`
- `0x18003adf0`
- `0x18003b64c`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x18003ab14`
- `RPCRT4!UuidToStringW` at `0x18003ab14`
- `wwapi!WwanFreeMemory` at `0x18003abbb`
- `wwapi!WwanFreeMemory` at `0x18003abbb`

## string_xrefs

- `0x18003ab75`: `DusmWwan::QueryCost::QueryWwanSubscriberInfo - IccId and/or Imsi properties are empty for profile %ws (GUID %ws) (iccid: %ws, imsi: %ws)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DusmWwan::QueryCost(DusmConnection *a1, unsigned int a2, int *a3)
{
  const WCHAR *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rbx
  __int64 v10; // r8
  __int64 v11; // rdx
  bool IsConnectionKeySet; // al
  const char *v13; // r8
  __int64 v14; // r9
  __int64 v15; // r10
  __int64 v16; // r11
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  unsigned int GpCost; // ebx
  __int64 v21; // rdx
  unsigned int *v22; // r8
  __int64 v23; // r9
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  unsigned int Source; // eax
  _DWORD *v28; // rcx
  __int64 v29; // rdx
  _DWORD *v30; // r8
  __int64 v31; // r9
  __int64 v32; // r8
  __int64 v33; // r9
  const char *v35; // [rsp+28h] [rbp-D8h]
  __int64 v36; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+58h] [rbp-A8h] BYREF
  RPC_WSTR StringUuid; // [rsp+60h] [rbp-A0h] BYREF
  UUID Uuid; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v40[32]; // [rsp+80h] [rbp-80h] BYREF
  UUID v41; // [rsp+A0h] [rbp-60h]
  _BYTE v42[64]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v43[32]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v44[176]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  if ( a2 == 1 )
  {
    GpCost = DusmStore::QueryGpCost(3, a3);
    if ( GpCost )
    {
      v22 = *(unsigned int **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v19, v18) + 8);
      v24 = *v22;
      if ( (unsigned int)v24 > 4 )
      {
        LODWORD(v36) = a3[1];
        LODWORD(StringUuid) = *a3;
        v37 = DusmSourceToSz(1, (unsigned int)StringUuid, v22, v23);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v25,
          (int)word_18005A2FA,
          v25,
          v26,
          (const WCHAR **)&v37,
          (__int64)&StringUuid,
          (__int64)&v36);
      }
      goto LABEL_19;
    }
  }
  else if ( a2 - 2 > 1 )
  {
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x32C,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmwwan.cpp",
      (const char *)0x57,
      (unsigned int)"DusmWwan::QueryCost",
      v35);
  }
  memset_0(v40, 0, 0x140u);
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)a1 + 48);
  DusmConnection::DusmConnection((__int64)v40, (_OWORD *)a1 + 2, v6, 3, 0);
  if ( DusmConnection::IsConnectionKeySet(a1) )
  {
    std::wstring::operator=(v44, (char *)a1 + 144);
    std::wstring::operator=(v43, (char *)a1 + 112);
  }
  else
  {
    DusmWwan::QueryWwanSubscriberInfo(v7, &v37, (__int64)a1 + 32);
    v8 = v37 + 8;
    v9 = -1;
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)(v8 + 2 * v10) );
    std::wstring::_Assign<wchar_t>(v43, v8, v10);
    v11 = v37 + 40;
    do
      ++v9;
    while ( *(_WORD *)(v11 + 2 * v9) );
    std::wstring::_Assign<wchar_t>(v44, v11, v9);
    Uuid = v41;
    StringUuid = 0;
    UuidToStringW(&Uuid, &StringUuid);
    std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v43);
    std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v44);
    std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v42);
    IsConnectionKeySet = DusmConnection::IsConnectionKeySet((DusmConnection *)v40);
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x354,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmwwan.cpp",
      (const char *)0x8000FFFFLL,
      !IsConnectionKeySet,
      (bool)"DusmWwan::QueryCost::QueryWwanSubscriberInfo - IccId and/or Imsi properties are empty for profile %ws (GUID "
            "%ws) (iccid: %ws, imsi: %ws)",
      v13,
      v15,
      v14,
      v16);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
    v17 = v37;
    v37 = 0;
    if ( v17 )
      WwanFreeMemory(v17);
  }
  if ( a2 == 1 )
    Source = DusmStore::QuerySource((__int64)v40);
  else
    Source = a2;
  GpCost = DusmStore::QueryCost((__int64)v40, Source, a3);
  DusmConnection::~DusmConnection((DusmConnection *)v40);
  if ( a2 == 1 )
  {
    if ( !GpCost )
    {
LABEL_20:
      v28 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v24, v21) + 8);
      if ( *v28 > 4u )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          (int)v28,
          (int)word_18005A37A);
      *(_QWORD *)a3 = DusmStore::QueryDefaultCost(3, 1);
      GpCost = 1;
      goto LABEL_23;
    }
LABEL_19:
    if ( *a3 )
      goto LABEL_23;
    goto LABEL_20;
  }
LABEL_23:
  v30 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v24, v21) + 8);
  if ( *v30 > 4u )
  {
    LODWORD(StringUuid) = a3[1];
    LODWORD(v36) = *a3;
    LODWORD(v37) = GpCost;
    *(_QWORD *)&Uuid.Data1 = DusmSourceToSz(a2, v29, v30, v31);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v32,
      (int)byte_18005A17D,
      v32,
      v33,
      (const WCHAR **)&Uuid,
      (__int64)&v37,
      (__int64)&v36,
      (__int64)&StringUuid);
  }
  return GpCost;
}

```

## disassembly

```asm
0x18003aa18  mov     [rsp-8+arg_18], rbx
0x18003aa1d  push    rbp
0x18003aa1e  push    rsi
0x18003aa1f  push    rdi
0x18003aa20  push    r14
0x18003aa22  push    r15
0x18003aa24  lea     rbp, [rsp-0D0h]
0x18003aa2c  sub     rsp, 1D0h
0x18003aa33  mov     rax, cs:__security_cookie
0x18003aa3a  xor     rax, rsp
0x18003aa3d  mov     [rbp+0F0h+var_30], rax
0x18003aa44  mov     rdi, r8
0x18003aa47  mov     esi, edx
0x18003aa49  mov     r14, rcx
0x18003aa4c  xor     r15d, r15d
0x18003aa4f  cmp     edx, 1
0x18003aa52  jz      loc_18003ABC6
0x18003aa58  lea     eax, [rdx-2]
0x18003aa5b  cmp     eax, 1
0x18003aa5e  ja      loc_18003AD51
0x18003aa64  xor     edx, edx; Val
0x18003aa66  mov     r8d, 140h; Size
0x18003aa6c  lea     rcx, [rbp+0F0h+var_170]; void *
0x18003aa70  call    memset_0
0x18003aa75  lea     rcx, [r14+30h]
0x18003aa79  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003aa7e  mov     qword ptr [rsp+1F0h+var_1D0], r15
0x18003aa83  mov     r9d, 3
0x18003aa89  mov     r8, rax
0x18003aa8c  lea     rdx, [r14+20h]
0x18003aa90  lea     rcx, [rbp+0F0h+var_170]
0x18003aa94  call    ??0DusmConnection@@QEAA@PEBU_GUID@@PEB_WW4_DUSM_MEDIA_TYPE@@1@Z; DusmConnection::DusmConnection(_GUID const *,wchar_t const *,_DUSM_MEDIA_TYPE,wchar_t const *)
0x18003aa99  nop
0x18003aa9a  mov     rcx, r14; this
0x18003aa9d  call    ?IsConnectionKeySet@DusmConnection@@QEBA_NXZ; DusmConnection::IsConnectionKeySet(void)
0x18003aaa2  test    al, al
0x18003aaa4  jnz     loc_18003AC3D
0x18003aaaa  lea     r8, [r14+20h]
0x18003aaae  lea     rdx, [rsp+1F0h+var_198]
0x18003aab3  call    ?QueryWwanSubscriberInfo@DusmWwan@@AEBA?AV?$unique_ptr@UWWAN_SUBSCRIBER_INFORMATION@@U?$function_deleter@P6AXPEAX@Z$1?WwanFreeMemory@@YAX0@Z@wil@@@wistd@@AEBU_GUID@@@Z; DusmWwan::QueryWwanSubscriberInfo(_GUID const &)
0x18003aab8  nop
0x18003aab9  mov     rdx, [rsp+1F0h+var_198]
0x18003aabe  add     rdx, 8
0x18003aac2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003aac6  mov     r8, rbx
0x18003aac9  inc     r8
0x18003aacc  cmp     [rdx+r8*2], r15w
0x18003aad1  jnz     short loc_18003AAC9
0x18003aad3  lea     rcx, [rbp+0F0h+var_100]
0x18003aad7  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18003aadc  mov     rdx, [rsp+1F0h+var_198]
0x18003aae1  add     rdx, 28h ; '('
0x18003aae5  inc     rbx
0x18003aae8  cmp     [rdx+rbx*2], r15w
0x18003aaed  jnz     short loc_18003AAE5
0x18003aaef  mov     r8, rbx
0x18003aaf2  lea     rcx, [rbp+0F0h+var_E0]
0x18003aaf6  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18003aafb  movaps  xmm0, [rbp+0F0h+var_150]
0x18003aaff  movdqu  xmmword ptr [rsp+1F0h+Uuid.Data1], xmm0
0x18003ab05  mov     [rsp+1F0h+StringUuid], r15
0x18003ab0a  lea     rdx, [rsp+1F0h+StringUuid]; StringUuid
0x18003ab0f  lea     rcx, [rsp+1F0h+Uuid]; Uuid
0x18003ab14  call    cs:__imp_UuidToStringW
0x18003ab1a  mov     edx, eax
0x18003ab1c  lea     rcx, [rbp+0F0h+var_100]
0x18003ab20  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003ab25  mov     r11, rax
0x18003ab28  lea     rcx, [rbp+0F0h+var_E0]
0x18003ab2c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003ab31  mov     r9, rax
0x18003ab34  lea     r10, aUuidtostringFa; "(UuidToString failed)"
0x18003ab3b  test    edx, edx
0x18003ab3d  cmovz   r10, [rsp+1F0h+StringUuid]
0x18003ab43  lea     rcx, [rbp+0F0h+var_140]
0x18003ab47  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003ab4c  mov     r8, rax
0x18003ab4f  lea     rcx, [rbp+0F0h+var_170]; this
0x18003ab53  call    ?IsConnectionKeySet@DusmConnection@@QEBA_NXZ; DusmConnection::IsConnectionKeySet(void)
0x18003ab58  xor     al, 1
0x18003ab5a  mov     rcx, [rbp+0F8h]; this
0x18003ab61  mov     [rsp+1F0h+var_1A8], r11
0x18003ab66  mov     [rsp+1F0h+var_1B0], r9
0x18003ab6b  mov     [rsp+1F0h+var_1B8], r10
0x18003ab70  mov     [rsp+1F0h+var_1C0], r8; char *
0x18003ab75  lea     rdx, aDusmwwanQueryc; "DusmWwan::QueryCost::QueryWwanSubscribe"...
0x18003ab7c  mov     qword ptr [rsp+1F0h+var_1C8], rdx; bool
0x18003ab81  mov     [rsp+1F0h+var_1D0], al; char
0x18003ab85  mov     r9d, 8000FFFFh; char *
0x18003ab8b  lea     r8, aOnecoreuapNetD_6; "onecoreuap\\net\\dusm\\lib\\dusmwwan.cp"...
0x18003ab92  mov     edx, 354h; void *
0x18003ab97  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18003ab9c  nop
0x18003ab9d  lea     rcx, [rsp+1F0h+StringUuid]
0x18003aba2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?WpRpcStringFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003aba7  nop
0x18003aba8  mov     rcx, [rsp+1F0h+var_198]
0x18003abad  mov     [rsp+1F0h+var_198], r15
0x18003abb2  test    rcx, rcx
0x18003abb5  jz      loc_18003AC5A
0x18003abbb  call    cs:__imp_WwanFreeMemory
0x18003abc1  jmp     loc_18003AC5A
0x18003abc6  mov     rdx, rdi
0x18003abc9  mov     ecx, 3
0x18003abce  call    ?QueryGpCost@DusmStore@@SAHW4_DUSM_MEDIA_TYPE@@PEAU_DUSM_CONNECTION_COST_DATA@@@Z; DusmStore::QueryGpCost(_DUSM_MEDIA_TYPE,_DUSM_CONNECTION_COST_DATA *)
0x18003abd3  mov     ebx, eax
0x18003abd5  test    eax, eax
0x18003abd7  jz      loc_18003AA64
0x18003abdd  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003abe2  mov     r8, [rax+8]
0x18003abe6  mov     ecx, [r8]
0x18003abe9  cmp     ecx, 4
0x18003abec  jbe     loc_18003AC8E
0x18003abf2  mov     edx, [rdi+4]
0x18003abf5  mov     dword ptr [rsp+1F0h+var_1A0], edx
0x18003abf9  mov     edx, [rdi]
0x18003abfb  mov     dword ptr [rsp+1F0h+StringUuid], edx
0x18003abff  mov     ecx, 1
0x18003ac04  call    ?DusmSourceToSz@@YAPEB_WW4_DUSM_SOURCE@@@Z; DusmSourceToSz(_DUSM_SOURCE)
0x18003ac09  mov     [rsp+1F0h+var_198], rax
0x18003ac0e  lea     rax, [rsp+1F0h+var_1A0]
0x18003ac13  mov     [rsp+1F0h+var_1C0], rax; __int64
0x18003ac18  lea     rax, [rsp+1F0h+StringUuid]
0x18003ac1d  mov     qword ptr [rsp+1F0h+var_1C8], rax; __int64
0x18003ac22  lea     rax, [rsp+1F0h+var_198]
0x18003ac27  mov     qword ptr [rsp+1F0h+var_1D0], rax; __int64
0x18003ac2c  lea     rdx, word_18005A2FA
0x18003ac33  mov     rcx, r8; int
0x18003ac36  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003ac3b  jmp     short loc_18003AC8E
0x18003ac3d  lea     rdx, [r14+90h]
0x18003ac44  lea     rcx, [rbp+0F0h+var_E0]
0x18003ac48  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003ac4d  lea     rdx, [r14+70h]
0x18003ac51  lea     rcx, [rbp+0F0h+var_100]
0x18003ac55  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003ac5a  cmp     esi, 1
0x18003ac5d  jnz     short loc_18003AC6A
0x18003ac5f  lea     rcx, [rbp+0F0h+var_170]
0x18003ac63  call    ?QuerySource@DusmStore@@SA?AW4_DUSM_SOURCE@@AEBVDusmConnection@@@Z; DusmStore::QuerySource(DusmConnection const &)
0x18003ac68  jmp     short loc_18003AC6C
0x18003ac6a  mov     eax, esi
0x18003ac6c  mov     r8, rdi
0x18003ac6f  mov     edx, eax
0x18003ac71  lea     rcx, [rbp+0F0h+var_170]
0x18003ac75  call    ?QueryCost@DusmStore@@SAHAEBVDusmConnection@@W4_DUSM_SOURCE@@PEAU_DUSM_CONNECTION_COST_DATA@@@Z; DusmStore::QueryCost(DusmConnection const &,_DUSM_SOURCE,_DUSM_CONNECTION_COST_DATA *)
0x18003ac7a  mov     ebx, eax
0x18003ac7c  lea     rcx, [rbp+0F0h+var_170]; this
0x18003ac80  call    ??1DusmConnection@@QEAA@XZ; DusmConnection::~DusmConnection(void)
0x18003ac85  cmp     esi, 1
0x18003ac88  jnz     short loc_18003ACC4
0x18003ac8a  test    ebx, ebx
0x18003ac8c  jz      short loc_18003AC93
0x18003ac8e  cmp     [rdi], r15d
0x18003ac91  jnz     short loc_18003ACC4
0x18003ac93  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003ac98  mov     rcx, [rax+8]
0x18003ac9c  mov     eax, [rcx]
0x18003ac9e  cmp     eax, 4
0x18003aca1  jbe     short loc_18003ACAF
0x18003aca3  lea     rdx, word_18005A37A
0x18003acaa  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18003acaf  mov     edx, 1
0x18003acb4  lea     ecx, [rdx+2]
0x18003acb7  call    ?QueryDefaultCost@DusmStore@@SA?AU_DUSM_CONNECTION_COST_DATA@@W4_DUSM_MEDIA_TYPE@@H@Z; DusmStore::QueryDefaultCost(_DUSM_MEDIA_TYPE,int)
0x18003acbc  mov     [rdi], rax
0x18003acbf  mov     ebx, 1
0x18003acc4  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003acc9  mov     r8, [rax+8]
0x18003accd  mov     eax, [r8]
0x18003acd0  cmp     eax, 4
0x18003acd3  jbe     short loc_18003AD29
0x18003acd5  mov     eax, [rdi+4]
0x18003acd8  mov     dword ptr [rsp+1F0h+StringUuid], eax
0x18003acdc  mov     eax, [rdi]
0x18003acde  mov     dword ptr [rsp+1F0h+var_1A0], eax
0x18003ace2  mov     dword ptr [rsp+1F0h+var_198], ebx
0x18003ace6  mov     ecx, esi
0x18003ace8  call    ?DusmSourceToSz@@YAPEB_WW4_DUSM_SOURCE@@@Z; DusmSourceToSz(_DUSM_SOURCE)
0x18003aced  mov     qword ptr [rsp+1F0h+Uuid.Data1], rax
0x18003acf2  lea     rax, [rsp+1F0h+StringUuid]
0x18003acf7  mov     [rsp+1F0h+var_1B8], rax; __int64
0x18003acfc  lea     rax, [rsp+1F0h+var_1A0]
0x18003ad01  mov     [rsp+1F0h+var_1C0], rax; __int64
0x18003ad06  lea     rax, [rsp+1F0h+var_198]
0x18003ad0b  mov     qword ptr [rsp+1F0h+var_1C8], rax; __int64
0x18003ad10  lea     rax, [rsp+1F0h+Uuid]
0x18003ad15  mov     qword ptr [rsp+1F0h+var_1D0], rax; __int64
0x18003ad1a  lea     rdx, byte_18005A17D
0x18003ad21  mov     rcx, r8; int
0x18003ad24  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003ad29  mov     eax, ebx
0x18003ad2b  mov     rcx, [rbp+0F0h+var_30]
0x18003ad32  xor     rcx, rsp; StackCookie
0x18003ad35  call    __security_check_cookie
0x18003ad3a  mov     rbx, [rsp+1F0h+arg_18]
0x18003ad42  add     rsp, 1D0h
0x18003ad49  pop     r15
0x18003ad4b  pop     r14
0x18003ad4d  pop     rdi
0x18003ad4e  pop     rsi
0x18003ad4f  pop     rbp
0x18003ad50  retn
0x18003ad51  mov     rcx, [rbp+0F8h]; this
0x18003ad58  lea     rax, aDusmwwanQueryc_0; "DusmWwan::QueryCost"
0x18003ad5f  mov     qword ptr [rsp+1F0h+var_1D0], rax; unsigned int
0x18003ad64  mov     r9d, 57h ; 'W'; char *
0x18003ad6a  lea     r8, aOnecoreuapNetD_6; "onecoreuap\\net\\dusm\\lib\\dusmwwan.cp"...
0x18003ad71  mov     edx, 32Ch; void *
0x18003ad76  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
