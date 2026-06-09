# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004104`
- end: `0x1800041bf`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `187`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800041d0`

## callees

- `0x180004104`
- `0x1800045dc`
- `0x1800047ac`
- `0x18001c010`

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
    Local = (struct wil::details::ThreadFailureCallbackHolder **)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                                                                   (__int64)a1,
                                                                   0);
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
0x180004104  push    rbx
0x180004106  push    rbp
0x180004107  push    rsi
0x180004108  push    rdi
0x180004109  push    r14
0x18000410b  push    r15
0x18000410d  sub     rsp, 28h
0x180004111  xor     r14b, r14b
0x180004114  mov     byte ptr [rdx], 0
0x180004117  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000411f  mov     r15, r8
0x180004122  mov     rsi, rdx
0x180004125  mov     rdi, rcx
0x180004128  mov     bpl, 1
0x18000412b  jz      short loc_18000418E
0x18000412d  xor     edx, edx
0x18000412f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180004134  mov     rbx, rax
0x180004137  test    rax, rax
0x18000413a  jz      short loc_18000418E
0x18000413c  cmp     qword ptr [rax], 0
0x180004140  jz      short loc_18000418E
0x180004142  mov     [rsi], r14b
0x180004145  mov     r9, r15; unsigned __int64
0x180004148  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x18000414b  mov     r8, rsi; char *
0x18000414e  mov     rcx, rdi; struct wil::FailureInfo *
0x180004151  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004156  test    al, al
0x180004158  jz      short loc_18000415E
0x18000415a  mov     [rdi+48h], rsi
0x18000415e  mov     rbx, [rbx]
0x180004161  mov     al, [rbx+28h]
0x180004164  mov     [rbx+28h], bpl
0x180004168  test    al, al
0x18000416a  jnz     short loc_180004185
0x18000416c  mov     rcx, [rbx+8]
0x180004170  mov     rdx, rdi
0x180004173  mov     rax, [rcx]
0x180004176  mov     rax, [rax]
0x180004179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000417e  or      r14b, al
0x180004181  mov     byte ptr [rbx+28h], 0
0x180004185  mov     rbx, [rbx+10h]
0x180004189  test    rbx, rbx
0x18000418c  jnz     short loc_180004161
0x18000418e  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004195  test    rax, rax
0x180004198  jz      short loc_1800041B2
0x18000419a  test    r14b, r14b
0x18000419d  jnz     short loc_1800041A7
0x18000419f  test    byte ptr [rdi+4], 2
0x1800041a3  jnz     short loc_1800041A7
0x1800041a5  xor     ebp, ebp
0x1800041a7  mov     rdx, rdi
0x1800041aa  mov     cl, bpl
0x1800041ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041b2  add     rsp, 28h
0x1800041b6  pop     r15
0x1800041b8  pop     r14
0x1800041ba  pop     rdi
0x1800041bb  pop     rsi
0x1800041bc  pop     rbp
0x1800041bd  pop     rbx
0x1800041be  retn
```
