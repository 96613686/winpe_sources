# PpfTraceLoggingProvider::PpfGenerateFinalPcrValuesForPpfEventLogActivity::StartActivity(void)

- ea: `0x18001838c`
- end: `0x1800184ee`
- name: `?StartActivity@PpfGenerateFinalPcrValuesForPpfEventLogActivity@PpfTraceLoggingProvider@@QEAAXXZ`
- size: `354`
- prototype: `void __fastcall(PpfTraceLoggingProvider::PpfGenerateFinalPcrValuesForPpfEventLogActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001b440`

## callees

- `0x180001640`
- `0x180003270`
- `0x1800070e0`
- `0x18000de98`
- `0x18000e680`
- `0x18001838c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800183f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800184b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800183f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800184b4`

## pseudocode

```c
void __fastcall PpfTraceLoggingProvider::PpfGenerateFinalPcrValuesForPpfEventLogActivity::StartActivity(
        PpfTraceLoggingProvider::PpfGenerateFinalPcrValuesForPpfEventLogActivity *this)
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
        tlgWriteTransfer_EventWriteTransfer(v4, &dword_1800686AC, v6 + 8, v7, 4, v12);
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
0x18001838c  mov     [rsp+arg_8], rbx
0x180018391  push    rdi
0x180018392  sub     rsp, 90h
0x180018399  mov     rax, cs:__security_cookie
0x1800183a0  xor     rax, rsp
0x1800183a3  mov     [rsp+98h+var_18], rax
0x1800183ab  mov     rbx, rcx
0x1800183ae  call    ?zInternalStart@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800183b3  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x1800183b8  mov     rdi, rax
0x1800183bb  mov     edx, [rax]
0x1800183bd  cmp     edx, 5
0x1800183c0  jbe     loc_180018481
0x1800183c6  mov     rax, [rax+18h]
0x1800183ca  mov     rdx, [rdi+10h]
0x1800183ce  mov     r8, 400000000000h
0x1800183d8  test    r8, rdx
0x1800183db  jz      loc_180018481
0x1800183e1  mov     rcx, rax
0x1800183e4  and     rcx, r8
0x1800183e7  cmp     rcx, rax
0x1800183ea  jnz     loc_180018481
0x1800183f0  call    cs:__imp_GetCurrentThreadId
0x1800183f7  nop     dword ptr [rax+rax+00h]
0x1800183fc  mov     [rsp+98h+var_68], eax
0x180018400  mov     [rsp+98h+var_60], 1000000h
0x180018409  mov     r8, [rbx+110h]
0x180018410  cmp     byte ptr [r8+4], 0
0x180018415  jz      short loc_180018436
0x180018417  lea     r9, [r8+18h]
0x18001841b  cmp     dword ptr [r9], 0
0x18001841f  jnz     short loc_180018439
0x180018421  cmp     dword ptr [r9+4], 0
0x180018426  jnz     short loc_180018439
0x180018428  cmp     dword ptr [r9+8], 0
0x18001842d  jnz     short loc_180018439
0x18001842f  cmp     dword ptr [r9+0Ch], 0
0x180018434  jnz     short loc_180018439
0x180018436  xor     r9d, r9d
0x180018439  lea     rax, [rsp+98h+var_68]
0x18001843e  mov     [rsp+98h+var_28], rax
0x180018443  mov     ecx, 4
0x180018448  mov     [rsp+98h+var_20], rcx
0x18001844d  lea     rax, [rsp+98h+var_60]
0x180018452  mov     [rsp+98h+var_38], rax
0x180018457  mov     [rsp+98h+var_30], 8
0x180018460  add     r8, 8
0x180018464  lea     rax, [rsp+98h+var_58]
0x180018469  mov     [rsp+98h+var_70], rax
0x18001846e  mov     [rsp+98h+var_78], ecx
0x180018472  lea     rdx, dword_1800686AC
0x180018479  mov     rcx, rdi
0x18001847c  call    _tlgWriteTransfer_EventWriteTransfer
0x180018481  cmp     dword ptr [rbx+138h], 0
0x180018488  jnz     short loc_1800184CC
0x18001848a  add     rbx, 120h
0x180018491  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180018499  jz      short loc_1800184C5
0x18001849b  mov     dl, 1
0x18001849d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800184a2  mov     [rbx], rax
0x1800184a5  test    rax, rax
0x1800184a8  jz      short loc_1800184CC
0x1800184aa  mov     rcx, [rax]
0x1800184ad  mov     [rbx+10h], rcx
0x1800184b1  mov     [rax], rbx
0x1800184b4  call    cs:__imp_GetCurrentThreadId
0x1800184bb  nop     dword ptr [rax+rax+00h]
0x1800184c0  mov     [rbx+18h], eax
0x1800184c3  jmp     short loc_1800184CC
0x1800184c5  mov     qword ptr [rbx], 0
0x1800184cc  mov     rcx, [rsp+98h+var_18]
0x1800184d4  xor     rcx, rsp; StackCookie
0x1800184d7  call    __security_check_cookie
0x1800184dc  mov     rbx, [rsp+98h+arg_8]
0x1800184e4  add     rsp, 90h
0x1800184eb  pop     rdi
0x1800184ec  retn
```
