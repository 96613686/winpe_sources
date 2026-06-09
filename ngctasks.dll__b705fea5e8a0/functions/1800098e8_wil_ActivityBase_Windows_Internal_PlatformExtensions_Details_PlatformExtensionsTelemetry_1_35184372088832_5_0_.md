# wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)

- ea: `0x1800098e8`
- end: `0x1800099b6`
- name: `?Destroy@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `206`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x1800090b8`

## callees

- `0x180006e9c`
- `0x180008c94`
- `0x1800098e8`
- `0x18000b39c`
- `0x18000c710`
- `0x18000e9d8`
- `0x18000eebc`

## pseudocode

```c
void __fastcall wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(
        __int64 a1)
{
  _QWORD *v2; // rdi
  char v3; // si
  _DWORD *v4; // rcx
  int v5; // eax
  int v6; // edx
  const struct wil::FailureInfo *v7; // rdx
  _BYTE v8[160]; // [rsp+20h] [rbp-A8h] BYREF
  RTL_SRWLOCK *v9; // [rsp+D0h] [rbp+8h] BYREF

  v2 = (_QWORD *)(a1 + 280);
  if ( !*(_QWORD *)(a1 + 280) )
    goto LABEL_17;
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v9);
  if ( *v2 && *(_DWORD *)*v2 == 1 )
  {
    v3 = 1;
  }
  else
  {
    v3 = 0;
    wil::details::shared_object<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(v2);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  if ( v3 )
  {
LABEL_17:
    v4 = *(_DWORD **)(a1 + 272);
    if ( *v4 == 1 )
    {
      v5 = -2147024322;
      if ( (int)v4[22] < 0 )
        v5 = v4[22];
      v6 = v4[62];
      if ( v6 < 1 )
      {
        memset_0(v8, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v8, v7);
      }
      if ( (int)v4[18] >= 0 )
        v4[18] = v5;
      v4[62] = v6 - 1;
      wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(a1);
    }
  }
}

```

## disassembly

```asm
0x1800098e8  mov     rax, rsp
0x1800098eb  mov     [rax+10h], rbx
0x1800098ef  mov     [rax+18h], rsi
0x1800098f3  push    rdi
0x1800098f4  sub     rsp, 0C0h
0x1800098fb  mov     rbx, rcx
0x1800098fe  lea     rdi, [rcx+118h]
0x180009905  cmp     qword ptr [rdi], 0
0x180009909  jz      short loc_180009945
0x18000990b  lea     rdx, [rax+8]
0x18000990f  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180009914  nop
0x180009915  mov     rax, [rdi]
0x180009918  test    rax, rax
0x18000991b  jz      short loc_180009927
0x18000991d  cmp     dword ptr [rax], 1
0x180009920  jnz     short loc_180009927
0x180009922  mov     sil, 1
0x180009925  jmp     short loc_180009933
0x180009927  xor     sil, sil
0x18000992a  mov     rcx, rdi
0x18000992d  call    ?reset@?$shared_object@V?$ActivityData@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180009932  nop
0x180009933  lea     rcx, [rsp+0C8h+arg_0]
0x18000993b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180009940  test    sil, sil
0x180009943  jz      short loc_1800099A1
0x180009945  mov     rcx, [rbx+110h]
0x18000994c  cmp     dword ptr [rcx], 1
0x18000994f  jnz     short loc_1800099A1
0x180009951  mov     eax, 8007023Eh
0x180009956  cmp     dword ptr [rcx+58h], 0
0x18000995a  cmovl   eax, [rcx+58h]
0x18000995e  mov     edx, [rcx+0F8h]
0x180009964  cmp     edx, 1
0x180009967  jge     short loc_180009986
0x180009969  xor     edx, edx; Val
0x18000996b  mov     r8d, 98h; Size
0x180009971  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180009976  call    memset_0
0x18000997b  lea     rcx, [rsp+0C8h+var_A8]; this
0x180009980  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180009986  cmp     dword ptr [rcx+48h], 0
0x18000998a  jl      short loc_18000998F
0x18000998c  mov     [rcx+48h], eax
0x18000998f  lea     eax, [rdx-1]
0x180009992  mov     [rcx+0F8h], eax
0x180009998  mov     rcx, rbx
0x18000999b  call    ?ReportStopActivity@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x1800099a0  nop
0x1800099a1  lea     r11, [rsp+0C8h+var_8]
0x1800099a9  mov     rbx, [r11+18h]
0x1800099ad  mov     rsi, [r11+20h]
0x1800099b1  mov     rsp, r11
0x1800099b4  pop     rdi
0x1800099b5  retn
```
