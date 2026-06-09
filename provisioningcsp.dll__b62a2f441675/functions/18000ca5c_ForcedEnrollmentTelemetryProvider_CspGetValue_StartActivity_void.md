# ForcedEnrollmentTelemetryProvider::CspGetValue::StartActivity(void)

- ea: `0x18000ca5c`
- end: `0x18000cbbe`
- name: `?StartActivity@CspGetValue@ForcedEnrollmentTelemetryProvider@@QEAAXXZ`
- size: `354`
- prototype: `void __fastcall(ForcedEnrollmentTelemetryProvider::CspGetValue *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000bd70`

## callees

- `0x180001a70`
- `0x1800058d0`
- `0x18000c3fc`
- `0x18000ca5c`
- `0x18000d668`
- `0x1800358a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cac0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cb84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cac0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cb84`

## pseudocode

```c
void __fastcall ForcedEnrollmentTelemetryProvider::CspGetValue::StartActivity(
        ForcedEnrollmentTelemetryProvider::CspGetValue *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // rcx
  const struct _tlgProvider_t *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  char *v9; // rbx
  _QWORD *Local; // rax
  DWORD CurrentThreadId; // [rsp+30h] [rbp-68h] BYREF
  __int64 v12; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v13[32]; // [rsp+40h] [rbp-58h] BYREF
  __int64 *v14; // [rsp+60h] [rbp-38h]
  __int64 v15; // [rsp+68h] [rbp-30h]
  DWORD *p_CurrentThreadId; // [rsp+70h] [rbp-28h]
  __int64 v17; // [rsp+78h] [rbp-20h]

  wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = ForcedEnrollmentTelemetryProvider::Provider();
  v4 = v2;
  v5 = *(unsigned int *)v2;
  if ( (unsigned int)v5 > 5 )
  {
    v6 = *((_QWORD *)v2 + 3);
    v5 = *((_QWORD *)v4 + 2);
    if ( (v5 & 0x400000000000LL) != 0 )
    {
      v3 = v6 & 0x400000000000LL;
      if ( (v6 & 0x400000000000LL) == v6 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v12 = 0;
        v7 = *((_QWORD *)this + 34);
        if ( !*(_BYTE *)(v7 + 4)
          || (v8 = v7 + 24, !*(_DWORD *)(v7 + 24))
          && !*(_DWORD *)(v7 + 28)
          && !*(_DWORD *)(v7 + 32)
          && !*(_DWORD *)(v7 + 36) )
        {
          v8 = 0;
        }
        p_CurrentThreadId = &CurrentThreadId;
        v17 = 4;
        v14 = &v12;
        v15 = 8;
        tlgWriteTransfer_EventWriteTransfer(v4, &word_180040C5E, v7 + 8, v8, 4, v13);
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v9 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v5) = 1;
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v3,
                          v5);
      *(_QWORD *)v9 = Local;
      if ( Local )
      {
        *((_QWORD *)v9 + 2) = *Local;
        *Local = v9;
        *((_DWORD *)v9 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v9 = 0;
    }
  }
}

```

## disassembly

```asm
0x18000ca5c  mov     [rsp+arg_8], rbx
0x18000ca61  push    rdi
0x18000ca62  sub     rsp, 90h
0x18000ca69  mov     rax, cs:__security_cookie
0x18000ca70  xor     rax, rsp
0x18000ca73  mov     [rsp+98h+var_18], rax
0x18000ca7b  mov     rbx, rcx
0x18000ca7e  call    ?zInternalStart@?$ActivityBase@VForcedEnrollmentTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000ca83  call    ?Provider@ForcedEnrollmentTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; ForcedEnrollmentTelemetryProvider::Provider(void)
0x18000ca88  mov     rdi, rax
0x18000ca8b  mov     edx, [rax]
0x18000ca8d  cmp     edx, 5
0x18000ca90  jbe     loc_18000CB51
0x18000ca96  mov     rax, [rax+18h]
0x18000ca9a  mov     rdx, [rdi+10h]
0x18000ca9e  mov     r8, 400000000000h
0x18000caa8  test    r8, rdx
0x18000caab  jz      loc_18000CB51
0x18000cab1  mov     rcx, rax
0x18000cab4  and     rcx, r8
0x18000cab7  cmp     rcx, rax
0x18000caba  jnz     loc_18000CB51
0x18000cac0  call    cs:__imp_GetCurrentThreadId
0x18000cac7  nop     dword ptr [rax+rax+00h]
0x18000cacc  mov     [rsp+98h+var_68], eax
0x18000cad0  mov     [rsp+98h+var_60], 0
0x18000cad9  mov     r8, [rbx+110h]
0x18000cae0  cmp     byte ptr [r8+4], 0
0x18000cae5  jz      short loc_18000CB06
0x18000cae7  lea     r9, [r8+18h]
0x18000caeb  cmp     dword ptr [r9], 0
0x18000caef  jnz     short loc_18000CB09
0x18000caf1  cmp     dword ptr [r9+4], 0
0x18000caf6  jnz     short loc_18000CB09
0x18000caf8  cmp     dword ptr [r9+8], 0
0x18000cafd  jnz     short loc_18000CB09
0x18000caff  cmp     dword ptr [r9+0Ch], 0
0x18000cb04  jnz     short loc_18000CB09
0x18000cb06  xor     r9d, r9d
0x18000cb09  lea     rax, [rsp+98h+var_68]
0x18000cb0e  mov     [rsp+98h+var_28], rax
0x18000cb13  mov     ecx, 4
0x18000cb18  mov     [rsp+98h+var_20], rcx
0x18000cb1d  lea     rax, [rsp+98h+var_60]
0x18000cb22  mov     [rsp+98h+var_38], rax
0x18000cb27  mov     [rsp+98h+var_30], 8
0x18000cb30  add     r8, 8
0x18000cb34  lea     rax, [rsp+98h+var_58]
0x18000cb39  mov     [rsp+98h+var_70], rax
0x18000cb3e  mov     [rsp+98h+var_78], ecx
0x18000cb42  lea     rdx, word_180040C5E
0x18000cb49  mov     rcx, rdi
0x18000cb4c  call    _tlgWriteTransfer_EventWriteTransfer
0x18000cb51  cmp     dword ptr [rbx+138h], 0
0x18000cb58  jnz     short loc_18000CB9C
0x18000cb5a  add     rbx, 120h
0x18000cb61  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000cb69  jz      short loc_18000CB95
0x18000cb6b  mov     dl, 1
0x18000cb6d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000cb72  mov     [rbx], rax
0x18000cb75  test    rax, rax
0x18000cb78  jz      short loc_18000CB9C
0x18000cb7a  mov     rcx, [rax]
0x18000cb7d  mov     [rbx+10h], rcx
0x18000cb81  mov     [rax], rbx
0x18000cb84  call    cs:__imp_GetCurrentThreadId
0x18000cb8b  nop     dword ptr [rax+rax+00h]
0x18000cb90  mov     [rbx+18h], eax
0x18000cb93  jmp     short loc_18000CB9C
0x18000cb95  mov     qword ptr [rbx], 0
0x18000cb9c  mov     rcx, [rsp+98h+var_18]
0x18000cba4  xor     rcx, rsp; StackCookie
0x18000cba7  call    __security_check_cookie
0x18000cbac  mov     rbx, [rsp+98h+arg_8]
0x18000cbb4  add     rsp, 90h
0x18000cbbb  pop     rdi
0x18000cbbc  retn
```
