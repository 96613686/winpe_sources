# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000635c`
- end: `0x180006415`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `185`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800062f0`

## callees

- `0x18000635c`
- `0x1800085b0`
- `0x18000f168`
- `0x180017010`

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
0x18000635c  push    rbx
0x18000635e  push    rbp
0x18000635f  push    rsi
0x180006360  push    rdi
0x180006361  push    r14
0x180006363  push    r15
0x180006365  sub     rsp, 28h
0x180006369  xor     r14b, r14b
0x18000636c  mov     byte ptr [rdx], 0
0x18000636f  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006377  mov     r15, r8
0x18000637a  mov     rsi, rdx
0x18000637d  mov     rdi, rcx
0x180006380  mov     bpl, 1
0x180006383  jz      short loc_1800063E4
0x180006385  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000638a  mov     rbx, rax
0x18000638d  test    rax, rax
0x180006390  jz      short loc_1800063E4
0x180006392  cmp     qword ptr [rax], 0
0x180006396  jz      short loc_1800063E4
0x180006398  mov     [rsi], r14b
0x18000639b  mov     r9, r15; unsigned __int64
0x18000639e  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x1800063a1  mov     r8, rsi; char *
0x1800063a4  mov     rcx, rdi; struct wil::FailureInfo *
0x1800063a7  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800063ac  test    al, al
0x1800063ae  jz      short loc_1800063B4
0x1800063b0  mov     [rdi+48h], rsi
0x1800063b4  mov     rbx, [rbx]
0x1800063b7  mov     al, [rbx+28h]
0x1800063ba  mov     [rbx+28h], bpl
0x1800063be  test    al, al
0x1800063c0  jnz     short loc_1800063DB
0x1800063c2  mov     rcx, [rbx+8]
0x1800063c6  mov     rdx, rdi
0x1800063c9  mov     rax, [rcx]
0x1800063cc  mov     rax, [rax]
0x1800063cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063d4  or      r14b, al
0x1800063d7  mov     byte ptr [rbx+28h], 0
0x1800063db  mov     rbx, [rbx+10h]
0x1800063df  test    rbx, rbx
0x1800063e2  jnz     short loc_1800063B7
0x1800063e4  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800063eb  test    rax, rax
0x1800063ee  jz      short loc_180006408
0x1800063f0  test    r14b, r14b
0x1800063f3  jnz     short loc_1800063FD
0x1800063f5  test    byte ptr [rdi+4], 2
0x1800063f9  jnz     short loc_1800063FD
0x1800063fb  xor     ebp, ebp
0x1800063fd  mov     rdx, rdi
0x180006400  mov     cl, bpl
0x180006403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006408  add     rsp, 28h
0x18000640c  pop     r15
0x18000640e  pop     r14
0x180006410  pop     rdi
0x180006411  pop     rsi
0x180006412  pop     rbp
0x180006413  pop     rbx
0x180006414  retn
```
