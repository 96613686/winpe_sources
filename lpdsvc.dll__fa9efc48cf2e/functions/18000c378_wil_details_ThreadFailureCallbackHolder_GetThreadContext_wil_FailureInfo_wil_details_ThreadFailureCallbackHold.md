# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000c378`
- end: `0x18000c454`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bc80`
- `0x18000c378`

## callees

- `0x1800025fe`
- `0x18000c378`

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
0x18000c378  push    rbx
0x18000c37a  push    rbp
0x18000c37b  push    rsi
0x18000c37c  push    rdi
0x18000c37d  sub     rsp, 28h
0x18000c381  xor     al, al
0x18000c383  mov     byte ptr [r8], 0
0x18000c387  mov     rbp, r9
0x18000c38a  mov     rdi, r8
0x18000c38d  mov     rsi, rdx
0x18000c390  mov     rbx, rcx
0x18000c393  test    rdx, rdx
0x18000c396  jz      loc_18000C44B
0x18000c39c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18000c3a0  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000c3a5  mov     rdx, [rsi+20h]
0x18000c3a9  test    rdx, rdx
0x18000c3ac  jz      loc_18000C44B
0x18000c3b2  cmp     dword ptr [rdx], 0
0x18000c3b5  jnz     short loc_18000C3C8
0x18000c3b7  mov     eax, 1
0x18000c3bc  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000c3c4  inc     eax
0x18000c3c6  mov     [rdx], eax
0x18000c3c8  cmp     dword ptr [rbx+50h], 0
0x18000c3cc  jnz     short loc_18000C3DF
0x18000c3ce  movups  xmm0, xmmword ptr [rdx]
0x18000c3d1  movups  xmmword ptr [rbx+50h], xmm0
0x18000c3d5  movsd   xmm1, qword ptr [rdx+10h]
0x18000c3da  movsd   qword ptr [rbx+60h], xmm1
0x18000c3df  movups  xmm0, xmmword ptr [rdx]
0x18000c3e2  lea     r10, [rdi+rbp]
0x18000c3e6  movups  xmmword ptr [rbx+68h], xmm0
0x18000c3ea  movsd   xmm1, qword ptr [rdx+10h]
0x18000c3ef  movsd   qword ptr [rbx+78h], xmm1
0x18000c3f4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000c3f8  mov     rax, rbx
0x18000c3fb  inc     rax
0x18000c3fe  cmp     byte ptr [rdi+rax], 0
0x18000c402  jnz     short loc_18000C3FB
0x18000c404  lea     rcx, [rax+rdi]
0x18000c408  mov     rax, r10
0x18000c40b  sub     rax, rcx
0x18000c40e  cmp     rax, 2
0x18000c412  jle     short loc_18000C449
0x18000c414  mov     byte ptr [rcx], 5Ch ; '\'
0x18000c417  lea     rdi, [rcx+1]
0x18000c41b  mov     r8, [rdx+8]; Source
0x18000c41f  inc     rbx
0x18000c422  cmp     byte ptr [r8+rbx], 0
0x18000c427  jnz     short loc_18000C41F
0x18000c429  sub     r10, rdi
0x18000c42c  inc     rbx
0x18000c42f  cmp     rbx, r10
0x18000c432  mov     rdx, r10; DestinationSize
0x18000c435  mov     rcx, rdi; Destination
0x18000c438  cmovnb  rbx, r10
0x18000c43c  mov     r9, rbx; SourceSize
0x18000c43f  call    memcpy_s
0x18000c444  mov     byte ptr [rbx+rdi-1], 0
0x18000c449  mov     al, 1
0x18000c44b  add     rsp, 28h
0x18000c44f  pop     rdi
0x18000c450  pop     rsi
0x18000c451  pop     rbp
0x18000c452  pop     rbx
0x18000c453  retn
```
