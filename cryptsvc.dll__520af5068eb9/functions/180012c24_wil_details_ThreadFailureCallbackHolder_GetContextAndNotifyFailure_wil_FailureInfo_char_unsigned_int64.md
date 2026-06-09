# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180012c24`
- end: `0x180012cdd`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `185`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180012cf0`

## callees

- `0x180012c24`
- `0x18001327c`
- `0x18001345c`
- `0x180018010`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(
        struct wil::FailureInfo *a1,
        char *a2,
        unsigned __int64 a3)
{
  char v3; // r14
  struct wil::FailureInfo *v6; // rdi
  char v7; // bp
  struct wil::details::ThreadFailureCallbackHolder **Local; // rax
  struct wil::details::ThreadFailureCallbackHolder **v9; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v10; // rbx
  char v11; // al

  v3 = 0;
  *a2 = 0;
  v6 = a1;
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
        if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(v6, *Local, a2, a3) )
          *((_QWORD *)v6 + 9) = a2;
        v10 = *v9;
        do
        {
          v11 = *((_BYTE *)v10 + 40);
          *((_BYTE *)v10 + 40) = 1;
          if ( !v11 )
          {
            v3 |= (***((__int64 (__fastcall ****)(_QWORD, struct wil::FailureInfo *))v10 + 1))(*((_QWORD *)v10 + 1), v6);
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
    if ( !v3 && (*((_BYTE *)v6 + 4) & 2) == 0 )
      v7 = 0;
    LOBYTE(a1) = v7;
    wil::details::g_pfnTelemetryCallback(a1, v6);
  }
}

```

## disassembly

```asm
0x180012c24  push    rbx
0x180012c26  push    rbp
0x180012c27  push    rsi
0x180012c28  push    rdi
0x180012c29  push    r14
0x180012c2b  push    r15
0x180012c2d  sub     rsp, 28h
0x180012c31  xor     r14b, r14b
0x180012c34  mov     byte ptr [rdx], 0
0x180012c37  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180012c3f  mov     r15, r8
0x180012c42  mov     rsi, rdx
0x180012c45  mov     rdi, rcx
0x180012c48  mov     bpl, 1
0x180012c4b  jz      short loc_180012CAC
0x180012c4d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180012c52  mov     rbx, rax
0x180012c55  test    rax, rax
0x180012c58  jz      short loc_180012CAC
0x180012c5a  cmp     qword ptr [rax], 0
0x180012c5e  jz      short loc_180012CAC
0x180012c60  mov     [rsi], r14b
0x180012c63  mov     r9, r15; unsigned __int64
0x180012c66  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180012c69  mov     r8, rsi; char *
0x180012c6c  mov     rcx, rdi; struct wil::FailureInfo *
0x180012c6f  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180012c74  test    al, al
0x180012c76  jz      short loc_180012C7C
0x180012c78  mov     [rdi+48h], rsi
0x180012c7c  mov     rbx, [rbx]
0x180012c7f  mov     al, [rbx+28h]
0x180012c82  mov     [rbx+28h], bpl
0x180012c86  test    al, al
0x180012c88  jnz     short loc_180012CA3
0x180012c8a  mov     rcx, [rbx+8]
0x180012c8e  mov     rdx, rdi
0x180012c91  mov     rax, [rcx]
0x180012c94  mov     rax, [rax]
0x180012c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c9c  or      r14b, al
0x180012c9f  mov     byte ptr [rbx+28h], 0
0x180012ca3  mov     rbx, [rbx+10h]
0x180012ca7  test    rbx, rbx
0x180012caa  jnz     short loc_180012C7F
0x180012cac  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180012cb3  test    rax, rax
0x180012cb6  jz      short loc_180012CD0
0x180012cb8  test    r14b, r14b
0x180012cbb  jnz     short loc_180012CC5
0x180012cbd  test    byte ptr [rdi+4], 2
0x180012cc1  jnz     short loc_180012CC5
0x180012cc3  xor     ebp, ebp
0x180012cc5  mov     rdx, rdi
0x180012cc8  mov     cl, bpl
0x180012ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cd0  add     rsp, 28h
0x180012cd4  pop     r15
0x180012cd6  pop     r14
0x180012cd8  pop     rdi
0x180012cd9  pop     rsi
0x180012cda  pop     rbp
0x180012cdb  pop     rbx
0x180012cdc  retn
```
