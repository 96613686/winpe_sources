# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140005ba0`
- end: `0x140005c7c`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004dd0`
- `0x140005ba0`

## callees

- `0x140005ba0`
- `0x14000a570`

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
0x140005ba0  push    rbx
0x140005ba2  push    rbp
0x140005ba3  push    rsi
0x140005ba4  push    rdi
0x140005ba5  sub     rsp, 28h
0x140005ba9  xor     al, al
0x140005bab  mov     byte ptr [r8], 0
0x140005baf  mov     rbp, r9
0x140005bb2  mov     rdi, r8
0x140005bb5  mov     rsi, rdx
0x140005bb8  mov     rbx, rcx
0x140005bbb  test    rdx, rdx
0x140005bbe  jz      loc_140005C73
0x140005bc4  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140005bc8  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140005bcd  mov     rdx, [rsi+20h]
0x140005bd1  test    rdx, rdx
0x140005bd4  jz      loc_140005C73
0x140005bda  cmp     dword ptr [rdx], 0
0x140005bdd  jnz     short loc_140005BF0
0x140005bdf  mov     eax, 1
0x140005be4  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140005bec  inc     eax
0x140005bee  mov     [rdx], eax
0x140005bf0  cmp     dword ptr [rbx+50h], 0
0x140005bf4  jnz     short loc_140005C07
0x140005bf6  movups  xmm0, xmmword ptr [rdx]
0x140005bf9  movups  xmmword ptr [rbx+50h], xmm0
0x140005bfd  movsd   xmm1, qword ptr [rdx+10h]
0x140005c02  movsd   qword ptr [rbx+60h], xmm1
0x140005c07  movups  xmm0, xmmword ptr [rdx]
0x140005c0a  lea     r10, [rdi+rbp]
0x140005c0e  movups  xmmword ptr [rbx+68h], xmm0
0x140005c12  movsd   xmm1, qword ptr [rdx+10h]
0x140005c17  movsd   qword ptr [rbx+78h], xmm1
0x140005c1c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140005c20  mov     rax, rbx
0x140005c23  inc     rax
0x140005c26  cmp     byte ptr [rdi+rax], 0
0x140005c2a  jnz     short loc_140005C23
0x140005c2c  lea     rcx, [rax+rdi]
0x140005c30  mov     rax, r10
0x140005c33  sub     rax, rcx
0x140005c36  cmp     rax, 2
0x140005c3a  jle     short loc_140005C71
0x140005c3c  mov     byte ptr [rcx], 5Ch ; '\'
0x140005c3f  lea     rdi, [rcx+1]
0x140005c43  mov     r8, [rdx+8]; Source
0x140005c47  inc     rbx
0x140005c4a  cmp     byte ptr [r8+rbx], 0
0x140005c4f  jnz     short loc_140005C47
0x140005c51  sub     r10, rdi
0x140005c54  inc     rbx
0x140005c57  cmp     rbx, r10
0x140005c5a  mov     rdx, r10; DestinationSize
0x140005c5d  mov     rcx, rdi; Destination
0x140005c60  cmovnb  rbx, r10
0x140005c64  mov     r9, rbx; SourceSize
0x140005c67  call    memcpy_s
0x140005c6c  mov     byte ptr [rbx+rdi-1], 0
0x140005c71  mov     al, 1
0x140005c73  add     rsp, 28h
0x140005c77  pop     rdi
0x140005c78  pop     rsi
0x140005c79  pop     rbp
0x140005c7a  pop     rbx
0x140005c7b  retn
```
