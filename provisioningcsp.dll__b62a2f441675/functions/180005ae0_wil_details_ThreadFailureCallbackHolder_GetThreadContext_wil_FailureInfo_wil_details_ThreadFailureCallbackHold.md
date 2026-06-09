# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180005ae0`
- end: `0x180005bc4`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `228`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005340`
- `0x180005ae0`

## callees

- `0x180005ae0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005ba7`
- `msvcrt!memcpy_s` at `0x180005ba7`

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
0x180005ae0  push    rbx
0x180005ae2  push    rbp
0x180005ae3  push    rsi
0x180005ae4  push    rdi
0x180005ae5  sub     rsp, 28h
0x180005ae9  xor     al, al
0x180005aeb  mov     byte ptr [r8], 0
0x180005aef  mov     rbp, r9
0x180005af2  mov     rdi, r8
0x180005af5  mov     rsi, rdx
0x180005af8  mov     rbx, rcx
0x180005afb  test    rdx, rdx
0x180005afe  jz      loc_180005BBA
0x180005b04  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180005b08  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005b0d  mov     rdx, [rsi+20h]
0x180005b11  test    rdx, rdx
0x180005b14  jz      loc_180005BBA
0x180005b1a  cmp     dword ptr [rdx], 0
0x180005b1d  jnz     short loc_180005B30
0x180005b1f  mov     eax, 1
0x180005b24  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180005b2c  inc     eax
0x180005b2e  mov     [rdx], eax
0x180005b30  cmp     dword ptr [rbx+50h], 0
0x180005b34  jnz     short loc_180005B47
0x180005b36  movups  xmm0, xmmword ptr [rdx]
0x180005b39  movups  xmmword ptr [rbx+50h], xmm0
0x180005b3d  movsd   xmm1, qword ptr [rdx+10h]
0x180005b42  movsd   qword ptr [rbx+60h], xmm1
0x180005b47  movups  xmm0, xmmword ptr [rdx]
0x180005b4a  lea     r10, [rdi+rbp]
0x180005b4e  movups  xmmword ptr [rbx+68h], xmm0
0x180005b52  movsd   xmm1, qword ptr [rdx+10h]
0x180005b57  movsd   qword ptr [rbx+78h], xmm1
0x180005b5c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005b60  mov     rax, rbx
0x180005b63  inc     rax
0x180005b66  cmp     byte ptr [rdi+rax], 0
0x180005b6a  jnz     short loc_180005B63
0x180005b6c  lea     rcx, [rax+rdi]
0x180005b70  mov     rax, r10
0x180005b73  sub     rax, rcx
0x180005b76  cmp     rax, 2
0x180005b7a  jle     short loc_180005BB8
0x180005b7c  mov     byte ptr [rcx], 5Ch ; '\'
0x180005b7f  lea     rdi, [rcx+1]
0x180005b83  mov     r8, [rdx+8]; Source
0x180005b87  inc     rbx
0x180005b8a  cmp     byte ptr [r8+rbx], 0
0x180005b8f  jnz     short loc_180005B87
0x180005b91  sub     r10, rdi
0x180005b94  inc     rbx
0x180005b97  cmp     rbx, r10
0x180005b9a  mov     rdx, r10; DestinationSize
0x180005b9d  mov     rcx, rdi; Destination
0x180005ba0  cmovnb  rbx, r10
0x180005ba4  mov     r9, rbx; SourceSize
0x180005ba7  call    cs:__imp_memcpy_s
0x180005bae  nop     dword ptr [rax+rax+00h]
0x180005bb3  mov     byte ptr [rbx+rdi-1], 0
0x180005bb8  mov     al, 1
0x180005bba  add     rsp, 28h
0x180005bbe  pop     rdi
0x180005bbf  pop     rsi
0x180005bc0  pop     rbp
0x180005bc1  pop     rbx
0x180005bc2  retn
```
