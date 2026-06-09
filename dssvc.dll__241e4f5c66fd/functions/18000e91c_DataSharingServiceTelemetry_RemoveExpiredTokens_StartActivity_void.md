# DataSharingServiceTelemetry::RemoveExpiredTokens::StartActivity(void)

- ea: `0x18000e91c`
- end: `0x18000ea51`
- name: `?StartActivity@RemoveExpiredTokens@DataSharingServiceTelemetry@@QEAAXXZ`
- size: `309`
- prototype: `void __fastcall(DataSharingServiceTelemetry::RemoveExpiredTokens *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18000c558`

## callees

- `0x180001818`
- `0x180005c54`
- `0x180007e80`
- `0x18000df98`
- `0x18000e91c`
- `0x18000ea58`
- `0x18001b340`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e99c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e99c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000e96b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000e96b`

## pseudocode

```c
void __fastcall DataSharingServiceTelemetry::RemoveExpiredTokens::StartActivity(
        DataSharingServiceTelemetry::RemoveExpiredTokens *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v5; // r8
  const GUID *v6; // r9
  RTL_SRWLOCK *v7; // [rsp+30h] [rbp-9h] BYREF
  __int64 v8; // [rsp+38h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+40h] [rbp+7h] BYREF
  __int64 *v10; // [rsp+60h] [rbp+27h]
  __int64 v11; // [rsp+68h] [rbp+2Fh]
  RTL_SRWLOCK **v12; // [rsp+70h] [rbp+37h]
  __int64 v13; // [rsp+78h] [rbp+3Fh]

  wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &v7);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)DataSharingServiceProvider::Provider() <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v7);
  v3 = DataSharingServiceProvider::Provider();
  if ( *(_DWORD *)v3 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v5 = *((_QWORD *)this + 34);
    LODWORD(v7) = CurrentThreadId;
    v8 = 0x1000000;
    if ( !*(_BYTE *)(v5 + 4)
      || (v6 = (const GUID *)(v5 + 24), !*(_DWORD *)(v5 + 24))
      && !*(_DWORD *)(v5 + 28)
      && !*(_DWORD *)(v5 + 32)
      && !*(_DWORD *)(v5 + 36) )
    {
      v6 = 0;
    }
    v11 = 8;
    v13 = 4;
    v12 = &v7;
    v10 = &v8;
    tlgWriteTransfer_EventWriteTransfer(
      (__int64)v3,
      (unsigned __int8 *)byte_180025C99,
      (const GUID *)(v5 + 8),
      v6,
      4u,
      &v9);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((DataSharingServiceTelemetry::RemoveExpiredTokens *)((char *)this + 288));
}

```

## disassembly

```asm
0x18000e91c  mov     [rsp-8+arg_8], rbx
0x18000e921  mov     [rsp-8+arg_10], rdi
0x18000e926  push    rbp
0x18000e927  lea     rbp, [rsp-57h]
0x18000e92c  sub     rsp, 90h
0x18000e933  mov     rax, cs:__security_cookie
0x18000e93a  xor     rax, rsp
0x18000e93d  mov     [rbp+57h+var_10], rax
0x18000e941  lea     rdx, [rbp+57h+var_60]
0x18000e945  mov     rbx, rcx
0x18000e948  call    ?LockExclusive@?$ActivityBase@VDataSharingServiceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000e94d  mov     rdi, [rbx+110h]
0x18000e954  call    ?Provider@DataSharingServiceProvider@@SAPEBU_tlgProvider_t@@XZ; DataSharingServiceProvider::Provider(void)
0x18000e959  mov     r8d, [rax]
0x18000e95c  cmp     r8d, 5
0x18000e960  jbe     short loc_18000E973
0x18000e962  lea     rdx, [rdi+8]; ActivityId
0x18000e966  mov     ecx, 3; ControlCode
0x18000e96b  call    cs:__imp_EventActivityIdControl
0x18000e971  jmp     short loc_18000E97A
0x18000e973  xorps   xmm0, xmm0
0x18000e976  movups  xmmword ptr [rdi+8], xmm0
0x18000e97a  lea     rcx, [rbp+57h+var_60]
0x18000e97e  mov     dword ptr [rdi], 1
0x18000e984  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000e989  call    ?Provider@DataSharingServiceProvider@@SAPEBU_tlgProvider_t@@XZ; DataSharingServiceProvider::Provider(void)
0x18000e98e  mov     rdi, rax
0x18000e991  mov     ecx, [rax]
0x18000e993  cmp     ecx, 5
0x18000e996  jbe     loc_18000EA1E
0x18000e99c  call    cs:__imp_GetCurrentThreadId
0x18000e9a2  mov     r8, [rbx+110h]
0x18000e9a9  mov     dword ptr [rbp+57h+var_60], eax
0x18000e9ac  mov     [rbp+57h+var_58], 1000000h
0x18000e9b4  cmp     byte ptr [r8+4], 0
0x18000e9b9  jz      short loc_18000E9DA
0x18000e9bb  lea     r9, [r8+18h]
0x18000e9bf  cmp     dword ptr [r9], 0
0x18000e9c3  jnz     short loc_18000E9DD
0x18000e9c5  cmp     dword ptr [r9+4], 0
0x18000e9ca  jnz     short loc_18000E9DD
0x18000e9cc  cmp     dword ptr [r9+8], 0
0x18000e9d1  jnz     short loc_18000E9DD
0x18000e9d3  cmp     dword ptr [r9+0Ch], 0
0x18000e9d8  jnz     short loc_18000E9DD
0x18000e9da  xor     r9d, r9d
0x18000e9dd  mov     ecx, 4
0x18000e9e2  mov     [rbp+57h+var_28], 8
0x18000e9ea  lea     rax, [rbp+57h+var_60]
0x18000e9ee  mov     [rbp+57h+var_18], rcx
0x18000e9f2  mov     [rbp+57h+var_20], rax
0x18000e9f6  lea     rdx, byte_180025C99
0x18000e9fd  lea     rax, [rbp+57h+var_58]
0x18000ea01  add     r8, 8
0x18000ea05  mov     [rbp+57h+var_30], rax
0x18000ea09  lea     rax, [rbp+57h+var_50]
0x18000ea0d  mov     [rsp+90h+var_68], rax
0x18000ea12  mov     [rsp+90h+var_70], ecx
0x18000ea16  mov     rcx, rdi
0x18000ea19  call    _tlgWriteTransfer_EventWriteTransfer
0x18000ea1e  lea     rcx, [rbx+120h]; this
0x18000ea25  cmp     dword ptr [rcx+18h], 0
0x18000ea29  jnz     short loc_18000EA30
0x18000ea2b  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18000ea30  mov     rcx, [rbp+57h+var_10]
0x18000ea34  xor     rcx, rsp; StackCookie
0x18000ea37  call    __security_check_cookie
0x18000ea3c  lea     r11, [rsp+90h+var_s0]
0x18000ea44  mov     rbx, [r11+18h]
0x18000ea48  mov     rdi, [r11+20h]
0x18000ea4c  mov     rsp, r11
0x18000ea4f  pop     rbp
0x18000ea50  retn
```
