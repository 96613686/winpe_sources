# wil::details::shared_object<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(void)

- ea: `0x18000ef14`
- end: `0x18000ef64`
- name: `?reset@?$shared_object@V?$ActivityData@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ`
- size: `80`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1800085e8`
- `0x180008b40`
- `0x1800099bc`

## callees

- `0x1800067f4`
- `0x180008ea4`
- `0x18000ef14`

## pseudocode

```c
void __fastcall wil::details::shared_object<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(
        __int64 *a1)
{
  volatile signed __int32 *v2; // rcx
  void *v3; // rdi

  v2 = (volatile signed __int32 *)*a1;
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2, 0xFFFFFFFF) == 1 )
    {
      v3 = (void *)*a1;
      if ( *a1 )
      {
        wil::details::shared_object<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>>::RefAndObject::~RefAndObject(*a1);
        operator delete(v3);
      }
    }
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x18000ef14  mov     [rsp+arg_0], rbx
0x18000ef19  push    rdi
0x18000ef1a  sub     rsp, 20h
0x18000ef1e  mov     rbx, rcx
0x18000ef21  mov     rcx, [rcx]
0x18000ef24  test    rcx, rcx
0x18000ef27  jz      short loc_18000EF59
0x18000ef29  or      eax, 0FFFFFFFFh
0x18000ef2c  lock xadd [rcx], eax
0x18000ef30  cmp     eax, 1
0x18000ef33  jnz     short loc_18000EF52
0x18000ef35  mov     rdi, [rbx]
0x18000ef38  test    rdi, rdi
0x18000ef3b  jz      short loc_18000EF52
0x18000ef3d  mov     rcx, rdi
0x18000ef40  call    ??1RefAndObject@?$shared_object@V?$ActivityData@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAA@XZ; wil::details::shared_object<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>>::RefAndObject::~RefAndObject(void)
0x18000ef45  mov     edx, 110h
0x18000ef4a  mov     rcx, rdi; Block
0x18000ef4d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ef52  mov     qword ptr [rbx], 0
0x18000ef59  mov     rbx, [rsp+28h+arg_0]
0x18000ef5e  add     rsp, 20h
0x18000ef62  pop     rdi
0x18000ef63  retn
```
