# DusmWlan::OpenHandle(void)

- ea: `0x1800380e8`
- end: `0x1800381b1`
- name: `?OpenHandle@DusmWlan@@AEAAXXZ`
- size: `201`
- prototype: `void __fastcall(DusmWlan *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003870c`

## callees

- `0x180007c90`
- `0x18000f094`
- `0x18000f684`
- `0x180012368`
- `0x180012a90`
- `0x1800369e0`
- `0x1800380e8`
- `0x180039360`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038108`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038108`
- `wlanapi!WlanOpenHandle` at `0x180038168`
- `wlanapi!WlanOpenHandle` at `0x180038168`

## string_xrefs

- `0x180038176`: `DusmWlan::OpenHandle::WlanOpenHandle`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DusmWlan::OpenHandle(DusmWlan *this)
{
  _QWORD *v2; // rax
  __int64 v3; // rax
  DWORD v4; // eax
  const char *v5; // [rsp+28h] [rbp-40h]
  DusmWlan *v6; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v7[8]; // [rsp+38h] [rbp-30h] BYREF
  std::_Ref_count_base *v8; // [rsp+40h] [rbp-28h]
  DWORD pdwNegotiatedVersion; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  pdwNegotiatedVersion = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  v6 = this;
  v2 = (_QWORD *)*((_QWORD *)this + 5);
  if ( !v2 || *v2 == -1 )
  {
    wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWlanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>>>::reset(
      (char *)this + 40,
      -1);
    if ( !*((_QWORD *)this + 5) )
    {
      v3 = std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWlanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>>,>(v7);
      std::shared_ptr<DusmDataPlanTraits>::operator=((char *)this + 40, v3);
      if ( v8 )
        std::_Ref_count_base::_Decref(v8);
    }
    v4 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, *((PHANDLE *)this + 5));
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0xA4,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmwlan.cpp",
      (const char *)v4,
      (unsigned int)"DusmWlan::OpenHandle::WlanOpenHandle",
      v5);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v6);
}

```

## disassembly

```asm
0x1800380e8  push    rbx
0x1800380ea  sub     rsp, 60h
0x1800380ee  mov     rax, cs:__security_cookie
0x1800380f5  xor     rax, rsp
0x1800380f8  mov     [rsp+68h+var_18], rax
0x1800380fd  mov     rbx, rcx
0x180038100  mov     [rsp+68h+pdwNegotiatedVersion], 0
0x180038108  call    cs:__imp_EnterCriticalSection
0x18003810e  mov     [rsp+68h+var_38], rbx
0x180038113  mov     rax, [rbx+28h]
0x180038117  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003811b  test    rax, rax
0x18003811e  jz      short loc_180038125
0x180038120  cmp     [rax], rdx
0x180038123  jnz     short loc_180038194
0x180038125  lea     rcx, [rbx+28h]
0x180038129  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWlanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWlanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>>>::reset(void *)
0x18003812e  cmp     qword ptr [rbx+28h], 0
0x180038133  jnz     short loc_18003815A
0x180038135  lea     rcx, [rsp+68h+var_30]
0x18003813a  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWlanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWlanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWlanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>>,>(void)
0x18003813f  mov     rdx, rax
0x180038142  lea     rcx, [rbx+28h]
0x180038146  call    ??4?$shared_ptr@VDusmDataPlanTraits@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<DusmDataPlanTraits>::operator=(std::shared_ptr<DusmDataPlanTraits> &&)
0x18003814b  mov     rcx, [rsp+68h+var_28]; this
0x180038150  test    rcx, rcx
0x180038153  jz      short loc_18003815A
0x180038155  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003815a  mov     r9, [rbx+28h]; phClientHandle
0x18003815e  lea     r8, [rsp+68h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x180038163  xor     edx, edx; pReserved
0x180038165  lea     ecx, [rdx+2]; dwClientVersion
0x180038168  call    cs:__imp_WlanOpenHandle
0x18003816e  mov     r9d, eax; char *
0x180038171  mov     rcx, [rsp+68h]; this
0x180038176  lea     rax, aDusmwlanOpenha; "DusmWlan::OpenHandle::WlanOpenHandle"
0x18003817d  mov     qword ptr [rsp+68h+var_48], rax; unsigned int
0x180038182  lea     r8, aOnecoreuapNetD_11; "onecoreuap\\net\\dusm\\lib\\dusmwlan.cp"...
0x180038189  mov     edx, 0A4h; void *
0x18003818e  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180038193  nop
0x180038194  lea     rcx, [rsp+68h+var_38]
0x180038199  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18003819e  mov     rcx, [rsp+68h+var_18]
0x1800381a3  xor     rcx, rsp; StackCookie
0x1800381a6  call    __security_check_cookie
0x1800381ab  add     rsp, 60h
0x1800381af  pop     rbx
0x1800381b0  retn
```
