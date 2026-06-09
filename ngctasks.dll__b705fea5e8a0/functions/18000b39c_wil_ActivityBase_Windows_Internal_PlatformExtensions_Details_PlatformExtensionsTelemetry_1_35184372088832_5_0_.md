# wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)

- ea: `0x18000b39c`
- end: `0x18000b43f`
- name: `?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `163`
- prototype: `RTL_SRWLOCK **__fastcall(__int64, RTL_SRWLOCK **)`
- caller_count: `8`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800098e8`
- `0x1800099bc`
- `0x18000bb20`
- `0x18000be70`
- `0x18000d1c4`
- `0x18000d318`
- `0x18000e750`
- `0x18000fac8`

## callees

- `0x180008c94`
- `0x18000b39c`
- `0x18000b448`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        __int64 a1,
        RTL_SRWLOCK **a2)
{
  __int64 v3; // rcx
  RTL_SRWLOCK **v4; // rax
  char v5; // bl
  RTL_SRWLOCK *v6; // rcx
  char v7; // bl
  RTL_SRWLOCK *v9; // [rsp+50h] [rbp+20h] BYREF
  RTL_SRWLOCK **v10; // [rsp+58h] [rbp+28h]
  RTL_SRWLOCK *v11; // [rsp+60h] [rbp+30h] BYREF

  v10 = a2;
  v3 = *(_QWORD *)(a1 + 280);
  if ( v3 )
  {
    v4 = (RTL_SRWLOCK **)wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
                           v3 + 8,
                           &v11);
    v5 = 1;
    v6 = *v4;
  }
  else
  {
    v9 = 0;
    v4 = &v9;
    v5 = 2;
    v6 = 0;
  }
  *a2 = v6;
  *v4 = 0;
  v7 = v5 | 4;
  if ( (v7 & 2) != 0 )
  {
    v7 &= ~2u;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  }
  if ( (v7 & 1) != 0 )
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  return a2;
}

```

## disassembly

```asm
0x18000b39c  mov     [rsp-18h+arg_8], rdx
0x18000b3a1  push    rbp
0x18000b3a2  push    rbx
0x18000b3a3  push    rdi
0x18000b3a4  mov     rbp, rsp
0x18000b3a7  sub     rsp, 30h
0x18000b3ab  mov     rdi, rdx
0x18000b3ae  mov     [rbp+var_10], 0
0x18000b3b5  mov     rcx, [rcx+118h]
0x18000b3bc  test    rcx, rcx
0x18000b3bf  jz      short loc_18000B3DC
0x18000b3c1  add     rcx, 8
0x18000b3c5  lea     rdx, [rbp+arg_10]
0x18000b3c9  call    ?LockExclusive@?$ActivityData@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000b3ce  nop
0x18000b3cf  mov     ebx, 1
0x18000b3d4  mov     [rbp+var_10], ebx
0x18000b3d7  mov     rcx, [rax]
0x18000b3da  jmp     short loc_18000B3FA
0x18000b3dc  mov     [rbp+arg_0], 0
0x18000b3e4  mov     [rbp+arg_0], 0
0x18000b3ec  lea     rax, [rbp+arg_0]
0x18000b3f0  mov     ebx, 2
0x18000b3f5  mov     [rbp+var_10], ebx
0x18000b3f8  xor     ecx, ecx
0x18000b3fa  mov     [rdi], rcx
0x18000b3fd  mov     qword ptr [rax], 0
0x18000b404  or      ebx, 4
0x18000b407  mov     [rbp+var_10], ebx
0x18000b40a  test    bl, 2
0x18000b40d  jz      short loc_18000B41F
0x18000b40f  and     ebx, 0FFFFFFFDh
0x18000b412  mov     [rbp+var_10], ebx
0x18000b415  lea     rcx, [rbp+arg_0]
0x18000b419  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000b41e  nop
0x18000b41f  test    bl, 1
0x18000b422  jz      short loc_18000B433
0x18000b424  and     ebx, 0FFFFFFFEh
0x18000b427  mov     [rbp+var_10], ebx
0x18000b42a  lea     rcx, [rbp+arg_10]
0x18000b42e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000b433  mov     rax, rdi
0x18000b436  add     rsp, 30h
0x18000b43a  pop     rdi
0x18000b43b  pop     rbx
0x18000b43c  pop     rbp
0x18000b43d  retn
```
