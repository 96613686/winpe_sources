# wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)

- ea: `0x140006b80`
- end: `0x140006c14`
- name: `?Destroy@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `148`
- prototype: `void __fastcall(__int64)`
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x140005f34`
- `0x140005f60`
- `0x140006060`
- `0x1400061d4`
- `0x140006200`
- `0x14000629c`

## callees

- `0x140005e18`
- `0x140006b80`
- `0x140008578`
- `0x140009f2c`
- `0x14000aaec`
- `0x14000e5e0`

## pseudocode

```c
void __fastcall wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(
        __int64 a1)
{
  _QWORD *v1; // rdi
  char v3; // si
  _DWORD *v4; // rcx
  __int64 v5; // rdx
  RTL_SRWLOCK *v6; // [rsp+30h] [rbp+8h] BYREF

  v1 = (_QWORD *)(a1 + 280);
  if ( !*(_QWORD *)(a1 + 280) )
    goto LABEL_7;
  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v6);
  if ( *v1 && *(_DWORD *)*v1 == 1 )
  {
    v3 = 1;
  }
  else
  {
    v3 = 0;
    wil::details::shared_object<wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v1);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v6);
  if ( v3 )
  {
LABEL_7:
    v4 = *(_DWORD **)(a1 + 272);
    if ( *v4 == 1 )
    {
      LODWORD(v6) = v4[22];
      v5 = 2147942974LL;
      if ( (int)v6 < 0 )
        v5 = (unsigned int)v6;
      wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v4,
        v5,
        &v6);
      wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(a1);
    }
  }
}

```

## disassembly

```asm
0x140006b80  mov     [rsp+arg_8], rbx
0x140006b85  mov     [rsp+arg_10], rsi
0x140006b8a  push    rdi
0x140006b8b  sub     rsp, 20h
0x140006b8f  lea     rdi, [rcx+118h]
0x140006b96  mov     rbx, rcx
0x140006b99  cmp     qword ptr [rdi], 0
0x140006b9d  jz      short loc_140006BD5
0x140006b9f  lea     rdx, [rsp+28h+arg_0]
0x140006ba4  call    ?LockExclusive@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140006ba9  mov     rax, [rdi]
0x140006bac  test    rax, rax
0x140006baf  jz      short loc_140006BBB
0x140006bb1  cmp     dword ptr [rax], 1
0x140006bb4  jnz     short loc_140006BBB
0x140006bb6  mov     sil, 1
0x140006bb9  jmp     short loc_140006BC6
0x140006bbb  xor     sil, sil
0x140006bbe  mov     rcx, rdi
0x140006bc1  call    ?reset@?$shared_object@V?$ActivityData@VDirectXDatabaseUpdaterLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x140006bc6  lea     rcx, [rsp+28h+arg_0]
0x140006bcb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140006bd0  test    sil, sil
0x140006bd3  jz      short loc_140006C04
0x140006bd5  mov     rcx, [rbx+110h]
0x140006bdc  cmp     dword ptr [rcx], 1
0x140006bdf  jnz     short loc_140006C04
0x140006be1  mov     eax, [rcx+58h]
0x140006be4  lea     r8, [rsp+28h+arg_0]
0x140006be9  test    eax, eax
0x140006beb  mov     dword ptr [rsp+28h+arg_0], eax
0x140006bef  mov     edx, 8007023Eh
0x140006bf4  cmovs   edx, eax
0x140006bf7  call    ?SetStopResult@?$ActivityData@VDirectXDatabaseUpdaterLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x140006bfc  mov     rcx, rbx
0x140006bff  call    ?ReportStopActivity@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x140006c04  mov     rbx, [rsp+28h+arg_8]
0x140006c09  mov     rsi, [rsp+28h+arg_10]
0x140006c0e  add     rsp, 20h
0x140006c12  pop     rdi
0x140006c13  retn
```
