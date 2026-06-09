# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000544c`
- end: `0x180005529`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004da4`
- `0x18000544c`

## callees

- `0x18000544c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005513`
- `msvcrt!memcpy_s` at `0x180005513`

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
0x18000544c  push    rbx
0x18000544e  push    rbp
0x18000544f  push    rsi
0x180005450  push    rdi
0x180005451  sub     rsp, 28h
0x180005455  xor     al, al
0x180005457  mov     byte ptr [r8], 0
0x18000545b  mov     rbp, r9
0x18000545e  mov     rdi, r8
0x180005461  mov     rsi, rdx
0x180005464  mov     rbx, rcx
0x180005467  test    rdx, rdx
0x18000546a  jz      loc_180005520
0x180005470  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180005474  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005479  mov     rdx, [rsi+20h]
0x18000547d  test    rdx, rdx
0x180005480  jz      loc_180005520
0x180005486  cmp     dword ptr [rdx], 0
0x180005489  jnz     short loc_18000549C
0x18000548b  mov     eax, 1
0x180005490  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180005498  inc     eax
0x18000549a  mov     [rdx], eax
0x18000549c  cmp     dword ptr [rbx+50h], 0
0x1800054a0  jnz     short loc_1800054B3
0x1800054a2  movups  xmm0, xmmword ptr [rdx]
0x1800054a5  movups  xmmword ptr [rbx+50h], xmm0
0x1800054a9  movsd   xmm1, qword ptr [rdx+10h]
0x1800054ae  movsd   qword ptr [rbx+60h], xmm1
0x1800054b3  movups  xmm0, xmmword ptr [rdx]
0x1800054b6  lea     r10, [rdi+rbp]
0x1800054ba  movups  xmmword ptr [rbx+68h], xmm0
0x1800054be  movsd   xmm1, qword ptr [rdx+10h]
0x1800054c3  movsd   qword ptr [rbx+78h], xmm1
0x1800054c8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800054cc  mov     rax, rbx
0x1800054cf  inc     rax
0x1800054d2  cmp     byte ptr [rdi+rax], 0
0x1800054d6  jnz     short loc_1800054CF
0x1800054d8  lea     rcx, [rax+rdi]
0x1800054dc  mov     rax, r10
0x1800054df  sub     rax, rcx
0x1800054e2  cmp     rax, 2
0x1800054e6  jle     short loc_18000551E
0x1800054e8  mov     byte ptr [rcx], 5Ch ; '\'
0x1800054eb  lea     rdi, [rcx+1]
0x1800054ef  mov     r8, [rdx+8]; Source
0x1800054f3  inc     rbx
0x1800054f6  cmp     byte ptr [r8+rbx], 0
0x1800054fb  jnz     short loc_1800054F3
0x1800054fd  sub     r10, rdi
0x180005500  inc     rbx
0x180005503  cmp     rbx, r10
0x180005506  mov     rdx, r10; DestinationSize
0x180005509  mov     rcx, rdi; Destination
0x18000550c  cmovnb  rbx, r10
0x180005510  mov     r9, rbx; SourceSize
0x180005513  call    cs:__imp_memcpy_s
0x180005519  mov     byte ptr [rbx+rdi-1], 0
0x18000551e  mov     al, 1
0x180005520  add     rsp, 28h
0x180005524  pop     rdi
0x180005525  pop     rsi
0x180005526  pop     rbp
0x180005527  pop     rbx
0x180005528  retn
```
