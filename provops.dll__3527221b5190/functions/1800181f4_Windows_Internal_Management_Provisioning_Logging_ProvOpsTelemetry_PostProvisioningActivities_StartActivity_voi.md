# Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::PostProvisioningActivities::StartActivity(void)

- ea: `0x1800181f4`
- end: `0x180018333`
- name: `?StartActivity@PostProvisioningActivities@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAXXZ`
- size: `319`
- prototype: `void __fastcall(Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::PostProvisioningActivities *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180013e9c`

## callees

- `0x180001678`
- `0x180006f50`
- `0x180013200`
- `0x1800181f4`
- `0x180018e0c`
- `0x180033ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018261`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018261`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180018243`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180018243`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001827a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001827a`

## pseudocode

```c
void __fastcall Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::PostProvisioningActivities::StartActivity(
        Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::PostProvisioningActivities *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rdi
  __int64 v4; // r8
  __int64 v5; // r9
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-9h] BYREF
  _QWORD v7[9]; // [rsp+38h] [rbp-1h] BYREF

  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider() <= 4u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v3 = Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider();
  if ( *(_DWORD *)v3 > 4u )
  {
    LODWORD(SRWLock) = GetCurrentThreadId();
    v7[0] = 0;
    v4 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v4 + 4)
      || (v5 = v4 + 24, !*(_DWORD *)(v4 + 24))
      && !*(_DWORD *)(v4 + 28)
      && !*(_DWORD *)(v4 + 32)
      && !*(_DWORD *)(v4 + 36) )
    {
      v5 = 0;
    }
    v7[7] = &SRWLock;
    v7[8] = 4;
    v7[5] = v7;
    v7[6] = 8;
    tlgWriteTransfer_EventWriteTransfer(v3, &byte_18003F0AF, v4 + 8, v5);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::PostProvisioningActivities *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800181f4  mov     [rsp-8+arg_8], rbx
0x1800181f9  mov     [rsp-8+arg_10], rdi
0x1800181fe  push    rbp
0x1800181ff  lea     rbp, [rsp-57h]
0x180018204  sub     rsp, 90h
0x18001820b  mov     rax, cs:__security_cookie
0x180018212  xor     rax, rsp
0x180018215  mov     [rbp+57h+var_10], rax
0x180018219  mov     rbx, rcx
0x18001821c  lea     rdx, [rbp+57h+SRWLock]
0x180018220  call    ?LockExclusive@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180018225  mov     rdi, [rbx+110h]
0x18001822c  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x180018231  mov     r8d, [rax]
0x180018234  cmp     r8d, 4
0x180018238  jbe     short loc_18001824B
0x18001823a  lea     rdx, [rdi+8]; ActivityId
0x18001823e  mov     ecx, 3; ControlCode
0x180018243  call    cs:__imp_EventActivityIdControl
0x180018249  jmp     short loc_180018252
0x18001824b  xorps   xmm0, xmm0
0x18001824e  movups  xmmword ptr [rdi+8], xmm0
0x180018252  mov     dword ptr [rdi], 1
0x180018258  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001825c  test    rcx, rcx
0x18001825f  jz      short loc_180018267
0x180018261  call    cs:__imp_ReleaseSRWLockExclusive
0x180018267  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x18001826c  mov     rdi, rax
0x18001826f  mov     ecx, [rax]
0x180018271  cmp     ecx, 4
0x180018274  jbe     loc_1800182FF
0x18001827a  call    cs:__imp_GetCurrentThreadId
0x180018280  mov     dword ptr [rbp+57h+SRWLock], eax
0x180018283  mov     [rbp+57h+var_58], 0
0x18001828b  mov     r8, [rbx+110h]
0x180018292  cmp     byte ptr [r8+4], 0
0x180018297  jz      short loc_1800182B8
0x180018299  lea     r9, [r8+18h]
0x18001829d  cmp     dword ptr [r9], 0
0x1800182a1  jnz     short loc_1800182BB
0x1800182a3  cmp     dword ptr [r9+4], 0
0x1800182a8  jnz     short loc_1800182BB
0x1800182aa  cmp     dword ptr [r9+8], 0
0x1800182af  jnz     short loc_1800182BB
0x1800182b1  cmp     dword ptr [r9+0Ch], 0
0x1800182b6  jnz     short loc_1800182BB
0x1800182b8  xor     r9d, r9d
0x1800182bb  lea     rax, [rbp+57h+SRWLock]
0x1800182bf  mov     [rbp+57h+var_20], rax
0x1800182c3  mov     [rbp+57h+var_18], 4
0x1800182cb  lea     rax, [rbp+57h+var_58]
0x1800182cf  mov     [rbp+57h+var_30], rax
0x1800182d3  mov     [rbp+57h+var_28], 8
0x1800182db  add     r8, 8
0x1800182df  lea     rax, [rbp+57h+var_50]
0x1800182e3  mov     [rsp+90h+var_68], rax
0x1800182e8  mov     [rsp+90h+var_70], 4
0x1800182f0  lea     rdx, byte_18003F0AF
0x1800182f7  mov     rcx, rdi
0x1800182fa  call    _tlgWriteTransfer_EventWriteTransfer
0x1800182ff  lea     rcx, [rbx+120h]; this
0x180018306  cmp     dword ptr [rcx+18h], 0
0x18001830a  jnz     short loc_180018312
0x18001830c  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180018311  nop
0x180018312  mov     rcx, [rbp+57h+var_10]
0x180018316  xor     rcx, rsp; StackCookie
0x180018319  call    __security_check_cookie
0x18001831e  lea     r11, [rsp+90h+var_s0]
0x180018326  mov     rbx, [r11+18h]
0x18001832a  mov     rdi, [r11+20h]
0x18001832e  mov     rsp, r11
0x180018331  pop     rbp
0x180018332  retn
```
