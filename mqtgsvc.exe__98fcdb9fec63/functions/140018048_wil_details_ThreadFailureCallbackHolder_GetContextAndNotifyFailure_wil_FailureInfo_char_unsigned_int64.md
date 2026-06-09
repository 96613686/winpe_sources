# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140018048`
- end: `0x140018143`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `251`
- prototype: `void __fastcall(unsigned __int64, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140018150`

## callees

- `0x140018048`
- `0x1400186b8`
- `0x140020010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140018077`
- `KERNEL32!GetCurrentThreadId` at `0x140018077`

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
0x140018048  push    rbx
0x14001804a  push    rbp
0x14001804b  push    rsi
0x14001804c  push    rdi
0x14001804d  push    r14
0x14001804f  push    r15
0x140018051  sub     rsp, 28h
0x140018055  mov     r15, r8
0x140018058  mov     rsi, rdx
0x14001805b  mov     rdi, rcx
0x14001805e  mov     byte ptr [rdx], 0
0x140018061  xor     r14b, r14b
0x140018064  mov     bpl, 1
0x140018067  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14001806e  test    rbx, rbx
0x140018071  jz      loc_140018111
0x140018077  call    cs:__imp_GetCurrentThreadId
0x14001807d  mov     r9d, eax
0x140018080  mov     r8d, eax
0x140018083  shr     r8, 2
0x140018087  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140018091  mul     r8
0x140018094  shr     rdx, 3
0x140018098  lea     rcx, [rdx+rdx*4]
0x14001809c  add     rcx, rcx
0x14001809f  sub     r8, rcx
0x1400180a2  mov     rbx, [rbx+r8*8]
0x1400180a6  test    rbx, rbx
0x1400180a9  jz      short loc_1400180BA
0x1400180ab  cmp     [rbx], r9d
0x1400180ae  jz      short loc_1400180B6
0x1400180b0  mov     rbx, [rbx+8]
0x1400180b4  jmp     short loc_1400180A6
0x1400180b6  add     rbx, 10h
0x1400180ba  test    rbx, rbx
0x1400180bd  jz      short loc_140018111
0x1400180bf  cmp     qword ptr [rbx], 0
0x1400180c3  jz      short loc_140018111
0x1400180c5  mov     byte ptr [rsi], 0
0x1400180c8  mov     r9, r15; unsigned __int64
0x1400180cb  mov     r8, rsi; char *
0x1400180ce  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1400180d1  mov     rcx, rdi; struct wil::FailureInfo *
0x1400180d4  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400180d9  test    al, al
0x1400180db  jz      short loc_1400180E1
0x1400180dd  mov     [rdi+48h], rsi
0x1400180e1  mov     rbx, [rbx]
0x1400180e4  mov     al, [rbx+28h]
0x1400180e7  mov     [rbx+28h], bpl
0x1400180eb  test    al, al
0x1400180ed  jnz     short loc_140018108
0x1400180ef  mov     rcx, [rbx+8]
0x1400180f3  mov     rax, [rcx]
0x1400180f6  mov     rdx, rdi
0x1400180f9  mov     rax, [rax]
0x1400180fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018101  or      r14b, al
0x140018104  mov     byte ptr [rbx+28h], 0
0x140018108  mov     rbx, [rbx+10h]
0x14001810c  test    rbx, rbx
0x14001810f  jnz     short loc_1400180E4
0x140018111  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140018118  test    rax, rax
0x14001811b  jz      short loc_140018136
0x14001811d  test    r14b, r14b
0x140018120  jnz     short loc_14001812A
0x140018122  test    byte ptr [rdi+4], 2
0x140018126  jnz     short loc_14001812A
0x140018128  xor     ebp, ebp
0x14001812a  mov     rdx, rdi
0x14001812d  mov     cl, bpl
0x140018130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018135  nop
0x140018136  add     rsp, 28h
0x14001813a  pop     r15
0x14001813c  pop     r14
0x14001813e  pop     rdi
0x14001813f  pop     rsi
0x140018140  pop     rbp
0x140018141  pop     rbx
0x140018142  retn
```
