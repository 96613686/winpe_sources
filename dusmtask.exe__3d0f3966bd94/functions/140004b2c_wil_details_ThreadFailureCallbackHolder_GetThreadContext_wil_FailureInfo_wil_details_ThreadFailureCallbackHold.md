# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140004b2c`
- end: `0x140004c08`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004430`
- `0x140004b2c`

## callees

- `0x140004b2c`
- `0x140006f88`

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
0x140004b2c  push    rbx
0x140004b2e  push    rbp
0x140004b2f  push    rsi
0x140004b30  push    rdi
0x140004b31  sub     rsp, 28h
0x140004b35  xor     al, al
0x140004b37  mov     byte ptr [r8], 0
0x140004b3b  mov     rbp, r9
0x140004b3e  mov     rdi, r8
0x140004b41  mov     rsi, rdx
0x140004b44  mov     rbx, rcx
0x140004b47  test    rdx, rdx
0x140004b4a  jz      loc_140004BFF
0x140004b50  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140004b54  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140004b59  mov     rdx, [rsi+20h]
0x140004b5d  test    rdx, rdx
0x140004b60  jz      loc_140004BFF
0x140004b66  cmp     dword ptr [rdx], 0
0x140004b69  jnz     short loc_140004B7C
0x140004b6b  mov     eax, 1
0x140004b70  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140004b78  inc     eax
0x140004b7a  mov     [rdx], eax
0x140004b7c  cmp     dword ptr [rbx+50h], 0
0x140004b80  jnz     short loc_140004B93
0x140004b82  movups  xmm0, xmmword ptr [rdx]
0x140004b85  movups  xmmword ptr [rbx+50h], xmm0
0x140004b89  movsd   xmm1, qword ptr [rdx+10h]
0x140004b8e  movsd   qword ptr [rbx+60h], xmm1
0x140004b93  movups  xmm0, xmmword ptr [rdx]
0x140004b96  lea     r10, [rdi+rbp]
0x140004b9a  movups  xmmword ptr [rbx+68h], xmm0
0x140004b9e  movsd   xmm1, qword ptr [rdx+10h]
0x140004ba3  movsd   qword ptr [rbx+78h], xmm1
0x140004ba8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140004bac  mov     rax, rbx
0x140004baf  inc     rax
0x140004bb2  cmp     byte ptr [rdi+rax], 0
0x140004bb6  jnz     short loc_140004BAF
0x140004bb8  lea     rcx, [rax+rdi]
0x140004bbc  mov     rax, r10
0x140004bbf  sub     rax, rcx
0x140004bc2  cmp     rax, 2
0x140004bc6  jle     short loc_140004BFD
0x140004bc8  mov     byte ptr [rcx], 5Ch ; '\'
0x140004bcb  lea     rdi, [rcx+1]
0x140004bcf  mov     r8, [rdx+8]; Source
0x140004bd3  inc     rbx
0x140004bd6  cmp     byte ptr [r8+rbx], 0
0x140004bdb  jnz     short loc_140004BD3
0x140004bdd  sub     r10, rdi
0x140004be0  inc     rbx
0x140004be3  cmp     rbx, r10
0x140004be6  mov     rdx, r10; DestinationSize
0x140004be9  mov     rcx, rdi; Destination
0x140004bec  cmovnb  rbx, r10
0x140004bf0  mov     r9, rbx; SourceSize
0x140004bf3  call    memcpy_s
0x140004bf8  mov     byte ptr [rbx+rdi-1], 0
0x140004bfd  mov     al, 1
0x140004bff  add     rsp, 28h
0x140004c03  pop     rdi
0x140004c04  pop     rsi
0x140004c05  pop     rbp
0x140004c06  pop     rbx
0x140004c07  retn
```
