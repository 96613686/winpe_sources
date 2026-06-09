# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000204c`
- end: `0x180002106`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180001fe0`

## callees

- `0x18000204c`
- `0x18000b0dc`
- `0x1800112e8`
- `0x180018010`

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
0x18000204c  push    rbx
0x18000204e  push    rbp
0x18000204f  push    rsi
0x180002050  push    rdi
0x180002051  push    r14
0x180002053  push    r15
0x180002055  sub     rsp, 28h
0x180002059  mov     r15, r8
0x18000205c  mov     rsi, rdx
0x18000205f  mov     rdi, rcx
0x180002062  mov     byte ptr [rdx], 0
0x180002065  xor     r14b, r14b
0x180002068  mov     bpl, 1
0x18000206b  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180002073  jz      short loc_1800020D4
0x180002075  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000207a  mov     rbx, rax
0x18000207d  test    rax, rax
0x180002080  jz      short loc_1800020D4
0x180002082  cmp     qword ptr [rax], 0
0x180002086  jz      short loc_1800020D4
0x180002088  mov     [rsi], r14b
0x18000208b  mov     r9, r15; unsigned __int64
0x18000208e  mov     r8, rsi; char *
0x180002091  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180002094  mov     rcx, rdi; struct wil::FailureInfo *
0x180002097  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000209c  test    al, al
0x18000209e  jz      short loc_1800020A4
0x1800020a0  mov     [rdi+48h], rsi
0x1800020a4  mov     rbx, [rbx]
0x1800020a7  mov     al, [rbx+28h]
0x1800020aa  mov     [rbx+28h], bpl
0x1800020ae  test    al, al
0x1800020b0  jnz     short loc_1800020CB
0x1800020b2  mov     rcx, [rbx+8]
0x1800020b6  mov     rax, [rcx]
0x1800020b9  mov     rdx, rdi
0x1800020bc  mov     rax, [rax]
0x1800020bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020c4  or      r14b, al
0x1800020c7  mov     byte ptr [rbx+28h], 0
0x1800020cb  mov     rbx, [rbx+10h]
0x1800020cf  test    rbx, rbx
0x1800020d2  jnz     short loc_1800020A7
0x1800020d4  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800020db  test    rax, rax
0x1800020de  jz      short loc_1800020F9
0x1800020e0  test    r14b, r14b
0x1800020e3  jnz     short loc_1800020ED
0x1800020e5  test    byte ptr [rdi+4], 2
0x1800020e9  jnz     short loc_1800020ED
0x1800020eb  xor     ebp, ebp
0x1800020ed  mov     rdx, rdi
0x1800020f0  mov     cl, bpl
0x1800020f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020f8  nop
0x1800020f9  add     rsp, 28h
0x1800020fd  pop     r15
0x1800020ff  pop     r14
0x180002101  pop     rdi
0x180002102  pop     rsi
0x180002103  pop     rbp
0x180002104  pop     rbx
0x180002105  retn
```
