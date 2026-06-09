# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180007110`
- end: `0x1800071e3`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `211`
- prototype: `static bool(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800069b4`
- `0x180007110`

## callees

- `0x180007110`
- `0x18000ae20`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800071cd`
- `msvcrt!memcpy_s` at `0x1800071cd`

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
0x180007110  push    rbx
0x180007112  push    rbp
0x180007113  push    rsi
0x180007114  push    rdi
0x180007115  sub     rsp, 28h
0x180007119  xor     al, al
0x18000711b  mov     byte ptr [r8], 0
0x18000711f  mov     rbp, r9
0x180007122  mov     rdi, r8
0x180007125  mov     rsi, rdx
0x180007128  mov     rbx, rcx
0x18000712b  test    rdx, rdx
0x18000712e  jz      loc_1800071DA
0x180007134  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180007138  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000713d  mov     rsi, [rsi+20h]
0x180007141  test    rsi, rsi
0x180007144  jz      loc_1800071DA
0x18000714a  cmp     dword ptr [rsi], 0
0x18000714d  jnz     short loc_180007160
0x18000714f  mov     eax, 1
0x180007154  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000715c  inc     eax
0x18000715e  mov     [rsi], eax
0x180007160  cmp     dword ptr [rbx+50h], 0
0x180007164  jnz     short loc_180007177
0x180007166  movups  xmm0, xmmword ptr [rsi]
0x180007169  movups  xmmword ptr [rbx+50h], xmm0
0x18000716d  movsd   xmm1, qword ptr [rsi+10h]
0x180007172  movsd   qword ptr [rbx+60h], xmm1
0x180007177  movups  xmm0, xmmword ptr [rsi]
0x18000717a  mov     rcx, rdi; char *
0x18000717d  add     rbp, rdi
0x180007180  movups  xmmword ptr [rbx+68h], xmm0
0x180007184  movsd   xmm1, qword ptr [rsi+10h]
0x180007189  movsd   qword ptr [rbx+78h], xmm1
0x18000718e  call    ?mqstrlen@@YAIPEBD@Z; mqstrlen(char const *)
0x180007193  mov     eax, eax
0x180007195  add     rdi, rax
0x180007198  mov     rax, rbp
0x18000719b  sub     rax, rdi
0x18000719e  cmp     rax, 2
0x1800071a2  jle     short loc_1800071D8
0x1800071a4  mov     byte ptr [rdi], 5Ch ; '\'
0x1800071a7  inc     rdi
0x1800071aa  mov     rcx, [rsi+8]; char *
0x1800071ae  sub     rbp, rdi
0x1800071b1  call    ?mqstrlen@@YAIPEBD@Z; mqstrlen(char const *)
0x1800071b6  mov     r8, [rsi+8]; Source
0x1800071ba  mov     rdx, rbp; DestinationSize
0x1800071bd  mov     rcx, rdi; Destination
0x1800071c0  lea     ebx, [rax+1]
0x1800071c3  cmp     rbx, rbp
0x1800071c6  cmovnb  rbx, rbp
0x1800071ca  mov     r9, rbx; SourceSize
0x1800071cd  call    cs:__imp_memcpy_s
0x1800071d3  mov     byte ptr [rbx+rdi-1], 0
0x1800071d8  mov     al, 1
0x1800071da  add     rsp, 28h
0x1800071de  pop     rdi
0x1800071df  pop     rsi
0x1800071e0  pop     rbp
0x1800071e1  pop     rbx
0x1800071e2  retn
```
