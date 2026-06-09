# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180006bd4`
- end: `0x180006c8e`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006ca0`

## callees

- `0x180006bd4`
- `0x180007010`
- `0x1800071cc`
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
0x180006bd4  push    rbx
0x180006bd6  push    rbp
0x180006bd7  push    rsi
0x180006bd8  push    rdi
0x180006bd9  push    r14
0x180006bdb  push    r15
0x180006bdd  sub     rsp, 28h
0x180006be1  mov     r15, r8
0x180006be4  mov     rsi, rdx
0x180006be7  mov     rdi, rcx
0x180006bea  mov     byte ptr [rdx], 0
0x180006bed  xor     r14b, r14b
0x180006bf0  mov     bpl, 1
0x180006bf3  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006bfb  jz      short loc_180006C5C
0x180006bfd  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180006c02  mov     rbx, rax
0x180006c05  test    rax, rax
0x180006c08  jz      short loc_180006C5C
0x180006c0a  cmp     qword ptr [rax], 0
0x180006c0e  jz      short loc_180006C5C
0x180006c10  mov     [rsi], r14b
0x180006c13  mov     r9, r15; unsigned __int64
0x180006c16  mov     r8, rsi; char *
0x180006c19  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180006c1c  mov     rcx, rdi; struct wil::FailureInfo *
0x180006c1f  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006c24  test    al, al
0x180006c26  jz      short loc_180006C2C
0x180006c28  mov     [rdi+48h], rsi
0x180006c2c  mov     rbx, [rbx]
0x180006c2f  mov     al, [rbx+28h]
0x180006c32  mov     [rbx+28h], bpl
0x180006c36  test    al, al
0x180006c38  jnz     short loc_180006C53
0x180006c3a  mov     rcx, [rbx+8]
0x180006c3e  mov     rax, [rcx]
0x180006c41  mov     rdx, rdi
0x180006c44  mov     rax, [rax]
0x180006c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c4c  or      r14b, al
0x180006c4f  mov     byte ptr [rbx+28h], 0
0x180006c53  mov     rbx, [rbx+10h]
0x180006c57  test    rbx, rbx
0x180006c5a  jnz     short loc_180006C2F
0x180006c5c  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180006c63  test    rax, rax
0x180006c66  jz      short loc_180006C81
0x180006c68  test    r14b, r14b
0x180006c6b  jnz     short loc_180006C75
0x180006c6d  test    byte ptr [rdi+4], 2
0x180006c71  jnz     short loc_180006C75
0x180006c73  xor     ebp, ebp
0x180006c75  mov     rdx, rdi
0x180006c78  mov     cl, bpl
0x180006c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c80  nop
0x180006c81  add     rsp, 28h
0x180006c85  pop     r15
0x180006c87  pop     r14
0x180006c89  pop     rdi
0x180006c8a  pop     rsi
0x180006c8b  pop     rbp
0x180006c8c  pop     rbx
0x180006c8d  retn
```
