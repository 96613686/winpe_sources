# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18001fea8`
- end: `0x18001ffa3`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `251`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001ffb0`

## callees

- `0x18001fea8`
- `0x18002043c`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fed7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fed7`

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
0x18001fea8  push    rbx
0x18001feaa  push    rbp
0x18001feab  push    rsi
0x18001feac  push    rdi
0x18001fead  push    r14
0x18001feaf  push    r15
0x18001feb1  sub     rsp, 28h
0x18001feb5  mov     r15, r8
0x18001feb8  mov     rsi, rdx
0x18001febb  mov     rdi, rcx
0x18001febe  mov     byte ptr [rdx], 0
0x18001fec1  xor     r14b, r14b
0x18001fec4  mov     bpl, 1
0x18001fec7  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001fece  test    rbx, rbx
0x18001fed1  jz      loc_18001FF71
0x18001fed7  call    cs:__imp_GetCurrentThreadId
0x18001fedd  mov     r9d, eax
0x18001fee0  mov     r8d, eax
0x18001fee3  shr     r8, 2
0x18001fee7  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001fef1  mul     r8
0x18001fef4  shr     rdx, 3
0x18001fef8  lea     rcx, [rdx+rdx*4]
0x18001fefc  add     rcx, rcx
0x18001feff  sub     r8, rcx
0x18001ff02  mov     rbx, [rbx+r8*8]
0x18001ff06  test    rbx, rbx
0x18001ff09  jz      short loc_18001FF1A
0x18001ff0b  cmp     [rbx], r9d
0x18001ff0e  jz      short loc_18001FF16
0x18001ff10  mov     rbx, [rbx+8]
0x18001ff14  jmp     short loc_18001FF06
0x18001ff16  add     rbx, 10h
0x18001ff1a  test    rbx, rbx
0x18001ff1d  jz      short loc_18001FF71
0x18001ff1f  cmp     qword ptr [rbx], 0
0x18001ff23  jz      short loc_18001FF71
0x18001ff25  mov     [rsi], r14b
0x18001ff28  mov     r9, r15; unsigned __int64
0x18001ff2b  mov     r8, rsi; char *
0x18001ff2e  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18001ff31  mov     rcx, rdi; struct wil::FailureInfo *
0x18001ff34  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18001ff39  test    al, al
0x18001ff3b  jz      short loc_18001FF41
0x18001ff3d  mov     [rdi+48h], rsi
0x18001ff41  mov     rbx, [rbx]
0x18001ff44  mov     al, [rbx+28h]
0x18001ff47  mov     [rbx+28h], bpl
0x18001ff4b  test    al, al
0x18001ff4d  jnz     short loc_18001FF68
0x18001ff4f  mov     rcx, [rbx+8]
0x18001ff53  mov     rax, [rcx]
0x18001ff56  mov     rdx, rdi
0x18001ff59  mov     rax, [rax]
0x18001ff5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff61  or      r14b, al
0x18001ff64  mov     byte ptr [rbx+28h], 0
0x18001ff68  mov     rbx, [rbx+10h]
0x18001ff6c  test    rbx, rbx
0x18001ff6f  jnz     short loc_18001FF44
0x18001ff71  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18001ff78  test    rax, rax
0x18001ff7b  jz      short loc_18001FF96
0x18001ff7d  test    r14b, r14b
0x18001ff80  jnz     short loc_18001FF8A
0x18001ff82  test    byte ptr [rdi+4], 2
0x18001ff86  jnz     short loc_18001FF8A
0x18001ff88  xor     ebp, ebp
0x18001ff8a  mov     rdx, rdi
0x18001ff8d  mov     cl, bpl
0x18001ff90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff95  nop
0x18001ff96  add     rsp, 28h
0x18001ff9a  pop     r15
0x18001ff9c  pop     r14
0x18001ff9e  pop     rdi
0x18001ff9f  pop     rsi
0x18001ffa0  pop     rbp
0x18001ffa1  pop     rbx
0x18001ffa2  retn
```
