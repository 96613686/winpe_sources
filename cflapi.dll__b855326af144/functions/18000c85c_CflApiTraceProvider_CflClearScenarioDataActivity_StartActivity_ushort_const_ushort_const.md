# CflApiTraceProvider::CflClearScenarioDataActivity::StartActivity(ushort const *,ushort const *)

- ea: `0x18000c85c`
- end: `0x18000c9b5`
- name: `?StartActivity@CflClearScenarioDataActivity@CflApiTraceProvider@@QEAAXPEBG0@Z`
- size: `345`
- prototype: `void __fastcall(CflApiTraceProvider::CflClearScenarioDataActivity *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ffb0`

## callees

- `0x180001bfc`
- `0x1800058b0`
- `0x18000a31c`
- `0x18000a4b8`
- `0x18000c85c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c8bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c8bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c8e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c996`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c8e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c996`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000c89c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000c89c`

## pseudocode

```c
void __fastcall CflApiTraceProvider::CflClearScenarioDataActivity::StartActivity(
        CflApiTraceProvider::CflClearScenarioDataActivity *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rdi
  RTL_SRWLOCK *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  _DWORD *v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  int v13; // r9d
  char *v14; // rbx
  _QWORD *Local; // rax
  const unsigned __int16 *v16; // [rsp+40h] [rbp-28h] BYREF
  _QWORD v17[4]; // [rsp+48h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+70h] [rbp+8h] BYREF
  const unsigned __int16 *v19; // [rsp+88h] [rbp+20h] BYREF

  wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
  v6 = *((_QWORD *)this + 34);
  if ( **((_DWORD **)CflApiTraceProvider::Instance() + 1) <= 5u )
    *(_OWORD *)(v6 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v6 + 8));
  v7 = SRWLock;
  *(_DWORD *)v6 = 1;
  if ( v7 )
    ReleaseSRWLockExclusive(v7);
  v10 = (_DWORD *)*((_QWORD *)CflApiTraceProvider::Instance() + 1);
  if ( *v10 > 5u )
  {
    v19 = a3;
    v16 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v12 = *((_QWORD *)this + 34);
    LODWORD(SRWLock) = CurrentThreadId;
    v17[0] = 0;
    if ( !*(_BYTE *)(v12 + 4)
      || (v13 = v12 + 24, !*(_DWORD *)(v12 + 24))
      && !*(_DWORD *)(v12 + 28)
      && !*(_DWORD *)(v12 + 32)
      && !*(_DWORD *)(v12 + 36) )
    {
      v13 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v10,
      (unsigned int)word_1800367E2,
      v12 + 8,
      v13,
      (__int64)v17,
      (__int64)&SRWLock,
      (__int64)&v16,
      (__int64)&v19);
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v14 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v8) = 1;
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v9,
                          v8);
      *(_QWORD *)v14 = Local;
      if ( Local )
      {
        *((_QWORD *)v14 + 2) = *Local;
        *Local = v14;
        *((_DWORD *)v14 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v14 = 0;
    }
  }
}

```

## disassembly

```asm
0x18000c85c  mov     [rsp+arg_8], rbx
0x18000c861  push    rbp
0x18000c862  push    rsi
0x18000c863  push    rdi
0x18000c864  sub     rsp, 50h
0x18000c868  mov     rbp, rdx
0x18000c86b  mov     rsi, r8
0x18000c86e  lea     rdx, [rsp+68h+SRWLock]
0x18000c873  mov     rbx, rcx
0x18000c876  call    ?LockExclusive@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000c87b  mov     rdi, [rbx+110h]
0x18000c882  call    ?Instance@CflApiTraceProvider@@KAPEAV1@XZ; CflApiTraceProvider::Instance(void)
0x18000c887  mov     r9, [rax+8]
0x18000c88b  mov     eax, [r9]
0x18000c88e  cmp     eax, 5
0x18000c891  jbe     short loc_18000C8A4
0x18000c893  lea     rdx, [rdi+8]; ActivityId
0x18000c897  mov     ecx, 3; ControlCode
0x18000c89c  call    cs:__imp_EventActivityIdControl
0x18000c8a2  jmp     short loc_18000C8AB
0x18000c8a4  xorps   xmm0, xmm0
0x18000c8a7  movups  xmmword ptr [rdi+8], xmm0
0x18000c8ab  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x18000c8b0  mov     dword ptr [rdi], 1
0x18000c8b6  test    rcx, rcx
0x18000c8b9  jz      short loc_18000C8C1
0x18000c8bb  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c8c1  call    ?Instance@CflApiTraceProvider@@KAPEAV1@XZ; CflApiTraceProvider::Instance(void)
0x18000c8c6  mov     rdi, [rax+8]
0x18000c8ca  mov     eax, [rdi]
0x18000c8cc  cmp     eax, 5
0x18000c8cf  jbe     loc_18000C963
0x18000c8d5  mov     [rsp+68h+arg_18], rsi
0x18000c8dd  mov     [rsp+68h+var_28], rbp
0x18000c8e2  call    cs:__imp_GetCurrentThreadId
0x18000c8e8  mov     r8, [rbx+110h]
0x18000c8ef  mov     dword ptr [rsp+68h+SRWLock], eax
0x18000c8f3  mov     [rsp+68h+var_20], 0
0x18000c8fc  cmp     byte ptr [r8+4], 0
0x18000c901  jz      short loc_18000C922
0x18000c903  lea     r9, [r8+18h]
0x18000c907  cmp     dword ptr [r9], 0
0x18000c90b  jnz     short loc_18000C925
0x18000c90d  cmp     dword ptr [r9+4], 0
0x18000c912  jnz     short loc_18000C925
0x18000c914  cmp     dword ptr [r9+8], 0
0x18000c919  jnz     short loc_18000C925
0x18000c91b  cmp     dword ptr [r9+0Ch], 0
0x18000c920  jnz     short loc_18000C925
0x18000c922  xor     r9d, r9d
0x18000c925  lea     rax, [rsp+68h+arg_18]
0x18000c92d  add     r8, 8
0x18000c931  mov     [rsp+68h+var_30], rax
0x18000c936  lea     rdx, word_1800367E2
0x18000c93d  lea     rax, [rsp+68h+var_28]
0x18000c942  mov     rcx, rdi
0x18000c945  mov     [rsp+68h+var_38], rax
0x18000c94a  lea     rax, [rsp+68h+SRWLock]
0x18000c94f  mov     [rsp+68h+var_40], rax
0x18000c954  lea     rax, [rsp+68h+var_20]
0x18000c959  mov     [rsp+68h+var_48], rax
0x18000c95e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000c963  cmp     dword ptr [rbx+138h], 0
0x18000c96a  jnz     short loc_18000C9A8
0x18000c96c  add     rbx, 120h
0x18000c973  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000c97b  jz      short loc_18000C9A1
0x18000c97d  mov     dl, 1
0x18000c97f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000c984  mov     [rbx], rax
0x18000c987  test    rax, rax
0x18000c98a  jz      short loc_18000C9A8
0x18000c98c  mov     rcx, [rax]
0x18000c98f  mov     [rbx+10h], rcx
0x18000c993  mov     [rax], rbx
0x18000c996  call    cs:__imp_GetCurrentThreadId
0x18000c99c  mov     [rbx+18h], eax
0x18000c99f  jmp     short loc_18000C9A8
0x18000c9a1  mov     qword ptr [rbx], 0
0x18000c9a8  mov     rbx, [rsp+68h+arg_8]
0x18000c9ad  add     rsp, 50h
0x18000c9b1  pop     rdi
0x18000c9b2  pop     rsi
0x18000c9b3  pop     rbp
0x18000c9b4  retn
```
