# wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180019238`
- end: `0x180019352`
- name: `?Stop@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `282`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `8`
- tags: ``

## callers

- `0x18000d408`
- `0x180011884`
- `0x180016840`
- `0x180017020`
- `0x180017380`

## callees

- `0x180001f08`
- `0x180006f50`
- `0x1800083c0`
- `0x180013034`
- `0x180013200`
- `0x180019238`
- `0x180033e9a`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001928e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001928e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800192b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800192b8`

## pseudocode

```c
void __fastcall wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        DWORD a2)
{
  __int64 v3; // rax
  int v4; // edi
  int v5; // edi
  const struct _tlgProvider_t *v6; // rdi
  const struct wil::FailureInfo *v7; // rdx
  _BYTE v8[168]; // [rsp+40h] [rbp-A8h] BYREF
  PSRWLOCK SRWLock; // [rsp+F0h] [rbp+8h] BYREF
  DWORD CurrentThreadId; // [rsp+F8h] [rbp+10h]
  __int64 v11; // [rsp+100h] [rbp+18h]

  CurrentThreadId = a2;
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)a1,
    &SRWLock);
  v3 = a1[34];
  v4 = *(_DWORD *)(v3 + 248);
  if ( v4 < 1 )
  {
    memset_0(v8, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v8, v7);
  }
  if ( *(int *)(v3 + 72) >= 0 )
    *(_DWORD *)(v3 + 72) = 0;
  v5 = v4 - 1;
  *(_DWORD *)(v3 + 248) = v5;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v5 )
  {
    v6 = Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider();
    if ( *(_DWORD *)v6 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      LODWORD(SRWLock) = 0;
      v11 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v6,
        (__int64)byte_18003F74B,
        a1[34] + 8LL);
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x180019238  mov     rax, rsp
0x18001923b  mov     [rax+20h], rbx
0x18001923f  mov     [rax+10h], edx
0x180019242  push    rdi
0x180019243  sub     rsp, 0E0h
0x18001924a  mov     rbx, rcx
0x18001924d  lea     rdx, [rax+8]
0x180019251  call    ?LockExclusive@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180019256  mov     rax, [rbx+110h]
0x18001925d  mov     edi, [rax+0F8h]
0x180019263  cmp     edi, 1
0x180019266  jl      loc_180019335
0x18001926c  cmp     dword ptr [rax+48h], 0
0x180019270  jl      short loc_180019279
0x180019272  mov     dword ptr [rax+48h], 0
0x180019279  dec     edi
0x18001927b  mov     [rax+0F8h], edi
0x180019281  mov     rcx, [rsp+0E8h+SRWLock]; SRWLock
0x180019289  test    rcx, rcx
0x18001928c  jz      short loc_180019294
0x18001928e  call    cs:__imp_ReleaseSRWLockExclusive
0x180019294  test    edi, edi
0x180019296  jnz     short loc_1800192A9
0x180019298  mov     rax, [rbx]
0x18001929b  mov     rcx, rbx
0x18001929e  mov     rax, [rax+8]
0x1800192a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192a7  jmp     short loc_18001931D
0x1800192a9  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x1800192ae  mov     rdi, rax
0x1800192b1  mov     ecx, [rax]
0x1800192b3  cmp     ecx, 5
0x1800192b6  jbe     short loc_18001931D
0x1800192b8  call    cs:__imp_GetCurrentThreadId
0x1800192be  mov     [rsp+0E8h+arg_8], eax
0x1800192c5  mov     dword ptr [rsp+0E8h+SRWLock], 0
0x1800192d0  mov     [rsp+0E8h+arg_10], 1000000h
0x1800192dc  mov     r8, [rbx+110h]
0x1800192e3  add     r8, 8
0x1800192e7  lea     rax, [rsp+0E8h+arg_8]
0x1800192ef  mov     [rsp+0E8h+var_B8], rax
0x1800192f4  lea     rax, [rsp+0E8h+SRWLock]
0x1800192fc  mov     [rsp+0E8h+var_C0], rax
0x180019301  lea     rax, [rsp+0E8h+arg_10]
0x180019309  mov     [rsp+0E8h+var_C8], rax
0x18001930e  lea     rdx, byte_18003F74B
0x180019315  mov     rcx, rdi
0x180019318  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001931d  mov     rcx, rbx
0x180019320  mov     rbx, [rsp+0E8h+arg_18]
0x180019328  add     rsp, 0E0h
0x18001932f  pop     rdi
0x180019330  jmp     ?IgnoreCurrentThread@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180019335  xor     edx, edx; Val
0x180019337  mov     r8d, 98h; Size
0x18001933d  lea     rcx, [rsp+0E8h+var_A8]; void *
0x180019342  call    memset_0
0x180019347  lea     rcx, [rsp+0E8h+var_A8]; this
0x18001934c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
