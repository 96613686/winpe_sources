# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x14000989c`
- end: `0x140009978`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140008e70`
- `0x14000989c`

## callees

- `0x14000989c`
- `0x140010f78`

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
0x14000989c  push    rbx
0x14000989e  push    rbp
0x14000989f  push    rsi
0x1400098a0  push    rdi
0x1400098a1  sub     rsp, 28h
0x1400098a5  xor     al, al
0x1400098a7  mov     byte ptr [r8], 0
0x1400098ab  mov     rbp, r9
0x1400098ae  mov     rdi, r8
0x1400098b1  mov     rsi, rdx
0x1400098b4  mov     rbx, rcx
0x1400098b7  test    rdx, rdx
0x1400098ba  jz      loc_14000996F
0x1400098c0  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1400098c4  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400098c9  mov     rdx, [rsi+20h]
0x1400098cd  test    rdx, rdx
0x1400098d0  jz      loc_14000996F
0x1400098d6  cmp     dword ptr [rdx], 0
0x1400098d9  jnz     short loc_1400098EC
0x1400098db  mov     eax, 1
0x1400098e0  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1400098e8  inc     eax
0x1400098ea  mov     [rdx], eax
0x1400098ec  cmp     dword ptr [rbx+50h], 0
0x1400098f0  jnz     short loc_140009903
0x1400098f2  movups  xmm0, xmmword ptr [rdx]
0x1400098f5  movups  xmmword ptr [rbx+50h], xmm0
0x1400098f9  movsd   xmm1, qword ptr [rdx+10h]
0x1400098fe  movsd   qword ptr [rbx+60h], xmm1
0x140009903  movups  xmm0, xmmword ptr [rdx]
0x140009906  lea     r10, [rdi+rbp]
0x14000990a  movups  xmmword ptr [rbx+68h], xmm0
0x14000990e  movsd   xmm1, qword ptr [rdx+10h]
0x140009913  movsd   qword ptr [rbx+78h], xmm1
0x140009918  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000991c  mov     rax, rbx
0x14000991f  inc     rax
0x140009922  cmp     byte ptr [rdi+rax], 0
0x140009926  jnz     short loc_14000991F
0x140009928  lea     rcx, [rax+rdi]
0x14000992c  mov     rax, r10
0x14000992f  sub     rax, rcx
0x140009932  cmp     rax, 2
0x140009936  jle     short loc_14000996D
0x140009938  mov     byte ptr [rcx], 5Ch ; '\'
0x14000993b  lea     rdi, [rcx+1]
0x14000993f  mov     r8, [rdx+8]; Source
0x140009943  inc     rbx
0x140009946  cmp     byte ptr [r8+rbx], 0
0x14000994b  jnz     short loc_140009943
0x14000994d  sub     r10, rdi
0x140009950  inc     rbx
0x140009953  cmp     rbx, r10
0x140009956  mov     rdx, r10; DestinationSize
0x140009959  mov     rcx, rdi; Destination
0x14000995c  cmovnb  rbx, r10
0x140009960  mov     r9, rbx; SourceSize
0x140009963  call    memcpy_s
0x140009968  mov     byte ptr [rbx+rdi-1], 0
0x14000996d  mov     al, 1
0x14000996f  add     rsp, 28h
0x140009973  pop     rdi
0x140009974  pop     rsi
0x140009975  pop     rbp
0x140009976  pop     rbx
0x140009977  retn
```
