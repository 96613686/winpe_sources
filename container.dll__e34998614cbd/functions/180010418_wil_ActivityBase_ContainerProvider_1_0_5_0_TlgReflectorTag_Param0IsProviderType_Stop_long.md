# wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180010418`
- end: `0x180010545`
- name: `?Stop@?$ActivityBase@VContainerProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `301`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `8`
- tags: ``

## callers

- `0x18000d710`
- `0x18000da40`
- `0x18000db40`
- `0x18000f560`
- `0x18000f620`
- `0x18000f6e0`
- `0x180022580`
- `0x18002b710`
- `0x18002c260`

## callees

- `0x180001660`
- `0x18000362c`
- `0x180007dd0`
- `0x18000895c`
- `0x18000af0c`
- `0x18000bb0c`
- `0x18000f2cc`
- `0x180010418`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001046e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001046e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010499`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010499`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1,
        int a2)
{
  __int64 v4; // rax
  int v5; // esi
  int v6; // edi
  int v7; // esi
  const struct _tlgProvider_t *v8; // rax
  int v9; // edi
  int v10; // r9d
  const struct wil::FailureInfo *v11; // rdx
  _BYTE v12[184]; // [rsp+40h] [rbp-B8h] BYREF
  PSRWLOCK SRWLock; // [rsp+100h] [rbp+8h] BYREF
  int v14; // [rsp+110h] [rbp+18h] BYREF
  __int64 v15; // [rsp+118h] [rbp+20h] BYREF

  wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v4 = *(_QWORD *)(a1 + 272);
  v5 = *(_DWORD *)(v4 + 248);
  if ( v5 < 1 )
  {
    memset_0(v12, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v12, v11);
  }
  v6 = *(_DWORD *)(v4 + 72);
  if ( v6 >= 0 )
  {
    *(_DWORD *)(v4 + 72) = a2;
    v6 = a2;
  }
  v7 = v5 - 1;
  *(_DWORD *)(v4 + 248) = v7;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v7 )
  {
    v8 = ContainerProvider::Provider();
    v9 = (int)v8;
    if ( *(_DWORD *)v8 > 5u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v14 = a2;
      v15 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)word_18003C34A,
        *(_QWORD *)(a1 + 272) + 8,
        v10,
        (__int64)&v15,
        (__int64)&v14,
        (__int64)&SRWLock);
    }
  }
  else
  {
    wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
      a1,
      (unsigned int)v6);
  }
  if ( *(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x180010418  mov     rax, rsp
0x18001041b  mov     [rax+10h], rbx
0x18001041f  push    rbp
0x180010420  push    rsi
0x180010421  push    rdi
0x180010422  sub     rsp, 0E0h
0x180010429  mov     ebp, edx
0x18001042b  mov     rbx, rcx
0x18001042e  lea     rdx, [rax+8]
0x180010432  call    ?LockExclusive@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180010437  mov     rax, [rbx+110h]
0x18001043e  mov     esi, [rax+0F8h]
0x180010444  cmp     esi, 1
0x180010447  jl      loc_180010528
0x18001044d  mov     edi, [rax+48h]
0x180010450  test    edi, edi
0x180010452  js      short loc_180010459
0x180010454  mov     [rax+48h], ebp
0x180010457  mov     edi, ebp
0x180010459  dec     esi
0x18001045b  mov     [rax+0F8h], esi
0x180010461  mov     rcx, [rsp+0F8h+SRWLock]; SRWLock
0x180010469  test    rcx, rcx
0x18001046c  jz      short loc_18001047A
0x18001046e  call    cs:__imp_ReleaseSRWLockExclusive
0x180010475  nop     dword ptr [rax+rax+00h]
0x18001047a  test    esi, esi
0x18001047c  jnz     short loc_18001048A
0x18001047e  mov     edx, edi
0x180010480  mov     rcx, rbx
0x180010483  call    ?ReportStopActivity@?$ActivityBase@VContainerProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x180010488  jmp     short loc_180010501
0x18001048a  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x18001048f  mov     rdi, rax
0x180010492  mov     ecx, [rax]
0x180010494  cmp     ecx, 5
0x180010497  jbe     short loc_180010501
0x180010499  call    cs:__imp_GetCurrentThreadId
0x1800104a0  nop     dword ptr [rax+rax+00h]
0x1800104a5  mov     dword ptr [rsp+0F8h+SRWLock], eax
0x1800104ac  mov     [rsp+0F8h+arg_10], ebp
0x1800104b3  mov     [rsp+0F8h+arg_18], 1000000h
0x1800104bf  mov     r8, [rbx+110h]
0x1800104c6  add     r8, 8
0x1800104ca  lea     rax, [rsp+0F8h+SRWLock]
0x1800104d2  mov     [rsp+0F8h+var_C8], rax
0x1800104d7  lea     rax, [rsp+0F8h+arg_10]
0x1800104df  mov     [rsp+0F8h+var_D0], rax
0x1800104e4  lea     rax, [rsp+0F8h+arg_18]
0x1800104ec  mov     [rsp+0F8h+var_D8], rax
0x1800104f1  lea     rdx, word_18003C34A
0x1800104f8  mov     rcx, rdi
0x1800104fb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180010500  nop
0x180010501  lea     rcx, [rbx+120h]; this
0x180010508  cmp     dword ptr [rcx+18h], 0
0x18001050c  jz      short loc_180010514
0x18001050e  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180010513  nop
0x180010514  mov     rbx, [rsp+0F8h+arg_8]
0x18001051c  add     rsp, 0E0h
0x180010523  pop     rdi
0x180010524  pop     rsi
0x180010525  pop     rbp
0x180010526  retn
0x180010528  xor     edx, edx; Val
0x18001052a  mov     r8d, 98h; Size
0x180010530  lea     rcx, [rsp+0F8h+var_B8]; void *
0x180010535  call    memset_0
0x18001053a  lea     rcx, [rsp+0F8h+var_B8]; this
0x18001053f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
