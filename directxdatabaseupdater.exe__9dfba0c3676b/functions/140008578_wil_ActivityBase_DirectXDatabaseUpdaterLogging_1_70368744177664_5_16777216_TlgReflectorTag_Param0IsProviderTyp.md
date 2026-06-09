# wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)

- ea: `0x140008578`
- end: `0x1400085f9`
- name: `?LockExclusive@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `129`
- prototype: `RTL_SRWLOCK **__fastcall(__int64, RTL_SRWLOCK **)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x140006b80`
- `0x140008e10`
- `0x14000b5fc`
- `0x14000ef38`
- `0x14000efa8`

## callees

- `0x140005e18`
- `0x140008578`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400085a0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400085a0`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
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
0x140008578  mov     [rsp+arg_10], rbx
0x14000857d  mov     [rsp+arg_18], rsi
0x140008582  push    rdi
0x140008583  sub     rsp, 20h
0x140008587  mov     rbx, [rcx+118h]
0x14000858e  mov     rdi, rdx
0x140008591  test    rbx, rbx
0x140008594  jz      short loc_1400085B4
0x140008596  add     rbx, 108h
0x14000859d  mov     rcx, rbx; SRWLock
0x1400085a0  call    cs:__imp_AcquireSRWLockExclusive
0x1400085a6  lea     rax, [rsp+28h+arg_8]
0x1400085ab  xor     ecx, ecx
0x1400085ad  mov     esi, 1
0x1400085b2  jmp     short loc_1400085C0
0x1400085b4  xor     ebx, ebx
0x1400085b6  lea     rax, [rsp+28h+arg_0]
0x1400085bb  xor     esi, esi
0x1400085bd  lea     ecx, [rbx+2]
0x1400085c0  mov     [rdi], rbx
0x1400085c3  mov     qword ptr [rax], 0
0x1400085ca  test    ecx, ecx
0x1400085cc  jz      short loc_1400085D8
0x1400085ce  lea     rcx, [rsp+28h+arg_0]
0x1400085d3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1400085d8  test    esi, esi
0x1400085da  jz      short loc_1400085E6
0x1400085dc  lea     rcx, [rsp+28h+arg_8]
0x1400085e1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1400085e6  mov     rbx, [rsp+28h+arg_10]
0x1400085eb  mov     rax, rdi
0x1400085ee  mov     rsi, [rsp+28h+arg_18]
0x1400085f3  add     rsp, 20h
0x1400085f7  pop     rdi
0x1400085f8  retn
```
