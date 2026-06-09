# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140078fc0`
- end: `0x14007909c`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400788d4`
- `0x140078fc0`

## callees

- `0x140078fc0`
- `0x14007bed8`

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
0x140078fc0  push    rbx
0x140078fc2  push    rbp
0x140078fc3  push    rsi
0x140078fc4  push    rdi
0x140078fc5  sub     rsp, 28h
0x140078fc9  xor     al, al
0x140078fcb  mov     byte ptr [r8], 0
0x140078fcf  mov     rbp, r9
0x140078fd2  mov     rdi, r8
0x140078fd5  mov     rsi, rdx
0x140078fd8  mov     rbx, rcx
0x140078fdb  test    rdx, rdx
0x140078fde  jz      loc_140079093
0x140078fe4  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140078fe8  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140078fed  mov     rdx, [rsi+20h]
0x140078ff1  test    rdx, rdx
0x140078ff4  jz      loc_140079093
0x140078ffa  cmp     dword ptr [rdx], 0
0x140078ffd  jnz     short loc_140079010
0x140078fff  mov     eax, 1
0x140079004  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x14007900c  inc     eax
0x14007900e  mov     [rdx], eax
0x140079010  cmp     dword ptr [rbx+50h], 0
0x140079014  jnz     short loc_140079027
0x140079016  movups  xmm0, xmmword ptr [rdx]
0x140079019  movups  xmmword ptr [rbx+50h], xmm0
0x14007901d  movsd   xmm1, qword ptr [rdx+10h]
0x140079022  movsd   qword ptr [rbx+60h], xmm1
0x140079027  movups  xmm0, xmmword ptr [rdx]
0x14007902a  lea     r10, [rdi+rbp]
0x14007902e  movups  xmmword ptr [rbx+68h], xmm0
0x140079032  movsd   xmm1, qword ptr [rdx+10h]
0x140079037  movsd   qword ptr [rbx+78h], xmm1
0x14007903c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140079040  mov     rax, rbx
0x140079043  inc     rax
0x140079046  cmp     byte ptr [rdi+rax], 0
0x14007904a  jnz     short loc_140079043
0x14007904c  lea     rcx, [rax+rdi]
0x140079050  mov     rax, r10
0x140079053  sub     rax, rcx
0x140079056  cmp     rax, 2
0x14007905a  jle     short loc_140079091
0x14007905c  mov     byte ptr [rcx], 5Ch ; '\'
0x14007905f  lea     rdi, [rcx+1]
0x140079063  mov     r8, [rdx+8]; Source
0x140079067  inc     rbx
0x14007906a  cmp     byte ptr [r8+rbx], 0
0x14007906f  jnz     short loc_140079067
0x140079071  sub     r10, rdi
0x140079074  inc     rbx
0x140079077  cmp     rbx, r10
0x14007907a  mov     rdx, r10; DestinationSize
0x14007907d  mov     rcx, rdi; Destination
0x140079080  cmovnb  rbx, r10
0x140079084  mov     r9, rbx; SourceSize
0x140079087  call    memcpy_s
0x14007908c  mov     byte ptr [rbx+rdi-1], 0
0x140079091  mov     al, 1
0x140079093  add     rsp, 28h
0x140079097  pop     rdi
0x140079098  pop     rsi
0x140079099  pop     rbp
0x14007909a  pop     rbx
0x14007909b  retn
```
