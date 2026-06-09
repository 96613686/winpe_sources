# IsoBurnLoggingTelemetry::BurnImage::StartActivity(void)

- ea: `0x1400086e4`
- end: `0x140008885`
- name: `?StartActivity@BurnImage@IsoBurnLoggingTelemetry@@QEAAXXZ`
- size: `417`
- prototype: `void __fastcall(IsoBurnLoggingTelemetry::BurnImage *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140009e64`

## callees

- `0x1400018dc`
- `0x140001fa0`
- `0x140005714`
- `0x140006c34`
- `0x140007610`
- `0x1400086e4`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x14000874e`
- `ADVAPI32!EventActivityIdControl` at `0x14000874e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000876c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000876c`
- `KERNEL32!GetCurrentThreadId` at `0x1400087a5`
- `KERNEL32!GetCurrentThreadId` at `0x14000885a`
- `KERNEL32!GetCurrentThreadId` at `0x1400087a5`
- `KERNEL32!GetCurrentThreadId` at `0x14000885a`

## pseudocode

```c
void __fastcall IsoBurnLoggingTelemetry::BurnImage::StartActivity(IsoBurnLoggingTelemetry::BurnImage *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rax
  RTL_SRWLOCK *v4; // rcx
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  const struct _tlgProvider_t *v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // rax
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  char *v13; // rbx
  _QWORD *Local; // rax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-29h] BYREF
  __int64 v16; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v17[32]; // [rsp+40h] [rbp-19h] BYREF
  __int64 *v18; // [rsp+60h] [rbp+7h]
  __int64 v19; // [rsp+68h] [rbp+Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+17h]
  __int64 v21; // [rsp+78h] [rbp+1Fh]

  wil::ActivityBase<IsoBurnLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  v3 = IsoBurnLoggingProvider::Provider();
  if ( *(_DWORD *)v3 > 5u
    && (*((_QWORD *)v3 + 2) & 0x200000000000LL) != 0
    && (*((_QWORD *)v3 + 3) & 0x200000000000LL) == *((_QWORD *)v3 + 3) )
  {
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  }
  else
  {
    *(_OWORD *)(v2 + 8) = 0;
  }
  v4 = SRWLock;
  *(_DWORD *)v2 = 1;
  if ( v4 )
    ReleaseSRWLockExclusive(v4);
  v5 = IsoBurnLoggingProvider::Provider();
  v7 = v5;
  v8 = *(unsigned int *)v5;
  if ( (unsigned int)v8 > 5 )
  {
    v9 = *((_QWORD *)v5 + 3);
    v8 = *((_QWORD *)v7 + 2);
    if ( (v8 & 0x200000000000LL) != 0 )
    {
      v8 = v9 & 0x200000000000LL;
      if ( (v9 & 0x200000000000LL) == v9 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v16 = 0;
        if ( !*(_BYTE *)(v11 + 4)
          || (v12 = v11 + 24, !*(_DWORD *)(v11 + 24))
          && !*(_DWORD *)(v11 + 28)
          && !*(_DWORD *)(v11 + 32)
          && !*(_DWORD *)(v11 + 36) )
        {
          v12 = 0;
        }
        v19 = 8;
        v21 = 4;
        p_SRWLock = &SRWLock;
        v18 = &v16;
        tlgWriteTransfer_EventWriteTransfer(v7, byte_140013423, v11 + 8, v12, 4, v17);
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v13 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v6) = 1;
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v8,
                          v6);
      *(_QWORD *)v13 = Local;
      if ( Local )
      {
        *((_QWORD *)v13 + 2) = *Local;
        *Local = v13;
        *((_DWORD *)v13 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v13 = 0;
    }
  }
}

```

## disassembly

```asm
0x1400086e4  push    rbp
0x1400086e6  push    rbx
0x1400086e7  push    rdi
0x1400086e8  push    r14
0x1400086ea  lea     rbp, [rsp-3Fh]
0x1400086ef  sub     rsp, 98h
0x1400086f6  mov     rax, cs:__security_cookie
0x1400086fd  xor     rax, rsp
0x140008700  mov     [rbp+57h+var_30], rax
0x140008704  lea     rdx, [rbp+57h+SRWLock]
0x140008708  mov     rbx, rcx
0x14000870b  call    ?LockExclusive@?$ActivityBase@VIsoBurnLoggingProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<IsoBurnLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140008710  mov     rdi, [rbx+110h]
0x140008717  call    ?Provider@IsoBurnLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; IsoBurnLoggingProvider::Provider(void)
0x14000871c  mov     r14, 200000000000h
0x140008726  mov     edx, [rax]
0x140008728  cmp     edx, 5
0x14000872b  jbe     short loc_140008756
0x14000872d  mov     rcx, [rax+18h]
0x140008731  mov     rax, [rax+10h]
0x140008735  test    r14, rax
0x140008738  jz      short loc_140008756
0x14000873a  mov     rax, rcx
0x14000873d  and     rax, r14
0x140008740  cmp     rax, rcx
0x140008743  jnz     short loc_140008756
0x140008745  lea     rdx, [rdi+8]; ActivityId
0x140008749  mov     ecx, 3; ControlCode
0x14000874e  call    cs:__imp_EventActivityIdControl
0x140008754  jmp     short loc_14000875D
0x140008756  xorps   xmm0, xmm0
0x140008759  movups  xmmword ptr [rdi+8], xmm0
0x14000875d  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x140008761  mov     dword ptr [rdi], 1
0x140008767  test    rcx, rcx
0x14000876a  jz      short loc_140008772
0x14000876c  call    cs:__imp_ReleaseSRWLockExclusive
0x140008772  call    ?Provider@IsoBurnLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; IsoBurnLoggingProvider::Provider(void)
0x140008777  mov     rdi, rax
0x14000877a  mov     ecx, [rax]
0x14000877c  cmp     ecx, 5
0x14000877f  jbe     loc_140008827
0x140008785  mov     rax, [rax+18h]
0x140008789  mov     rcx, [rdi+10h]
0x14000878d  test    r14, rcx
0x140008790  jz      loc_140008827
0x140008796  mov     rcx, rax
0x140008799  and     rcx, r14
0x14000879c  cmp     rcx, rax
0x14000879f  jnz     loc_140008827
0x1400087a5  call    cs:__imp_GetCurrentThreadId
0x1400087ab  mov     r8, [rbx+110h]
0x1400087b2  mov     dword ptr [rbp+57h+SRWLock], eax
0x1400087b5  mov     [rbp+57h+var_78], 0
0x1400087bd  cmp     byte ptr [r8+4], 0
0x1400087c2  jz      short loc_1400087E3
0x1400087c4  lea     r9, [r8+18h]
0x1400087c8  cmp     dword ptr [r9], 0
0x1400087cc  jnz     short loc_1400087E6
0x1400087ce  cmp     dword ptr [r9+4], 0
0x1400087d3  jnz     short loc_1400087E6
0x1400087d5  cmp     dword ptr [r9+8], 0
0x1400087da  jnz     short loc_1400087E6
0x1400087dc  cmp     dword ptr [r9+0Ch], 0
0x1400087e1  jnz     short loc_1400087E6
0x1400087e3  xor     r9d, r9d
0x1400087e6  mov     ecx, 4
0x1400087eb  mov     [rbp+57h+var_48], 8
0x1400087f3  lea     rax, [rbp+57h+SRWLock]
0x1400087f7  mov     [rbp+57h+var_38], rcx
0x1400087fb  mov     [rbp+57h+var_40], rax
0x1400087ff  lea     rdx, byte_140013423
0x140008806  lea     rax, [rbp+57h+var_78]
0x14000880a  add     r8, 8
0x14000880e  mov     [rbp+57h+var_50], rax
0x140008812  lea     rax, [rbp+57h+var_70]
0x140008816  mov     [rsp+0B0h+var_88], rax
0x14000881b  mov     [rsp+0B0h+var_90], ecx
0x14000881f  mov     rcx, rdi
0x140008822  call    _tlgWriteTransfer_EventWriteTransfer
0x140008827  cmp     dword ptr [rbx+138h], 0
0x14000882e  jnz     short loc_14000886C
0x140008830  add     rbx, 120h
0x140008837  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000883f  jz      short loc_140008865
0x140008841  mov     dl, 1
0x140008843  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x140008848  mov     [rbx], rax
0x14000884b  test    rax, rax
0x14000884e  jz      short loc_14000886C
0x140008850  mov     rcx, [rax]
0x140008853  mov     [rbx+10h], rcx
0x140008857  mov     [rax], rbx
0x14000885a  call    cs:__imp_GetCurrentThreadId
0x140008860  mov     [rbx+18h], eax
0x140008863  jmp     short loc_14000886C
0x140008865  mov     qword ptr [rbx], 0
0x14000886c  mov     rcx, [rbp+57h+var_30]
0x140008870  xor     rcx, rsp; StackCookie
0x140008873  call    __security_check_cookie
0x140008878  add     rsp, 98h
0x14000887f  pop     r14
0x140008881  pop     rdi
0x140008882  pop     rbx
0x140008883  pop     rbp
0x140008884  retn
```
