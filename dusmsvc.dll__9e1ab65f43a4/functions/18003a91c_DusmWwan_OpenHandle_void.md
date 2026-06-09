# DusmWwan::OpenHandle(void)

- ea: `0x18003a91c`
- end: `0x18003aa11`
- name: `?OpenHandle@DusmWwan@@AEAAXXZ`
- size: `245`
- prototype: `void __fastcall(DusmWwan *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18003b56c`

## callees

- `0x1800021e4`
- `0x180007c90`
- `0x18000f094`
- `0x18000f684`
- `0x180012368`
- `0x180012a90`
- `0x180013444`
- `0x1800396f4`
- `0x18003a91c`
- `0x18003c980`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a947`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a947`
- `wwapi!WwanOpenHandle` at `0x18003a9a7`
- `wwapi!WwanOpenHandle` at `0x18003a9a7`

## string_xrefs

- `0x18003a9b5`: `DusmWwan::OpenHandle::WwanOpenHandle`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DusmWwan::OpenHandle(DusmWwan *this)
{
  char *v2; // rbx
  __int64 v3; // rcx
  _QWORD *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rax
  unsigned int v7; // eax
  _DWORD *v8; // rcx
  const char *v9; // [rsp+28h] [rbp-40h]
  char *v10; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v11[8]; // [rsp+38h] [rbp-30h] BYREF
  std::_Ref_count_base *v12; // [rsp+40h] [rbp-28h]
  int v13; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v13 = 0;
  v2 = (char *)this + 24;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v10 = v2;
  v4 = (_QWORD *)*((_QWORD *)this + 8);
  v5 = -1;
  if ( !v4 || *v4 == -1 )
  {
    wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>>>::reset(
      (char *)this + 64,
      -1);
    if ( !*((_QWORD *)this + 8) )
    {
      v6 = std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>>,>(v11);
      std::shared_ptr<DusmDataPlanTraits>::operator=((char *)this + 64, v6);
      if ( v12 )
        std::_Ref_count_base::_Decref(v12);
    }
    v7 = WwanOpenHandle(1, 0, &v13, *((_QWORD *)this + 8));
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0xA9,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmwwan.cpp",
      (const char *)v7,
      (unsigned int)"DusmWwan::OpenHandle::WwanOpenHandle",
      v9);
  }
  v8 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v3, v5) + 8);
  if ( *v8 > 5u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (int)v8,
      (int)&word_18005B416);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v10);
}

```

## disassembly

```asm
0x18003a91c  mov     [rsp+arg_8], rbx
0x18003a921  push    rdi
0x18003a922  sub     rsp, 60h
0x18003a926  mov     rax, cs:__security_cookie
0x18003a92d  xor     rax, rsp
0x18003a930  mov     [rsp+68h+var_18], rax
0x18003a935  mov     rdi, rcx
0x18003a938  mov     [rsp+68h+var_20], 0
0x18003a940  lea     rbx, [rcx+18h]
0x18003a944  mov     rcx, rbx; lpCriticalSection
0x18003a947  call    cs:__imp_EnterCriticalSection
0x18003a94d  mov     [rsp+68h+var_38], rbx
0x18003a952  mov     rax, [rdi+40h]
0x18003a956  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003a95a  test    rax, rax
0x18003a95d  jz      short loc_18003A964
0x18003a95f  cmp     [rax], rdx
0x18003a962  jnz     short loc_18003A9D2
0x18003a964  lea     rcx, [rdi+40h]
0x18003a968  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>>>::reset(void *)
0x18003a96d  cmp     qword ptr [rdi+40h], 0
0x18003a972  jnz     short loc_18003A999
0x18003a974  lea     rcx, [rsp+68h+var_30]
0x18003a979  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>>,>(void)
0x18003a97e  mov     rdx, rax
0x18003a981  lea     rcx, [rdi+40h]
0x18003a985  call    ??4?$shared_ptr@VDusmDataPlanTraits@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<DusmDataPlanTraits>::operator=(std::shared_ptr<DusmDataPlanTraits> &&)
0x18003a98a  mov     rcx, [rsp+68h+var_28]; this
0x18003a98f  test    rcx, rcx
0x18003a992  jz      short loc_18003A999
0x18003a994  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003a999  mov     r9, [rdi+40h]
0x18003a99d  lea     r8, [rsp+68h+var_20]
0x18003a9a2  xor     edx, edx
0x18003a9a4  lea     ecx, [rdx+1]
0x18003a9a7  call    cs:__imp_WwanOpenHandle
0x18003a9ad  mov     r9d, eax; char *
0x18003a9b0  mov     rcx, [rsp+68h]; this
0x18003a9b5  lea     rax, aDusmwwanOpenha; "DusmWwan::OpenHandle::WwanOpenHandle"
0x18003a9bc  mov     qword ptr [rsp+68h+var_48], rax; unsigned int
0x18003a9c1  lea     r8, aOnecoreuapNetD_6; "onecoreuap\\net\\dusm\\lib\\dusmwwan.cp"...
0x18003a9c8  mov     edx, 0A9h; void *
0x18003a9cd  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18003a9d2  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003a9d7  mov     rcx, [rax+8]
0x18003a9db  mov     eax, [rcx]
0x18003a9dd  cmp     eax, 5
0x18003a9e0  jbe     short loc_18003A9EF
0x18003a9e2  lea     rdx, word_18005B416
0x18003a9e9  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18003a9ee  nop
0x18003a9ef  lea     rcx, [rsp+68h+var_38]
0x18003a9f4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18003a9f9  mov     rcx, [rsp+68h+var_18]
0x18003a9fe  xor     rcx, rsp; StackCookie
0x18003aa01  call    __security_check_cookie
0x18003aa06  mov     rbx, [rsp+68h+arg_8]
0x18003aa0b  add     rsp, 60h
0x18003aa0f  pop     rdi
0x18003aa10  retn
```
