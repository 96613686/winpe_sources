# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180008a1c`
- end: `0x180008b17`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `251`
- prototype: `void __fastcall(unsigned __int64, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008b20`

## callees

- `0x180008a1c`
- `0x180009098`
- `0x18002d010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180008a4b`
- `KERNEL32!GetCurrentThreadId` at `0x180008a4b`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(
        unsigned __int64 a1,
        char *a2,
        unsigned __int64 a3)
{
  struct wil::FailureInfo *v5; // rdi
  char v6; // r14
  char v7; // bp
  __int64 v8; // rbx
  unsigned __int64 CurrentThreadId; // r9
  __int64 i; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v11; // rbx
  char v12; // al

  v5 = (struct wil::FailureInfo *)a1;
  *a2 = 0;
  v6 = 0;
  v7 = 1;
  v8 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    a1 = 10 * ((CurrentThreadId >> 2) / 0xA);
    for ( i = *(_QWORD *)(v8 + 8 * ((CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      {
        i += 16;
        break;
      }
    }
    if ( i && *(_QWORD *)i )
    {
      *a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(
             v5,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             a2,
             a3) )
      {
        *((_QWORD *)v5 + 9) = a2;
      }
      v11 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v12 = *((_BYTE *)v11 + 40);
        *((_BYTE *)v11 + 40) = 1;
        if ( !v12 )
        {
          v6 |= (***((__int64 (__fastcall ****)(_QWORD, struct wil::FailureInfo *))v11 + 1))(*((_QWORD *)v11 + 1), v5);
          *((_BYTE *)v11 + 40) = 0;
        }
        v11 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v11 + 2);
      }
      while ( v11 );
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
0x180008a1c  push    rbx
0x180008a1e  push    rbp
0x180008a1f  push    rsi
0x180008a20  push    rdi
0x180008a21  push    r14
0x180008a23  push    r15
0x180008a25  sub     rsp, 28h
0x180008a29  mov     r15, r8
0x180008a2c  mov     rsi, rdx
0x180008a2f  mov     rdi, rcx
0x180008a32  mov     byte ptr [rdx], 0
0x180008a35  xor     r14b, r14b
0x180008a38  mov     bpl, 1
0x180008a3b  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180008a42  test    rbx, rbx
0x180008a45  jz      loc_180008AE5
0x180008a4b  call    cs:__imp_GetCurrentThreadId
0x180008a51  mov     r9d, eax
0x180008a54  mov     r8d, eax
0x180008a57  shr     r8, 2
0x180008a5b  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008a65  mul     r8
0x180008a68  shr     rdx, 3
0x180008a6c  lea     rcx, [rdx+rdx*4]
0x180008a70  add     rcx, rcx
0x180008a73  sub     r8, rcx
0x180008a76  mov     rbx, [rbx+r8*8]
0x180008a7a  test    rbx, rbx
0x180008a7d  jz      short loc_180008A8E
0x180008a7f  cmp     [rbx], r9d
0x180008a82  jz      short loc_180008A8A
0x180008a84  mov     rbx, [rbx+8]
0x180008a88  jmp     short loc_180008A7A
0x180008a8a  add     rbx, 10h
0x180008a8e  test    rbx, rbx
0x180008a91  jz      short loc_180008AE5
0x180008a93  cmp     qword ptr [rbx], 0
0x180008a97  jz      short loc_180008AE5
0x180008a99  mov     [rsi], r14b
0x180008a9c  mov     r9, r15; unsigned __int64
0x180008a9f  mov     r8, rsi; char *
0x180008aa2  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180008aa5  mov     rcx, rdi; struct wil::FailureInfo *
0x180008aa8  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180008aad  test    al, al
0x180008aaf  jz      short loc_180008AB5
0x180008ab1  mov     [rdi+48h], rsi
0x180008ab5  mov     rbx, [rbx]
0x180008ab8  mov     al, [rbx+28h]
0x180008abb  mov     [rbx+28h], bpl
0x180008abf  test    al, al
0x180008ac1  jnz     short loc_180008ADC
0x180008ac3  mov     rcx, [rbx+8]
0x180008ac7  mov     rax, [rcx]
0x180008aca  mov     rdx, rdi
0x180008acd  mov     rax, [rax]
0x180008ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ad5  or      r14b, al
0x180008ad8  mov     byte ptr [rbx+28h], 0
0x180008adc  mov     rbx, [rbx+10h]
0x180008ae0  test    rbx, rbx
0x180008ae3  jnz     short loc_180008AB8
0x180008ae5  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180008aec  test    rax, rax
0x180008aef  jz      short loc_180008B0A
0x180008af1  test    r14b, r14b
0x180008af4  jnz     short loc_180008AFE
0x180008af6  test    byte ptr [rdi+4], 2
0x180008afa  jnz     short loc_180008AFE
0x180008afc  xor     ebp, ebp
0x180008afe  mov     rdx, rdi
0x180008b01  mov     cl, bpl
0x180008b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b09  nop
0x180008b0a  add     rsp, 28h
0x180008b0e  pop     r15
0x180008b10  pop     r14
0x180008b12  pop     rdi
0x180008b13  pop     rsi
0x180008b14  pop     rbp
0x180008b15  pop     rbx
0x180008b16  retn
```
