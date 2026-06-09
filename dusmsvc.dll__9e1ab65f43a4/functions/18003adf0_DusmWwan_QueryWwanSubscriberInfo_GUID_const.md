# DusmWwan::QueryWwanSubscriberInfo(_GUID const &)

- ea: `0x18003adf0`
- end: `0x18003b026`
- name: `?QueryWwanSubscriberInfo@DusmWwan@@AEBA?AV?$unique_ptr@UWWAN_SUBSCRIBER_INFORMATION@@U?$function_deleter@P6AXPEAX@Z$1?WwanFreeMemory@@YAX0@Z@wil@@@wistd@@AEBU_GUID@@@Z`
- size: `566`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003aa18`
- `0x18003b33c`
- `0x18003b814`
- `0x18003be1c`

## callees

- `0x180001010`
- `0x1800020fc`
- `0x18000438c`
- `0x180007c90`
- `0x18000ca00`
- `0x18000f094`
- `0x180012368`
- `0x180013444`
- `0x1800397b4`
- `0x18003adf0`
- `0x18003b64c`
- `0x18003b6b4`
- `0x180043f48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ae43`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ae43`
- `wwapi!WwanQueryInterface` at `0x18003ae94`
- `wwapi!WwanQueryInterface` at `0x18003ae94`

## string_xrefs

- `0x18003afd9`: `DusmWwan::QueryWwanSubscriberInfo - StringCchCopyW failed to copy defaultSubscriberId`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 *__fastcall DusmWwan::QueryWwanSubscriberInfo(__int64 a1, __int64 *a2, __int64 a3)
{
  DusmWwan *v5; // rdi
  __int64 *v6; // rcx
  __int64 v7; // rbx
  __int64 v8; // rcx
  unsigned int Interface; // eax
  __int64 v10; // rcx
  int v11; // edx
  char v12; // cf
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rax
  _DWORD *v16; // r8
  __int64 v17; // r8
  __int64 v18; // r9
  _DWORD *v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  unsigned int v22; // eax
  char *v24; // [rsp+28h] [rbp-31h]
  char *v25; // [rsp+30h] [rbp-29h]
  __int64 v26; // [rsp+38h] [rbp-21h]
  __int64 v27; // [rsp+48h] [rbp-11h] BYREF
  char *v28; // [rsp+50h] [rbp-9h] BYREF
  __int64 *v29; // [rsp+58h] [rbp-1h] BYREF
  char v30[8]; // [rsp+60h] [rbp+7h] BYREF
  char v31; // [rsp+68h] [rbp+Fh]
  __int64 *v32; // [rsp+70h] [rbp+17h]
  char *v33; // [rsp+78h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v32 = a2;
  v5 = DusmWwan::s_pInstance;
  *a2 = 0;
  LODWORD(v33) = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v5 + 24));
  v28 = (char *)v5 + 24;
  v29 = a2;
  *(_QWORD *)v30 = 0;
  v31 = 1;
  v6 = (__int64 *)*((_QWORD *)v5 + 8);
  v7 = -1;
  if ( v6 )
    v8 = *v6;
  else
    v8 = -1;
  Interface = WwanQueryInterface(v8, a3, 36);
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x174,
    (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmwwan.cpp",
    (const char *)Interface,
    (unsigned int)"DusmWwan::QueryWwanSubscriberInfo::WwanQueryInterface",
    v30,
    0,
    0,
    1);
  wil::details::out_param_ptr_t<unsigned char * *,wistd::unique_ptr<WWAN_INTERFACE_OBJECT,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>::~out_param_ptr_t<unsigned char * *,wistd::unique_ptr<WWAN_INTERFACE_OBJECT,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>(&v29);
  v11 = (int)v33;
  v12 = (unsigned int)v33 < 0x5C;
  if ( (unsigned int)v33 < 0x5C )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v10);
    v11 = (int)v33;
    v12 = (unsigned int)v33 < 0x5C;
  }
  LODWORD(v26) = 92;
  LODWORD(v25) = v11;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x17C,
    (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmwwan.cpp",
    (const char *)0x8000FFFFLL,
    v12,
    (bool)"DusmWwan::QueryWwanSubscriberInfo::WwanQueryInterface - dataSize(%ul) is smaller than that of WWAN_SUBSCRIBER_"
          "INFORMATION(%ul)",
    v25,
    v26);
  v14 = *a2;
  if ( *(_DWORD *)*a2 == 1 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)(v14 + 2 * v15 + 40) );
    if ( !v15 )
    {
      v16 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v14, v13) + 8);
      if ( *v16 > 5u )
      {
        if ( (unsigned __int8)tlgKeywordOn(v16, 0x200000000000LL) )
        {
          v27 = 2048;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
            v17,
            (int)byte_18005AEED,
            v17,
            v18,
            (__int64)&v27);
        }
      }
    }
    do
      ++v7;
    while ( *(_WORD *)(*a2 + 2 * v7 + 8) );
    if ( !v7 )
    {
      v19 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v14, v13) + 8);
      if ( *v19 > 3u )
      {
        v27 = *a2 + 40;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
          (int)v19,
          (int)&word_18005AE36,
          v20,
          v21,
          (const WCHAR **)&v27);
      }
      v22 = StringCchCopyW((wchar_t *)(*a2 + 8), 0x10u, L"FFFFFFFFFFFFFFF");
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x193,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmwwan.cpp",
        (const char *)v22,
        (int)"DusmWwan::QueryWwanSubscriberInfo - StringCchCopyW failed to copy defaultSubscriberId",
        v24);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v28);
  return a2;
}

```

## disassembly

```asm
0x18003adf0  mov     [rsp-8+arg_0], rbx
0x18003adf5  push    rbp
0x18003adf6  push    rsi
0x18003adf7  push    rdi
0x18003adf8  push    r14
0x18003adfa  push    r15
0x18003adfc  lea     rbp, [rsp-37h]
0x18003ae01  sub     rsp, 90h
0x18003ae08  mov     rax, cs:__security_cookie
0x18003ae0f  xor     rax, rsp
0x18003ae12  mov     [rbp+57h+var_30], rax
0x18003ae16  mov     r14, r8
0x18003ae19  mov     rsi, rdx
0x18003ae1c  mov     [rbp+57h+var_40], rdx
0x18003ae20  xor     r15d, r15d
0x18003ae23  mov     [rbp+57h+var_70], r15d
0x18003ae27  mov     rdi, cs:?s_pInstance@DusmWwan@@0PEAV1@EA; DusmWwan * DusmWwan::s_pInstance
0x18003ae2e  mov     [rdx], r15
0x18003ae31  mov     [rbp+57h+var_70], 1
0x18003ae38  mov     dword ptr [rbp+57h+var_38], r15d
0x18003ae3c  lea     rbx, [rdi+18h]
0x18003ae40  mov     rcx, rbx; lpCriticalSection
0x18003ae43  call    cs:__imp_EnterCriticalSection
0x18003ae49  mov     [rbp+57h+var_60], rbx
0x18003ae4d  mov     [rbp+57h+var_58], rsi
0x18003ae51  mov     qword ptr [rbp+57h+var_50], r15
0x18003ae55  mov     [rbp+57h+var_48], 1
0x18003ae59  mov     rcx, [rdi+40h]
0x18003ae5d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003ae61  test    rcx, rcx
0x18003ae64  jz      short loc_18003AE6B
0x18003ae66  mov     rcx, [rcx]
0x18003ae69  jmp     short loc_18003AE6E
0x18003ae6b  mov     rcx, rbx
0x18003ae6e  mov     [rsp+0B0h+var_78], r15
0x18003ae73  mov     [rsp+0B0h+var_80], r15
0x18003ae78  lea     rax, [rbp+57h+var_50]
0x18003ae7c  mov     [rsp+0B0h+var_88], rax; char *
0x18003ae81  lea     rax, [rbp+57h+var_38]
0x18003ae85  mov     qword ptr [rsp+0B0h+var_90], rax
0x18003ae8a  xor     r9d, r9d
0x18003ae8d  lea     r8d, [r9+24h]
0x18003ae91  mov     rdx, r14
0x18003ae94  call    cs:__imp_WwanQueryInterface
0x18003ae9a  mov     r9d, eax; char *
0x18003ae9d  mov     rcx, [rbp+5Fh]; this
0x18003aea1  lea     rax, aDusmwwanQueryw_1; "DusmWwan::QueryWwanSubscriberInfo::Wwan"...
0x18003aea8  mov     qword ptr [rsp+0B0h+var_90], rax; unsigned int
0x18003aead  lea     rdi, aOnecoreuapNetD_6; "onecoreuap\\net\\dusm\\lib\\dusmwwan.cp"...
0x18003aeb4  mov     r8, rdi; unsigned int
0x18003aeb7  mov     edx, 174h; void *
0x18003aebc  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18003aec1  nop
0x18003aec2  lea     rcx, [rbp+57h+var_58]
0x18003aec6  call    ??1?$out_param_ptr_t@PEAPEAEV?$unique_ptr@UWWAN_INTERFACE_OBJECT@@U?$function_deleter@P6AXPEAX@Z$1?WwanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<uchar * *,wistd::unique_ptr<WWAN_INTERFACE_OBJECT,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>::~out_param_ptr_t<uchar * *,wistd::unique_ptr<WWAN_INTERFACE_OBJECT,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>(void)
0x18003aecb  mov     edx, dword ptr [rbp+57h+var_38]
0x18003aece  cmp     edx, 5Ch ; '\'
0x18003aed1  jnb     short loc_18003AEDE
0x18003aed3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003aed8  mov     edx, dword ptr [rbp+57h+var_38]
0x18003aedb  cmp     edx, 5Ch ; '\'
0x18003aede  setb    al
0x18003aee1  mov     rcx, [rbp+5Fh]; this
0x18003aee5  mov     dword ptr [rsp+0B0h+var_78], 5Ch ; '\'
0x18003aeed  mov     dword ptr [rsp+0B0h+var_80], edx; char *
0x18003aef1  lea     rdx, aDusmwwanQueryw; "DusmWwan::QueryWwanSubscriberInfo::Wwan"...
0x18003aef8  mov     [rsp+0B0h+var_88], rdx; char *
0x18003aefd  mov     [rsp+0B0h+var_90], al; char
0x18003af01  mov     r9d, 8000FFFFh; char *
0x18003af07  mov     r8, rdi; unsigned int
0x18003af0a  mov     edx, 17Ch; void *
0x18003af0f  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18003af14  mov     rcx, [rsi]
0x18003af17  cmp     dword ptr [rcx], 1
0x18003af1a  jnz     loc_18003AFF6
0x18003af20  mov     rax, rbx
0x18003af23  inc     rax
0x18003af26  cmp     [rcx+rax*2+28h], r15w
0x18003af2c  jnz     short loc_18003AF23
0x18003af2e  test    rax, rax
0x18003af31  jnz     short loc_18003AF7A
0x18003af33  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003af38  mov     r8, [rax+8]
0x18003af3c  mov     eax, [r8]
0x18003af3f  cmp     eax, 5
0x18003af42  jbe     short loc_18003AF7A
0x18003af44  mov     rdx, 200000000000h
0x18003af4e  mov     rcx, r8
0x18003af51  call    _tlgKeywordOn
0x18003af56  test    al, al
0x18003af58  jz      short loc_18003AF7A
0x18003af5a  mov     [rbp+57h+var_68], 800h
0x18003af62  lea     rax, [rbp+57h+var_68]
0x18003af66  mov     qword ptr [rsp+0B0h+var_90], rax
0x18003af6b  lea     rdx, byte_18005AEED
0x18003af72  mov     rcx, r8
0x18003af75  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18003af7a  mov     rax, [rsi]
0x18003af7d  inc     rbx
0x18003af80  cmp     [rax+rbx*2+8], r15w
0x18003af86  jnz     short loc_18003AF7D
0x18003af88  test    rbx, rbx
0x18003af8b  jnz     short loc_18003AFF6
0x18003af8d  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003af92  mov     rcx, [rax+8]
0x18003af96  mov     eax, [rcx]
0x18003af98  cmp     eax, 3
0x18003af9b  jbe     short loc_18003AFBD
0x18003af9d  mov     rax, [rsi]
0x18003afa0  add     rax, 28h ; '('
0x18003afa4  mov     [rbp+57h+var_68], rax
0x18003afa8  lea     rax, [rbp+57h+var_68]
0x18003afac  mov     qword ptr [rsp+0B0h+var_90], rax
0x18003afb1  lea     rdx, word_18005AE36
0x18003afb8  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18003afbd  mov     rcx, [rsi]
0x18003afc0  add     rcx, 8; wchar_t *
0x18003afc4  lea     r8, aFfffffffffffff; "FFFFFFFFFFFFFFF"
0x18003afcb  mov     edx, 10h; unsigned __int64
0x18003afd0  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18003afd5  mov     rcx, [rbp+5Fh]; this
0x18003afd9  lea     rdx, aDusmwwanQueryw_0; "DusmWwan::QueryWwanSubscriberInfo - Str"...
0x18003afe0  mov     qword ptr [rsp+0B0h+var_90], rdx; int
0x18003afe5  mov     r9d, eax; char *
0x18003afe8  mov     r8, rdi; unsigned int
0x18003afeb  mov     edx, 193h; void *
0x18003aff0  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003aff5  nop
0x18003aff6  lea     rcx, [rbp+57h+var_60]
0x18003affa  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18003afff  mov     rax, rsi
0x18003b002  mov     rcx, [rbp+57h+var_30]
0x18003b006  xor     rcx, rsp; StackCookie
0x18003b009  call    __security_check_cookie
0x18003b00e  mov     rbx, [rsp+0B0h+arg_0]
0x18003b016  add     rsp, 90h
0x18003b01d  pop     r15
0x18003b01f  pop     r14
0x18003b021  pop     rdi
0x18003b022  pop     rsi
0x18003b023  pop     rbp
0x18003b024  retn
```
