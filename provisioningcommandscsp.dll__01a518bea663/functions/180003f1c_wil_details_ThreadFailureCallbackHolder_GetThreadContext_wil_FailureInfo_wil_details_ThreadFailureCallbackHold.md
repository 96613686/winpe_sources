# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180003f1c`
- end: `0x180003ff9`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800038e0`
- `0x180003f1c`

## callees

- `0x180003f1c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180003fe3`
- `msvcrt!memcpy_s` at `0x180003fe3`

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
0x180003f1c  push    rbx
0x180003f1e  push    rbp
0x180003f1f  push    rsi
0x180003f20  push    rdi
0x180003f21  sub     rsp, 28h
0x180003f25  xor     al, al
0x180003f27  mov     byte ptr [r8], 0
0x180003f2b  mov     rbp, r9
0x180003f2e  mov     rdi, r8
0x180003f31  mov     rsi, rdx
0x180003f34  mov     rbx, rcx
0x180003f37  test    rdx, rdx
0x180003f3a  jz      loc_180003FF0
0x180003f40  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180003f44  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003f49  mov     rdx, [rsi+20h]
0x180003f4d  test    rdx, rdx
0x180003f50  jz      loc_180003FF0
0x180003f56  cmp     dword ptr [rdx], 0
0x180003f59  jnz     short loc_180003F6C
0x180003f5b  mov     eax, 1
0x180003f60  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180003f68  inc     eax
0x180003f6a  mov     [rdx], eax
0x180003f6c  cmp     dword ptr [rbx+50h], 0
0x180003f70  jnz     short loc_180003F83
0x180003f72  movups  xmm0, xmmword ptr [rdx]
0x180003f75  movups  xmmword ptr [rbx+50h], xmm0
0x180003f79  movsd   xmm1, qword ptr [rdx+10h]
0x180003f7e  movsd   qword ptr [rbx+60h], xmm1
0x180003f83  movups  xmm0, xmmword ptr [rdx]
0x180003f86  lea     r10, [rdi+rbp]
0x180003f8a  movups  xmmword ptr [rbx+68h], xmm0
0x180003f8e  movsd   xmm1, qword ptr [rdx+10h]
0x180003f93  movsd   qword ptr [rbx+78h], xmm1
0x180003f98  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003f9c  mov     rax, rbx
0x180003f9f  inc     rax
0x180003fa2  cmp     byte ptr [rdi+rax], 0
0x180003fa6  jnz     short loc_180003F9F
0x180003fa8  lea     rcx, [rax+rdi]
0x180003fac  mov     rax, r10
0x180003faf  sub     rax, rcx
0x180003fb2  cmp     rax, 2
0x180003fb6  jle     short loc_180003FEE
0x180003fb8  mov     byte ptr [rcx], 5Ch ; '\'
0x180003fbb  lea     rdi, [rcx+1]
0x180003fbf  mov     r8, [rdx+8]; Source
0x180003fc3  inc     rbx
0x180003fc6  cmp     byte ptr [r8+rbx], 0
0x180003fcb  jnz     short loc_180003FC3
0x180003fcd  sub     r10, rdi
0x180003fd0  inc     rbx
0x180003fd3  cmp     rbx, r10
0x180003fd6  mov     rdx, r10; DestinationSize
0x180003fd9  mov     rcx, rdi; Destination
0x180003fdc  cmovnb  rbx, r10
0x180003fe0  mov     r9, rbx; SourceSize
0x180003fe3  call    cs:__imp_memcpy_s
0x180003fe9  mov     byte ptr [rbx+rdi-1], 0
0x180003fee  mov     al, 1
0x180003ff0  add     rsp, 28h
0x180003ff4  pop     rdi
0x180003ff5  pop     rsi
0x180003ff6  pop     rbp
0x180003ff7  pop     rbx
0x180003ff8  retn
```
