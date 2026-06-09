# wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)

- ea: `0x18000df98`
- end: `0x18000e019`
- name: `?LockExclusive@?$ActivityBase@VDataSharingServiceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `129`
- prototype: `RTL_SRWLOCK **__fastcall(__int64, RTL_SRWLOCK **)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18000d994`
- `0x18000e0d0`
- `0x18000e91c`
- `0x18000f6fc`

## callees

- `0x180007e80`
- `0x18000df98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000dfc0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000dfc0`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
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
0x18000df98  mov     [rsp+arg_10], rbx
0x18000df9d  mov     [rsp+arg_18], rsi
0x18000dfa2  push    rdi
0x18000dfa3  sub     rsp, 20h
0x18000dfa7  mov     rbx, [rcx+118h]
0x18000dfae  mov     rdi, rdx
0x18000dfb1  test    rbx, rbx
0x18000dfb4  jz      short loc_18000DFD4
0x18000dfb6  add     rbx, 108h
0x18000dfbd  mov     rcx, rbx; SRWLock
0x18000dfc0  call    cs:__imp_AcquireSRWLockExclusive
0x18000dfc6  lea     rax, [rsp+28h+arg_8]
0x18000dfcb  xor     ecx, ecx
0x18000dfcd  mov     esi, 1
0x18000dfd2  jmp     short loc_18000DFE0
0x18000dfd4  xor     ebx, ebx
0x18000dfd6  lea     rax, [rsp+28h+arg_0]
0x18000dfdb  xor     esi, esi
0x18000dfdd  lea     ecx, [rbx+2]
0x18000dfe0  mov     [rdi], rbx
0x18000dfe3  mov     qword ptr [rax], 0
0x18000dfea  test    ecx, ecx
0x18000dfec  jz      short loc_18000DFF8
0x18000dfee  lea     rcx, [rsp+28h+arg_0]
0x18000dff3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000dff8  test    esi, esi
0x18000dffa  jz      short loc_18000E006
0x18000dffc  lea     rcx, [rsp+28h+arg_8]
0x18000e001  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000e006  mov     rbx, [rsp+28h+arg_10]
0x18000e00b  mov     rax, rdi
0x18000e00e  mov     rsi, [rsp+28h+arg_18]
0x18000e013  add     rsp, 20h
0x18000e017  pop     rdi
0x18000e018  retn
```
