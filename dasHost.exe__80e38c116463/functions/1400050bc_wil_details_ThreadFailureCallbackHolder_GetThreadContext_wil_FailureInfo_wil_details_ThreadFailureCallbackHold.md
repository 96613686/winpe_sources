# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1400050bc`
- end: `0x140005198`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400049c0`
- `0x1400050bc`

## callees

- `0x1400050bc`
- `0x140008948`

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
0x1400050bc  push    rbx
0x1400050be  push    rbp
0x1400050bf  push    rsi
0x1400050c0  push    rdi
0x1400050c1  sub     rsp, 28h
0x1400050c5  xor     al, al
0x1400050c7  mov     byte ptr [r8], 0
0x1400050cb  mov     rbp, r9
0x1400050ce  mov     rdi, r8
0x1400050d1  mov     rsi, rdx
0x1400050d4  mov     rbx, rcx
0x1400050d7  test    rdx, rdx
0x1400050da  jz      loc_14000518F
0x1400050e0  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1400050e4  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400050e9  mov     rdx, [rsi+20h]
0x1400050ed  test    rdx, rdx
0x1400050f0  jz      loc_14000518F
0x1400050f6  cmp     dword ptr [rdx], 0
0x1400050f9  jnz     short loc_14000510C
0x1400050fb  mov     eax, 1
0x140005100  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140005108  inc     eax
0x14000510a  mov     [rdx], eax
0x14000510c  cmp     dword ptr [rbx+50h], 0
0x140005110  jnz     short loc_140005123
0x140005112  movups  xmm0, xmmword ptr [rdx]
0x140005115  movups  xmmword ptr [rbx+50h], xmm0
0x140005119  movsd   xmm1, qword ptr [rdx+10h]
0x14000511e  movsd   qword ptr [rbx+60h], xmm1
0x140005123  movups  xmm0, xmmword ptr [rdx]
0x140005126  lea     r10, [rdi+rbp]
0x14000512a  movups  xmmword ptr [rbx+68h], xmm0
0x14000512e  movsd   xmm1, qword ptr [rdx+10h]
0x140005133  movsd   qword ptr [rbx+78h], xmm1
0x140005138  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000513c  mov     rax, rbx
0x14000513f  inc     rax
0x140005142  cmp     byte ptr [rdi+rax], 0
0x140005146  jnz     short loc_14000513F
0x140005148  lea     rcx, [rax+rdi]
0x14000514c  mov     rax, r10
0x14000514f  sub     rax, rcx
0x140005152  cmp     rax, 2
0x140005156  jle     short loc_14000518D
0x140005158  mov     byte ptr [rcx], 5Ch ; '\'
0x14000515b  lea     rdi, [rcx+1]
0x14000515f  mov     r8, [rdx+8]; Source
0x140005163  inc     rbx
0x140005166  cmp     byte ptr [r8+rbx], 0
0x14000516b  jnz     short loc_140005163
0x14000516d  sub     r10, rdi
0x140005170  inc     rbx
0x140005173  cmp     rbx, r10
0x140005176  mov     rdx, r10; DestinationSize
0x140005179  mov     rcx, rdi; Destination
0x14000517c  cmovnb  rbx, r10
0x140005180  mov     r9, rbx; SourceSize
0x140005183  call    memcpy_s
0x140005188  mov     byte ptr [rbx+rdi-1], 0
0x14000518d  mov     al, 1
0x14000518f  add     rsp, 28h
0x140005193  pop     rdi
0x140005194  pop     rsi
0x140005195  pop     rbp
0x140005196  pop     rbx
0x140005197  retn
```
