# wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18000ffd4`
- end: `0x180010119`
- name: `?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `325`
- prototype: ``
- caller_count: `12`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180009ad8`
- `0x18000e530`
- `0x180014330`
- `0x180014400`
- `0x180014510`
- `0x1800146e0`
- `0x180014a00`
- `0x180014c20`
- `0x180014e80`
- `0x180015050`
- `0x1800152d0`
- `0x1800154a0`

## callees

- `0x180001664`
- `0x1800032b8`
- `0x18000b9b4`
- `0x18000bc04`
- `0x18000ffd4`
- `0x18001251c`
- `0x180012f2c`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001002c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001002c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001007d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001007d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1)
{
  __int64 v2; // rax
  int v3; // edi
  int v4; // edi
  __int64 v5; // rdi
  __int64 v6; // r9
  const struct wil::FailureInfo *v7; // rdx
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-C8h] BYREF
  DWORD CurrentThreadId; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v10; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE v11[168]; // [rsp+60h] [rbp-A8h] BYREF

  SRWLock = 0;
  wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v2 = *(_QWORD *)(a1 + 272);
  v3 = *(_DWORD *)(v2 + 248);
  if ( v3 < 1 )
  {
    memset_0(v11, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v11, v7);
  }
  if ( *(int *)(v2 + 72) >= 0 )
    *(_DWORD *)(v2 + 72) = 0;
  v4 = v3 - 1;
  *(_DWORD *)(v2 + 248) = v4;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v4 )
  {
    v5 = *((_QWORD *)ComputeStorage::Diagnostics::TraceProvider::Instance() + 1);
    if ( *(_DWORD *)v5 > 5u
      && (*(_QWORD *)(v5 + 16) & 0x20040LL) != 0
      && (*(_QWORD *)(v5 + 24) & 0x20040LL) == *(_QWORD *)(v5 + 24) )
    {
      CurrentThreadId = GetCurrentThreadId();
      LODWORD(SRWLock) = 0;
      v10 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v5,
        (int)word_18005468A,
        *(_QWORD *)(a1 + 272) + 8,
        v6,
        (__int64)&v10,
        (__int64)&SRWLock,
        (__int64)&CurrentThreadId);
    }
  }
  else
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  }
  if ( *(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x18000ffd4  mov     [rsp+arg_8], rbx
0x18000ffd9  push    rdi
0x18000ffda  sub     rsp, 100h
0x18000ffe1  mov     rbx, rcx
0x18000ffe4  mov     [rsp+108h+SRWLock], 0
0x18000ffed  lea     rdx, [rsp+108h+SRWLock]
0x18000fff2  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000fff7  mov     rax, [rbx+110h]
0x18000fffe  mov     edi, [rax+0F8h]
0x180010004  cmp     edi, 1
0x180010007  jl      loc_1800100FC
0x18001000d  cmp     dword ptr [rax+48h], 0
0x180010011  jl      short loc_18001001A
0x180010013  mov     dword ptr [rax+48h], 0
0x18001001a  dec     edi
0x18001001c  mov     [rax+0F8h], edi
0x180010022  mov     rcx, [rsp+108h+SRWLock]; SRWLock
0x180010027  test    rcx, rcx
0x18001002a  jz      short loc_180010038
0x18001002c  call    cs:__imp_ReleaseSRWLockExclusive
0x180010033  nop     dword ptr [rax+rax+00h]
0x180010038  test    edi, edi
0x18001003a  jnz     short loc_180010050
0x18001003c  mov     rax, [rbx]
0x18001003f  mov     rcx, rbx
0x180010042  mov     rax, [rax+8]
0x180010046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001004b  jmp     loc_1800100D7
0x180010050  call    ?Instance@TraceProvider@Diagnostics@ComputeStorage@@KAPEAV123@XZ; ComputeStorage::Diagnostics::TraceProvider::Instance(void)
0x180010055  mov     rdi, [rax+8]
0x180010059  mov     eax, [rdi]
0x18001005b  cmp     eax, 5
0x18001005e  jbe     short loc_1800100D7
0x180010060  mov     rcx, [rdi+18h]
0x180010064  mov     rax, [rdi+10h]
0x180010068  mov     edx, 20040h
0x18001006d  test    rdx, rax
0x180010070  jz      short loc_1800100D7
0x180010072  mov     rax, rcx
0x180010075  and     rax, rdx
0x180010078  cmp     rax, rcx
0x18001007b  jnz     short loc_1800100D7
0x18001007d  call    cs:__imp_GetCurrentThreadId
0x180010084  nop     dword ptr [rax+rax+00h]
0x180010089  mov     [rsp+108h+var_C0], eax
0x18001008d  mov     dword ptr [rsp+108h+SRWLock], 0
0x180010095  mov     [rsp+108h+var_B8], 1000000h
0x18001009e  mov     r8, [rbx+110h]
0x1800100a5  add     r8, 8
0x1800100a9  lea     rax, [rsp+108h+var_C0]
0x1800100ae  mov     [rsp+108h+var_D8], rax
0x1800100b3  lea     rax, [rsp+108h+SRWLock]
0x1800100b8  mov     [rsp+108h+var_E0], rax
0x1800100bd  lea     rax, [rsp+108h+var_B8]
0x1800100c2  mov     [rsp+108h+var_E8], rax
0x1800100c7  lea     rdx, word_18005468A
0x1800100ce  mov     rcx, rdi
0x1800100d1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800100d6  nop
0x1800100d7  lea     rcx, [rbx+120h]; this
0x1800100de  cmp     dword ptr [rcx+18h], 0
0x1800100e2  jz      short loc_1800100EA
0x1800100e4  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800100e9  nop
0x1800100ea  mov     rbx, [rsp+108h+arg_8]
0x1800100f2  add     rsp, 100h
0x1800100f9  pop     rdi
0x1800100fa  retn
0x1800100fc  xor     edx, edx; Val
0x1800100fe  mov     r8d, 98h; Size
0x180010104  lea     rcx, [rsp+108h+var_A8]; void *
0x180010109  call    memset_0
0x18001010e  lea     rcx, [rsp+108h+var_A8]; this
0x180010113  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
