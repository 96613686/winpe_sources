# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004234`
- end: `0x1800042ef`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `187`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004300`

## callees

- `0x180004234`
- `0x180004734`
- `0x1800048d0`
- `0x18001a010`

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
0x180004234  push    rbx
0x180004236  push    rbp
0x180004237  push    rsi
0x180004238  push    rdi
0x180004239  push    r14
0x18000423b  push    r15
0x18000423d  sub     rsp, 28h
0x180004241  mov     r15, r8
0x180004244  mov     rsi, rdx
0x180004247  mov     rdi, rcx
0x18000424a  mov     byte ptr [rdx], 0
0x18000424d  xor     r14b, r14b
0x180004250  mov     bpl, 1
0x180004253  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000425b  jz      short loc_1800042BC
0x18000425d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180004262  mov     rbx, rax
0x180004265  test    rax, rax
0x180004268  jz      short loc_1800042BC
0x18000426a  cmp     qword ptr [rax], 0
0x18000426e  jz      short loc_1800042BC
0x180004270  mov     [rsi], r14b
0x180004273  mov     r9, r15; unsigned __int64
0x180004276  mov     r8, rsi; char *
0x180004279  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x18000427c  mov     rcx, rdi; struct wil::FailureInfo *
0x18000427f  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004284  test    al, al
0x180004286  jz      short loc_18000428C
0x180004288  mov     [rdi+48h], rsi
0x18000428c  mov     rbx, [rbx]
0x18000428f  mov     al, [rbx+28h]
0x180004292  mov     [rbx+28h], bpl
0x180004296  test    al, al
0x180004298  jnz     short loc_1800042B3
0x18000429a  mov     rcx, [rbx+8]
0x18000429e  mov     rax, [rcx]
0x1800042a1  mov     rdx, rdi
0x1800042a4  mov     rax, [rax]
0x1800042a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042ac  or      r14b, al
0x1800042af  mov     byte ptr [rbx+28h], 0
0x1800042b3  mov     rbx, [rbx+10h]
0x1800042b7  test    rbx, rbx
0x1800042ba  jnz     short loc_18000428F
0x1800042bc  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800042c3  test    rax, rax
0x1800042c6  jz      short loc_1800042E1
0x1800042c8  test    r14b, r14b
0x1800042cb  jnz     short loc_1800042D5
0x1800042cd  test    byte ptr [rdi+4], 2
0x1800042d1  jnz     short loc_1800042D5
0x1800042d3  xor     ebp, ebp
0x1800042d5  mov     rdx, rdi
0x1800042d8  mov     cl, bpl
0x1800042db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042e0  nop
0x1800042e1  add     rsp, 28h
0x1800042e5  pop     r15
0x1800042e7  pop     r14
0x1800042e9  pop     rdi
0x1800042ea  pop     rsi
0x1800042eb  pop     rbp
0x1800042ec  pop     rbx
0x1800042ed  retn
```
