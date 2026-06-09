# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180005b14`
- end: `0x180005bcf`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `187`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005be0`

## callees

- `0x180005b14`
- `0x180005fec`
- `0x180006204`
- `0x180013010`

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
    Local = (struct wil::details::ThreadFailureCallbackHolder **)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                                                                   (__int64)a1,
                                                                   0);
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
0x180005b14  push    rbx
0x180005b16  push    rbp
0x180005b17  push    rsi
0x180005b18  push    rdi
0x180005b19  push    r14
0x180005b1b  push    r15
0x180005b1d  sub     rsp, 28h
0x180005b21  xor     r14b, r14b
0x180005b24  mov     byte ptr [rdx], 0
0x180005b27  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005b2f  mov     r15, r8
0x180005b32  mov     rsi, rdx
0x180005b35  mov     rdi, rcx
0x180005b38  mov     bpl, 1
0x180005b3b  jz      short loc_180005B9E
0x180005b3d  xor     edx, edx
0x180005b3f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180005b44  mov     rbx, rax
0x180005b47  test    rax, rax
0x180005b4a  jz      short loc_180005B9E
0x180005b4c  cmp     qword ptr [rax], 0
0x180005b50  jz      short loc_180005B9E
0x180005b52  mov     [rsi], r14b
0x180005b55  mov     r9, r15; unsigned __int64
0x180005b58  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180005b5b  mov     r8, rsi; char *
0x180005b5e  mov     rcx, rdi; struct wil::FailureInfo *
0x180005b61  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005b66  test    al, al
0x180005b68  jz      short loc_180005B6E
0x180005b6a  mov     [rdi+48h], rsi
0x180005b6e  mov     rbx, [rbx]
0x180005b71  mov     al, [rbx+28h]
0x180005b74  mov     [rbx+28h], bpl
0x180005b78  test    al, al
0x180005b7a  jnz     short loc_180005B95
0x180005b7c  mov     rcx, [rbx+8]
0x180005b80  mov     rdx, rdi
0x180005b83  mov     rax, [rcx]
0x180005b86  mov     rax, [rax]
0x180005b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b8e  or      r14b, al
0x180005b91  mov     byte ptr [rbx+28h], 0
0x180005b95  mov     rbx, [rbx+10h]
0x180005b99  test    rbx, rbx
0x180005b9c  jnz     short loc_180005B71
0x180005b9e  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180005ba5  test    rax, rax
0x180005ba8  jz      short loc_180005BC2
0x180005baa  test    r14b, r14b
0x180005bad  jnz     short loc_180005BB7
0x180005baf  test    byte ptr [rdi+4], 2
0x180005bb3  jnz     short loc_180005BB7
0x180005bb5  xor     ebp, ebp
0x180005bb7  mov     rdx, rdi
0x180005bba  mov     cl, bpl
0x180005bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bc2  add     rsp, 28h
0x180005bc6  pop     r15
0x180005bc8  pop     r14
0x180005bca  pop     rdi
0x180005bcb  pop     rsi
0x180005bcc  pop     rbp
0x180005bcd  pop     rbx
0x180005bce  retn
```
