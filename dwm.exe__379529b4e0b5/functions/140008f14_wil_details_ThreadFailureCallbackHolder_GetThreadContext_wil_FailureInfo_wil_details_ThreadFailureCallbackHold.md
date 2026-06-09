# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140008f14`
- end: `0x140008ff0`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400088c4`
- `0x140008f14`

## callees

- `0x140008f14`
- `0x14000bebc`

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
0x140008f14  push    rbx
0x140008f16  push    rbp
0x140008f17  push    rsi
0x140008f18  push    rdi
0x140008f19  sub     rsp, 28h
0x140008f1d  xor     al, al
0x140008f1f  mov     byte ptr [r8], 0
0x140008f23  mov     rbp, r9
0x140008f26  mov     rdi, r8
0x140008f29  mov     rsi, rdx
0x140008f2c  mov     rbx, rcx
0x140008f2f  test    rdx, rdx
0x140008f32  jz      loc_140008FE7
0x140008f38  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140008f3c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140008f41  mov     rdx, [rsi+20h]
0x140008f45  test    rdx, rdx
0x140008f48  jz      loc_140008FE7
0x140008f4e  cmp     dword ptr [rdx], 0
0x140008f51  jnz     short loc_140008F64
0x140008f53  mov     eax, 1
0x140008f58  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140008f60  inc     eax
0x140008f62  mov     [rdx], eax
0x140008f64  cmp     dword ptr [rbx+50h], 0
0x140008f68  jnz     short loc_140008F7B
0x140008f6a  movups  xmm0, xmmword ptr [rdx]
0x140008f6d  movups  xmmword ptr [rbx+50h], xmm0
0x140008f71  movsd   xmm1, qword ptr [rdx+10h]
0x140008f76  movsd   qword ptr [rbx+60h], xmm1
0x140008f7b  movups  xmm0, xmmword ptr [rdx]
0x140008f7e  lea     r10, [rdi+rbp]
0x140008f82  movups  xmmword ptr [rbx+68h], xmm0
0x140008f86  movsd   xmm1, qword ptr [rdx+10h]
0x140008f8b  movsd   qword ptr [rbx+78h], xmm1
0x140008f90  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140008f94  mov     rax, rbx
0x140008f97  inc     rax
0x140008f9a  cmp     byte ptr [rdi+rax], 0
0x140008f9e  jnz     short loc_140008F97
0x140008fa0  lea     rcx, [rax+rdi]
0x140008fa4  mov     rax, r10
0x140008fa7  sub     rax, rcx
0x140008faa  cmp     rax, 2
0x140008fae  jle     short loc_140008FE5
0x140008fb0  mov     byte ptr [rcx], 5Ch ; '\'
0x140008fb3  lea     rdi, [rcx+1]
0x140008fb7  mov     r8, [rdx+8]; Source
0x140008fbb  inc     rbx
0x140008fbe  cmp     byte ptr [r8+rbx], 0
0x140008fc3  jnz     short loc_140008FBB
0x140008fc5  sub     r10, rdi
0x140008fc8  inc     rbx
0x140008fcb  cmp     rbx, r10
0x140008fce  mov     rdx, r10; DestinationSize
0x140008fd1  mov     rcx, rdi; Destination
0x140008fd4  cmovnb  rbx, r10
0x140008fd8  mov     r9, rbx; SourceSize
0x140008fdb  call    memcpy_s
0x140008fe0  mov     byte ptr [rbx+rdi-1], 0
0x140008fe5  mov     al, 1
0x140008fe7  add     rsp, 28h
0x140008feb  pop     rdi
0x140008fec  pop     rsi
0x140008fed  pop     rbp
0x140008fee  pop     rbx
0x140008fef  retn
```
