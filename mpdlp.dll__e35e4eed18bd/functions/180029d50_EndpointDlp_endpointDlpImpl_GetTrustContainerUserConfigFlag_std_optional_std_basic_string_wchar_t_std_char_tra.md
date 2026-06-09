# EndpointDlp::endpointDlpImpl::GetTrustContainerUserConfigFlag(std::optional<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>> const &)

- ea: `0x180029d50`
- end: `0x18002a017`
- name: `?GetTrustContainerUserConfigFlag@endpointDlpImpl@EndpointDlp@@QEBA_NAEBV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@Z`
- size: `711`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180029850`

## callees

- `0x1800058a4`
- `0x180028d80`
- `0x180029d50`
- `0x18002a3a0`
- `0x1800301a0`
- `0x18004bc70`
- `0x1800a04b4`
- `0x18010b558`
- `0x18010b568`
- `0x18010d1e0`
- `0x18010d310`
- `0x18010d380`
- `0x18023a290`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180029e1a`
- `KERNEL32!CompareStringOrdinal` at `0x180029e69`
- `KERNEL32!CompareStringOrdinal` at `0x180029e1a`
- `KERNEL32!CompareStringOrdinal` at `0x180029e69`
- `KERNEL32!AcquireSRWLockShared` at `0x180029d77`
- `KERNEL32!AcquireSRWLockShared` at `0x180029d77`
- `KERNEL32!ReleaseSRWLockShared` at `0x180029ead`
- `KERNEL32!ReleaseSRWLockShared` at `0x180029ead`

## string_xrefs

- `0x180029ef3`: `Call to GetTrustContainerUserConfigFlag before Initialization`
- `0x180029fb6`: `GetTrustContainerUserConfigFlag failed to get SID.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
char __fastcall EndpointDlp::endpointDlpImpl::GetTrustContainerUserConfigFlag(__int64 a1, __int64 *a2)
{
  RTL_SRWLOCK *v4; // r12
  volatile signed __int32 *v5; // r15
  __int64 v6; // r13
  __int64 *v7; // rsi
  __int64 *v8; // rbx
  const WCHAR *v9; // rcx
  const WCHAR *v10; // r8
  int v11; // eax
  __int64 *v12; // rcx
  const WCHAR *v13; // r8
  char v14; // bl
  struct EndpointDlp::TraceLoggingProvider *v16; // rax
  int v17; // r8d
  int v18; // r9d
  _DWORD *v19; // rcx
  struct EndpointDlp::TraceLoggingProvider *v20; // rax
  int v21; // r8d
  int v22; // r9d
  _DWORD *v23; // rcx
  int v24; // [rsp+30h] [rbp-68h] BYREF
  const wchar_t *v25; // [rsp+38h] [rbp-60h] BYREF
  RTL_SRWLOCK *v26; // [rsp+40h] [rbp-58h] BYREF
  int v27; // [rsp+5Ch] [rbp-3Ch]

  v4 = (RTL_SRWLOCK *)(a1 + 368);
  AcquireSRWLockShared((PSRWLOCK)(a1 + 368));
  v26 = v4;
  if ( !*(_BYTE *)(a1 + 376) )
  {
    v16 = EndpointDlp::TraceLoggingProvider::Instance();
    v19 = *(_DWORD **)v16;
    if ( **(_DWORD **)v16 > 2u )
    {
      v25 = L"Call to GetTrustContainerUserConfigFlag before Initialization";
      v24 = -2147023782;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        (_DWORD)v19,
        (unsigned int)byte_1802C198D,
        v17,
        v18,
        (__int64)&v24,
        (__int64)&v25);
    }
    goto LABEL_34;
  }
  if ( !*((_BYTE *)a2 + 32) )
  {
    if ( dword_180314328 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 108LL)
      && (Init_thread_header(&dword_180314328), dword_180314328 == -1) )
    {
      a2 = qword_180314300;
      EndpointDlp::Common::GetUserSidForCurrentProcess(qword_180314300);
      atexit(EndpointDlp::_anonymous_namespace_::GetEffectiveUserSid_::_2_::_dynamic_atexit_destructor_for__currentProcessSid__);
      Init_thread_footer(&dword_180314328);
    }
    else
    {
      a2 = qword_180314300;
    }
    if ( !LOBYTE(qword_180314300[4]) )
    {
      v20 = EndpointDlp::TraceLoggingProvider::Instance();
      v23 = *(_DWORD **)v20;
      if ( **(_DWORD **)v20 > 2u )
      {
        v25 = L"GetTrustContainerUserConfigFlag failed to get SID.";
        v24 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          (_DWORD)v23,
          (unsigned int)qword_1802BEB20,
          v21,
          v22,
          (__int64)&v24,
          (__int64)&v25);
      }
LABEL_34:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v26);
      return 0;
    }
  }
  Lock_shared_ptr_spin_lock();
  v5 = (volatile signed __int32 *)qword_180314278;
  if ( qword_180314278 )
  {
    _InterlockedIncrement((volatile signed __int32 *)qword_180314278 + 2);
    v5 = (volatile signed __int32 *)qword_180314278;
  }
  v6 = qword_180314270;
  Unlock_shared_ptr_spin_lock();
  if ( v6 )
  {
    if ( !a2[2] )
      goto LABEL_24;
    v7 = *(__int64 **)v6;
    v8 = *(__int64 **)(*(_QWORD *)v6 + 8LL);
    v27 = 0;
    if ( !*((_BYTE *)v8 + 25) )
    {
      do
      {
        v9 = (const WCHAR *)(v8 + 4);
        v10 = (const WCHAR *)a2;
        if ( (unsigned __int64)a2[3] > 7 )
          v10 = (const WCHAR *)*a2;
        if ( (unsigned __int64)v8[7] > 7 )
          v9 = *(const WCHAR **)v9;
        v11 = CompareStringOrdinal(v9, -1, v10, -1, 1);
        if ( v11 != 1 )
          v7 = v8;
        v12 = v8 + 2;
        if ( v11 != 1 )
          v12 = v8;
        v8 = (__int64 *)*v12;
      }
      while ( !*(_BYTE *)(*v12 + 25) );
    }
    if ( *((_BYTE *)v7 + 25) )
      goto LABEL_24;
    v13 = (const WCHAR *)(v7 + 4);
    if ( (unsigned __int64)v7[7] > 7 )
      v13 = *(const WCHAR **)v13;
    if ( (unsigned __int64)a2[3] > 7 )
      a2 = (__int64 *)*a2;
    if ( CompareStringOrdinal((LPCWCH)a2, -1, v13, -1, 1) == 1 || v7 == *(__int64 **)v6 )
LABEL_24:
      v14 = 0;
    else
      v14 = *((_BYTE *)v7 + 75);
    if ( v5 && _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v5);
    }
  }
  else
  {
    if ( v5 )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v5);
    v14 = 0;
  }
  if ( v4 )
    ReleaseSRWLockShared(v4);
  return v14;
}

```

## disassembly

```asm
0x180029d50  mov     [rsp+arg_10], rbx
0x180029d55  mov     [rsp+arg_18], rsi
0x180029d5a  push    rdi
0x180029d5b  push    r12
0x180029d5d  push    r13
0x180029d5f  push    r14
0x180029d61  push    r15
0x180029d63  sub     rsp, 70h
0x180029d67  mov     rdi, rdx
0x180029d6a  mov     rbx, rcx
0x180029d6d  lea     r12, [rcx+170h]
0x180029d74  mov     rcx, r12; SRWLock
0x180029d77  call    cs:__imp_AcquireSRWLockShared
0x180029d7d  mov     [rsp+98h+var_58], r12
0x180029d82  cmp     byte ptr [rbx+178h], 0
0x180029d89  jz      loc_180029EE6
0x180029d8f  cmp     byte ptr [rdi+20h], 0
0x180029d93  jz      loc_180029F36
0x180029d99  call    _Lock_shared_ptr_spin_lock
0x180029d9e  mov     r15, cs:qword_180314278
0x180029da5  test    r15, r15
0x180029da8  jz      short loc_180029DB6
0x180029daa  lock inc dword ptr [r15+8]
0x180029daf  mov     r15, cs:qword_180314278
0x180029db6  mov     r13, cs:qword_180314270
0x180029dbd  call    _Unlock_shared_ptr_spin_lock
0x180029dc2  test    r13, r13
0x180029dc5  jz      loc_180029FFC
0x180029dcb  mov     r14d, 0FFFFFFFFh
0x180029dd1  cmp     qword ptr [rdi+10h], 0
0x180029dd6  jz      loc_180029E7A
0x180029ddc  mov     rsi, [r13+0]
0x180029de0  mov     rbx, [rsi+8]
0x180029de4  xor     eax, eax
0x180029de6  mov     [rsp+98h+var_3C], eax
0x180029dea  cmp     [rbx+19h], al
0x180029ded  jnz     short loc_180029E39
0x180029def  nop
0x180029df0  lea     rcx, [rbx+20h]; lpString1
0x180029df4  mov     r8, rdi
0x180029df7  cmp     qword ptr [rdi+18h], 7
0x180029dfc  jbe     short loc_180029E01
0x180029dfe  mov     r8, [rdi]; lpString2
0x180029e01  cmp     qword ptr [rcx+18h], 7
0x180029e06  ja      loc_180029ED0
0x180029e0c  mov     [rsp+98h+bIgnoreCase], 1; bIgnoreCase
0x180029e14  mov     r9d, r14d; cchCount2
0x180029e17  mov     edx, r14d; cchCount1
0x180029e1a  call    cs:__imp_CompareStringOrdinal
0x180029e20  cmp     eax, 1
0x180029e23  jz      short loc_180029E28
0x180029e25  mov     rsi, rbx
0x180029e28  lea     rcx, [rbx+10h]
0x180029e2c  cmovnz  rcx, rbx
0x180029e30  mov     rbx, [rcx]
0x180029e33  cmp     byte ptr [rbx+19h], 0
0x180029e37  jz      short loc_180029DF0
0x180029e39  cmp     byte ptr [rsi+19h], 0
0x180029e3d  jnz     short loc_180029E7A
0x180029e3f  lea     r8, [rsi+20h]
0x180029e43  cmp     qword ptr [r8+18h], 7
0x180029e48  jbe     short loc_180029E4D
0x180029e4a  mov     r8, [r8]; lpString2
0x180029e4d  cmp     qword ptr [rdi+18h], 7
0x180029e52  ja      loc_180029EDE
0x180029e58  mov     [rsp+98h+bIgnoreCase], 1; bIgnoreCase
0x180029e60  mov     r9d, r14d; cchCount2
0x180029e63  mov     edx, r14d; cchCount1
0x180029e66  mov     rcx, rdi; lpString1
0x180029e69  call    cs:__imp_CompareStringOrdinal
0x180029e6f  cmp     eax, 1
0x180029e72  jz      short loc_180029E7A
0x180029e74  cmp     rsi, [r13+0]
0x180029e78  jnz     short loc_180029ED8
0x180029e7a  xor     bl, bl
0x180029e7c  test    r15, r15
0x180029e7f  jz      short loc_180029EA5
0x180029e81  lock xadd [r15+8], r14d
0x180029e87  cmp     r14d, 1
0x180029e8b  jnz     short loc_180029EA5
0x180029e8d  mov     rax, [r15]
0x180029e90  mov     rcx, r15
0x180029e93  mov     rax, [rax]
0x180029e96  call    cs:__guard_dispatch_icall_fptr
0x180029e9c  mov     rcx, r15; this
0x180029e9f  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180029ea4  nop
0x180029ea5  test    r12, r12
0x180029ea8  jz      short loc_180029EB3
0x180029eaa  mov     rcx, r12; SRWLock
0x180029ead  call    cs:__imp_ReleaseSRWLockShared
0x180029eb3  movzx   eax, bl
0x180029eb6  lea     r11, [rsp+98h+var_28]
0x180029ebb  mov     rbx, [r11+40h]
0x180029ebf  mov     rsi, [r11+48h]
0x180029ec3  mov     rsp, r11
0x180029ec6  pop     r15
0x180029ec8  pop     r14
0x180029eca  pop     r13
0x180029ecc  pop     r12
0x180029ece  pop     rdi
0x180029ecf  retn
0x180029ed0  mov     rcx, [rcx]
0x180029ed3  jmp     loc_180029E0C
0x180029ed8  movzx   ebx, byte ptr [rsi+4Bh]
0x180029edc  jmp     short loc_180029E7C
0x180029ede  mov     rdi, [rdi]
0x180029ee1  jmp     loc_180029E58
0x180029ee6  call    ?Instance@TraceLoggingProvider@EndpointDlp@@SAAEAV12@XZ; EndpointDlp::TraceLoggingProvider::Instance(void)
0x180029eeb  mov     rcx, [rax]
0x180029eee  cmp     dword ptr [rcx], 2
0x180029ef1  jbe     short loc_180029F28
0x180029ef3  lea     rax, aCallToGettrust; "Call to GetTrustContainerUserConfigFlag"...
0x180029efa  mov     [rsp+98h+var_60], rax
0x180029eff  mov     [rsp+98h+var_68], 8007045Ah
0x180029f07  lea     rax, [rsp+98h+var_60]
0x180029f0c  mov     [rsp+98h+var_70], rax
0x180029f11  lea     rax, [rsp+98h+var_68]
0x180029f16  mov     qword ptr [rsp+98h+bIgnoreCase], rax
0x180029f1b  lea     rdx, byte_1802C198D
0x180029f22  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180029f27  nop
0x180029f28  lea     rcx, [rsp+98h+var_58]
0x180029f2d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180029f32  xor     al, al
0x180029f34  jmp     short loc_180029EB6
0x180029f36  mov     ecx, cs:_tls_index
0x180029f3c  mov     rax, gs:58h
0x180029f45  mov     edx, 6Ch ; 'l'
0x180029f4a  mov     rax, [rax+rcx*8]
0x180029f4e  mov     ecx, [rdx+rax]
0x180029f51  cmp     cs:dword_180314328, ecx
0x180029f57  jle     short loc_180029F98
0x180029f59  lea     rcx, dword_180314328
0x180029f60  call    _Init_thread_header
0x180029f65  cmp     cs:dword_180314328, 0FFFFFFFFh
0x180029f6c  jnz     short loc_180029F98
0x180029f6e  lea     rdi, qword_180314300
0x180029f75  mov     rcx, rdi
0x180029f78  call    ?GetUserSidForCurrentProcess@Common@EndpointDlp@@YA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@XZ; EndpointDlp::Common::GetUserSidForCurrentProcess(void)
0x180029f7d  lea     rcx, _EndpointDlp___anonymous_namespace___GetEffectiveUserSid____2____dynamic_atexit_destructor_for__currentProcessSid__; void (__cdecl *)()
0x180029f84  call    atexit
0x180029f89  nop
0x180029f8a  lea     rcx, dword_180314328
0x180029f91  call    _Init_thread_footer
0x180029f96  jmp     short loc_180029F9F
0x180029f98  lea     rdi, qword_180314300
0x180029f9f  cmp     byte ptr [rdi+20h], 0
0x180029fa3  jnz     loc_180029D99
0x180029fa9  call    ?Instance@TraceLoggingProvider@EndpointDlp@@SAAEAV12@XZ; EndpointDlp::TraceLoggingProvider::Instance(void)
0x180029fae  mov     rcx, [rax]
0x180029fb1  cmp     dword ptr [rcx], 2
0x180029fb4  jbe     short loc_180029FEB
0x180029fb6  lea     rax, aGettrustcontai_0; "GetTrustContainerUserConfigFlag failed "...
0x180029fbd  mov     [rsp+98h+var_60], rax
0x180029fc2  mov     [rsp+98h+var_68], 80004005h
0x180029fca  lea     rax, [rsp+98h+var_60]
0x180029fcf  mov     [rsp+98h+var_70], rax
0x180029fd4  lea     rax, [rsp+98h+var_68]
0x180029fd9  mov     qword ptr [rsp+98h+bIgnoreCase], rax
0x180029fde  lea     rdx, qword_1802BEB20
0x180029fe5  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180029fea  nop
0x180029feb  lea     rcx, [rsp+98h+var_58]
0x180029ff0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180029ff5  xor     al, al
0x180029ff7  jmp     loc_180029EB6
0x180029ffc  test    r15, r15
0x180029fff  jz      short loc_18002A009
0x18002a001  mov     rcx, r15; this
0x18002a004  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002a009  xor     bl, bl
0x18002a00b  jmp     loc_180029EA5
0x18002a010  xor     al, al
0x18002a012  jmp     loc_180029EB6
```
