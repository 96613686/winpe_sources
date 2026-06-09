# PpfTraceLoggingProvider::FirmwareDeviceQueryCallbackActivity::StartActivity(void)

- ea: `0x180050c3c`
- end: `0x180050d9e`
- name: `?StartActivity@FirmwareDeviceQueryCallbackActivity@PpfTraceLoggingProvider@@QEAAXXZ`
- size: `354`
- prototype: `void __fastcall(PpfTraceLoggingProvider::FirmwareDeviceQueryCallbackActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18004f450`

## callees

- `0x180001640`
- `0x180003270`
- `0x1800070e0`
- `0x18000de98`
- `0x18000e680`
- `0x180050c3c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180050ca0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180050d64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180050ca0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180050d64`

## pseudocode

```c
void __fastcall PpfTraceLoggingProvider::FirmwareDeviceQueryCallbackActivity::StartActivity(
        PpfTraceLoggingProvider::FirmwareDeviceQueryCallbackActivity *this)
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
        tlgWriteTransfer_EventWriteTransfer(v4, byte_1800698E9, v6 + 8, v7, 4, v12);
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
0x180050c3c  mov     [rsp+arg_8], rbx
0x180050c41  push    rdi
0x180050c42  sub     rsp, 90h
0x180050c49  mov     rax, cs:__security_cookie
0x180050c50  xor     rax, rsp
0x180050c53  mov     [rsp+98h+var_18], rax
0x180050c5b  mov     rbx, rcx
0x180050c5e  call    ?zInternalStart@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180050c63  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x180050c68  mov     rdi, rax
0x180050c6b  mov     edx, [rax]
0x180050c6d  cmp     edx, 5
0x180050c70  jbe     loc_180050D31
0x180050c76  mov     rax, [rax+18h]
0x180050c7a  mov     rdx, [rdi+10h]
0x180050c7e  mov     r8, 400000000000h
0x180050c88  test    r8, rdx
0x180050c8b  jz      loc_180050D31
0x180050c91  mov     rcx, rax
0x180050c94  and     rcx, r8
0x180050c97  cmp     rcx, rax
0x180050c9a  jnz     loc_180050D31
0x180050ca0  call    cs:__imp_GetCurrentThreadId
0x180050ca7  nop     dword ptr [rax+rax+00h]
0x180050cac  mov     [rsp+98h+var_68], eax
0x180050cb0  mov     [rsp+98h+var_60], 1000000h
0x180050cb9  mov     r8, [rbx+110h]
0x180050cc0  cmp     byte ptr [r8+4], 0
0x180050cc5  jz      short loc_180050CE6
0x180050cc7  lea     r9, [r8+18h]
0x180050ccb  cmp     dword ptr [r9], 0
0x180050ccf  jnz     short loc_180050CE9
0x180050cd1  cmp     dword ptr [r9+4], 0
0x180050cd6  jnz     short loc_180050CE9
0x180050cd8  cmp     dword ptr [r9+8], 0
0x180050cdd  jnz     short loc_180050CE9
0x180050cdf  cmp     dword ptr [r9+0Ch], 0
0x180050ce4  jnz     short loc_180050CE9
0x180050ce6  xor     r9d, r9d
0x180050ce9  lea     rax, [rsp+98h+var_68]
0x180050cee  mov     [rsp+98h+var_28], rax
0x180050cf3  mov     ecx, 4
0x180050cf8  mov     [rsp+98h+var_20], rcx
0x180050cfd  lea     rax, [rsp+98h+var_60]
0x180050d02  mov     [rsp+98h+var_38], rax
0x180050d07  mov     [rsp+98h+var_30], 8
0x180050d10  add     r8, 8
0x180050d14  lea     rax, [rsp+98h+var_58]
0x180050d19  mov     [rsp+98h+var_70], rax
0x180050d1e  mov     [rsp+98h+var_78], ecx
0x180050d22  lea     rdx, byte_1800698E9
0x180050d29  mov     rcx, rdi
0x180050d2c  call    _tlgWriteTransfer_EventWriteTransfer
0x180050d31  cmp     dword ptr [rbx+138h], 0
0x180050d38  jnz     short loc_180050D7C
0x180050d3a  add     rbx, 120h
0x180050d41  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180050d49  jz      short loc_180050D75
0x180050d4b  mov     dl, 1
0x180050d4d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180050d52  mov     [rbx], rax
0x180050d55  test    rax, rax
0x180050d58  jz      short loc_180050D7C
0x180050d5a  mov     rcx, [rax]
0x180050d5d  mov     [rbx+10h], rcx
0x180050d61  mov     [rax], rbx
0x180050d64  call    cs:__imp_GetCurrentThreadId
0x180050d6b  nop     dword ptr [rax+rax+00h]
0x180050d70  mov     [rbx+18h], eax
0x180050d73  jmp     short loc_180050D7C
0x180050d75  mov     qword ptr [rbx], 0
0x180050d7c  mov     rcx, [rsp+98h+var_18]
0x180050d84  xor     rcx, rsp; StackCookie
0x180050d87  call    __security_check_cookie
0x180050d8c  mov     rbx, [rsp+98h+arg_8]
0x180050d94  add     rsp, 90h
0x180050d9b  pop     rdi
0x180050d9c  retn
```
