# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000686c`
- end: `0x180006948`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006170`
- `0x18000686c`

## callees

- `0x18000686c`
- `0x18000ac08`

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
0x18000686c  push    rbx
0x18000686e  push    rbp
0x18000686f  push    rsi
0x180006870  push    rdi
0x180006871  sub     rsp, 28h
0x180006875  xor     al, al
0x180006877  mov     byte ptr [r8], 0
0x18000687b  mov     rbp, r9
0x18000687e  mov     rdi, r8
0x180006881  mov     rsi, rdx
0x180006884  mov     rbx, rcx
0x180006887  test    rdx, rdx
0x18000688a  jz      loc_18000693F
0x180006890  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180006894  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006899  mov     rdx, [rsi+20h]
0x18000689d  test    rdx, rdx
0x1800068a0  jz      loc_18000693F
0x1800068a6  cmp     dword ptr [rdx], 0
0x1800068a9  jnz     short loc_1800068BC
0x1800068ab  mov     eax, 1
0x1800068b0  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1800068b8  inc     eax
0x1800068ba  mov     [rdx], eax
0x1800068bc  cmp     dword ptr [rbx+50h], 0
0x1800068c0  jnz     short loc_1800068D3
0x1800068c2  movups  xmm0, xmmword ptr [rdx]
0x1800068c5  movups  xmmword ptr [rbx+50h], xmm0
0x1800068c9  movsd   xmm1, qword ptr [rdx+10h]
0x1800068ce  movsd   qword ptr [rbx+60h], xmm1
0x1800068d3  movups  xmm0, xmmword ptr [rdx]
0x1800068d6  lea     r10, [rdi+rbp]
0x1800068da  movups  xmmword ptr [rbx+68h], xmm0
0x1800068de  movsd   xmm1, qword ptr [rdx+10h]
0x1800068e3  movsd   qword ptr [rbx+78h], xmm1
0x1800068e8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800068ec  mov     rax, rbx
0x1800068ef  inc     rax
0x1800068f2  cmp     byte ptr [rdi+rax], 0
0x1800068f6  jnz     short loc_1800068EF
0x1800068f8  lea     rcx, [rax+rdi]
0x1800068fc  mov     rax, r10
0x1800068ff  sub     rax, rcx
0x180006902  cmp     rax, 2
0x180006906  jle     short loc_18000693D
0x180006908  mov     byte ptr [rcx], 5Ch ; '\'
0x18000690b  lea     rdi, [rcx+1]
0x18000690f  mov     r8, [rdx+8]; Source
0x180006913  inc     rbx
0x180006916  cmp     byte ptr [r8+rbx], 0
0x18000691b  jnz     short loc_180006913
0x18000691d  sub     r10, rdi
0x180006920  inc     rbx
0x180006923  cmp     rbx, r10
0x180006926  mov     rdx, r10; DestinationSize
0x180006929  mov     rcx, rdi; Destination
0x18000692c  cmovnb  rbx, r10
0x180006930  mov     r9, rbx; SourceSize
0x180006933  call    memcpy_s
0x180006938  mov     byte ptr [rbx+rdi-1], 0
0x18000693d  mov     al, 1
0x18000693f  add     rsp, 28h
0x180006943  pop     rdi
0x180006944  pop     rsi
0x180006945  pop     rbp
0x180006946  pop     rbx
0x180006947  retn
```
