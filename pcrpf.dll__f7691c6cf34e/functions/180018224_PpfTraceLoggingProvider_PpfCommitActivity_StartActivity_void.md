# PpfTraceLoggingProvider::PpfCommitActivity::StartActivity(void)

- ea: `0x180018224`
- end: `0x180018386`
- name: `?StartActivity@PpfCommitActivity@PpfTraceLoggingProvider@@QEAAXXZ`
- size: `354`
- prototype: `void __fastcall(PpfTraceLoggingProvider::PpfCommitActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000fec8`

## callees

- `0x180001640`
- `0x180003270`
- `0x1800070e0`
- `0x18000de98`
- `0x18000e680`
- `0x180018224`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018288`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001834c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018288`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001834c`

## pseudocode

```c
void __fastcall PpfTraceLoggingProvider::PpfCommitActivity::StartActivity(
        PpfTraceLoggingProvider::PpfCommitActivity *this)
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
        tlgWriteTransfer_EventWriteTransfer(v4, &byte_1800695DF, v6 + 8, v7, 4, v12);
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
0x180018224  mov     [rsp+arg_8], rbx
0x180018229  push    rdi
0x18001822a  sub     rsp, 90h
0x180018231  mov     rax, cs:__security_cookie
0x180018238  xor     rax, rsp
0x18001823b  mov     [rsp+98h+var_18], rax
0x180018243  mov     rbx, rcx
0x180018246  call    ?zInternalStart@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001824b  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x180018250  mov     rdi, rax
0x180018253  mov     edx, [rax]
0x180018255  cmp     edx, 5
0x180018258  jbe     loc_180018319
0x18001825e  mov     rax, [rax+18h]
0x180018262  mov     rdx, [rdi+10h]
0x180018266  mov     r8, 400000000000h
0x180018270  test    r8, rdx
0x180018273  jz      loc_180018319
0x180018279  mov     rcx, rax
0x18001827c  and     rcx, r8
0x18001827f  cmp     rcx, rax
0x180018282  jnz     loc_180018319
0x180018288  call    cs:__imp_GetCurrentThreadId
0x18001828f  nop     dword ptr [rax+rax+00h]
0x180018294  mov     [rsp+98h+var_68], eax
0x180018298  mov     [rsp+98h+var_60], 1000000h
0x1800182a1  mov     r8, [rbx+110h]
0x1800182a8  cmp     byte ptr [r8+4], 0
0x1800182ad  jz      short loc_1800182CE
0x1800182af  lea     r9, [r8+18h]
0x1800182b3  cmp     dword ptr [r9], 0
0x1800182b7  jnz     short loc_1800182D1
0x1800182b9  cmp     dword ptr [r9+4], 0
0x1800182be  jnz     short loc_1800182D1
0x1800182c0  cmp     dword ptr [r9+8], 0
0x1800182c5  jnz     short loc_1800182D1
0x1800182c7  cmp     dword ptr [r9+0Ch], 0
0x1800182cc  jnz     short loc_1800182D1
0x1800182ce  xor     r9d, r9d
0x1800182d1  lea     rax, [rsp+98h+var_68]
0x1800182d6  mov     [rsp+98h+var_28], rax
0x1800182db  mov     ecx, 4
0x1800182e0  mov     [rsp+98h+var_20], rcx
0x1800182e5  lea     rax, [rsp+98h+var_60]
0x1800182ea  mov     [rsp+98h+var_38], rax
0x1800182ef  mov     [rsp+98h+var_30], 8
0x1800182f8  add     r8, 8
0x1800182fc  lea     rax, [rsp+98h+var_58]
0x180018301  mov     [rsp+98h+var_70], rax
0x180018306  mov     [rsp+98h+var_78], ecx
0x18001830a  lea     rdx, byte_1800695DF
0x180018311  mov     rcx, rdi
0x180018314  call    _tlgWriteTransfer_EventWriteTransfer
0x180018319  cmp     dword ptr [rbx+138h], 0
0x180018320  jnz     short loc_180018364
0x180018322  add     rbx, 120h
0x180018329  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180018331  jz      short loc_18001835D
0x180018333  mov     dl, 1
0x180018335  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001833a  mov     [rbx], rax
0x18001833d  test    rax, rax
0x180018340  jz      short loc_180018364
0x180018342  mov     rcx, [rax]
0x180018345  mov     [rbx+10h], rcx
0x180018349  mov     [rax], rbx
0x18001834c  call    cs:__imp_GetCurrentThreadId
0x180018353  nop     dword ptr [rax+rax+00h]
0x180018358  mov     [rbx+18h], eax
0x18001835b  jmp     short loc_180018364
0x18001835d  mov     qword ptr [rbx], 0
0x180018364  mov     rcx, [rsp+98h+var_18]
0x18001836c  xor     rcx, rsp; StackCookie
0x18001836f  call    __security_check_cookie
0x180018374  mov     rbx, [rsp+98h+arg_8]
0x18001837c  add     rsp, 90h
0x180018383  pop     rdi
0x180018384  retn
```
