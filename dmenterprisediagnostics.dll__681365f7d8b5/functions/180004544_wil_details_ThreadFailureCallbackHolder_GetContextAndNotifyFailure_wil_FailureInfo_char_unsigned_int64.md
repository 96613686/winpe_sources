# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004544`
- end: `0x1800045ff`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `187`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004610`

## callees

- `0x180004544`
- `0x180004a44`
- `0x180004be0`
- `0x180027010`

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
0x180004544  push    rbx
0x180004546  push    rbp
0x180004547  push    rsi
0x180004548  push    rdi
0x180004549  push    r14
0x18000454b  push    r15
0x18000454d  sub     rsp, 28h
0x180004551  mov     r15, r8
0x180004554  mov     rsi, rdx
0x180004557  mov     rdi, rcx
0x18000455a  mov     byte ptr [rdx], 0
0x18000455d  xor     r14b, r14b
0x180004560  mov     bpl, 1
0x180004563  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000456b  jz      short loc_1800045CC
0x18000456d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180004572  mov     rbx, rax
0x180004575  test    rax, rax
0x180004578  jz      short loc_1800045CC
0x18000457a  cmp     qword ptr [rax], 0
0x18000457e  jz      short loc_1800045CC
0x180004580  mov     [rsi], r14b
0x180004583  mov     r9, r15; unsigned __int64
0x180004586  mov     r8, rsi; char *
0x180004589  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x18000458c  mov     rcx, rdi; struct wil::FailureInfo *
0x18000458f  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004594  test    al, al
0x180004596  jz      short loc_18000459C
0x180004598  mov     [rdi+48h], rsi
0x18000459c  mov     rbx, [rbx]
0x18000459f  mov     al, [rbx+28h]
0x1800045a2  mov     [rbx+28h], bpl
0x1800045a6  test    al, al
0x1800045a8  jnz     short loc_1800045C3
0x1800045aa  mov     rcx, [rbx+8]
0x1800045ae  mov     rax, [rcx]
0x1800045b1  mov     rdx, rdi
0x1800045b4  mov     rax, [rax]
0x1800045b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045bc  or      r14b, al
0x1800045bf  mov     byte ptr [rbx+28h], 0
0x1800045c3  mov     rbx, [rbx+10h]
0x1800045c7  test    rbx, rbx
0x1800045ca  jnz     short loc_18000459F
0x1800045cc  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800045d3  test    rax, rax
0x1800045d6  jz      short loc_1800045F1
0x1800045d8  test    r14b, r14b
0x1800045db  jnz     short loc_1800045E5
0x1800045dd  test    byte ptr [rdi+4], 2
0x1800045e1  jnz     short loc_1800045E5
0x1800045e3  xor     ebp, ebp
0x1800045e5  mov     rdx, rdi
0x1800045e8  mov     cl, bpl
0x1800045eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045f0  nop
0x1800045f1  add     rsp, 28h
0x1800045f5  pop     r15
0x1800045f7  pop     r14
0x1800045f9  pop     rdi
0x1800045fa  pop     rsi
0x1800045fb  pop     rbp
0x1800045fc  pop     rbx
0x1800045fd  retn
```
