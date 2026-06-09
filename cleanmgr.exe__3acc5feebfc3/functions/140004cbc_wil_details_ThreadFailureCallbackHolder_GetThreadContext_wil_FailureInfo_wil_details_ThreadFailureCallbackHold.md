# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140004cbc`
- end: `0x140004d98`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004614`
- `0x140004cbc`

## callees

- `0x140004cbc`
- `0x1400069a8`

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
0x140004cbc  push    rbx
0x140004cbe  push    rbp
0x140004cbf  push    rsi
0x140004cc0  push    rdi
0x140004cc1  sub     rsp, 28h
0x140004cc5  xor     al, al
0x140004cc7  mov     byte ptr [r8], 0
0x140004ccb  mov     rbp, r9
0x140004cce  mov     rdi, r8
0x140004cd1  mov     rsi, rdx
0x140004cd4  mov     rbx, rcx
0x140004cd7  test    rdx, rdx
0x140004cda  jz      loc_140004D8F
0x140004ce0  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140004ce4  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140004ce9  mov     rdx, [rsi+20h]
0x140004ced  test    rdx, rdx
0x140004cf0  jz      loc_140004D8F
0x140004cf6  cmp     dword ptr [rdx], 0
0x140004cf9  jnz     short loc_140004D0C
0x140004cfb  mov     eax, 1
0x140004d00  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140004d08  inc     eax
0x140004d0a  mov     [rdx], eax
0x140004d0c  cmp     dword ptr [rbx+50h], 0
0x140004d10  jnz     short loc_140004D23
0x140004d12  movups  xmm0, xmmword ptr [rdx]
0x140004d15  movups  xmmword ptr [rbx+50h], xmm0
0x140004d19  movsd   xmm1, qword ptr [rdx+10h]
0x140004d1e  movsd   qword ptr [rbx+60h], xmm1
0x140004d23  movups  xmm0, xmmword ptr [rdx]
0x140004d26  lea     r10, [rdi+rbp]
0x140004d2a  movups  xmmword ptr [rbx+68h], xmm0
0x140004d2e  movsd   xmm1, qword ptr [rdx+10h]
0x140004d33  movsd   qword ptr [rbx+78h], xmm1
0x140004d38  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140004d3c  mov     rax, rbx
0x140004d3f  inc     rax
0x140004d42  cmp     byte ptr [rdi+rax], 0
0x140004d46  jnz     short loc_140004D3F
0x140004d48  lea     rcx, [rax+rdi]
0x140004d4c  mov     rax, r10
0x140004d4f  sub     rax, rcx
0x140004d52  cmp     rax, 2
0x140004d56  jle     short loc_140004D8D
0x140004d58  mov     byte ptr [rcx], 5Ch ; '\'
0x140004d5b  lea     rdi, [rcx+1]
0x140004d5f  mov     r8, [rdx+8]; Source
0x140004d63  inc     rbx
0x140004d66  cmp     byte ptr [r8+rbx], 0
0x140004d6b  jnz     short loc_140004D63
0x140004d6d  sub     r10, rdi
0x140004d70  inc     rbx
0x140004d73  cmp     rbx, r10
0x140004d76  mov     rdx, r10; DestinationSize
0x140004d79  mov     rcx, rdi; Destination
0x140004d7c  cmovnb  rbx, r10
0x140004d80  mov     r9, rbx; SourceSize
0x140004d83  call    memcpy_s
0x140004d88  mov     byte ptr [rbx+rdi-1], 0
0x140004d8d  mov     al, 1
0x140004d8f  add     rsp, 28h
0x140004d93  pop     rdi
0x140004d94  pop     rsi
0x140004d95  pop     rbp
0x140004d96  pop     rbx
0x140004d97  retn
```
