# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180004d5c`
- end: `0x180004e39`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004720`
- `0x180004d5c`

## callees

- `0x180004d5c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180004e23`
- `msvcrt!memcpy_s` at `0x180004e23`

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
0x180004d5c  push    rbx
0x180004d5e  push    rbp
0x180004d5f  push    rsi
0x180004d60  push    rdi
0x180004d61  sub     rsp, 28h
0x180004d65  xor     al, al
0x180004d67  mov     byte ptr [r8], 0
0x180004d6b  mov     rbp, r9
0x180004d6e  mov     rdi, r8
0x180004d71  mov     rsi, rdx
0x180004d74  mov     rbx, rcx
0x180004d77  test    rdx, rdx
0x180004d7a  jz      loc_180004E30
0x180004d80  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180004d84  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004d89  mov     rdx, [rsi+20h]
0x180004d8d  test    rdx, rdx
0x180004d90  jz      loc_180004E30
0x180004d96  cmp     dword ptr [rdx], 0
0x180004d99  jnz     short loc_180004DAC
0x180004d9b  mov     eax, 1
0x180004da0  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180004da8  inc     eax
0x180004daa  mov     [rdx], eax
0x180004dac  cmp     dword ptr [rbx+50h], 0
0x180004db0  jnz     short loc_180004DC3
0x180004db2  movups  xmm0, xmmword ptr [rdx]
0x180004db5  movups  xmmword ptr [rbx+50h], xmm0
0x180004db9  movsd   xmm1, qword ptr [rdx+10h]
0x180004dbe  movsd   qword ptr [rbx+60h], xmm1
0x180004dc3  movups  xmm0, xmmword ptr [rdx]
0x180004dc6  lea     r10, [rdi+rbp]
0x180004dca  movups  xmmword ptr [rbx+68h], xmm0
0x180004dce  movsd   xmm1, qword ptr [rdx+10h]
0x180004dd3  movsd   qword ptr [rbx+78h], xmm1
0x180004dd8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004ddc  mov     rax, rbx
0x180004ddf  inc     rax
0x180004de2  cmp     byte ptr [rdi+rax], 0
0x180004de6  jnz     short loc_180004DDF
0x180004de8  lea     rcx, [rax+rdi]
0x180004dec  mov     rax, r10
0x180004def  sub     rax, rcx
0x180004df2  cmp     rax, 2
0x180004df6  jle     short loc_180004E2E
0x180004df8  mov     byte ptr [rcx], 5Ch ; '\'
0x180004dfb  lea     rdi, [rcx+1]
0x180004dff  mov     r8, [rdx+8]; Source
0x180004e03  inc     rbx
0x180004e06  cmp     byte ptr [r8+rbx], 0
0x180004e0b  jnz     short loc_180004E03
0x180004e0d  sub     r10, rdi
0x180004e10  inc     rbx
0x180004e13  cmp     rbx, r10
0x180004e16  mov     rdx, r10; DestinationSize
0x180004e19  mov     rcx, rdi; Destination
0x180004e1c  cmovnb  rbx, r10
0x180004e20  mov     r9, rbx; SourceSize
0x180004e23  call    cs:__imp_memcpy_s
0x180004e29  mov     byte ptr [rbx+rdi-1], 0
0x180004e2e  mov     al, 1
0x180004e30  add     rsp, 28h
0x180004e34  pop     rdi
0x180004e35  pop     rsi
0x180004e36  pop     rbp
0x180004e37  pop     rbx
0x180004e38  retn
```
