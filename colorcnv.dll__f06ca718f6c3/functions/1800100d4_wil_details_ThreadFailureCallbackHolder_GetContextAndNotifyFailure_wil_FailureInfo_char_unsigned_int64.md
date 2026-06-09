# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800100d4`
- end: `0x18001018d`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `185`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800101a0`

## callees

- `0x1800100d4`
- `0x1800105ac`
- `0x180010734`
- `0x18002b010`

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
0x1800100d4  push    rbx
0x1800100d6  push    rbp
0x1800100d7  push    rsi
0x1800100d8  push    rdi
0x1800100d9  push    r14
0x1800100db  push    r15
0x1800100dd  sub     rsp, 28h
0x1800100e1  xor     r14b, r14b
0x1800100e4  mov     byte ptr [rdx], 0
0x1800100e7  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800100ef  mov     r15, r8
0x1800100f2  mov     rsi, rdx
0x1800100f5  mov     rdi, rcx
0x1800100f8  mov     bpl, 1
0x1800100fb  jz      short loc_18001015C
0x1800100fd  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180010102  mov     rbx, rax
0x180010105  test    rax, rax
0x180010108  jz      short loc_18001015C
0x18001010a  cmp     qword ptr [rax], 0
0x18001010e  jz      short loc_18001015C
0x180010110  mov     [rsi], r14b
0x180010113  mov     r9, r15; unsigned __int64
0x180010116  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180010119  mov     r8, rsi; char *
0x18001011c  mov     rcx, rdi; struct wil::FailureInfo *
0x18001011f  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180010124  test    al, al
0x180010126  jz      short loc_18001012C
0x180010128  mov     [rdi+48h], rsi
0x18001012c  mov     rbx, [rbx]
0x18001012f  mov     al, [rbx+28h]
0x180010132  mov     [rbx+28h], bpl
0x180010136  test    al, al
0x180010138  jnz     short loc_180010153
0x18001013a  mov     rcx, [rbx+8]
0x18001013e  mov     rdx, rdi
0x180010141  mov     rax, [rcx]
0x180010144  mov     rax, [rax]
0x180010147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001014c  or      r14b, al
0x18001014f  mov     byte ptr [rbx+28h], 0
0x180010153  mov     rbx, [rbx+10h]
0x180010157  test    rbx, rbx
0x18001015a  jnz     short loc_18001012F
0x18001015c  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180010163  test    rax, rax
0x180010166  jz      short loc_180010180
0x180010168  test    r14b, r14b
0x18001016b  jnz     short loc_180010175
0x18001016d  test    byte ptr [rdi+4], 2
0x180010171  jnz     short loc_180010175
0x180010173  xor     ebp, ebp
0x180010175  mov     rdx, rdi
0x180010178  mov     cl, bpl
0x18001017b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010180  add     rsp, 28h
0x180010184  pop     r15
0x180010186  pop     r14
0x180010188  pop     rdi
0x180010189  pop     rsi
0x18001018a  pop     rbp
0x18001018b  pop     rbx
0x18001018c  retn
```
