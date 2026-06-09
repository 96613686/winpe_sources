# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800054b4`
- end: `0x180005570`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `188`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005580`

## callees

- `0x1800054b4`
- `0x1800059fc`
- `0x180005c10`
- `0x180012010`

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
    Local = (struct wil::details::ThreadFailureCallbackHolder **)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                                                                   a1,
                                                                   0);
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
0x1800054b4  push    rbx
0x1800054b6  push    rbp
0x1800054b7  push    rsi
0x1800054b8  push    rdi
0x1800054b9  push    r14
0x1800054bb  push    r15
0x1800054bd  sub     rsp, 28h
0x1800054c1  mov     r15, r8
0x1800054c4  mov     rsi, rdx
0x1800054c7  mov     rdi, rcx
0x1800054ca  mov     byte ptr [rdx], 0
0x1800054cd  xor     r14b, r14b
0x1800054d0  mov     bpl, 1
0x1800054d3  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800054db  jz      short loc_18000553E
0x1800054dd  xor     edx, edx
0x1800054df  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800054e4  mov     rbx, rax
0x1800054e7  test    rax, rax
0x1800054ea  jz      short loc_18000553E
0x1800054ec  cmp     qword ptr [rax], 0
0x1800054f0  jz      short loc_18000553E
0x1800054f2  mov     [rsi], r14b
0x1800054f5  mov     r9, r15; unsigned __int64
0x1800054f8  mov     r8, rsi; char *
0x1800054fb  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x1800054fe  mov     rcx, rdi; struct wil::FailureInfo *
0x180005501  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005506  test    al, al
0x180005508  jz      short loc_18000550E
0x18000550a  mov     [rdi+48h], rsi
0x18000550e  mov     rbx, [rbx]
0x180005511  mov     al, [rbx+28h]
0x180005514  mov     [rbx+28h], bpl
0x180005518  test    al, al
0x18000551a  jnz     short loc_180005535
0x18000551c  mov     rcx, [rbx+8]
0x180005520  mov     rax, [rcx]
0x180005523  mov     rdx, rdi
0x180005526  mov     rax, [rax]
0x180005529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000552e  or      r14b, al
0x180005531  mov     byte ptr [rbx+28h], 0
0x180005535  mov     rbx, [rbx+10h]
0x180005539  test    rbx, rbx
0x18000553c  jnz     short loc_180005511
0x18000553e  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180005545  test    rax, rax
0x180005548  jz      short loc_180005563
0x18000554a  test    r14b, r14b
0x18000554d  jnz     short loc_180005557
0x18000554f  test    byte ptr [rdi+4], 2
0x180005553  jnz     short loc_180005557
0x180005555  xor     ebp, ebp
0x180005557  mov     rdx, rdi
0x18000555a  mov     cl, bpl
0x18000555d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005562  nop
0x180005563  add     rsp, 28h
0x180005567  pop     r15
0x180005569  pop     r14
0x18000556b  pop     rdi
0x18000556c  pop     rsi
0x18000556d  pop     rbp
0x18000556e  pop     rbx
0x18000556f  retn
```
