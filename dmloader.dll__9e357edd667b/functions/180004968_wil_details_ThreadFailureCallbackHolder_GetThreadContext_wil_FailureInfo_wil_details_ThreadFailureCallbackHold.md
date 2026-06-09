# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180004968`
- end: `0x180004a44`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004270`
- `0x180004968`

## callees

- `0x180004968`
- `0x180007de8`

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
0x180004968  push    rbx
0x18000496a  push    rbp
0x18000496b  push    rsi
0x18000496c  push    rdi
0x18000496d  sub     rsp, 28h
0x180004971  xor     al, al
0x180004973  mov     byte ptr [r8], 0
0x180004977  mov     rbp, r9
0x18000497a  mov     rdi, r8
0x18000497d  mov     rsi, rdx
0x180004980  mov     rbx, rcx
0x180004983  test    rdx, rdx
0x180004986  jz      loc_180004A3B
0x18000498c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180004990  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004995  mov     rdx, [rsi+20h]
0x180004999  test    rdx, rdx
0x18000499c  jz      loc_180004A3B
0x1800049a2  cmp     dword ptr [rdx], 0
0x1800049a5  jnz     short loc_1800049B8
0x1800049a7  mov     eax, 1
0x1800049ac  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1800049b4  inc     eax
0x1800049b6  mov     [rdx], eax
0x1800049b8  cmp     dword ptr [rbx+50h], 0
0x1800049bc  jnz     short loc_1800049CF
0x1800049be  movups  xmm0, xmmword ptr [rdx]
0x1800049c1  movups  xmmword ptr [rbx+50h], xmm0
0x1800049c5  movsd   xmm1, qword ptr [rdx+10h]
0x1800049ca  movsd   qword ptr [rbx+60h], xmm1
0x1800049cf  movups  xmm0, xmmword ptr [rdx]
0x1800049d2  lea     r10, [rdi+rbp]
0x1800049d6  movups  xmmword ptr [rbx+68h], xmm0
0x1800049da  movsd   xmm1, qword ptr [rdx+10h]
0x1800049df  movsd   qword ptr [rbx+78h], xmm1
0x1800049e4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800049e8  mov     rax, rbx
0x1800049eb  inc     rax
0x1800049ee  cmp     byte ptr [rdi+rax], 0
0x1800049f2  jnz     short loc_1800049EB
0x1800049f4  lea     rcx, [rax+rdi]
0x1800049f8  mov     rax, r10
0x1800049fb  sub     rax, rcx
0x1800049fe  cmp     rax, 2
0x180004a02  jle     short loc_180004A39
0x180004a04  mov     byte ptr [rcx], 5Ch ; '\'
0x180004a07  lea     rdi, [rcx+1]
0x180004a0b  mov     r8, [rdx+8]; Source
0x180004a0f  inc     rbx
0x180004a12  cmp     byte ptr [r8+rbx], 0
0x180004a17  jnz     short loc_180004A0F
0x180004a19  sub     r10, rdi
0x180004a1c  inc     rbx
0x180004a1f  cmp     rbx, r10
0x180004a22  mov     rdx, r10; DestinationSize
0x180004a25  mov     rcx, rdi; Destination
0x180004a28  cmovnb  rbx, r10
0x180004a2c  mov     r9, rbx; SourceSize
0x180004a2f  call    memcpy_s
0x180004a34  mov     byte ptr [rbx+rdi-1], 0
0x180004a39  mov     al, 1
0x180004a3b  add     rsp, 28h
0x180004a3f  pop     rdi
0x180004a40  pop     rsi
0x180004a41  pop     rbp
0x180004a42  pop     rbx
0x180004a43  retn
```
