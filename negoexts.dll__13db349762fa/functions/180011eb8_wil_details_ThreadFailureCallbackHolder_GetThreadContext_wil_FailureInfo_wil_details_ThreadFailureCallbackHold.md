# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180011eb8`
- end: `0x180011f95`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180011708`
- `0x180011eb8`

## callees

- `0x180011eb8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180011f7f`
- `msvcrt!memcpy_s` at `0x180011f7f`

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
0x180011eb8  push    rbx
0x180011eba  push    rbp
0x180011ebb  push    rsi
0x180011ebc  push    rdi
0x180011ebd  sub     rsp, 28h
0x180011ec1  xor     al, al
0x180011ec3  mov     byte ptr [r8], 0
0x180011ec7  mov     rbp, r9
0x180011eca  mov     rdi, r8
0x180011ecd  mov     rsi, rdx
0x180011ed0  mov     rbx, rcx
0x180011ed3  test    rdx, rdx
0x180011ed6  jz      loc_180011F8C
0x180011edc  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180011ee0  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180011ee5  mov     rdx, [rsi+20h]
0x180011ee9  test    rdx, rdx
0x180011eec  jz      loc_180011F8C
0x180011ef2  cmp     dword ptr [rdx], 0
0x180011ef5  jnz     short loc_180011F08
0x180011ef7  mov     eax, 1
0x180011efc  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180011f04  inc     eax
0x180011f06  mov     [rdx], eax
0x180011f08  cmp     dword ptr [rbx+50h], 0
0x180011f0c  jnz     short loc_180011F1F
0x180011f0e  movups  xmm0, xmmword ptr [rdx]
0x180011f11  movups  xmmword ptr [rbx+50h], xmm0
0x180011f15  movsd   xmm1, qword ptr [rdx+10h]
0x180011f1a  movsd   qword ptr [rbx+60h], xmm1
0x180011f1f  movups  xmm0, xmmword ptr [rdx]
0x180011f22  lea     r10, [rdi+rbp]
0x180011f26  movups  xmmword ptr [rbx+68h], xmm0
0x180011f2a  movsd   xmm1, qword ptr [rdx+10h]
0x180011f2f  movsd   qword ptr [rbx+78h], xmm1
0x180011f34  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180011f38  mov     rax, rbx
0x180011f3b  inc     rax
0x180011f3e  cmp     byte ptr [rdi+rax], 0
0x180011f42  jnz     short loc_180011F3B
0x180011f44  lea     rcx, [rax+rdi]
0x180011f48  mov     rax, r10
0x180011f4b  sub     rax, rcx
0x180011f4e  cmp     rax, 2
0x180011f52  jle     short loc_180011F8A
0x180011f54  mov     byte ptr [rcx], 5Ch ; '\'
0x180011f57  lea     rdi, [rcx+1]
0x180011f5b  mov     r8, [rdx+8]; Source
0x180011f5f  inc     rbx
0x180011f62  cmp     byte ptr [r8+rbx], 0
0x180011f67  jnz     short loc_180011F5F
0x180011f69  sub     r10, rdi
0x180011f6c  inc     rbx
0x180011f6f  cmp     rbx, r10
0x180011f72  mov     rdx, r10; DestinationSize
0x180011f75  mov     rcx, rdi; Destination
0x180011f78  cmovnb  rbx, r10
0x180011f7c  mov     r9, rbx; SourceSize
0x180011f7f  call    cs:__imp_memcpy_s
0x180011f85  mov     byte ptr [rbx+rdi-1], 0
0x180011f8a  mov     al, 1
0x180011f8c  add     rsp, 28h
0x180011f90  pop     rdi
0x180011f91  pop     rsi
0x180011f92  pop     rbp
0x180011f93  pop     rbx
0x180011f94  retn
```
