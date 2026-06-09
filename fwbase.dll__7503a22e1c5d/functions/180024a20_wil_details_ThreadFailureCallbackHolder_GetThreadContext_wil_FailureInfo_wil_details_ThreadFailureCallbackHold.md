# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180024a20`
- end: `0x180024b0b`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `235`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800242b0`
- `0x180024a20`

## callees

- `0x180024a20`
- `0x180029fd0`

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
  char *v14; // rcx
  char *v15; // rdi
  _BYTE *v16; // r8
  rsize_t v17; // r10
  rsize_t v18; // rbx
  void *v19; // rcx

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
      while ( a3[++v12] != 0 )
        ;
      v14 = &a3[v12];
      if ( (__int64)(a4 - v12) > 2 )
      {
        *v14 = 92;
        v15 = v14 + 1;
        v16 = (_BYTE *)*((_QWORD *)v9 + 1);
        do
          ++v11;
        while ( v16[v11] );
        v17 = v10 - v15;
        v18 = v11 + 1;
        v19 = v14 + 1;
        if ( v18 >= v17 )
          v18 = v17;
        memcpy_s(v19, v17, v16, v18);
        v15[v18 - 1] = 0;
      }
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180024a20  push    rbx
0x180024a22  push    rbp
0x180024a23  push    rsi
0x180024a24  push    rdi
0x180024a25  sub     rsp, 28h
0x180024a29  xor     al, al
0x180024a2b  mov     byte ptr [r8], 0
0x180024a2f  mov     rbp, r9
0x180024a32  mov     rdi, r8
0x180024a35  mov     rsi, rdx
0x180024a38  mov     rbx, rcx
0x180024a3b  test    rdx, rdx
0x180024a3e  jz      loc_180024B02
0x180024a44  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180024a48  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180024a4d  mov     rdx, [rsi+20h]
0x180024a51  test    rdx, rdx
0x180024a54  jz      loc_180024B02
0x180024a5a  cmp     dword ptr [rdx], 0
0x180024a5d  jnz     short loc_180024A70
0x180024a5f  mov     eax, 1
0x180024a64  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180024a6c  inc     eax
0x180024a6e  mov     [rdx], eax
0x180024a70  cmp     dword ptr [rbx+50h], 0
0x180024a74  jnz     short loc_180024A87
0x180024a76  movups  xmm0, xmmword ptr [rdx]
0x180024a79  movups  xmmword ptr [rbx+50h], xmm0
0x180024a7d  movsd   xmm1, qword ptr [rdx+10h]
0x180024a82  movsd   qword ptr [rbx+60h], xmm1
0x180024a87  movups  xmm0, xmmword ptr [rdx]
0x180024a8a  lea     r10, [rdi+rbp]
0x180024a8e  movups  xmmword ptr [rbx+68h], xmm0
0x180024a92  movsd   xmm1, qword ptr [rdx+10h]
0x180024a97  movsd   qword ptr [rbx+78h], xmm1
0x180024a9c  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180024aa3  mov     rax, rbx
0x180024aa6  nop     word ptr [rax+rax+00000000h]
0x180024ab0  cmp     byte ptr [rdi+rax+1], 0
0x180024ab5  lea     rax, [rax+1]
0x180024ab9  jnz     short loc_180024AB0
0x180024abb  lea     rcx, [rax+rdi]
0x180024abf  mov     rax, r10
0x180024ac2  sub     rax, rcx
0x180024ac5  cmp     rax, 2
0x180024ac9  jle     short loc_180024B00
0x180024acb  mov     byte ptr [rcx], 5Ch ; '\'
0x180024ace  lea     rdi, [rcx+1]
0x180024ad2  mov     r8, [rdx+8]; Source
0x180024ad6  inc     rbx
0x180024ad9  cmp     byte ptr [r8+rbx], 0
0x180024ade  jnz     short loc_180024AD6
0x180024ae0  sub     r10, rdi
0x180024ae3  inc     rbx
0x180024ae6  cmp     rbx, r10
0x180024ae9  mov     rdx, r10; DestinationSize
0x180024aec  mov     rcx, rdi; Destination
0x180024aef  cmovnb  rbx, r10
0x180024af3  mov     r9, rbx; SourceSize
0x180024af6  call    memcpy_s
0x180024afb  mov     byte ptr [rbx+rdi-1], 0
0x180024b00  mov     al, 1
0x180024b02  add     rsp, 28h
0x180024b06  pop     rdi
0x180024b07  pop     rsi
0x180024b08  pop     rbp
0x180024b09  pop     rbx
0x180024b0a  retn
```
