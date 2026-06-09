# wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)

- ea: `0x1800099bc`
- end: `0x180009a8a`
- name: `?Destroy@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `206`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180009088`

## callees

- `0x180006e9c`
- `0x180008c94`
- `0x1800099bc`
- `0x18000b39c`
- `0x18000c710`
- `0x18000e9d8`
- `0x18000ef14`

## pseudocode

```c
void __fastcall wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(
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
    wil::details::shared_object<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(v2);
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
0x1800099bc  mov     rax, rsp
0x1800099bf  mov     [rax+10h], rbx
0x1800099c3  mov     [rax+18h], rsi
0x1800099c7  push    rdi
0x1800099c8  sub     rsp, 0C0h
0x1800099cf  mov     rbx, rcx
0x1800099d2  lea     rdi, [rcx+118h]
0x1800099d9  cmp     qword ptr [rdi], 0
0x1800099dd  jz      short loc_180009A19
0x1800099df  lea     rdx, [rax+8]
0x1800099e3  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800099e8  nop
0x1800099e9  mov     rax, [rdi]
0x1800099ec  test    rax, rax
0x1800099ef  jz      short loc_1800099FB
0x1800099f1  cmp     dword ptr [rax], 1
0x1800099f4  jnz     short loc_1800099FB
0x1800099f6  mov     sil, 1
0x1800099f9  jmp     short loc_180009A07
0x1800099fb  xor     sil, sil
0x1800099fe  mov     rcx, rdi
0x180009a01  call    ?reset@?$shared_object@V?$ActivityData@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180009a06  nop
0x180009a07  lea     rcx, [rsp+0C8h+arg_0]
0x180009a0f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180009a14  test    sil, sil
0x180009a17  jz      short loc_180009A75
0x180009a19  mov     rcx, [rbx+110h]
0x180009a20  cmp     dword ptr [rcx], 1
0x180009a23  jnz     short loc_180009A75
0x180009a25  mov     eax, 8007023Eh
0x180009a2a  cmp     dword ptr [rcx+58h], 0
0x180009a2e  cmovl   eax, [rcx+58h]
0x180009a32  mov     edx, [rcx+0F8h]
0x180009a38  cmp     edx, 1
0x180009a3b  jge     short loc_180009A5A
0x180009a3d  xor     edx, edx; Val
0x180009a3f  mov     r8d, 98h; Size
0x180009a45  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180009a4a  call    memset_0
0x180009a4f  lea     rcx, [rsp+0C8h+var_A8]; this
0x180009a54  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180009a5a  cmp     dword ptr [rcx+48h], 0
0x180009a5e  jl      short loc_180009A63
0x180009a60  mov     [rcx+48h], eax
0x180009a63  lea     eax, [rdx-1]
0x180009a66  mov     [rcx+0F8h], eax
0x180009a6c  mov     rcx, rbx
0x180009a6f  call    ?ReportStopActivity@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x180009a74  nop
0x180009a75  lea     r11, [rsp+0C8h+var_8]
0x180009a7d  mov     rbx, [r11+18h]
0x180009a81  mov     rsi, [r11+20h]
0x180009a85  mov     rsp, r11
0x180009a88  pop     rdi
0x180009a89  retn
```
