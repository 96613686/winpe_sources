# WorkerEtwProvider::Cleanup::StartActivity(ushort const *)

- ea: `0x1400078e4`
- end: `0x140007a7d`
- name: `?StartActivity@Cleanup@WorkerEtwProvider@@QEAAXPEBG@Z`
- size: `409`
- prototype: `void __fastcall(WorkerEtwProvider::Cleanup *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400060a8`

## callees

- `0x140001a60`
- `0x1400020b0`
- `0x140004ed0`
- `0x140006894`
- `0x1400078e4`
- `0x14000939c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007959`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007a44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007959`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007a44`

## pseudocode

```c
void __fastcall WorkerEtwProvider::Cleanup::StartActivity(WorkerEtwProvider::Cleanup *this, const unsigned __int16 *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // rcx
  const struct _tlgProvider_t *v6; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rax
  int v11; // eax
  char *v12; // rbx
  _QWORD *Local; // rax
  DWORD v14; // [rsp+30h] [rbp-29h] BYREF
  __int64 v15; // [rsp+38h] [rbp-21h] BYREF
  char v16[32]; // [rsp+40h] [rbp-19h] BYREF
  __int64 *v17; // [rsp+60h] [rbp+7h]
  __int64 v18; // [rsp+68h] [rbp+Fh]
  DWORD *v19; // [rsp+70h] [rbp+17h]
  __int64 v20; // [rsp+78h] [rbp+1Fh]
  const unsigned __int16 *v21; // [rsp+80h] [rbp+27h]
  int v22; // [rsp+88h] [rbp+2Fh]
  int v23; // [rsp+8Ch] [rbp+33h]

  wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v4 = WorkerEtwProvider::Provider();
  v6 = v4;
  if ( *(_DWORD *)v4 > 5u )
  {
    v5 = *((_QWORD *)v4 + 2);
    if ( (v5 & 0x400000000000LL) != 0 && (*((_QWORD *)v4 + 3) & 0x400000000000LL) == *((_QWORD *)v4 + 3) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v8 = *((_QWORD *)this + 34);
      v14 = CurrentThreadId;
      v15 = 0x1000000;
      if ( !*(_BYTE *)(v8 + 4)
        || (v9 = v8 + 24, !*(_DWORD *)(v8 + 24))
        && !*(_DWORD *)(v8 + 28)
        && !*(_DWORD *)(v8 + 32)
        && !*(_DWORD *)(v8 + 36) )
      {
        v9 = 0;
      }
      if ( a2 )
      {
        v10 = -1;
        do
          ++v10;
        while ( a2[v10] );
        v11 = 2 * v10 + 2;
      }
      else
      {
        a2 = (const unsigned __int16 *)&dword_140036644;
        v11 = 2;
      }
      v22 = v11;
      v21 = a2;
      v19 = &v14;
      v23 = 0;
      v17 = &v15;
      v20 = 4;
      v18 = 8;
      tlgWriteTransfer_EventWriteTransfer(v6, &word_14003909E, v8 + 8, v9, 5, v16);
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v12 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v5,
                          1);
      *(_QWORD *)v12 = Local;
      if ( Local )
      {
        *((_QWORD *)v12 + 2) = *Local;
        *Local = v12;
        *((_DWORD *)v12 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v12 = 0;
    }
  }
}

```

## disassembly

```asm
0x1400078e4  mov     [rsp-8+arg_8], rbx
0x1400078e9  mov     [rsp-8+arg_10], rsi
0x1400078ee  push    rbp
0x1400078ef  push    rdi
0x1400078f0  push    r14
0x1400078f2  lea     rbp, [rsp-47h]
0x1400078f7  sub     rsp, 0A0h
0x1400078fe  mov     rax, cs:__security_cookie
0x140007905  xor     rax, rsp
0x140007908  mov     [rbp+57h+var_20], rax
0x14000790c  mov     rdi, rdx
0x14000790f  mov     rbx, rcx
0x140007912  call    ?zInternalStart@?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x140007917  call    ?Provider@WorkerEtwProvider@@SAPEBU_tlgProvider_t@@XZ; WorkerEtwProvider::Provider(void)
0x14000791c  xor     r14d, r14d
0x14000791f  mov     rsi, rax
0x140007922  mov     r8d, [rax]
0x140007925  cmp     r8d, 5
0x140007929  jbe     loc_140007A12
0x14000792f  mov     rdx, [rax+18h]
0x140007933  mov     r8, 400000000000h
0x14000793d  mov     rcx, [rax+10h]
0x140007941  test    r8, rcx
0x140007944  jz      loc_140007A12
0x14000794a  mov     rax, rdx
0x14000794d  and     rax, r8
0x140007950  cmp     rax, rdx
0x140007953  jnz     loc_140007A12
0x140007959  call    cs:__imp_GetCurrentThreadId
0x140007960  nop     dword ptr [rax+rax+00h]
0x140007965  mov     r8, [rbx+110h]
0x14000796c  mov     [rbp+57h+var_80], eax
0x14000796f  mov     [rbp+57h+var_78], 1000000h
0x140007977  cmp     [r8+4], r14b
0x14000797b  jz      short loc_140007998
0x14000797d  lea     r9, [r8+18h]
0x140007981  cmp     [r9], r14d
0x140007984  jnz     short loc_14000799B
0x140007986  cmp     [r9+4], r14d
0x14000798a  jnz     short loc_14000799B
0x14000798c  cmp     [r9+8], r14d
0x140007990  jnz     short loc_14000799B
0x140007992  cmp     [r9+0Ch], r14d
0x140007996  jnz     short loc_14000799B
0x140007998  mov     r9, r14
0x14000799b  test    rdi, rdi
0x14000799e  jz      short loc_1400079B7
0x1400079a0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400079a4  inc     rax
0x1400079a7  cmp     [rdi+rax*2], r14w
0x1400079ac  jnz     short loc_1400079A4
0x1400079ae  lea     eax, ds:2[rax*2]
0x1400079b5  jmp     short loc_1400079C3
0x1400079b7  lea     rdi, dword_140036644
0x1400079be  mov     eax, 2
0x1400079c3  mov     [rbp+57h+var_28], eax
0x1400079c6  lea     rdx, word_14003909E
0x1400079cd  lea     rax, [rbp+57h+var_80]
0x1400079d1  mov     [rbp+57h+var_30], rdi
0x1400079d5  mov     [rbp+57h+var_40], rax
0x1400079d9  add     r8, 8
0x1400079dd  lea     rax, [rbp+57h+var_78]
0x1400079e1  mov     [rbp+57h+var_24], r14d
0x1400079e5  mov     [rbp+57h+var_50], rax
0x1400079e9  mov     rcx, rsi
0x1400079ec  lea     rax, [rbp+57h+var_70]
0x1400079f0  mov     [rbp+57h+var_38], 4
0x1400079f8  mov     [rsp+0B0h+var_88], rax
0x1400079fd  mov     [rsp+0B0h+var_90], 5
0x140007a05  mov     [rbp+57h+var_48], 8
0x140007a0d  call    _tlgWriteTransfer_EventWriteTransfer
0x140007a12  cmp     [rbx+138h], r14d
0x140007a19  jnz     short loc_140007A58
0x140007a1b  add     rbx, 120h
0x140007a22  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r14; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140007a29  jz      short loc_140007A55
0x140007a2b  mov     dl, 1
0x140007a2d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x140007a32  mov     [rbx], rax
0x140007a35  test    rax, rax
0x140007a38  jz      short loc_140007A58
0x140007a3a  mov     rcx, [rax]
0x140007a3d  mov     [rbx+10h], rcx
0x140007a41  mov     [rax], rbx
0x140007a44  call    cs:__imp_GetCurrentThreadId
0x140007a4b  nop     dword ptr [rax+rax+00h]
0x140007a50  mov     [rbx+18h], eax
0x140007a53  jmp     short loc_140007A58
0x140007a55  mov     [rbx], r14
0x140007a58  mov     rcx, [rbp+57h+var_20]
0x140007a5c  xor     rcx, rsp; StackCookie
0x140007a5f  call    __security_check_cookie
0x140007a64  lea     r11, [rsp+0B0h+var_10]
0x140007a6c  mov     rbx, [r11+28h]
0x140007a70  mov     rsi, [r11+30h]
0x140007a74  mov     rsp, r11
0x140007a77  pop     r14
0x140007a79  pop     rdi
0x140007a7a  pop     rbp
0x140007a7b  retn
```
