# PpfTraceLoggingProvider::PpfGetPredictionsIntActivity::StartActivity(void)

- ea: `0x1800184f4`
- end: `0x180018656`
- name: `?StartActivity@PpfGetPredictionsIntActivity@PpfTraceLoggingProvider@@QEAAXXZ`
- size: `354`
- prototype: `void __fastcall(PpfTraceLoggingProvider::PpfGetPredictionsIntActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800141f4`

## callees

- `0x180001640`
- `0x180003270`
- `0x1800070e0`
- `0x18000de98`
- `0x18000e680`
- `0x1800184f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018558`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001861c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018558`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001861c`

## pseudocode

```c
void __fastcall PpfTraceLoggingProvider::PpfGetPredictionsIntActivity::StartActivity(
        PpfTraceLoggingProvider::PpfGetPredictionsIntActivity *this)
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
        tlgWriteTransfer_EventWriteTransfer(v4, word_18006967A, v6 + 8, v7, 4, v12);
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
0x1800184f4  mov     [rsp+arg_8], rbx
0x1800184f9  push    rdi
0x1800184fa  sub     rsp, 90h
0x180018501  mov     rax, cs:__security_cookie
0x180018508  xor     rax, rsp
0x18001850b  mov     [rsp+98h+var_18], rax
0x180018513  mov     rbx, rcx
0x180018516  call    ?zInternalStart@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001851b  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x180018520  mov     rdi, rax
0x180018523  mov     edx, [rax]
0x180018525  cmp     edx, 5
0x180018528  jbe     loc_1800185E9
0x18001852e  mov     rax, [rax+18h]
0x180018532  mov     rdx, [rdi+10h]
0x180018536  mov     r8, 400000000000h
0x180018540  test    r8, rdx
0x180018543  jz      loc_1800185E9
0x180018549  mov     rcx, rax
0x18001854c  and     rcx, r8
0x18001854f  cmp     rcx, rax
0x180018552  jnz     loc_1800185E9
0x180018558  call    cs:__imp_GetCurrentThreadId
0x18001855f  nop     dword ptr [rax+rax+00h]
0x180018564  mov     [rsp+98h+var_68], eax
0x180018568  mov     [rsp+98h+var_60], 1000000h
0x180018571  mov     r8, [rbx+110h]
0x180018578  cmp     byte ptr [r8+4], 0
0x18001857d  jz      short loc_18001859E
0x18001857f  lea     r9, [r8+18h]
0x180018583  cmp     dword ptr [r9], 0
0x180018587  jnz     short loc_1800185A1
0x180018589  cmp     dword ptr [r9+4], 0
0x18001858e  jnz     short loc_1800185A1
0x180018590  cmp     dword ptr [r9+8], 0
0x180018595  jnz     short loc_1800185A1
0x180018597  cmp     dword ptr [r9+0Ch], 0
0x18001859c  jnz     short loc_1800185A1
0x18001859e  xor     r9d, r9d
0x1800185a1  lea     rax, [rsp+98h+var_68]
0x1800185a6  mov     [rsp+98h+var_28], rax
0x1800185ab  mov     ecx, 4
0x1800185b0  mov     [rsp+98h+var_20], rcx
0x1800185b5  lea     rax, [rsp+98h+var_60]
0x1800185ba  mov     [rsp+98h+var_38], rax
0x1800185bf  mov     [rsp+98h+var_30], 8
0x1800185c8  add     r8, 8
0x1800185cc  lea     rax, [rsp+98h+var_58]
0x1800185d1  mov     [rsp+98h+var_70], rax
0x1800185d6  mov     [rsp+98h+var_78], ecx
0x1800185da  lea     rdx, word_18006967A
0x1800185e1  mov     rcx, rdi
0x1800185e4  call    _tlgWriteTransfer_EventWriteTransfer
0x1800185e9  cmp     dword ptr [rbx+138h], 0
0x1800185f0  jnz     short loc_180018634
0x1800185f2  add     rbx, 120h
0x1800185f9  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180018601  jz      short loc_18001862D
0x180018603  mov     dl, 1
0x180018605  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001860a  mov     [rbx], rax
0x18001860d  test    rax, rax
0x180018610  jz      short loc_180018634
0x180018612  mov     rcx, [rax]
0x180018615  mov     [rbx+10h], rcx
0x180018619  mov     [rax], rbx
0x18001861c  call    cs:__imp_GetCurrentThreadId
0x180018623  nop     dword ptr [rax+rax+00h]
0x180018628  mov     [rbx+18h], eax
0x18001862b  jmp     short loc_180018634
0x18001862d  mov     qword ptr [rbx], 0
0x180018634  mov     rcx, [rsp+98h+var_18]
0x18001863c  xor     rcx, rsp; StackCookie
0x18001863f  call    __security_check_cookie
0x180018644  mov     rbx, [rsp+98h+arg_8]
0x18001864c  add     rsp, 90h
0x180018653  pop     rdi
0x180018654  retn
```
