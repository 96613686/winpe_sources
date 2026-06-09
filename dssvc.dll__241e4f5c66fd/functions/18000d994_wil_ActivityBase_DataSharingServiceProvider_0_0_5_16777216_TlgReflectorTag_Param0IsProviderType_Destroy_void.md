# wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)

- ea: `0x18000d994`
- end: `0x18000da5f`
- name: `?Destroy@?$ActivityBase@VDataSharingServiceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `203`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18000c95c`

## callees

- `0x1800069c8`
- `0x180007e80`
- `0x18000d994`
- `0x18000df98`
- `0x18000e350`
- `0x18000f590`
- `0x18001b30a`

## pseudocode

```c
void __fastcall wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(
        __int64 a1)
{
  _QWORD *v1; // rdi
  char v3; // si
  _DWORD *v4; // rcx
  int v5; // eax
  int v6; // edx
  const struct wil::FailureInfo *v7; // rdx
  _BYTE v8[160]; // [rsp+20h] [rbp-A8h] BYREF
  RTL_SRWLOCK *v9; // [rsp+D0h] [rbp+8h] BYREF

  v1 = (_QWORD *)(a1 + 280);
  if ( !*(_QWORD *)(a1 + 280) )
    goto LABEL_17;
  wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v9);
  if ( *v1 && *(_DWORD *)*v1 == 1 )
  {
    v3 = 1;
  }
  else
  {
    v3 = 0;
    wil::details::shared_object<wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DataSharingServiceProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v1);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  if ( v3 )
  {
LABEL_17:
    v4 = *(_DWORD **)(a1 + 272);
    if ( *v4 == 1 )
    {
      v5 = -2147024322;
      v6 = v4[62];
      if ( (int)v4[22] < 0 )
        v5 = v4[22];
      if ( v6 < 1 )
      {
        memset_0(v8, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v8, v7);
      }
      if ( (int)v4[18] >= 0 )
        v4[18] = v5;
      v4[62] = v6 - 1;
      wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(a1);
    }
  }
}

```

## disassembly

```asm
0x18000d994  mov     rax, rsp
0x18000d997  mov     [rax+10h], rbx
0x18000d99b  mov     [rax+18h], rsi
0x18000d99f  push    rdi
0x18000d9a0  sub     rsp, 0C0h
0x18000d9a7  lea     rdi, [rcx+118h]
0x18000d9ae  mov     rbx, rcx
0x18000d9b1  cmp     qword ptr [rdi], 0
0x18000d9b5  jz      short loc_18000D9EF
0x18000d9b7  lea     rdx, [rax+8]
0x18000d9bb  call    ?LockExclusive@?$ActivityBase@VDataSharingServiceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000d9c0  mov     rax, [rdi]
0x18000d9c3  test    rax, rax
0x18000d9c6  jz      short loc_18000D9D2
0x18000d9c8  cmp     dword ptr [rax], 1
0x18000d9cb  jnz     short loc_18000D9D2
0x18000d9cd  mov     sil, 1
0x18000d9d0  jmp     short loc_18000D9DD
0x18000d9d2  xor     sil, sil
0x18000d9d5  mov     rcx, rdi
0x18000d9d8  call    ?reset@?$shared_object@V?$ActivityData@VDataSharingServiceProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDataSharingServiceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DataSharingServiceProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18000d9dd  lea     rcx, [rsp+0C8h+arg_0]
0x18000d9e5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000d9ea  test    sil, sil
0x18000d9ed  jz      short loc_18000DA4A
0x18000d9ef  mov     rcx, [rbx+110h]
0x18000d9f6  cmp     dword ptr [rcx], 1
0x18000d9f9  jnz     short loc_18000DA4A
0x18000d9fb  cmp     dword ptr [rcx+58h], 0
0x18000d9ff  mov     eax, 8007023Eh
0x18000da04  mov     edx, [rcx+0F8h]
0x18000da0a  cmovl   eax, [rcx+58h]
0x18000da0e  cmp     edx, 1
0x18000da11  jge     short loc_18000DA30
0x18000da13  xor     edx, edx; Val
0x18000da15  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000da1a  mov     r8d, 98h; Size
0x18000da20  call    memset_0
0x18000da25  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000da2a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000da30  cmp     dword ptr [rcx+48h], 0
0x18000da34  jl      short loc_18000DA39
0x18000da36  mov     [rcx+48h], eax
0x18000da39  lea     eax, [rdx-1]
0x18000da3c  mov     [rcx+0F8h], eax
0x18000da42  mov     rcx, rbx
0x18000da45  call    ?ReportStopActivity@?$ActivityBase@VDataSharingServiceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x18000da4a  lea     r11, [rsp+0C8h+var_8]
0x18000da52  mov     rbx, [r11+18h]
0x18000da56  mov     rsi, [r11+20h]
0x18000da5a  mov     rsp, r11
0x18000da5d  pop     rdi
0x18000da5e  retn
```
