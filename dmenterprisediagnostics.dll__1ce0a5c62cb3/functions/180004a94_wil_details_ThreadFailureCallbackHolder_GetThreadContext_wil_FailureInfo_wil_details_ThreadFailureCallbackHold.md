# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180004a94`
- end: `0x180004b70`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004438`
- `0x180004a94`

## callees

- `0x180004a94`
- `0x180007a20`

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
0x180004a94  push    rbx
0x180004a96  push    rbp
0x180004a97  push    rsi
0x180004a98  push    rdi
0x180004a99  sub     rsp, 28h
0x180004a9d  xor     al, al
0x180004a9f  mov     byte ptr [r8], 0
0x180004aa3  mov     rbp, r9
0x180004aa6  mov     rdi, r8
0x180004aa9  mov     rsi, rdx
0x180004aac  mov     rbx, rcx
0x180004aaf  test    rdx, rdx
0x180004ab2  jz      loc_180004B67
0x180004ab8  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180004abc  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004ac1  mov     rdx, [rsi+20h]
0x180004ac5  test    rdx, rdx
0x180004ac8  jz      loc_180004B67
0x180004ace  cmp     dword ptr [rdx], 0
0x180004ad1  jnz     short loc_180004AE4
0x180004ad3  mov     eax, 1
0x180004ad8  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180004ae0  inc     eax
0x180004ae2  mov     [rdx], eax
0x180004ae4  cmp     dword ptr [rbx+50h], 0
0x180004ae8  jnz     short loc_180004AFB
0x180004aea  movups  xmm0, xmmword ptr [rdx]
0x180004aed  movups  xmmword ptr [rbx+50h], xmm0
0x180004af1  movsd   xmm1, qword ptr [rdx+10h]
0x180004af6  movsd   qword ptr [rbx+60h], xmm1
0x180004afb  movups  xmm0, xmmword ptr [rdx]
0x180004afe  lea     r10, [rdi+rbp]
0x180004b02  movups  xmmword ptr [rbx+68h], xmm0
0x180004b06  movsd   xmm1, qword ptr [rdx+10h]
0x180004b0b  movsd   qword ptr [rbx+78h], xmm1
0x180004b10  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004b14  mov     rax, rbx
0x180004b17  inc     rax
0x180004b1a  cmp     byte ptr [rdi+rax], 0
0x180004b1e  jnz     short loc_180004B17
0x180004b20  lea     rcx, [rax+rdi]
0x180004b24  mov     rax, r10
0x180004b27  sub     rax, rcx
0x180004b2a  cmp     rax, 2
0x180004b2e  jle     short loc_180004B65
0x180004b30  mov     byte ptr [rcx], 5Ch ; '\'
0x180004b33  lea     rdi, [rcx+1]
0x180004b37  mov     r8, [rdx+8]; Source
0x180004b3b  inc     rbx
0x180004b3e  cmp     byte ptr [r8+rbx], 0
0x180004b43  jnz     short loc_180004B3B
0x180004b45  sub     r10, rdi
0x180004b48  inc     rbx
0x180004b4b  cmp     rbx, r10
0x180004b4e  mov     rdx, r10; DestinationSize
0x180004b51  mov     rcx, rdi; Destination
0x180004b54  cmovnb  rbx, r10
0x180004b58  mov     r9, rbx; SourceSize
0x180004b5b  call    memcpy_s
0x180004b60  mov     byte ptr [rbx+rdi-1], 0
0x180004b65  mov     al, 1
0x180004b67  add     rsp, 28h
0x180004b6b  pop     rdi
0x180004b6c  pop     rsi
0x180004b6d  pop     rbp
0x180004b6e  pop     rbx
0x180004b6f  retn
```
