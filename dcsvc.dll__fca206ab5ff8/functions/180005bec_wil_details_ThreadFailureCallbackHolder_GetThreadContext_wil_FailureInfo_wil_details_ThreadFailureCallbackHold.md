# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180005bec`
- end: `0x180005cc8`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800054f0`
- `0x180005bec`

## callees

- `0x180005bec`
- `0x18000a8b4`

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
0x180005bec  push    rbx
0x180005bee  push    rbp
0x180005bef  push    rsi
0x180005bf0  push    rdi
0x180005bf1  sub     rsp, 28h
0x180005bf5  xor     al, al
0x180005bf7  mov     byte ptr [r8], 0
0x180005bfb  mov     rbp, r9
0x180005bfe  mov     rdi, r8
0x180005c01  mov     rsi, rdx
0x180005c04  mov     rbx, rcx
0x180005c07  test    rdx, rdx
0x180005c0a  jz      loc_180005CBF
0x180005c10  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180005c14  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005c19  mov     rdx, [rsi+20h]
0x180005c1d  test    rdx, rdx
0x180005c20  jz      loc_180005CBF
0x180005c26  cmp     dword ptr [rdx], 0
0x180005c29  jnz     short loc_180005C3C
0x180005c2b  mov     eax, 1
0x180005c30  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180005c38  inc     eax
0x180005c3a  mov     [rdx], eax
0x180005c3c  cmp     dword ptr [rbx+50h], 0
0x180005c40  jnz     short loc_180005C53
0x180005c42  movups  xmm0, xmmword ptr [rdx]
0x180005c45  movups  xmmword ptr [rbx+50h], xmm0
0x180005c49  movsd   xmm1, qword ptr [rdx+10h]
0x180005c4e  movsd   qword ptr [rbx+60h], xmm1
0x180005c53  movups  xmm0, xmmword ptr [rdx]
0x180005c56  lea     r10, [rdi+rbp]
0x180005c5a  movups  xmmword ptr [rbx+68h], xmm0
0x180005c5e  movsd   xmm1, qword ptr [rdx+10h]
0x180005c63  movsd   qword ptr [rbx+78h], xmm1
0x180005c68  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005c6c  mov     rax, rbx
0x180005c6f  inc     rax
0x180005c72  cmp     byte ptr [rdi+rax], 0
0x180005c76  jnz     short loc_180005C6F
0x180005c78  lea     rcx, [rax+rdi]
0x180005c7c  mov     rax, r10
0x180005c7f  sub     rax, rcx
0x180005c82  cmp     rax, 2
0x180005c86  jle     short loc_180005CBD
0x180005c88  mov     byte ptr [rcx], 5Ch ; '\'
0x180005c8b  lea     rdi, [rcx+1]
0x180005c8f  mov     r8, [rdx+8]; Source
0x180005c93  inc     rbx
0x180005c96  cmp     byte ptr [r8+rbx], 0
0x180005c9b  jnz     short loc_180005C93
0x180005c9d  sub     r10, rdi
0x180005ca0  inc     rbx
0x180005ca3  cmp     rbx, r10
0x180005ca6  mov     rdx, r10; DestinationSize
0x180005ca9  mov     rcx, rdi; Destination
0x180005cac  cmovnb  rbx, r10
0x180005cb0  mov     r9, rbx; SourceSize
0x180005cb3  call    memcpy_s
0x180005cb8  mov     byte ptr [rbx+rdi-1], 0
0x180005cbd  mov     al, 1
0x180005cbf  add     rsp, 28h
0x180005cc3  pop     rdi
0x180005cc4  pop     rsi
0x180005cc5  pop     rbp
0x180005cc6  pop     rbx
0x180005cc7  retn
```
