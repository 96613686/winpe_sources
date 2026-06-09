# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180005694`
- end: `0x18000574d`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `185`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005760`

## callees

- `0x180005694`
- `0x180005ad0`
- `0x180005cb4`
- `0x18000a010`

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
0x180005694  push    rbx
0x180005696  push    rbp
0x180005697  push    rsi
0x180005698  push    rdi
0x180005699  push    r14
0x18000569b  push    r15
0x18000569d  sub     rsp, 28h
0x1800056a1  xor     r14b, r14b
0x1800056a4  mov     byte ptr [rdx], 0
0x1800056a7  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800056af  mov     r15, r8
0x1800056b2  mov     rsi, rdx
0x1800056b5  mov     rdi, rcx
0x1800056b8  mov     bpl, 1
0x1800056bb  jz      short loc_18000571C
0x1800056bd  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800056c2  mov     rbx, rax
0x1800056c5  test    rax, rax
0x1800056c8  jz      short loc_18000571C
0x1800056ca  cmp     qword ptr [rax], 0
0x1800056ce  jz      short loc_18000571C
0x1800056d0  mov     [rsi], r14b
0x1800056d3  mov     r9, r15; unsigned __int64
0x1800056d6  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x1800056d9  mov     r8, rsi; char *
0x1800056dc  mov     rcx, rdi; struct wil::FailureInfo *
0x1800056df  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800056e4  test    al, al
0x1800056e6  jz      short loc_1800056EC
0x1800056e8  mov     [rdi+48h], rsi
0x1800056ec  mov     rbx, [rbx]
0x1800056ef  mov     al, [rbx+28h]
0x1800056f2  mov     [rbx+28h], bpl
0x1800056f6  test    al, al
0x1800056f8  jnz     short loc_180005713
0x1800056fa  mov     rcx, [rbx+8]
0x1800056fe  mov     rdx, rdi
0x180005701  mov     rax, [rcx]
0x180005704  mov     rax, [rax]
0x180005707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000570c  or      r14b, al
0x18000570f  mov     byte ptr [rbx+28h], 0
0x180005713  mov     rbx, [rbx+10h]
0x180005717  test    rbx, rbx
0x18000571a  jnz     short loc_1800056EF
0x18000571c  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180005723  test    rax, rax
0x180005726  jz      short loc_180005740
0x180005728  test    r14b, r14b
0x18000572b  jnz     short loc_180005735
0x18000572d  test    byte ptr [rdi+4], 2
0x180005731  jnz     short loc_180005735
0x180005733  xor     ebp, ebp
0x180005735  mov     rdx, rdi
0x180005738  mov     cl, bpl
0x18000573b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005740  add     rsp, 28h
0x180005744  pop     r15
0x180005746  pop     r14
0x180005748  pop     rdi
0x180005749  pop     rsi
0x18000574a  pop     rbp
0x18000574b  pop     rbx
0x18000574c  retn
```
