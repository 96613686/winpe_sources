# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180005cb4`
- end: `0x180005d91`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005694`
- `0x180005cb4`

## callees

- `0x180005cb4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005d7b`
- `msvcrt!memcpy_s` at `0x180005d7b`

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
0x180005cb4  push    rbx
0x180005cb6  push    rbp
0x180005cb7  push    rsi
0x180005cb8  push    rdi
0x180005cb9  sub     rsp, 28h
0x180005cbd  xor     al, al
0x180005cbf  mov     byte ptr [r8], 0
0x180005cc3  mov     rbp, r9
0x180005cc6  mov     rdi, r8
0x180005cc9  mov     rsi, rdx
0x180005ccc  mov     rbx, rcx
0x180005ccf  test    rdx, rdx
0x180005cd2  jz      loc_180005D88
0x180005cd8  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180005cdc  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005ce1  mov     rdx, [rsi+20h]
0x180005ce5  test    rdx, rdx
0x180005ce8  jz      loc_180005D88
0x180005cee  cmp     dword ptr [rdx], 0
0x180005cf1  jnz     short loc_180005D04
0x180005cf3  mov     eax, 1
0x180005cf8  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180005d00  inc     eax
0x180005d02  mov     [rdx], eax
0x180005d04  cmp     dword ptr [rbx+50h], 0
0x180005d08  jnz     short loc_180005D1B
0x180005d0a  movups  xmm0, xmmword ptr [rdx]
0x180005d0d  movups  xmmword ptr [rbx+50h], xmm0
0x180005d11  movsd   xmm1, qword ptr [rdx+10h]
0x180005d16  movsd   qword ptr [rbx+60h], xmm1
0x180005d1b  movups  xmm0, xmmword ptr [rdx]
0x180005d1e  lea     r10, [rdi+rbp]
0x180005d22  movups  xmmword ptr [rbx+68h], xmm0
0x180005d26  movsd   xmm1, qword ptr [rdx+10h]
0x180005d2b  movsd   qword ptr [rbx+78h], xmm1
0x180005d30  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005d34  mov     rax, rbx
0x180005d37  inc     rax
0x180005d3a  cmp     byte ptr [rdi+rax], 0
0x180005d3e  jnz     short loc_180005D37
0x180005d40  lea     rcx, [rax+rdi]
0x180005d44  mov     rax, r10
0x180005d47  sub     rax, rcx
0x180005d4a  cmp     rax, 2
0x180005d4e  jle     short loc_180005D86
0x180005d50  mov     byte ptr [rcx], 5Ch ; '\'
0x180005d53  lea     rdi, [rcx+1]
0x180005d57  mov     r8, [rdx+8]; Source
0x180005d5b  inc     rbx
0x180005d5e  cmp     byte ptr [r8+rbx], 0
0x180005d63  jnz     short loc_180005D5B
0x180005d65  sub     r10, rdi
0x180005d68  inc     rbx
0x180005d6b  cmp     rbx, r10
0x180005d6e  mov     rdx, r10; DestinationSize
0x180005d71  mov     rcx, rdi; Destination
0x180005d74  cmovnb  rbx, r10
0x180005d78  mov     r9, rbx; SourceSize
0x180005d7b  call    cs:__imp_memcpy_s
0x180005d81  mov     byte ptr [rbx+rdi-1], 0
0x180005d86  mov     al, 1
0x180005d88  add     rsp, 28h
0x180005d8c  pop     rdi
0x180005d8d  pop     rsi
0x180005d8e  pop     rbp
0x180005d8f  pop     rbx
0x180005d90  retn
```
