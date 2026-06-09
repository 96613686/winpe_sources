# PpfTraceLoggingProvider::PpfInitializeActivity::StartActivity(void)

- ea: `0x18001865c`
- end: `0x1800187be`
- name: `?StartActivity@PpfInitializeActivity@PpfTraceLoggingProvider@@QEAAXXZ`
- size: `354`
- prototype: `void __fastcall(PpfTraceLoggingProvider::PpfInitializeActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800107e8`

## callees

- `0x180001640`
- `0x180003270`
- `0x1800070e0`
- `0x18000de98`
- `0x18000e680`
- `0x18001865c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800186c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018784`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800186c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018784`

## pseudocode

```c
void __fastcall PpfTraceLoggingProvider::PpfInitializeActivity::StartActivity(
        PpfTraceLoggingProvider::PpfInitializeActivity *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // rcx
  const struct _tlgProvider_t *v4; // rdi
  __int64 v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  char *v8; // rbx
  _QWORD *Local; // rax
  DWORD CurrentThreadId; // [rsp+30h] [rbp-68h] BYREF
  __int64 v11; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v12[32]; // [rsp+40h] [rbp-58h] BYREF
  __int64 *v13; // [rsp+60h] [rbp-38h]
  __int64 v14; // [rsp+68h] [rbp-30h]
  DWORD *p_CurrentThreadId; // [rsp+70h] [rbp-28h]
  __int64 v16; // [rsp+78h] [rbp-20h]

  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = PpfTraceLoggingProvider::Provider();
  v4 = v2;
  if ( *(_DWORD *)v2 > 5u )
  {
    v5 = *((_QWORD *)v2 + 3);
    if ( (*((_QWORD *)v4 + 2) & 0x400000000000LL) != 0 )
    {
      v3 = v5 & 0x400000000000LL;
      if ( (v5 & 0x400000000000LL) == v5 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v11 = 0x1000000;
        v6 = *((_QWORD *)this + 34);
        if ( !*(_BYTE *)(v6 + 4)
          || (v7 = v6 + 24, !*(_DWORD *)(v6 + 24))
          && !*(_DWORD *)(v6 + 28)
          && !*(_DWORD *)(v6 + 32)
          && !*(_DWORD *)(v6 + 36) )
        {
          v7 = 0;
        }
        p_CurrentThreadId = &CurrentThreadId;
        v16 = 4;
        v13 = &v11;
        v14 = 8;
        tlgWriteTransfer_EventWriteTransfer(v4, word_180068A62, v6 + 8, v7, 4, v12);
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v8 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v3,
                          1);
      *(_QWORD *)v8 = Local;
      if ( Local )
      {
        *((_QWORD *)v8 + 2) = *Local;
        *Local = v8;
        *((_DWORD *)v8 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v8 = 0;
    }
  }
}

```

## disassembly

```asm
0x18001865c  mov     [rsp+arg_8], rbx
0x180018661  push    rdi
0x180018662  sub     rsp, 90h
0x180018669  mov     rax, cs:__security_cookie
0x180018670  xor     rax, rsp
0x180018673  mov     [rsp+98h+var_18], rax
0x18001867b  mov     rbx, rcx
0x18001867e  call    ?zInternalStart@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180018683  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x180018688  mov     rdi, rax
0x18001868b  mov     edx, [rax]
0x18001868d  cmp     edx, 5
0x180018690  jbe     loc_180018751
0x180018696  mov     rax, [rax+18h]
0x18001869a  mov     rdx, [rdi+10h]
0x18001869e  mov     r8, 400000000000h
0x1800186a8  test    r8, rdx
0x1800186ab  jz      loc_180018751
0x1800186b1  mov     rcx, rax
0x1800186b4  and     rcx, r8
0x1800186b7  cmp     rcx, rax
0x1800186ba  jnz     loc_180018751
0x1800186c0  call    cs:__imp_GetCurrentThreadId
0x1800186c7  nop     dword ptr [rax+rax+00h]
0x1800186cc  mov     [rsp+98h+var_68], eax
0x1800186d0  mov     [rsp+98h+var_60], 1000000h
0x1800186d9  mov     r8, [rbx+110h]
0x1800186e0  cmp     byte ptr [r8+4], 0
0x1800186e5  jz      short loc_180018706
0x1800186e7  lea     r9, [r8+18h]
0x1800186eb  cmp     dword ptr [r9], 0
0x1800186ef  jnz     short loc_180018709
0x1800186f1  cmp     dword ptr [r9+4], 0
0x1800186f6  jnz     short loc_180018709
0x1800186f8  cmp     dword ptr [r9+8], 0
0x1800186fd  jnz     short loc_180018709
0x1800186ff  cmp     dword ptr [r9+0Ch], 0
0x180018704  jnz     short loc_180018709
0x180018706  xor     r9d, r9d
0x180018709  lea     rax, [rsp+98h+var_68]
0x18001870e  mov     [rsp+98h+var_28], rax
0x180018713  mov     ecx, 4
0x180018718  mov     [rsp+98h+var_20], rcx
0x18001871d  lea     rax, [rsp+98h+var_60]
0x180018722  mov     [rsp+98h+var_38], rax
0x180018727  mov     [rsp+98h+var_30], 8
0x180018730  add     r8, 8
0x180018734  lea     rax, [rsp+98h+var_58]
0x180018739  mov     [rsp+98h+var_70], rax
0x18001873e  mov     [rsp+98h+var_78], ecx
0x180018742  lea     rdx, word_180068A62
0x180018749  mov     rcx, rdi
0x18001874c  call    _tlgWriteTransfer_EventWriteTransfer
0x180018751  cmp     dword ptr [rbx+138h], 0
0x180018758  jnz     short loc_18001879C
0x18001875a  add     rbx, 120h
0x180018761  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180018769  jz      short loc_180018795
0x18001876b  mov     dl, 1
0x18001876d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180018772  mov     [rbx], rax
0x180018775  test    rax, rax
0x180018778  jz      short loc_18001879C
0x18001877a  mov     rcx, [rax]
0x18001877d  mov     [rbx+10h], rcx
0x180018781  mov     [rax], rbx
0x180018784  call    cs:__imp_GetCurrentThreadId
0x18001878b  nop     dword ptr [rax+rax+00h]
0x180018790  mov     [rbx+18h], eax
0x180018793  jmp     short loc_18001879C
0x180018795  mov     qword ptr [rbx], 0
0x18001879c  mov     rcx, [rsp+98h+var_18]
0x1800187a4  xor     rcx, rsp; StackCookie
0x1800187a7  call    __security_check_cookie
0x1800187ac  mov     rbx, [rsp+98h+arg_8]
0x1800187b4  add     rsp, 90h
0x1800187bb  pop     rdi
0x1800187bc  retn
```
