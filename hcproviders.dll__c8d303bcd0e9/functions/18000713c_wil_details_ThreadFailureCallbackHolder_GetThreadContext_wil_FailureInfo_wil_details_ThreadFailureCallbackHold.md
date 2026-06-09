# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000713c`
- end: `0x180007220`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `228`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006b44`
- `0x18000713c`

## callees

- `0x18000713c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007203`
- `msvcrt!memcpy_s` at `0x180007203`

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
0x18000713c  push    rbx
0x18000713e  push    rbp
0x18000713f  push    rsi
0x180007140  push    rdi
0x180007141  sub     rsp, 28h
0x180007145  xor     al, al
0x180007147  mov     byte ptr [r8], 0
0x18000714b  mov     rbp, r9
0x18000714e  mov     rdi, r8
0x180007151  mov     rsi, rdx
0x180007154  mov     rbx, rcx
0x180007157  test    rdx, rdx
0x18000715a  jz      loc_180007216
0x180007160  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180007164  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180007169  mov     rdx, [rsi+20h]
0x18000716d  test    rdx, rdx
0x180007170  jz      loc_180007216
0x180007176  cmp     dword ptr [rdx], 0
0x180007179  jnz     short loc_18000718C
0x18000717b  mov     eax, 1
0x180007180  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180007188  inc     eax
0x18000718a  mov     [rdx], eax
0x18000718c  cmp     dword ptr [rbx+50h], 0
0x180007190  jnz     short loc_1800071A3
0x180007192  movups  xmm0, xmmword ptr [rdx]
0x180007195  movups  xmmword ptr [rbx+50h], xmm0
0x180007199  movsd   xmm1, qword ptr [rdx+10h]
0x18000719e  movsd   qword ptr [rbx+60h], xmm1
0x1800071a3  movups  xmm0, xmmword ptr [rdx]
0x1800071a6  lea     r10, [rdi+rbp]
0x1800071aa  movups  xmmword ptr [rbx+68h], xmm0
0x1800071ae  movsd   xmm1, qword ptr [rdx+10h]
0x1800071b3  movsd   qword ptr [rbx+78h], xmm1
0x1800071b8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800071bc  mov     rax, rbx
0x1800071bf  inc     rax
0x1800071c2  cmp     byte ptr [rdi+rax], 0
0x1800071c6  jnz     short loc_1800071BF
0x1800071c8  lea     rcx, [rax+rdi]
0x1800071cc  mov     rax, r10
0x1800071cf  sub     rax, rcx
0x1800071d2  cmp     rax, 2
0x1800071d6  jle     short loc_180007214
0x1800071d8  mov     byte ptr [rcx], 5Ch ; '\'
0x1800071db  lea     rdi, [rcx+1]
0x1800071df  mov     r8, [rdx+8]; Source
0x1800071e3  inc     rbx
0x1800071e6  cmp     byte ptr [r8+rbx], 0
0x1800071eb  jnz     short loc_1800071E3
0x1800071ed  sub     r10, rdi
0x1800071f0  inc     rbx
0x1800071f3  cmp     rbx, r10
0x1800071f6  mov     rdx, r10; DestinationSize
0x1800071f9  mov     rcx, rdi; Destination
0x1800071fc  cmovnb  rbx, r10
0x180007200  mov     r9, rbx; SourceSize
0x180007203  call    cs:__imp_memcpy_s
0x18000720a  nop     dword ptr [rax+rax+00h]
0x18000720f  mov     byte ptr [rbx+rdi-1], 0
0x180007214  mov     al, 1
0x180007216  add     rsp, 28h
0x18000721a  pop     rdi
0x18000721b  pop     rsi
0x18000721c  pop     rbp
0x18000721d  pop     rbx
0x18000721e  retn
```
