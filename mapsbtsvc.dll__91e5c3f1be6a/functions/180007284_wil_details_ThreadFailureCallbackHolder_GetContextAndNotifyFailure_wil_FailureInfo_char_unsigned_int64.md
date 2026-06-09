# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180007284`
- end: `0x18000733e`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007350`

## callees

- `0x180007284`
- `0x18000775c`
- `0x1800078e4`
- `0x180015010`

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
0x180007284  push    rbx
0x180007286  push    rbp
0x180007287  push    rsi
0x180007288  push    rdi
0x180007289  push    r14
0x18000728b  push    r15
0x18000728d  sub     rsp, 28h
0x180007291  mov     r15, r8
0x180007294  mov     rsi, rdx
0x180007297  mov     rdi, rcx
0x18000729a  mov     byte ptr [rdx], 0
0x18000729d  xor     r14b, r14b
0x1800072a0  mov     bpl, 1
0x1800072a3  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800072ab  jz      short loc_18000730C
0x1800072ad  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800072b2  mov     rbx, rax
0x1800072b5  test    rax, rax
0x1800072b8  jz      short loc_18000730C
0x1800072ba  cmp     qword ptr [rax], 0
0x1800072be  jz      short loc_18000730C
0x1800072c0  mov     [rsi], r14b
0x1800072c3  mov     r9, r15; unsigned __int64
0x1800072c6  mov     r8, rsi; char *
0x1800072c9  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x1800072cc  mov     rcx, rdi; struct wil::FailureInfo *
0x1800072cf  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800072d4  test    al, al
0x1800072d6  jz      short loc_1800072DC
0x1800072d8  mov     [rdi+48h], rsi
0x1800072dc  mov     rbx, [rbx]
0x1800072df  mov     al, [rbx+28h]
0x1800072e2  mov     [rbx+28h], bpl
0x1800072e6  test    al, al
0x1800072e8  jnz     short loc_180007303
0x1800072ea  mov     rcx, [rbx+8]
0x1800072ee  mov     rax, [rcx]
0x1800072f1  mov     rdx, rdi
0x1800072f4  mov     rax, [rax]
0x1800072f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072fc  or      r14b, al
0x1800072ff  mov     byte ptr [rbx+28h], 0
0x180007303  mov     rbx, [rbx+10h]
0x180007307  test    rbx, rbx
0x18000730a  jnz     short loc_1800072DF
0x18000730c  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180007313  test    rax, rax
0x180007316  jz      short loc_180007331
0x180007318  test    r14b, r14b
0x18000731b  jnz     short loc_180007325
0x18000731d  test    byte ptr [rdi+4], 2
0x180007321  jnz     short loc_180007325
0x180007323  xor     ebp, ebp
0x180007325  mov     rdx, rdi
0x180007328  mov     cl, bpl
0x18000732b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007330  nop
0x180007331  add     rsp, 28h
0x180007335  pop     r15
0x180007337  pop     r14
0x180007339  pop     rdi
0x18000733a  pop     rsi
0x18000733b  pop     rbp
0x18000733c  pop     rbx
0x18000733d  retn
```
