# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000da04`
- end: `0x18000daf6`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `242`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d070`
- `0x18000da04`

## callees

- `0x18000da04`
- `0x18001a6ac`

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
  char *v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // rax
  char *v13; // rdi
  _BYTE *v14; // rdi
  _BYTE *v15; // r8
  rsize_t v16; // rcx
  rsize_t v17; // rbx

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
      if ( v10 - v13 > 2 )
      {
        *v13 = 92;
        v14 = v13 + 1;
        v15 = (_BYTE *)*((_QWORD *)v9 + 1);
        do
          ++v11;
        while ( v15[v11] );
        v16 = v10 - v14;
        v17 = v11 + 1;
        if ( v17 >= v16 )
          v17 = v16;
        memcpy_s(v14, v16, v15, v17);
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
0x18000da04  mov     [rsp+arg_0], rbx
0x18000da09  mov     [rsp+arg_8], rbp
0x18000da0e  mov     [rsp+arg_10], rsi
0x18000da13  push    rdi
0x18000da14  sub     rsp, 20h
0x18000da18  xor     al, al
0x18000da1a  mov     byte ptr [r8], 0
0x18000da1e  mov     rbp, r9
0x18000da21  mov     rdi, r8
0x18000da24  mov     rsi, rdx
0x18000da27  mov     rbx, rcx
0x18000da2a  test    rdx, rdx
0x18000da2d  jz      loc_18000DAE0
0x18000da33  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18000da37  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000da3c  mov     rdx, [rsi+20h]
0x18000da40  test    rdx, rdx
0x18000da43  jz      loc_18000DAE0
0x18000da49  cmp     dword ptr [rdx], 0
0x18000da4c  jnz     short loc_18000DA5F
0x18000da4e  mov     eax, 1
0x18000da53  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000da5b  inc     eax
0x18000da5d  mov     [rdx], eax
0x18000da5f  cmp     dword ptr [rbx+50h], 0
0x18000da63  jnz     short loc_18000DA76
0x18000da65  movups  xmm0, xmmword ptr [rdx]
0x18000da68  movups  xmmword ptr [rbx+50h], xmm0
0x18000da6c  movsd   xmm1, qword ptr [rdx+10h]
0x18000da71  movsd   qword ptr [rbx+60h], xmm1
0x18000da76  movups  xmm0, xmmword ptr [rdx]
0x18000da79  lea     rcx, [rdi+rbp]
0x18000da7d  movups  xmmword ptr [rbx+68h], xmm0
0x18000da81  movsd   xmm1, qword ptr [rdx+10h]
0x18000da86  movsd   qword ptr [rbx+78h], xmm1
0x18000da8b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000da8f  mov     rax, rbx
0x18000da92  inc     rax
0x18000da95  cmp     byte ptr [rdi+rax], 0
0x18000da99  jnz     short loc_18000DA92
0x18000da9b  add     rdi, rax
0x18000da9e  mov     rax, rcx
0x18000daa1  sub     rax, rdi
0x18000daa4  cmp     rax, 2
0x18000daa8  jle     short loc_18000DADE
0x18000daaa  mov     byte ptr [rdi], 5Ch ; '\'
0x18000daad  inc     rdi
0x18000dab0  mov     r8, [rdx+8]; Source
0x18000dab4  inc     rbx
0x18000dab7  cmp     byte ptr [r8+rbx], 0
0x18000dabc  jnz     short loc_18000DAB4
0x18000dabe  sub     rcx, rdi
0x18000dac1  inc     rbx
0x18000dac4  cmp     rbx, rcx
0x18000dac7  mov     rdx, rcx; DestinationSize
0x18000daca  cmovnb  rbx, rcx
0x18000dace  mov     rcx, rdi; Destination
0x18000dad1  mov     r9, rbx; SourceSize
0x18000dad4  call    memcpy_s
0x18000dad9  mov     byte ptr [rbx+rdi-1], 0
0x18000dade  mov     al, 1
0x18000dae0  mov     rbx, [rsp+28h+arg_0]
0x18000dae5  mov     rbp, [rsp+28h+arg_8]
0x18000daea  mov     rsi, [rsp+28h+arg_10]
0x18000daef  add     rsp, 20h
0x18000daf3  pop     rdi
0x18000daf4  retn
```
