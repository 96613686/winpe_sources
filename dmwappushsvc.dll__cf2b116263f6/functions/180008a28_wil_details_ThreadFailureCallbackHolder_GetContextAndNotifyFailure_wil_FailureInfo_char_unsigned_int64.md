# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180008a28`
- end: `0x180008b23`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `251`
- prototype: `void __fastcall(unsigned __int64, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008b30`

## callees

- `0x180008a28`
- `0x180008d9c`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008a57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008a57`

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
0x180008a28  push    rbx
0x180008a2a  push    rbp
0x180008a2b  push    rsi
0x180008a2c  push    rdi
0x180008a2d  push    r14
0x180008a2f  push    r15
0x180008a31  sub     rsp, 28h
0x180008a35  mov     r15, r8
0x180008a38  mov     rsi, rdx
0x180008a3b  mov     rdi, rcx
0x180008a3e  mov     byte ptr [rdx], 0
0x180008a41  xor     r14b, r14b
0x180008a44  mov     bpl, 1
0x180008a47  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180008a4e  test    rbx, rbx
0x180008a51  jz      loc_180008AF1
0x180008a57  call    cs:__imp_GetCurrentThreadId
0x180008a5d  mov     r9d, eax
0x180008a60  mov     r8d, eax
0x180008a63  shr     r8, 2
0x180008a67  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008a71  mul     r8
0x180008a74  shr     rdx, 3
0x180008a78  lea     rcx, [rdx+rdx*4]
0x180008a7c  add     rcx, rcx
0x180008a7f  sub     r8, rcx
0x180008a82  mov     rbx, [rbx+r8*8]
0x180008a86  test    rbx, rbx
0x180008a89  jz      short loc_180008A9A
0x180008a8b  cmp     [rbx], r9d
0x180008a8e  jz      short loc_180008A96
0x180008a90  mov     rbx, [rbx+8]
0x180008a94  jmp     short loc_180008A86
0x180008a96  add     rbx, 10h
0x180008a9a  test    rbx, rbx
0x180008a9d  jz      short loc_180008AF1
0x180008a9f  cmp     qword ptr [rbx], 0
0x180008aa3  jz      short loc_180008AF1
0x180008aa5  mov     [rsi], r14b
0x180008aa8  mov     r9, r15; unsigned __int64
0x180008aab  mov     r8, rsi; char *
0x180008aae  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180008ab1  mov     rcx, rdi; struct wil::FailureInfo *
0x180008ab4  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180008ab9  test    al, al
0x180008abb  jz      short loc_180008AC1
0x180008abd  mov     [rdi+48h], rsi
0x180008ac1  mov     rbx, [rbx]
0x180008ac4  mov     al, [rbx+28h]
0x180008ac7  mov     [rbx+28h], bpl
0x180008acb  test    al, al
0x180008acd  jnz     short loc_180008AE8
0x180008acf  mov     rcx, [rbx+8]
0x180008ad3  mov     rax, [rcx]
0x180008ad6  mov     rdx, rdi
0x180008ad9  mov     rax, [rax]
0x180008adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ae1  or      r14b, al
0x180008ae4  mov     byte ptr [rbx+28h], 0
0x180008ae8  mov     rbx, [rbx+10h]
0x180008aec  test    rbx, rbx
0x180008aef  jnz     short loc_180008AC4
0x180008af1  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180008af8  test    rax, rax
0x180008afb  jz      short loc_180008B16
0x180008afd  test    r14b, r14b
0x180008b00  jnz     short loc_180008B0A
0x180008b02  test    byte ptr [rdi+4], 2
0x180008b06  jnz     short loc_180008B0A
0x180008b08  xor     ebp, ebp
0x180008b0a  mov     rdx, rdi
0x180008b0d  mov     cl, bpl
0x180008b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b15  nop
0x180008b16  add     rsp, 28h
0x180008b1a  pop     r15
0x180008b1c  pop     r14
0x180008b1e  pop     rdi
0x180008b1f  pop     rsi
0x180008b20  pop     rbp
0x180008b21  pop     rbx
0x180008b22  retn
```
