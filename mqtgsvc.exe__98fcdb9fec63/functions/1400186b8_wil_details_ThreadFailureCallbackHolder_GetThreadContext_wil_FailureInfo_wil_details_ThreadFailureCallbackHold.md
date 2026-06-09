# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1400186b8`
- end: `0x14001878b`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `211`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140018048`
- `0x1400186b8`

## callees

- `0x14000eda0`
- `0x1400186b8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140018775`
- `msvcrt!memcpy_s` at `0x140018775`

## pseudocode

```c
bool __fastcall wil::details::ThreadFailureCallbackHolder::GetThreadContext(
        struct wil::FailureInfo *a1,
        struct wil::details::ThreadFailureCallbackHolder **a2,
        char *a3,
        unsigned __int64 a4)
{
  bool result; // al
  struct wil::details::ThreadFailureCallbackHolder *v9; // rsi
  char *v10; // rbp
  char *v11; // rdi
  _BYTE *v12; // rdi
  rsize_t v13; // rbp
  rsize_t v14; // rbx

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
      v11 = &a3[mqstrlen(a3)];
      if ( v10 - v11 > 2 )
      {
        *v11 = 92;
        v12 = v11 + 1;
        v13 = v10 - v12;
        v14 = mqstrlen(*((const char **)v9 + 1)) + 1;
        if ( v14 >= v13 )
          v14 = v13;
        memcpy_s(v12, v13, *((const void *const *)v9 + 1), v14);
        v12[v14 - 1] = 0;
      }
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400186b8  push    rbx
0x1400186ba  push    rbp
0x1400186bb  push    rsi
0x1400186bc  push    rdi
0x1400186bd  sub     rsp, 28h
0x1400186c1  xor     al, al
0x1400186c3  mov     byte ptr [r8], 0
0x1400186c7  mov     rbp, r9
0x1400186ca  mov     rdi, r8
0x1400186cd  mov     rsi, rdx
0x1400186d0  mov     rbx, rcx
0x1400186d3  test    rdx, rdx
0x1400186d6  jz      loc_140018782
0x1400186dc  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1400186e0  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400186e5  mov     rsi, [rsi+20h]
0x1400186e9  test    rsi, rsi
0x1400186ec  jz      loc_140018782
0x1400186f2  cmp     dword ptr [rsi], 0
0x1400186f5  jnz     short loc_140018708
0x1400186f7  mov     eax, 1
0x1400186fc  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140018704  inc     eax
0x140018706  mov     [rsi], eax
0x140018708  cmp     dword ptr [rbx+50h], 0
0x14001870c  jnz     short loc_14001871F
0x14001870e  movups  xmm0, xmmword ptr [rsi]
0x140018711  movups  xmmword ptr [rbx+50h], xmm0
0x140018715  movsd   xmm1, qword ptr [rsi+10h]
0x14001871a  movsd   qword ptr [rbx+60h], xmm1
0x14001871f  movups  xmm0, xmmword ptr [rsi]
0x140018722  mov     rcx, rdi; char *
0x140018725  add     rbp, rdi
0x140018728  movups  xmmword ptr [rbx+68h], xmm0
0x14001872c  movsd   xmm1, qword ptr [rsi+10h]
0x140018731  movsd   qword ptr [rbx+78h], xmm1
0x140018736  call    ?mqstrlen@@YAIPEBD@Z; mqstrlen(char const *)
0x14001873b  mov     eax, eax
0x14001873d  add     rdi, rax
0x140018740  mov     rax, rbp
0x140018743  sub     rax, rdi
0x140018746  cmp     rax, 2
0x14001874a  jle     short loc_140018780
0x14001874c  mov     byte ptr [rdi], 5Ch ; '\'
0x14001874f  inc     rdi
0x140018752  mov     rcx, [rsi+8]; char *
0x140018756  sub     rbp, rdi
0x140018759  call    ?mqstrlen@@YAIPEBD@Z; mqstrlen(char const *)
0x14001875e  mov     r8, [rsi+8]; Source
0x140018762  mov     rdx, rbp; DestinationSize
0x140018765  mov     rcx, rdi; Destination
0x140018768  lea     ebx, [rax+1]
0x14001876b  cmp     rbx, rbp
0x14001876e  cmovnb  rbx, rbp
0x140018772  mov     r9, rbx; SourceSize
0x140018775  call    cs:__imp_memcpy_s
0x14001877b  mov     byte ptr [rbx+rdi-1], 0
0x140018780  mov     al, 1
0x140018782  add     rsp, 28h
0x140018786  pop     rdi
0x140018787  pop     rsi
0x140018788  pop     rbp
0x140018789  pop     rbx
0x14001878a  retn
```
