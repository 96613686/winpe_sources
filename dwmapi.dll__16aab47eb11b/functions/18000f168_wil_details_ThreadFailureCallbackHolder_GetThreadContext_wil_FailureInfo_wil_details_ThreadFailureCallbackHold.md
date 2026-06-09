# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000f168`
- end: `0x18000f244`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000635c`
- `0x18000f168`

## callees

- `0x18000ca48`
- `0x18000f168`

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
0x18000f168  push    rbx
0x18000f16a  push    rbp
0x18000f16b  push    rsi
0x18000f16c  push    rdi
0x18000f16d  sub     rsp, 28h
0x18000f171  xor     al, al
0x18000f173  mov     byte ptr [r8], 0
0x18000f177  mov     rbp, r9
0x18000f17a  mov     rdi, r8
0x18000f17d  mov     rsi, rdx
0x18000f180  mov     rbx, rcx
0x18000f183  test    rdx, rdx
0x18000f186  jz      loc_18000F23B
0x18000f18c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18000f190  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000f195  mov     rdx, [rsi+20h]
0x18000f199  test    rdx, rdx
0x18000f19c  jz      loc_18000F23B
0x18000f1a2  cmp     dword ptr [rdx], 0
0x18000f1a5  jnz     short loc_18000F1B8
0x18000f1a7  mov     eax, 1
0x18000f1ac  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000f1b4  inc     eax
0x18000f1b6  mov     [rdx], eax
0x18000f1b8  cmp     dword ptr [rbx+50h], 0
0x18000f1bc  jnz     short loc_18000F1CF
0x18000f1be  movups  xmm0, xmmword ptr [rdx]
0x18000f1c1  movups  xmmword ptr [rbx+50h], xmm0
0x18000f1c5  movsd   xmm1, qword ptr [rdx+10h]
0x18000f1ca  movsd   qword ptr [rbx+60h], xmm1
0x18000f1cf  movups  xmm0, xmmword ptr [rdx]
0x18000f1d2  lea     r10, [rdi+rbp]
0x18000f1d6  movups  xmmword ptr [rbx+68h], xmm0
0x18000f1da  movsd   xmm1, qword ptr [rdx+10h]
0x18000f1df  movsd   qword ptr [rbx+78h], xmm1
0x18000f1e4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000f1e8  mov     rax, rbx
0x18000f1eb  inc     rax
0x18000f1ee  cmp     byte ptr [rdi+rax], 0
0x18000f1f2  jnz     short loc_18000F1EB
0x18000f1f4  lea     rcx, [rax+rdi]
0x18000f1f8  mov     rax, r10
0x18000f1fb  sub     rax, rcx
0x18000f1fe  cmp     rax, 2
0x18000f202  jle     short loc_18000F239
0x18000f204  mov     byte ptr [rcx], 5Ch ; '\'
0x18000f207  lea     rdi, [rcx+1]
0x18000f20b  mov     r8, [rdx+8]; Source
0x18000f20f  inc     rbx
0x18000f212  cmp     byte ptr [r8+rbx], 0
0x18000f217  jnz     short loc_18000F20F
0x18000f219  sub     r10, rdi
0x18000f21c  inc     rbx
0x18000f21f  cmp     rbx, r10
0x18000f222  mov     rdx, r10; DestinationSize
0x18000f225  mov     rcx, rdi; Destination
0x18000f228  cmovnb  rbx, r10
0x18000f22c  mov     r9, rbx; SourceSize
0x18000f22f  call    memcpy_s
0x18000f234  mov     byte ptr [rbx+rdi-1], 0
0x18000f239  mov     al, 1
0x18000f23b  add     rsp, 28h
0x18000f23f  pop     rdi
0x18000f240  pop     rsi
0x18000f241  pop     rbp
0x18000f242  pop     rbx
0x18000f243  retn
```
