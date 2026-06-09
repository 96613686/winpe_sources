# Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackage::StartActivity(ushort const *)

- ea: `0x180018abc`
- end: `0x180018bb9`
- name: `?StartActivity@RemovePackage@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAXPEBG@Z`
- size: `253`
- prototype: `void __fastcall(Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackage *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180016840`

## callees

- `0x18000223c`
- `0x180006f50`
- `0x180013200`
- `0x180018abc`
- `0x180018e0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018b11`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018b11`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180018af2`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180018af2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018b2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018b2b`

## pseudocode

```c
void __fastcall Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackage::StartActivity(
        Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackage *this,
        const unsigned __int16 *a2)
{
  __int64 v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  const struct _tlgProvider_t *v6; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  PSRWLOCK SRWLock; // [rsp+60h] [rbp+8h] BYREF
  const unsigned __int16 *v11; // [rsp+70h] [rbp+18h] BYREF
  __int64 v12; // [rsp+78h] [rbp+20h] BYREF

  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v4 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider() <= 5u )
    *(_OWORD *)(v4 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  v5 = SRWLock;
  *(_DWORD *)v4 = 1;
  if ( v5 )
    ReleaseSRWLockExclusive(v5);
  v6 = Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider();
  if ( *(_DWORD *)v6 > 5u )
  {
    v11 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v8 = *((_QWORD *)this + 34);
    LODWORD(SRWLock) = CurrentThreadId;
    v12 = 0;
    if ( !*(_BYTE *)(v8 + 4)
      || (v9 = v8 + 24, !*(_DWORD *)(v8 + 24))
      && !*(_DWORD *)(v8 + 28)
      && !*(_DWORD *)(v8 + 32)
      && !*(_DWORD *)(v8 + 36) )
    {
      v9 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      (__int64)v6,
      (__int64)&dword_18003F7A4,
      v8 + 8,
      v9,
      (__int64)&v12,
      (__int64)&SRWLock,
      &v11);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackage *)((char *)this + 288));
}

```

## disassembly

```asm
0x180018abc  push    rbx
0x180018abe  push    rsi
0x180018abf  push    rdi
0x180018ac0  sub     rsp, 40h
0x180018ac4  mov     rsi, rdx
0x180018ac7  mov     rbx, rcx
0x180018aca  lea     rdx, [rsp+58h+SRWLock]
0x180018acf  call    ?LockExclusive@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180018ad4  mov     rdi, [rbx+110h]
0x180018adb  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x180018ae0  mov     r8d, [rax]
0x180018ae3  cmp     r8d, 5
0x180018ae7  jbe     short loc_180018AFA
0x180018ae9  lea     rdx, [rdi+8]; ActivityId
0x180018aed  mov     ecx, 3; ControlCode
0x180018af2  call    cs:__imp_EventActivityIdControl
0x180018af8  jmp     short loc_180018B01
0x180018afa  xorps   xmm0, xmm0
0x180018afd  movups  xmmword ptr [rdi+8], xmm0
0x180018b01  mov     rcx, [rsp+58h+SRWLock]; SRWLock
0x180018b06  mov     dword ptr [rdi], 1
0x180018b0c  test    rcx, rcx
0x180018b0f  jz      short loc_180018B17
0x180018b11  call    cs:__imp_ReleaseSRWLockExclusive
0x180018b17  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x180018b1c  mov     rdi, rax
0x180018b1f  mov     ecx, [rax]
0x180018b21  cmp     ecx, 5
0x180018b24  jbe     short loc_180018B9F
0x180018b26  mov     [rsp+58h+arg_10], rsi
0x180018b2b  call    cs:__imp_GetCurrentThreadId
0x180018b31  mov     r8, [rbx+110h]
0x180018b38  mov     dword ptr [rsp+58h+SRWLock], eax
0x180018b3c  mov     [rsp+58h+arg_18], 0
0x180018b45  cmp     byte ptr [r8+4], 0
0x180018b4a  jz      short loc_180018B6B
0x180018b4c  lea     r9, [r8+18h]
0x180018b50  cmp     dword ptr [r9], 0
0x180018b54  jnz     short loc_180018B6E
0x180018b56  cmp     dword ptr [r9+4], 0
0x180018b5b  jnz     short loc_180018B6E
0x180018b5d  cmp     dword ptr [r9+8], 0
0x180018b62  jnz     short loc_180018B6E
0x180018b64  cmp     dword ptr [r9+0Ch], 0
0x180018b69  jnz     short loc_180018B6E
0x180018b6b  xor     r9d, r9d
0x180018b6e  lea     rax, [rsp+58h+arg_10]
0x180018b73  add     r8, 8
0x180018b77  mov     [rsp+58h+var_28], rax
0x180018b7c  lea     rdx, dword_18003F7A4
0x180018b83  lea     rax, [rsp+58h+SRWLock]
0x180018b88  mov     rcx, rdi
0x180018b8b  mov     [rsp+58h+var_30], rax
0x180018b90  lea     rax, [rsp+58h+arg_18]
0x180018b95  mov     [rsp+58h+var_38], rax
0x180018b9a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180018b9f  lea     rcx, [rbx+120h]; this
0x180018ba6  cmp     dword ptr [rcx+18h], 0
0x180018baa  jnz     short loc_180018BB1
0x180018bac  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180018bb1  add     rsp, 40h
0x180018bb5  pop     rdi
0x180018bb6  pop     rsi
0x180018bb7  pop     rbx
0x180018bb8  retn
```
