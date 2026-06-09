# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180003e34`
- end: `0x180003eee`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003f00`

## callees

- `0x180003e34`
- `0x18000430c`
- `0x180004464`
- `0x18000a010`

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
0x180003e34  push    rbx
0x180003e36  push    rbp
0x180003e37  push    rsi
0x180003e38  push    rdi
0x180003e39  push    r14
0x180003e3b  push    r15
0x180003e3d  sub     rsp, 28h
0x180003e41  mov     r15, r8
0x180003e44  mov     rsi, rdx
0x180003e47  mov     rdi, rcx
0x180003e4a  mov     byte ptr [rdx], 0
0x180003e4d  xor     r14b, r14b
0x180003e50  mov     bpl, 1
0x180003e53  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180003e5b  jz      short loc_180003EBC
0x180003e5d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180003e62  mov     rbx, rax
0x180003e65  test    rax, rax
0x180003e68  jz      short loc_180003EBC
0x180003e6a  cmp     qword ptr [rax], 0
0x180003e6e  jz      short loc_180003EBC
0x180003e70  mov     [rsi], r14b
0x180003e73  mov     r9, r15; unsigned __int64
0x180003e76  mov     r8, rsi; char *
0x180003e79  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180003e7c  mov     rcx, rdi; struct wil::FailureInfo *
0x180003e7f  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003e84  test    al, al
0x180003e86  jz      short loc_180003E8C
0x180003e88  mov     [rdi+48h], rsi
0x180003e8c  mov     rbx, [rbx]
0x180003e8f  mov     al, [rbx+28h]
0x180003e92  mov     [rbx+28h], bpl
0x180003e96  test    al, al
0x180003e98  jnz     short loc_180003EB3
0x180003e9a  mov     rcx, [rbx+8]
0x180003e9e  mov     rax, [rcx]
0x180003ea1  mov     rdx, rdi
0x180003ea4  mov     rax, [rax]
0x180003ea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eac  or      r14b, al
0x180003eaf  mov     byte ptr [rbx+28h], 0
0x180003eb3  mov     rbx, [rbx+10h]
0x180003eb7  test    rbx, rbx
0x180003eba  jnz     short loc_180003E8F
0x180003ebc  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180003ec3  test    rax, rax
0x180003ec6  jz      short loc_180003EE1
0x180003ec8  test    r14b, r14b
0x180003ecb  jnz     short loc_180003ED5
0x180003ecd  test    byte ptr [rdi+4], 2
0x180003ed1  jnz     short loc_180003ED5
0x180003ed3  xor     ebp, ebp
0x180003ed5  mov     rdx, rdi
0x180003ed8  mov     cl, bpl
0x180003edb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ee0  nop
0x180003ee1  add     rsp, 28h
0x180003ee5  pop     r15
0x180003ee7  pop     r14
0x180003ee9  pop     rdi
0x180003eea  pop     rsi
0x180003eeb  pop     rbp
0x180003eec  pop     rbx
0x180003eed  retn
```
