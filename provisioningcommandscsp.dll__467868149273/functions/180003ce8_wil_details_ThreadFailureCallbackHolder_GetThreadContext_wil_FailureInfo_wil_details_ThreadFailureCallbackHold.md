# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180003ce8`
- end: `0x180003dcc`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `228`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003670`
- `0x180003ce8`

## callees

- `0x180003ce8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180003daf`
- `msvcrt!memcpy_s` at `0x180003daf`

## pseudocode

```c
bool __fastcall wil::details::ThreadFailureCallbackHolder::GetThreadContext(
        struct wil::FailureInfo *a1,
        struct wil::details::ThreadFailureCallbackHolder **a2,
        char *a3,
        unsigned __int64 a4)
{
  bool result; // al
  struct wil::details::ThreadFailureCallbackHolder *v9; // rdx
  char *v10; // r10
  __int64 v11; // rbx
  __int64 v12; // rax
  char *v13; // rcx
  char *v14; // rdi
  _BYTE *v15; // r8
  rsize_t v16; // r10
  rsize_t v17; // rbx
  void *v18; // rcx

  result = 0;
  *a3 = 0;
  if ( a2 )
  {
    result = wil::details::ThreadFailureCallbackHolder::GetThreadContext(a1, a2[2], a3, a4);
    v9 = a2[4];
    if ( v9 )
    {
      if ( !*(_DWORD *)v9 )
        *(_DWORD *)v9 = _InterlockedIncrement(&wil::details::ThreadFailureCallbackHolder::s_telemetryId);
      if ( !*((_DWORD *)a1 + 20) )
      {
        *((_OWORD *)a1 + 5) = *(_OWORD *)v9;
        *((_QWORD *)a1 + 12) = *((_QWORD *)v9 + 2);
      }
      v10 = &a3[a4];
      *(_OWORD *)((char *)a1 + 104) = *(_OWORD *)v9;
      *((_QWORD *)a1 + 15) = *((_QWORD *)v9 + 2);
      v11 = -1;
      v12 = -1;
      do
        ++v12;
      while ( a3[v12] );
      v13 = &a3[v12];
      if ( (__int64)(a4 - v12) > 2 )
      {
        *v13 = 92;
        v14 = v13 + 1;
        v15 = (_BYTE *)*((_QWORD *)v9 + 1);
        do
          ++v11;
        while ( v15[v11] );
        v16 = v10 - v14;
        v17 = v11 + 1;
        v18 = v13 + 1;
        if ( v17 >= v16 )
          v17 = v16;
        memcpy_s(v18, v16, v15, v17);
        v14[v17 - 1] = 0;
      }
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003ce8  push    rbx
0x180003cea  push    rbp
0x180003ceb  push    rsi
0x180003cec  push    rdi
0x180003ced  sub     rsp, 28h
0x180003cf1  xor     al, al
0x180003cf3  mov     byte ptr [r8], 0
0x180003cf7  mov     rbp, r9
0x180003cfa  mov     rdi, r8
0x180003cfd  mov     rsi, rdx
0x180003d00  mov     rbx, rcx
0x180003d03  test    rdx, rdx
0x180003d06  jz      loc_180003DC2
0x180003d0c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180003d10  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003d15  mov     rdx, [rsi+20h]
0x180003d19  test    rdx, rdx
0x180003d1c  jz      loc_180003DC2
0x180003d22  cmp     dword ptr [rdx], 0
0x180003d25  jnz     short loc_180003D38
0x180003d27  mov     eax, 1
0x180003d2c  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180003d34  inc     eax
0x180003d36  mov     [rdx], eax
0x180003d38  cmp     dword ptr [rbx+50h], 0
0x180003d3c  jnz     short loc_180003D4F
0x180003d3e  movups  xmm0, xmmword ptr [rdx]
0x180003d41  movups  xmmword ptr [rbx+50h], xmm0
0x180003d45  movsd   xmm1, qword ptr [rdx+10h]
0x180003d4a  movsd   qword ptr [rbx+60h], xmm1
0x180003d4f  movups  xmm0, xmmword ptr [rdx]
0x180003d52  lea     r10, [rdi+rbp]
0x180003d56  movups  xmmword ptr [rbx+68h], xmm0
0x180003d5a  movsd   xmm1, qword ptr [rdx+10h]
0x180003d5f  movsd   qword ptr [rbx+78h], xmm1
0x180003d64  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003d68  mov     rax, rbx
0x180003d6b  inc     rax
0x180003d6e  cmp     byte ptr [rdi+rax], 0
0x180003d72  jnz     short loc_180003D6B
0x180003d74  lea     rcx, [rax+rdi]
0x180003d78  mov     rax, r10
0x180003d7b  sub     rax, rcx
0x180003d7e  cmp     rax, 2
0x180003d82  jle     short loc_180003DC0
0x180003d84  mov     byte ptr [rcx], 5Ch ; '\'
0x180003d87  lea     rdi, [rcx+1]
0x180003d8b  mov     r8, [rdx+8]; Source
0x180003d8f  inc     rbx
0x180003d92  cmp     byte ptr [r8+rbx], 0
0x180003d97  jnz     short loc_180003D8F
0x180003d99  sub     r10, rdi
0x180003d9c  inc     rbx
0x180003d9f  cmp     rbx, r10
0x180003da2  mov     rdx, r10; DestinationSize
0x180003da5  mov     rcx, rdi; Destination
0x180003da8  cmovnb  rbx, r10
0x180003dac  mov     r9, rbx; SourceSize
0x180003daf  call    cs:__imp_memcpy_s
0x180003db6  nop     dword ptr [rax+rax+00h]
0x180003dbb  mov     byte ptr [rbx+rdi-1], 0
0x180003dc0  mov     al, 1
0x180003dc2  add     rsp, 28h
0x180003dc6  pop     rdi
0x180003dc7  pop     rsi
0x180003dc8  pop     rbp
0x180003dc9  pop     rbx
0x180003dca  retn
```
