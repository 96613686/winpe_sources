# wil::details::shared_object<wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)

- ea: `0x18001506c`
- end: `0x1800150b8`
- name: `?reset@?$shared_object@V?$ActivityData@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ`
- size: `76`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800103cc`
- `0x180011454`

## callees

- `0x180002f84`
- `0x180010404`
- `0x18001506c`

## pseudocode

```c
void __fastcall wil::details::shared_object<wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(
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
        wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>((__int64)(v3 + 2));
        operator delete((void *)v3);
      }
    }
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x18001506c  mov     [rsp+arg_0], rbx
0x180015071  push    rdi
0x180015072  sub     rsp, 20h
0x180015076  mov     rbx, rcx
0x180015079  mov     rcx, [rcx]
0x18001507c  test    rcx, rcx
0x18001507f  jz      short loc_1800150AD
0x180015081  or      eax, 0FFFFFFFFh
0x180015084  lock xadd [rcx], eax
0x180015088  cmp     eax, 1
0x18001508b  jnz     short loc_1800150A6
0x18001508d  mov     rdi, [rbx]
0x180015090  test    rdi, rdi
0x180015093  jz      short loc_1800150A6
0x180015095  lea     rcx, [rdi+8]
0x180015099  call    ??1?$ActivityData@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001509e  mov     rcx, rdi; Block
0x1800150a1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800150a6  mov     qword ptr [rbx], 0
0x1800150ad  mov     rbx, [rsp+28h+arg_0]
0x1800150b2  add     rsp, 20h
0x1800150b6  pop     rdi
0x1800150b7  retn
```
