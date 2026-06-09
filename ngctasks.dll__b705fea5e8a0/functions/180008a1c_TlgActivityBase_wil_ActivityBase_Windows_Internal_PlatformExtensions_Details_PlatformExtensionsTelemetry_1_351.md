# _TlgActivityBase<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>,35184372088832,5>::~_TlgActivityBase<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>,35184372088832,5>(void)

- ea: `0x180008a1c`
- end: `0x180008a56`
- name: `??1?$_TlgActivityBase@V?$ActivityData@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@$0CAAAAAAAAAAA@$04@@IEAA@XZ`
- size: `58`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180008624`
- `0x18001ec7c`
- `0x18001eea5`

## callees

- `0x1800080a4`
- `0x180008a1c`
- `0x18000c3b0`

## pseudocode

```c
void __fastcall _TlgActivityBase<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>,35184372088832,5>::~_TlgActivityBase<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>,35184372088832,5>(
        _DWORD *a1)
{
  unsigned int *v2; // rax

  if ( *a1 == 1 )
  {
    *a1 = 2;
    v2 = (unsigned int *)wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>::Provider();
    _tlgWriteActivityAutoStop<35184372088832,5>(v2);
  }
  *a1 = 3;
}

```

## disassembly

```asm
0x180008a1c  mov     [rsp+arg_0], rbx
0x180008a21  push    rdi
0x180008a22  sub     rsp, 20h
0x180008a26  mov     rdi, rcx
0x180008a29  cmp     dword ptr [rcx], 1
0x180008a2c  jnz     short loc_180008A45
0x180008a2e  mov     dword ptr [rcx], 2
0x180008a34  call    ?Provider@?$ActivityData@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@SAPEBU_tlgProvider_t@@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>::Provider(void)
0x180008a39  mov     rcx, rax
0x180008a3c  lea     rdx, [rdi+8]
0x180008a40  call    ??$_tlgWriteActivityAutoStop@$0CAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<35184372088832,5>(_tlgProvider_t const *,_GUID const *)
0x180008a45  mov     dword ptr [rdi], 3
0x180008a4b  mov     rbx, [rsp+28h+arg_0]
0x180008a50  add     rsp, 20h
0x180008a54  pop     rdi
0x180008a55  retn
```
