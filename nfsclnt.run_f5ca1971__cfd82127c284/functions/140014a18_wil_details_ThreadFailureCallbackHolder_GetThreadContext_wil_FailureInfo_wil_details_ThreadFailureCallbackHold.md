# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140014a18`
- end: `0x140014af5`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140014320`
- `0x140014a18`

## callees

- `0x140014a18`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140014adf`
- `msvcrt!memcpy_s` at `0x140014adf`

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
0x140014a18  push    rbx
0x140014a1a  push    rbp
0x140014a1b  push    rsi
0x140014a1c  push    rdi
0x140014a1d  sub     rsp, 28h
0x140014a21  xor     al, al
0x140014a23  mov     byte ptr [r8], 0
0x140014a27  mov     rbp, r9
0x140014a2a  mov     rdi, r8
0x140014a2d  mov     rsi, rdx
0x140014a30  mov     rbx, rcx
0x140014a33  test    rdx, rdx
0x140014a36  jz      loc_140014AEC
0x140014a3c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140014a40  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140014a45  mov     rdx, [rsi+20h]
0x140014a49  test    rdx, rdx
0x140014a4c  jz      loc_140014AEC
0x140014a52  cmp     dword ptr [rdx], 0
0x140014a55  jnz     short loc_140014A68
0x140014a57  mov     eax, 1
0x140014a5c  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140014a64  inc     eax
0x140014a66  mov     [rdx], eax
0x140014a68  cmp     dword ptr [rbx+50h], 0
0x140014a6c  jnz     short loc_140014A7F
0x140014a6e  movups  xmm0, xmmword ptr [rdx]
0x140014a71  movups  xmmword ptr [rbx+50h], xmm0
0x140014a75  movsd   xmm1, qword ptr [rdx+10h]
0x140014a7a  movsd   qword ptr [rbx+60h], xmm1
0x140014a7f  movups  xmm0, xmmword ptr [rdx]
0x140014a82  lea     r10, [rdi+rbp]
0x140014a86  movups  xmmword ptr [rbx+68h], xmm0
0x140014a8a  movsd   xmm1, qword ptr [rdx+10h]
0x140014a8f  movsd   qword ptr [rbx+78h], xmm1
0x140014a94  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140014a98  mov     rax, rbx
0x140014a9b  inc     rax
0x140014a9e  cmp     byte ptr [rdi+rax], 0
0x140014aa2  jnz     short loc_140014A9B
0x140014aa4  lea     rcx, [rax+rdi]
0x140014aa8  mov     rax, r10
0x140014aab  sub     rax, rcx
0x140014aae  cmp     rax, 2
0x140014ab2  jle     short loc_140014AEA
0x140014ab4  mov     byte ptr [rcx], 5Ch ; '\'
0x140014ab7  lea     rdi, [rcx+1]
0x140014abb  mov     r8, [rdx+8]; Source
0x140014abf  inc     rbx
0x140014ac2  cmp     byte ptr [r8+rbx], 0
0x140014ac7  jnz     short loc_140014ABF
0x140014ac9  sub     r10, rdi
0x140014acc  inc     rbx
0x140014acf  cmp     rbx, r10
0x140014ad2  mov     rdx, r10; DestinationSize
0x140014ad5  mov     rcx, rdi; Destination
0x140014ad8  cmovnb  rbx, r10
0x140014adc  mov     r9, rbx; SourceSize
0x140014adf  call    cs:__imp_memcpy_s
0x140014ae5  mov     byte ptr [rbx+rdi-1], 0
0x140014aea  mov     al, 1
0x140014aec  add     rsp, 28h
0x140014af0  pop     rdi
0x140014af1  pop     rsi
0x140014af2  pop     rbp
0x140014af3  pop     rbx
0x140014af4  retn
```
