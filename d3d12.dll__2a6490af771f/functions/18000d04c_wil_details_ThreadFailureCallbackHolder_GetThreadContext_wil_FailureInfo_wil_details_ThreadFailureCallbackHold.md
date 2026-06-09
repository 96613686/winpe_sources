# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000d04c`
- end: `0x18000d128`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cbbc`
- `0x18000d04c`

## callees

- `0x18000463c`
- `0x18000d04c`

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
0x18000d04c  push    rbx
0x18000d04e  push    rbp
0x18000d04f  push    rsi
0x18000d050  push    rdi
0x18000d051  sub     rsp, 28h
0x18000d055  xor     al, al
0x18000d057  mov     byte ptr [r8], 0
0x18000d05b  mov     rbp, r9
0x18000d05e  mov     rdi, r8
0x18000d061  mov     rsi, rdx
0x18000d064  mov     rbx, rcx
0x18000d067  test    rdx, rdx
0x18000d06a  jz      loc_18000D11F
0x18000d070  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18000d074  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000d079  mov     rdx, [rsi+20h]
0x18000d07d  test    rdx, rdx
0x18000d080  jz      loc_18000D11F
0x18000d086  cmp     dword ptr [rdx], 0
0x18000d089  jnz     short loc_18000D09C
0x18000d08b  mov     eax, 1
0x18000d090  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000d098  inc     eax
0x18000d09a  mov     [rdx], eax
0x18000d09c  cmp     dword ptr [rbx+50h], 0
0x18000d0a0  jnz     short loc_18000D0B3
0x18000d0a2  movups  xmm0, xmmword ptr [rdx]
0x18000d0a5  movups  xmmword ptr [rbx+50h], xmm0
0x18000d0a9  movsd   xmm1, qword ptr [rdx+10h]
0x18000d0ae  movsd   qword ptr [rbx+60h], xmm1
0x18000d0b3  movups  xmm0, xmmword ptr [rdx]
0x18000d0b6  lea     r10, [rdi+rbp]
0x18000d0ba  movups  xmmword ptr [rbx+68h], xmm0
0x18000d0be  movsd   xmm1, qword ptr [rdx+10h]
0x18000d0c3  movsd   qword ptr [rbx+78h], xmm1
0x18000d0c8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000d0cc  mov     rax, rbx
0x18000d0cf  inc     rax
0x18000d0d2  cmp     byte ptr [rdi+rax], 0
0x18000d0d6  jnz     short loc_18000D0CF
0x18000d0d8  lea     rcx, [rax+rdi]
0x18000d0dc  mov     rax, r10
0x18000d0df  sub     rax, rcx
0x18000d0e2  cmp     rax, 2
0x18000d0e6  jle     short loc_18000D11D
0x18000d0e8  mov     byte ptr [rcx], 5Ch ; '\'
0x18000d0eb  lea     rdi, [rcx+1]
0x18000d0ef  mov     r8, [rdx+8]; Source
0x18000d0f3  inc     rbx
0x18000d0f6  cmp     byte ptr [r8+rbx], 0
0x18000d0fb  jnz     short loc_18000D0F3
0x18000d0fd  sub     r10, rdi
0x18000d100  inc     rbx
0x18000d103  cmp     rbx, r10
0x18000d106  mov     rdx, r10; DestinationSize
0x18000d109  mov     rcx, rdi; Destination
0x18000d10c  cmovnb  rbx, r10
0x18000d110  mov     r9, rbx; SourceSize
0x18000d113  call    memcpy_s
0x18000d118  mov     byte ptr [rbx+rdi-1], 0
0x18000d11d  mov     al, 1
0x18000d11f  add     rsp, 28h
0x18000d123  pop     rdi
0x18000d124  pop     rsi
0x18000d125  pop     rbp
0x18000d126  pop     rbx
0x18000d127  retn
```
