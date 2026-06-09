# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140012258`
- end: `0x140012335`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140011c98`
- `0x140012258`

## callees

- `0x140012258`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14001231f`
- `msvcrt!memcpy_s` at `0x14001231f`

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
0x140012258  push    rbx
0x14001225a  push    rbp
0x14001225b  push    rsi
0x14001225c  push    rdi
0x14001225d  sub     rsp, 28h
0x140012261  xor     al, al
0x140012263  mov     byte ptr [r8], 0
0x140012267  mov     rbp, r9
0x14001226a  mov     rdi, r8
0x14001226d  mov     rsi, rdx
0x140012270  mov     rbx, rcx
0x140012273  test    rdx, rdx
0x140012276  jz      loc_14001232C
0x14001227c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140012280  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140012285  mov     rdx, [rsi+20h]
0x140012289  test    rdx, rdx
0x14001228c  jz      loc_14001232C
0x140012292  cmp     dword ptr [rdx], 0
0x140012295  jnz     short loc_1400122A8
0x140012297  mov     eax, 1
0x14001229c  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1400122a4  inc     eax
0x1400122a6  mov     [rdx], eax
0x1400122a8  cmp     dword ptr [rbx+50h], 0
0x1400122ac  jnz     short loc_1400122BF
0x1400122ae  movups  xmm0, xmmword ptr [rdx]
0x1400122b1  movups  xmmword ptr [rbx+50h], xmm0
0x1400122b5  movsd   xmm1, qword ptr [rdx+10h]
0x1400122ba  movsd   qword ptr [rbx+60h], xmm1
0x1400122bf  movups  xmm0, xmmword ptr [rdx]
0x1400122c2  lea     r10, [rdi+rbp]
0x1400122c6  movups  xmmword ptr [rbx+68h], xmm0
0x1400122ca  movsd   xmm1, qword ptr [rdx+10h]
0x1400122cf  movsd   qword ptr [rbx+78h], xmm1
0x1400122d4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400122d8  mov     rax, rbx
0x1400122db  inc     rax
0x1400122de  cmp     byte ptr [rdi+rax], 0
0x1400122e2  jnz     short loc_1400122DB
0x1400122e4  lea     rcx, [rax+rdi]
0x1400122e8  mov     rax, r10
0x1400122eb  sub     rax, rcx
0x1400122ee  cmp     rax, 2
0x1400122f2  jle     short loc_14001232A
0x1400122f4  mov     byte ptr [rcx], 5Ch ; '\'
0x1400122f7  lea     rdi, [rcx+1]
0x1400122fb  mov     r8, [rdx+8]; Source
0x1400122ff  inc     rbx
0x140012302  cmp     byte ptr [r8+rbx], 0
0x140012307  jnz     short loc_1400122FF
0x140012309  sub     r10, rdi
0x14001230c  inc     rbx
0x14001230f  cmp     rbx, r10
0x140012312  mov     rdx, r10; DestinationSize
0x140012315  mov     rcx, rdi; Destination
0x140012318  cmovnb  rbx, r10
0x14001231c  mov     r9, rbx; SourceSize
0x14001231f  call    cs:__imp_memcpy_s
0x140012325  mov     byte ptr [rbx+rdi-1], 0
0x14001232a  mov     al, 1
0x14001232c  add     rsp, 28h
0x140012330  pop     rdi
0x140012331  pop     rsi
0x140012332  pop     rbp
0x140012333  pop     rbx
0x140012334  retn
```
