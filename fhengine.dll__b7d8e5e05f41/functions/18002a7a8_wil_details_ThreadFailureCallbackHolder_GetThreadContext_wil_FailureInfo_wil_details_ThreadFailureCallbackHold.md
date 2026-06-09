# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18002a7a8`
- end: `0x18002a885`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180029848`
- `0x18002a7a8`

## callees

- `0x18002a7a8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18002a86f`
- `msvcrt!memcpy_s` at `0x18002a86f`

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
0x18002a7a8  push    rbx
0x18002a7aa  push    rbp
0x18002a7ab  push    rsi
0x18002a7ac  push    rdi
0x18002a7ad  sub     rsp, 28h
0x18002a7b1  xor     al, al
0x18002a7b3  mov     byte ptr [r8], 0
0x18002a7b7  mov     rbp, r9
0x18002a7ba  mov     rdi, r8
0x18002a7bd  mov     rsi, rdx
0x18002a7c0  mov     rbx, rcx
0x18002a7c3  test    rdx, rdx
0x18002a7c6  jz      loc_18002A87C
0x18002a7cc  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18002a7d0  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18002a7d5  mov     rdx, [rsi+20h]
0x18002a7d9  test    rdx, rdx
0x18002a7dc  jz      loc_18002A87C
0x18002a7e2  cmp     dword ptr [rdx], 0
0x18002a7e5  jnz     short loc_18002A7F8
0x18002a7e7  mov     eax, 1
0x18002a7ec  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18002a7f4  inc     eax
0x18002a7f6  mov     [rdx], eax
0x18002a7f8  cmp     dword ptr [rbx+50h], 0
0x18002a7fc  jnz     short loc_18002A80F
0x18002a7fe  movups  xmm0, xmmword ptr [rdx]
0x18002a801  movups  xmmword ptr [rbx+50h], xmm0
0x18002a805  movsd   xmm1, qword ptr [rdx+10h]
0x18002a80a  movsd   qword ptr [rbx+60h], xmm1
0x18002a80f  movups  xmm0, xmmword ptr [rdx]
0x18002a812  lea     r10, [rdi+rbp]
0x18002a816  movups  xmmword ptr [rbx+68h], xmm0
0x18002a81a  movsd   xmm1, qword ptr [rdx+10h]
0x18002a81f  movsd   qword ptr [rbx+78h], xmm1
0x18002a824  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002a828  mov     rax, rbx
0x18002a82b  inc     rax
0x18002a82e  cmp     byte ptr [rdi+rax], 0
0x18002a832  jnz     short loc_18002A82B
0x18002a834  lea     rcx, [rax+rdi]
0x18002a838  mov     rax, r10
0x18002a83b  sub     rax, rcx
0x18002a83e  cmp     rax, 2
0x18002a842  jle     short loc_18002A87A
0x18002a844  mov     byte ptr [rcx], 5Ch ; '\'
0x18002a847  lea     rdi, [rcx+1]
0x18002a84b  mov     r8, [rdx+8]; Source
0x18002a84f  inc     rbx
0x18002a852  cmp     byte ptr [r8+rbx], 0
0x18002a857  jnz     short loc_18002A84F
0x18002a859  sub     r10, rdi
0x18002a85c  inc     rbx
0x18002a85f  cmp     rbx, r10
0x18002a862  mov     rdx, r10; DestinationSize
0x18002a865  mov     rcx, rdi; Destination
0x18002a868  cmovnb  rbx, r10
0x18002a86c  mov     r9, rbx; SourceSize
0x18002a86f  call    cs:__imp_memcpy_s
0x18002a875  mov     byte ptr [rbx+rdi-1], 0
0x18002a87a  mov     al, 1
0x18002a87c  add     rsp, 28h
0x18002a880  pop     rdi
0x18002a881  pop     rsi
0x18002a882  pop     rbp
0x18002a883  pop     rbx
0x18002a884  retn
```
