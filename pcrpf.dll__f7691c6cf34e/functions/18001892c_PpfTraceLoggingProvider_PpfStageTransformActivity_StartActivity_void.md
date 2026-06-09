# PpfTraceLoggingProvider::PpfStageTransformActivity::StartActivity(void)

- ea: `0x18001892c`
- end: `0x180018a8e`
- name: `?StartActivity@PpfStageTransformActivity@PpfTraceLoggingProvider@@QEAAXXZ`
- size: `354`
- prototype: `void __fastcall(PpfTraceLoggingProvider::PpfStageTransformActivity *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18001bab0`
- `0x18001bb90`

## callees

- `0x180001640`
- `0x180003270`
- `0x1800070e0`
- `0x18000de98`
- `0x18000e680`
- `0x18001892c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018990`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018a54`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018990`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018a54`

## pseudocode

```c
void __fastcall PpfTraceLoggingProvider::PpfStageTransformActivity::StartActivity(
        PpfTraceLoggingProvider::PpfStageTransformActivity *this)
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
        tlgWriteTransfer_EventWriteTransfer(v4, byte_180068713, v6 + 8, v7, 4, v12);
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
0x18001892c  mov     [rsp+arg_8], rbx
0x180018931  push    rdi
0x180018932  sub     rsp, 90h
0x180018939  mov     rax, cs:__security_cookie
0x180018940  xor     rax, rsp
0x180018943  mov     [rsp+98h+var_18], rax
0x18001894b  mov     rbx, rcx
0x18001894e  call    ?zInternalStart@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180018953  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x180018958  mov     rdi, rax
0x18001895b  mov     edx, [rax]
0x18001895d  cmp     edx, 5
0x180018960  jbe     loc_180018A21
0x180018966  mov     rax, [rax+18h]
0x18001896a  mov     rdx, [rdi+10h]
0x18001896e  mov     r8, 400000000000h
0x180018978  test    r8, rdx
0x18001897b  jz      loc_180018A21
0x180018981  mov     rcx, rax
0x180018984  and     rcx, r8
0x180018987  cmp     rcx, rax
0x18001898a  jnz     loc_180018A21
0x180018990  call    cs:__imp_GetCurrentThreadId
0x180018997  nop     dword ptr [rax+rax+00h]
0x18001899c  mov     [rsp+98h+var_68], eax
0x1800189a0  mov     [rsp+98h+var_60], 1000000h
0x1800189a9  mov     r8, [rbx+110h]
0x1800189b0  cmp     byte ptr [r8+4], 0
0x1800189b5  jz      short loc_1800189D6
0x1800189b7  lea     r9, [r8+18h]
0x1800189bb  cmp     dword ptr [r9], 0
0x1800189bf  jnz     short loc_1800189D9
0x1800189c1  cmp     dword ptr [r9+4], 0
0x1800189c6  jnz     short loc_1800189D9
0x1800189c8  cmp     dword ptr [r9+8], 0
0x1800189cd  jnz     short loc_1800189D9
0x1800189cf  cmp     dword ptr [r9+0Ch], 0
0x1800189d4  jnz     short loc_1800189D9
0x1800189d6  xor     r9d, r9d
0x1800189d9  lea     rax, [rsp+98h+var_68]
0x1800189de  mov     [rsp+98h+var_28], rax
0x1800189e3  mov     ecx, 4
0x1800189e8  mov     [rsp+98h+var_20], rcx
0x1800189ed  lea     rax, [rsp+98h+var_60]
0x1800189f2  mov     [rsp+98h+var_38], rax
0x1800189f7  mov     [rsp+98h+var_30], 8
0x180018a00  add     r8, 8
0x180018a04  lea     rax, [rsp+98h+var_58]
0x180018a09  mov     [rsp+98h+var_70], rax
0x180018a0e  mov     [rsp+98h+var_78], ecx
0x180018a12  lea     rdx, byte_180068713
0x180018a19  mov     rcx, rdi
0x180018a1c  call    _tlgWriteTransfer_EventWriteTransfer
0x180018a21  cmp     dword ptr [rbx+138h], 0
0x180018a28  jnz     short loc_180018A6C
0x180018a2a  add     rbx, 120h
0x180018a31  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180018a39  jz      short loc_180018A65
0x180018a3b  mov     dl, 1
0x180018a3d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180018a42  mov     [rbx], rax
0x180018a45  test    rax, rax
0x180018a48  jz      short loc_180018A6C
0x180018a4a  mov     rcx, [rax]
0x180018a4d  mov     [rbx+10h], rcx
0x180018a51  mov     [rax], rbx
0x180018a54  call    cs:__imp_GetCurrentThreadId
0x180018a5b  nop     dword ptr [rax+rax+00h]
0x180018a60  mov     [rbx+18h], eax
0x180018a63  jmp     short loc_180018A6C
0x180018a65  mov     qword ptr [rbx], 0
0x180018a6c  mov     rcx, [rsp+98h+var_18]
0x180018a74  xor     rcx, rsp; StackCookie
0x180018a77  call    __security_check_cookie
0x180018a7c  mov     rbx, [rsp+98h+arg_8]
0x180018a84  add     rsp, 90h
0x180018a8b  pop     rdi
0x180018a8c  retn
```
