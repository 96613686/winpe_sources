# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140003848`
- end: `0x140003925`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003150`
- `0x140003848`

## callees

- `0x140003848`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000390f`
- `msvcrt!memcpy_s` at `0x14000390f`

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
0x140003848  push    rbx
0x14000384a  push    rbp
0x14000384b  push    rsi
0x14000384c  push    rdi
0x14000384d  sub     rsp, 28h
0x140003851  xor     al, al
0x140003853  mov     byte ptr [r8], 0
0x140003857  mov     rbp, r9
0x14000385a  mov     rdi, r8
0x14000385d  mov     rsi, rdx
0x140003860  mov     rbx, rcx
0x140003863  test    rdx, rdx
0x140003866  jz      loc_14000391C
0x14000386c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140003870  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140003875  mov     rdx, [rsi+20h]
0x140003879  test    rdx, rdx
0x14000387c  jz      loc_14000391C
0x140003882  cmp     dword ptr [rdx], 0
0x140003885  jnz     short loc_140003898
0x140003887  mov     eax, 1
0x14000388c  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140003894  inc     eax
0x140003896  mov     [rdx], eax
0x140003898  cmp     dword ptr [rbx+50h], 0
0x14000389c  jnz     short loc_1400038AF
0x14000389e  movups  xmm0, xmmword ptr [rdx]
0x1400038a1  movups  xmmword ptr [rbx+50h], xmm0
0x1400038a5  movsd   xmm1, qword ptr [rdx+10h]
0x1400038aa  movsd   qword ptr [rbx+60h], xmm1
0x1400038af  movups  xmm0, xmmword ptr [rdx]
0x1400038b2  lea     r10, [rdi+rbp]
0x1400038b6  movups  xmmword ptr [rbx+68h], xmm0
0x1400038ba  movsd   xmm1, qword ptr [rdx+10h]
0x1400038bf  movsd   qword ptr [rbx+78h], xmm1
0x1400038c4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400038c8  mov     rax, rbx
0x1400038cb  inc     rax
0x1400038ce  cmp     byte ptr [rdi+rax], 0
0x1400038d2  jnz     short loc_1400038CB
0x1400038d4  lea     rcx, [rax+rdi]
0x1400038d8  mov     rax, r10
0x1400038db  sub     rax, rcx
0x1400038de  cmp     rax, 2
0x1400038e2  jle     short loc_14000391A
0x1400038e4  mov     byte ptr [rcx], 5Ch ; '\'
0x1400038e7  lea     rdi, [rcx+1]
0x1400038eb  mov     r8, [rdx+8]; Source
0x1400038ef  inc     rbx
0x1400038f2  cmp     byte ptr [r8+rbx], 0
0x1400038f7  jnz     short loc_1400038EF
0x1400038f9  sub     r10, rdi
0x1400038fc  inc     rbx
0x1400038ff  cmp     rbx, r10
0x140003902  mov     rdx, r10; DestinationSize
0x140003905  mov     rcx, rdi; Destination
0x140003908  cmovnb  rbx, r10
0x14000390c  mov     r9, rbx; SourceSize
0x14000390f  call    cs:__imp_memcpy_s
0x140003915  mov     byte ptr [rbx+rdi-1], 0
0x14000391a  mov     al, 1
0x14000391c  add     rsp, 28h
0x140003920  pop     rdi
0x140003921  pop     rsi
0x140003922  pop     rbp
0x140003923  pop     rbx
0x140003924  retn
```
