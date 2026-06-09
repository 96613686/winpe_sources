# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000528c`
- end: `0x180005368`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004b90`
- `0x18000528c`

## callees

- `0x18000528c`
- `0x180009458`

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
0x18000528c  push    rbx
0x18000528e  push    rbp
0x18000528f  push    rsi
0x180005290  push    rdi
0x180005291  sub     rsp, 28h
0x180005295  xor     al, al
0x180005297  mov     byte ptr [r8], 0
0x18000529b  mov     rbp, r9
0x18000529e  mov     rdi, r8
0x1800052a1  mov     rsi, rdx
0x1800052a4  mov     rbx, rcx
0x1800052a7  test    rdx, rdx
0x1800052aa  jz      loc_18000535F
0x1800052b0  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1800052b4  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800052b9  mov     rdx, [rsi+20h]
0x1800052bd  test    rdx, rdx
0x1800052c0  jz      loc_18000535F
0x1800052c6  cmp     dword ptr [rdx], 0
0x1800052c9  jnz     short loc_1800052DC
0x1800052cb  mov     eax, 1
0x1800052d0  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1800052d8  inc     eax
0x1800052da  mov     [rdx], eax
0x1800052dc  cmp     dword ptr [rbx+50h], 0
0x1800052e0  jnz     short loc_1800052F3
0x1800052e2  movups  xmm0, xmmword ptr [rdx]
0x1800052e5  movups  xmmword ptr [rbx+50h], xmm0
0x1800052e9  movsd   xmm1, qword ptr [rdx+10h]
0x1800052ee  movsd   qword ptr [rbx+60h], xmm1
0x1800052f3  movups  xmm0, xmmword ptr [rdx]
0x1800052f6  lea     r10, [rdi+rbp]
0x1800052fa  movups  xmmword ptr [rbx+68h], xmm0
0x1800052fe  movsd   xmm1, qword ptr [rdx+10h]
0x180005303  movsd   qword ptr [rbx+78h], xmm1
0x180005308  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000530c  mov     rax, rbx
0x18000530f  inc     rax
0x180005312  cmp     byte ptr [rdi+rax], 0
0x180005316  jnz     short loc_18000530F
0x180005318  lea     rcx, [rax+rdi]
0x18000531c  mov     rax, r10
0x18000531f  sub     rax, rcx
0x180005322  cmp     rax, 2
0x180005326  jle     short loc_18000535D
0x180005328  mov     byte ptr [rcx], 5Ch ; '\'
0x18000532b  lea     rdi, [rcx+1]
0x18000532f  mov     r8, [rdx+8]; Source
0x180005333  inc     rbx
0x180005336  cmp     byte ptr [r8+rbx], 0
0x18000533b  jnz     short loc_180005333
0x18000533d  sub     r10, rdi
0x180005340  inc     rbx
0x180005343  cmp     rbx, r10
0x180005346  mov     rdx, r10; DestinationSize
0x180005349  mov     rcx, rdi; Destination
0x18000534c  cmovnb  rbx, r10
0x180005350  mov     r9, rbx; SourceSize
0x180005353  call    memcpy_s
0x180005358  mov     byte ptr [rbx+rdi-1], 0
0x18000535d  mov     al, 1
0x18000535f  add     rsp, 28h
0x180005363  pop     rdi
0x180005364  pop     rsi
0x180005365  pop     rbp
0x180005366  pop     rbx
0x180005367  retn
```
