# wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18000d8d8`
- end: `0x18000d9f3`
- name: `?Stop@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `283`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `11`
- callee_count: `8`
- tags: ``

## callers

- `0x18000ffb0`
- `0x1800101c0`
- `0x1800102f0`
- `0x180010470`
- `0x180010a00`
- `0x180010bd0`
- `0x180010db0`
- `0x180011230`
- `0x1800113b0`
- `0x180011b10`
- `0x180011dd0`

## callees

- `0x1800015d0`
- `0x180002ef8`
- `0x180007610`
- `0x18000a290`
- `0x18000a31c`
- `0x18000a4b8`
- `0x18000d8d8`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d92e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d92e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d959`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d959`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        DWORD a2)
{
  __int64 v3; // rax
  int v4; // edi
  int v5; // edi
  _DWORD *v6; // rdi
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
    v6 = (_DWORD *)*((_QWORD *)CflApiTraceProvider::Instance() + 1);
    if ( *v6 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      LODWORD(SRWLock) = 0;
      v12 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v6,
        (unsigned int)byte_180035F15,
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
0x18000d8d8  mov     rax, rsp
0x18000d8db  mov     [rax+20h], rbx
0x18000d8df  mov     [rax+10h], edx
0x18000d8e2  push    rdi
0x18000d8e3  sub     rsp, 0E0h
0x18000d8ea  mov     rbx, rcx
0x18000d8ed  lea     rdx, [rax+8]
0x18000d8f1  call    ?LockExclusive@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000d8f6  mov     rax, [rbx+110h]
0x18000d8fd  mov     edi, [rax+0F8h]
0x18000d903  cmp     edi, 1
0x18000d906  jl      loc_18000D9D6
0x18000d90c  cmp     dword ptr [rax+48h], 0
0x18000d910  jl      short loc_18000D919
0x18000d912  mov     dword ptr [rax+48h], 0
0x18000d919  dec     edi
0x18000d91b  mov     [rax+0F8h], edi
0x18000d921  mov     rcx, [rsp+0E8h+SRWLock]; SRWLock
0x18000d929  test    rcx, rcx
0x18000d92c  jz      short loc_18000D934
0x18000d92e  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d934  test    edi, edi
0x18000d936  jnz     short loc_18000D949
0x18000d938  mov     rax, [rbx]
0x18000d93b  mov     rcx, rbx
0x18000d93e  mov     rax, [rax+8]
0x18000d942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d947  jmp     short loc_18000D9BE
0x18000d949  call    ?Instance@CflApiTraceProvider@@KAPEAV1@XZ; CflApiTraceProvider::Instance(void)
0x18000d94e  mov     rdi, [rax+8]
0x18000d952  mov     eax, [rdi]
0x18000d954  cmp     eax, 5
0x18000d957  jbe     short loc_18000D9BE
0x18000d959  call    cs:__imp_GetCurrentThreadId
0x18000d95f  mov     [rsp+0E8h+arg_8], eax
0x18000d966  mov     dword ptr [rsp+0E8h+SRWLock], 0
0x18000d971  mov     [rsp+0E8h+arg_10], 1000000h
0x18000d97d  mov     r8, [rbx+110h]
0x18000d984  add     r8, 8
0x18000d988  lea     rax, [rsp+0E8h+arg_8]
0x18000d990  mov     [rsp+0E8h+var_B8], rax
0x18000d995  lea     rax, [rsp+0E8h+SRWLock]
0x18000d99d  mov     [rsp+0E8h+var_C0], rax
0x18000d9a2  lea     rax, [rsp+0E8h+arg_10]
0x18000d9aa  mov     [rsp+0E8h+var_C8], rax
0x18000d9af  lea     rdx, byte_180035F15
0x18000d9b6  mov     rcx, rdi
0x18000d9b9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000d9be  mov     rcx, rbx
0x18000d9c1  mov     rbx, [rsp+0E8h+arg_18]
0x18000d9c9  add     rsp, 0E0h
0x18000d9d0  pop     rdi
0x18000d9d1  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCflApiTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000d9d6  xor     edx, edx; Val
0x18000d9d8  mov     r8d, 98h; Size
0x18000d9de  lea     rcx, [rsp+0E8h+var_A8]; void *
0x18000d9e3  call    memset_0
0x18000d9e8  lea     rcx, [rsp+0E8h+var_A8]; this
0x18000d9ed  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
