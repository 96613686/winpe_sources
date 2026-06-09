# wil::ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18001054c`
- end: `0x1800106a9`
- name: `?Stop@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `349`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x18000d8f0`
- `0x18000e140`
- `0x18000e5a0`

## callees

- `0x180001660`
- `0x18000362c`
- `0x180007dd0`
- `0x18000895c`
- `0x18000af0c`
- `0x18000bb0c`
- `0x18001054c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800105a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800105a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800105fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800105fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1,
        DWORD a2)
{
  __int64 v3; // rax
  int v4; // edi
  int v5; // edi
  const struct _tlgProvider_t *v6; // rax
  const struct _tlgProvider_t *v7; // rdi
  __int64 v8; // rax
  int v9; // r9d
  const struct wil::FailureInfo *v10; // rdx
  _BYTE v11[168]; // [rsp+40h] [rbp-A8h] BYREF
  PSRWLOCK SRWLock; // [rsp+F0h] [rbp+8h] BYREF
  DWORD CurrentThreadId; // [rsp+F8h] [rbp+10h] BYREF
  __int64 v14; // [rsp+100h] [rbp+18h] BYREF

  CurrentThreadId = a2;
  wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v3 = *(_QWORD *)(a1 + 272);
  v4 = *(_DWORD *)(v3 + 248);
  if ( v4 < 1 )
  {
    memset_0(v11, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v11, v10);
  }
  if ( *(int *)(v3 + 72) >= 0 )
    *(_DWORD *)(v3 + 72) = 0;
  v5 = v4 - 1;
  *(_DWORD *)(v3 + 248) = v5;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v5 )
  {
    v6 = ContainerProvider::Provider();
    v7 = v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      v8 = *((_QWORD *)v6 + 3);
      if ( (*((_QWORD *)v7 + 2) & 0x400000000000LL) != 0 && (v8 & 0x400000000000LL) == v8 )
      {
        CurrentThreadId = GetCurrentThreadId();
        LODWORD(SRWLock) = 0;
        v14 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v7,
          (unsigned int)&unk_18003BC80,
          *(_QWORD *)(a1 + 272) + 8,
          v9,
          (__int64)&v14,
          (__int64)&SRWLock,
          (__int64)&CurrentThreadId);
      }
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
0x18001054c  mov     rax, rsp
0x18001054f  mov     [rax+20h], rbx
0x180010553  mov     [rax+10h], edx
0x180010556  push    rdi
0x180010557  sub     rsp, 0E0h
0x18001055e  mov     rbx, rcx
0x180010561  lea     rdx, [rax+8]
0x180010565  call    ?LockExclusive@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001056a  mov     rax, [rbx+110h]
0x180010571  mov     edi, [rax+0F8h]
0x180010577  cmp     edi, 1
0x18001057a  jl      loc_18001068C
0x180010580  cmp     dword ptr [rax+48h], 0
0x180010584  jl      short loc_18001058D
0x180010586  mov     dword ptr [rax+48h], 0
0x18001058d  dec     edi
0x18001058f  mov     [rax+0F8h], edi
0x180010595  mov     rcx, [rsp+0E8h+SRWLock]; SRWLock
0x18001059d  test    rcx, rcx
0x1800105a0  jz      short loc_1800105AE
0x1800105a2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800105a9  nop     dword ptr [rax+rax+00h]
0x1800105ae  test    edi, edi
0x1800105b0  jnz     short loc_1800105C6
0x1800105b2  mov     rax, [rbx]
0x1800105b5  mov     rcx, rbx
0x1800105b8  mov     rax, [rax+8]
0x1800105bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105c1  jmp     loc_180010667
0x1800105c6  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x1800105cb  mov     rdi, rax
0x1800105ce  mov     ecx, [rax]
0x1800105d0  cmp     ecx, 5
0x1800105d3  jbe     loc_180010667
0x1800105d9  mov     rax, [rax+18h]
0x1800105dd  mov     rcx, [rdi+10h]
0x1800105e1  mov     rdx, 400000000000h
0x1800105eb  test    rdx, rcx
0x1800105ee  jz      short loc_180010667
0x1800105f0  mov     rcx, rax
0x1800105f3  and     rcx, rdx
0x1800105f6  cmp     rcx, rax
0x1800105f9  jnz     short loc_180010667
0x1800105fb  call    cs:__imp_GetCurrentThreadId
0x180010602  nop     dword ptr [rax+rax+00h]
0x180010607  mov     [rsp+0E8h+arg_8], eax
0x18001060e  mov     dword ptr [rsp+0E8h+SRWLock], 0
0x180010619  mov     [rsp+0E8h+arg_10], 1000000h
0x180010625  mov     r8, [rbx+110h]
0x18001062c  add     r8, 8
0x180010630  lea     rax, [rsp+0E8h+arg_8]
0x180010638  mov     [rsp+0E8h+var_B8], rax
0x18001063d  lea     rax, [rsp+0E8h+SRWLock]
0x180010645  mov     [rsp+0E8h+var_C0], rax
0x18001064a  lea     rax, [rsp+0E8h+arg_10]
0x180010652  mov     [rsp+0E8h+var_C8], rax
0x180010657  lea     rdx, unk_18003BC80
0x18001065e  mov     rcx, rdi
0x180010661  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180010666  nop
0x180010667  lea     rcx, [rbx+120h]; this
0x18001066e  cmp     dword ptr [rcx+18h], 0
0x180010672  jz      short loc_18001067A
0x180010674  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180010679  nop
0x18001067a  mov     rbx, [rsp+0E8h+arg_18]
0x180010682  add     rsp, 0E0h
0x180010689  pop     rdi
0x18001068a  retn
0x18001068c  xor     edx, edx; Val
0x18001068e  mov     r8d, 98h; Size
0x180010694  lea     rcx, [rsp+0E8h+var_A8]; void *
0x180010699  call    memset_0
0x18001069e  lea     rcx, [rsp+0E8h+var_A8]; this
0x1800106a3  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
