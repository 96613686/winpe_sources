# PpfTraceLoggingProvider::CleanupBitLockerReducedPcrProfileActivity::StartActivity(void)

- ea: `0x180053970`
- end: `0x180053ad2`
- name: `?StartActivity@CleanupBitLockerReducedPcrProfileActivity@PpfTraceLoggingProvider@@QEAAXXZ`
- size: `354`
- prototype: `void __fastcall(PpfTraceLoggingProvider::CleanupBitLockerReducedPcrProfileActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180052728`

## callees

- `0x180001640`
- `0x180003270`
- `0x1800070e0`
- `0x18000de98`
- `0x18000e680`
- `0x180053970`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800539d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053a98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800539d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053a98`

## pseudocode

```c
void __fastcall PpfTraceLoggingProvider::CleanupBitLockerReducedPcrProfileActivity::StartActivity(
        PpfTraceLoggingProvider::CleanupBitLockerReducedPcrProfileActivity *this)
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
        tlgWriteTransfer_EventWriteTransfer(v4, &byte_180069E6F, v6 + 8, v7, 4, v12);
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
0x180053970  mov     [rsp+arg_8], rbx
0x180053975  push    rdi
0x180053976  sub     rsp, 90h
0x18005397d  mov     rax, cs:__security_cookie
0x180053984  xor     rax, rsp
0x180053987  mov     [rsp+98h+var_18], rax
0x18005398f  mov     rbx, rcx
0x180053992  call    ?zInternalStart@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180053997  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x18005399c  mov     rdi, rax
0x18005399f  mov     edx, [rax]
0x1800539a1  cmp     edx, 5
0x1800539a4  jbe     loc_180053A65
0x1800539aa  mov     rax, [rax+18h]
0x1800539ae  mov     rdx, [rdi+10h]
0x1800539b2  mov     r8, 400000000000h
0x1800539bc  test    r8, rdx
0x1800539bf  jz      loc_180053A65
0x1800539c5  mov     rcx, rax
0x1800539c8  and     rcx, r8
0x1800539cb  cmp     rcx, rax
0x1800539ce  jnz     loc_180053A65
0x1800539d4  call    cs:__imp_GetCurrentThreadId
0x1800539db  nop     dword ptr [rax+rax+00h]
0x1800539e0  mov     [rsp+98h+var_68], eax
0x1800539e4  mov     [rsp+98h+var_60], 1000000h
0x1800539ed  mov     r8, [rbx+110h]
0x1800539f4  cmp     byte ptr [r8+4], 0
0x1800539f9  jz      short loc_180053A1A
0x1800539fb  lea     r9, [r8+18h]
0x1800539ff  cmp     dword ptr [r9], 0
0x180053a03  jnz     short loc_180053A1D
0x180053a05  cmp     dword ptr [r9+4], 0
0x180053a0a  jnz     short loc_180053A1D
0x180053a0c  cmp     dword ptr [r9+8], 0
0x180053a11  jnz     short loc_180053A1D
0x180053a13  cmp     dword ptr [r9+0Ch], 0
0x180053a18  jnz     short loc_180053A1D
0x180053a1a  xor     r9d, r9d
0x180053a1d  lea     rax, [rsp+98h+var_68]
0x180053a22  mov     [rsp+98h+var_28], rax
0x180053a27  mov     ecx, 4
0x180053a2c  mov     [rsp+98h+var_20], rcx
0x180053a31  lea     rax, [rsp+98h+var_60]
0x180053a36  mov     [rsp+98h+var_38], rax
0x180053a3b  mov     [rsp+98h+var_30], 8
0x180053a44  add     r8, 8
0x180053a48  lea     rax, [rsp+98h+var_58]
0x180053a4d  mov     [rsp+98h+var_70], rax
0x180053a52  mov     [rsp+98h+var_78], ecx
0x180053a56  lea     rdx, byte_180069E6F
0x180053a5d  mov     rcx, rdi
0x180053a60  call    _tlgWriteTransfer_EventWriteTransfer
0x180053a65  cmp     dword ptr [rbx+138h], 0
0x180053a6c  jnz     short loc_180053AB0
0x180053a6e  add     rbx, 120h
0x180053a75  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180053a7d  jz      short loc_180053AA9
0x180053a7f  mov     dl, 1
0x180053a81  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180053a86  mov     [rbx], rax
0x180053a89  test    rax, rax
0x180053a8c  jz      short loc_180053AB0
0x180053a8e  mov     rcx, [rax]
0x180053a91  mov     [rbx+10h], rcx
0x180053a95  mov     [rax], rbx
0x180053a98  call    cs:__imp_GetCurrentThreadId
0x180053a9f  nop     dword ptr [rax+rax+00h]
0x180053aa4  mov     [rbx+18h], eax
0x180053aa7  jmp     short loc_180053AB0
0x180053aa9  mov     qword ptr [rbx], 0
0x180053ab0  mov     rcx, [rsp+98h+var_18]
0x180053ab8  xor     rcx, rsp; StackCookie
0x180053abb  call    __security_check_cookie
0x180053ac0  mov     rbx, [rsp+98h+arg_8]
0x180053ac8  add     rsp, 90h
0x180053acf  pop     rdi
0x180053ad0  retn
```
