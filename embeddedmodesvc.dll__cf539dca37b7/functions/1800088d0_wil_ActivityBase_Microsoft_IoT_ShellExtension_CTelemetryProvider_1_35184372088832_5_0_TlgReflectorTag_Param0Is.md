# wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)

- ea: `0x1800088d0`
- end: `0x180008951`
- name: `?LockExclusive@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `129`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800087b8`
- `0x180008960`
- `0x1800091c4`
- `0x1800095bc`
- `0x180009618`
- `0x180011454`
- `0x180012110`
- `0x180013648`
- `0x180013b38`

## callees

- `0x180008710`
- `0x1800088d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800088f8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800088f8`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        __int64 a1,
        RTL_SRWLOCK **a2)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v4; // rbx
  RTL_SRWLOCK **v5; // rax
  int v6; // ecx
  int v7; // esi
  RTL_SRWLOCK *v9; // [rsp+30h] [rbp+8h] BYREF
  RTL_SRWLOCK *v10; // [rsp+38h] [rbp+10h] BYREF

  v2 = *(RTL_SRWLOCK **)(a1 + 280);
  if ( v2 )
  {
    v4 = v2 + 33;
    AcquireSRWLockExclusive(v4);
    v5 = &v10;
    v6 = 0;
    v7 = 1;
  }
  else
  {
    v4 = 0;
    v5 = &v9;
    v7 = 0;
    v6 = 2;
  }
  *a2 = v4;
  *v5 = 0;
  if ( v6 )
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  if ( v7 )
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  return a2;
}

```

## disassembly

```asm
0x1800088d0  mov     [rsp+arg_10], rbx
0x1800088d5  mov     [rsp+arg_18], rsi
0x1800088da  push    rdi
0x1800088db  sub     rsp, 20h
0x1800088df  mov     rbx, [rcx+118h]
0x1800088e6  mov     rdi, rdx
0x1800088e9  test    rbx, rbx
0x1800088ec  jz      short loc_18000890C
0x1800088ee  add     rbx, 108h
0x1800088f5  mov     rcx, rbx; SRWLock
0x1800088f8  call    cs:__imp_AcquireSRWLockExclusive
0x1800088fe  lea     rax, [rsp+28h+arg_8]
0x180008903  xor     ecx, ecx
0x180008905  mov     esi, 1
0x18000890a  jmp     short loc_180008918
0x18000890c  xor     ebx, ebx
0x18000890e  lea     rax, [rsp+28h+arg_0]
0x180008913  xor     esi, esi
0x180008915  lea     ecx, [rbx+2]
0x180008918  mov     [rdi], rbx
0x18000891b  mov     qword ptr [rax], 0
0x180008922  test    ecx, ecx
0x180008924  jz      short loc_180008930
0x180008926  lea     rcx, [rsp+28h+arg_0]
0x18000892b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180008930  test    esi, esi
0x180008932  jz      short loc_18000893E
0x180008934  lea     rcx, [rsp+28h+arg_8]
0x180008939  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000893e  mov     rbx, [rsp+28h+arg_10]
0x180008943  mov     rax, rdi
0x180008946  mov     rsi, [rsp+28h+arg_18]
0x18000894b  add     rsp, 20h
0x18000894f  pop     rdi
0x180008950  retn
```
