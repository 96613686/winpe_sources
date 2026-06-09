# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000d2a0`
- end: `0x18000d37c`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c7b0`
- `0x18000d2a0`

## callees

- `0x18000d2a0`
- `0x1800196f0`

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
0x18000d2a0  push    rbx
0x18000d2a2  push    rbp
0x18000d2a3  push    rsi
0x18000d2a4  push    rdi
0x18000d2a5  sub     rsp, 28h
0x18000d2a9  xor     al, al
0x18000d2ab  mov     byte ptr [r8], 0
0x18000d2af  mov     rbp, r9
0x18000d2b2  mov     rdi, r8
0x18000d2b5  mov     rsi, rdx
0x18000d2b8  mov     rbx, rcx
0x18000d2bb  test    rdx, rdx
0x18000d2be  jz      loc_18000D373
0x18000d2c4  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18000d2c8  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000d2cd  mov     rdx, [rsi+20h]
0x18000d2d1  test    rdx, rdx
0x18000d2d4  jz      loc_18000D373
0x18000d2da  cmp     dword ptr [rdx], 0
0x18000d2dd  jnz     short loc_18000D2F0
0x18000d2df  mov     eax, 1
0x18000d2e4  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000d2ec  inc     eax
0x18000d2ee  mov     [rdx], eax
0x18000d2f0  cmp     dword ptr [rbx+50h], 0
0x18000d2f4  jnz     short loc_18000D307
0x18000d2f6  movups  xmm0, xmmword ptr [rdx]
0x18000d2f9  movups  xmmword ptr [rbx+50h], xmm0
0x18000d2fd  movsd   xmm1, qword ptr [rdx+10h]
0x18000d302  movsd   qword ptr [rbx+60h], xmm1
0x18000d307  movups  xmm0, xmmword ptr [rdx]
0x18000d30a  lea     r10, [rdi+rbp]
0x18000d30e  movups  xmmword ptr [rbx+68h], xmm0
0x18000d312  movsd   xmm1, qword ptr [rdx+10h]
0x18000d317  movsd   qword ptr [rbx+78h], xmm1
0x18000d31c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000d320  mov     rax, rbx
0x18000d323  inc     rax
0x18000d326  cmp     byte ptr [rdi+rax], 0
0x18000d32a  jnz     short loc_18000D323
0x18000d32c  lea     rcx, [rax+rdi]
0x18000d330  mov     rax, r10
0x18000d333  sub     rax, rcx
0x18000d336  cmp     rax, 2
0x18000d33a  jle     short loc_18000D371
0x18000d33c  mov     byte ptr [rcx], 5Ch ; '\'
0x18000d33f  lea     rdi, [rcx+1]
0x18000d343  mov     r8, [rdx+8]; Source
0x18000d347  inc     rbx
0x18000d34a  cmp     byte ptr [r8+rbx], 0
0x18000d34f  jnz     short loc_18000D347
0x18000d351  sub     r10, rdi
0x18000d354  inc     rbx
0x18000d357  cmp     rbx, r10
0x18000d35a  mov     rdx, r10; DestinationSize
0x18000d35d  mov     rcx, rdi; Destination
0x18000d360  cmovnb  rbx, r10
0x18000d364  mov     r9, rbx; SourceSize
0x18000d367  call    memcpy_s
0x18000d36c  mov     byte ptr [rbx+rdi-1], 0
0x18000d371  mov     al, 1
0x18000d373  add     rsp, 28h
0x18000d377  pop     rdi
0x18000d378  pop     rsi
0x18000d379  pop     rbp
0x18000d37a  pop     rbx
0x18000d37b  retn
```
