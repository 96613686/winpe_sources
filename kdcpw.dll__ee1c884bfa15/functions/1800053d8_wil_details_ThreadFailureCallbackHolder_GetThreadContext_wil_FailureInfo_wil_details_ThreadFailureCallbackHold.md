# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1800053d8`
- end: `0x1800054b4`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004ce0`
- `0x1800053d8`

## callees

- `0x1800053d8`
- `0x1800094bc`

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
0x1800053d8  push    rbx
0x1800053da  push    rbp
0x1800053db  push    rsi
0x1800053dc  push    rdi
0x1800053dd  sub     rsp, 28h
0x1800053e1  xor     al, al
0x1800053e3  mov     byte ptr [r8], 0
0x1800053e7  mov     rbp, r9
0x1800053ea  mov     rdi, r8
0x1800053ed  mov     rsi, rdx
0x1800053f0  mov     rbx, rcx
0x1800053f3  test    rdx, rdx
0x1800053f6  jz      loc_1800054AB
0x1800053fc  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180005400  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005405  mov     rdx, [rsi+20h]
0x180005409  test    rdx, rdx
0x18000540c  jz      loc_1800054AB
0x180005412  cmp     dword ptr [rdx], 0
0x180005415  jnz     short loc_180005428
0x180005417  mov     eax, 1
0x18000541c  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180005424  inc     eax
0x180005426  mov     [rdx], eax
0x180005428  cmp     dword ptr [rbx+50h], 0
0x18000542c  jnz     short loc_18000543F
0x18000542e  movups  xmm0, xmmword ptr [rdx]
0x180005431  movups  xmmword ptr [rbx+50h], xmm0
0x180005435  movsd   xmm1, qword ptr [rdx+10h]
0x18000543a  movsd   qword ptr [rbx+60h], xmm1
0x18000543f  movups  xmm0, xmmword ptr [rdx]
0x180005442  lea     r10, [rdi+rbp]
0x180005446  movups  xmmword ptr [rbx+68h], xmm0
0x18000544a  movsd   xmm1, qword ptr [rdx+10h]
0x18000544f  movsd   qword ptr [rbx+78h], xmm1
0x180005454  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005458  mov     rax, rbx
0x18000545b  inc     rax
0x18000545e  cmp     byte ptr [rdi+rax], 0
0x180005462  jnz     short loc_18000545B
0x180005464  lea     rcx, [rax+rdi]
0x180005468  mov     rax, r10
0x18000546b  sub     rax, rcx
0x18000546e  cmp     rax, 2
0x180005472  jle     short loc_1800054A9
0x180005474  mov     byte ptr [rcx], 5Ch ; '\'
0x180005477  lea     rdi, [rcx+1]
0x18000547b  mov     r8, [rdx+8]; Source
0x18000547f  inc     rbx
0x180005482  cmp     byte ptr [r8+rbx], 0
0x180005487  jnz     short loc_18000547F
0x180005489  sub     r10, rdi
0x18000548c  inc     rbx
0x18000548f  cmp     rbx, r10
0x180005492  mov     rdx, r10; DestinationSize
0x180005495  mov     rcx, rdi; Destination
0x180005498  cmovnb  rbx, r10
0x18000549c  mov     r9, rbx; SourceSize
0x18000549f  call    memcpy_s
0x1800054a4  mov     byte ptr [rbx+rdi-1], 0
0x1800054a9  mov     al, 1
0x1800054ab  add     rsp, 28h
0x1800054af  pop     rdi
0x1800054b0  pop     rsi
0x1800054b1  pop     rbp
0x1800054b2  pop     rbx
0x1800054b3  retn
```
