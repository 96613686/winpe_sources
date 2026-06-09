# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1800175f4`
- end: `0x1800176d0`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180016fa8`
- `0x1800175f4`

## callees

- `0x1800175f4`
- `0x18001aea4`

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
0x1800175f4  push    rbx
0x1800175f6  push    rbp
0x1800175f7  push    rsi
0x1800175f8  push    rdi
0x1800175f9  sub     rsp, 28h
0x1800175fd  xor     al, al
0x1800175ff  mov     byte ptr [r8], 0
0x180017603  mov     rbp, r9
0x180017606  mov     rdi, r8
0x180017609  mov     rsi, rdx
0x18001760c  mov     rbx, rcx
0x18001760f  test    rdx, rdx
0x180017612  jz      loc_1800176C7
0x180017618  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18001761c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180017621  mov     rdx, [rsi+20h]
0x180017625  test    rdx, rdx
0x180017628  jz      loc_1800176C7
0x18001762e  cmp     dword ptr [rdx], 0
0x180017631  jnz     short loc_180017644
0x180017633  mov     eax, 1
0x180017638  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180017640  inc     eax
0x180017642  mov     [rdx], eax
0x180017644  cmp     dword ptr [rbx+50h], 0
0x180017648  jnz     short loc_18001765B
0x18001764a  movups  xmm0, xmmword ptr [rdx]
0x18001764d  movups  xmmword ptr [rbx+50h], xmm0
0x180017651  movsd   xmm1, qword ptr [rdx+10h]
0x180017656  movsd   qword ptr [rbx+60h], xmm1
0x18001765b  movups  xmm0, xmmword ptr [rdx]
0x18001765e  lea     r10, [rdi+rbp]
0x180017662  movups  xmmword ptr [rbx+68h], xmm0
0x180017666  movsd   xmm1, qword ptr [rdx+10h]
0x18001766b  movsd   qword ptr [rbx+78h], xmm1
0x180017670  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180017674  mov     rax, rbx
0x180017677  inc     rax
0x18001767a  cmp     byte ptr [rdi+rax], 0
0x18001767e  jnz     short loc_180017677
0x180017680  lea     rcx, [rax+rdi]
0x180017684  mov     rax, r10
0x180017687  sub     rax, rcx
0x18001768a  cmp     rax, 2
0x18001768e  jle     short loc_1800176C5
0x180017690  mov     byte ptr [rcx], 5Ch ; '\'
0x180017693  lea     rdi, [rcx+1]
0x180017697  mov     r8, [rdx+8]; Source
0x18001769b  inc     rbx
0x18001769e  cmp     byte ptr [r8+rbx], 0
0x1800176a3  jnz     short loc_18001769B
0x1800176a5  sub     r10, rdi
0x1800176a8  inc     rbx
0x1800176ab  cmp     rbx, r10
0x1800176ae  mov     rdx, r10; DestinationSize
0x1800176b1  mov     rcx, rdi; Destination
0x1800176b4  cmovnb  rbx, r10
0x1800176b8  mov     r9, rbx; SourceSize
0x1800176bb  call    memcpy_s
0x1800176c0  mov     byte ptr [rbx+rdi-1], 0
0x1800176c5  mov     al, 1
0x1800176c7  add     rsp, 28h
0x1800176cb  pop     rdi
0x1800176cc  pop     rsi
0x1800176cd  pop     rbp
0x1800176ce  pop     rbx
0x1800176cf  retn
```
