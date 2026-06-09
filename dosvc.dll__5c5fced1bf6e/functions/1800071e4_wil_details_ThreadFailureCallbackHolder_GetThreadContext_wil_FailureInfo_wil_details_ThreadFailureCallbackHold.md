# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1800071e4`
- end: `0x1800072c0`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006c18`
- `0x1800071e4`

## callees

- `0x180002e70`
- `0x1800071e4`

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
        memcpy_s_0(v18, v16, v15, v17);
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
0x1800071e4  push    rbx
0x1800071e6  push    rbp
0x1800071e7  push    rsi
0x1800071e8  push    rdi
0x1800071e9  sub     rsp, 28h
0x1800071ed  xor     al, al
0x1800071ef  mov     byte ptr [r8], 0
0x1800071f3  mov     rbp, r9
0x1800071f6  mov     rdi, r8
0x1800071f9  mov     rsi, rdx
0x1800071fc  mov     rbx, rcx
0x1800071ff  test    rdx, rdx
0x180007202  jz      loc_1800072B7
0x180007208  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18000720c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180007211  mov     rdx, [rsi+20h]
0x180007215  test    rdx, rdx
0x180007218  jz      loc_1800072B7
0x18000721e  cmp     dword ptr [rdx], 0
0x180007221  jnz     short loc_180007234
0x180007223  mov     eax, 1
0x180007228  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180007230  inc     eax
0x180007232  mov     [rdx], eax
0x180007234  cmp     dword ptr [rbx+50h], 0
0x180007238  jnz     short loc_18000724B
0x18000723a  movups  xmm0, xmmword ptr [rdx]
0x18000723d  movups  xmmword ptr [rbx+50h], xmm0
0x180007241  movsd   xmm1, qword ptr [rdx+10h]
0x180007246  movsd   qword ptr [rbx+60h], xmm1
0x18000724b  movups  xmm0, xmmword ptr [rdx]
0x18000724e  lea     r10, [rdi+rbp]
0x180007252  movups  xmmword ptr [rbx+68h], xmm0
0x180007256  movsd   xmm1, qword ptr [rdx+10h]
0x18000725b  movsd   qword ptr [rbx+78h], xmm1
0x180007260  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180007264  mov     rax, rbx
0x180007267  inc     rax
0x18000726a  cmp     byte ptr [rdi+rax], 0
0x18000726e  jnz     short loc_180007267
0x180007270  lea     rcx, [rax+rdi]
0x180007274  mov     rax, r10
0x180007277  sub     rax, rcx
0x18000727a  cmp     rax, 2
0x18000727e  jle     short loc_1800072B5
0x180007280  mov     byte ptr [rcx], 5Ch ; '\'
0x180007283  lea     rdi, [rcx+1]
0x180007287  mov     r8, [rdx+8]; Source
0x18000728b  inc     rbx
0x18000728e  cmp     byte ptr [r8+rbx], 0
0x180007293  jnz     short loc_18000728B
0x180007295  sub     r10, rdi
0x180007298  inc     rbx
0x18000729b  cmp     rbx, r10
0x18000729e  mov     rdx, r10; DestinationSize
0x1800072a1  mov     rcx, rdi; Destination
0x1800072a4  cmovnb  rbx, r10
0x1800072a8  mov     r9, rbx; SourceSize
0x1800072ab  call    memcpy_s_0
0x1800072b0  mov     byte ptr [rbx+rdi-1], 0
0x1800072b5  mov     al, 1
0x1800072b7  add     rsp, 28h
0x1800072bb  pop     rdi
0x1800072bc  pop     rsi
0x1800072bd  pop     rbp
0x1800072be  pop     rbx
0x1800072bf  retn
```
