# EduPrintProvTelemetry::EduPrintProvActivity::StartActivity(void)

- ea: `0x140012754`
- end: `0x1400128f5`
- name: `?StartActivity@EduPrintProvActivity@EduPrintProvTelemetry@@QEAAXXZ`
- size: `417`
- prototype: `void __fastcall(EduPrintProvTelemetry::EduPrintProvActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140011bb0`

## callees

- `0x1400016dc`
- `0x140002600`
- `0x140007440`
- `0x14000cfac`
- `0x140012014`
- `0x140012754`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400127dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400127dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140012815`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400128ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140012815`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400128ca`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1400127be`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1400127be`

## pseudocode

```c
void __fastcall EduPrintProvTelemetry::EduPrintProvActivity::StartActivity(
        EduPrintProvTelemetry::EduPrintProvActivity *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rax
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // rdx
  const struct _tlgProvider_t *v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  char *v11; // rbx
  _QWORD *Local; // rax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-29h] BYREF
  __int64 v14; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v15[32]; // [rsp+40h] [rbp-19h] BYREF
  __int64 *v16; // [rsp+60h] [rbp+7h]
  __int64 v17; // [rsp+68h] [rbp+Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+17h]
  __int64 v19; // [rsp+78h] [rbp+1Fh]

  wil::ActivityBase<EduPrintProvLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  v3 = EduPrintProvLogging::Provider();
  if ( *(_DWORD *)v3 > 5u
    && (*((_QWORD *)v3 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v3 + 3) & 0x400000000000LL) == *((_QWORD *)v3 + 3) )
  {
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  }
  else
  {
    *(_OWORD *)(v2 + 8) = 0;
  }
  *(_DWORD *)v2 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v4 = EduPrintProvLogging::Provider();
  v6 = v4;
  v7 = *(unsigned int *)v4;
  if ( (unsigned int)v7 > 5 )
  {
    v8 = *((_QWORD *)v4 + 3);
    v7 = *((_QWORD *)v6 + 2);
    if ( (v7 & 0x400000000000LL) != 0 )
    {
      v7 = v8 & 0x400000000000LL;
      if ( (v8 & 0x400000000000LL) == v8 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v14 = 0;
        v9 = *((_QWORD *)this + 34);
        if ( !*(_BYTE *)(v9 + 4)
          || (v10 = v9 + 24, !*(_DWORD *)(v9 + 24))
          && !*(_DWORD *)(v9 + 28)
          && !*(_DWORD *)(v9 + 32)
          && !*(_DWORD *)(v9 + 36) )
        {
          v10 = 0;
        }
        p_SRWLock = &SRWLock;
        v19 = 4;
        v16 = &v14;
        v17 = 8;
        tlgWriteTransfer_EventWriteTransfer(v6, byte_140017E15, v9 + 8, v10, 4, v15);
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v11 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v5) = 1;
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v7,
                          v5);
      *(_QWORD *)v11 = Local;
      if ( Local )
      {
        *((_QWORD *)v11 + 2) = *Local;
        *Local = v11;
        *((_DWORD *)v11 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v11 = 0;
    }
  }
}

```

## disassembly

```asm
0x140012754  push    rbp
0x140012756  push    rbx
0x140012757  push    rdi
0x140012758  push    r14
0x14001275a  lea     rbp, [rsp-3Fh]
0x14001275f  sub     rsp, 98h
0x140012766  mov     rax, cs:__security_cookie
0x14001276d  xor     rax, rsp
0x140012770  mov     [rbp+57h+var_30], rax
0x140012774  mov     rbx, rcx
0x140012777  lea     rdx, [rbp+57h+SRWLock]
0x14001277b  call    ?LockExclusive@?$ActivityBase@VEduPrintProvLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<EduPrintProvLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140012780  mov     rdi, [rbx+110h]
0x140012787  call    ?Provider@EduPrintProvLogging@@SAPEBU_tlgProvider_t@@XZ; EduPrintProvLogging::Provider(void)
0x14001278c  mov     edx, [rax]
0x14001278e  mov     r14, 400000000000h
0x140012798  cmp     edx, 5
0x14001279b  jbe     short loc_1400127C6
0x14001279d  mov     rcx, [rax+18h]
0x1400127a1  mov     rax, [rax+10h]
0x1400127a5  test    r14, rax
0x1400127a8  jz      short loc_1400127C6
0x1400127aa  mov     rax, rcx
0x1400127ad  and     rax, r14
0x1400127b0  cmp     rax, rcx
0x1400127b3  jnz     short loc_1400127C6
0x1400127b5  lea     rdx, [rdi+8]; ActivityId
0x1400127b9  mov     ecx, 3; ControlCode
0x1400127be  call    cs:__imp_EventActivityIdControl
0x1400127c4  jmp     short loc_1400127CD
0x1400127c6  xorps   xmm0, xmm0
0x1400127c9  movups  xmmword ptr [rdi+8], xmm0
0x1400127cd  mov     dword ptr [rdi], 1
0x1400127d3  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1400127d7  test    rcx, rcx
0x1400127da  jz      short loc_1400127E2
0x1400127dc  call    cs:__imp_ReleaseSRWLockExclusive
0x1400127e2  call    ?Provider@EduPrintProvLogging@@SAPEBU_tlgProvider_t@@XZ; EduPrintProvLogging::Provider(void)
0x1400127e7  mov     rdi, rax
0x1400127ea  mov     ecx, [rax]
0x1400127ec  cmp     ecx, 5
0x1400127ef  jbe     loc_140012897
0x1400127f5  mov     rax, [rax+18h]
0x1400127f9  mov     rcx, [rdi+10h]
0x1400127fd  test    r14, rcx
0x140012800  jz      loc_140012897
0x140012806  mov     rcx, rax
0x140012809  and     rcx, r14
0x14001280c  cmp     rcx, rax
0x14001280f  jnz     loc_140012897
0x140012815  call    cs:__imp_GetCurrentThreadId
0x14001281b  mov     dword ptr [rbp+57h+SRWLock], eax
0x14001281e  mov     [rbp+57h+var_78], 0
0x140012826  mov     r8, [rbx+110h]
0x14001282d  cmp     byte ptr [r8+4], 0
0x140012832  jz      short loc_140012853
0x140012834  lea     r9, [r8+18h]
0x140012838  cmp     dword ptr [r9], 0
0x14001283c  jnz     short loc_140012856
0x14001283e  cmp     dword ptr [r9+4], 0
0x140012843  jnz     short loc_140012856
0x140012845  cmp     dword ptr [r9+8], 0
0x14001284a  jnz     short loc_140012856
0x14001284c  cmp     dword ptr [r9+0Ch], 0
0x140012851  jnz     short loc_140012856
0x140012853  xor     r9d, r9d
0x140012856  lea     rax, [rbp+57h+SRWLock]
0x14001285a  mov     [rbp+57h+var_40], rax
0x14001285e  mov     ecx, 4
0x140012863  mov     [rbp+57h+var_38], rcx
0x140012867  lea     rax, [rbp+57h+var_78]
0x14001286b  mov     [rbp+57h+var_50], rax
0x14001286f  mov     [rbp+57h+var_48], 8
0x140012877  add     r8, 8
0x14001287b  lea     rax, [rbp+57h+var_70]
0x14001287f  mov     [rsp+0B0h+var_88], rax
0x140012884  mov     [rsp+0B0h+var_90], ecx
0x140012888  lea     rdx, byte_140017E15
0x14001288f  mov     rcx, rdi
0x140012892  call    _tlgWriteTransfer_EventWriteTransfer
0x140012897  cmp     dword ptr [rbx+138h], 0
0x14001289e  jnz     short loc_1400128DC
0x1400128a0  add     rbx, 120h
0x1400128a7  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400128af  jz      short loc_1400128D5
0x1400128b1  mov     dl, 1
0x1400128b3  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1400128b8  mov     [rbx], rax
0x1400128bb  test    rax, rax
0x1400128be  jz      short loc_1400128DC
0x1400128c0  mov     rcx, [rax]
0x1400128c3  mov     [rbx+10h], rcx
0x1400128c7  mov     [rax], rbx
0x1400128ca  call    cs:__imp_GetCurrentThreadId
0x1400128d0  mov     [rbx+18h], eax
0x1400128d3  jmp     short loc_1400128DC
0x1400128d5  mov     qword ptr [rbx], 0
0x1400128dc  mov     rcx, [rbp+57h+var_30]
0x1400128e0  xor     rcx, rsp; StackCookie
0x1400128e3  call    __security_check_cookie
0x1400128e8  add     rsp, 98h
0x1400128ef  pop     r14
0x1400128f1  pop     rdi
0x1400128f2  pop     rbx
0x1400128f3  pop     rbp
0x1400128f4  retn
```
