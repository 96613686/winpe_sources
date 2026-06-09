# wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180013b38`
- end: `0x180013c18`
- name: `?Stop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `224`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800104ac`
- `0x1800114f0`

## callees

- `0x1800019bc`
- `0x180001de4`
- `0x180008710`
- `0x180008898`
- `0x1800088d0`
- `0x180008ca0`
- `0x180009044`
- `0x180013b38`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013bb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013bb3`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  char v2; // bl
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  RTL_SRWLOCK *v11; // [rsp+50h] [rbp+8h] BYREF
  DWORD v12; // [rsp+58h] [rbp+10h] BYREF
  __int64 v13; // [rsp+60h] [rbp+18h] BYREF

  v12 = 0;
  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v11);
  v2 = wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v12);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  if ( v2 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v3 = Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider();
    v6 = (__int64)v3;
    if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x200000000000LL, v4, v5) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v8 = a1[34];
      v12 = CurrentThreadId;
      LODWORD(v11) = 0;
      v13 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (__int64)byte_18002078B,
        v8 + 8,
        v9,
        (__int64)&v13,
        (__int64)&v11,
        (__int64)&v12);
    }
  }
  return wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x180013b38  mov     rax, rsp
0x180013b3b  mov     [rax+20h], rbx
0x180013b3f  mov     [rax+10h], edx
0x180013b42  push    rdi
0x180013b43  sub     rsp, 40h
0x180013b47  lea     rdx, [rax+8]
0x180013b4b  mov     dword ptr [rax+10h], 0
0x180013b52  mov     rdi, rcx
0x180013b55  call    ?LockExclusive@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180013b5a  mov     rcx, [rdi+110h]
0x180013b61  lea     r8, [rsp+48h+arg_8]
0x180013b66  xor     edx, edx
0x180013b68  call    ?SetStopResult@?$ActivityData@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x180013b6d  lea     rcx, [rsp+48h+arg_0]
0x180013b72  mov     bl, al
0x180013b74  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180013b79  test    bl, bl
0x180013b7b  jz      short loc_180013B8E
0x180013b7d  mov     rax, [rdi]
0x180013b80  mov     rcx, rdi
0x180013b83  mov     rax, [rax+8]
0x180013b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b8c  jmp     short loc_180013C06
0x180013b8e  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x180013b93  mov     rbx, rax
0x180013b96  mov     ecx, [rax]
0x180013b98  cmp     ecx, 5
0x180013b9b  jbe     short loc_180013C06
0x180013b9d  mov     rdx, 200000000000h
0x180013ba7  mov     rcx, rax
0x180013baa  call    _tlgKeywordOn
0x180013baf  test    al, al
0x180013bb1  jz      short loc_180013C06
0x180013bb3  call    cs:__imp_GetCurrentThreadId
0x180013bb9  mov     r8, [rdi+110h]
0x180013bc0  lea     rdx, byte_18002078B
0x180013bc7  mov     [rsp+48h+arg_8], eax
0x180013bcb  add     r8, 8
0x180013bcf  lea     rax, [rsp+48h+arg_8]
0x180013bd4  mov     dword ptr [rsp+48h+arg_0], 0
0x180013bdc  mov     [rsp+48h+var_18], rax
0x180013be1  mov     rcx, rbx
0x180013be4  lea     rax, [rsp+48h+arg_0]
0x180013be9  mov     [rsp+48h+arg_10], 1000000h
0x180013bf2  mov     [rsp+48h+var_20], rax
0x180013bf7  lea     rax, [rsp+48h+arg_10]
0x180013bfc  mov     [rsp+48h+var_28], rax
0x180013c01  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180013c06  mov     rcx, rdi
0x180013c09  mov     rbx, [rsp+48h+arg_18]
0x180013c0e  add     rsp, 40h
0x180013c12  pop     rdi
0x180013c13  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
