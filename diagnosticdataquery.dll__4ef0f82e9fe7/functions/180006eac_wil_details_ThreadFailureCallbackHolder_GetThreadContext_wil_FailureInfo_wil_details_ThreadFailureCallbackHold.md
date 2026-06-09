# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180006eac`
- end: `0x180006f88`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800067b0`
- `0x180006eac`

## callees

- `0x180006eac`
- `0x180008b78`

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
0x180006eac  push    rbx
0x180006eae  push    rbp
0x180006eaf  push    rsi
0x180006eb0  push    rdi
0x180006eb1  sub     rsp, 28h
0x180006eb5  xor     al, al
0x180006eb7  mov     byte ptr [r8], 0
0x180006ebb  mov     rbp, r9
0x180006ebe  mov     rdi, r8
0x180006ec1  mov     rsi, rdx
0x180006ec4  mov     rbx, rcx
0x180006ec7  test    rdx, rdx
0x180006eca  jz      loc_180006F7F
0x180006ed0  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180006ed4  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006ed9  mov     rdx, [rsi+20h]
0x180006edd  test    rdx, rdx
0x180006ee0  jz      loc_180006F7F
0x180006ee6  cmp     dword ptr [rdx], 0
0x180006ee9  jnz     short loc_180006EFC
0x180006eeb  mov     eax, 1
0x180006ef0  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180006ef8  inc     eax
0x180006efa  mov     [rdx], eax
0x180006efc  cmp     dword ptr [rbx+50h], 0
0x180006f00  jnz     short loc_180006F13
0x180006f02  movups  xmm0, xmmword ptr [rdx]
0x180006f05  movups  xmmword ptr [rbx+50h], xmm0
0x180006f09  movsd   xmm1, qword ptr [rdx+10h]
0x180006f0e  movsd   qword ptr [rbx+60h], xmm1
0x180006f13  movups  xmm0, xmmword ptr [rdx]
0x180006f16  lea     r10, [rdi+rbp]
0x180006f1a  movups  xmmword ptr [rbx+68h], xmm0
0x180006f1e  movsd   xmm1, qword ptr [rdx+10h]
0x180006f23  movsd   qword ptr [rbx+78h], xmm1
0x180006f28  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006f2c  mov     rax, rbx
0x180006f2f  inc     rax
0x180006f32  cmp     byte ptr [rdi+rax], 0
0x180006f36  jnz     short loc_180006F2F
0x180006f38  lea     rcx, [rax+rdi]
0x180006f3c  mov     rax, r10
0x180006f3f  sub     rax, rcx
0x180006f42  cmp     rax, 2
0x180006f46  jle     short loc_180006F7D
0x180006f48  mov     byte ptr [rcx], 5Ch ; '\'
0x180006f4b  lea     rdi, [rcx+1]
0x180006f4f  mov     r8, [rdx+8]; Source
0x180006f53  inc     rbx
0x180006f56  cmp     byte ptr [r8+rbx], 0
0x180006f5b  jnz     short loc_180006F53
0x180006f5d  sub     r10, rdi
0x180006f60  inc     rbx
0x180006f63  cmp     rbx, r10
0x180006f66  mov     rdx, r10; DestinationSize
0x180006f69  mov     rcx, rdi; Destination
0x180006f6c  cmovnb  rbx, r10
0x180006f70  mov     r9, rbx; SourceSize
0x180006f73  call    memcpy_s
0x180006f78  mov     byte ptr [rbx+rdi-1], 0
0x180006f7d  mov     al, 1
0x180006f7f  add     rsp, 28h
0x180006f83  pop     rdi
0x180006f84  pop     rsi
0x180006f85  pop     rbp
0x180006f86  pop     rbx
0x180006f87  retn
```
