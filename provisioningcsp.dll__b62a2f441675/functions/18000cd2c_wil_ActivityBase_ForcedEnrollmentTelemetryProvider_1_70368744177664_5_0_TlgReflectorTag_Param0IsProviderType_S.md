# wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18000cd2c`
- end: `0x18000ce5e`
- name: `?Stop@?$ActivityBase@VForcedEnrollmentTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `306`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x18000bb80`
- `0x18000bd70`
- `0x18000c7d0`

## callees

- `0x180001404`
- `0x18000768c`
- `0x18000bec0`
- `0x18000bf44`
- `0x18000c3fc`
- `0x18000cd2c`
- `0x18003586a`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cdd0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cdd0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cd7b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cd7b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
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

  wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
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
    v5 = ForcedEnrollmentTelemetryProvider::Provider();
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
          (unsigned int)&dword_180040834,
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
  wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x18000cd2c  mov     [rsp+arg_8], rbx
0x18000cd31  push    rdi
0x18000cd32  sub     rsp, 100h
0x18000cd39  mov     rbx, rcx
0x18000cd3c  lea     rdx, [rsp+108h+SRWLock]
0x18000cd41  call    ?LockExclusive@?$ActivityBase@VForcedEnrollmentTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000cd46  mov     rax, [rbx+110h]
0x18000cd4d  mov     edi, [rax+0F8h]
0x18000cd53  cmp     edi, 1
0x18000cd56  jl      loc_18000CE41
0x18000cd5c  cmp     dword ptr [rax+48h], 0
0x18000cd60  jl      short loc_18000CD69
0x18000cd62  mov     dword ptr [rax+48h], 0
0x18000cd69  dec     edi
0x18000cd6b  mov     [rax+0F8h], edi
0x18000cd71  mov     rcx, [rsp+108h+SRWLock]; SRWLock
0x18000cd76  test    rcx, rcx
0x18000cd79  jz      short loc_18000CD87
0x18000cd7b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cd82  nop     dword ptr [rax+rax+00h]
0x18000cd87  test    edi, edi
0x18000cd89  jnz     short loc_18000CD9F
0x18000cd8b  mov     rax, [rbx]
0x18000cd8e  mov     rcx, rbx
0x18000cd91  mov     rax, [rax+8]
0x18000cd95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd9a  jmp     loc_18000CE29
0x18000cd9f  call    ?Provider@ForcedEnrollmentTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; ForcedEnrollmentTelemetryProvider::Provider(void)
0x18000cda4  mov     rdi, rax
0x18000cda7  mov     ecx, [rax]
0x18000cda9  cmp     ecx, 5
0x18000cdac  jbe     short loc_18000CE29
0x18000cdae  mov     rax, [rax+18h]
0x18000cdb2  mov     rcx, [rdi+10h]
0x18000cdb6  mov     rdx, 400000000000h
0x18000cdc0  test    rdx, rcx
0x18000cdc3  jz      short loc_18000CE29
0x18000cdc5  mov     rcx, rax
0x18000cdc8  and     rcx, rdx
0x18000cdcb  cmp     rcx, rax
0x18000cdce  jnz     short loc_18000CE29
0x18000cdd0  call    cs:__imp_GetCurrentThreadId
0x18000cdd7  nop     dword ptr [rax+rax+00h]
0x18000cddc  mov     [rsp+108h+var_C8], eax
0x18000cde0  mov     dword ptr [rsp+108h+SRWLock], 0
0x18000cde8  mov     [rsp+108h+var_B8], 1000000h
0x18000cdf1  mov     r8, [rbx+110h]
0x18000cdf8  add     r8, 8
0x18000cdfc  lea     rax, [rsp+108h+var_C8]
0x18000ce01  mov     [rsp+108h+var_D8], rax
0x18000ce06  lea     rax, [rsp+108h+SRWLock]
0x18000ce0b  mov     [rsp+108h+var_E0], rax
0x18000ce10  lea     rax, [rsp+108h+var_B8]
0x18000ce15  mov     [rsp+108h+var_E8], rax
0x18000ce1a  lea     rdx, dword_180040834
0x18000ce21  mov     rcx, rdi
0x18000ce24  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000ce29  mov     rcx, rbx
0x18000ce2c  mov     rbx, [rsp+108h+arg_8]
0x18000ce34  add     rsp, 100h
0x18000ce3b  pop     rdi
0x18000ce3c  jmp     ?IgnoreCurrentThread@?$ActivityBase@VForcedEnrollmentTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000ce41  xor     edx, edx; Val
0x18000ce43  mov     r8d, 98h; Size
0x18000ce49  lea     rcx, [rsp+108h+var_A8]; void *
0x18000ce4e  call    memset_0
0x18000ce53  lea     rcx, [rsp+108h+var_A8]; this
0x18000ce58  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
