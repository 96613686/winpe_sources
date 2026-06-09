# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140003ab8`
- end: `0x140003b95`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140003440`
- `0x140003ab8`

## callees

- `0x140003ab8`
- `0x1400059dc`

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
0x140003ab8  push    rbx
0x140003aba  push    rbp
0x140003abb  push    rsi
0x140003abc  push    rdi
0x140003abd  sub     rsp, 28h
0x140003ac1  xor     al, al
0x140003ac3  mov     byte ptr [r8], 0
0x140003ac7  mov     rbp, r9
0x140003aca  mov     rdi, r8
0x140003acd  mov     rsi, rdx
0x140003ad0  mov     rbx, rcx
0x140003ad3  test    rdx, rdx
0x140003ad6  jz      loc_140003B8B
0x140003adc  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140003ae0  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140003ae5  mov     rdx, [rsi+20h]
0x140003ae9  test    rdx, rdx
0x140003aec  jz      loc_140003B8B
0x140003af2  cmp     dword ptr [rdx], 0
0x140003af5  jnz     short loc_140003B08
0x140003af7  mov     eax, 1
0x140003afc  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140003b04  inc     eax
0x140003b06  mov     [rdx], eax
0x140003b08  cmp     dword ptr [rbx+50h], 0
0x140003b0c  jnz     short loc_140003B1F
0x140003b0e  movups  xmm0, xmmword ptr [rdx]
0x140003b11  movups  xmmword ptr [rbx+50h], xmm0
0x140003b15  movsd   xmm1, qword ptr [rdx+10h]
0x140003b1a  movsd   qword ptr [rbx+60h], xmm1
0x140003b1f  movups  xmm0, xmmword ptr [rdx]
0x140003b22  lea     r10, [rdi+rbp]
0x140003b26  movups  xmmword ptr [rbx+68h], xmm0
0x140003b2a  movsd   xmm1, qword ptr [rdx+10h]
0x140003b2f  movsd   qword ptr [rbx+78h], xmm1
0x140003b34  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140003b38  mov     rax, rbx
0x140003b3b  inc     rax
0x140003b3e  cmp     byte ptr [rdi+rax], 0
0x140003b42  jnz     short loc_140003B3B
0x140003b44  lea     rcx, [rax+rdi]
0x140003b48  mov     rax, r10
0x140003b4b  sub     rax, rcx
0x140003b4e  cmp     rax, 2
0x140003b52  jle     short loc_140003B89
0x140003b54  mov     byte ptr [rcx], 5Ch ; '\'
0x140003b57  lea     rdi, [rcx+1]
0x140003b5b  mov     r8, [rdx+8]; Source
0x140003b5f  inc     rbx
0x140003b62  cmp     byte ptr [r8+rbx], 0
0x140003b67  jnz     short loc_140003B5F
0x140003b69  sub     r10, rdi
0x140003b6c  inc     rbx
0x140003b6f  cmp     rbx, r10
0x140003b72  mov     rdx, r10; DestinationSize
0x140003b75  mov     rcx, rdi; Destination
0x140003b78  cmovnb  rbx, r10
0x140003b7c  mov     r9, rbx; SourceSize
0x140003b7f  call    memcpy_s
0x140003b84  mov     byte ptr [rbx+rdi-1], 0
0x140003b89  mov     al, 1
0x140003b8b  add     rsp, 28h
0x140003b8f  pop     rdi
0x140003b90  pop     rsi
0x140003b91  pop     rbp
0x140003b92  pop     rbx
0x140003b93  retn
```
