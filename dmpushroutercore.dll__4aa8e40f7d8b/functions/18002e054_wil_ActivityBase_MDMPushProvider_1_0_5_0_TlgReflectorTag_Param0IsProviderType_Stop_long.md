# wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18002e054`
- end: `0x18002e164`
- name: `?Stop@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `272`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x180027394`
- `0x180029994`
- `0x18002ccec`

## callees

- `0x180001cb4`
- `0x1800043a8`
- `0x18000d1c0`
- `0x18002cc70`
- `0x18002cef8`
- `0x18002d36c`
- `0x18002d45c`
- `0x18002e054`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e0d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e0d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002e0ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002e0ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1,
        DWORD a2)
{
  __int64 v3; // rax
  int v4; // esi
  int v5; // edi
  int v6; // esi
  const struct _tlgProvider_t *v7; // rax
  int v8; // edi
  int v9; // r9d
  const struct wil::FailureInfo *v10; // rdx
  _BYTE v11[184]; // [rsp+40h] [rbp-B8h] BYREF
  PSRWLOCK SRWLock; // [rsp+100h] [rbp+8h] BYREF
  DWORD CurrentThreadId; // [rsp+108h] [rbp+10h] BYREF
  __int64 v14; // [rsp+110h] [rbp+18h] BYREF

  CurrentThreadId = a2;
  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(a1, &SRWLock);
  v3 = *(_QWORD *)(a1 + 272);
  v4 = *(_DWORD *)(v3 + 248);
  if ( v4 < 1 )
  {
    memset_0(v11, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v11, v10);
  }
  v5 = *(_DWORD *)(v3 + 72);
  if ( v5 >= 0 )
  {
    *(_DWORD *)(v3 + 72) = 0;
    v5 = 0;
  }
  v6 = v4 - 1;
  *(_DWORD *)(v3 + 248) = v6;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v6 )
  {
    v7 = MDMPushProvider::Provider();
    v8 = (int)v7;
    if ( *(_DWORD *)v7 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      LODWORD(SRWLock) = 0;
      v14 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v8,
        (unsigned int)byte_18004700B,
        *(_QWORD *)(a1 + 272) + 8,
        v9,
        (__int64)&v14,
        (__int64)&SRWLock,
        (__int64)&CurrentThreadId);
    }
  }
  else
  {
    wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
      a1,
      (unsigned int)v5);
  }
  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x18002e054  mov     rax, rsp
0x18002e057  mov     [rax+10h], edx
0x18002e05a  push    rbx
0x18002e05b  push    rsi
0x18002e05c  push    rdi
0x18002e05d  sub     rsp, 0E0h
0x18002e064  mov     rbx, rcx
0x18002e067  lea     rdx, [rax+8]
0x18002e06b  call    ?LockExclusive@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002e070  mov     rax, [rbx+110h]
0x18002e077  mov     esi, [rax+0F8h]
0x18002e07d  cmp     esi, 1
0x18002e080  jl      loc_18002E147
0x18002e086  mov     edi, [rax+48h]
0x18002e089  test    edi, edi
0x18002e08b  js      short loc_18002E096
0x18002e08d  mov     dword ptr [rax+48h], 0
0x18002e094  xor     edi, edi
0x18002e096  dec     esi
0x18002e098  mov     [rax+0F8h], esi
0x18002e09e  mov     rcx, [rsp+0F8h+SRWLock]; SRWLock
0x18002e0a6  test    rcx, rcx
0x18002e0a9  jz      short loc_18002E0B1
0x18002e0ab  call    cs:__imp_ReleaseSRWLockExclusive
0x18002e0b1  test    esi, esi
0x18002e0b3  jnz     short loc_18002E0C1
0x18002e0b5  mov     edx, edi
0x18002e0b7  mov     rcx, rbx
0x18002e0ba  call    ?ReportStopActivity@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x18002e0bf  jmp     short loc_18002E135
0x18002e0c1  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x18002e0c6  mov     rdi, rax
0x18002e0c9  mov     ecx, [rax]
0x18002e0cb  cmp     ecx, 5
0x18002e0ce  jbe     short loc_18002E135
0x18002e0d0  call    cs:__imp_GetCurrentThreadId
0x18002e0d6  mov     [rsp+0F8h+arg_8], eax
0x18002e0dd  mov     dword ptr [rsp+0F8h+SRWLock], 0
0x18002e0e8  mov     [rsp+0F8h+arg_10], 1000000h
0x18002e0f4  mov     r8, [rbx+110h]
0x18002e0fb  add     r8, 8
0x18002e0ff  lea     rax, [rsp+0F8h+arg_8]
0x18002e107  mov     [rsp+0F8h+var_C8], rax
0x18002e10c  lea     rax, [rsp+0F8h+SRWLock]
0x18002e114  mov     [rsp+0F8h+var_D0], rax
0x18002e119  lea     rax, [rsp+0F8h+arg_10]
0x18002e121  mov     [rsp+0F8h+var_D8], rax
0x18002e126  lea     rdx, byte_18004700B
0x18002e12d  mov     rcx, rdi
0x18002e130  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002e135  mov     rcx, rbx
0x18002e138  add     rsp, 0E0h
0x18002e13f  pop     rdi
0x18002e140  pop     rsi
0x18002e141  pop     rbx
0x18002e142  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18002e147  xor     edx, edx; Val
0x18002e149  mov     r8d, 98h; Size
0x18002e14f  lea     rcx, [rsp+0F8h+var_B8]; void *
0x18002e154  call    memset_0
0x18002e159  lea     rcx, [rsp+0F8h+var_B8]; this
0x18002e15e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
