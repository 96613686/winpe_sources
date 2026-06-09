# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180011708`
- end: `0x1800117c1`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `185`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800117d0`

## callees

- `0x180011708`
- `0x180011d2c`
- `0x180011eb8`
- `0x180020010`

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
0x180011708  push    rbx
0x18001170a  push    rbp
0x18001170b  push    rsi
0x18001170c  push    rdi
0x18001170d  push    r14
0x18001170f  push    r15
0x180011711  sub     rsp, 28h
0x180011715  xor     r14b, r14b
0x180011718  mov     byte ptr [rdx], 0
0x18001171b  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180011723  mov     r15, r8
0x180011726  mov     rsi, rdx
0x180011729  mov     rdi, rcx
0x18001172c  mov     bpl, 1
0x18001172f  jz      short loc_180011790
0x180011731  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180011736  mov     rbx, rax
0x180011739  test    rax, rax
0x18001173c  jz      short loc_180011790
0x18001173e  cmp     qword ptr [rax], 0
0x180011742  jz      short loc_180011790
0x180011744  mov     [rsi], r14b
0x180011747  mov     r9, r15; unsigned __int64
0x18001174a  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x18001174d  mov     r8, rsi; char *
0x180011750  mov     rcx, rdi; struct wil::FailureInfo *
0x180011753  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180011758  test    al, al
0x18001175a  jz      short loc_180011760
0x18001175c  mov     [rdi+48h], rsi
0x180011760  mov     rbx, [rbx]
0x180011763  mov     al, [rbx+28h]
0x180011766  mov     [rbx+28h], bpl
0x18001176a  test    al, al
0x18001176c  jnz     short loc_180011787
0x18001176e  mov     rcx, [rbx+8]
0x180011772  mov     rdx, rdi
0x180011775  mov     rax, [rcx]
0x180011778  mov     rax, [rax]
0x18001177b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011780  or      r14b, al
0x180011783  mov     byte ptr [rbx+28h], 0
0x180011787  mov     rbx, [rbx+10h]
0x18001178b  test    rbx, rbx
0x18001178e  jnz     short loc_180011763
0x180011790  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180011797  test    rax, rax
0x18001179a  jz      short loc_1800117B4
0x18001179c  test    r14b, r14b
0x18001179f  jnz     short loc_1800117A9
0x1800117a1  test    byte ptr [rdi+4], 2
0x1800117a5  jnz     short loc_1800117A9
0x1800117a7  xor     ebp, ebp
0x1800117a9  mov     rdx, rdi
0x1800117ac  mov     cl, bpl
0x1800117af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117b4  add     rsp, 28h
0x1800117b8  pop     r15
0x1800117ba  pop     r14
0x1800117bc  pop     rdi
0x1800117bd  pop     rsi
0x1800117be  pop     rbp
0x1800117bf  pop     rbx
0x1800117c0  retn
```
