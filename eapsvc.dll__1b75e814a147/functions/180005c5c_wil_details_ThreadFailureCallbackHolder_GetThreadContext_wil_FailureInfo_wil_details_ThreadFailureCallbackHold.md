# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180005c5c`
- end: `0x180005d38`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005560`
- `0x180005c5c`

## callees

- `0x180005c5c`
- `0x180009fe8`

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
0x180005c5c  push    rbx
0x180005c5e  push    rbp
0x180005c5f  push    rsi
0x180005c60  push    rdi
0x180005c61  sub     rsp, 28h
0x180005c65  xor     al, al
0x180005c67  mov     byte ptr [r8], 0
0x180005c6b  mov     rbp, r9
0x180005c6e  mov     rdi, r8
0x180005c71  mov     rsi, rdx
0x180005c74  mov     rbx, rcx
0x180005c77  test    rdx, rdx
0x180005c7a  jz      loc_180005D2F
0x180005c80  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180005c84  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005c89  mov     rdx, [rsi+20h]
0x180005c8d  test    rdx, rdx
0x180005c90  jz      loc_180005D2F
0x180005c96  cmp     dword ptr [rdx], 0
0x180005c99  jnz     short loc_180005CAC
0x180005c9b  mov     eax, 1
0x180005ca0  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180005ca8  inc     eax
0x180005caa  mov     [rdx], eax
0x180005cac  cmp     dword ptr [rbx+50h], 0
0x180005cb0  jnz     short loc_180005CC3
0x180005cb2  movups  xmm0, xmmword ptr [rdx]
0x180005cb5  movups  xmmword ptr [rbx+50h], xmm0
0x180005cb9  movsd   xmm1, qword ptr [rdx+10h]
0x180005cbe  movsd   qword ptr [rbx+60h], xmm1
0x180005cc3  movups  xmm0, xmmword ptr [rdx]
0x180005cc6  lea     r10, [rdi+rbp]
0x180005cca  movups  xmmword ptr [rbx+68h], xmm0
0x180005cce  movsd   xmm1, qword ptr [rdx+10h]
0x180005cd3  movsd   qword ptr [rbx+78h], xmm1
0x180005cd8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005cdc  mov     rax, rbx
0x180005cdf  inc     rax
0x180005ce2  cmp     byte ptr [rdi+rax], 0
0x180005ce6  jnz     short loc_180005CDF
0x180005ce8  lea     rcx, [rax+rdi]
0x180005cec  mov     rax, r10
0x180005cef  sub     rax, rcx
0x180005cf2  cmp     rax, 2
0x180005cf6  jle     short loc_180005D2D
0x180005cf8  mov     byte ptr [rcx], 5Ch ; '\'
0x180005cfb  lea     rdi, [rcx+1]
0x180005cff  mov     r8, [rdx+8]; Source
0x180005d03  inc     rbx
0x180005d06  cmp     byte ptr [r8+rbx], 0
0x180005d0b  jnz     short loc_180005D03
0x180005d0d  sub     r10, rdi
0x180005d10  inc     rbx
0x180005d13  cmp     rbx, r10
0x180005d16  mov     rdx, r10; DestinationSize
0x180005d19  mov     rcx, rdi; Destination
0x180005d1c  cmovnb  rbx, r10
0x180005d20  mov     r9, rbx; SourceSize
0x180005d23  call    memcpy_s
0x180005d28  mov     byte ptr [rbx+rdi-1], 0
0x180005d2d  mov     al, 1
0x180005d2f  add     rsp, 28h
0x180005d33  pop     rdi
0x180005d34  pop     rsi
0x180005d35  pop     rbp
0x180005d36  pop     rbx
0x180005d37  retn
```
