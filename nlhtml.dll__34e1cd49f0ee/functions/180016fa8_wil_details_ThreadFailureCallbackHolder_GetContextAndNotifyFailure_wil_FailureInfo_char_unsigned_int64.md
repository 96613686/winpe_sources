# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180016fa8`
- end: `0x180017062`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180017070`

## callees

- `0x180016fa8`
- `0x1800173e0`
- `0x1800175f4`
- `0x180025010`

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
0x180016fa8  push    rbx
0x180016faa  push    rbp
0x180016fab  push    rsi
0x180016fac  push    rdi
0x180016fad  push    r14
0x180016faf  push    r15
0x180016fb1  sub     rsp, 28h
0x180016fb5  mov     r15, r8
0x180016fb8  mov     rsi, rdx
0x180016fbb  mov     rdi, rcx
0x180016fbe  mov     byte ptr [rdx], 0
0x180016fc1  xor     r14b, r14b
0x180016fc4  mov     bpl, 1
0x180016fc7  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180016fcf  jz      short loc_180017030
0x180016fd1  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180016fd6  mov     rbx, rax
0x180016fd9  test    rax, rax
0x180016fdc  jz      short loc_180017030
0x180016fde  cmp     qword ptr [rax], 0
0x180016fe2  jz      short loc_180017030
0x180016fe4  mov     [rsi], r14b
0x180016fe7  mov     r9, r15; unsigned __int64
0x180016fea  mov     r8, rsi; char *
0x180016fed  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180016ff0  mov     rcx, rdi; struct wil::FailureInfo *
0x180016ff3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180016ff8  test    al, al
0x180016ffa  jz      short loc_180017000
0x180016ffc  mov     [rdi+48h], rsi
0x180017000  mov     rbx, [rbx]
0x180017003  mov     al, [rbx+28h]
0x180017006  mov     [rbx+28h], bpl
0x18001700a  test    al, al
0x18001700c  jnz     short loc_180017027
0x18001700e  mov     rcx, [rbx+8]
0x180017012  mov     rax, [rcx]
0x180017015  mov     rdx, rdi
0x180017018  mov     rax, [rax]
0x18001701b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017020  or      r14b, al
0x180017023  mov     byte ptr [rbx+28h], 0
0x180017027  mov     rbx, [rbx+10h]
0x18001702b  test    rbx, rbx
0x18001702e  jnz     short loc_180017003
0x180017030  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180017037  test    rax, rax
0x18001703a  jz      short loc_180017055
0x18001703c  test    r14b, r14b
0x18001703f  jnz     short loc_180017049
0x180017041  test    byte ptr [rdi+4], 2
0x180017045  jnz     short loc_180017049
0x180017047  xor     ebp, ebp
0x180017049  mov     rdx, rdi
0x18001704c  mov     cl, bpl
0x18001704f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017054  nop
0x180017055  add     rsp, 28h
0x180017059  pop     r15
0x18001705b  pop     r14
0x18001705d  pop     rdi
0x18001705e  pop     rsi
0x18001705f  pop     rbp
0x180017060  pop     rbx
0x180017061  retn
```
