# CflApiTraceProvider::CflDeserializeSessionContextActivity::StartActivity(ushort const *,ushort const *)

- ea: `0x18000cb1c`
- end: `0x18000cc75`
- name: `?StartActivity@CflDeserializeSessionContextActivity@CflApiTraceProvider@@QEAAXPEBG0@Z`
- size: `345`
- prototype: `void __fastcall(CflApiTraceProvider::CflDeserializeSessionContextActivity *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800102f0`
- `0x180010470`

## callees

- `0x180001bfc`
- `0x1800058b0`
- `0x18000a31c`
- `0x18000a4b8`
- `0x18000cb1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cb7b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cb7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cba2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cc56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cba2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cc56`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000cb5c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000cb5c`

## pseudocode

```c
void __fastcall CflApiTraceProvider::CflDeserializeSessionContextActivity::StartActivity(
        CflApiTraceProvider::CflDeserializeSessionContextActivity *this,
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
      (unsigned int)&unk_180036378,
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
0x18000cb1c  mov     [rsp+arg_8], rbx
0x18000cb21  push    rbp
0x18000cb22  push    rsi
0x18000cb23  push    rdi
0x18000cb24  sub     rsp, 50h
0x18000cb28  mov     rbp, rdx
0x18000cb2b  mov     rsi, r8
0x18000cb2e  lea     rdx, [rsp+68h+SRWLock]
0x18000cb33  mov     rbx, rcx
0x18000cb36  call    ?LockExclusive@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000cb3b  mov     rdi, [rbx+110h]
0x18000cb42  call    ?Instance@CflApiTraceProvider@@KAPEAV1@XZ; CflApiTraceProvider::Instance(void)
0x18000cb47  mov     r9, [rax+8]
0x18000cb4b  mov     eax, [r9]
0x18000cb4e  cmp     eax, 5
0x18000cb51  jbe     short loc_18000CB64
0x18000cb53  lea     rdx, [rdi+8]; ActivityId
0x18000cb57  mov     ecx, 3; ControlCode
0x18000cb5c  call    cs:__imp_EventActivityIdControl
0x18000cb62  jmp     short loc_18000CB6B
0x18000cb64  xorps   xmm0, xmm0
0x18000cb67  movups  xmmword ptr [rdi+8], xmm0
0x18000cb6b  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x18000cb70  mov     dword ptr [rdi], 1
0x18000cb76  test    rcx, rcx
0x18000cb79  jz      short loc_18000CB81
0x18000cb7b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cb81  call    ?Instance@CflApiTraceProvider@@KAPEAV1@XZ; CflApiTraceProvider::Instance(void)
0x18000cb86  mov     rdi, [rax+8]
0x18000cb8a  mov     eax, [rdi]
0x18000cb8c  cmp     eax, 5
0x18000cb8f  jbe     loc_18000CC23
0x18000cb95  mov     [rsp+68h+arg_18], rsi
0x18000cb9d  mov     [rsp+68h+var_28], rbp
0x18000cba2  call    cs:__imp_GetCurrentThreadId
0x18000cba8  mov     r8, [rbx+110h]
0x18000cbaf  mov     dword ptr [rsp+68h+SRWLock], eax
0x18000cbb3  mov     [rsp+68h+var_20], 0
0x18000cbbc  cmp     byte ptr [r8+4], 0
0x18000cbc1  jz      short loc_18000CBE2
0x18000cbc3  lea     r9, [r8+18h]
0x18000cbc7  cmp     dword ptr [r9], 0
0x18000cbcb  jnz     short loc_18000CBE5
0x18000cbcd  cmp     dword ptr [r9+4], 0
0x18000cbd2  jnz     short loc_18000CBE5
0x18000cbd4  cmp     dword ptr [r9+8], 0
0x18000cbd9  jnz     short loc_18000CBE5
0x18000cbdb  cmp     dword ptr [r9+0Ch], 0
0x18000cbe0  jnz     short loc_18000CBE5
0x18000cbe2  xor     r9d, r9d
0x18000cbe5  lea     rax, [rsp+68h+arg_18]
0x18000cbed  add     r8, 8
0x18000cbf1  mov     [rsp+68h+var_30], rax
0x18000cbf6  lea     rdx, unk_180036378
0x18000cbfd  lea     rax, [rsp+68h+var_28]
0x18000cc02  mov     rcx, rdi
0x18000cc05  mov     [rsp+68h+var_38], rax
0x18000cc0a  lea     rax, [rsp+68h+SRWLock]
0x18000cc0f  mov     [rsp+68h+var_40], rax
0x18000cc14  lea     rax, [rsp+68h+var_20]
0x18000cc19  mov     [rsp+68h+var_48], rax
0x18000cc1e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000cc23  cmp     dword ptr [rbx+138h], 0
0x18000cc2a  jnz     short loc_18000CC68
0x18000cc2c  add     rbx, 120h
0x18000cc33  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000cc3b  jz      short loc_18000CC61
0x18000cc3d  mov     dl, 1
0x18000cc3f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000cc44  mov     [rbx], rax
0x18000cc47  test    rax, rax
0x18000cc4a  jz      short loc_18000CC68
0x18000cc4c  mov     rcx, [rax]
0x18000cc4f  mov     [rbx+10h], rcx
0x18000cc53  mov     [rax], rbx
0x18000cc56  call    cs:__imp_GetCurrentThreadId
0x18000cc5c  mov     [rbx+18h], eax
0x18000cc5f  jmp     short loc_18000CC68
0x18000cc61  mov     qword ptr [rbx], 0
0x18000cc68  mov     rbx, [rsp+68h+arg_8]
0x18000cc6d  add     rsp, 50h
0x18000cc71  pop     rdi
0x18000cc72  pop     rsi
0x18000cc73  pop     rbp
0x18000cc74  retn
```
