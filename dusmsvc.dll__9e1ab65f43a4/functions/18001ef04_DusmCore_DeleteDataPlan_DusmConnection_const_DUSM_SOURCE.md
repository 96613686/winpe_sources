# DusmCore::DeleteDataPlan(DusmConnection const &,_DUSM_SOURCE)

- ea: `0x18001ef04`
- end: `0x18001efca`
- name: `?DeleteDataPlan@DusmCore@@SAXAEBVDusmConnection@@W4_DUSM_SOURCE@@@Z`
- size: `198`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18001b688`
- `0x180037138`

## callees

- `0x18000f094`
- `0x180012a90`
- `0x180012fcc`
- `0x180013444`
- `0x1800176e4`
- `0x180018680`
- `0x1800191b0`
- `0x1800193d8`
- `0x18001ef04`
- `0x18001efd0`
- `0x18001f058`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ef1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ef1f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DusmCore::DeleteDataPlan(__int64 a1, unsigned int a2)
{
  LPCRITICAL_SECTION v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // rcx
  int v7; // ebx
  unsigned int v8; // ebp
  __int64 v9; // rdi
  unsigned __int64 v10; // rdx
  unsigned __int8 v11; // cl
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  std::_Ref_count_base *v16[2]; // [rsp+30h] [rbp-38h] BYREF
  LPCRITICAL_SECTION v17[5]; // [rsp+40h] [rbp-28h] BYREF

  v4 = DusmCore::s_pInstance;
  EnterCriticalSection(DusmCore::s_pInstance);
  v17[0] = v4;
  *(_OWORD *)v16 = 0;
  DusmCore::GetConnectionFromList(v5, v16, a1);
  if ( v16[0] && *((_DWORD *)v16[0] + 6) == a2 )
  {
    DusmConnection::DeleteDataPlan(v16[0]);
    DusmCore::EvaluateConnectionAndPublish(v6, v16);
    DusmConnection::PublishMbaeNotification(v16[0], 5);
  }
  v7 = *(_DWORD *)(a1 + 12);
  v8 = *(_DWORD *)(a1 + 16);
  v9 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 48);
  if ( DusmTraceLoggingProvider::IsEnabled(v11, v10) )
  {
    wil::details::static_lazy<DusmTraceLoggingProvider>::get(v13, v12);
    DusmTraceLoggingProvider::TelemetryDataPlanDeletedImpl(v14, v9, v8, a2, v7);
  }
  if ( v16[1] )
    std::_Ref_count_base::_Decref(v16[1]);
  return wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v17);
}

```

## disassembly

```asm
0x18001ef04  mov     [rsp+arg_10], rbx
0x18001ef09  push    rbp
0x18001ef0a  push    rsi
0x18001ef0b  push    rdi
0x18001ef0c  sub     rsp, 50h
0x18001ef10  mov     esi, edx
0x18001ef12  mov     rdi, rcx
0x18001ef15  mov     rbx, cs:?s_pInstance@DusmCore@@0PEAV1@EA; DusmCore * DusmCore::s_pInstance
0x18001ef1c  mov     rcx, rbx; lpCriticalSection
0x18001ef1f  call    cs:__imp_EnterCriticalSection
0x18001ef25  mov     [rsp+68h+var_28], rbx
0x18001ef2a  xorps   xmm0, xmm0
0x18001ef2d  movups  xmmword ptr [rsp+68h+var_38], xmm0
0x18001ef32  mov     r8, rdi
0x18001ef35  lea     rdx, [rsp+68h+var_38]
0x18001ef3a  call    ?GetConnectionFromList@DusmCore@@AEBA?AV?$shared_ptr@VDusmConnection@@@std@@AEBVDusmConnection@@@Z; DusmCore::GetConnectionFromList(DusmConnection const &)
0x18001ef3f  nop
0x18001ef40  mov     rcx, [rsp+68h+var_38]; this
0x18001ef45  test    rcx, rcx
0x18001ef48  jz      short loc_18001EF6D
0x18001ef4a  cmp     [rcx+18h], esi
0x18001ef4d  jnz     short loc_18001EF6D
0x18001ef4f  call    ?DeleteDataPlan@DusmConnection@@QEAAXXZ; DusmConnection::DeleteDataPlan(void)
0x18001ef54  lea     rdx, [rsp+68h+var_38]
0x18001ef59  call    ?EvaluateConnectionAndPublish@DusmCore@@AEAAXAEBV?$shared_ptr@VDusmConnection@@@std@@@Z; DusmCore::EvaluateConnectionAndPublish(std::shared_ptr<DusmConnection> const &)
0x18001ef5e  mov     edx, 5
0x18001ef63  mov     rcx, [rsp+68h+var_38]
0x18001ef68  call    ?PublishMbaeNotification@DusmConnection@@QEBAXW4NotificationMessageType@@@Z; DusmConnection::PublishMbaeNotification(NotificationMessageType)
0x18001ef6d  mov     ebx, [rdi+0Ch]
0x18001ef70  mov     ebp, [rdi+10h]
0x18001ef73  lea     rcx, [rdi+30h]
0x18001ef77  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ef7c  mov     rdi, rax
0x18001ef7f  call    ?IsEnabled@DusmTraceLoggingProvider@@SA_NE_K@Z; DusmTraceLoggingProvider::IsEnabled(uchar,unsigned __int64)
0x18001ef84  test    al, al
0x18001ef86  jz      short loc_18001EFA0
0x18001ef88  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18001ef8d  mov     [rsp+68h+var_48], ebx
0x18001ef91  mov     r9d, esi
0x18001ef94  mov     r8d, ebp
0x18001ef97  mov     rdx, rdi
0x18001ef9a  call    ?TelemetryDataPlanDeletedImpl@DusmTraceLoggingProvider@@AEAAXPEB_WW4_DUSM_MEDIA_TYPE@@W4_DUSM_SOURCE@@W4_DUSM_DPU_STATE@@@Z; DusmTraceLoggingProvider::TelemetryDataPlanDeletedImpl(wchar_t const *,_DUSM_MEDIA_TYPE,_DUSM_SOURCE,_DUSM_DPU_STATE)
0x18001ef9f  nop
0x18001efa0  mov     rcx, [rsp+68h+var_38+8]; this
0x18001efa5  test    rcx, rcx
0x18001efa8  jz      short loc_18001EFB0
0x18001efaa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001efaf  nop
0x18001efb0  lea     rcx, [rsp+68h+var_28]
0x18001efb5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001efba  mov     rbx, [rsp+68h+arg_10]
0x18001efc2  add     rsp, 50h
0x18001efc6  pop     rdi
0x18001efc7  pop     rsi
0x18001efc8  pop     rbp
0x18001efc9  retn
```
