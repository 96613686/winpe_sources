# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180009d88`
- end: `0x180009e65`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009690`
- `0x180009d88`

## callees

- `0x180009d88`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180009e4f`
- `msvcrt!memcpy_s` at `0x180009e4f`

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
0x180009d88  push    rbx
0x180009d8a  push    rbp
0x180009d8b  push    rsi
0x180009d8c  push    rdi
0x180009d8d  sub     rsp, 28h
0x180009d91  xor     al, al
0x180009d93  mov     byte ptr [r8], 0
0x180009d97  mov     rbp, r9
0x180009d9a  mov     rdi, r8
0x180009d9d  mov     rsi, rdx
0x180009da0  mov     rbx, rcx
0x180009da3  test    rdx, rdx
0x180009da6  jz      loc_180009E5C
0x180009dac  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180009db0  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180009db5  mov     rdx, [rsi+20h]
0x180009db9  test    rdx, rdx
0x180009dbc  jz      loc_180009E5C
0x180009dc2  cmp     dword ptr [rdx], 0
0x180009dc5  jnz     short loc_180009DD8
0x180009dc7  mov     eax, 1
0x180009dcc  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180009dd4  inc     eax
0x180009dd6  mov     [rdx], eax
0x180009dd8  cmp     dword ptr [rbx+50h], 0
0x180009ddc  jnz     short loc_180009DEF
0x180009dde  movups  xmm0, xmmword ptr [rdx]
0x180009de1  movups  xmmword ptr [rbx+50h], xmm0
0x180009de5  movsd   xmm1, qword ptr [rdx+10h]
0x180009dea  movsd   qword ptr [rbx+60h], xmm1
0x180009def  movups  xmm0, xmmword ptr [rdx]
0x180009df2  lea     r10, [rdi+rbp]
0x180009df6  movups  xmmword ptr [rbx+68h], xmm0
0x180009dfa  movsd   xmm1, qword ptr [rdx+10h]
0x180009dff  movsd   qword ptr [rbx+78h], xmm1
0x180009e04  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180009e08  mov     rax, rbx
0x180009e0b  inc     rax
0x180009e0e  cmp     byte ptr [rdi+rax], 0
0x180009e12  jnz     short loc_180009E0B
0x180009e14  lea     rcx, [rax+rdi]
0x180009e18  mov     rax, r10
0x180009e1b  sub     rax, rcx
0x180009e1e  cmp     rax, 2
0x180009e22  jle     short loc_180009E5A
0x180009e24  mov     byte ptr [rcx], 5Ch ; '\'
0x180009e27  lea     rdi, [rcx+1]
0x180009e2b  mov     r8, [rdx+8]; Source
0x180009e2f  inc     rbx
0x180009e32  cmp     byte ptr [r8+rbx], 0
0x180009e37  jnz     short loc_180009E2F
0x180009e39  sub     r10, rdi
0x180009e3c  inc     rbx
0x180009e3f  cmp     rbx, r10
0x180009e42  mov     rdx, r10; DestinationSize
0x180009e45  mov     rcx, rdi; Destination
0x180009e48  cmovnb  rbx, r10
0x180009e4c  mov     r9, rbx; SourceSize
0x180009e4f  call    cs:__imp_memcpy_s
0x180009e55  mov     byte ptr [rbx+rdi-1], 0
0x180009e5a  mov     al, 1
0x180009e5c  add     rsp, 28h
0x180009e60  pop     rdi
0x180009e61  pop     rsi
0x180009e62  pop     rbp
0x180009e63  pop     rbx
0x180009e64  retn
```
