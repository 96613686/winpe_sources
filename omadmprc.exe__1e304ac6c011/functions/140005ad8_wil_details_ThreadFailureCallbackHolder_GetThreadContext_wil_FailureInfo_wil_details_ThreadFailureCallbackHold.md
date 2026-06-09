# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140005ad8`
- end: `0x140005bbc`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `228`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140005460`
- `0x140005ad8`

## callees

- `0x140005ad8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140005b9f`
- `msvcrt!memcpy_s` at `0x140005b9f`

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
0x140005ad8  push    rbx
0x140005ada  push    rbp
0x140005adb  push    rsi
0x140005adc  push    rdi
0x140005add  sub     rsp, 28h
0x140005ae1  xor     al, al
0x140005ae3  mov     byte ptr [r8], 0
0x140005ae7  mov     rbp, r9
0x140005aea  mov     rdi, r8
0x140005aed  mov     rsi, rdx
0x140005af0  mov     rbx, rcx
0x140005af3  test    rdx, rdx
0x140005af6  jz      loc_140005BB2
0x140005afc  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140005b00  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140005b05  mov     rdx, [rsi+20h]
0x140005b09  test    rdx, rdx
0x140005b0c  jz      loc_140005BB2
0x140005b12  cmp     dword ptr [rdx], 0
0x140005b15  jnz     short loc_140005B28
0x140005b17  mov     eax, 1
0x140005b1c  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140005b24  inc     eax
0x140005b26  mov     [rdx], eax
0x140005b28  cmp     dword ptr [rbx+50h], 0
0x140005b2c  jnz     short loc_140005B3F
0x140005b2e  movups  xmm0, xmmword ptr [rdx]
0x140005b31  movups  xmmword ptr [rbx+50h], xmm0
0x140005b35  movsd   xmm1, qword ptr [rdx+10h]
0x140005b3a  movsd   qword ptr [rbx+60h], xmm1
0x140005b3f  movups  xmm0, xmmword ptr [rdx]
0x140005b42  lea     r10, [rdi+rbp]
0x140005b46  movups  xmmword ptr [rbx+68h], xmm0
0x140005b4a  movsd   xmm1, qword ptr [rdx+10h]
0x140005b4f  movsd   qword ptr [rbx+78h], xmm1
0x140005b54  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140005b58  mov     rax, rbx
0x140005b5b  inc     rax
0x140005b5e  cmp     byte ptr [rdi+rax], 0
0x140005b62  jnz     short loc_140005B5B
0x140005b64  lea     rcx, [rax+rdi]
0x140005b68  mov     rax, r10
0x140005b6b  sub     rax, rcx
0x140005b6e  cmp     rax, 2
0x140005b72  jle     short loc_140005BB0
0x140005b74  mov     byte ptr [rcx], 5Ch ; '\'
0x140005b77  lea     rdi, [rcx+1]
0x140005b7b  mov     r8, [rdx+8]; Source
0x140005b7f  inc     rbx
0x140005b82  cmp     byte ptr [r8+rbx], 0
0x140005b87  jnz     short loc_140005B7F
0x140005b89  sub     r10, rdi
0x140005b8c  inc     rbx
0x140005b8f  cmp     rbx, r10
0x140005b92  mov     rdx, r10; DestinationSize
0x140005b95  mov     rcx, rdi; Destination
0x140005b98  cmovnb  rbx, r10
0x140005b9c  mov     r9, rbx; SourceSize
0x140005b9f  call    cs:__imp_memcpy_s
0x140005ba6  nop     dword ptr [rax+rax+00h]
0x140005bab  mov     byte ptr [rbx+rdi-1], 0
0x140005bb0  mov     al, 1
0x140005bb2  add     rsp, 28h
0x140005bb6  pop     rdi
0x140005bb7  pop     rsi
0x140005bb8  pop     rbp
0x140005bb9  pop     rbx
0x140005bba  retn
```
