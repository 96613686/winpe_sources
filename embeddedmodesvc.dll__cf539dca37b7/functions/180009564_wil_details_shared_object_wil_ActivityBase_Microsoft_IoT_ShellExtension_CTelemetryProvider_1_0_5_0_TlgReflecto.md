# wil::details::shared_object<wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)

- ea: `0x180009564`
- end: `0x1800095b5`
- name: `?reset@?$shared_object@V?$ActivityData@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ`
- size: `81`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000860c`
- `0x1800087b8`

## callees

- `0x180002ee0`
- `0x180008644`
- `0x180009564`

## pseudocode

```c
void __fastcall wil::details::shared_object<wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(
        volatile signed __int32 **a1)
{
  volatile signed __int32 *v2; // rcx
  volatile signed __int32 *v3; // rdi

  v2 = *a1;
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2, 0xFFFFFFFF) == 1 )
    {
      v3 = *a1;
      if ( *a1 )
      {
        wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>((__int64)(v3 + 2));
        operator delete((void *)v3);
      }
    }
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x180009564  mov     [rsp+arg_0], rbx
0x180009569  push    rdi
0x18000956a  sub     rsp, 20h
0x18000956e  mov     rbx, rcx
0x180009571  mov     rcx, [rcx]
0x180009574  test    rcx, rcx
0x180009577  jz      short loc_1800095AA
0x180009579  or      eax, 0FFFFFFFFh
0x18000957c  lock xadd [rcx], eax
0x180009580  cmp     eax, 1
0x180009583  jnz     short loc_1800095A3
0x180009585  mov     rdi, [rbx]
0x180009588  test    rdi, rdi
0x18000958b  jz      short loc_1800095A3
0x18000958d  lea     rcx, [rdi+8]
0x180009591  call    ??1?$ActivityData@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x180009596  mov     edx, 110h; unsigned __int64
0x18000959b  mov     rcx, rdi; void *
0x18000959e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800095a3  mov     qword ptr [rbx], 0
0x1800095aa  mov     rbx, [rsp+28h+arg_0]
0x1800095af  add     rsp, 20h
0x1800095b3  pop     rdi
0x1800095b4  retn
```
