# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140004614`
- end: `0x1400046d0`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `188`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400046e0`

## callees

- `0x140004614`
- `0x140004aec`
- `0x140004cbc`
- `0x140018010`

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
    Local = (struct wil::details::ThreadFailureCallbackHolder **)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                                                                   a1,
                                                                   0);
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
0x140004614  push    rbx
0x140004616  push    rbp
0x140004617  push    rsi
0x140004618  push    rdi
0x140004619  push    r14
0x14000461b  push    r15
0x14000461d  sub     rsp, 28h
0x140004621  mov     r15, r8
0x140004624  mov     rsi, rdx
0x140004627  mov     rdi, rcx
0x14000462a  mov     byte ptr [rdx], 0
0x14000462d  xor     r14b, r14b
0x140004630  mov     bpl, 1
0x140004633  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000463b  jz      short loc_14000469E
0x14000463d  xor     edx, edx
0x14000463f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x140004644  mov     rbx, rax
0x140004647  test    rax, rax
0x14000464a  jz      short loc_14000469E
0x14000464c  cmp     qword ptr [rax], 0
0x140004650  jz      short loc_14000469E
0x140004652  mov     [rsi], r14b
0x140004655  mov     r9, r15; unsigned __int64
0x140004658  mov     r8, rsi; char *
0x14000465b  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x14000465e  mov     rcx, rdi; struct wil::FailureInfo *
0x140004661  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140004666  test    al, al
0x140004668  jz      short loc_14000466E
0x14000466a  mov     [rdi+48h], rsi
0x14000466e  mov     rbx, [rbx]
0x140004671  mov     al, [rbx+28h]
0x140004674  mov     [rbx+28h], bpl
0x140004678  test    al, al
0x14000467a  jnz     short loc_140004695
0x14000467c  mov     rcx, [rbx+8]
0x140004680  mov     rax, [rcx]
0x140004683  mov     rdx, rdi
0x140004686  mov     rax, [rax]
0x140004689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000468e  or      r14b, al
0x140004691  mov     byte ptr [rbx+28h], 0
0x140004695  mov     rbx, [rbx+10h]
0x140004699  test    rbx, rbx
0x14000469c  jnz     short loc_140004671
0x14000469e  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1400046a5  test    rax, rax
0x1400046a8  jz      short loc_1400046C3
0x1400046aa  test    r14b, r14b
0x1400046ad  jnz     short loc_1400046B7
0x1400046af  test    byte ptr [rdi+4], 2
0x1400046b3  jnz     short loc_1400046B7
0x1400046b5  xor     ebp, ebp
0x1400046b7  mov     rdx, rdi
0x1400046ba  mov     cl, bpl
0x1400046bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400046c2  nop
0x1400046c3  add     rsp, 28h
0x1400046c7  pop     r15
0x1400046c9  pop     r14
0x1400046cb  pop     rdi
0x1400046cc  pop     rsi
0x1400046cd  pop     rbp
0x1400046ce  pop     rbx
0x1400046cf  retn
```
