# wil::ActivityBase<ProfileServiceLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18002b1c8`
- end: `0x18002b297`
- name: `?Stop@?$ActivityBase@VProfileServiceLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `207`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18002af20`
- `0x18002bb60`

## callees

- `0x180021ea0`
- `0x1800231b0`
- `0x18002356c`
- `0x180026468`
- `0x18002b1c8`
- `0x18004a9c4`
- `0x18004a9e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b20a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b20a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b232`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b232`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<ProfileServiceLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  char v2; // di
  const struct _tlgProvider_t *v3; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  PSRWLOCK SRWLock; // [rsp+50h] [rbp+8h] BYREF
  DWORD v9; // [rsp+58h] [rbp+10h] BYREF
  __int64 v10; // [rsp+60h] [rbp+18h] BYREF

  v9 = 0;
  wil::ActivityBase<ProfileLogging,1,70368744177664,1,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v2 = wil::ActivityBase<ProfileServiceLogging,1,35184372088832,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileServiceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v9);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v2 )
  {
    wil::ActivityBase<ProfileServiceLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(a1, v9);
  }
  else
  {
    v3 = ProfileServiceLogging::Provider();
    if ( *(_DWORD *)v3 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v5 = a1[34];
      v9 = CurrentThreadId;
      LODWORD(SRWLock) = 0;
      v10 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v3,
        (unsigned __int8 *)word_18007141A,
        v5 + 8,
        v6,
        (__int64)&v10,
        (__int64)&SRWLock,
        (__int64)&v9);
    }
  }
  return wil::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x18002b1c8  mov     rax, rsp
0x18002b1cb  mov     [rax+20h], rbx
0x18002b1cf  mov     [rax+10h], edx
0x18002b1d2  push    rdi
0x18002b1d3  sub     rsp, 40h
0x18002b1d7  lea     rdx, [rax+8]
0x18002b1db  mov     dword ptr [rax+10h], 0
0x18002b1e2  mov     rbx, rcx
0x18002b1e5  call    ?LockExclusive@?$ActivityBase@VProfileLogging@@$00$0EAAAAAAAAAAA@$00$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ProfileLogging,1,70368744177664,1,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002b1ea  mov     rcx, [rbx+110h]
0x18002b1f1  lea     r8, [rsp+48h+arg_8]
0x18002b1f6  xor     edx, edx
0x18002b1f8  call    ?SetStopResult@?$ActivityData@VProfileServiceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VProfileServiceLogging@@$00$0CAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<ProfileServiceLogging,1,35184372088832,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileServiceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18002b1fd  mov     rcx, [rsp+48h+SRWLock]; SRWLock
0x18002b202  mov     dil, al
0x18002b205  test    rcx, rcx
0x18002b208  jz      short loc_18002B210
0x18002b20a  call    cs:__imp_ReleaseSRWLockExclusive
0x18002b210  test    dil, dil
0x18002b213  jz      short loc_18002B223
0x18002b215  mov     edx, [rsp+48h+arg_8]
0x18002b219  mov     rcx, rbx
0x18002b21c  call    ?ReportStopActivity@?$ActivityBase@VProfileServiceLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<ProfileServiceLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x18002b221  jmp     short loc_18002B285
0x18002b223  call    ?Provider@ProfileServiceLogging@@SAPEBU_tlgProvider_t@@XZ; ProfileServiceLogging::Provider(void)
0x18002b228  mov     rdi, rax
0x18002b22b  mov     ecx, [rax]
0x18002b22d  cmp     ecx, 5
0x18002b230  jbe     short loc_18002B285
0x18002b232  call    cs:__imp_GetCurrentThreadId
0x18002b238  mov     r8, [rbx+110h]
0x18002b23f  lea     rdx, word_18007141A
0x18002b246  mov     [rsp+48h+arg_8], eax
0x18002b24a  add     r8, 8
0x18002b24e  lea     rax, [rsp+48h+arg_8]
0x18002b253  mov     dword ptr [rsp+48h+SRWLock], 0
0x18002b25b  mov     [rsp+48h+var_18], rax
0x18002b260  mov     rcx, rdi
0x18002b263  lea     rax, [rsp+48h+SRWLock]
0x18002b268  mov     [rsp+48h+arg_10], 1000000h
0x18002b271  mov     [rsp+48h+var_20], rax
0x18002b276  lea     rax, [rsp+48h+arg_10]
0x18002b27b  mov     [rsp+48h+var_28], rax
0x18002b280  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002b285  mov     rcx, rbx
0x18002b288  mov     rbx, [rsp+48h+arg_18]
0x18002b28d  add     rsp, 40h
0x18002b291  pop     rdi
0x18002b292  jmp     ?IgnoreCurrentThread@?$ActivityBase@VProfileLogging@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ProfileLogging,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
