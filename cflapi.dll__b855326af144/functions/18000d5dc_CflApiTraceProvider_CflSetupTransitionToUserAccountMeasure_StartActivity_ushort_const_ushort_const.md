# CflApiTraceProvider::CflSetupTransitionToUserAccountMeasure::StartActivity(ushort const *,ushort const *)

- ea: `0x18000d5dc`
- end: `0x18000d785`
- name: `?StartActivity@CflSetupTransitionToUserAccountMeasure@CflApiTraceProvider@@QEAAXPEBG0@Z`
- size: `425`
- prototype: `void __fastcall(CflApiTraceProvider::CflSetupTransitionToUserAccountMeasure *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180011f20`

## callees

- `0x180001bfc`
- `0x1800058b0`
- `0x18000a31c`
- `0x18000a4b8`
- `0x18000d5dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d663`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d663`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d6aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d75e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d6aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d75e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000d644`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000d644`

## pseudocode

```c
void __fastcall CflApiTraceProvider::CflSetupTransitionToUserAccountMeasure::StartActivity(
        CflApiTraceProvider::CflSetupTransitionToUserAccountMeasure *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rdi
  __int64 v7; // r9
  RTL_SRWLOCK *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  int v14; // r9d
  char *v15; // rbx
  _QWORD *Local; // rax
  const unsigned __int16 *v17; // [rsp+40h] [rbp-28h] BYREF
  __int64 v18; // [rsp+48h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+70h] [rbp+8h] BYREF
  const unsigned __int16 *v20; // [rsp+88h] [rbp+20h] BYREF

  wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
  v6 = *((_QWORD *)this + 34);
  v7 = *((_QWORD *)CflApiTraceProvider::Instance() + 1);
  if ( *(_DWORD *)v7 > 5u
    && (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v7 + 24) & 0x400000000000LL) == *(_QWORD *)(v7 + 24) )
  {
    EventActivityIdControl(3u, (LPGUID)(v6 + 8));
  }
  else
  {
    *(_OWORD *)(v6 + 8) = 0;
  }
  v8 = SRWLock;
  *(_DWORD *)v6 = 1;
  if ( v8 )
    ReleaseSRWLockExclusive(v8);
  v11 = *((_QWORD *)CflApiTraceProvider::Instance() + 1);
  if ( *(_DWORD *)v11 > 5u )
  {
    v10 = *(_QWORD *)(v11 + 24);
    if ( (*(_QWORD *)(v11 + 16) & 0x400000000000LL) != 0 && (v10 & 0x400000000000LL) == v10 )
    {
      v20 = a3;
      v17 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v13 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v18 = 0;
      if ( !*(_BYTE *)(v13 + 4)
        || (v14 = v13 + 24, !*(_DWORD *)(v13 + 24))
        && !*(_DWORD *)(v13 + 28)
        && !*(_DWORD *)(v13 + 32)
        && !*(_DWORD *)(v13 + 36) )
      {
        v14 = 0;
      }
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v11,
        (unsigned int)&unk_180037060,
        v13 + 8,
        v14,
        (__int64)&v18,
        (__int64)&SRWLock,
        (__int64)&v17,
        (__int64)&v20);
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v15 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v9) = 1;
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v10,
                          v9);
      *(_QWORD *)v15 = Local;
      if ( Local )
      {
        *((_QWORD *)v15 + 2) = *Local;
        *Local = v15;
        *((_DWORD *)v15 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v15 = 0;
    }
  }
}

```

## disassembly

```asm
0x18000d5dc  mov     [rsp+arg_8], rbx
0x18000d5e1  mov     [rsp+arg_10], rbp
0x18000d5e6  push    rsi
0x18000d5e7  push    rdi
0x18000d5e8  push    r15
0x18000d5ea  sub     rsp, 50h
0x18000d5ee  mov     rbp, rdx
0x18000d5f1  mov     rsi, r8
0x18000d5f4  lea     rdx, [rsp+68h+SRWLock]
0x18000d5f9  mov     rbx, rcx
0x18000d5fc  call    ?LockExclusive@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000d601  mov     rdi, [rbx+110h]
0x18000d608  call    ?Instance@CflApiTraceProvider@@KAPEAV1@XZ; CflApiTraceProvider::Instance(void)
0x18000d60d  mov     r15, 400000000000h
0x18000d617  mov     r9, [rax+8]
0x18000d61b  mov     eax, [r9]
0x18000d61e  cmp     eax, 5
0x18000d621  jbe     short loc_18000D64C
0x18000d623  mov     rcx, [r9+18h]
0x18000d627  mov     rax, [r9+10h]
0x18000d62b  test    r15, rax
0x18000d62e  jz      short loc_18000D64C
0x18000d630  mov     rax, rcx
0x18000d633  and     rax, r15
0x18000d636  cmp     rax, rcx
0x18000d639  jnz     short loc_18000D64C
0x18000d63b  lea     rdx, [rdi+8]; ActivityId
0x18000d63f  mov     ecx, 3; ControlCode
0x18000d644  call    cs:__imp_EventActivityIdControl
0x18000d64a  jmp     short loc_18000D653
0x18000d64c  xorps   xmm0, xmm0
0x18000d64f  movups  xmmword ptr [rdi+8], xmm0
0x18000d653  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x18000d658  mov     dword ptr [rdi], 1
0x18000d65e  test    rcx, rcx
0x18000d661  jz      short loc_18000D669
0x18000d663  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d669  call    ?Instance@CflApiTraceProvider@@KAPEAV1@XZ; CflApiTraceProvider::Instance(void)
0x18000d66e  mov     rdi, [rax+8]
0x18000d672  mov     eax, [rdi]
0x18000d674  cmp     eax, 5
0x18000d677  jbe     loc_18000D72B
0x18000d67d  mov     rcx, [rdi+18h]
0x18000d681  mov     rax, [rdi+10h]
0x18000d685  test    r15, rax
0x18000d688  jz      loc_18000D72B
0x18000d68e  mov     rax, rcx
0x18000d691  and     rax, r15
0x18000d694  cmp     rax, rcx
0x18000d697  jnz     loc_18000D72B
0x18000d69d  mov     [rsp+68h+arg_18], rsi
0x18000d6a5  mov     [rsp+68h+var_28], rbp
0x18000d6aa  call    cs:__imp_GetCurrentThreadId
0x18000d6b0  mov     r8, [rbx+110h]
0x18000d6b7  mov     dword ptr [rsp+68h+SRWLock], eax
0x18000d6bb  mov     [rsp+68h+var_20], 0
0x18000d6c4  cmp     byte ptr [r8+4], 0
0x18000d6c9  jz      short loc_18000D6EA
0x18000d6cb  lea     r9, [r8+18h]
0x18000d6cf  cmp     dword ptr [r9], 0
0x18000d6d3  jnz     short loc_18000D6ED
0x18000d6d5  cmp     dword ptr [r9+4], 0
0x18000d6da  jnz     short loc_18000D6ED
0x18000d6dc  cmp     dword ptr [r9+8], 0
0x18000d6e1  jnz     short loc_18000D6ED
0x18000d6e3  cmp     dword ptr [r9+0Ch], 0
0x18000d6e8  jnz     short loc_18000D6ED
0x18000d6ea  xor     r9d, r9d
0x18000d6ed  lea     rax, [rsp+68h+arg_18]
0x18000d6f5  add     r8, 8
0x18000d6f9  mov     [rsp+68h+var_30], rax
0x18000d6fe  lea     rdx, unk_180037060
0x18000d705  lea     rax, [rsp+68h+var_28]
0x18000d70a  mov     rcx, rdi
0x18000d70d  mov     [rsp+68h+var_38], rax
0x18000d712  lea     rax, [rsp+68h+SRWLock]
0x18000d717  mov     [rsp+68h+var_40], rax
0x18000d71c  lea     rax, [rsp+68h+var_20]
0x18000d721  mov     [rsp+68h+var_48], rax
0x18000d726  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000d72b  cmp     dword ptr [rbx+138h], 0
0x18000d732  jnz     short loc_18000D770
0x18000d734  add     rbx, 120h
0x18000d73b  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000d743  jz      short loc_18000D769
0x18000d745  mov     dl, 1
0x18000d747  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000d74c  mov     [rbx], rax
0x18000d74f  test    rax, rax
0x18000d752  jz      short loc_18000D770
0x18000d754  mov     rcx, [rax]
0x18000d757  mov     [rbx+10h], rcx
0x18000d75b  mov     [rax], rbx
0x18000d75e  call    cs:__imp_GetCurrentThreadId
0x18000d764  mov     [rbx+18h], eax
0x18000d767  jmp     short loc_18000D770
0x18000d769  mov     qword ptr [rbx], 0
0x18000d770  lea     r11, [rsp+68h+var_18]
0x18000d775  mov     rbx, [r11+28h]
0x18000d779  mov     rbp, [r11+30h]
0x18000d77d  mov     rsp, r11
0x18000d780  pop     r15
0x18000d782  pop     rdi
0x18000d783  pop     rsi
0x18000d784  retn
```
