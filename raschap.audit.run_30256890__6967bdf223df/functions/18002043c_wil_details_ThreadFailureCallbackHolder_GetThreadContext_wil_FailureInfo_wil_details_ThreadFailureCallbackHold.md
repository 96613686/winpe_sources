# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18002043c`
- end: `0x180020518`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001fea8`
- `0x18002043c`

## callees

- `0x1800118a4`
- `0x18002043c`

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
0x18002043c  push    rbx
0x18002043e  push    rbp
0x18002043f  push    rsi
0x180020440  push    rdi
0x180020441  sub     rsp, 28h
0x180020445  xor     al, al
0x180020447  mov     byte ptr [r8], 0
0x18002044b  mov     rbp, r9
0x18002044e  mov     rdi, r8
0x180020451  mov     rsi, rdx
0x180020454  mov     rbx, rcx
0x180020457  test    rdx, rdx
0x18002045a  jz      loc_18002050F
0x180020460  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180020464  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180020469  mov     rdx, [rsi+20h]
0x18002046d  test    rdx, rdx
0x180020470  jz      loc_18002050F
0x180020476  cmp     dword ptr [rdx], 0
0x180020479  jnz     short loc_18002048C
0x18002047b  mov     eax, 1
0x180020480  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180020488  inc     eax
0x18002048a  mov     [rdx], eax
0x18002048c  cmp     dword ptr [rbx+50h], 0
0x180020490  jnz     short loc_1800204A3
0x180020492  movups  xmm0, xmmword ptr [rdx]
0x180020495  movups  xmmword ptr [rbx+50h], xmm0
0x180020499  movsd   xmm1, qword ptr [rdx+10h]
0x18002049e  movsd   qword ptr [rbx+60h], xmm1
0x1800204a3  movups  xmm0, xmmword ptr [rdx]
0x1800204a6  lea     r10, [rdi+rbp]
0x1800204aa  movups  xmmword ptr [rbx+68h], xmm0
0x1800204ae  movsd   xmm1, qword ptr [rdx+10h]
0x1800204b3  movsd   qword ptr [rbx+78h], xmm1
0x1800204b8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800204bc  mov     rax, rbx
0x1800204bf  inc     rax
0x1800204c2  cmp     byte ptr [rdi+rax], 0
0x1800204c6  jnz     short loc_1800204BF
0x1800204c8  lea     rcx, [rax+rdi]
0x1800204cc  mov     rax, r10
0x1800204cf  sub     rax, rcx
0x1800204d2  cmp     rax, 2
0x1800204d6  jle     short loc_18002050D
0x1800204d8  mov     byte ptr [rcx], 5Ch ; '\'
0x1800204db  lea     rdi, [rcx+1]
0x1800204df  mov     r8, [rdx+8]; Source
0x1800204e3  inc     rbx
0x1800204e6  cmp     byte ptr [r8+rbx], 0
0x1800204eb  jnz     short loc_1800204E3
0x1800204ed  sub     r10, rdi
0x1800204f0  inc     rbx
0x1800204f3  cmp     rbx, r10
0x1800204f6  mov     rdx, r10; DestinationSize
0x1800204f9  mov     rcx, rdi; Destination
0x1800204fc  cmovnb  rbx, r10
0x180020500  mov     r9, rbx; SourceSize
0x180020503  call    memcpy_s
0x180020508  mov     byte ptr [rbx+rdi-1], 0
0x18002050d  mov     al, 1
0x18002050f  add     rsp, 28h
0x180020513  pop     rdi
0x180020514  pop     rsi
0x180020515  pop     rbp
0x180020516  pop     rbx
0x180020517  retn
```
