# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800089d4`
- end: `0x180008a8e`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008aa0`

## callees

- `0x1800089d4`
- `0x180008eac`
- `0x1800090c0`
- `0x180028010`

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
0x1800089d4  push    rbx
0x1800089d6  push    rbp
0x1800089d7  push    rsi
0x1800089d8  push    rdi
0x1800089d9  push    r14
0x1800089db  push    r15
0x1800089dd  sub     rsp, 28h
0x1800089e1  mov     r15, r8
0x1800089e4  mov     rsi, rdx
0x1800089e7  mov     rdi, rcx
0x1800089ea  mov     byte ptr [rdx], 0
0x1800089ed  xor     r14b, r14b
0x1800089f0  mov     bpl, 1
0x1800089f3  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800089fb  jz      short loc_180008A5C
0x1800089fd  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180008a02  mov     rbx, rax
0x180008a05  test    rax, rax
0x180008a08  jz      short loc_180008A5C
0x180008a0a  cmp     qword ptr [rax], 0
0x180008a0e  jz      short loc_180008A5C
0x180008a10  mov     [rsi], r14b
0x180008a13  mov     r9, r15; unsigned __int64
0x180008a16  mov     r8, rsi; char *
0x180008a19  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180008a1c  mov     rcx, rdi; struct wil::FailureInfo *
0x180008a1f  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180008a24  test    al, al
0x180008a26  jz      short loc_180008A2C
0x180008a28  mov     [rdi+48h], rsi
0x180008a2c  mov     rbx, [rbx]
0x180008a2f  mov     al, [rbx+28h]
0x180008a32  mov     [rbx+28h], bpl
0x180008a36  test    al, al
0x180008a38  jnz     short loc_180008A53
0x180008a3a  mov     rcx, [rbx+8]
0x180008a3e  mov     rax, [rcx]
0x180008a41  mov     rdx, rdi
0x180008a44  mov     rax, [rax]
0x180008a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a4c  or      r14b, al
0x180008a4f  mov     byte ptr [rbx+28h], 0
0x180008a53  mov     rbx, [rbx+10h]
0x180008a57  test    rbx, rbx
0x180008a5a  jnz     short loc_180008A2F
0x180008a5c  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180008a63  test    rax, rax
0x180008a66  jz      short loc_180008A81
0x180008a68  test    r14b, r14b
0x180008a6b  jnz     short loc_180008A75
0x180008a6d  test    byte ptr [rdi+4], 2
0x180008a71  jnz     short loc_180008A75
0x180008a73  xor     ebp, ebp
0x180008a75  mov     rdx, rdi
0x180008a78  mov     cl, bpl
0x180008a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a80  nop
0x180008a81  add     rsp, 28h
0x180008a85  pop     r15
0x180008a87  pop     r14
0x180008a89  pop     rdi
0x180008a8a  pop     rsi
0x180008a8b  pop     rbp
0x180008a8c  pop     rbx
0x180008a8d  retn
```
