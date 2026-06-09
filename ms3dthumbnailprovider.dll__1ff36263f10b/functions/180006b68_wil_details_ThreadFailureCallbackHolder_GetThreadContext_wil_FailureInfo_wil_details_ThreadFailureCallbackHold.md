# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180006b68`
- end: `0x180006c44`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800063a0`
- `0x180006b68`

## callees

- `0x180006b68`
- `0x180009c08`

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
0x180006b68  push    rbx
0x180006b6a  push    rbp
0x180006b6b  push    rsi
0x180006b6c  push    rdi
0x180006b6d  sub     rsp, 28h
0x180006b71  xor     al, al
0x180006b73  mov     byte ptr [r8], 0
0x180006b77  mov     rbp, r9
0x180006b7a  mov     rdi, r8
0x180006b7d  mov     rsi, rdx
0x180006b80  mov     rbx, rcx
0x180006b83  test    rdx, rdx
0x180006b86  jz      loc_180006C3B
0x180006b8c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180006b90  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006b95  mov     rdx, [rsi+20h]
0x180006b99  test    rdx, rdx
0x180006b9c  jz      loc_180006C3B
0x180006ba2  cmp     dword ptr [rdx], 0
0x180006ba5  jnz     short loc_180006BB8
0x180006ba7  mov     eax, 1
0x180006bac  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180006bb4  inc     eax
0x180006bb6  mov     [rdx], eax
0x180006bb8  cmp     dword ptr [rbx+50h], 0
0x180006bbc  jnz     short loc_180006BCF
0x180006bbe  movups  xmm0, xmmword ptr [rdx]
0x180006bc1  movups  xmmword ptr [rbx+50h], xmm0
0x180006bc5  movsd   xmm1, qword ptr [rdx+10h]
0x180006bca  movsd   qword ptr [rbx+60h], xmm1
0x180006bcf  movups  xmm0, xmmword ptr [rdx]
0x180006bd2  lea     r10, [rdi+rbp]
0x180006bd6  movups  xmmword ptr [rbx+68h], xmm0
0x180006bda  movsd   xmm1, qword ptr [rdx+10h]
0x180006bdf  movsd   qword ptr [rbx+78h], xmm1
0x180006be4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006be8  mov     rax, rbx
0x180006beb  inc     rax
0x180006bee  cmp     byte ptr [rdi+rax], 0
0x180006bf2  jnz     short loc_180006BEB
0x180006bf4  lea     rcx, [rax+rdi]
0x180006bf8  mov     rax, r10
0x180006bfb  sub     rax, rcx
0x180006bfe  cmp     rax, 2
0x180006c02  jle     short loc_180006C39
0x180006c04  mov     byte ptr [rcx], 5Ch ; '\'
0x180006c07  lea     rdi, [rcx+1]
0x180006c0b  mov     r8, [rdx+8]; Source
0x180006c0f  inc     rbx
0x180006c12  cmp     byte ptr [r8+rbx], 0
0x180006c17  jnz     short loc_180006C0F
0x180006c19  sub     r10, rdi
0x180006c1c  inc     rbx
0x180006c1f  cmp     rbx, r10
0x180006c22  mov     rdx, r10; DestinationSize
0x180006c25  mov     rcx, rdi; Destination
0x180006c28  cmovnb  rbx, r10
0x180006c2c  mov     r9, rbx; SourceSize
0x180006c2f  call    memcpy_s
0x180006c34  mov     byte ptr [rbx+rdi-1], 0
0x180006c39  mov     al, 1
0x180006c3b  add     rsp, 28h
0x180006c3f  pop     rdi
0x180006c40  pop     rsi
0x180006c41  pop     rbp
0x180006c42  pop     rbx
0x180006c43  retn
```
