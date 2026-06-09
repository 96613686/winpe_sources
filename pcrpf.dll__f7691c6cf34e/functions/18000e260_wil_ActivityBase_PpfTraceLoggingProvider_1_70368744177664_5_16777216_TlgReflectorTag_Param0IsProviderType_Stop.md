# wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18000e260`
- end: `0x18000e392`
- name: `?Stop@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `306`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x18000cfec`
- `0x18001b440`
- `0x18004f450`
- `0x180052728`

## callees

- `0x1800016e4`
- `0x180003cf0`
- `0x18000b30c`
- `0x18000cb38`
- `0x18000cbbc`
- `0x18000de98`
- `0x18000e260`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e2af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e2af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e304`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e304`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  __int64 v2; // rax
  int v3; // edi
  int v4; // edi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // r9
  const struct wil::FailureInfo *v9; // rdx
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C8h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE v13[168]; // [rsp+60h] [rbp-A8h] BYREF

  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)a1,
    &SRWLock);
  v2 = a1[34];
  v3 = *(_DWORD *)(v2 + 248);
  if ( v3 < 1 )
  {
    memset_0(v13, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v13, v9);
  }
  if ( *(int *)(v2 + 72) >= 0 )
    *(_DWORD *)(v2 + 72) = 0;
  v4 = v3 - 1;
  *(_DWORD *)(v2 + 248) = v4;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v4 )
  {
    v5 = PpfTraceLoggingProvider::Provider();
    v6 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0 && (v7 & 0x400000000000LL) == v7 )
      {
        CurrentThreadId = GetCurrentThreadId();
        LODWORD(SRWLock) = 0;
        v12 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v6,
          (__int64)byte_180067DD1,
          a1[34] + 8LL,
          v8,
          (__int64)&v12,
          (__int64)&SRWLock,
          (__int64)&CurrentThreadId);
      }
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x18000e260  mov     [rsp+arg_8], rbx
0x18000e265  push    rdi
0x18000e266  sub     rsp, 100h
0x18000e26d  mov     rbx, rcx
0x18000e270  lea     rdx, [rsp+108h+SRWLock]
0x18000e275  call    ?LockExclusive@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000e27a  mov     rax, [rbx+110h]
0x18000e281  mov     edi, [rax+0F8h]
0x18000e287  cmp     edi, 1
0x18000e28a  jl      loc_18000E375
0x18000e290  cmp     dword ptr [rax+48h], 0
0x18000e294  jl      short loc_18000E29D
0x18000e296  mov     dword ptr [rax+48h], 0
0x18000e29d  dec     edi
0x18000e29f  mov     [rax+0F8h], edi
0x18000e2a5  mov     rcx, [rsp+108h+SRWLock]; SRWLock
0x18000e2aa  test    rcx, rcx
0x18000e2ad  jz      short loc_18000E2BB
0x18000e2af  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e2b6  nop     dword ptr [rax+rax+00h]
0x18000e2bb  test    edi, edi
0x18000e2bd  jnz     short loc_18000E2D3
0x18000e2bf  mov     rax, [rbx]
0x18000e2c2  mov     rcx, rbx
0x18000e2c5  mov     rax, [rax+8]
0x18000e2c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2ce  jmp     loc_18000E35D
0x18000e2d3  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x18000e2d8  mov     rdi, rax
0x18000e2db  mov     ecx, [rax]
0x18000e2dd  cmp     ecx, 5
0x18000e2e0  jbe     short loc_18000E35D
0x18000e2e2  mov     rax, [rax+18h]
0x18000e2e6  mov     rcx, [rdi+10h]
0x18000e2ea  mov     rdx, 400000000000h
0x18000e2f4  test    rdx, rcx
0x18000e2f7  jz      short loc_18000E35D
0x18000e2f9  mov     rcx, rax
0x18000e2fc  and     rcx, rdx
0x18000e2ff  cmp     rcx, rax
0x18000e302  jnz     short loc_18000E35D
0x18000e304  call    cs:__imp_GetCurrentThreadId
0x18000e30b  nop     dword ptr [rax+rax+00h]
0x18000e310  mov     [rsp+108h+var_C8], eax
0x18000e314  mov     dword ptr [rsp+108h+SRWLock], 0
0x18000e31c  mov     [rsp+108h+var_B8], 1000000h
0x18000e325  mov     r8, [rbx+110h]
0x18000e32c  add     r8, 8
0x18000e330  lea     rax, [rsp+108h+var_C8]
0x18000e335  mov     [rsp+108h+var_D8], rax
0x18000e33a  lea     rax, [rsp+108h+SRWLock]
0x18000e33f  mov     [rsp+108h+var_E0], rax
0x18000e344  lea     rax, [rsp+108h+var_B8]
0x18000e349  mov     [rsp+108h+var_E8], rax
0x18000e34e  lea     rdx, byte_180067DD1
0x18000e355  mov     rcx, rdi
0x18000e358  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000e35d  mov     rcx, rbx
0x18000e360  mov     rbx, [rsp+108h+arg_8]
0x18000e368  add     rsp, 100h
0x18000e36f  pop     rdi
0x18000e370  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000e375  xor     edx, edx; Val
0x18000e377  mov     r8d, 98h; Size
0x18000e37d  lea     rcx, [rsp+108h+var_A8]; void *
0x18000e382  call    memset_0
0x18000e387  lea     rcx, [rsp+108h+var_A8]; this
0x18000e38c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
