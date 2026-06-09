# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180006c18`
- end: `0x180006d13`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `251`
- prototype: `void __fastcall(unsigned __int64, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006d20`

## callees

- `0x180006c18`
- `0x1800071e4`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006c47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006c47`

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
0x180006c18  push    rbx
0x180006c1a  push    rbp
0x180006c1b  push    rsi
0x180006c1c  push    rdi
0x180006c1d  push    r14
0x180006c1f  push    r15
0x180006c21  sub     rsp, 28h
0x180006c25  mov     r15, r8
0x180006c28  mov     rsi, rdx
0x180006c2b  mov     rdi, rcx
0x180006c2e  mov     byte ptr [rdx], 0
0x180006c31  xor     r14b, r14b
0x180006c34  mov     bpl, 1
0x180006c37  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006c3e  test    rbx, rbx
0x180006c41  jz      loc_180006CE1
0x180006c47  call    cs:__imp_GetCurrentThreadId
0x180006c4d  mov     r9d, eax
0x180006c50  mov     r8d, eax
0x180006c53  shr     r8, 2
0x180006c57  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006c61  mul     r8
0x180006c64  shr     rdx, 3
0x180006c68  lea     rcx, [rdx+rdx*4]
0x180006c6c  add     rcx, rcx
0x180006c6f  sub     r8, rcx
0x180006c72  mov     rbx, [rbx+r8*8]
0x180006c76  test    rbx, rbx
0x180006c79  jz      short loc_180006C8A
0x180006c7b  cmp     [rbx], r9d
0x180006c7e  jz      short loc_180006C86
0x180006c80  mov     rbx, [rbx+8]
0x180006c84  jmp     short loc_180006C76
0x180006c86  add     rbx, 10h
0x180006c8a  test    rbx, rbx
0x180006c8d  jz      short loc_180006CE1
0x180006c8f  cmp     qword ptr [rbx], 0
0x180006c93  jz      short loc_180006CE1
0x180006c95  mov     [rsi], r14b
0x180006c98  mov     r9, r15; unsigned __int64
0x180006c9b  mov     r8, rsi; char *
0x180006c9e  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180006ca1  mov     rcx, rdi; struct wil::FailureInfo *
0x180006ca4  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006ca9  test    al, al
0x180006cab  jz      short loc_180006CB1
0x180006cad  mov     [rdi+48h], rsi
0x180006cb1  mov     rbx, [rbx]
0x180006cb4  mov     al, [rbx+28h]
0x180006cb7  mov     [rbx+28h], bpl
0x180006cbb  test    al, al
0x180006cbd  jnz     short loc_180006CD8
0x180006cbf  mov     rcx, [rbx+8]
0x180006cc3  mov     rax, [rcx]
0x180006cc6  mov     rdx, rdi
0x180006cc9  mov     rax, [rax]
0x180006ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cd1  or      r14b, al
0x180006cd4  mov     byte ptr [rbx+28h], 0
0x180006cd8  mov     rbx, [rbx+10h]
0x180006cdc  test    rbx, rbx
0x180006cdf  jnz     short loc_180006CB4
0x180006ce1  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180006ce8  test    rax, rax
0x180006ceb  jz      short loc_180006D06
0x180006ced  test    r14b, r14b
0x180006cf0  jnz     short loc_180006CFA
0x180006cf2  test    byte ptr [rdi+4], 2
0x180006cf6  jnz     short loc_180006CFA
0x180006cf8  xor     ebp, ebp
0x180006cfa  mov     rdx, rdi
0x180006cfd  mov     cl, bpl
0x180006d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d05  nop
0x180006d06  add     rsp, 28h
0x180006d0a  pop     r15
0x180006d0c  pop     r14
0x180006d0e  pop     rdi
0x180006d0f  pop     rsi
0x180006d10  pop     rbp
0x180006d11  pop     rbx
0x180006d12  retn
```
