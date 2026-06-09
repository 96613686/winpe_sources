# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1400034d8`
- end: `0x140003591`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `185`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400035a0`

## callees

- `0x1400034d8`
- `0x1400039ac`
- `0x140003b34`
- `0x140006010`

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
0x1400034d8  push    rbx
0x1400034da  push    rbp
0x1400034db  push    rsi
0x1400034dc  push    rdi
0x1400034dd  push    r14
0x1400034df  push    r15
0x1400034e1  sub     rsp, 28h
0x1400034e5  xor     r14b, r14b
0x1400034e8  mov     byte ptr [rdx], 0
0x1400034eb  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400034f3  mov     r15, r8
0x1400034f6  mov     rsi, rdx
0x1400034f9  mov     rdi, rcx
0x1400034fc  mov     bpl, 1
0x1400034ff  jz      short loc_140003560
0x140003501  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x140003506  mov     rbx, rax
0x140003509  test    rax, rax
0x14000350c  jz      short loc_140003560
0x14000350e  cmp     qword ptr [rax], 0
0x140003512  jz      short loc_140003560
0x140003514  mov     [rsi], r14b
0x140003517  mov     r9, r15; unsigned __int64
0x14000351a  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x14000351d  mov     r8, rsi; char *
0x140003520  mov     rcx, rdi; struct wil::FailureInfo *
0x140003523  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140003528  test    al, al
0x14000352a  jz      short loc_140003530
0x14000352c  mov     [rdi+48h], rsi
0x140003530  mov     rbx, [rbx]
0x140003533  mov     al, [rbx+28h]
0x140003536  mov     [rbx+28h], bpl
0x14000353a  test    al, al
0x14000353c  jnz     short loc_140003557
0x14000353e  mov     rcx, [rbx+8]
0x140003542  mov     rdx, rdi
0x140003545  mov     rax, [rcx]
0x140003548  mov     rax, [rax]
0x14000354b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003550  or      r14b, al
0x140003553  mov     byte ptr [rbx+28h], 0
0x140003557  mov     rbx, [rbx+10h]
0x14000355b  test    rbx, rbx
0x14000355e  jnz     short loc_140003533
0x140003560  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140003567  test    rax, rax
0x14000356a  jz      short loc_140003584
0x14000356c  test    r14b, r14b
0x14000356f  jnz     short loc_140003579
0x140003571  test    byte ptr [rdi+4], 2
0x140003575  jnz     short loc_140003579
0x140003577  xor     ebp, ebp
0x140003579  mov     rdx, rdi
0x14000357c  mov     cl, bpl
0x14000357f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003584  add     rsp, 28h
0x140003588  pop     r15
0x14000358a  pop     r14
0x14000358c  pop     rdi
0x14000358d  pop     rsi
0x14000358e  pop     rbp
0x14000358f  pop     rbx
0x140003590  retn
```
