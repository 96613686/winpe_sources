# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180019e6c`
- end: `0x180019f49`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800193ac`
- `0x180019e6c`

## callees

- `0x180019e6c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180019f33`
- `msvcrt!memcpy_s` at `0x180019f33`

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
0x180019e6c  push    rbx
0x180019e6e  push    rbp
0x180019e6f  push    rsi
0x180019e70  push    rdi
0x180019e71  sub     rsp, 28h
0x180019e75  xor     al, al
0x180019e77  mov     byte ptr [r8], 0
0x180019e7b  mov     rbp, r9
0x180019e7e  mov     rdi, r8
0x180019e81  mov     rsi, rdx
0x180019e84  mov     rbx, rcx
0x180019e87  test    rdx, rdx
0x180019e8a  jz      loc_180019F40
0x180019e90  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180019e94  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180019e99  mov     rdx, [rsi+20h]
0x180019e9d  test    rdx, rdx
0x180019ea0  jz      loc_180019F40
0x180019ea6  cmp     dword ptr [rdx], 0
0x180019ea9  jnz     short loc_180019EBC
0x180019eab  mov     eax, 1
0x180019eb0  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180019eb8  inc     eax
0x180019eba  mov     [rdx], eax
0x180019ebc  cmp     dword ptr [rbx+50h], 0
0x180019ec0  jnz     short loc_180019ED3
0x180019ec2  movups  xmm0, xmmword ptr [rdx]
0x180019ec5  movups  xmmword ptr [rbx+50h], xmm0
0x180019ec9  movsd   xmm1, qword ptr [rdx+10h]
0x180019ece  movsd   qword ptr [rbx+60h], xmm1
0x180019ed3  movups  xmm0, xmmword ptr [rdx]
0x180019ed6  lea     r10, [rdi+rbp]
0x180019eda  movups  xmmword ptr [rbx+68h], xmm0
0x180019ede  movsd   xmm1, qword ptr [rdx+10h]
0x180019ee3  movsd   qword ptr [rbx+78h], xmm1
0x180019ee8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180019eec  mov     rax, rbx
0x180019eef  inc     rax
0x180019ef2  cmp     byte ptr [rdi+rax], 0
0x180019ef6  jnz     short loc_180019EEF
0x180019ef8  lea     rcx, [rax+rdi]
0x180019efc  mov     rax, r10
0x180019eff  sub     rax, rcx
0x180019f02  cmp     rax, 2
0x180019f06  jle     short loc_180019F3E
0x180019f08  mov     byte ptr [rcx], 5Ch ; '\'
0x180019f0b  lea     rdi, [rcx+1]
0x180019f0f  mov     r8, [rdx+8]; Source
0x180019f13  inc     rbx
0x180019f16  cmp     byte ptr [r8+rbx], 0
0x180019f1b  jnz     short loc_180019F13
0x180019f1d  sub     r10, rdi
0x180019f20  inc     rbx
0x180019f23  cmp     rbx, r10
0x180019f26  mov     rdx, r10; DestinationSize
0x180019f29  mov     rcx, rdi; Destination
0x180019f2c  cmovnb  rbx, r10
0x180019f30  mov     r9, rbx; SourceSize
0x180019f33  call    cs:__imp_memcpy_s
0x180019f39  mov     byte ptr [rbx+rdi-1], 0
0x180019f3e  mov     al, 1
0x180019f40  add     rsp, 28h
0x180019f44  pop     rdi
0x180019f45  pop     rsi
0x180019f46  pop     rbp
0x180019f47  pop     rbx
0x180019f48  retn
```
