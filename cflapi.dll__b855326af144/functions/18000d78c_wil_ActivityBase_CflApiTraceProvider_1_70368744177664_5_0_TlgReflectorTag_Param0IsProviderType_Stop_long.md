# wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18000d78c`
- end: `0x18000d8d0`
- name: `?Stop@?$ActivityBase@VCflApiTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `324`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x180011770`
- `0x180011940`
- `0x180011f20`

## callees

- `0x1800015d0`
- `0x180002ef8`
- `0x180007610`
- `0x18000a290`
- `0x18000a31c`
- `0x18000a4b8`
- `0x18000d78c`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d7e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d7e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d836`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d836`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        DWORD a2)
{
  __int64 v3; // rax
  int v4; // edi
  int v5; // edi
  __int64 v6; // rdi
  int v7; // r9d
  const struct wil::FailureInfo *v8; // rdx
  _BYTE v9[168]; // [rsp+40h] [rbp-A8h] BYREF
  PSRWLOCK SRWLock; // [rsp+F0h] [rbp+8h] BYREF
  DWORD CurrentThreadId; // [rsp+F8h] [rbp+10h] BYREF
  __int64 v12; // [rsp+100h] [rbp+18h] BYREF

  CurrentThreadId = a2;
  wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(a1, &SRWLock);
  v3 = a1[34];
  v4 = *(_DWORD *)(v3 + 248);
  if ( v4 < 1 )
  {
    memset_0(v9, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v9, v8);
  }
  if ( *(int *)(v3 + 72) >= 0 )
    *(_DWORD *)(v3 + 72) = 0;
  v5 = v4 - 1;
  *(_DWORD *)(v3 + 248) = v5;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v5 )
  {
    v6 = *((_QWORD *)CflApiTraceProvider::Instance() + 1);
    if ( *(_DWORD *)v6 > 5u
      && (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x400000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      CurrentThreadId = GetCurrentThreadId();
      LODWORD(SRWLock) = 0;
      v12 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)&word_1800360A6,
        a1[34] + 8,
        v7,
        (__int64)&v12,
        (__int64)&SRWLock,
        (__int64)&CurrentThreadId);
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x18000d78c  mov     rax, rsp
0x18000d78f  mov     [rax+20h], rbx
0x18000d793  mov     [rax+10h], edx
0x18000d796  push    rdi
0x18000d797  sub     rsp, 0E0h
0x18000d79e  mov     rbx, rcx
0x18000d7a1  lea     rdx, [rax+8]
0x18000d7a5  call    ?LockExclusive@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000d7aa  mov     rax, [rbx+110h]
0x18000d7b1  mov     edi, [rax+0F8h]
0x18000d7b7  cmp     edi, 1
0x18000d7ba  jl      loc_18000D8B3
0x18000d7c0  cmp     dword ptr [rax+48h], 0
0x18000d7c4  jl      short loc_18000D7CD
0x18000d7c6  mov     dword ptr [rax+48h], 0
0x18000d7cd  dec     edi
0x18000d7cf  mov     [rax+0F8h], edi
0x18000d7d5  mov     rcx, [rsp+0E8h+SRWLock]; SRWLock
0x18000d7dd  test    rcx, rcx
0x18000d7e0  jz      short loc_18000D7E8
0x18000d7e2  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d7e8  test    edi, edi
0x18000d7ea  jnz     short loc_18000D800
0x18000d7ec  mov     rax, [rbx]
0x18000d7ef  mov     rcx, rbx
0x18000d7f2  mov     rax, [rax+8]
0x18000d7f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7fb  jmp     loc_18000D89B
0x18000d800  call    ?Instance@CflApiTraceProvider@@KAPEAV1@XZ; CflApiTraceProvider::Instance(void)
0x18000d805  mov     rdi, [rax+8]
0x18000d809  mov     eax, [rdi]
0x18000d80b  cmp     eax, 5
0x18000d80e  jbe     loc_18000D89B
0x18000d814  mov     rcx, [rdi+18h]
0x18000d818  mov     rax, [rdi+10h]
0x18000d81c  mov     rdx, 400000000000h
0x18000d826  test    rdx, rax
0x18000d829  jz      short loc_18000D89B
0x18000d82b  mov     rax, rcx
0x18000d82e  and     rax, rdx
0x18000d831  cmp     rax, rcx
0x18000d834  jnz     short loc_18000D89B
0x18000d836  call    cs:__imp_GetCurrentThreadId
0x18000d83c  mov     [rsp+0E8h+arg_8], eax
0x18000d843  mov     dword ptr [rsp+0E8h+SRWLock], 0
0x18000d84e  mov     [rsp+0E8h+arg_10], 1000000h
0x18000d85a  mov     r8, [rbx+110h]
0x18000d861  add     r8, 8
0x18000d865  lea     rax, [rsp+0E8h+arg_8]
0x18000d86d  mov     [rsp+0E8h+var_B8], rax
0x18000d872  lea     rax, [rsp+0E8h+SRWLock]
0x18000d87a  mov     [rsp+0E8h+var_C0], rax
0x18000d87f  lea     rax, [rsp+0E8h+arg_10]
0x18000d887  mov     [rsp+0E8h+var_C8], rax
0x18000d88c  lea     rdx, word_1800360A6
0x18000d893  mov     rcx, rdi
0x18000d896  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000d89b  mov     rcx, rbx
0x18000d89e  mov     rbx, [rsp+0E8h+arg_18]
0x18000d8a6  add     rsp, 0E0h
0x18000d8ad  pop     rdi
0x18000d8ae  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCflApiTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000d8b3  xor     edx, edx; Val
0x18000d8b5  mov     r8d, 98h; Size
0x18000d8bb  lea     rcx, [rsp+0E8h+var_A8]; void *
0x18000d8c0  call    memset_0
0x18000d8c5  lea     rcx, [rsp+0E8h+var_A8]; this
0x18000d8ca  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
