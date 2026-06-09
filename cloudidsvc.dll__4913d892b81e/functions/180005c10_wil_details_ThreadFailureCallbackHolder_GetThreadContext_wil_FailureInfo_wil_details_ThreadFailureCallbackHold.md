# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180005c10`
- end: `0x180005cec`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800054b4`
- `0x180005c10`

## callees

- `0x180005c10`
- `0x180008660`

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
0x180005c10  push    rbx
0x180005c12  push    rbp
0x180005c13  push    rsi
0x180005c14  push    rdi
0x180005c15  sub     rsp, 28h
0x180005c19  xor     al, al
0x180005c1b  mov     byte ptr [r8], 0
0x180005c1f  mov     rbp, r9
0x180005c22  mov     rdi, r8
0x180005c25  mov     rsi, rdx
0x180005c28  mov     rbx, rcx
0x180005c2b  test    rdx, rdx
0x180005c2e  jz      loc_180005CE3
0x180005c34  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180005c38  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005c3d  mov     rdx, [rsi+20h]
0x180005c41  test    rdx, rdx
0x180005c44  jz      loc_180005CE3
0x180005c4a  cmp     dword ptr [rdx], 0
0x180005c4d  jnz     short loc_180005C60
0x180005c4f  mov     eax, 1
0x180005c54  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180005c5c  inc     eax
0x180005c5e  mov     [rdx], eax
0x180005c60  cmp     dword ptr [rbx+50h], 0
0x180005c64  jnz     short loc_180005C77
0x180005c66  movups  xmm0, xmmword ptr [rdx]
0x180005c69  movups  xmmword ptr [rbx+50h], xmm0
0x180005c6d  movsd   xmm1, qword ptr [rdx+10h]
0x180005c72  movsd   qword ptr [rbx+60h], xmm1
0x180005c77  movups  xmm0, xmmword ptr [rdx]
0x180005c7a  lea     r10, [rdi+rbp]
0x180005c7e  movups  xmmword ptr [rbx+68h], xmm0
0x180005c82  movsd   xmm1, qword ptr [rdx+10h]
0x180005c87  movsd   qword ptr [rbx+78h], xmm1
0x180005c8c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005c90  mov     rax, rbx
0x180005c93  inc     rax
0x180005c96  cmp     byte ptr [rdi+rax], 0
0x180005c9a  jnz     short loc_180005C93
0x180005c9c  lea     rcx, [rax+rdi]
0x180005ca0  mov     rax, r10
0x180005ca3  sub     rax, rcx
0x180005ca6  cmp     rax, 2
0x180005caa  jle     short loc_180005CE1
0x180005cac  mov     byte ptr [rcx], 5Ch ; '\'
0x180005caf  lea     rdi, [rcx+1]
0x180005cb3  mov     r8, [rdx+8]; Source
0x180005cb7  inc     rbx
0x180005cba  cmp     byte ptr [r8+rbx], 0
0x180005cbf  jnz     short loc_180005CB7
0x180005cc1  sub     r10, rdi
0x180005cc4  inc     rbx
0x180005cc7  cmp     rbx, r10
0x180005cca  mov     rdx, r10; DestinationSize
0x180005ccd  mov     rcx, rdi; Destination
0x180005cd0  cmovnb  rbx, r10
0x180005cd4  mov     r9, rbx; SourceSize
0x180005cd7  call    memcpy_s
0x180005cdc  mov     byte ptr [rbx+rdi-1], 0
0x180005ce1  mov     al, 1
0x180005ce3  add     rsp, 28h
0x180005ce7  pop     rdi
0x180005ce8  pop     rsi
0x180005ce9  pop     rbp
0x180005cea  pop     rbx
0x180005ceb  retn
```
