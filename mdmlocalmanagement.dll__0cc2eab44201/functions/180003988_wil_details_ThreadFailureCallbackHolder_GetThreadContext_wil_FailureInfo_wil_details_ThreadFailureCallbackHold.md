# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180003988`
- end: `0x180003a65`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003310`
- `0x180003988`

## callees

- `0x180003988`
- `0x180005df8`

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
0x180003988  push    rbx
0x18000398a  push    rbp
0x18000398b  push    rsi
0x18000398c  push    rdi
0x18000398d  sub     rsp, 28h
0x180003991  xor     al, al
0x180003993  mov     byte ptr [r8], 0
0x180003997  mov     rbp, r9
0x18000399a  mov     rdi, r8
0x18000399d  mov     rsi, rdx
0x1800039a0  mov     rbx, rcx
0x1800039a3  test    rdx, rdx
0x1800039a6  jz      loc_180003A5B
0x1800039ac  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1800039b0  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800039b5  mov     rdx, [rsi+20h]
0x1800039b9  test    rdx, rdx
0x1800039bc  jz      loc_180003A5B
0x1800039c2  cmp     dword ptr [rdx], 0
0x1800039c5  jnz     short loc_1800039D8
0x1800039c7  mov     eax, 1
0x1800039cc  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1800039d4  inc     eax
0x1800039d6  mov     [rdx], eax
0x1800039d8  cmp     dword ptr [rbx+50h], 0
0x1800039dc  jnz     short loc_1800039EF
0x1800039de  movups  xmm0, xmmword ptr [rdx]
0x1800039e1  movups  xmmword ptr [rbx+50h], xmm0
0x1800039e5  movsd   xmm1, qword ptr [rdx+10h]
0x1800039ea  movsd   qword ptr [rbx+60h], xmm1
0x1800039ef  movups  xmm0, xmmword ptr [rdx]
0x1800039f2  lea     r10, [rdi+rbp]
0x1800039f6  movups  xmmword ptr [rbx+68h], xmm0
0x1800039fa  movsd   xmm1, qword ptr [rdx+10h]
0x1800039ff  movsd   qword ptr [rbx+78h], xmm1
0x180003a04  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003a08  mov     rax, rbx
0x180003a0b  inc     rax
0x180003a0e  cmp     byte ptr [rdi+rax], 0
0x180003a12  jnz     short loc_180003A0B
0x180003a14  lea     rcx, [rax+rdi]
0x180003a18  mov     rax, r10
0x180003a1b  sub     rax, rcx
0x180003a1e  cmp     rax, 2
0x180003a22  jle     short loc_180003A59
0x180003a24  mov     byte ptr [rcx], 5Ch ; '\'
0x180003a27  lea     rdi, [rcx+1]
0x180003a2b  mov     r8, [rdx+8]; Source
0x180003a2f  inc     rbx
0x180003a32  cmp     byte ptr [r8+rbx], 0
0x180003a37  jnz     short loc_180003A2F
0x180003a39  sub     r10, rdi
0x180003a3c  inc     rbx
0x180003a3f  cmp     rbx, r10
0x180003a42  mov     rdx, r10; DestinationSize
0x180003a45  mov     rcx, rdi; Destination
0x180003a48  cmovnb  rbx, r10
0x180003a4c  mov     r9, rbx; SourceSize
0x180003a4f  call    memcpy_s
0x180003a54  mov     byte ptr [rbx+rdi-1], 0
0x180003a59  mov     al, 1
0x180003a5b  add     rsp, 28h
0x180003a5f  pop     rdi
0x180003a60  pop     rsi
0x180003a61  pop     rbp
0x180003a62  pop     rbx
0x180003a63  retn
```
