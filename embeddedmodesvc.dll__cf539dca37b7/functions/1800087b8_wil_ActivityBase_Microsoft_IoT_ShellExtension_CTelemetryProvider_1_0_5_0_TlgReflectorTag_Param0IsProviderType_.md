# wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)

- ea: `0x1800087b8`
- end: `0x180008850`
- name: `?Destroy@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `152`
- prototype: `void __fastcall(__int64)`
- caller_count: `8`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008730`
- `0x18000acc8`
- `0x1800105f4`
- `0x180010620`
- `0x18001064c`
- `0x180010678`
- `0x1800106a4`
- `0x1800106d0`

## callees

- `0x180008710`
- `0x1800087b8`
- `0x1800088d0`
- `0x180008de0`
- `0x180009044`
- `0x180009564`

## pseudocode

```c
void __fastcall wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(
        __int64 a1)
{
  _QWORD *v1; // rdi
  char v3; // si
  _DWORD *v4; // rcx
  __int64 v5; // rdx
  RTL_SRWLOCK *v6; // [rsp+30h] [rbp+8h] BYREF

  v1 = (_QWORD *)(a1 + 280);
  if ( !*(_QWORD *)(a1 + 280) )
    goto LABEL_7;
  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v6);
  if ( *v1 && *(_DWORD *)*v1 == 1 )
  {
    v3 = 1;
  }
  else
  {
    v3 = 0;
    wil::details::shared_object<wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v1);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v6);
  if ( v3 )
  {
LABEL_7:
    v4 = *(_DWORD **)(a1 + 272);
    if ( *v4 == 1 )
    {
      LODWORD(v6) = v4[22];
      v5 = 2147942974LL;
      if ( (int)v6 < 0 )
        v5 = (unsigned int)v6;
      wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v4,
        v5,
        &v6);
      wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
        a1,
        (unsigned int)v6);
    }
  }
}

```

## disassembly

```asm
0x1800087b8  mov     [rsp+arg_8], rbx
0x1800087bd  mov     [rsp+arg_10], rsi
0x1800087c2  push    rdi
0x1800087c3  sub     rsp, 20h
0x1800087c7  lea     rdi, [rcx+118h]
0x1800087ce  mov     rbx, rcx
0x1800087d1  cmp     qword ptr [rdi], 0
0x1800087d5  jz      short loc_18000880D
0x1800087d7  lea     rdx, [rsp+28h+arg_0]
0x1800087dc  call    ?LockExclusive@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800087e1  mov     rax, [rdi]
0x1800087e4  test    rax, rax
0x1800087e7  jz      short loc_1800087F3
0x1800087e9  cmp     dword ptr [rax], 1
0x1800087ec  jnz     short loc_1800087F3
0x1800087ee  mov     sil, 1
0x1800087f1  jmp     short loc_1800087FE
0x1800087f3  xor     sil, sil
0x1800087f6  mov     rcx, rdi
0x1800087f9  call    ?reset@?$shared_object@V?$ActivityData@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x1800087fe  lea     rcx, [rsp+28h+arg_0]
0x180008803  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180008808  test    sil, sil
0x18000880b  jz      short loc_180008840
0x18000880d  mov     rcx, [rbx+110h]
0x180008814  cmp     dword ptr [rcx], 1
0x180008817  jnz     short loc_180008840
0x180008819  mov     eax, [rcx+58h]
0x18000881c  lea     r8, [rsp+28h+arg_0]
0x180008821  test    eax, eax
0x180008823  mov     dword ptr [rsp+28h+arg_0], eax
0x180008827  mov     edx, 8007023Eh
0x18000882c  cmovs   edx, eax
0x18000882f  call    ?SetStopResult@?$ActivityData@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x180008834  mov     edx, dword ptr [rsp+28h+arg_0]
0x180008838  mov     rcx, rbx
0x18000883b  call    ?ReportStopActivity@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x180008840  mov     rbx, [rsp+28h+arg_8]
0x180008845  mov     rsi, [rsp+28h+arg_10]
0x18000884a  add     rsp, 20h
0x18000884e  pop     rdi
0x18000884f  retn
```
