# wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180018e80`
- end: `0x180018fc3`
- name: `?Stop@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `323`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x18000d574`
- `0x18000ebbc`
- `0x18000f8d0`
- `0x180010b40`

## callees

- `0x180001f08`
- `0x180006f50`
- `0x1800083c0`
- `0x180013034`
- `0x180013200`
- `0x180018e80`
- `0x180033e9a`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018ed6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018ed6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018f29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018f29`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        DWORD a2)
{
  __int64 v3; // rax
  int v4; // edi
  int v5; // edi
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // rdi
  __int64 v8; // rax
  const struct wil::FailureInfo *v9; // rdx
  _BYTE v10[168]; // [rsp+40h] [rbp-A8h] BYREF
  PSRWLOCK SRWLock; // [rsp+F0h] [rbp+8h] BYREF
  DWORD CurrentThreadId; // [rsp+F8h] [rbp+10h]
  __int64 v13; // [rsp+100h] [rbp+18h]

  CurrentThreadId = a2;
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)a1,
    &SRWLock);
  v3 = a1[34];
  v4 = *(_DWORD *)(v3 + 248);
  if ( v4 < 1 )
  {
    memset_0(v10, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v10, v9);
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
    v7 = (__int64)v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      v8 = *((_QWORD *)v6 + 3);
      if ( (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0 && (v8 & 0x400000000000LL) == v8 )
      {
        CurrentThreadId = GetCurrentThreadId();
        LODWORD(SRWLock) = 0;
        v13 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v7,
          (__int64)byte_18003ED91,
          a1[34] + 8LL);
      }
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
0x180018e80  mov     rax, rsp
0x180018e83  mov     [rax+20h], rbx
0x180018e87  mov     [rax+10h], edx
0x180018e8a  push    rdi
0x180018e8b  sub     rsp, 0E0h
0x180018e92  mov     rbx, rcx
0x180018e95  lea     rdx, [rax+8]
0x180018e99  call    ?LockExclusive@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180018e9e  mov     rax, [rbx+110h]
0x180018ea5  mov     edi, [rax+0F8h]
0x180018eab  cmp     edi, 1
0x180018eae  jl      loc_180018FA6
0x180018eb4  cmp     dword ptr [rax+48h], 0
0x180018eb8  jl      short loc_180018EC1
0x180018eba  mov     dword ptr [rax+48h], 0
0x180018ec1  dec     edi
0x180018ec3  mov     [rax+0F8h], edi
0x180018ec9  mov     rcx, [rsp+0E8h+SRWLock]; SRWLock
0x180018ed1  test    rcx, rcx
0x180018ed4  jz      short loc_180018EDC
0x180018ed6  call    cs:__imp_ReleaseSRWLockExclusive
0x180018edc  test    edi, edi
0x180018ede  jnz     short loc_180018EF4
0x180018ee0  mov     rax, [rbx]
0x180018ee3  mov     rcx, rbx
0x180018ee6  mov     rax, [rax+8]
0x180018eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018eef  jmp     loc_180018F8E
0x180018ef4  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x180018ef9  mov     rdi, rax
0x180018efc  mov     ecx, [rax]
0x180018efe  cmp     ecx, 5
0x180018f01  jbe     loc_180018F8E
0x180018f07  mov     rax, [rax+18h]
0x180018f0b  mov     rcx, [rdi+10h]
0x180018f0f  mov     rdx, 400000000000h
0x180018f19  test    rdx, rcx
0x180018f1c  jz      short loc_180018F8E
0x180018f1e  mov     rcx, rax
0x180018f21  and     rcx, rdx
0x180018f24  cmp     rcx, rax
0x180018f27  jnz     short loc_180018F8E
0x180018f29  call    cs:__imp_GetCurrentThreadId
0x180018f2f  mov     [rsp+0E8h+arg_8], eax
0x180018f36  mov     dword ptr [rsp+0E8h+SRWLock], 0
0x180018f41  mov     [rsp+0E8h+arg_10], 1000000h
0x180018f4d  mov     r8, [rbx+110h]
0x180018f54  add     r8, 8
0x180018f58  lea     rax, [rsp+0E8h+arg_8]
0x180018f60  mov     [rsp+0E8h+var_B8], rax
0x180018f65  lea     rax, [rsp+0E8h+SRWLock]
0x180018f6d  mov     [rsp+0E8h+var_C0], rax
0x180018f72  lea     rax, [rsp+0E8h+arg_10]
0x180018f7a  mov     [rsp+0E8h+var_C8], rax
0x180018f7f  lea     rdx, byte_18003ED91
0x180018f86  mov     rcx, rdi
0x180018f89  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180018f8e  mov     rcx, rbx
0x180018f91  mov     rbx, [rsp+0E8h+arg_18]
0x180018f99  add     rsp, 0E0h
0x180018fa0  pop     rdi
0x180018fa1  jmp     ?IgnoreCurrentThread@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180018fa6  xor     edx, edx; Val
0x180018fa8  mov     r8d, 98h; Size
0x180018fae  lea     rcx, [rsp+0E8h+var_A8]; void *
0x180018fb3  call    memset_0
0x180018fb8  lea     rcx, [rsp+0E8h+var_A8]; this
0x180018fbd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
