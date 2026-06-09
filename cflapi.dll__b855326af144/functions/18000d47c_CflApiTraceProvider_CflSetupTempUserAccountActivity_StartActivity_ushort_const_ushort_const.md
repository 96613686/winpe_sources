# CflApiTraceProvider::CflSetupTempUserAccountActivity::StartActivity(ushort const *,ushort const *)

- ea: `0x18000d47c`
- end: `0x18000d5d5`
- name: `?StartActivity@CflSetupTempUserAccountActivity@CflApiTraceProvider@@QEAAXPEBG0@Z`
- size: `345`
- prototype: `void __fastcall(CflApiTraceProvider::CflSetupTempUserAccountActivity *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180011dd0`

## callees

- `0x180001bfc`
- `0x1800058b0`
- `0x18000a31c`
- `0x18000a4b8`
- `0x18000d47c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d4db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d4db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d502`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d5b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d502`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d5b6`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000d4bc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000d4bc`

## pseudocode

```c
void __fastcall CflApiTraceProvider::CflSetupTempUserAccountActivity::StartActivity(
        CflApiTraceProvider::CflSetupTempUserAccountActivity *this,
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
      (unsigned int)byte_1800376CD,
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
0x18000d47c  mov     [rsp+arg_8], rbx
0x18000d481  push    rbp
0x18000d482  push    rsi
0x18000d483  push    rdi
0x18000d484  sub     rsp, 50h
0x18000d488  mov     rbp, rdx
0x18000d48b  mov     rsi, r8
0x18000d48e  lea     rdx, [rsp+68h+SRWLock]
0x18000d493  mov     rbx, rcx
0x18000d496  call    ?LockExclusive@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000d49b  mov     rdi, [rbx+110h]
0x18000d4a2  call    ?Instance@CflApiTraceProvider@@KAPEAV1@XZ; CflApiTraceProvider::Instance(void)
0x18000d4a7  mov     r9, [rax+8]
0x18000d4ab  mov     eax, [r9]
0x18000d4ae  cmp     eax, 5
0x18000d4b1  jbe     short loc_18000D4C4
0x18000d4b3  lea     rdx, [rdi+8]; ActivityId
0x18000d4b7  mov     ecx, 3; ControlCode
0x18000d4bc  call    cs:__imp_EventActivityIdControl
0x18000d4c2  jmp     short loc_18000D4CB
0x18000d4c4  xorps   xmm0, xmm0
0x18000d4c7  movups  xmmword ptr [rdi+8], xmm0
0x18000d4cb  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x18000d4d0  mov     dword ptr [rdi], 1
0x18000d4d6  test    rcx, rcx
0x18000d4d9  jz      short loc_18000D4E1
0x18000d4db  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d4e1  call    ?Instance@CflApiTraceProvider@@KAPEAV1@XZ; CflApiTraceProvider::Instance(void)
0x18000d4e6  mov     rdi, [rax+8]
0x18000d4ea  mov     eax, [rdi]
0x18000d4ec  cmp     eax, 5
0x18000d4ef  jbe     loc_18000D583
0x18000d4f5  mov     [rsp+68h+arg_18], rsi
0x18000d4fd  mov     [rsp+68h+var_28], rbp
0x18000d502  call    cs:__imp_GetCurrentThreadId
0x18000d508  mov     r8, [rbx+110h]
0x18000d50f  mov     dword ptr [rsp+68h+SRWLock], eax
0x18000d513  mov     [rsp+68h+var_20], 0
0x18000d51c  cmp     byte ptr [r8+4], 0
0x18000d521  jz      short loc_18000D542
0x18000d523  lea     r9, [r8+18h]
0x18000d527  cmp     dword ptr [r9], 0
0x18000d52b  jnz     short loc_18000D545
0x18000d52d  cmp     dword ptr [r9+4], 0
0x18000d532  jnz     short loc_18000D545
0x18000d534  cmp     dword ptr [r9+8], 0
0x18000d539  jnz     short loc_18000D545
0x18000d53b  cmp     dword ptr [r9+0Ch], 0
0x18000d540  jnz     short loc_18000D545
0x18000d542  xor     r9d, r9d
0x18000d545  lea     rax, [rsp+68h+arg_18]
0x18000d54d  add     r8, 8
0x18000d551  mov     [rsp+68h+var_30], rax
0x18000d556  lea     rdx, byte_1800376CD
0x18000d55d  lea     rax, [rsp+68h+var_28]
0x18000d562  mov     rcx, rdi
0x18000d565  mov     [rsp+68h+var_38], rax
0x18000d56a  lea     rax, [rsp+68h+SRWLock]
0x18000d56f  mov     [rsp+68h+var_40], rax
0x18000d574  lea     rax, [rsp+68h+var_20]
0x18000d579  mov     [rsp+68h+var_48], rax
0x18000d57e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000d583  cmp     dword ptr [rbx+138h], 0
0x18000d58a  jnz     short loc_18000D5C8
0x18000d58c  add     rbx, 120h
0x18000d593  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000d59b  jz      short loc_18000D5C1
0x18000d59d  mov     dl, 1
0x18000d59f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000d5a4  mov     [rbx], rax
0x18000d5a7  test    rax, rax
0x18000d5aa  jz      short loc_18000D5C8
0x18000d5ac  mov     rcx, [rax]
0x18000d5af  mov     [rbx+10h], rcx
0x18000d5b3  mov     [rax], rbx
0x18000d5b6  call    cs:__imp_GetCurrentThreadId
0x18000d5bc  mov     [rbx+18h], eax
0x18000d5bf  jmp     short loc_18000D5C8
0x18000d5c1  mov     qword ptr [rbx], 0
0x18000d5c8  mov     rbx, [rsp+68h+arg_8]
0x18000d5cd  add     rsp, 50h
0x18000d5d1  pop     rdi
0x18000d5d2  pop     rsi
0x18000d5d3  pop     rbp
0x18000d5d4  retn
```
