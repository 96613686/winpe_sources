# wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x140007d1c`
- end: `0x140007e4e`
- name: `?Stop@?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `306`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x140005fbc`
- `0x1400060a8`
- `0x140006188`
- `0x1400066e0`

## callees

- `0x1400012bc`
- `0x140002b2c`
- `0x14000547c`
- `0x140005644`
- `0x140006894`
- `0x140007d1c`
- `0x140008dcc`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007d6b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007d6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007dc0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007dc0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  __int64 v2; // rax
  int v3; // edi
  int v4; // edi
  const struct _tlgProvider_t *v5; // rax
  const struct _tlgProvider_t *v6; // rdi
  __int64 v7; // rax
  int v8; // r9d
  const struct wil::FailureInfo *v9; // rdx
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C8h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE v13[168]; // [rsp+60h] [rbp-A8h] BYREF

  wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
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
    v5 = WorkerEtwProvider::Provider();
    v6 = v5;
    if ( *(_DWORD *)v5 > 5u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*((_QWORD *)v6 + 2) & 0x400000000000LL) != 0 && (v7 & 0x400000000000LL) == v7 )
      {
        CurrentThreadId = GetCurrentThreadId();
        LODWORD(SRWLock) = 0;
        v12 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v6,
          (unsigned int)byte_1400390E3,
          a1[34] + 8,
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
  wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x140007d1c  mov     [rsp+arg_8], rbx
0x140007d21  push    rdi
0x140007d22  sub     rsp, 100h
0x140007d29  mov     rbx, rcx
0x140007d2c  lea     rdx, [rsp+108h+SRWLock]
0x140007d31  call    ?LockExclusive@?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140007d36  mov     rax, [rbx+110h]
0x140007d3d  mov     edi, [rax+0F8h]
0x140007d43  cmp     edi, 1
0x140007d46  jl      loc_140007E31
0x140007d4c  cmp     dword ptr [rax+48h], 0
0x140007d50  jl      short loc_140007D59
0x140007d52  mov     dword ptr [rax+48h], 0
0x140007d59  dec     edi
0x140007d5b  mov     [rax+0F8h], edi
0x140007d61  mov     rcx, [rsp+108h+SRWLock]; SRWLock
0x140007d66  test    rcx, rcx
0x140007d69  jz      short loc_140007D77
0x140007d6b  call    cs:__imp_ReleaseSRWLockExclusive
0x140007d72  nop     dword ptr [rax+rax+00h]
0x140007d77  test    edi, edi
0x140007d79  jnz     short loc_140007D8F
0x140007d7b  mov     rax, [rbx]
0x140007d7e  mov     rcx, rbx
0x140007d81  mov     rax, [rax+8]
0x140007d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007d8a  jmp     loc_140007E19
0x140007d8f  call    ?Provider@WorkerEtwProvider@@SAPEBU_tlgProvider_t@@XZ; WorkerEtwProvider::Provider(void)
0x140007d94  mov     rdi, rax
0x140007d97  mov     ecx, [rax]
0x140007d99  cmp     ecx, 5
0x140007d9c  jbe     short loc_140007E19
0x140007d9e  mov     rax, [rax+18h]
0x140007da2  mov     rcx, [rdi+10h]
0x140007da6  mov     rdx, 400000000000h
0x140007db0  test    rdx, rcx
0x140007db3  jz      short loc_140007E19
0x140007db5  mov     rcx, rax
0x140007db8  and     rcx, rdx
0x140007dbb  cmp     rcx, rax
0x140007dbe  jnz     short loc_140007E19
0x140007dc0  call    cs:__imp_GetCurrentThreadId
0x140007dc7  nop     dword ptr [rax+rax+00h]
0x140007dcc  mov     [rsp+108h+var_C8], eax
0x140007dd0  mov     dword ptr [rsp+108h+SRWLock], 0
0x140007dd8  mov     [rsp+108h+var_B8], 1000000h
0x140007de1  mov     r8, [rbx+110h]
0x140007de8  add     r8, 8
0x140007dec  lea     rax, [rsp+108h+var_C8]
0x140007df1  mov     [rsp+108h+var_D8], rax
0x140007df6  lea     rax, [rsp+108h+SRWLock]
0x140007dfb  mov     [rsp+108h+var_E0], rax
0x140007e00  lea     rax, [rsp+108h+var_B8]
0x140007e05  mov     [rsp+108h+var_E8], rax
0x140007e0a  lea     rdx, byte_1400390E3
0x140007e11  mov     rcx, rdi
0x140007e14  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140007e19  mov     rcx, rbx
0x140007e1c  mov     rbx, [rsp+108h+arg_8]
0x140007e24  add     rsp, 100h
0x140007e2b  pop     rdi
0x140007e2c  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x140007e31  xor     edx, edx; Val
0x140007e33  mov     r8d, 98h; Size
0x140007e39  lea     rcx, [rsp+108h+var_A8]; void *
0x140007e3e  call    memset_0
0x140007e43  lea     rcx, [rsp+108h+var_A8]; this
0x140007e48  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
