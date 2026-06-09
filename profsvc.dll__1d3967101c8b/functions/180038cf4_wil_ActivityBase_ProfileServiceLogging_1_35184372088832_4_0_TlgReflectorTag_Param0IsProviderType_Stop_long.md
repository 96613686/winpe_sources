# wil::ActivityBase<ProfileServiceLogging,1,35184372088832,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180038cf4`
- end: `0x180038ddc`
- name: `?Stop@?$ActivityBase@VProfileServiceLogging@@$00$0CAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `232`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180038a30`
- `0x180038c10`

## callees

- `0x1800231b0`
- `0x18002356c`
- `0x180025698`
- `0x180026468`
- `0x180027dd8`
- `0x180038cf4`
- `0x18004a9c4`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180038d36`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180038d36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038d77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038d77`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<ProfileServiceLogging,1,35184372088832,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  char v2; // di
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  PSRWLOCK SRWLock; // [rsp+50h] [rbp+8h] BYREF
  DWORD v12; // [rsp+58h] [rbp+10h] BYREF
  __int64 v13; // [rsp+60h] [rbp+18h] BYREF

  v12 = 0;
  wil::ActivityBase<ProfileServiceLogging,1,35184372088832,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v2 = wil::ActivityBase<ProfileServiceLogging,1,35184372088832,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileServiceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v12);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v2 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v3 = ProfileServiceLogging::Provider();
    v6 = (__int64)v3;
    if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x200000000000LL, v4, v5) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v8 = a1[34];
      v12 = CurrentThreadId;
      LODWORD(SRWLock) = 0;
      v13 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned __int8 *)&unk_1800716C0,
        v8 + 8,
        v9,
        (__int64)&v13,
        (__int64)&SRWLock,
        (__int64)&v12);
    }
  }
  return wil::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x180038cf4  mov     rax, rsp
0x180038cf7  mov     [rax+20h], rbx
0x180038cfb  mov     [rax+10h], edx
0x180038cfe  push    rdi
0x180038cff  sub     rsp, 40h
0x180038d03  lea     rdx, [rax+8]
0x180038d07  mov     dword ptr [rax+10h], 0
0x180038d0e  mov     rbx, rcx
0x180038d11  call    ?LockExclusive@?$ActivityBase@VProfileServiceLogging@@$00$0CAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ProfileServiceLogging,1,35184372088832,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180038d16  mov     rcx, [rbx+110h]
0x180038d1d  lea     r8, [rsp+48h+arg_8]
0x180038d22  xor     edx, edx
0x180038d24  call    ?SetStopResult@?$ActivityData@VProfileServiceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VProfileServiceLogging@@$00$0CAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<ProfileServiceLogging,1,35184372088832,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileServiceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x180038d29  mov     rcx, [rsp+48h+SRWLock]; SRWLock
0x180038d2e  mov     dil, al
0x180038d31  test    rcx, rcx
0x180038d34  jz      short loc_180038D3C
0x180038d36  call    cs:__imp_ReleaseSRWLockExclusive
0x180038d3c  test    dil, dil
0x180038d3f  jz      short loc_180038D52
0x180038d41  mov     rax, [rbx]
0x180038d44  mov     rcx, rbx
0x180038d47  mov     rax, [rax+8]
0x180038d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d50  jmp     short loc_180038DCA
0x180038d52  call    ?Provider@ProfileServiceLogging@@SAPEBU_tlgProvider_t@@XZ; ProfileServiceLogging::Provider(void)
0x180038d57  mov     rdi, rax
0x180038d5a  mov     ecx, [rax]
0x180038d5c  cmp     ecx, 5
0x180038d5f  jbe     short loc_180038DCA
0x180038d61  mov     rdx, 200000000000h
0x180038d6b  mov     rcx, rax
0x180038d6e  call    _tlgKeywordOn
0x180038d73  test    al, al
0x180038d75  jz      short loc_180038DCA
0x180038d77  call    cs:__imp_GetCurrentThreadId
0x180038d7d  mov     r8, [rbx+110h]
0x180038d84  lea     rdx, unk_1800716C0
0x180038d8b  mov     [rsp+48h+arg_8], eax
0x180038d8f  add     r8, 8
0x180038d93  lea     rax, [rsp+48h+arg_8]
0x180038d98  mov     dword ptr [rsp+48h+SRWLock], 0
0x180038da0  mov     [rsp+48h+var_18], rax
0x180038da5  mov     rcx, rdi
0x180038da8  lea     rax, [rsp+48h+SRWLock]
0x180038dad  mov     [rsp+48h+arg_10], 1000000h
0x180038db6  mov     [rsp+48h+var_20], rax
0x180038dbb  lea     rax, [rsp+48h+arg_10]
0x180038dc0  mov     [rsp+48h+var_28], rax
0x180038dc5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180038dca  mov     rcx, rbx
0x180038dcd  mov     rbx, [rsp+48h+arg_18]
0x180038dd2  add     rsp, 40h
0x180038dd6  pop     rdi
0x180038dd7  jmp     ?IgnoreCurrentThread@?$ActivityBase@VProfileLogging@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
