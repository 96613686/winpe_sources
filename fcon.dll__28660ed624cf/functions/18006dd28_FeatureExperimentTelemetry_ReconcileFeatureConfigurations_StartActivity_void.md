# FeatureExperimentTelemetry::ReconcileFeatureConfigurations::StartActivity(void)

- ea: `0x18006dd28`
- end: `0x18006de8c`
- name: `?StartActivity@ReconcileFeatureConfigurations@FeatureExperimentTelemetry@@QEAAXXZ`
- size: `356`
- prototype: `void __fastcall(FeatureExperimentTelemetry::ReconcileFeatureConfigurations *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18006e1d0`

## callees

- `0x1800017ec`
- `0x180001818`
- `0x180003220`
- `0x180005f54`
- `0x18002452c`
- `0x180045208`
- `0x18006d7bc`
- `0x18006dd28`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006ddd6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006ddd6`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18006dd8b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18006dd8b`

## pseudocode

```c
void __fastcall FeatureExperimentTelemetry::ReconcileFeatureConfigurations::StartActivity(
        FeatureExperimentTelemetry::ReconcileFeatureConfigurations *this)
{
  __int64 v2; // rbx
  const struct _tlgProvider_t *v3; // rax
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // rbx
  __int64 v6; // r8
  const GUID *v7; // r9
  DWORD CurrentThreadId; // [rsp+30h] [rbp-9h] BYREF
  __int64 v9; // [rsp+38h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+40h] [rbp+7h] BYREF
  __int64 *v11; // [rsp+60h] [rbp+27h]
  __int64 v12; // [rsp+68h] [rbp+2Fh]
  DWORD *p_CurrentThreadId; // [rsp+70h] [rbp+37h]
  __int64 v14; // [rsp+78h] [rbp+3Fh]

  wil::ActivityBase<FeatureExperimentLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &CurrentThreadId);
  v2 = *((_QWORD *)this + 34);
  v3 = FeatureExperimentLogging::Provider();
  if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL) )
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&CurrentThreadId);
  v4 = FeatureExperimentLogging::Provider();
  v5 = (__int64)v4;
  if ( *(_DWORD *)v4 > 5u && (unsigned __int8)tlgKeywordOn(v4, 0x400000000000LL) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v9 = 0;
    v6 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v6 + 4)
      || (v7 = (const GUID *)(v6 + 24), !*(_DWORD *)(v6 + 24))
      && !*(_DWORD *)(v6 + 28)
      && !*(_DWORD *)(v6 + 32)
      && !*(_DWORD *)(v6 + 36) )
    {
      v7 = 0;
    }
    p_CurrentThreadId = &CurrentThreadId;
    v14 = 4;
    v11 = &v9;
    v12 = 8;
    tlgWriteTransfer_EventWriteTransfer(v5, (unsigned __int8 *)byte_1800E3919, (const GUID *)(v6 + 8), v7, 4u, &v10);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((FeatureExperimentTelemetry::ReconcileFeatureConfigurations *)((char *)this + 288));
}

```

## disassembly

```asm
0x18006dd28  mov     [rsp-8+arg_8], rbx
0x18006dd2d  mov     [rsp-8+arg_10], rdi
0x18006dd32  push    rbp
0x18006dd33  lea     rbp, [rsp-57h]
0x18006dd38  sub     rsp, 90h
0x18006dd3f  mov     rax, cs:__security_cookie
0x18006dd46  xor     rax, rsp
0x18006dd49  mov     [rbp+57h+var_10], rax
0x18006dd4d  mov     rdi, rcx
0x18006dd50  lea     rdx, [rbp+57h+var_60]
0x18006dd54  call    ?LockExclusive@?$ActivityBase@VFeatureExperimentLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<FeatureExperimentLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18006dd59  mov     rbx, [rdi+110h]
0x18006dd60  call    ?Provider@FeatureExperimentLogging@@SAPEBU_tlgProvider_t@@XZ; FeatureExperimentLogging::Provider(void)
0x18006dd65  mov     edx, [rax]
0x18006dd67  cmp     edx, 5
0x18006dd6a  jbe     short loc_18006DD93
0x18006dd6c  mov     rdx, 400000000000h
0x18006dd76  mov     rcx, rax
0x18006dd79  call    _tlgKeywordOn
0x18006dd7e  test    al, al
0x18006dd80  jz      short loc_18006DD93
0x18006dd82  lea     rdx, [rbx+8]; ActivityId
0x18006dd86  mov     ecx, 3; ControlCode
0x18006dd8b  call    cs:__imp_EventActivityIdControl
0x18006dd91  jmp     short loc_18006DD9A
0x18006dd93  xorps   xmm0, xmm0
0x18006dd96  movups  xmmword ptr [rbx+8], xmm0
0x18006dd9a  mov     dword ptr [rbx], 1
0x18006dda0  lea     rcx, [rbp+57h+var_60]
0x18006dda4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18006dda9  call    ?Provider@FeatureExperimentLogging@@SAPEBU_tlgProvider_t@@XZ; FeatureExperimentLogging::Provider(void)
0x18006ddae  mov     rbx, rax
0x18006ddb1  mov     ecx, [rax]
0x18006ddb3  cmp     ecx, 5
0x18006ddb6  jbe     loc_18006DE58
0x18006ddbc  mov     rdx, 400000000000h
0x18006ddc6  mov     rcx, rax
0x18006ddc9  call    _tlgKeywordOn
0x18006ddce  test    al, al
0x18006ddd0  jz      loc_18006DE58
0x18006ddd6  call    cs:__imp_GetCurrentThreadId
0x18006dddc  mov     [rbp+57h+var_60], eax
0x18006dddf  mov     [rbp+57h+var_58], 0
0x18006dde7  mov     r8, [rdi+110h]
0x18006ddee  cmp     byte ptr [r8+4], 0
0x18006ddf3  jz      short loc_18006DE14
0x18006ddf5  lea     r9, [r8+18h]
0x18006ddf9  cmp     dword ptr [r9], 0
0x18006ddfd  jnz     short loc_18006DE17
0x18006ddff  cmp     dword ptr [r9+4], 0
0x18006de04  jnz     short loc_18006DE17
0x18006de06  cmp     dword ptr [r9+8], 0
0x18006de0b  jnz     short loc_18006DE17
0x18006de0d  cmp     dword ptr [r9+0Ch], 0
0x18006de12  jnz     short loc_18006DE17
0x18006de14  xor     r9d, r9d
0x18006de17  lea     rax, [rbp+57h+var_60]
0x18006de1b  mov     [rbp+57h+var_20], rax
0x18006de1f  mov     ecx, 4
0x18006de24  mov     [rbp+57h+var_18], rcx
0x18006de28  lea     rax, [rbp+57h+var_58]
0x18006de2c  mov     [rbp+57h+var_30], rax
0x18006de30  mov     [rbp+57h+var_28], 8
0x18006de38  add     r8, 8
0x18006de3c  lea     rax, [rbp+57h+var_50]
0x18006de40  mov     [rsp+90h+var_68], rax
0x18006de45  mov     [rsp+90h+var_70], ecx
0x18006de49  lea     rdx, byte_1800E3919
0x18006de50  mov     rcx, rbx
0x18006de53  call    _tlgWriteTransfer_EventWriteTransfer
0x18006de58  lea     rcx, [rdi+120h]; this
0x18006de5f  cmp     dword ptr [rcx+18h], 0
0x18006de63  jnz     short loc_18006DE6B
0x18006de65  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18006de6a  nop
0x18006de6b  mov     rcx, [rbp+57h+var_10]
0x18006de6f  xor     rcx, rsp; StackCookie
0x18006de72  call    __security_check_cookie
0x18006de77  lea     r11, [rsp+90h+var_s0]
0x18006de7f  mov     rbx, [r11+18h]
0x18006de83  mov     rdi, [r11+20h]
0x18006de87  mov     rsp, r11
0x18006de8a  pop     rbp
0x18006de8b  retn
```
