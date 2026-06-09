# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180004930`
- end: `0x180004a0d`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004390`
- `0x180004930`

## callees

- `0x180004930`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800049f7`
- `msvcrt!memcpy_s` at `0x1800049f7`

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
0x180004930  push    rbx
0x180004932  push    rbp
0x180004933  push    rsi
0x180004934  push    rdi
0x180004935  sub     rsp, 28h
0x180004939  xor     al, al
0x18000493b  mov     byte ptr [r8], 0
0x18000493f  mov     rbp, r9
0x180004942  mov     rdi, r8
0x180004945  mov     rsi, rdx
0x180004948  mov     rbx, rcx
0x18000494b  test    rdx, rdx
0x18000494e  jz      loc_180004A04
0x180004954  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180004958  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000495d  mov     rdx, [rsi+20h]
0x180004961  test    rdx, rdx
0x180004964  jz      loc_180004A04
0x18000496a  cmp     dword ptr [rdx], 0
0x18000496d  jnz     short loc_180004980
0x18000496f  mov     eax, 1
0x180004974  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000497c  inc     eax
0x18000497e  mov     [rdx], eax
0x180004980  cmp     dword ptr [rbx+50h], 0
0x180004984  jnz     short loc_180004997
0x180004986  movups  xmm0, xmmword ptr [rdx]
0x180004989  movups  xmmword ptr [rbx+50h], xmm0
0x18000498d  movsd   xmm1, qword ptr [rdx+10h]
0x180004992  movsd   qword ptr [rbx+60h], xmm1
0x180004997  movups  xmm0, xmmword ptr [rdx]
0x18000499a  lea     r10, [rdi+rbp]
0x18000499e  movups  xmmword ptr [rbx+68h], xmm0
0x1800049a2  movsd   xmm1, qword ptr [rdx+10h]
0x1800049a7  movsd   qword ptr [rbx+78h], xmm1
0x1800049ac  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800049b0  mov     rax, rbx
0x1800049b3  inc     rax
0x1800049b6  cmp     byte ptr [rdi+rax], 0
0x1800049ba  jnz     short loc_1800049B3
0x1800049bc  lea     rcx, [rax+rdi]
0x1800049c0  mov     rax, r10
0x1800049c3  sub     rax, rcx
0x1800049c6  cmp     rax, 2
0x1800049ca  jle     short loc_180004A02
0x1800049cc  mov     byte ptr [rcx], 5Ch ; '\'
0x1800049cf  lea     rdi, [rcx+1]
0x1800049d3  mov     r8, [rdx+8]; Source
0x1800049d7  inc     rbx
0x1800049da  cmp     byte ptr [r8+rbx], 0
0x1800049df  jnz     short loc_1800049D7
0x1800049e1  sub     r10, rdi
0x1800049e4  inc     rbx
0x1800049e7  cmp     rbx, r10
0x1800049ea  mov     rdx, r10; DestinationSize
0x1800049ed  mov     rcx, rdi; Destination
0x1800049f0  cmovnb  rbx, r10
0x1800049f4  mov     r9, rbx; SourceSize
0x1800049f7  call    cs:__imp_memcpy_s
0x1800049fd  mov     byte ptr [rbx+rdi-1], 0
0x180004a02  mov     al, 1
0x180004a04  add     rsp, 28h
0x180004a08  pop     rdi
0x180004a09  pop     rsi
0x180004a0a  pop     rbp
0x180004a0b  pop     rbx
0x180004a0c  retn
```
