# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180003c2c`
- end: `0x180003d08`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003530`
- `0x180003c2c`

## callees

- `0x180003c2c`
- `0x180005a48`

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
0x180003c2c  push    rbx
0x180003c2e  push    rbp
0x180003c2f  push    rsi
0x180003c30  push    rdi
0x180003c31  sub     rsp, 28h
0x180003c35  xor     al, al
0x180003c37  mov     byte ptr [r8], 0
0x180003c3b  mov     rbp, r9
0x180003c3e  mov     rdi, r8
0x180003c41  mov     rsi, rdx
0x180003c44  mov     rbx, rcx
0x180003c47  test    rdx, rdx
0x180003c4a  jz      loc_180003CFF
0x180003c50  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180003c54  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003c59  mov     rdx, [rsi+20h]
0x180003c5d  test    rdx, rdx
0x180003c60  jz      loc_180003CFF
0x180003c66  cmp     dword ptr [rdx], 0
0x180003c69  jnz     short loc_180003C7C
0x180003c6b  mov     eax, 1
0x180003c70  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180003c78  inc     eax
0x180003c7a  mov     [rdx], eax
0x180003c7c  cmp     dword ptr [rbx+50h], 0
0x180003c80  jnz     short loc_180003C93
0x180003c82  movups  xmm0, xmmword ptr [rdx]
0x180003c85  movups  xmmword ptr [rbx+50h], xmm0
0x180003c89  movsd   xmm1, qword ptr [rdx+10h]
0x180003c8e  movsd   qword ptr [rbx+60h], xmm1
0x180003c93  movups  xmm0, xmmword ptr [rdx]
0x180003c96  lea     r10, [rdi+rbp]
0x180003c9a  movups  xmmword ptr [rbx+68h], xmm0
0x180003c9e  movsd   xmm1, qword ptr [rdx+10h]
0x180003ca3  movsd   qword ptr [rbx+78h], xmm1
0x180003ca8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003cac  mov     rax, rbx
0x180003caf  inc     rax
0x180003cb2  cmp     byte ptr [rdi+rax], 0
0x180003cb6  jnz     short loc_180003CAF
0x180003cb8  lea     rcx, [rax+rdi]
0x180003cbc  mov     rax, r10
0x180003cbf  sub     rax, rcx
0x180003cc2  cmp     rax, 2
0x180003cc6  jle     short loc_180003CFD
0x180003cc8  mov     byte ptr [rcx], 5Ch ; '\'
0x180003ccb  lea     rdi, [rcx+1]
0x180003ccf  mov     r8, [rdx+8]; Source
0x180003cd3  inc     rbx
0x180003cd6  cmp     byte ptr [r8+rbx], 0
0x180003cdb  jnz     short loc_180003CD3
0x180003cdd  sub     r10, rdi
0x180003ce0  inc     rbx
0x180003ce3  cmp     rbx, r10
0x180003ce6  mov     rdx, r10; DestinationSize
0x180003ce9  mov     rcx, rdi; Destination
0x180003cec  cmovnb  rbx, r10
0x180003cf0  mov     r9, rbx; SourceSize
0x180003cf3  call    memcpy_s
0x180003cf8  mov     byte ptr [rbx+rdi-1], 0
0x180003cfd  mov     al, 1
0x180003cff  add     rsp, 28h
0x180003d03  pop     rdi
0x180003d04  pop     rsi
0x180003d05  pop     rbp
0x180003d06  pop     rbx
0x180003d07  retn
```
