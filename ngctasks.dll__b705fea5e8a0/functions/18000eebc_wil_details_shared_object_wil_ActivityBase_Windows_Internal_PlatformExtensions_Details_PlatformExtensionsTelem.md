# wil::details::shared_object<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(void)

- ea: `0x18000eebc`
- end: `0x18000ef0c`
- name: `?reset@?$shared_object@V?$ActivityData@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ`
- size: `80`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1800085ac`
- `0x180008b34`
- `0x1800098e8`

## callees

- `0x1800067f4`
- `0x180008e88`
- `0x18000eebc`

## pseudocode

```c
void __fastcall wil::details::shared_object<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(
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
        wil::details::shared_object<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>>::RefAndObject::~RefAndObject(*a1);
        operator delete(v3);
      }
    }
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x18000eebc  mov     [rsp+arg_0], rbx
0x18000eec1  push    rdi
0x18000eec2  sub     rsp, 20h
0x18000eec6  mov     rbx, rcx
0x18000eec9  mov     rcx, [rcx]
0x18000eecc  test    rcx, rcx
0x18000eecf  jz      short loc_18000EF01
0x18000eed1  or      eax, 0FFFFFFFFh
0x18000eed4  lock xadd [rcx], eax
0x18000eed8  cmp     eax, 1
0x18000eedb  jnz     short loc_18000EEFA
0x18000eedd  mov     rdi, [rbx]
0x18000eee0  test    rdi, rdi
0x18000eee3  jz      short loc_18000EEFA
0x18000eee5  mov     rcx, rdi
0x18000eee8  call    ??1RefAndObject@?$shared_object@V?$ActivityData@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAA@XZ; wil::details::shared_object<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>>::RefAndObject::~RefAndObject(void)
0x18000eeed  mov     edx, 110h
0x18000eef2  mov     rcx, rdi; Block
0x18000eef5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000eefa  mov     qword ptr [rbx], 0
0x18000ef01  mov     rbx, [rsp+28h+arg_0]
0x18000ef06  add     rsp, 20h
0x18000ef0a  pop     rdi
0x18000ef0b  retn
```
