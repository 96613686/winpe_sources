# wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)

- ea: `0x14000f94c`
- end: `0x14000fa18`
- name: `?Destroy@?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `204`
- prototype: `void __fastcall(__int64)`
- caller_count: `7`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14000f6ac`
- `0x14000f6d8`
- `0x14000f704`
- `0x14000f730`
- `0x14000f75c`
- `0x14000f87c`
- `0x14000f904`

## callees

- `0x140003390`
- `0x1400063a8`
- `0x140006e08`
- `0x14000f94c`
- `0x14000fce0`
- `0x1400105b8`
- `0x140015fc8`

## pseudocode

```c
void __fastcall wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(
        __int64 a1)
{
  _QWORD *v2; // rdi
  char v3; // si
  _DWORD *v4; // rcx
  int v5; // eax
  int v6; // edx
  const struct wil::FailureInfo *v7; // rdx
  _BYTE v8[160]; // [rsp+20h] [rbp-A8h] BYREF
  RTL_SRWLOCK *v9; // [rsp+D0h] [rbp+8h] BYREF

  v2 = (_QWORD *)(a1 + 280);
  if ( !*(_QWORD *)(a1 + 280) )
    goto LABEL_17;
  wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v9);
  if ( *v2 && *(_DWORD *)*v2 == 1 )
  {
    v3 = 1;
  }
  else
  {
    v3 = 0;
    wil::details::shared_object<wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<g_hProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v2);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  if ( v3 )
  {
LABEL_17:
    v4 = *(_DWORD **)(a1 + 272);
    if ( *v4 == 1 )
    {
      v5 = -2147024322;
      if ( (int)v4[22] < 0 )
        v5 = v4[22];
      v6 = v4[62];
      if ( v6 < 1 )
      {
        memset_0(v8, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v8, v7);
      }
      if ( (int)v4[18] >= 0 )
        v4[18] = v5;
      v4[62] = v6 - 1;
      wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(a1);
    }
  }
}

```

## disassembly

```asm
0x14000f94c  mov     rax, rsp
0x14000f94f  mov     [rax+10h], rbx
0x14000f953  mov     [rax+18h], rsi
0x14000f957  push    rdi
0x14000f958  sub     rsp, 0C0h
0x14000f95f  mov     rbx, rcx
0x14000f962  lea     rdi, [rcx+118h]
0x14000f969  cmp     qword ptr [rdi], 0
0x14000f96d  jz      short loc_14000F9A7
0x14000f96f  lea     rdx, [rax+8]
0x14000f973  call    ?LockExclusive@?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000f978  mov     rax, [rdi]
0x14000f97b  test    rax, rax
0x14000f97e  jz      short loc_14000F98A
0x14000f980  cmp     dword ptr [rax], 1
0x14000f983  jnz     short loc_14000F98A
0x14000f985  mov     sil, 1
0x14000f988  jmp     short loc_14000F995
0x14000f98a  xor     sil, sil
0x14000f98d  mov     rcx, rdi
0x14000f990  call    ?reset@?$shared_object@V?$ActivityData@Vg_hProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<g_hProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x14000f995  lea     rcx, [rsp+0C8h+arg_0]
0x14000f99d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000f9a2  test    sil, sil
0x14000f9a5  jz      short loc_14000FA03
0x14000f9a7  mov     rcx, [rbx+110h]
0x14000f9ae  cmp     dword ptr [rcx], 1
0x14000f9b1  jnz     short loc_14000FA03
0x14000f9b3  mov     eax, 8007023Eh
0x14000f9b8  cmp     dword ptr [rcx+58h], 0
0x14000f9bc  cmovl   eax, [rcx+58h]
0x14000f9c0  mov     edx, [rcx+0F8h]
0x14000f9c6  cmp     edx, 1
0x14000f9c9  jge     short loc_14000F9E8
0x14000f9cb  xor     edx, edx; Val
0x14000f9cd  mov     r8d, 98h; Size
0x14000f9d3  lea     rcx, [rsp+0C8h+var_A8]; void *
0x14000f9d8  call    memset_0
0x14000f9dd  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000f9e2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000f9e8  cmp     dword ptr [rcx+48h], 0
0x14000f9ec  jl      short loc_14000F9F1
0x14000f9ee  mov     [rcx+48h], eax
0x14000f9f1  lea     eax, [rdx-1]
0x14000f9f4  mov     [rcx+0F8h], eax
0x14000f9fa  mov     rcx, rbx
0x14000f9fd  call    ?ReportStopActivity@?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x14000fa02  nop
0x14000fa03  lea     r11, [rsp+0C8h+var_8]
0x14000fa0b  mov     rbx, [r11+18h]
0x14000fa0f  mov     rsi, [r11+20h]
0x14000fa13  mov     rsp, r11
0x14000fa16  pop     rdi
0x14000fa17  retn
```
