# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140003b34`
- end: `0x140003c11`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400034d8`
- `0x140003b34`

## callees

- `0x140003b34`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140003bfb`
- `msvcrt!memcpy_s` at `0x140003bfb`

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
0x140003b34  push    rbx
0x140003b36  push    rbp
0x140003b37  push    rsi
0x140003b38  push    rdi
0x140003b39  sub     rsp, 28h
0x140003b3d  xor     al, al
0x140003b3f  mov     byte ptr [r8], 0
0x140003b43  mov     rbp, r9
0x140003b46  mov     rdi, r8
0x140003b49  mov     rsi, rdx
0x140003b4c  mov     rbx, rcx
0x140003b4f  test    rdx, rdx
0x140003b52  jz      loc_140003C08
0x140003b58  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140003b5c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140003b61  mov     rdx, [rsi+20h]
0x140003b65  test    rdx, rdx
0x140003b68  jz      loc_140003C08
0x140003b6e  cmp     dword ptr [rdx], 0
0x140003b71  jnz     short loc_140003B84
0x140003b73  mov     eax, 1
0x140003b78  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140003b80  inc     eax
0x140003b82  mov     [rdx], eax
0x140003b84  cmp     dword ptr [rbx+50h], 0
0x140003b88  jnz     short loc_140003B9B
0x140003b8a  movups  xmm0, xmmword ptr [rdx]
0x140003b8d  movups  xmmword ptr [rbx+50h], xmm0
0x140003b91  movsd   xmm1, qword ptr [rdx+10h]
0x140003b96  movsd   qword ptr [rbx+60h], xmm1
0x140003b9b  movups  xmm0, xmmword ptr [rdx]
0x140003b9e  lea     r10, [rdi+rbp]
0x140003ba2  movups  xmmword ptr [rbx+68h], xmm0
0x140003ba6  movsd   xmm1, qword ptr [rdx+10h]
0x140003bab  movsd   qword ptr [rbx+78h], xmm1
0x140003bb0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140003bb4  mov     rax, rbx
0x140003bb7  inc     rax
0x140003bba  cmp     byte ptr [rdi+rax], 0
0x140003bbe  jnz     short loc_140003BB7
0x140003bc0  lea     rcx, [rax+rdi]
0x140003bc4  mov     rax, r10
0x140003bc7  sub     rax, rcx
0x140003bca  cmp     rax, 2
0x140003bce  jle     short loc_140003C06
0x140003bd0  mov     byte ptr [rcx], 5Ch ; '\'
0x140003bd3  lea     rdi, [rcx+1]
0x140003bd7  mov     r8, [rdx+8]; Source
0x140003bdb  inc     rbx
0x140003bde  cmp     byte ptr [r8+rbx], 0
0x140003be3  jnz     short loc_140003BDB
0x140003be5  sub     r10, rdi
0x140003be8  inc     rbx
0x140003beb  cmp     rbx, r10
0x140003bee  mov     rdx, r10; DestinationSize
0x140003bf1  mov     rcx, rdi; Destination
0x140003bf4  cmovnb  rbx, r10
0x140003bf8  mov     r9, rbx; SourceSize
0x140003bfb  call    cs:__imp_memcpy_s
0x140003c01  mov     byte ptr [rbx+rdi-1], 0
0x140003c06  mov     al, 1
0x140003c08  add     rsp, 28h
0x140003c0c  pop     rdi
0x140003c0d  pop     rsi
0x140003c0e  pop     rbp
0x140003c0f  pop     rbx
0x140003c10  retn
```
