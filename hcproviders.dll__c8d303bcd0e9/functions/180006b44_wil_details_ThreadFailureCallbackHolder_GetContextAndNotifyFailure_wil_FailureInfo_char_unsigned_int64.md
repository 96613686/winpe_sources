# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180006b44`
- end: `0x180006bfe`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006c10`

## callees

- `0x180006b44`
- `0x180006fa0`
- `0x18000713c`
- `0x18000b010`

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
0x180006b44  push    rbx
0x180006b46  push    rbp
0x180006b47  push    rsi
0x180006b48  push    rdi
0x180006b49  push    r14
0x180006b4b  push    r15
0x180006b4d  sub     rsp, 28h
0x180006b51  xor     r14b, r14b
0x180006b54  mov     byte ptr [rdx], 0
0x180006b57  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006b5f  mov     r15, r8
0x180006b62  mov     rsi, rdx
0x180006b65  mov     rdi, rcx
0x180006b68  mov     bpl, 1
0x180006b6b  jz      short loc_180006BCC
0x180006b6d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180006b72  mov     rbx, rax
0x180006b75  test    rax, rax
0x180006b78  jz      short loc_180006BCC
0x180006b7a  cmp     qword ptr [rax], 0
0x180006b7e  jz      short loc_180006BCC
0x180006b80  mov     [rsi], r14b
0x180006b83  mov     r9, r15; unsigned __int64
0x180006b86  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180006b89  mov     r8, rsi; char *
0x180006b8c  mov     rcx, rdi; struct wil::FailureInfo *
0x180006b8f  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006b94  test    al, al
0x180006b96  jz      short loc_180006B9C
0x180006b98  mov     [rdi+48h], rsi
0x180006b9c  mov     rbx, [rbx]
0x180006b9f  mov     al, [rbx+28h]
0x180006ba2  mov     [rbx+28h], bpl
0x180006ba6  test    al, al
0x180006ba8  jnz     short loc_180006BC3
0x180006baa  mov     rcx, [rbx+8]
0x180006bae  mov     rdx, rdi
0x180006bb1  mov     rax, [rcx]
0x180006bb4  mov     rax, [rax]
0x180006bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bbc  or      r14b, al
0x180006bbf  mov     byte ptr [rbx+28h], 0
0x180006bc3  mov     rbx, [rbx+10h]
0x180006bc7  test    rbx, rbx
0x180006bca  jnz     short loc_180006B9F
0x180006bcc  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180006bd3  test    rax, rax
0x180006bd6  jz      short loc_180006BF0
0x180006bd8  test    r14b, r14b
0x180006bdb  jnz     short loc_180006BE5
0x180006bdd  test    byte ptr [rdi+4], 2
0x180006be1  jnz     short loc_180006BE5
0x180006be3  xor     ebp, ebp
0x180006be5  mov     rdx, rdi
0x180006be8  mov     cl, bpl
0x180006beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bf0  add     rsp, 28h
0x180006bf4  pop     r15
0x180006bf6  pop     r14
0x180006bf8  pop     rdi
0x180006bf9  pop     rsi
0x180006bfa  pop     rbp
0x180006bfb  pop     rbx
0x180006bfc  retn
```
