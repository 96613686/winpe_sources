# wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x1800091c4`
- end: `0x18000928b`
- name: `?Stop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `199`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800086ac`
- `0x180009690`
- `0x18000af90`
- `0x180010acc`
- `0x180010bfc`
- `0x180011290`
- `0x1800114f0`
- `0x180012790`
- `0x1800129c0`
- `0x180012c00`

## callees

- `0x180001de4`
- `0x180008710`
- `0x180008898`
- `0x1800088d0`
- `0x180008ca0`
- `0x180008de0`
- `0x180009044`
- `0x1800091c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009226`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009226`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1)
{
  char v2; // bl
  const struct _tlgProvider_t *v3; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  RTL_SRWLOCK *v8; // [rsp+50h] [rbp+8h] BYREF
  DWORD v9; // [rsp+58h] [rbp+10h] BYREF
  __int64 v10; // [rsp+60h] [rbp+18h] BYREF

  v9 = 0;
  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v8);
  v2 = wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         *(_QWORD *)(a1 + 272),
         0,
         &v9);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  if ( v2 )
  {
    wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
      a1,
      v9);
  }
  else
  {
    v3 = Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider();
    if ( *(_DWORD *)v3 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v5 = *(_QWORD *)(a1 + 272);
      v9 = CurrentThreadId;
      LODWORD(v8) = 0;
      v10 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v3,
        (__int64)word_18001F9AA,
        v5 + 8,
        v6,
        (__int64)&v10,
        (__int64)&v8,
        (__int64)&v9);
    }
  }
  return wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x1800091c4  mov     rax, rsp
0x1800091c7  mov     [rax+20h], rbx
0x1800091cb  mov     [rax+10h], edx
0x1800091ce  push    rdi
0x1800091cf  sub     rsp, 40h
0x1800091d3  lea     rdx, [rax+8]
0x1800091d7  mov     dword ptr [rax+10h], 0
0x1800091de  mov     rdi, rcx
0x1800091e1  call    ?LockExclusive@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800091e6  mov     rcx, [rdi+110h]
0x1800091ed  lea     r8, [rsp+48h+arg_8]
0x1800091f2  xor     edx, edx
0x1800091f4  call    ?SetStopResult@?$ActivityData@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x1800091f9  lea     rcx, [rsp+48h+arg_0]
0x1800091fe  mov     bl, al
0x180009200  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180009205  test    bl, bl
0x180009207  jz      short loc_180009217
0x180009209  mov     edx, [rsp+48h+arg_8]
0x18000920d  mov     rcx, rdi
0x180009210  call    ?ReportStopActivity@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x180009215  jmp     short loc_180009279
0x180009217  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x18000921c  mov     rbx, rax
0x18000921f  mov     ecx, [rax]
0x180009221  cmp     ecx, 5
0x180009224  jbe     short loc_180009279
0x180009226  call    cs:__imp_GetCurrentThreadId
0x18000922c  mov     r8, [rdi+110h]
0x180009233  lea     rdx, word_18001F9AA
0x18000923a  mov     [rsp+48h+arg_8], eax
0x18000923e  add     r8, 8
0x180009242  lea     rax, [rsp+48h+arg_8]
0x180009247  mov     dword ptr [rsp+48h+arg_0], 0
0x18000924f  mov     [rsp+48h+var_18], rax
0x180009254  mov     rcx, rbx
0x180009257  lea     rax, [rsp+48h+arg_0]
0x18000925c  mov     [rsp+48h+arg_10], 1000000h
0x180009265  mov     [rsp+48h+var_20], rax
0x18000926a  lea     rax, [rsp+48h+arg_10]
0x18000926f  mov     [rsp+48h+var_28], rax
0x180009274  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180009279  mov     rcx, rdi
0x18000927c  mov     rbx, [rsp+48h+arg_18]
0x180009281  add     rsp, 40h
0x180009285  pop     rdi
0x180009286  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
