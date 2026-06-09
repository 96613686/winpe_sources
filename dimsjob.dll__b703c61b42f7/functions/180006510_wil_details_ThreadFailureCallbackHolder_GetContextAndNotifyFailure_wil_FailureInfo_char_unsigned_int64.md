# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180006510`
- end: `0x1800065ca`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800065d0`

## callees

- `0x180006510`
- `0x1800069dc`
- `0x180006b98`
- `0x18000c010`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(
        struct wil::FailureInfo *a1,
        char *a2,
        unsigned __int64 a3)
{
  struct wil::FailureInfo *v5; // rdi
  char v6; // r14
  char v7; // bp
  struct wil::details::ThreadFailureCallbackHolder **Local; // rax
  struct wil::details::ThreadFailureCallbackHolder **v9; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v10; // rbx
  char v11; // al

  v5 = a1;
  *a2 = 0;
  v6 = 0;
  v7 = 1;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    Local = (struct wil::details::ThreadFailureCallbackHolder **)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal();
    v9 = Local;
    if ( Local )
    {
      if ( *Local )
      {
        *a2 = 0;
        if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(v5, *Local, a2, a3) )
          *((_QWORD *)v5 + 9) = a2;
        v10 = *v9;
        do
        {
          v11 = *((_BYTE *)v10 + 40);
          *((_BYTE *)v10 + 40) = 1;
          if ( !v11 )
          {
            v6 |= (***((__int64 (__fastcall ****)(_QWORD, struct wil::FailureInfo *))v10 + 1))(*((_QWORD *)v10 + 1), v5);
            *((_BYTE *)v10 + 40) = 0;
          }
          v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
        }
        while ( v10 );
      }
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
0x180006510  push    rbx
0x180006512  push    rbp
0x180006513  push    rsi
0x180006514  push    rdi
0x180006515  push    r14
0x180006517  push    r15
0x180006519  sub     rsp, 28h
0x18000651d  mov     r15, r8
0x180006520  mov     rsi, rdx
0x180006523  mov     rdi, rcx
0x180006526  mov     byte ptr [rdx], 0
0x180006529  xor     r14b, r14b
0x18000652c  mov     bpl, 1
0x18000652f  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006537  jz      short loc_180006598
0x180006539  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000653e  mov     rbx, rax
0x180006541  test    rax, rax
0x180006544  jz      short loc_180006598
0x180006546  cmp     qword ptr [rax], 0
0x18000654a  jz      short loc_180006598
0x18000654c  mov     [rsi], r14b
0x18000654f  mov     r9, r15; unsigned __int64
0x180006552  mov     r8, rsi; char *
0x180006555  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180006558  mov     rcx, rdi; struct wil::FailureInfo *
0x18000655b  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006560  test    al, al
0x180006562  jz      short loc_180006568
0x180006564  mov     [rdi+48h], rsi
0x180006568  mov     rbx, [rbx]
0x18000656b  mov     al, [rbx+28h]
0x18000656e  mov     [rbx+28h], bpl
0x180006572  test    al, al
0x180006574  jnz     short loc_18000658F
0x180006576  mov     rcx, [rbx+8]
0x18000657a  mov     rax, [rcx]
0x18000657d  mov     rdx, rdi
0x180006580  mov     rax, [rax]
0x180006583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006588  or      r14b, al
0x18000658b  mov     byte ptr [rbx+28h], 0
0x18000658f  mov     rbx, [rbx+10h]
0x180006593  test    rbx, rbx
0x180006596  jnz     short loc_18000656B
0x180006598  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000659f  test    rax, rax
0x1800065a2  jz      short loc_1800065BD
0x1800065a4  test    r14b, r14b
0x1800065a7  jnz     short loc_1800065B1
0x1800065a9  test    byte ptr [rdi+4], 2
0x1800065ad  jnz     short loc_1800065B1
0x1800065af  xor     ebp, ebp
0x1800065b1  mov     rdx, rdi
0x1800065b4  mov     cl, bpl
0x1800065b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065bc  nop
0x1800065bd  add     rsp, 28h
0x1800065c1  pop     r15
0x1800065c3  pop     r14
0x1800065c5  pop     rdi
0x1800065c6  pop     rsi
0x1800065c7  pop     rbp
0x1800065c8  pop     rbx
0x1800065c9  retn
```
