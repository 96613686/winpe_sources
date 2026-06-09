# wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)

- ea: `0x180011454`
- end: `0x1800114e8`
- name: `?Destroy@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `148`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800105c8`
- `0x18001091c`

## callees

- `0x180008710`
- `0x1800088d0`
- `0x180009044`
- `0x180011454`
- `0x180013634`
- `0x18001506c`

## pseudocode

```c
void __fastcall wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(
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
    wil::details::shared_object<wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v1);
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
      wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(a1);
    }
  }
}

```

## disassembly

```asm
0x180011454  mov     [rsp+arg_8], rbx
0x180011459  mov     [rsp+arg_10], rsi
0x18001145e  push    rdi
0x18001145f  sub     rsp, 20h
0x180011463  lea     rdi, [rcx+118h]
0x18001146a  mov     rbx, rcx
0x18001146d  cmp     qword ptr [rdi], 0
0x180011471  jz      short loc_1800114A9
0x180011473  lea     rdx, [rsp+28h+arg_0]
0x180011478  call    ?LockExclusive@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001147d  mov     rax, [rdi]
0x180011480  test    rax, rax
0x180011483  jz      short loc_18001148F
0x180011485  cmp     dword ptr [rax], 1
0x180011488  jnz     short loc_18001148F
0x18001148a  mov     sil, 1
0x18001148d  jmp     short loc_18001149A
0x18001148f  xor     sil, sil
0x180011492  mov     rcx, rdi
0x180011495  call    ?reset@?$shared_object@V?$ActivityData@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18001149a  lea     rcx, [rsp+28h+arg_0]
0x18001149f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800114a4  test    sil, sil
0x1800114a7  jz      short loc_1800114D8
0x1800114a9  mov     rcx, [rbx+110h]
0x1800114b0  cmp     dword ptr [rcx], 1
0x1800114b3  jnz     short loc_1800114D8
0x1800114b5  mov     eax, [rcx+58h]
0x1800114b8  lea     r8, [rsp+28h+arg_0]
0x1800114bd  test    eax, eax
0x1800114bf  mov     dword ptr [rsp+28h+arg_0], eax
0x1800114c3  mov     edx, 8007023Eh
0x1800114c8  cmovs   edx, eax
0x1800114cb  call    ?SetStopResult@?$ActivityData@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x1800114d0  mov     rcx, rbx
0x1800114d3  call    ?ReportStopActivity@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x1800114d8  mov     rbx, [rsp+28h+arg_8]
0x1800114dd  mov     rsi, [rsp+28h+arg_10]
0x1800114e2  add     rsp, 20h
0x1800114e6  pop     rdi
0x1800114e7  retn
```
