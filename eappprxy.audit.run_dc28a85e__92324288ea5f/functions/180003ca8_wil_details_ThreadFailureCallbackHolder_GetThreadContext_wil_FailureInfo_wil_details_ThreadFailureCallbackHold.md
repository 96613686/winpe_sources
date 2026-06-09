# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180003ca8`
- end: `0x180003d85`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003630`
- `0x180003ca8`

## callees

- `0x180003ca8`
- `0x18000b36c`

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
0x180003ca8  push    rbx
0x180003caa  push    rbp
0x180003cab  push    rsi
0x180003cac  push    rdi
0x180003cad  sub     rsp, 28h
0x180003cb1  xor     al, al
0x180003cb3  mov     byte ptr [r8], 0
0x180003cb7  mov     rbp, r9
0x180003cba  mov     rdi, r8
0x180003cbd  mov     rsi, rdx
0x180003cc0  mov     rbx, rcx
0x180003cc3  test    rdx, rdx
0x180003cc6  jz      loc_180003D7B
0x180003ccc  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180003cd0  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003cd5  mov     rdx, [rsi+20h]
0x180003cd9  test    rdx, rdx
0x180003cdc  jz      loc_180003D7B
0x180003ce2  cmp     dword ptr [rdx], 0
0x180003ce5  jnz     short loc_180003CF8
0x180003ce7  mov     eax, 1
0x180003cec  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180003cf4  inc     eax
0x180003cf6  mov     [rdx], eax
0x180003cf8  cmp     dword ptr [rbx+50h], 0
0x180003cfc  jnz     short loc_180003D0F
0x180003cfe  movups  xmm0, xmmword ptr [rdx]
0x180003d01  movups  xmmword ptr [rbx+50h], xmm0
0x180003d05  movsd   xmm1, qword ptr [rdx+10h]
0x180003d0a  movsd   qword ptr [rbx+60h], xmm1
0x180003d0f  movups  xmm0, xmmword ptr [rdx]
0x180003d12  lea     r10, [rdi+rbp]
0x180003d16  movups  xmmword ptr [rbx+68h], xmm0
0x180003d1a  movsd   xmm1, qword ptr [rdx+10h]
0x180003d1f  movsd   qword ptr [rbx+78h], xmm1
0x180003d24  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003d28  mov     rax, rbx
0x180003d2b  inc     rax
0x180003d2e  cmp     byte ptr [rdi+rax], 0
0x180003d32  jnz     short loc_180003D2B
0x180003d34  lea     rcx, [rax+rdi]
0x180003d38  mov     rax, r10
0x180003d3b  sub     rax, rcx
0x180003d3e  cmp     rax, 2
0x180003d42  jle     short loc_180003D79
0x180003d44  mov     byte ptr [rcx], 5Ch ; '\'
0x180003d47  lea     rdi, [rcx+1]
0x180003d4b  mov     r8, [rdx+8]; Source
0x180003d4f  inc     rbx
0x180003d52  cmp     byte ptr [r8+rbx], 0
0x180003d57  jnz     short loc_180003D4F
0x180003d59  sub     r10, rdi
0x180003d5c  inc     rbx
0x180003d5f  cmp     rbx, r10
0x180003d62  mov     rdx, r10; DestinationSize
0x180003d65  mov     rcx, rdi; Destination
0x180003d68  cmovnb  rbx, r10
0x180003d6c  mov     r9, rbx; SourceSize
0x180003d6f  call    memcpy_s
0x180003d74  mov     byte ptr [rbx+rdi-1], 0
0x180003d79  mov     al, 1
0x180003d7b  add     rsp, 28h
0x180003d7f  pop     rdi
0x180003d80  pop     rsi
0x180003d81  pop     rbp
0x180003d82  pop     rbx
0x180003d83  retn
```
