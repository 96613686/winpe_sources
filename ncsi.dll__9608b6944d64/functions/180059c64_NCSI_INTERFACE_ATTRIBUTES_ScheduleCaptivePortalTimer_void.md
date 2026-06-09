# NCSI_INTERFACE_ATTRIBUTES::ScheduleCaptivePortalTimer(void)

- ea: `0x180059c64`
- end: `0x180059e05`
- name: `?ScheduleCaptivePortalTimer@NCSI_INTERFACE_ATTRIBUTES@@AEAAXXZ`
- size: `417`
- prototype: `void __fastcall(NCSI_INTERFACE_ATTRIBUTES *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180058ff0`
- `0x18005a054`
- `0x18005a2b4`

## callees

- `0x1800045a0`
- `0x18000d188`
- `0x180021e64`
- `0x1800257b8`
- `0x18002e960`
- `0x180047240`
- `0x18004a110`
- `0x180055a68`
- `0x180055f34`
- `0x180059c64`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180059db1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180059db1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180059de5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180059de5`

## pseudocode

```c
void __fastcall NCSI_INTERFACE_ATTRIBUTES::ScheduleCaptivePortalTimer(NCSI_INTERFACE_ATTRIBUTES *this)
{
  NCSI_INTERFACE_ATTRIBUTES *v1; // rdi
  __int64 v2; // r8
  __int64 v3; // r9
  unsigned int *v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rcx
  DWORD v9; // esi
  void **v10; // rax
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v12; // r9
  struct _TP_TIMER *v13; // rcx
  __int64 v14; // [rsp+40h] [rbp-68h] BYREF
  int v15; // [rsp+48h] [rbp-60h] BYREF
  __int64 v16; // [rsp+50h] [rbp-58h] BYREF
  __int64 v17; // [rsp+58h] [rbp-50h] BYREF
  NCSI_INTERFACE_ATTRIBUTES *v18; // [rsp+60h] [rbp-48h]
  struct _FILETIME pftDueTime; // [rsp+68h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v1 = this;
  v18 = this;
  if ( Ncsi::Power::IsSystemInStandby(this) )
  {
    if ( (unsigned int)dword_18009A080 > 5 )
    {
      v14 = (__int64)"ScheduleCaptivePortalTimer - Bailing in standby";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (__int64)&dword_18009A080,
        (unsigned __int8 *)word_18008764A,
        v2,
        v3,
        (const unsigned __int16 **)&v14);
    }
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      (char *)v1 + 12848,
      0);
  }
  else
  {
    v4 = (unsigned int *)((char *)v1 + 12856);
    if ( (unsigned int)dword_18009A080 > 5 )
    {
      v15 = *v4;
      LODWORD(v14) = NCSI_INTERFACE_ATTRIBUTES::GetIfaceType(v1);
      v17 = *(_QWORD *)v1;
      v16 = (__int64)v1 + 8;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v5,
        (int)&word_1800875C6,
        v6,
        v7,
        &v16,
        (__int64)&v17,
        (__int64)&v14,
        (__int64)&v15);
    }
    v8 = *v4;
    v14 = -10000000 * v8;
    pftDueTime = (struct _FILETIME)(-10000000 * v8);
    v9 = 300;
    if ( (unsigned int)(250 * v8) > 0x12C )
      v9 = 250 * v8;
    LODWORD(v14) = v9;
    if ( !*((_QWORD *)v1 + 1606) )
    {
      try
      {
        v10 = (void **)std::make_unique<_NET_LUID_LH,_NET_LUID_LH &,0>(&v16, v1);
        std::unique_ptr<_NET_LUID_LH>::operator=<std::default_delete<_NET_LUID_LH>,0>((void **)v1 + 1605, v10);
        std::unique_ptr<_NET_LUID_LH>::~unique_ptr<_NET_LUID_LH>(&v16);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            NCSI_INTERFACE_ATTRIBUTES::NcsiCaptivePortalTimerExpireCallback,
                            *((PVOID *)v1 + 1605),
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          (char *)v1 + 12848,
          ThreadpoolTimer);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x332,
          (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\interfaceattributes.cpp",
          v12);
        v9 = v14;
        v1 = v18;
      }
    }
    v13 = (struct _TP_TIMER *)*((_QWORD *)v1 + 1606);
    if ( v13 )
      SetThreadpoolTimer(v13, &pftDueTime, 0, v9);
  }
}

```

## disassembly

```asm
0x180059c64  push    rbx
0x180059c66  push    rsi
0x180059c67  push    rdi
0x180059c68  push    r14
0x180059c6a  sub     rsp, 88h
0x180059c71  mov     rax, cs:__security_cookie
0x180059c78  xor     rax, rsp
0x180059c7b  mov     [rsp+0A8h+var_38], rax
0x180059c80  mov     rdi, rcx
0x180059c83  mov     [rsp+0A8h+var_48], rcx
0x180059c88  call    ?IsSystemInStandby@Power@Ncsi@@YA_NXZ; Ncsi::Power::IsSystemInStandby(void)
0x180059c8d  test    al, al
0x180059c8f  mov     eax, cs:dword_18009A080
0x180059c95  jz      short loc_180059CD8
0x180059c97  cmp     eax, 5
0x180059c9a  jbe     short loc_180059CC5
0x180059c9c  lea     rax, aSchedulecaptiv; "ScheduleCaptivePortalTimer - Bailing in"...
0x180059ca3  mov     [rsp+0A8h+var_68], rax
0x180059ca8  lea     rax, [rsp+0A8h+var_68]
0x180059cad  mov     [rsp+0A8h+var_88], rax
0x180059cb2  lea     rdx, word_18008764A
0x180059cb9  lea     rcx, dword_18009A080
0x180059cc0  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180059cc5  lea     rcx, [rdi+3230h]
0x180059ccc  xor     edx, edx
0x180059cce  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180059cd3  jmp     loc_180059DEB
0x180059cd8  lea     rbx, [rdi+3238h]
0x180059cdf  cmp     eax, 5
0x180059ce2  jbe     short loc_180059D3B
0x180059ce4  mov     eax, [rbx]
0x180059ce6  mov     [rsp+0A8h+var_60], eax
0x180059cea  mov     rcx, rdi; this
0x180059ced  call    ?GetIfaceType@NCSI_INTERFACE_ATTRIBUTES@@QEBA?BKXZ; NCSI_INTERFACE_ATTRIBUTES::GetIfaceType(void)
0x180059cf2  mov     dword ptr [rsp+0A8h+var_68], eax
0x180059cf6  mov     rax, [rdi]
0x180059cf9  mov     [rsp+0A8h+var_50], rax
0x180059cfe  lea     rax, [rdi+8]
0x180059d02  mov     [rsp+0A8h+var_58], rax
0x180059d07  lea     rax, [rsp+0A8h+var_60]
0x180059d0c  mov     [rsp+0A8h+var_70], rax
0x180059d11  lea     rax, [rsp+0A8h+var_68]
0x180059d16  mov     [rsp+0A8h+var_78], rax
0x180059d1b  lea     rax, [rsp+0A8h+var_50]
0x180059d20  mov     [rsp+0A8h+var_80], rax
0x180059d25  lea     rax, [rsp+0A8h+var_58]
0x180059d2a  mov     [rsp+0A8h+var_88], rax
0x180059d2f  lea     rdx, word_1800875C6
0x180059d36  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180059d3b  mov     ecx, [rbx]
0x180059d3d  imul    rax, rcx, 0FFFFFFFFFF676980h
0x180059d44  mov     dword ptr [rsp+0A8h+var_68], eax
0x180059d48  shr     rax, 20h
0x180059d4c  mov     dword ptr [rsp+0A8h+var_68+4], eax
0x180059d50  mov     rax, [rsp+0A8h+var_68]
0x180059d55  mov     qword ptr [rsp+0A8h+pftDueTime.dwLowDateTime], rax
0x180059d5a  imul    eax, ecx, 0FAh
0x180059d60  mov     esi, 12Ch
0x180059d65  cmp     eax, esi
0x180059d67  cmova   esi, eax
0x180059d6a  mov     dword ptr [rsp+0A8h+var_68], esi
0x180059d6e  lea     r14, [rdi+3230h]
0x180059d75  cmp     qword ptr [r14], 0
0x180059d79  jnz     short loc_180059DCE
0x180059d7b  mov     rdx, rdi
0x180059d7e  lea     rcx, [rsp+0A8h+var_58]
0x180059d83  call    ??$make_unique@T_NET_LUID_LH@@AEAT1@$0A@@std@@YA?AV?$unique_ptr@T_NET_LUID_LH@@U?$default_delete@T_NET_LUID_LH@@@std@@@0@AEAT_NET_LUID_LH@@@Z; std::make_unique<_NET_LUID_LH,_NET_LUID_LH &,0>(_NET_LUID_LH &)
0x180059d88  lea     rbx, [rdi+3228h]
0x180059d8f  mov     rdx, rax
0x180059d92  mov     rcx, rbx
0x180059d95  call    ??$?4U?$default_delete@T_NET_LUID_LH@@@std@@$0A@@?$unique_ptr@T_NET_LUID_LH@@U?$default_delete@T_NET_LUID_LH@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<_NET_LUID_LH>::operator=<std::default_delete<_NET_LUID_LH>,0>(std::unique_ptr<_NET_LUID_LH> &&)
0x180059d9a  lea     rcx, [rsp+0A8h+var_58]
0x180059d9f  call    ??1?$unique_ptr@T_NET_LUID_LH@@U?$default_delete@T_NET_LUID_LH@@@std@@@std@@QEAA@XZ; std::unique_ptr<_NET_LUID_LH>::~unique_ptr<_NET_LUID_LH>(void)
0x180059da4  xor     r8d, r8d; pcbe
0x180059da7  mov     rdx, [rbx]; pv
0x180059daa  lea     rcx, ?NcsiCaptivePortalTimerExpireCallback@NCSI_INTERFACE_ATTRIBUTES@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180059db1  call    cs:__imp_CreateThreadpoolTimer
0x180059db7  mov     rdx, rax
0x180059dba  mov     rcx, r14
0x180059dbd  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180059dc2  nop
0x180059dc3  jmp     short loc_180059DCE
0x180059dc5  mov     esi, dword ptr [rsp+0A8h+var_68]
0x180059dc9  mov     rdi, [rsp+0A8h+var_48]
0x180059dce  mov     rcx, [rdi+3230h]; pti
0x180059dd5  test    rcx, rcx
0x180059dd8  jz      short loc_180059DEB
0x180059dda  mov     r9d, esi; msWindowLength
0x180059ddd  xor     r8d, r8d; msPeriod
0x180059de0  lea     rdx, [rsp+0A8h+pftDueTime]; pftDueTime
0x180059de5  call    cs:__imp_SetThreadpoolTimer
0x180059deb  mov     rcx, [rsp+0A8h+var_38]
0x180059df0  xor     rcx, rsp; StackCookie
0x180059df3  call    __security_check_cookie
0x180059df8  add     rsp, 88h
0x180059dff  pop     r14
0x180059e01  pop     rdi
0x180059e02  pop     rsi
0x180059e03  pop     rbx
0x180059e04  retn
```
