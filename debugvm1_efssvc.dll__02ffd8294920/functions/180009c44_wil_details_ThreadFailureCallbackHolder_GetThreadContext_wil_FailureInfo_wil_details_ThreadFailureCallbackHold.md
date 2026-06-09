# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180009c44`
- end: `0x180009d21`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800096c0`
- `0x180009c44`

## callees

- `0x180009c44`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180009d0b`
- `msvcrt!memcpy_s` at `0x180009d0b`

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
0x180009c44  push    rbx
0x180009c46  push    rbp
0x180009c47  push    rsi
0x180009c48  push    rdi
0x180009c49  sub     rsp, 28h
0x180009c4d  xor     al, al
0x180009c4f  mov     byte ptr [r8], 0
0x180009c53  mov     rbp, r9
0x180009c56  mov     rdi, r8
0x180009c59  mov     rsi, rdx
0x180009c5c  mov     rbx, rcx
0x180009c5f  test    rdx, rdx
0x180009c62  jz      loc_180009D18
0x180009c68  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180009c6c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180009c71  mov     rdx, [rsi+20h]
0x180009c75  test    rdx, rdx
0x180009c78  jz      loc_180009D18
0x180009c7e  cmp     dword ptr [rdx], 0
0x180009c81  jnz     short loc_180009C94
0x180009c83  mov     eax, 1
0x180009c88  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180009c90  inc     eax
0x180009c92  mov     [rdx], eax
0x180009c94  cmp     dword ptr [rbx+50h], 0
0x180009c98  jnz     short loc_180009CAB
0x180009c9a  movups  xmm0, xmmword ptr [rdx]
0x180009c9d  movups  xmmword ptr [rbx+50h], xmm0
0x180009ca1  movsd   xmm1, qword ptr [rdx+10h]
0x180009ca6  movsd   qword ptr [rbx+60h], xmm1
0x180009cab  movups  xmm0, xmmword ptr [rdx]
0x180009cae  lea     r10, [rdi+rbp]
0x180009cb2  movups  xmmword ptr [rbx+68h], xmm0
0x180009cb6  movsd   xmm1, qword ptr [rdx+10h]
0x180009cbb  movsd   qword ptr [rbx+78h], xmm1
0x180009cc0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180009cc4  mov     rax, rbx
0x180009cc7  inc     rax
0x180009cca  cmp     byte ptr [rdi+rax], 0
0x180009cce  jnz     short loc_180009CC7
0x180009cd0  lea     rcx, [rax+rdi]
0x180009cd4  mov     rax, r10
0x180009cd7  sub     rax, rcx
0x180009cda  cmp     rax, 2
0x180009cde  jle     short loc_180009D16
0x180009ce0  mov     byte ptr [rcx], 5Ch ; '\'
0x180009ce3  lea     rdi, [rcx+1]
0x180009ce7  mov     r8, [rdx+8]; Source
0x180009ceb  inc     rbx
0x180009cee  cmp     byte ptr [r8+rbx], 0
0x180009cf3  jnz     short loc_180009CEB
0x180009cf5  sub     r10, rdi
0x180009cf8  inc     rbx
0x180009cfb  cmp     rbx, r10
0x180009cfe  mov     rdx, r10; DestinationSize
0x180009d01  mov     rcx, rdi; Destination
0x180009d04  cmovnb  rbx, r10
0x180009d08  mov     r9, rbx; SourceSize
0x180009d0b  call    cs:__imp_memcpy_s
0x180009d11  mov     byte ptr [rbx+rdi-1], 0
0x180009d16  mov     al, 1
0x180009d18  add     rsp, 28h
0x180009d1c  pop     rdi
0x180009d1d  pop     rsi
0x180009d1e  pop     rbp
0x180009d1f  pop     rbx
0x180009d20  retn
```
