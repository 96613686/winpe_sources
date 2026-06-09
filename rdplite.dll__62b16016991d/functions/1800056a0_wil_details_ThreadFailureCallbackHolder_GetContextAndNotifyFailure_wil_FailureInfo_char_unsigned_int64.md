# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800056a0`
- end: `0x18000579b`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `251`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800057b0`

## callees

- `0x1800056a0`
- `0x180005ca4`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800056cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800056cf`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(
        unsigned __int64 a1,
        char *a2,
        unsigned __int64 a3)
{
  struct wil::FailureInfo *v5; // rdi
  char v6; // r14
  char v7; // bp
  __int64 v8; // rbx
  unsigned __int64 CurrentThreadId; // r9
  __int64 i; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v11; // rbx
  char v12; // al

  v5 = (struct wil::FailureInfo *)a1;
  *a2 = 0;
  v6 = 0;
  v7 = 1;
  v8 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    a1 = 10 * ((CurrentThreadId >> 2) / 0xA);
    for ( i = *(_QWORD *)(v8 + 8 * ((CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      {
        i += 16;
        break;
      }
    }
    if ( i && *(_QWORD *)i )
    {
      *a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(
             v5,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             a2,
             a3) )
      {
        *((_QWORD *)v5 + 9) = a2;
      }
      v11 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v12 = *((_BYTE *)v11 + 40);
        *((_BYTE *)v11 + 40) = 1;
        if ( !v12 )
        {
          v6 |= (***((__int64 (__fastcall ****)(_QWORD, struct wil::FailureInfo *))v11 + 1))(*((_QWORD *)v11 + 1), v5);
          *((_BYTE *)v11 + 40) = 0;
        }
        v11 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v11 + 2);
      }
      while ( v11 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( !v6 && (*((_BYTE *)v5 + 4) & 2) == 0 )
      v7 = 0;
    LOBYTE(a1) = v7;
    wil::details::g_pfnTelemetryCallback(a1, v5);
  }
}

```

## disassembly

```asm
0x1800056a0  push    rbx
0x1800056a2  push    rbp
0x1800056a3  push    rsi
0x1800056a4  push    rdi
0x1800056a5  push    r14
0x1800056a7  push    r15
0x1800056a9  sub     rsp, 28h
0x1800056ad  mov     r15, r8
0x1800056b0  mov     rsi, rdx
0x1800056b3  mov     rdi, rcx
0x1800056b6  mov     byte ptr [rdx], 0
0x1800056b9  xor     r14b, r14b
0x1800056bc  mov     bpl, 1
0x1800056bf  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800056c6  test    rbx, rbx
0x1800056c9  jz      loc_180005769
0x1800056cf  call    cs:__imp_GetCurrentThreadId
0x1800056d5  mov     r9d, eax
0x1800056d8  mov     r8d, eax
0x1800056db  shr     r8, 2
0x1800056df  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800056e9  mul     r8
0x1800056ec  shr     rdx, 3
0x1800056f0  lea     rcx, [rdx+rdx*4]
0x1800056f4  add     rcx, rcx
0x1800056f7  sub     r8, rcx
0x1800056fa  mov     rbx, [rbx+r8*8]
0x1800056fe  test    rbx, rbx
0x180005701  jz      short loc_180005712
0x180005703  cmp     [rbx], r9d
0x180005706  jz      short loc_18000570E
0x180005708  mov     rbx, [rbx+8]
0x18000570c  jmp     short loc_1800056FE
0x18000570e  add     rbx, 10h
0x180005712  test    rbx, rbx
0x180005715  jz      short loc_180005769
0x180005717  cmp     qword ptr [rbx], 0
0x18000571b  jz      short loc_180005769
0x18000571d  mov     [rsi], r14b
0x180005720  mov     r9, r15; unsigned __int64
0x180005723  mov     r8, rsi; char *
0x180005726  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180005729  mov     rcx, rdi; struct wil::FailureInfo *
0x18000572c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005731  test    al, al
0x180005733  jz      short loc_180005739
0x180005735  mov     [rdi+48h], rsi
0x180005739  mov     rbx, [rbx]
0x18000573c  mov     al, [rbx+28h]
0x18000573f  mov     [rbx+28h], bpl
0x180005743  test    al, al
0x180005745  jnz     short loc_180005760
0x180005747  mov     rcx, [rbx+8]
0x18000574b  mov     rax, [rcx]
0x18000574e  mov     rdx, rdi
0x180005751  mov     rax, [rax]
0x180005754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005759  or      r14b, al
0x18000575c  mov     byte ptr [rbx+28h], 0
0x180005760  mov     rbx, [rbx+10h]
0x180005764  test    rbx, rbx
0x180005767  jnz     short loc_18000573C
0x180005769  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180005770  test    rax, rax
0x180005773  jz      short loc_18000578E
0x180005775  test    r14b, r14b
0x180005778  jnz     short loc_180005782
0x18000577a  test    byte ptr [rdi+4], 2
0x18000577e  jnz     short loc_180005782
0x180005780  xor     ebp, ebp
0x180005782  mov     rdx, rdi
0x180005785  mov     cl, bpl
0x180005788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000578d  nop
0x18000578e  add     rsp, 28h
0x180005792  pop     r15
0x180005794  pop     r14
0x180005796  pop     rdi
0x180005797  pop     rsi
0x180005798  pop     rbp
0x180005799  pop     rbx
0x18000579a  retn
```
