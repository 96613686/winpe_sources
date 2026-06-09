# ForcedEnrollmentTelemetryProvider::CspSetValue::StartActivity(void)

- ea: `0x18000cbc4`
- end: `0x18000cd26`
- name: `?StartActivity@CspSetValue@ForcedEnrollmentTelemetryProvider@@QEAAXXZ`
- size: `354`
- prototype: `void __fastcall(ForcedEnrollmentTelemetryProvider::CspSetValue *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000c7d0`

## callees

- `0x180001a70`
- `0x1800058d0`
- `0x18000c3fc`
- `0x18000cbc4`
- `0x18000d668`
- `0x1800358a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cc28`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ccec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cc28`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ccec`

## pseudocode

```c
void __fastcall ForcedEnrollmentTelemetryProvider::CspSetValue::StartActivity(
        ForcedEnrollmentTelemetryProvider::CspSetValue *this)
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
        tlgWriteTransfer_EventWriteTransfer(v4, &word_180040EEE, v7 + 8, v8, 4, v13);
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
0x18000cbc4  mov     [rsp+arg_8], rbx
0x18000cbc9  push    rdi
0x18000cbca  sub     rsp, 90h
0x18000cbd1  mov     rax, cs:__security_cookie
0x18000cbd8  xor     rax, rsp
0x18000cbdb  mov     [rsp+98h+var_18], rax
0x18000cbe3  mov     rbx, rcx
0x18000cbe6  call    ?zInternalStart@?$ActivityBase@VForcedEnrollmentTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000cbeb  call    ?Provider@ForcedEnrollmentTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; ForcedEnrollmentTelemetryProvider::Provider(void)
0x18000cbf0  mov     rdi, rax
0x18000cbf3  mov     edx, [rax]
0x18000cbf5  cmp     edx, 5
0x18000cbf8  jbe     loc_18000CCB9
0x18000cbfe  mov     rax, [rax+18h]
0x18000cc02  mov     rdx, [rdi+10h]
0x18000cc06  mov     r8, 400000000000h
0x18000cc10  test    r8, rdx
0x18000cc13  jz      loc_18000CCB9
0x18000cc19  mov     rcx, rax
0x18000cc1c  and     rcx, r8
0x18000cc1f  cmp     rcx, rax
0x18000cc22  jnz     loc_18000CCB9
0x18000cc28  call    cs:__imp_GetCurrentThreadId
0x18000cc2f  nop     dword ptr [rax+rax+00h]
0x18000cc34  mov     [rsp+98h+var_68], eax
0x18000cc38  mov     [rsp+98h+var_60], 0
0x18000cc41  mov     r8, [rbx+110h]
0x18000cc48  cmp     byte ptr [r8+4], 0
0x18000cc4d  jz      short loc_18000CC6E
0x18000cc4f  lea     r9, [r8+18h]
0x18000cc53  cmp     dword ptr [r9], 0
0x18000cc57  jnz     short loc_18000CC71
0x18000cc59  cmp     dword ptr [r9+4], 0
0x18000cc5e  jnz     short loc_18000CC71
0x18000cc60  cmp     dword ptr [r9+8], 0
0x18000cc65  jnz     short loc_18000CC71
0x18000cc67  cmp     dword ptr [r9+0Ch], 0
0x18000cc6c  jnz     short loc_18000CC71
0x18000cc6e  xor     r9d, r9d
0x18000cc71  lea     rax, [rsp+98h+var_68]
0x18000cc76  mov     [rsp+98h+var_28], rax
0x18000cc7b  mov     ecx, 4
0x18000cc80  mov     [rsp+98h+var_20], rcx
0x18000cc85  lea     rax, [rsp+98h+var_60]
0x18000cc8a  mov     [rsp+98h+var_38], rax
0x18000cc8f  mov     [rsp+98h+var_30], 8
0x18000cc98  add     r8, 8
0x18000cc9c  lea     rax, [rsp+98h+var_58]
0x18000cca1  mov     [rsp+98h+var_70], rax
0x18000cca6  mov     [rsp+98h+var_78], ecx
0x18000ccaa  lea     rdx, word_180040EEE
0x18000ccb1  mov     rcx, rdi
0x18000ccb4  call    _tlgWriteTransfer_EventWriteTransfer
0x18000ccb9  cmp     dword ptr [rbx+138h], 0
0x18000ccc0  jnz     short loc_18000CD04
0x18000ccc2  add     rbx, 120h
0x18000ccc9  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000ccd1  jz      short loc_18000CCFD
0x18000ccd3  mov     dl, 1
0x18000ccd5  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000ccda  mov     [rbx], rax
0x18000ccdd  test    rax, rax
0x18000cce0  jz      short loc_18000CD04
0x18000cce2  mov     rcx, [rax]
0x18000cce5  mov     [rbx+10h], rcx
0x18000cce9  mov     [rax], rbx
0x18000ccec  call    cs:__imp_GetCurrentThreadId
0x18000ccf3  nop     dword ptr [rax+rax+00h]
0x18000ccf8  mov     [rbx+18h], eax
0x18000ccfb  jmp     short loc_18000CD04
0x18000ccfd  mov     qword ptr [rbx], 0
0x18000cd04  mov     rcx, [rsp+98h+var_18]
0x18000cd0c  xor     rcx, rsp; StackCookie
0x18000cd0f  call    __security_check_cookie
0x18000cd14  mov     rbx, [rsp+98h+arg_8]
0x18000cd1c  add     rsp, 90h
0x18000cd23  pop     rdi
0x18000cd24  retn
```
