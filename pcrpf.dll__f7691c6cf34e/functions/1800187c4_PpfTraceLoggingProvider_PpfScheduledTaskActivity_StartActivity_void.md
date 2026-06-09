# PpfTraceLoggingProvider::PpfScheduledTaskActivity::StartActivity(void)

- ea: `0x1800187c4`
- end: `0x180018926`
- name: `?StartActivity@PpfScheduledTaskActivity@PpfTraceLoggingProvider@@QEAAXXZ`
- size: `354`
- prototype: `void __fastcall(PpfTraceLoggingProvider::PpfScheduledTaskActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180015ff8`

## callees

- `0x180001640`
- `0x180003270`
- `0x1800070e0`
- `0x18000de98`
- `0x18000e680`
- `0x1800187c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018828`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800188ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018828`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800188ec`

## pseudocode

```c
void __fastcall PpfTraceLoggingProvider::PpfScheduledTaskActivity::StartActivity(
        PpfTraceLoggingProvider::PpfScheduledTaskActivity *this)
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
        tlgWriteTransfer_EventWriteTransfer(v4, &unk_180068C78, v6 + 8, v7, 4, v12);
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
0x1800187c4  mov     [rsp+arg_8], rbx
0x1800187c9  push    rdi
0x1800187ca  sub     rsp, 90h
0x1800187d1  mov     rax, cs:__security_cookie
0x1800187d8  xor     rax, rsp
0x1800187db  mov     [rsp+98h+var_18], rax
0x1800187e3  mov     rbx, rcx
0x1800187e6  call    ?zInternalStart@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800187eb  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x1800187f0  mov     rdi, rax
0x1800187f3  mov     edx, [rax]
0x1800187f5  cmp     edx, 5
0x1800187f8  jbe     loc_1800188B9
0x1800187fe  mov     rax, [rax+18h]
0x180018802  mov     rdx, [rdi+10h]
0x180018806  mov     r8, 400000000000h
0x180018810  test    r8, rdx
0x180018813  jz      loc_1800188B9
0x180018819  mov     rcx, rax
0x18001881c  and     rcx, r8
0x18001881f  cmp     rcx, rax
0x180018822  jnz     loc_1800188B9
0x180018828  call    cs:__imp_GetCurrentThreadId
0x18001882f  nop     dword ptr [rax+rax+00h]
0x180018834  mov     [rsp+98h+var_68], eax
0x180018838  mov     [rsp+98h+var_60], 1000000h
0x180018841  mov     r8, [rbx+110h]
0x180018848  cmp     byte ptr [r8+4], 0
0x18001884d  jz      short loc_18001886E
0x18001884f  lea     r9, [r8+18h]
0x180018853  cmp     dword ptr [r9], 0
0x180018857  jnz     short loc_180018871
0x180018859  cmp     dword ptr [r9+4], 0
0x18001885e  jnz     short loc_180018871
0x180018860  cmp     dword ptr [r9+8], 0
0x180018865  jnz     short loc_180018871
0x180018867  cmp     dword ptr [r9+0Ch], 0
0x18001886c  jnz     short loc_180018871
0x18001886e  xor     r9d, r9d
0x180018871  lea     rax, [rsp+98h+var_68]
0x180018876  mov     [rsp+98h+var_28], rax
0x18001887b  mov     ecx, 4
0x180018880  mov     [rsp+98h+var_20], rcx
0x180018885  lea     rax, [rsp+98h+var_60]
0x18001888a  mov     [rsp+98h+var_38], rax
0x18001888f  mov     [rsp+98h+var_30], 8
0x180018898  add     r8, 8
0x18001889c  lea     rax, [rsp+98h+var_58]
0x1800188a1  mov     [rsp+98h+var_70], rax
0x1800188a6  mov     [rsp+98h+var_78], ecx
0x1800188aa  lea     rdx, unk_180068C78
0x1800188b1  mov     rcx, rdi
0x1800188b4  call    _tlgWriteTransfer_EventWriteTransfer
0x1800188b9  cmp     dword ptr [rbx+138h], 0
0x1800188c0  jnz     short loc_180018904
0x1800188c2  add     rbx, 120h
0x1800188c9  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800188d1  jz      short loc_1800188FD
0x1800188d3  mov     dl, 1
0x1800188d5  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800188da  mov     [rbx], rax
0x1800188dd  test    rax, rax
0x1800188e0  jz      short loc_180018904
0x1800188e2  mov     rcx, [rax]
0x1800188e5  mov     [rbx+10h], rcx
0x1800188e9  mov     [rax], rbx
0x1800188ec  call    cs:__imp_GetCurrentThreadId
0x1800188f3  nop     dword ptr [rax+rax+00h]
0x1800188f8  mov     [rbx+18h], eax
0x1800188fb  jmp     short loc_180018904
0x1800188fd  mov     qword ptr [rbx], 0
0x180018904  mov     rcx, [rsp+98h+var_18]
0x18001890c  xor     rcx, rsp; StackCookie
0x18001890f  call    __security_check_cookie
0x180018914  mov     rbx, [rsp+98h+arg_8]
0x18001891c  add     rsp, 90h
0x180018923  pop     rdi
0x180018924  retn
```
