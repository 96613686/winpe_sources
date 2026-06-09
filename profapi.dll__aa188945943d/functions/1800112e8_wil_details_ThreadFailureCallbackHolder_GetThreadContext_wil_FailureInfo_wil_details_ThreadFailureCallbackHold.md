# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1800112e8`
- end: `0x1800113c4`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000204c`
- `0x1800112e8`

## callees

- `0x18000f160`
- `0x1800112e8`

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
0x1800112e8  push    rbx
0x1800112ea  push    rbp
0x1800112eb  push    rsi
0x1800112ec  push    rdi
0x1800112ed  sub     rsp, 28h
0x1800112f1  xor     al, al
0x1800112f3  mov     byte ptr [r8], 0
0x1800112f7  mov     rbp, r9
0x1800112fa  mov     rdi, r8
0x1800112fd  mov     rsi, rdx
0x180011300  mov     rbx, rcx
0x180011303  test    rdx, rdx
0x180011306  jz      loc_1800113BB
0x18001130c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180011310  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180011315  mov     rdx, [rsi+20h]
0x180011319  test    rdx, rdx
0x18001131c  jz      loc_1800113BB
0x180011322  cmp     dword ptr [rdx], 0
0x180011325  jnz     short loc_180011338
0x180011327  mov     eax, 1
0x18001132c  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180011334  inc     eax
0x180011336  mov     [rdx], eax
0x180011338  cmp     dword ptr [rbx+50h], 0
0x18001133c  jnz     short loc_18001134F
0x18001133e  movups  xmm0, xmmword ptr [rdx]
0x180011341  movups  xmmword ptr [rbx+50h], xmm0
0x180011345  movsd   xmm1, qword ptr [rdx+10h]
0x18001134a  movsd   qword ptr [rbx+60h], xmm1
0x18001134f  movups  xmm0, xmmword ptr [rdx]
0x180011352  lea     r10, [rdi+rbp]
0x180011356  movups  xmmword ptr [rbx+68h], xmm0
0x18001135a  movsd   xmm1, qword ptr [rdx+10h]
0x18001135f  movsd   qword ptr [rbx+78h], xmm1
0x180011364  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180011368  mov     rax, rbx
0x18001136b  inc     rax
0x18001136e  cmp     byte ptr [rdi+rax], 0
0x180011372  jnz     short loc_18001136B
0x180011374  lea     rcx, [rax+rdi]
0x180011378  mov     rax, r10
0x18001137b  sub     rax, rcx
0x18001137e  cmp     rax, 2
0x180011382  jle     short loc_1800113B9
0x180011384  mov     byte ptr [rcx], 5Ch ; '\'
0x180011387  lea     rdi, [rcx+1]
0x18001138b  mov     r8, [rdx+8]; Source
0x18001138f  inc     rbx
0x180011392  cmp     byte ptr [r8+rbx], 0
0x180011397  jnz     short loc_18001138F
0x180011399  sub     r10, rdi
0x18001139c  inc     rbx
0x18001139f  cmp     rbx, r10
0x1800113a2  mov     rdx, r10; DestinationSize
0x1800113a5  mov     rcx, rdi; Destination
0x1800113a8  cmovnb  rbx, r10
0x1800113ac  mov     r9, rbx; SourceSize
0x1800113af  call    memcpy_s
0x1800113b4  mov     byte ptr [rbx+rdi-1], 0
0x1800113b9  mov     al, 1
0x1800113bb  add     rsp, 28h
0x1800113bf  pop     rdi
0x1800113c0  pop     rsi
0x1800113c1  pop     rbp
0x1800113c2  pop     rbx
0x1800113c3  retn
```
