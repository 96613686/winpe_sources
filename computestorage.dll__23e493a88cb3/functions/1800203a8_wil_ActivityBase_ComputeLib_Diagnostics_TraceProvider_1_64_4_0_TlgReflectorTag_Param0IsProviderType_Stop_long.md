# wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,1,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x1800203a8`
- end: `0x1800204ee`
- name: `?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLib@@$00$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `326`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001ea88`

## callees

- `0x180001664`
- `0x1800032b8`
- `0x18000bc04`
- `0x18001251c`
- `0x180012f2c`
- `0x18001f068`
- `0x18001f95c`
- `0x1800203a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020408`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020408`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002044e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002044e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,1,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1)
{
  __int64 v2; // rax
  int v3; // esi
  int v4; // ebx
  int v5; // esi
  const struct _tlgProvider_t *v6; // rax
  const struct _tlgProvider_t *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // r9
  const struct wil::FailureInfo *v10; // rdx
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-C8h] BYREF
  DWORD CurrentThreadId; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE v14[160]; // [rsp+60h] [rbp-A8h] BYREF

  SRWLock = 0;
  wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v2 = *(_QWORD *)(a1 + 272);
  v3 = *(_DWORD *)(v2 + 248);
  if ( v3 < 1 )
  {
    memset_0(v14, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v14, v10);
  }
  v4 = *(_DWORD *)(v2 + 72);
  if ( v4 >= 0 )
  {
    *(_DWORD *)(v2 + 72) = 0;
    v4 = 0;
  }
  v5 = v3 - 1;
  *(_DWORD *)(v2 + 248) = v5;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v5 )
  {
    v6 = ComputeLib::Diagnostics::TraceProvider::Provider();
    v7 = v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      v8 = *((_QWORD *)v6 + 3);
      if ( (*((_QWORD *)v7 + 2) & 0x40) != 0 && (v8 & 0x40) == v8 )
      {
        CurrentThreadId = GetCurrentThreadId();
        LODWORD(SRWLock) = 0;
        v13 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (int)v7,
          (int)byte_180055641,
          *(_QWORD *)(a1 + 272) + 8,
          v9,
          (__int64)&v13,
          (__int64)&SRWLock,
          (__int64)&CurrentThreadId);
      }
    }
  }
  else
  {
    wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,1,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
      (_QWORD *)a1,
      v4);
  }
  if ( *(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x1800203a8  mov     [rsp+arg_8], rbx
0x1800203ad  mov     [rsp+arg_10], rsi
0x1800203b2  push    rdi
0x1800203b3  sub     rsp, 100h
0x1800203ba  mov     rdi, rcx
0x1800203bd  mov     [rsp+108h+SRWLock], 0
0x1800203c6  lea     rdx, [rsp+108h+SRWLock]
0x1800203cb  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800203d0  mov     rax, [rdi+110h]
0x1800203d7  mov     esi, [rax+0F8h]
0x1800203dd  cmp     esi, 1
0x1800203e0  jl      loc_1800204D1
0x1800203e6  mov     ebx, [rax+48h]
0x1800203e9  test    ebx, ebx
0x1800203eb  js      short loc_1800203F6
0x1800203ed  mov     dword ptr [rax+48h], 0
0x1800203f4  xor     ebx, ebx
0x1800203f6  dec     esi
0x1800203f8  mov     [rax+0F8h], esi
0x1800203fe  mov     rcx, [rsp+108h+SRWLock]; SRWLock
0x180020403  test    rcx, rcx
0x180020406  jz      short loc_180020414
0x180020408  call    cs:__imp_ReleaseSRWLockExclusive
0x18002040f  nop     dword ptr [rax+rax+00h]
0x180020414  test    esi, esi
0x180020416  jnz     short loc_180020427
0x180020418  mov     edx, ebx
0x18002041a  mov     rcx, rdi
0x18002041d  call    ?ReportStopActivity@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLib@@$00$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,1,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x180020422  jmp     loc_1800204A8
0x180020427  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18002042c  mov     rbx, rax
0x18002042f  mov     ecx, [rax]
0x180020431  cmp     ecx, 5
0x180020434  jbe     short loc_1800204A8
0x180020436  mov     rax, [rax+18h]
0x18002043a  mov     rcx, [rbx+10h]
0x18002043e  test    cl, 40h
0x180020441  jz      short loc_1800204A8
0x180020443  mov     rcx, rax
0x180020446  and     ecx, 40h
0x180020449  cmp     rcx, rax
0x18002044c  jnz     short loc_1800204A8
0x18002044e  call    cs:__imp_GetCurrentThreadId
0x180020455  nop     dword ptr [rax+rax+00h]
0x18002045a  mov     [rsp+108h+var_C0], eax
0x18002045e  mov     dword ptr [rsp+108h+SRWLock], 0
0x180020466  mov     [rsp+108h+var_B8], 1000000h
0x18002046f  mov     r8, [rdi+110h]
0x180020476  add     r8, 8
0x18002047a  lea     rax, [rsp+108h+var_C0]
0x18002047f  mov     [rsp+108h+var_D8], rax
0x180020484  lea     rax, [rsp+108h+SRWLock]
0x180020489  mov     [rsp+108h+var_E0], rax
0x18002048e  lea     rax, [rsp+108h+var_B8]
0x180020493  mov     [rsp+108h+var_E8], rax
0x180020498  lea     rdx, byte_180055641
0x18002049f  mov     rcx, rbx
0x1800204a2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800204a7  nop
0x1800204a8  lea     rcx, [rdi+120h]; this
0x1800204af  cmp     dword ptr [rcx+18h], 0
0x1800204b3  jz      short loc_1800204BB
0x1800204b5  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800204ba  nop
0x1800204bb  lea     r11, [rsp+108h+var_8]
0x1800204c3  mov     rbx, [r11+18h]
0x1800204c7  mov     rsi, [r11+20h]
0x1800204cb  mov     rsp, r11
0x1800204ce  pop     rdi
0x1800204cf  retn
0x1800204d1  xor     edx, edx; Val
0x1800204d3  mov     r8d, 98h; Size
0x1800204d9  lea     rcx, [rsp+108h+var_A8]; void *
0x1800204de  call    memset_0
0x1800204e3  lea     rcx, [rsp+108h+var_A8]; this
0x1800204e8  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
