# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1400079dc`
- end: `0x140007ab8`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140007190`
- `0x1400079dc`

## callees

- `0x1400079dc`
- `0x14000d778`

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
0x1400079dc  push    rbx
0x1400079de  push    rbp
0x1400079df  push    rsi
0x1400079e0  push    rdi
0x1400079e1  sub     rsp, 28h
0x1400079e5  xor     al, al
0x1400079e7  mov     byte ptr [r8], 0
0x1400079eb  mov     rbp, r9
0x1400079ee  mov     rdi, r8
0x1400079f1  mov     rsi, rdx
0x1400079f4  mov     rbx, rcx
0x1400079f7  test    rdx, rdx
0x1400079fa  jz      loc_140007AAF
0x140007a00  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140007a04  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140007a09  mov     rdx, [rsi+20h]
0x140007a0d  test    rdx, rdx
0x140007a10  jz      loc_140007AAF
0x140007a16  cmp     dword ptr [rdx], 0
0x140007a19  jnz     short loc_140007A2C
0x140007a1b  mov     eax, 1
0x140007a20  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140007a28  inc     eax
0x140007a2a  mov     [rdx], eax
0x140007a2c  cmp     dword ptr [rbx+50h], 0
0x140007a30  jnz     short loc_140007A43
0x140007a32  movups  xmm0, xmmword ptr [rdx]
0x140007a35  movups  xmmword ptr [rbx+50h], xmm0
0x140007a39  movsd   xmm1, qword ptr [rdx+10h]
0x140007a3e  movsd   qword ptr [rbx+60h], xmm1
0x140007a43  movups  xmm0, xmmword ptr [rdx]
0x140007a46  lea     r10, [rdi+rbp]
0x140007a4a  movups  xmmword ptr [rbx+68h], xmm0
0x140007a4e  movsd   xmm1, qword ptr [rdx+10h]
0x140007a53  movsd   qword ptr [rbx+78h], xmm1
0x140007a58  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140007a5c  mov     rax, rbx
0x140007a5f  inc     rax
0x140007a62  cmp     byte ptr [rdi+rax], 0
0x140007a66  jnz     short loc_140007A5F
0x140007a68  lea     rcx, [rax+rdi]
0x140007a6c  mov     rax, r10
0x140007a6f  sub     rax, rcx
0x140007a72  cmp     rax, 2
0x140007a76  jle     short loc_140007AAD
0x140007a78  mov     byte ptr [rcx], 5Ch ; '\'
0x140007a7b  lea     rdi, [rcx+1]
0x140007a7f  mov     r8, [rdx+8]; Source
0x140007a83  inc     rbx
0x140007a86  cmp     byte ptr [r8+rbx], 0
0x140007a8b  jnz     short loc_140007A83
0x140007a8d  sub     r10, rdi
0x140007a90  inc     rbx
0x140007a93  cmp     rbx, r10
0x140007a96  mov     rdx, r10; DestinationSize
0x140007a99  mov     rcx, rdi; Destination
0x140007a9c  cmovnb  rbx, r10
0x140007aa0  mov     r9, rbx; SourceSize
0x140007aa3  call    memcpy_s
0x140007aa8  mov     byte ptr [rbx+rdi-1], 0
0x140007aad  mov     al, 1
0x140007aaf  add     rsp, 28h
0x140007ab3  pop     rdi
0x140007ab4  pop     rsi
0x140007ab5  pop     rbp
0x140007ab6  pop     rbx
0x140007ab7  retn
```
