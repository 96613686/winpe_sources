# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180005a2c`
- end: `0x180005b08`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005330`
- `0x180005a2c`

## callees

- `0x180005a2c`
- `0x180007eac`

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
0x180005a2c  push    rbx
0x180005a2e  push    rbp
0x180005a2f  push    rsi
0x180005a30  push    rdi
0x180005a31  sub     rsp, 28h
0x180005a35  xor     al, al
0x180005a37  mov     byte ptr [r8], 0
0x180005a3b  mov     rbp, r9
0x180005a3e  mov     rdi, r8
0x180005a41  mov     rsi, rdx
0x180005a44  mov     rbx, rcx
0x180005a47  test    rdx, rdx
0x180005a4a  jz      loc_180005AFF
0x180005a50  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180005a54  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005a59  mov     rdx, [rsi+20h]
0x180005a5d  test    rdx, rdx
0x180005a60  jz      loc_180005AFF
0x180005a66  cmp     dword ptr [rdx], 0
0x180005a69  jnz     short loc_180005A7C
0x180005a6b  mov     eax, 1
0x180005a70  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180005a78  inc     eax
0x180005a7a  mov     [rdx], eax
0x180005a7c  cmp     dword ptr [rbx+50h], 0
0x180005a80  jnz     short loc_180005A93
0x180005a82  movups  xmm0, xmmword ptr [rdx]
0x180005a85  movups  xmmword ptr [rbx+50h], xmm0
0x180005a89  movsd   xmm1, qword ptr [rdx+10h]
0x180005a8e  movsd   qword ptr [rbx+60h], xmm1
0x180005a93  movups  xmm0, xmmword ptr [rdx]
0x180005a96  lea     r10, [rdi+rbp]
0x180005a9a  movups  xmmword ptr [rbx+68h], xmm0
0x180005a9e  movsd   xmm1, qword ptr [rdx+10h]
0x180005aa3  movsd   qword ptr [rbx+78h], xmm1
0x180005aa8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005aac  mov     rax, rbx
0x180005aaf  inc     rax
0x180005ab2  cmp     byte ptr [rdi+rax], 0
0x180005ab6  jnz     short loc_180005AAF
0x180005ab8  lea     rcx, [rax+rdi]
0x180005abc  mov     rax, r10
0x180005abf  sub     rax, rcx
0x180005ac2  cmp     rax, 2
0x180005ac6  jle     short loc_180005AFD
0x180005ac8  mov     byte ptr [rcx], 5Ch ; '\'
0x180005acb  lea     rdi, [rcx+1]
0x180005acf  mov     r8, [rdx+8]; Source
0x180005ad3  inc     rbx
0x180005ad6  cmp     byte ptr [r8+rbx], 0
0x180005adb  jnz     short loc_180005AD3
0x180005add  sub     r10, rdi
0x180005ae0  inc     rbx
0x180005ae3  cmp     rbx, r10
0x180005ae6  mov     rdx, r10; DestinationSize
0x180005ae9  mov     rcx, rdi; Destination
0x180005aec  cmovnb  rbx, r10
0x180005af0  mov     r9, rbx; SourceSize
0x180005af3  call    memcpy_s
0x180005af8  mov     byte ptr [rbx+rdi-1], 0
0x180005afd  mov     al, 1
0x180005aff  add     rsp, 28h
0x180005b03  pop     rdi
0x180005b04  pop     rsi
0x180005b05  pop     rbp
0x180005b06  pop     rbx
0x180005b07  retn
```
