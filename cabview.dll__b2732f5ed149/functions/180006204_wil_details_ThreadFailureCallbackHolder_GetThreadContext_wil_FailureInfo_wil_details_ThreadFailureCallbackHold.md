# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180006204`
- end: `0x1800062e0`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005b14`
- `0x180006204`

## callees

- `0x180006204`
- `0x18000a310`

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
0x180006204  push    rbx
0x180006206  push    rbp
0x180006207  push    rsi
0x180006208  push    rdi
0x180006209  sub     rsp, 28h
0x18000620d  xor     al, al
0x18000620f  mov     byte ptr [r8], 0
0x180006213  mov     rbp, r9
0x180006216  mov     rdi, r8
0x180006219  mov     rsi, rdx
0x18000621c  mov     rbx, rcx
0x18000621f  test    rdx, rdx
0x180006222  jz      loc_1800062D7
0x180006228  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18000622c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006231  mov     rdx, [rsi+20h]
0x180006235  test    rdx, rdx
0x180006238  jz      loc_1800062D7
0x18000623e  cmp     dword ptr [rdx], 0
0x180006241  jnz     short loc_180006254
0x180006243  mov     eax, 1
0x180006248  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180006250  inc     eax
0x180006252  mov     [rdx], eax
0x180006254  cmp     dword ptr [rbx+50h], 0
0x180006258  jnz     short loc_18000626B
0x18000625a  movups  xmm0, xmmword ptr [rdx]
0x18000625d  movups  xmmword ptr [rbx+50h], xmm0
0x180006261  movsd   xmm1, qword ptr [rdx+10h]
0x180006266  movsd   qword ptr [rbx+60h], xmm1
0x18000626b  movups  xmm0, xmmword ptr [rdx]
0x18000626e  lea     r10, [rdi+rbp]
0x180006272  movups  xmmword ptr [rbx+68h], xmm0
0x180006276  movsd   xmm1, qword ptr [rdx+10h]
0x18000627b  movsd   qword ptr [rbx+78h], xmm1
0x180006280  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006284  mov     rax, rbx
0x180006287  inc     rax
0x18000628a  cmp     byte ptr [rdi+rax], 0
0x18000628e  jnz     short loc_180006287
0x180006290  lea     rcx, [rax+rdi]
0x180006294  mov     rax, r10
0x180006297  sub     rax, rcx
0x18000629a  cmp     rax, 2
0x18000629e  jle     short loc_1800062D5
0x1800062a0  mov     byte ptr [rcx], 5Ch ; '\'
0x1800062a3  lea     rdi, [rcx+1]
0x1800062a7  mov     r8, [rdx+8]; Source
0x1800062ab  inc     rbx
0x1800062ae  cmp     byte ptr [r8+rbx], 0
0x1800062b3  jnz     short loc_1800062AB
0x1800062b5  sub     r10, rdi
0x1800062b8  inc     rbx
0x1800062bb  cmp     rbx, r10
0x1800062be  mov     rdx, r10; DestinationSize
0x1800062c1  mov     rcx, rdi; Destination
0x1800062c4  cmovnb  rbx, r10
0x1800062c8  mov     r9, rbx; SourceSize
0x1800062cb  call    memcpy_s
0x1800062d0  mov     byte ptr [rbx+rdi-1], 0
0x1800062d5  mov     al, 1
0x1800062d7  add     rsp, 28h
0x1800062db  pop     rdi
0x1800062dc  pop     rsi
0x1800062dd  pop     rbp
0x1800062de  pop     rbx
0x1800062df  retn
```
