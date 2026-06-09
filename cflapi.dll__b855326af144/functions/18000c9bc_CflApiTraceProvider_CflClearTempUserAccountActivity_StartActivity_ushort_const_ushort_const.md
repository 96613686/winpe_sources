# CflApiTraceProvider::CflClearTempUserAccountActivity::StartActivity(ushort const *,ushort const *)

- ea: `0x18000c9bc`
- end: `0x18000cb15`
- name: `?StartActivity@CflClearTempUserAccountActivity@CflApiTraceProvider@@QEAAXPEBG0@Z`
- size: `345`
- prototype: `void __fastcall(CflApiTraceProvider::CflClearTempUserAccountActivity *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800101c0`

## callees

- `0x180001bfc`
- `0x1800058b0`
- `0x18000a31c`
- `0x18000a4b8`
- `0x18000c9bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ca1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ca1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ca42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000caf6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ca42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000caf6`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000c9fc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000c9fc`

## pseudocode

```c
void __fastcall CflApiTraceProvider::CflClearTempUserAccountActivity::StartActivity(
        CflApiTraceProvider::CflClearTempUserAccountActivity *this,
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
      (unsigned int)&dword_1800374A4,
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
0x18000c9bc  mov     [rsp+arg_8], rbx
0x18000c9c1  push    rbp
0x18000c9c2  push    rsi
0x18000c9c3  push    rdi
0x18000c9c4  sub     rsp, 50h
0x18000c9c8  mov     rbp, rdx
0x18000c9cb  mov     rsi, r8
0x18000c9ce  lea     rdx, [rsp+68h+SRWLock]
0x18000c9d3  mov     rbx, rcx
0x18000c9d6  call    ?LockExclusive@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000c9db  mov     rdi, [rbx+110h]
0x18000c9e2  call    ?Instance@CflApiTraceProvider@@KAPEAV1@XZ; CflApiTraceProvider::Instance(void)
0x18000c9e7  mov     r9, [rax+8]
0x18000c9eb  mov     eax, [r9]
0x18000c9ee  cmp     eax, 5
0x18000c9f1  jbe     short loc_18000CA04
0x18000c9f3  lea     rdx, [rdi+8]; ActivityId
0x18000c9f7  mov     ecx, 3; ControlCode
0x18000c9fc  call    cs:__imp_EventActivityIdControl
0x18000ca02  jmp     short loc_18000CA0B
0x18000ca04  xorps   xmm0, xmm0
0x18000ca07  movups  xmmword ptr [rdi+8], xmm0
0x18000ca0b  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x18000ca10  mov     dword ptr [rdi], 1
0x18000ca16  test    rcx, rcx
0x18000ca19  jz      short loc_18000CA21
0x18000ca1b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ca21  call    ?Instance@CflApiTraceProvider@@KAPEAV1@XZ; CflApiTraceProvider::Instance(void)
0x18000ca26  mov     rdi, [rax+8]
0x18000ca2a  mov     eax, [rdi]
0x18000ca2c  cmp     eax, 5
0x18000ca2f  jbe     loc_18000CAC3
0x18000ca35  mov     [rsp+68h+arg_18], rsi
0x18000ca3d  mov     [rsp+68h+var_28], rbp
0x18000ca42  call    cs:__imp_GetCurrentThreadId
0x18000ca48  mov     r8, [rbx+110h]
0x18000ca4f  mov     dword ptr [rsp+68h+SRWLock], eax
0x18000ca53  mov     [rsp+68h+var_20], 0
0x18000ca5c  cmp     byte ptr [r8+4], 0
0x18000ca61  jz      short loc_18000CA82
0x18000ca63  lea     r9, [r8+18h]
0x18000ca67  cmp     dword ptr [r9], 0
0x18000ca6b  jnz     short loc_18000CA85
0x18000ca6d  cmp     dword ptr [r9+4], 0
0x18000ca72  jnz     short loc_18000CA85
0x18000ca74  cmp     dword ptr [r9+8], 0
0x18000ca79  jnz     short loc_18000CA85
0x18000ca7b  cmp     dword ptr [r9+0Ch], 0
0x18000ca80  jnz     short loc_18000CA85
0x18000ca82  xor     r9d, r9d
0x18000ca85  lea     rax, [rsp+68h+arg_18]
0x18000ca8d  add     r8, 8
0x18000ca91  mov     [rsp+68h+var_30], rax
0x18000ca96  lea     rdx, dword_1800374A4
0x18000ca9d  lea     rax, [rsp+68h+var_28]
0x18000caa2  mov     rcx, rdi
0x18000caa5  mov     [rsp+68h+var_38], rax
0x18000caaa  lea     rax, [rsp+68h+SRWLock]
0x18000caaf  mov     [rsp+68h+var_40], rax
0x18000cab4  lea     rax, [rsp+68h+var_20]
0x18000cab9  mov     [rsp+68h+var_48], rax
0x18000cabe  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000cac3  cmp     dword ptr [rbx+138h], 0
0x18000caca  jnz     short loc_18000CB08
0x18000cacc  add     rbx, 120h
0x18000cad3  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000cadb  jz      short loc_18000CB01
0x18000cadd  mov     dl, 1
0x18000cadf  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000cae4  mov     [rbx], rax
0x18000cae7  test    rax, rax
0x18000caea  jz      short loc_18000CB08
0x18000caec  mov     rcx, [rax]
0x18000caef  mov     [rbx+10h], rcx
0x18000caf3  mov     [rax], rbx
0x18000caf6  call    cs:__imp_GetCurrentThreadId
0x18000cafc  mov     [rbx+18h], eax
0x18000caff  jmp     short loc_18000CB08
0x18000cb01  mov     qword ptr [rbx], 0
0x18000cb08  mov     rbx, [rsp+68h+arg_8]
0x18000cb0d  add     rsp, 50h
0x18000cb11  pop     rdi
0x18000cb12  pop     rsi
0x18000cb13  pop     rbp
0x18000cb14  retn
```
