# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000d740`
- end: `0x18000d81c`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cfa0`
- `0x18000d740`

## callees

- `0x18000d740`
- `0x1800105a0`

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
0x18000d740  push    rbx
0x18000d742  push    rbp
0x18000d743  push    rsi
0x18000d744  push    rdi
0x18000d745  sub     rsp, 28h
0x18000d749  xor     al, al
0x18000d74b  mov     byte ptr [r8], 0
0x18000d74f  mov     rbp, r9
0x18000d752  mov     rdi, r8
0x18000d755  mov     rsi, rdx
0x18000d758  mov     rbx, rcx
0x18000d75b  test    rdx, rdx
0x18000d75e  jz      loc_18000D813
0x18000d764  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18000d768  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000d76d  mov     rdx, [rsi+20h]
0x18000d771  test    rdx, rdx
0x18000d774  jz      loc_18000D813
0x18000d77a  cmp     dword ptr [rdx], 0
0x18000d77d  jnz     short loc_18000D790
0x18000d77f  mov     eax, 1
0x18000d784  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000d78c  inc     eax
0x18000d78e  mov     [rdx], eax
0x18000d790  cmp     dword ptr [rbx+50h], 0
0x18000d794  jnz     short loc_18000D7A7
0x18000d796  movups  xmm0, xmmword ptr [rdx]
0x18000d799  movups  xmmword ptr [rbx+50h], xmm0
0x18000d79d  movsd   xmm1, qword ptr [rdx+10h]
0x18000d7a2  movsd   qword ptr [rbx+60h], xmm1
0x18000d7a7  movups  xmm0, xmmword ptr [rdx]
0x18000d7aa  lea     r10, [rdi+rbp]
0x18000d7ae  movups  xmmword ptr [rbx+68h], xmm0
0x18000d7b2  movsd   xmm1, qword ptr [rdx+10h]
0x18000d7b7  movsd   qword ptr [rbx+78h], xmm1
0x18000d7bc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000d7c0  mov     rax, rbx
0x18000d7c3  inc     rax
0x18000d7c6  cmp     byte ptr [rdi+rax], 0
0x18000d7ca  jnz     short loc_18000D7C3
0x18000d7cc  lea     rcx, [rax+rdi]
0x18000d7d0  mov     rax, r10
0x18000d7d3  sub     rax, rcx
0x18000d7d6  cmp     rax, 2
0x18000d7da  jle     short loc_18000D811
0x18000d7dc  mov     byte ptr [rcx], 5Ch ; '\'
0x18000d7df  lea     rdi, [rcx+1]
0x18000d7e3  mov     r8, [rdx+8]; Source
0x18000d7e7  inc     rbx
0x18000d7ea  cmp     byte ptr [r8+rbx], 0
0x18000d7ef  jnz     short loc_18000D7E7
0x18000d7f1  sub     r10, rdi
0x18000d7f4  inc     rbx
0x18000d7f7  cmp     rbx, r10
0x18000d7fa  mov     rdx, r10; DestinationSize
0x18000d7fd  mov     rcx, rdi; Destination
0x18000d800  cmovnb  rbx, r10
0x18000d804  mov     r9, rbx; SourceSize
0x18000d807  call    memcpy_s
0x18000d80c  mov     byte ptr [rbx+rdi-1], 0
0x18000d811  mov     al, 1
0x18000d813  add     rsp, 28h
0x18000d817  pop     rdi
0x18000d818  pop     rsi
0x18000d819  pop     rbp
0x18000d81a  pop     rbx
0x18000d81b  retn
```
