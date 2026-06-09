# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180004e04`
- end: `0x180004ee8`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `228`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800046d0`
- `0x180004e04`

## callees

- `0x180004e04`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180004ecb`
- `msvcrt!memcpy_s` at `0x180004ecb`

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
0x180004e04  push    rbx
0x180004e06  push    rbp
0x180004e07  push    rsi
0x180004e08  push    rdi
0x180004e09  sub     rsp, 28h
0x180004e0d  xor     al, al
0x180004e0f  mov     byte ptr [r8], 0
0x180004e13  mov     rbp, r9
0x180004e16  mov     rdi, r8
0x180004e19  mov     rsi, rdx
0x180004e1c  mov     rbx, rcx
0x180004e1f  test    rdx, rdx
0x180004e22  jz      loc_180004EDE
0x180004e28  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180004e2c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004e31  mov     rdx, [rsi+20h]
0x180004e35  test    rdx, rdx
0x180004e38  jz      loc_180004EDE
0x180004e3e  cmp     dword ptr [rdx], 0
0x180004e41  jnz     short loc_180004E54
0x180004e43  mov     eax, 1
0x180004e48  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180004e50  inc     eax
0x180004e52  mov     [rdx], eax
0x180004e54  cmp     dword ptr [rbx+50h], 0
0x180004e58  jnz     short loc_180004E6B
0x180004e5a  movups  xmm0, xmmword ptr [rdx]
0x180004e5d  movups  xmmword ptr [rbx+50h], xmm0
0x180004e61  movsd   xmm1, qword ptr [rdx+10h]
0x180004e66  movsd   qword ptr [rbx+60h], xmm1
0x180004e6b  movups  xmm0, xmmword ptr [rdx]
0x180004e6e  lea     r10, [rdi+rbp]
0x180004e72  movups  xmmword ptr [rbx+68h], xmm0
0x180004e76  movsd   xmm1, qword ptr [rdx+10h]
0x180004e7b  movsd   qword ptr [rbx+78h], xmm1
0x180004e80  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004e84  mov     rax, rbx
0x180004e87  inc     rax
0x180004e8a  cmp     byte ptr [rdi+rax], 0
0x180004e8e  jnz     short loc_180004E87
0x180004e90  lea     rcx, [rax+rdi]
0x180004e94  mov     rax, r10
0x180004e97  sub     rax, rcx
0x180004e9a  cmp     rax, 2
0x180004e9e  jle     short loc_180004EDC
0x180004ea0  mov     byte ptr [rcx], 5Ch ; '\'
0x180004ea3  lea     rdi, [rcx+1]
0x180004ea7  mov     r8, [rdx+8]; Source
0x180004eab  inc     rbx
0x180004eae  cmp     byte ptr [r8+rbx], 0
0x180004eb3  jnz     short loc_180004EAB
0x180004eb5  sub     r10, rdi
0x180004eb8  inc     rbx
0x180004ebb  cmp     rbx, r10
0x180004ebe  mov     rdx, r10; DestinationSize
0x180004ec1  mov     rcx, rdi; Destination
0x180004ec4  cmovnb  rbx, r10
0x180004ec8  mov     r9, rbx; SourceSize
0x180004ecb  call    cs:__imp_memcpy_s
0x180004ed2  nop     dword ptr [rax+rax+00h]
0x180004ed7  mov     byte ptr [rbx+rdi-1], 0
0x180004edc  mov     al, 1
0x180004ede  add     rsp, 28h
0x180004ee2  pop     rdi
0x180004ee3  pop     rsi
0x180004ee4  pop     rbp
0x180004ee5  pop     rbx
0x180004ee6  retn
```
