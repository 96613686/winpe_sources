# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000481c`
- end: `0x1800048f9`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004174`
- `0x18000481c`

## callees

- `0x18000481c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800048e3`
- `msvcrt!memcpy_s` at `0x1800048e3`

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
0x18000481c  push    rbx
0x18000481e  push    rbp
0x18000481f  push    rsi
0x180004820  push    rdi
0x180004821  sub     rsp, 28h
0x180004825  xor     al, al
0x180004827  mov     byte ptr [r8], 0
0x18000482b  mov     rbp, r9
0x18000482e  mov     rdi, r8
0x180004831  mov     rsi, rdx
0x180004834  mov     rbx, rcx
0x180004837  test    rdx, rdx
0x18000483a  jz      loc_1800048F0
0x180004840  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180004844  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004849  mov     rdx, [rsi+20h]
0x18000484d  test    rdx, rdx
0x180004850  jz      loc_1800048F0
0x180004856  cmp     dword ptr [rdx], 0
0x180004859  jnz     short loc_18000486C
0x18000485b  mov     eax, 1
0x180004860  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180004868  inc     eax
0x18000486a  mov     [rdx], eax
0x18000486c  cmp     dword ptr [rbx+50h], 0
0x180004870  jnz     short loc_180004883
0x180004872  movups  xmm0, xmmword ptr [rdx]
0x180004875  movups  xmmword ptr [rbx+50h], xmm0
0x180004879  movsd   xmm1, qword ptr [rdx+10h]
0x18000487e  movsd   qword ptr [rbx+60h], xmm1
0x180004883  movups  xmm0, xmmword ptr [rdx]
0x180004886  lea     r10, [rdi+rbp]
0x18000488a  movups  xmmword ptr [rbx+68h], xmm0
0x18000488e  movsd   xmm1, qword ptr [rdx+10h]
0x180004893  movsd   qword ptr [rbx+78h], xmm1
0x180004898  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000489c  mov     rax, rbx
0x18000489f  inc     rax
0x1800048a2  cmp     byte ptr [rdi+rax], 0
0x1800048a6  jnz     short loc_18000489F
0x1800048a8  lea     rcx, [rax+rdi]
0x1800048ac  mov     rax, r10
0x1800048af  sub     rax, rcx
0x1800048b2  cmp     rax, 2
0x1800048b6  jle     short loc_1800048EE
0x1800048b8  mov     byte ptr [rcx], 5Ch ; '\'
0x1800048bb  lea     rdi, [rcx+1]
0x1800048bf  mov     r8, [rdx+8]; Source
0x1800048c3  inc     rbx
0x1800048c6  cmp     byte ptr [r8+rbx], 0
0x1800048cb  jnz     short loc_1800048C3
0x1800048cd  sub     r10, rdi
0x1800048d0  inc     rbx
0x1800048d3  cmp     rbx, r10
0x1800048d6  mov     rdx, r10; DestinationSize
0x1800048d9  mov     rcx, rdi; Destination
0x1800048dc  cmovnb  rbx, r10
0x1800048e0  mov     r9, rbx; SourceSize
0x1800048e3  call    cs:__imp_memcpy_s
0x1800048e9  mov     byte ptr [rbx+rdi-1], 0
0x1800048ee  mov     al, 1
0x1800048f0  add     rsp, 28h
0x1800048f4  pop     rdi
0x1800048f5  pop     rsi
0x1800048f6  pop     rbp
0x1800048f7  pop     rbx
0x1800048f8  retn
```
