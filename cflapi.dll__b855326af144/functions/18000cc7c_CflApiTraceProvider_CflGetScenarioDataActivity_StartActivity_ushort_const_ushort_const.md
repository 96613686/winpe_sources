# CflApiTraceProvider::CflGetScenarioDataActivity::StartActivity(ushort const *,ushort const *)

- ea: `0x18000cc7c`
- end: `0x18000cdd5`
- name: `?StartActivity@CflGetScenarioDataActivity@CflApiTraceProvider@@QEAAXPEBG0@Z`
- size: `345`
- prototype: `void __fastcall(CflApiTraceProvider::CflGetScenarioDataActivity *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180010a00`
- `0x180010bd0`

## callees

- `0x180001bfc`
- `0x1800058b0`
- `0x18000a31c`
- `0x18000a4b8`
- `0x18000cc7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ccdb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ccdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cd02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cdb6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cd02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cdb6`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000ccbc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000ccbc`

## pseudocode

```c
void __fastcall CflApiTraceProvider::CflGetScenarioDataActivity::StartActivity(
        CflApiTraceProvider::CflGetScenarioDataActivity *this,
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
      (unsigned int)word_180036A02,
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
0x18000cc7c  mov     [rsp+arg_8], rbx
0x18000cc81  push    rbp
0x18000cc82  push    rsi
0x18000cc83  push    rdi
0x18000cc84  sub     rsp, 50h
0x18000cc88  mov     rbp, rdx
0x18000cc8b  mov     rsi, r8
0x18000cc8e  lea     rdx, [rsp+68h+SRWLock]
0x18000cc93  mov     rbx, rcx
0x18000cc96  call    ?LockExclusive@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000cc9b  mov     rdi, [rbx+110h]
0x18000cca2  call    ?Instance@CflApiTraceProvider@@KAPEAV1@XZ; CflApiTraceProvider::Instance(void)
0x18000cca7  mov     r9, [rax+8]
0x18000ccab  mov     eax, [r9]
0x18000ccae  cmp     eax, 5
0x18000ccb1  jbe     short loc_18000CCC4
0x18000ccb3  lea     rdx, [rdi+8]; ActivityId
0x18000ccb7  mov     ecx, 3; ControlCode
0x18000ccbc  call    cs:__imp_EventActivityIdControl
0x18000ccc2  jmp     short loc_18000CCCB
0x18000ccc4  xorps   xmm0, xmm0
0x18000ccc7  movups  xmmword ptr [rdi+8], xmm0
0x18000cccb  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x18000ccd0  mov     dword ptr [rdi], 1
0x18000ccd6  test    rcx, rcx
0x18000ccd9  jz      short loc_18000CCE1
0x18000ccdb  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cce1  call    ?Instance@CflApiTraceProvider@@KAPEAV1@XZ; CflApiTraceProvider::Instance(void)
0x18000cce6  mov     rdi, [rax+8]
0x18000ccea  mov     eax, [rdi]
0x18000ccec  cmp     eax, 5
0x18000ccef  jbe     loc_18000CD83
0x18000ccf5  mov     [rsp+68h+arg_18], rsi
0x18000ccfd  mov     [rsp+68h+var_28], rbp
0x18000cd02  call    cs:__imp_GetCurrentThreadId
0x18000cd08  mov     r8, [rbx+110h]
0x18000cd0f  mov     dword ptr [rsp+68h+SRWLock], eax
0x18000cd13  mov     [rsp+68h+var_20], 0
0x18000cd1c  cmp     byte ptr [r8+4], 0
0x18000cd21  jz      short loc_18000CD42
0x18000cd23  lea     r9, [r8+18h]
0x18000cd27  cmp     dword ptr [r9], 0
0x18000cd2b  jnz     short loc_18000CD45
0x18000cd2d  cmp     dword ptr [r9+4], 0
0x18000cd32  jnz     short loc_18000CD45
0x18000cd34  cmp     dword ptr [r9+8], 0
0x18000cd39  jnz     short loc_18000CD45
0x18000cd3b  cmp     dword ptr [r9+0Ch], 0
0x18000cd40  jnz     short loc_18000CD45
0x18000cd42  xor     r9d, r9d
0x18000cd45  lea     rax, [rsp+68h+arg_18]
0x18000cd4d  add     r8, 8
0x18000cd51  mov     [rsp+68h+var_30], rax
0x18000cd56  lea     rdx, word_180036A02
0x18000cd5d  lea     rax, [rsp+68h+var_28]
0x18000cd62  mov     rcx, rdi
0x18000cd65  mov     [rsp+68h+var_38], rax
0x18000cd6a  lea     rax, [rsp+68h+SRWLock]
0x18000cd6f  mov     [rsp+68h+var_40], rax
0x18000cd74  lea     rax, [rsp+68h+var_20]
0x18000cd79  mov     [rsp+68h+var_48], rax
0x18000cd7e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000cd83  cmp     dword ptr [rbx+138h], 0
0x18000cd8a  jnz     short loc_18000CDC8
0x18000cd8c  add     rbx, 120h
0x18000cd93  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000cd9b  jz      short loc_18000CDC1
0x18000cd9d  mov     dl, 1
0x18000cd9f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000cda4  mov     [rbx], rax
0x18000cda7  test    rax, rax
0x18000cdaa  jz      short loc_18000CDC8
0x18000cdac  mov     rcx, [rax]
0x18000cdaf  mov     [rbx+10h], rcx
0x18000cdb3  mov     [rax], rbx
0x18000cdb6  call    cs:__imp_GetCurrentThreadId
0x18000cdbc  mov     [rbx+18h], eax
0x18000cdbf  jmp     short loc_18000CDC8
0x18000cdc1  mov     qword ptr [rbx], 0
0x18000cdc8  mov     rbx, [rsp+68h+arg_8]
0x18000cdcd  add     rsp, 50h
0x18000cdd1  pop     rdi
0x18000cdd2  pop     rsi
0x18000cdd3  pop     rbp
0x18000cdd4  retn
```
