# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180010734`
- end: `0x180010810`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800100d4`
- `0x180010734`

## callees

- `0x180010734`
- `0x180014cf4`

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
0x180010734  push    rbx
0x180010736  push    rbp
0x180010737  push    rsi
0x180010738  push    rdi
0x180010739  sub     rsp, 28h
0x18001073d  xor     al, al
0x18001073f  mov     byte ptr [r8], 0
0x180010743  mov     rbp, r9
0x180010746  mov     rdi, r8
0x180010749  mov     rsi, rdx
0x18001074c  mov     rbx, rcx
0x18001074f  test    rdx, rdx
0x180010752  jz      loc_180010807
0x180010758  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18001075c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180010761  mov     rdx, [rsi+20h]
0x180010765  test    rdx, rdx
0x180010768  jz      loc_180010807
0x18001076e  cmp     dword ptr [rdx], 0
0x180010771  jnz     short loc_180010784
0x180010773  mov     eax, 1
0x180010778  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180010780  inc     eax
0x180010782  mov     [rdx], eax
0x180010784  cmp     dword ptr [rbx+50h], 0
0x180010788  jnz     short loc_18001079B
0x18001078a  movups  xmm0, xmmword ptr [rdx]
0x18001078d  movups  xmmword ptr [rbx+50h], xmm0
0x180010791  movsd   xmm1, qword ptr [rdx+10h]
0x180010796  movsd   qword ptr [rbx+60h], xmm1
0x18001079b  movups  xmm0, xmmword ptr [rdx]
0x18001079e  lea     r10, [rdi+rbp]
0x1800107a2  movups  xmmword ptr [rbx+68h], xmm0
0x1800107a6  movsd   xmm1, qword ptr [rdx+10h]
0x1800107ab  movsd   qword ptr [rbx+78h], xmm1
0x1800107b0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800107b4  mov     rax, rbx
0x1800107b7  inc     rax
0x1800107ba  cmp     byte ptr [rdi+rax], 0
0x1800107be  jnz     short loc_1800107B7
0x1800107c0  lea     rcx, [rax+rdi]
0x1800107c4  mov     rax, r10
0x1800107c7  sub     rax, rcx
0x1800107ca  cmp     rax, 2
0x1800107ce  jle     short loc_180010805
0x1800107d0  mov     byte ptr [rcx], 5Ch ; '\'
0x1800107d3  lea     rdi, [rcx+1]
0x1800107d7  mov     r8, [rdx+8]; Source
0x1800107db  inc     rbx
0x1800107de  cmp     byte ptr [r8+rbx], 0
0x1800107e3  jnz     short loc_1800107DB
0x1800107e5  sub     r10, rdi
0x1800107e8  inc     rbx
0x1800107eb  cmp     rbx, r10
0x1800107ee  mov     rdx, r10; DestinationSize
0x1800107f1  mov     rcx, rdi; Destination
0x1800107f4  cmovnb  rbx, r10
0x1800107f8  mov     r9, rbx; SourceSize
0x1800107fb  call    memcpy_s
0x180010800  mov     byte ptr [rbx+rdi-1], 0
0x180010805  mov     al, 1
0x180010807  add     rsp, 28h
0x18001080b  pop     rdi
0x18001080c  pop     rsi
0x18001080d  pop     rbp
0x18001080e  pop     rbx
0x18001080f  retn
```
