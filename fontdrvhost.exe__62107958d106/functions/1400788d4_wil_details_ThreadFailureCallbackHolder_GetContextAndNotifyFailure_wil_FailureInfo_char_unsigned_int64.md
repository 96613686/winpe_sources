# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1400788d4`
- end: `0x14007898e`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400789a0`

## callees

- `0x1400788d4`
- `0x140078dac`
- `0x140078fc0`
- `0x140098010`

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
0x1400788d4  push    rbx
0x1400788d6  push    rbp
0x1400788d7  push    rsi
0x1400788d8  push    rdi
0x1400788d9  push    r14
0x1400788db  push    r15
0x1400788dd  sub     rsp, 28h
0x1400788e1  mov     r15, r8
0x1400788e4  mov     rsi, rdx
0x1400788e7  mov     rdi, rcx
0x1400788ea  mov     byte ptr [rdx], 0
0x1400788ed  xor     r14b, r14b
0x1400788f0  mov     bpl, 1
0x1400788f3  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400788fb  jz      short loc_14007895C
0x1400788fd  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x140078902  mov     rbx, rax
0x140078905  test    rax, rax
0x140078908  jz      short loc_14007895C
0x14007890a  cmp     qword ptr [rax], 0
0x14007890e  jz      short loc_14007895C
0x140078910  mov     [rsi], r14b
0x140078913  mov     r9, r15; unsigned __int64
0x140078916  mov     r8, rsi; char *
0x140078919  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x14007891c  mov     rcx, rdi; struct wil::FailureInfo *
0x14007891f  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140078924  test    al, al
0x140078926  jz      short loc_14007892C
0x140078928  mov     [rdi+48h], rsi
0x14007892c  mov     rbx, [rbx]
0x14007892f  mov     al, [rbx+28h]
0x140078932  mov     [rbx+28h], bpl
0x140078936  test    al, al
0x140078938  jnz     short loc_140078953
0x14007893a  mov     rcx, [rbx+8]
0x14007893e  mov     rax, [rcx]
0x140078941  mov     rdx, rdi
0x140078944  mov     rax, [rax]
0x140078947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007894c  or      r14b, al
0x14007894f  mov     byte ptr [rbx+28h], 0
0x140078953  mov     rbx, [rbx+10h]
0x140078957  test    rbx, rbx
0x14007895a  jnz     short loc_14007892F
0x14007895c  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140078963  test    rax, rax
0x140078966  jz      short loc_140078981
0x140078968  test    r14b, r14b
0x14007896b  jnz     short loc_140078975
0x14007896d  test    byte ptr [rdi+4], 2
0x140078971  jnz     short loc_140078975
0x140078973  xor     ebp, ebp
0x140078975  mov     rdx, rdi
0x140078978  mov     cl, bpl
0x14007897b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140078980  nop
0x140078981  add     rsp, 28h
0x140078985  pop     r15
0x140078987  pop     r14
0x140078989  pop     rdi
0x14007898a  pop     rsi
0x14007898b  pop     rbp
0x14007898c  pop     rbx
0x14007898d  retn
```
