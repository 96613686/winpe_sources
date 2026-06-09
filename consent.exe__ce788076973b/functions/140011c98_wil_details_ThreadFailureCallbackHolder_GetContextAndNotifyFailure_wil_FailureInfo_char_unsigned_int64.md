# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140011c98`
- end: `0x140011d52`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140011d60`

## callees

- `0x140011c98`
- `0x1400120d0`
- `0x140012258`
- `0x14001f010`

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
0x140011c98  push    rbx
0x140011c9a  push    rbp
0x140011c9b  push    rsi
0x140011c9c  push    rdi
0x140011c9d  push    r14
0x140011c9f  push    r15
0x140011ca1  sub     rsp, 28h
0x140011ca5  mov     r15, r8
0x140011ca8  mov     rsi, rdx
0x140011cab  mov     rdi, rcx
0x140011cae  mov     byte ptr [rdx], 0
0x140011cb1  xor     r14b, r14b
0x140011cb4  mov     bpl, 1
0x140011cb7  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140011cbf  jz      short loc_140011D20
0x140011cc1  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x140011cc6  mov     rbx, rax
0x140011cc9  test    rax, rax
0x140011ccc  jz      short loc_140011D20
0x140011cce  cmp     qword ptr [rax], 0
0x140011cd2  jz      short loc_140011D20
0x140011cd4  mov     [rsi], r14b
0x140011cd7  mov     r9, r15; unsigned __int64
0x140011cda  mov     r8, rsi; char *
0x140011cdd  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x140011ce0  mov     rcx, rdi; struct wil::FailureInfo *
0x140011ce3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140011ce8  test    al, al
0x140011cea  jz      short loc_140011CF0
0x140011cec  mov     [rdi+48h], rsi
0x140011cf0  mov     rbx, [rbx]
0x140011cf3  mov     al, [rbx+28h]
0x140011cf6  mov     [rbx+28h], bpl
0x140011cfa  test    al, al
0x140011cfc  jnz     short loc_140011D17
0x140011cfe  mov     rcx, [rbx+8]
0x140011d02  mov     rax, [rcx]
0x140011d05  mov     rdx, rdi
0x140011d08  mov     rax, [rax]
0x140011d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011d10  or      r14b, al
0x140011d13  mov     byte ptr [rbx+28h], 0
0x140011d17  mov     rbx, [rbx+10h]
0x140011d1b  test    rbx, rbx
0x140011d1e  jnz     short loc_140011CF3
0x140011d20  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140011d27  test    rax, rax
0x140011d2a  jz      short loc_140011D45
0x140011d2c  test    r14b, r14b
0x140011d2f  jnz     short loc_140011D39
0x140011d31  test    byte ptr [rdi+4], 2
0x140011d35  jnz     short loc_140011D39
0x140011d37  xor     ebp, ebp
0x140011d39  mov     rdx, rdi
0x140011d3c  mov     cl, bpl
0x140011d3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011d44  nop
0x140011d45  add     rsp, 28h
0x140011d49  pop     r15
0x140011d4b  pop     r14
0x140011d4d  pop     rdi
0x140011d4e  pop     rsi
0x140011d4f  pop     rbp
0x140011d50  pop     rbx
0x140011d51  retn
```
