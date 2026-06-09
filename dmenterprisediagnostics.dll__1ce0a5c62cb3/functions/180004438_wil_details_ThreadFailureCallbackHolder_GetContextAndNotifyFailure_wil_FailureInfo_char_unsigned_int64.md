# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004438`
- end: `0x1800044f2`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004500`

## callees

- `0x180004438`
- `0x18000490c`
- `0x180004a94`
- `0x180026010`

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
0x180004438  push    rbx
0x18000443a  push    rbp
0x18000443b  push    rsi
0x18000443c  push    rdi
0x18000443d  push    r14
0x18000443f  push    r15
0x180004441  sub     rsp, 28h
0x180004445  mov     r15, r8
0x180004448  mov     rsi, rdx
0x18000444b  mov     rdi, rcx
0x18000444e  mov     byte ptr [rdx], 0
0x180004451  xor     r14b, r14b
0x180004454  mov     bpl, 1
0x180004457  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000445f  jz      short loc_1800044C0
0x180004461  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180004466  mov     rbx, rax
0x180004469  test    rax, rax
0x18000446c  jz      short loc_1800044C0
0x18000446e  cmp     qword ptr [rax], 0
0x180004472  jz      short loc_1800044C0
0x180004474  mov     [rsi], r14b
0x180004477  mov     r9, r15; unsigned __int64
0x18000447a  mov     r8, rsi; char *
0x18000447d  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180004480  mov     rcx, rdi; struct wil::FailureInfo *
0x180004483  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004488  test    al, al
0x18000448a  jz      short loc_180004490
0x18000448c  mov     [rdi+48h], rsi
0x180004490  mov     rbx, [rbx]
0x180004493  mov     al, [rbx+28h]
0x180004496  mov     [rbx+28h], bpl
0x18000449a  test    al, al
0x18000449c  jnz     short loc_1800044B7
0x18000449e  mov     rcx, [rbx+8]
0x1800044a2  mov     rax, [rcx]
0x1800044a5  mov     rdx, rdi
0x1800044a8  mov     rax, [rax]
0x1800044ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044b0  or      r14b, al
0x1800044b3  mov     byte ptr [rbx+28h], 0
0x1800044b7  mov     rbx, [rbx+10h]
0x1800044bb  test    rbx, rbx
0x1800044be  jnz     short loc_180004493
0x1800044c0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800044c7  test    rax, rax
0x1800044ca  jz      short loc_1800044E5
0x1800044cc  test    r14b, r14b
0x1800044cf  jnz     short loc_1800044D9
0x1800044d1  test    byte ptr [rdi+4], 2
0x1800044d5  jnz     short loc_1800044D9
0x1800044d7  xor     ebp, ebp
0x1800044d9  mov     rdx, rdi
0x1800044dc  mov     cl, bpl
0x1800044df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044e4  nop
0x1800044e5  add     rsp, 28h
0x1800044e9  pop     r15
0x1800044eb  pop     r14
0x1800044ed  pop     rdi
0x1800044ee  pop     rsi
0x1800044ef  pop     rbp
0x1800044f0  pop     rbx
0x1800044f1  retn
```
