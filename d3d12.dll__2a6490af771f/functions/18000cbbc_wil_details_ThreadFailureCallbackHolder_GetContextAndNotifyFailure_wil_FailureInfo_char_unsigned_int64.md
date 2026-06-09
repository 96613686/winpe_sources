# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000cbbc`
- end: `0x18000cc76`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000cc80`

## callees

- `0x18000cbbc`
- `0x18000cff0`
- `0x18000d04c`
- `0x180015010`

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
0x18000cbbc  push    rbx
0x18000cbbe  push    rbp
0x18000cbbf  push    rsi
0x18000cbc0  push    rdi
0x18000cbc1  push    r14
0x18000cbc3  push    r15
0x18000cbc5  sub     rsp, 28h
0x18000cbc9  mov     r15, r8
0x18000cbcc  mov     rsi, rdx
0x18000cbcf  mov     rdi, rcx
0x18000cbd2  mov     byte ptr [rdx], 0
0x18000cbd5  xor     r14b, r14b
0x18000cbd8  mov     bpl, 1
0x18000cbdb  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000cbe3  jz      short loc_18000CC44
0x18000cbe5  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000cbea  mov     rbx, rax
0x18000cbed  test    rax, rax
0x18000cbf0  jz      short loc_18000CC44
0x18000cbf2  cmp     qword ptr [rax], 0
0x18000cbf6  jz      short loc_18000CC44
0x18000cbf8  mov     [rsi], r14b
0x18000cbfb  mov     r9, r15; unsigned __int64
0x18000cbfe  mov     r8, rsi; char *
0x18000cc01  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x18000cc04  mov     rcx, rdi; struct wil::FailureInfo *
0x18000cc07  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000cc0c  test    al, al
0x18000cc0e  jz      short loc_18000CC14
0x18000cc10  mov     [rdi+48h], rsi
0x18000cc14  mov     rbx, [rbx]
0x18000cc17  mov     al, [rbx+28h]
0x18000cc1a  mov     [rbx+28h], bpl
0x18000cc1e  test    al, al
0x18000cc20  jnz     short loc_18000CC3B
0x18000cc22  mov     rcx, [rbx+8]
0x18000cc26  mov     rax, [rcx]
0x18000cc29  mov     rdx, rdi
0x18000cc2c  mov     rax, [rax]
0x18000cc2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc34  or      r14b, al
0x18000cc37  mov     byte ptr [rbx+28h], 0
0x18000cc3b  mov     rbx, [rbx+10h]
0x18000cc3f  test    rbx, rbx
0x18000cc42  jnz     short loc_18000CC17
0x18000cc44  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000cc4b  test    rax, rax
0x18000cc4e  jz      short loc_18000CC69
0x18000cc50  test    r14b, r14b
0x18000cc53  jnz     short loc_18000CC5D
0x18000cc55  test    byte ptr [rdi+4], 2
0x18000cc59  jnz     short loc_18000CC5D
0x18000cc5b  xor     ebp, ebp
0x18000cc5d  mov     rdx, rdi
0x18000cc60  mov     cl, bpl
0x18000cc63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc68  nop
0x18000cc69  add     rsp, 28h
0x18000cc6d  pop     r15
0x18000cc6f  pop     r14
0x18000cc71  pop     rdi
0x18000cc72  pop     rsi
0x18000cc73  pop     rbp
0x18000cc74  pop     rbx
0x18000cc75  retn
```
