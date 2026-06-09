# wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x1800106b0`
- end: `0x18001080d`
- name: `?Stop@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000e5a0`

## callees

- `0x180001660`
- `0x18000362c`
- `0x180007dd0`
- `0x18000895c`
- `0x18000af0c`
- `0x18000bb0c`
- `0x1800106b0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010706`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010706`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001075f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001075f`

## pseudocode

```c
void __fastcall wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::Stop(
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
          (unsigned int)&word_18003C77E,
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
0x1800106b0  mov     rax, rsp
0x1800106b3  mov     [rax+20h], rbx
0x1800106b7  mov     [rax+10h], edx
0x1800106ba  push    rdi
0x1800106bb  sub     rsp, 0E0h
0x1800106c2  mov     rbx, rcx
0x1800106c5  lea     rdx, [rax+8]
0x1800106c9  call    ?LockExclusive@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800106ce  mov     rax, [rbx+110h]
0x1800106d5  mov     edi, [rax+0F8h]
0x1800106db  cmp     edi, 1
0x1800106de  jl      loc_1800107F0
0x1800106e4  cmp     dword ptr [rax+48h], 0
0x1800106e8  jl      short loc_1800106F1
0x1800106ea  mov     dword ptr [rax+48h], 0
0x1800106f1  dec     edi
0x1800106f3  mov     [rax+0F8h], edi
0x1800106f9  mov     rcx, [rsp+0E8h+SRWLock]; SRWLock
0x180010701  test    rcx, rcx
0x180010704  jz      short loc_180010712
0x180010706  call    cs:__imp_ReleaseSRWLockExclusive
0x18001070d  nop     dword ptr [rax+rax+00h]
0x180010712  test    edi, edi
0x180010714  jnz     short loc_18001072A
0x180010716  mov     rax, [rbx]
0x180010719  mov     rcx, rbx
0x18001071c  mov     rax, [rax+8]
0x180010720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010725  jmp     loc_1800107CB
0x18001072a  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x18001072f  mov     rdi, rax
0x180010732  mov     ecx, [rax]
0x180010734  cmp     ecx, 5
0x180010737  jbe     loc_1800107CB
0x18001073d  mov     rax, [rax+18h]
0x180010741  mov     rcx, [rdi+10h]
0x180010745  mov     rdx, 400000000000h
0x18001074f  test    rdx, rcx
0x180010752  jz      short loc_1800107CB
0x180010754  mov     rcx, rax
0x180010757  and     rcx, rdx
0x18001075a  cmp     rcx, rax
0x18001075d  jnz     short loc_1800107CB
0x18001075f  call    cs:__imp_GetCurrentThreadId
0x180010766  nop     dword ptr [rax+rax+00h]
0x18001076b  mov     [rsp+0E8h+arg_8], eax
0x180010772  mov     dword ptr [rsp+0E8h+SRWLock], 0
0x18001077d  mov     [rsp+0E8h+arg_10], 1000000h
0x180010789  mov     r8, [rbx+110h]
0x180010790  add     r8, 8
0x180010794  lea     rax, [rsp+0E8h+arg_8]
0x18001079c  mov     [rsp+0E8h+var_B8], rax
0x1800107a1  lea     rax, [rsp+0E8h+SRWLock]
0x1800107a9  mov     [rsp+0E8h+var_C0], rax
0x1800107ae  lea     rax, [rsp+0E8h+arg_10]
0x1800107b6  mov     [rsp+0E8h+var_C8], rax
0x1800107bb  lea     rdx, word_18003C77E
0x1800107c2  mov     rcx, rdi
0x1800107c5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800107ca  nop
0x1800107cb  lea     rcx, [rbx+120h]; this
0x1800107d2  cmp     dword ptr [rcx+18h], 0
0x1800107d6  jz      short loc_1800107DE
0x1800107d8  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800107dd  nop
0x1800107de  mov     rbx, [rsp+0E8h+arg_18]
0x1800107e6  add     rsp, 0E0h
0x1800107ed  pop     rdi
0x1800107ee  retn
0x1800107f0  xor     edx, edx; Val
0x1800107f2  mov     r8d, 98h; Size
0x1800107f8  lea     rcx, [rsp+0E8h+var_A8]; void *
0x1800107fd  call    memset_0
0x180010802  lea     rcx, [rsp+0E8h+var_A8]; this
0x180010807  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
