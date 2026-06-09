# ForcedEnrollmentTelemetryProvider::CspGetChildNodeNames::StartActivity(void)

- ea: `0x18000c8f4`
- end: `0x18000ca56`
- name: `?StartActivity@CspGetChildNodeNames@ForcedEnrollmentTelemetryProvider@@QEAAXXZ`
- size: `354`
- prototype: `void __fastcall(ForcedEnrollmentTelemetryProvider::CspGetChildNodeNames *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000bb80`

## callees

- `0x180001a70`
- `0x1800058d0`
- `0x18000c3fc`
- `0x18000c8f4`
- `0x18000d668`
- `0x1800358a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c958`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ca1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c958`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ca1c`

## pseudocode

```c
void __fastcall ForcedEnrollmentTelemetryProvider::CspGetChildNodeNames::StartActivity(
        ForcedEnrollmentTelemetryProvider::CspGetChildNodeNames *this)
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
        tlgWriteTransfer_EventWriteTransfer(v4, &unk_1800410A0, v7 + 8, v8, 4, v13);
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
0x18000c8f4  mov     [rsp+arg_8], rbx
0x18000c8f9  push    rdi
0x18000c8fa  sub     rsp, 90h
0x18000c901  mov     rax, cs:__security_cookie
0x18000c908  xor     rax, rsp
0x18000c90b  mov     [rsp+98h+var_18], rax
0x18000c913  mov     rbx, rcx
0x18000c916  call    ?zInternalStart@?$ActivityBase@VForcedEnrollmentTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000c91b  call    ?Provider@ForcedEnrollmentTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; ForcedEnrollmentTelemetryProvider::Provider(void)
0x18000c920  mov     rdi, rax
0x18000c923  mov     edx, [rax]
0x18000c925  cmp     edx, 5
0x18000c928  jbe     loc_18000C9E9
0x18000c92e  mov     rax, [rax+18h]
0x18000c932  mov     rdx, [rdi+10h]
0x18000c936  mov     r8, 400000000000h
0x18000c940  test    r8, rdx
0x18000c943  jz      loc_18000C9E9
0x18000c949  mov     rcx, rax
0x18000c94c  and     rcx, r8
0x18000c94f  cmp     rcx, rax
0x18000c952  jnz     loc_18000C9E9
0x18000c958  call    cs:__imp_GetCurrentThreadId
0x18000c95f  nop     dword ptr [rax+rax+00h]
0x18000c964  mov     [rsp+98h+var_68], eax
0x18000c968  mov     [rsp+98h+var_60], 0
0x18000c971  mov     r8, [rbx+110h]
0x18000c978  cmp     byte ptr [r8+4], 0
0x18000c97d  jz      short loc_18000C99E
0x18000c97f  lea     r9, [r8+18h]
0x18000c983  cmp     dword ptr [r9], 0
0x18000c987  jnz     short loc_18000C9A1
0x18000c989  cmp     dword ptr [r9+4], 0
0x18000c98e  jnz     short loc_18000C9A1
0x18000c990  cmp     dword ptr [r9+8], 0
0x18000c995  jnz     short loc_18000C9A1
0x18000c997  cmp     dword ptr [r9+0Ch], 0
0x18000c99c  jnz     short loc_18000C9A1
0x18000c99e  xor     r9d, r9d
0x18000c9a1  lea     rax, [rsp+98h+var_68]
0x18000c9a6  mov     [rsp+98h+var_28], rax
0x18000c9ab  mov     ecx, 4
0x18000c9b0  mov     [rsp+98h+var_20], rcx
0x18000c9b5  lea     rax, [rsp+98h+var_60]
0x18000c9ba  mov     [rsp+98h+var_38], rax
0x18000c9bf  mov     [rsp+98h+var_30], 8
0x18000c9c8  add     r8, 8
0x18000c9cc  lea     rax, [rsp+98h+var_58]
0x18000c9d1  mov     [rsp+98h+var_70], rax
0x18000c9d6  mov     [rsp+98h+var_78], ecx
0x18000c9da  lea     rdx, unk_1800410A0
0x18000c9e1  mov     rcx, rdi
0x18000c9e4  call    _tlgWriteTransfer_EventWriteTransfer
0x18000c9e9  cmp     dword ptr [rbx+138h], 0
0x18000c9f0  jnz     short loc_18000CA34
0x18000c9f2  add     rbx, 120h
0x18000c9f9  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000ca01  jz      short loc_18000CA2D
0x18000ca03  mov     dl, 1
0x18000ca05  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000ca0a  mov     [rbx], rax
0x18000ca0d  test    rax, rax
0x18000ca10  jz      short loc_18000CA34
0x18000ca12  mov     rcx, [rax]
0x18000ca15  mov     [rbx+10h], rcx
0x18000ca19  mov     [rax], rbx
0x18000ca1c  call    cs:__imp_GetCurrentThreadId
0x18000ca23  nop     dword ptr [rax+rax+00h]
0x18000ca28  mov     [rbx+18h], eax
0x18000ca2b  jmp     short loc_18000CA34
0x18000ca2d  mov     qword ptr [rbx], 0
0x18000ca34  mov     rcx, [rsp+98h+var_18]
0x18000ca3c  xor     rcx, rsp; StackCookie
0x18000ca3f  call    __security_check_cookie
0x18000ca44  mov     rbx, [rsp+98h+arg_8]
0x18000ca4c  add     rsp, 90h
0x18000ca53  pop     rdi
0x18000ca54  retn
```
